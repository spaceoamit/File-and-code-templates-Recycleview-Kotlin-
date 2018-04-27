# File-and-code-templates-Recycleview-Kotlin-
File &amp; code template for kotlin Recycleview. Generate adapter with minimum information


```
#if (${PACKAGE_NAME} && ${PACKAGE_NAME} != "")package ${PACKAGE_NAME}

#end
import android.support.v7.widget.RecyclerView
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
#parse("File Header.java")

class ${AdapterName}(private val itemList: List<${ModelClass}>, private val itemClick: (${ModelClass}) -> Unit) :
        RecyclerView.Adapter<${AdapterName}.ViewHolder>() {


    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        val layoutInflater = LayoutInflater.from(parent.context)
        return ViewHolder((layoutInflater.inflate(R.layout.${layoutName},parent, false)), itemClick)
    }

    override fun getItemCount() = itemList.size


    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        holder.bindForecast(itemList[position])
    }


    class ViewHolder(view: View, private val itemClick: (${ModelClass}) -> Unit) : RecyclerView.ViewHolder(view) {

        val yourview = view
  
        fun bindForecast(mBean: ${ModelClass}) {

            with(mBean) {
              
                yourview.setOnClickListener { itemClick(this) }
            }
             
        }

    }
}

```
