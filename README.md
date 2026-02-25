<script>
function addNewProduct(){
let name=document.getElementById('new-name').value.trim();
let price=parseInt(document.getElementById('new-price').value);
let file=document.getElementById('new-img').files[0];

if(!name || !price){
alert("Nomi va narxni kiriting!");
return;
}

if(!file){
alert("Rasm tanlang!");
return;
}

let reader=new FileReader();

reader.onload=function(e){
let imgData=e.target.result;

products.push({
id:Date.now(),
name,
price,
img:imgData
});

saveProducts();
renderAll();

document.getElementById('new-name').value='';
document.getElementById('new-price').value='';
document.getElementById('new-img').value='';
};

reader.readAsDataURL(file);
}
</script>
