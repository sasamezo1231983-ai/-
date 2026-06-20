
<div id="result"></div>
<div id="certificate" style="display:none;border:3px solid green;
padding:20px;margin-top:20px;text-align:center;background:#f0fff0;">
<h2>🏆 شهادة نجاح 🏆</h2>
<p>تهانينا! لقد اجتزت امتحان الكيمياء العضوية بنجاح.</p>
<p id="studentScore"></p>
</div>

<script>
function checkQuiz(){

const answers={
q1:"c",
q2:"b",
q3:"b",
q4:"b",
q5:"c",
q6:"b",
q7:"c",
q8:"d",
q9:"c",
q10:"a",
q11:"b",
q12:"a",
q13:"a",
q14:"b",
q15:"b",
q16:"a",
q17:"c",
q18:"c",
q19:"d",
q20:"a"
};

let score=0;
let details="<h3>التصحيح:</h3>";

for(let q in answers){

let selected=document.querySelector(
'input[name="'+q+'"]:checked'
);

if(selected){

if(selected.value===answers[q]){
score++;
details+="✅ "+q+" صحيحة<br>";
}else{
details+="❌ "+q+" خاطئة<br>";
}

}else{
details+="⚠️ "+q+" غير مجابة<br>";
}

}

let percent=(score/20)*100;

let grade="";

if(percent>=90){
grade="ممتاز";
}else if(percent>=80){
grade="جيد جداً";
}else if(percent>=70){
grade="جيد";
}else if(percent>=60){
grade="مقبول";
}else{
grade="راسب";
}

document.getElementById("result").innerHTML=
"<h2>النتيجة النهائية</h2>"+
"الدرجة: "+score+" / 20<br>"+
"النسبة المئوية: "+percent+"%<br>"+
"التقدير: "+grade+"<br><br>"+
details;

if(percent>=60){
document.getElementById("certificate").style.display="block";
document.getElementById("studentScore").innerHTML=
"النتيجة: "+score+"/20 ("+percent+"%)";
}else{
document.getElementById("certificate").style.display="none";
}
}
</script>
