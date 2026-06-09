# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::PopulateControls

- ea: `0x5f30`
- end: `0x64e8`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::PopulateControls`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5eb0`

## callees

- `0x5f30`

## string_xrefs

- `0x63c1`: `;old_psId=`

## pseudocode

```c

```

## disassembly

```asm
0x5f30  ldarg.0
0x5f31  ldfld    class [System.Web]System.Web.UI.WebControls.ListBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::navItems
0x5f36  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x5f3b  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Clear()
0x5f40  ldarg.0
0x5f41  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::parentSelectBox
0x5f46  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x5f4b  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Clear()
0x5f50  ldarg.0
0x5f51  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::parentSelectBox
0x5f56  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x5f5b  ldstr    aCpRootnode// "CP_RootNode"
0x5f60  call     string [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Loc::Get(string)
0x5f65  ldstr    a0// "0"
0x5f6a  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x5f6f  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x5f74  ldstr    aNew// "new"
0x5f79  stloc.0
0x5f7a  ldstr    aNew// "new"
0x5f7f  stloc.1
0x5f80  ldc.i4.m1
0x5f81  stloc.2
0x5f82  ldnull
0x5f83  stloc.3
0x5f84  ldstr    a1_1// "-1"
0x5f89  stloc.s  4
0x5f8b  ldarg.0
0x5f8c  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x5f91  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5f96  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5f9b  ldstr    aPbe// "PBE"
0x5fa0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5fa5  stloc.s  5
0x5fa7  ldloc.s  5
0x5fa9  brfalse.s loc_5FBD
0x5fab  ldarg.2
0x5fac  ldloc.s  5
0x5fae  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::GetFile(string)
0x5fb3  stloc.s  6
0x5fb5  ldloc.s  6
0x5fb7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFile::get_ServerRelativeUrl()
0x5fbc  stloc.3
0x5fbd  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5fc2  stloc.s  7
0x5fc4  ldarg.0
0x5fc5  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::testDiv
0x5fca  ldstr    asc_21500// ""
0x5fcf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x5fd4  ldc.i4.0
0x5fd5  stloc.s  8
0x5fd7  br       loc_6360
0x5fdc  ldarg.1
0x5fdd  ldloc.s  8
0x5fdf  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection::get_Item(int32)
0x5fe4  stloc.s  9
0x5fe6  ldloc.s  9
0x5fe8  call     bool [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::IsNavNodeVisible(class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode)
0x5fed  brfalse  loc_635A
0x5ff2  ldloc.s  9
0x5ff4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x5ff9  ldloc.s  9
0x5ffb  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x6000  stloc.s  0x18
0x6002  ldloca.s 0x18
0x6004  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6009  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x600e  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x6013  stloc.s  0xA
0x6015  ldarg.0
0x6016  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlSelect Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::parentSelectBox
0x601b  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.HtmlControls.HtmlSelect::get_Items()
0x6020  ldloc.s  0xA
0x6022  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x6027  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden::.ctor()
0x602c  stloc.s  0xB
0x602e  ldloc.s  0xB
0x6030  ldloc.s  9
0x6032  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x6037  box      [mscorlib]System.Int32
0x603c  ldstr    aChildren// "_children"
0x6041  call     string [mscorlib]System.String::Concat(object, object)
0x6046  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x604b  ldloc.s  8
0x604d  ldc.i4.0
0x604e  bgt.s    loc_6057
0x6050  ldstr    a1_1// "-1"
0x6055  br.s     loc_606F
0x6057  ldarg.1
0x6058  ldloc.s  8
0x605a  ldc.i4.1
0x605b  sub
0x605c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection::get_Item(int32)
0x6061  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x6066  stloc.s  0x19
0x6068  ldloca.s 0x19
0x606a  call     instance string [mscorlib]System.Int32::ToString()
0x606f  stloc.s  0xC
0x6071  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6076  ldstr    a0123_0// "{0}:{1}:{2}:{3}"
0x607b  ldc.i4.4
0x607c  newarr   [mscorlib]System.Object
0x6081  stloc.s  0x1A
0x6083  ldloc.s  0x1A
0x6085  ldc.i4.0
0x6086  ldloc.s  9
0x6088  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x608d  box      [mscorlib]System.Int32
0x6092  stelem.ref
0x6093  ldloc.s  0x1A
0x6095  ldc.i4.1
0x6096  ldloc.s  9
0x6098  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_ParentId()
0x609d  box      [mscorlib]System.Int32
0x60a2  stelem.ref
0x60a3  ldloc.s  0x1A
0x60a5  ldc.i4.2
0x60a6  ldloc.s  8
0x60a8  box      [mscorlib]System.Int32
0x60ad  stelem.ref
0x60ae  ldloc.s  0x1A
0x60b0  ldc.i4.3
0x60b1  ldloc.s  0xC
0x60b3  stelem.ref
0x60b4  ldloc.s  0x1A
0x60b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x60bb  stloc.s  0xD
0x60bd  ldloc.s  9
0x60bf  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x60c4  ldloc.s  0xD
0x60c6  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x60cb  stloc.s  0xA
0x60cd  ldarg.0
0x60ce  ldfld    class [System.Web]System.Web.UI.WebControls.ListBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::navItems
0x60d3  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x60d8  ldloc.s  0xA
0x60da  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x60df  ldloc.3
0x60e0  ldloc.s  9
0x60e2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Url()
0x60e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x60ec  brfalse.s loc_6110
0x60ee  ldloc.s  0xA
0x60f0  ldc.i4.1
0x60f1  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Selected(bool)
0x60f6  ldloc.s  0xC
0x60f8  stloc.s  4
0x60fa  ldloc.s  9
0x60fc  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_ParentId()
0x6101  stloc.s  0x1B
0x6103  ldloca.s 0x1B
0x6105  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x610a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x610f  stloc.0
0x6110  ldloc.s  7
0x6112  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6117  ldstr    a01234_0// "{0},{1},{2},{3}, {4};"
0x611c  ldc.i4.5
0x611d  newarr   [mscorlib]System.Object
0x6122  stloc.s  0x1C
0x6124  ldloc.s  0x1C
0x6126  ldc.i4.0
0x6127  ldloc.s  9
0x6129  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x612e  stelem.ref
0x612f  ldloc.s  0x1C
0x6131  ldc.i4.1
0x6132  ldloc.s  9
0x6134  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x6139  box      [mscorlib]System.Int32
0x613e  stelem.ref
0x613f  ldloc.s  0x1C
0x6141  ldc.i4.2
0x6142  ldloc.s  8
0x6144  box      [mscorlib]System.Int32
0x6149  stelem.ref
0x614a  ldloc.s  0x1C
0x614c  ldc.i4.3
0x614d  ldloc.s  9
0x614f  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_ParentId()
0x6154  box      [mscorlib]System.Int32
0x6159  stelem.ref
0x615a  ldloc.s  0x1C
0x615c  ldc.i4.4
0x615d  ldloc.s  0xC
0x615f  stelem.ref
0x6160  ldloc.s  0x1C
0x6162  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x6167  pop
0x6168  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x616d  stloc.s  0xE
0x616f  ldc.i4.0
0x6170  stloc.s  0xF
0x6172  br       loc_62D4
0x6177  ldloc.s  9
0x6179  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Children()
0x617e  ldloc.s  0xF
0x6180  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection::get_Item(int32)
0x6185  stloc.s  0x10
0x6187  ldloc.s  0x10
0x6189  call     bool [Microsoft.SharePoint.Spx.WebSiteCore]Microsoft.SharePoint.Spx.WebsiteCore.Navigation::IsNavNodeVisible(class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode)
0x618e  brfalse  loc_62CE
0x6193  ldloc.s  0x10
0x6195  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x619a  ldloc.s  0x10
0x619c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x61a1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x61a6  ldc.i4.3
0x61a7  add
0x61a8  ldc.i4   0xA0
0x61ad  call     char [mscorlib]System.Convert::ToChar(int32)
0x61b2  callvirt instance string [mscorlib]System.String::PadLeft(int32, char)
0x61b7  ldc.i4.5
0x61b8  newarr   [mscorlib]System.String
0x61bd  stloc.s  0x1D
0x61bf  ldloc.s  0x1D
0x61c1  ldc.i4.0
0x61c2  ldloc.s  0x10
0x61c4  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x61c9  stloc.s  0x1E
0x61cb  ldloca.s 0x1E
0x61cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x61d2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x61d7  stelem.ref
0x61d8  ldloc.s  0x1D
0x61da  ldc.i4.1
0x61db  ldstr    asc_2224E// ":"
0x61e0  stelem.ref
0x61e1  ldloc.s  0x1D
0x61e3  ldc.i4.2
0x61e4  ldloc.s  0x10
0x61e6  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_ParentId()
0x61eb  stloc.s  0x1F
0x61ed  ldloca.s 0x1F
0x61ef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x61f4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x61f9  stelem.ref
0x61fa  ldloc.s  0x1D
0x61fc  ldc.i4.3
0x61fd  ldstr    asc_2224E// ":"
0x6202  stelem.ref
0x6203  ldloc.s  0x1D
0x6205  ldc.i4.4
0x6206  ldloca.s 0xF
0x6208  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x620d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6212  stelem.ref
0x6213  ldloc.s  0x1D
0x6215  call     string [mscorlib]System.String::Concat(string[])
0x621a  newobj   instance void [System.Web]System.Web.UI.WebControls.ListItem::.ctor(string, string)
0x621f  stloc.s  0x11
0x6221  ldarg.0
0x6222  ldfld    class [System.Web]System.Web.UI.WebControls.ListBox Microsoft.SharePoint.Spx.WebSite.ApplicationPages.PageNavigation::navItems
0x6227  callvirt instance class [System.Web]System.Web.UI.WebControls.ListItemCollection [System.Web]System.Web.UI.WebControls.ListControl::get_Items()
0x622c  ldloc.s  0x11
0x622e  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItemCollection::Add(class [System.Web]System.Web.UI.WebControls.ListItem)
0x6233  ldloc.3
0x6234  ldloc.s  0x10
0x6236  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Url()
0x623b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6240  brfalse.s loc_624A
0x6242  ldloc.s  0x11
0x6244  ldc.i4.1
0x6245  callvirt instance void [System.Web]System.Web.UI.WebControls.ListItem::set_Selected(bool)
0x624a  ldloc.s  0xF
0x624c  ldc.i4.0
0x624d  bgt.s    loc_6256
0x624f  ldstr    a1_1// "-1"
0x6254  br.s     loc_6274
0x6256  ldloc.s  9
0x6258  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Children()
0x625d  ldloc.s  0xF
0x625f  ldc.i4.1
0x6260  sub
0x6261  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNodeCollection::get_Item(int32)
0x6266  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x626b  stloc.s  0x20
0x626d  ldloca.s 0x20
0x626f  call     instance string [mscorlib]System.Int32::ToString()
0x6274  stloc.s  0x12
0x6276  ldloc.s  0xE
0x6278  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x627d  ldstr    a01234_0// "{0},{1},{2},{3}, {4};"
0x6282  ldc.i4.5
0x6283  newarr   [mscorlib]System.Object
0x6288  stloc.s  0x21
0x628a  ldloc.s  0x21
0x628c  ldc.i4.0
0x628d  ldloc.s  0x10
0x628f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Title()
0x6294  stelem.ref
0x6295  ldloc.s  0x21
0x6297  ldc.i4.1
0x6298  ldloc.s  0x10
0x629a  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.Navigation.SPNavigationNode::get_Id()
0x629f  box      [mscorlib]System.Int32
0x62a4  stelem.ref
0x62a5  ldloc.s  0x21
0x62a7  ldc.i4.2
0x62a8  ldloc.s  0xF
0x62aa  box      [mscorlib]System.Int32
  ... truncated ...
```
