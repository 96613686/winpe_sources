# System.Web.UI.Design.WebControls.CreateDataSourceDialog::InitializePanelControls

- ea: `0x197d0`
- end: `0x199bf`
- name: `System.Web.UI.Design.WebControls.CreateDataSourceDialog::InitializePanelControls`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x193b0`

## callees

- `0x19770`
- `0x19790`
- `0x197b0`
- `0x197d0`
- `0x19ad0`
- `0x52320`
- `0x526f0`
- `0x8ef40`
- `0xef310`
- `0xf5c50`

## string_xrefs

- `0x197d6`: `CreateDataSource_SelectType`
- `0x197eb`: `CreateDataSource_ID`
- `0x19807`: `CreateDataSource_Title`
- `0x1981c`: `CreateDataSource_SelectTypeDesc`
- `0x1982c`: `CreateDataSource_Description`
- `0x19841`: `CreateDataSource_Caption`

## pseudocode

```c

```

## disassembly

```asm
0x197d0  ldarg.0
0x197d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.CreateDataSourceDialog::_selectLabel
0x197d6  ldstr    aCreatedatasour_1// "CreateDataSource_SelectType"
0x197db  call     string System.Design.SR::GetString(string name)
0x197e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x197e5  ldarg.0
0x197e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.CreateDataSourceDialog::_idLabel
0x197eb  ldstr    aCreatedatasour_2// "CreateDataSource_ID"
0x197f0  call     string System.Design.SR::GetString(string name)
0x197f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x197fa  ldarg.0
0x197fb  call     instance class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.Util.TaskForm::get_OKButton()
0x19800  ldc.i4.0
0x19801  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x19806  ldarg.0
0x19807  ldstr    aCreatedatasour_3// "CreateDataSource_Title"
0x1980c  call     string System.Design.SR::GetString(string name)
0x19811  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x19816  ldarg.0
0x19817  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.CreateDataSourceDialog::_descriptionBox
0x1981c  ldstr    aCreatedatasour_4// "CreateDataSource_SelectTypeDesc"
0x19821  call     string System.Design.SR::GetString(string name)
0x19826  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1982b  ldarg.0
0x1982c  ldstr    aCreatedatasour_5// "CreateDataSource_Description"
0x19831  call     string System.Design.SR::GetString(string name)
0x19836  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x1983b  ldarg.0
0x1983c  call     instance class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.Util.TaskFormBase::get_CaptionLabel()
0x19841  ldstr    aCreatedatasour_6// "CreateDataSource_Caption"
0x19846  call     string System.Design.SR::GetString(string name)
0x1984b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x19850  ldarg.0
0x19851  call     instance void System.Web.UI.Design.WebControls.CreateDataSourceDialog::UpdateFonts()
0x19856  ldarg.0
0x19857  call     instance class [System]System.ComponentModel.ISite System.Web.UI.Design.WebControls.CreateDataSourceDialog::GetSite()
0x1985c  stloc.0
0x1985d  ldloc.0
0x1985e  brfalse  loc_199BE
0x19863  ldloc.0
0x19864  ldtoken  [System]System.ComponentModel.Design.IComponentDiscoveryService
0x19869  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1986e  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x19873  castclass [System]System.ComponentModel.Design.IComponentDiscoveryService
0x19878  stloc.1
0x19879  ldloc.0
0x1987a  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x1987f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19884  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x19889  castclass [System]System.ComponentModel.Design.IDesignerHost
0x1988e  stloc.2
0x1988f  ldloc.1
0x19890  brfalse  loc_199BE
0x19895  ldloc.1
0x19896  ldloc.2
0x19897  ldarg.0
0x19898  ldfld    class [mscorlib]System.Type System.Web.UI.Design.WebControls.CreateDataSourceDialog::_dataSourceType
0x1989d  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.IComponentDiscoveryService::GetComponentTypes(class [System]System.ComponentModel.Design.IDesignerHost, class [mscorlib]System.Type)
0x198a2  stloc.3
0x198a3  ldloc.3
0x198a4  brfalse  loc_199BE
0x198a9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ImageList::.ctor()
0x198ae  stloc.s  4
0x198b0  ldloc.s  4
0x198b2  ldc.i4.s 0x20
0x198b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList::set_ColorDepth(valuetype [System.Windows.Forms]System.Windows.Forms.ColorDepth)
0x198b9  ldarg.0
0x198ba  call     instance bool System.Web.UI.Design.WebControls.CreateDataSourceDialog::IsTargetFramework45OrAbove()
0x198bf  stloc.s  5
0x198c1  ldloc.3
0x198c2  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x198c7  newarr   [mscorlib]System.Type
0x198cc  stloc.s  6
0x198ce  ldloc.3
0x198cf  ldloc.s  6
0x198d1  ldc.i4.0
0x198d2  callvirt instance void [mscorlib]System.Collections.ICollection::CopyTo(class [mscorlib]System.Array, int32)
0x198d7  ldloc.s  6
0x198d9  stloc.s  7
0x198db  ldc.i4.0
0x198dc  stloc.s  8
0x198de  br       loc_1999B
0x198e3  ldloc.s  7
0x198e5  ldloc.s  8
0x198e7  ldelem.ref
0x198e8  stloc.s  9
0x198ea  ldarg.0
0x198eb  ldloc.s  9
0x198ed  call     instance bool System.Web.UI.Design.WebControls.CreateDataSourceDialog::IsSupportedInTargetFramework(class [mscorlib]System.Type type)
0x198f2  brfalse  loc_19995
0x198f7  ldloc.s  9
0x198f9  call     class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.TypeDescriptor::GetAttributes(class [mscorlib]System.Type)
0x198fe  stloc.s  0xA
0x19900  ldnull
0x19901  stloc.s  0xB
0x19903  ldloc.s  0xA
0x19905  brfalse.s loc_19942
0x19907  ldloc.s  0xA
0x19909  ldtoken  [System.Drawing]System.Drawing.ToolboxBitmapAttribute
0x1990e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19913  callvirt instance class [mscorlib]System.Attribute [System]System.ComponentModel.AttributeCollection::get_Item(class [mscorlib]System.Type)
0x19918  isinst   [System.Drawing]System.Drawing.ToolboxBitmapAttribute
0x1991d  stloc.s  0xC
0x1991f  ldloc.s  0xC
0x19921  brfalse.s loc_19942
0x19923  ldloc.s  0xC
0x19925  ldsfld   class [System.Drawing]System.Drawing.ToolboxBitmapAttribute [System.Drawing]System.Drawing.ToolboxBitmapAttribute::Default
0x1992a  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1992f  brtrue.s loc_19942
0x19931  ldloc.s  0xC
0x19933  ldloc.s  9
0x19935  ldc.i4.1
0x19936  callvirt instance class [System.Drawing]System.Drawing.Image [System.Drawing]System.Drawing.ToolboxBitmapAttribute::GetImage(class [mscorlib]System.Type, bool)
0x1993b  isinst   [System.Drawing]System.Drawing.Bitmap
0x19940  stloc.s  0xB
0x19942  ldloc.s  0xB
0x19944  brtrue.s loc_19958
0x19946  ldarg.0
0x19947  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1994c  ldstr    aCustomdatasour// "CustomDataSource.bmp"
0x19951  call     class [System.Drawing]System.Drawing.Bitmap System.Drawing.BitmapSelector::CreateBitmap(class [mscorlib]System.Type type, string originalName)
0x19956  stloc.s  0xB
0x19958  ldloc.s  4
0x1995a  ldc.i4.s 0x20
0x1995c  ldc.i4.s 0x20
0x1995e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x19963  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList::set_ImageSize(valuetype [System.Drawing]System.Drawing.Size)
0x19968  ldloc.s  4
0x1996a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection [System.Windows.Forms]System.Windows.Forms.ImageList::get_Images()
0x1996f  ldloc.s  9
0x19971  callvirt instance string [mscorlib]System.Type::get_FullName()
0x19976  ldloc.s  0xB
0x19978  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ImageList/ImageCollection::Add(string, class [System.Drawing]System.Drawing.Image)
0x1997d  ldarg.0
0x1997e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.CreateDataSourceDialog::_dataSourceTypesListView
0x19983  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x19988  ldloc.s  9
0x1998a  newobj   instance void DataSourceListViewItem::.ctor(class [mscorlib]System.Type dataSourceType)
0x1998f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListViewItem [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ListViewItem)
0x19994  pop
0x19995  ldloc.s  8
0x19997  ldc.i4.1
0x19998  add
0x19999  stloc.s  8
0x1999b  ldloc.s  8
0x1999d  ldloc.s  7
0x1999f  ldlen
0x199a0  conv.i4
0x199a1  blt      loc_198E3
0x199a6  ldarg.0
0x199a7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.CreateDataSourceDialog::_dataSourceTypesListView
0x199ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::Sort()
0x199b1  ldarg.0
0x199b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.CreateDataSourceDialog::_dataSourceTypesListView
0x199b7  ldloc.s  4
0x199b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_LargeImageList(class [System.Windows.Forms]System.Windows.Forms.ImageList)
0x199be  ret
```
