#MainActivity.java
package com.example.sid;

import android.os.Bundle;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.ListView;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import com.example.sid.R;

public class MainActivity extends AppCompatActivity {
    int IMAGES[]={R.drawable.apple,R.drawable.guava,R.drawable.mango,R.drawable.orange};
    String ID[]={"1","2","3","4"};
    String NAME[]={"Apple","Guava","Mango","Orange"};
    String CATEGORY[]={"Fruit","Fruit","Fruit","Fruit"};
    String PRICE[]={"180/kg","80/kg","180/kg","100/kg"};



    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        ListView listView=(ListView)findViewById(R.id.listView);
        CustomAdapter CA=new CustomAdapter();
        listView.setAdapter(CA);

    }

    class CustomAdapter extends BaseAdapter{

        @Override
        public int getCount() {
            return IMAGES.length;
        }

        @Override
        public Object getItem(int position) {
            return null;
        }

        @Override
        public long getItemId(int position) {
            return 0;
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            convertView=getLayoutInflater().inflate(R.layout.customlayout,null);

            ImageView imageView=(ImageView)convertView.findViewById(R.id.imageView);
            TextView id=(TextView)convertView.findViewById(R.id.textView);
            TextView name=(TextView)convertView.findViewById(R.id.textView2);
            TextView category=(TextView)convertView.findViewById(R.id.textView3);
            TextView price=(TextView)convertView.findViewById(R.id.textView4);

            imageView.setImageResource(IMAGES[position]);
            id.setText(ID[position]);
            name.setText(NAME[position]);
            category.setText(CATEGORY[position]);
            price.setText(PRICE[position]);

            return convertView;
        }
    }
}

#customlayout.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent" android:layout_height="match_parent">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="75dp"
        android:layout_height="150dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="43dp"
        android:layout_marginLeft="43dp"
        android:layout_marginTop="55dp"
        android:src="@mipmap/ic_launcher"
        tools:srcCompat="@tools:sample/avatars" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="Large Text"
        android:id="@+id/textView"
        android:layout_alignTop="@+id/imageView"
        android:layout_alignParentRight="true"
        android:layout_alignParentEnd="true"
        android:layout_marginRight="51dp"
        android:layout_marginEnd="51dp" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="Large Text"
        android:id="@+id/textView2"
        android:layout_below="@+id/textView"
        android:layout_alignRight="@+id/textView"
        android:layout_alignEnd="@+id/textView" />
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="Large Text"
        android:id="@+id/textView3"
        android:layout_below="@+id/textView2"
        android:layout_alignRight="@+id/textView2"
        android:layout_alignEnd="@+id/textView2" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="Large Text"
        android:id="@+id/textView4"
        android:layout_below="@+id/textView3"
        android:layout_alignRight="@+id/textView3"
        android:layout_alignEnd="@+id/textView3" />
</RelativeLayout>

#activity_main.xml
