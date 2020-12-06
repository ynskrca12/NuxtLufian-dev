<template>
<div id="ilkdiv">       
    
       <table width="100%" >  
            <thead id="tblilk">
                <tr>
                    <td>Ürün</td> 
                    <td>Ürün Adı</td>
                    <td>Miktar</td>
                    <td>Birim Fiyat</td>
                    <td>Toplam Tutar</td>
                    <td>Sil</td>
                 </tr>
                
                 
            </thead>
            

             <tbody>   
            <tr>
                <td > <img v-if="show" width="190" src="https://www.lufian.com/lommel-spor-blazer-ceket-slim-fit-deve-tuyu-ceket-lufian-129425-37-B.jpg"> </td>
                <td ><button v-if="show" href="https://www.lufian.com/lommel-spor-blazer-ceket-slim-fit-deve-tuyu">Lommel Spor Blazer Ceket Slim Fit Deve Tüyü</button> </td>
                <td v-if="show" >Adet <button   v-if="urunMiktari > 1" v-on:click="urunMiktari--"> - </button>
				<a  class="pMiktar">{{ urunMiktari }}</a>
                
				<button  v-on:click="urunMiktari++"> + </button></td>
                <td ><p v-if="show">{{urunFiyat}} TL</p> </td>
                <td ><p v-if="show"> {{ topTutar() }} TL</p> </td>
                <td ><button @click="show= !show" >x</button></td>
            </tr>
             </tbody>
         </table>

         <ul>
            <li class="ekstra"><button class="btn-border">Sepeti Temizle</button></li>
            <li class="ekstra"><button class="btn-border">Alışverişe Devam</button></li>
            <li class="ekstra"><button class="btn-border">Resim Ekle</button></li>
            <li class="ekstra"><button class="btn-border">Alışveriş Listeme Ekle</button></li>
            <li class="ekstra"> <button  class="btn-border">Sepeti Güncelle</button></li>
         </ul>



              <div class="footerdiv">

                 <div id="divindirim">
                     <p>İndirim Kuponu</p>
                     <input type="text" id="inputtext">
                     <button id="btnuygula">UYGULA</button>
                 </div>
         
        
      
            <div id="divsatinal">  
            <lu >
                <li class="inlineli">Sepet Toplamı : {{topTutar()}} </li>
                <li class="inlineli">Genel Toplam : {{ topTutar() }}</li>
             </lu>
             
         
            </div>

             <div id="aciklama">
            <p>Sepetinizde değişiklik yaptıysanız güncellemeyi unutmayın. Ödeme ve onay sayfasına kadar satın alma işleminizi iptal edebilirsiniz.</p>

            <nuxt-link to="/üyegiris" tag="a">
                <button id="btnsatinal">Satın Al</button>
            </nuxt-link>

            </div>

         </div>
        
        
       

        


    
</div>
</template>>




<script>
export default {
    data:function () {
        return{
        
            urunFiyat:1299,
            urunMiktari:1,
            show:true
          
        }
    },
     methods:{
        topTutar:function () {
            return this.urunMiktari * this.urunFiyat
                
        
        },
        
        
            

        }
    
    
}



</script>>


<style scoped>

#tblilk{
    text-decoration:underline;
}

#ilkdiv{
    font-family: 'Jost',sans-serif;
}

.footerdiv{
    margin: 1em;
}


td{
    text-align: center;
}

table{
    border:none
}

.btn-border{
    border: 1px solid whitesmoke;
    background-color:gray ;
    margin-top: 10px;
    display: inline;
    font-family: 'Jost',sans-serif;
    color:black;
    width: 11em;
    font-size: 14px;
    background-color: whitesmoke;

   
}

#divindirim{
    background-color: whitesmoke;
    width: 75%;
    height: 70px;
}

#inputtext{
    width: 73%;
    background-color: white;
    height: 40px;
    margin-top: 5px;
    margin-right: 5px;
}

#inputsubmit{
     width: 24%;
     background-color:gray
}

#divsatinal{
    width: 23%;
    position: absolute;
    top: 63%;
    right: 0;
    background-color: white;
    height: 102px
}

#btnsatinal{
    float: right;
    margin-right: 1em;
    padding: 0px 25px;
    background-color: #101341;
    width: 23%;
    color: white;
    height: 3em;
    font-size: 16px;
    margin-top: -15px;
}

#btnuygula{
      
    padding: 0px 25px;
    background-color: gray;
    width: 14em ;
    color: white;
    height: 2em;
    display: inline;
}

.ekstra{
    display: inline;
    margin: 0px;
   
}

.inlineli{
    display: block;
    margin: 25px;
}

#aciklama{
    font-family: 'Jost',sans-serif;
    margin-left: 1em;
    margin-top: 30px;
    font-size: 12px;
}

 .pMiktar{
        padding: 5px;
        margin-left: 5px;
        margin-right: 5px;
    }


</style>