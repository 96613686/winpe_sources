# System.Web.UI.Design.UserControlDesigner::GetDesignTimeHtml

- ea: `0x11fb0`
- end: `0x12539`
- name: `System.Web.UI.Design.UserControlDesigner::GetDesignTimeHtml`
- size: `1417`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x2760`
- `0x29b0`
- `0x2a10`
- `0x3150`
- `0x5640`
- `0xc040`
- `0xe3b0`
- `0xe7e0`
- `0x11ea0`
- `0x11ed0`
- `0x11f20`
- `0x11fb0`
- `0x127a0`
- `0x12ba0`
- `0x12c60`
- `0x584f0`
- `0x8eec0`
- `0x8ef40`
- `0xf0ec0`
- `0xf10d0`
- `0xf1100`

## string_xrefs

- `0x120cb`: `__aspnetUserControlCache`
- `0x120e9`: `__aspnetUserControlCache`

## pseudocode

```c

```

## disassembly

```asm
0x11fb0  ldarg.0
0x11fb1  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x11fb6  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x11fbb  brfalse  loc_12532
0x11fc0  ldarg.0
0x11fc1  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x11fc6  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x11fcb  ldtoken  System.Web.UI.Design.IWebApplication
0x11fd0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11fd5  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x11fda  castclass System.Web.UI.Design.IWebApplication
0x11fdf  stloc.0
0x11fe0  ldarg.0
0x11fe1  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x11fe6  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x11feb  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x11ff0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11ff5  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x11ffa  castclass [System]System.ComponentModel.Design.IDesignerHost
0x11fff  stloc.1
0x12000  ldloc.0
0x12001  brfalse  loc_12532
0x12006  ldloc.1
0x12007  brfalse  loc_12532
0x1200c  ldarg.0
0x1200d  call     instance class System.Web.UI.Design.WebFormsRootDesigner System.Web.UI.Design.ControlDesigner::get_RootDesigner()
0x12012  callvirt instance class System.Web.UI.Design.WebFormsReferenceManager System.Web.UI.Design.WebFormsRootDesigner::get_ReferenceManager()
0x12017  brfalse  loc_12532
0x1201c  ldarg.0
0x1201d  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x12022  castclass [System.Web]System.Web.UI.IUserControlDesignerAccessor
0x12027  stloc.2
0x12028  ldloc.2
0x12029  callvirt instance string [System.Web]System.Web.UI.IUserControlDesignerAccessor::get_TagName()
0x1202e  ldc.i4.1
0x1202f  newarr   [mscorlib]System.Char
0x12034  dup
0x12035  ldc.i4.0
0x12036  ldc.i4.s 0x3A
0x12038  stelem.i2
0x12039  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1203e  stloc.3
0x1203f  ldarg.0
0x12040  call     instance class System.Web.UI.Design.WebFormsRootDesigner System.Web.UI.Design.ControlDesigner::get_RootDesigner()
0x12045  callvirt instance class System.Web.UI.Design.WebFormsReferenceManager System.Web.UI.Design.WebFormsRootDesigner::get_ReferenceManager()
0x1204a  ldloc.3
0x1204b  ldc.i4.0
0x1204c  ldelem.ref
0x1204d  ldloc.3
0x1204e  ldc.i4.1
0x1204f  ldelem.ref
0x12050  callvirt instance string System.Web.UI.Design.WebFormsReferenceManager::GetUserControlPath(string tagPrefix, string tagName)
0x12055  stloc.s  4
0x12057  ldarg.0
0x12058  ldloc.s  4
0x1205a  call     instance string System.Web.UI.Design.UserControlDesigner::MakeAppRelativePath(string path)
0x1205f  stloc.s  4
0x12061  ldarg.0
0x12062  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x12067  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x1206c  ldtoken  [System.Web]System.Web.UI.IThemeResolutionService
0x12071  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12076  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x1207b  castclass [System.Web]System.Web.UI.IThemeResolutionService
0x12080  stloc.s  5
0x12082  ldarg.0
0x12083  ldloc.s  4
0x12085  ldloc.s  5
0x12087  call     instance string System.Web.UI.Design.UserControlDesigner::GenerateUserControlCacheKey(string userControlPath, class [System.Web]System.Web.UI.IThemeResolutionService themeService)
0x1208c  stloc.s  6
0x1208e  ldloc.s  4
0x12090  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12095  brtrue   loc_12532
0x1209a  ldnull
0x1209b  stloc.s  7
0x1209d  ldsfld   string [mscorlib]System.String::Empty
0x120a2  stloc.s  8
0x120a4  ldc.i4.0
0x120a5  stloc.s  9
0x120a7  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.Design.UserControlDesigner::_antiRecursionDictionary
0x120ac  stloc.s  0xA
0x120ae  ldloc.0
0x120af  ldtoken  [System]System.ComponentModel.Design.IDictionaryService
0x120b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x120b9  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x120be  castclass [System]System.ComponentModel.Design.IDictionaryService
0x120c3  stloc.s  0xB
0x120c5  ldloc.s  0xB
0x120c7  brfalse.s loc_12138
0x120c9  ldloc.s  0xB
0x120cb  ldstr    aAspnetusercont// "__aspnetUserControlCache"
0x120d0  callvirt instance object [System]System.ComponentModel.Design.IDictionaryService::GetValue(object)
0x120d5  castclass [mscorlib]System.Collections.IDictionary
0x120da  stloc.s  0xA
0x120dc  ldloc.s  0xA
0x120de  brtrue.s loc_120F5
0x120e0  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x120e5  stloc.s  0xA
0x120e7  ldloc.s  0xB
0x120e9  ldstr    aAspnetusercont// "__aspnetUserControlCache"
0x120ee  ldloc.s  0xA
0x120f0  callvirt instance void [System]System.ComponentModel.Design.IDictionaryService::SetValue(object, object)
0x120f5  ldloc.s  0xA
0x120f7  ldloc.s  6
0x120f9  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x120fe  castclass [System.Web]System.Web.UI.Pair
0x12103  stloc.s  0xD
0x12105  ldloc.s  0xD
0x12107  brfalse.s loc_12135
0x12109  ldloc.s  0xD
0x1210b  ldfld    object [System.Web]System.Web.UI.Pair::First
0x12110  castclass [mscorlib]System.String
0x12115  stloc.s  7
0x12117  ldloc.s  0xD
0x12119  ldfld    object [System.Web]System.Web.UI.Pair::Second
0x1211e  castclass [mscorlib]System.String
0x12123  stloc.s  8
0x12125  ldloc.s  8
0x12127  ldstr    aMvwres// "mvwres:"
0x1212c  callvirt instance bool [mscorlib]System.String::Contains(string)
0x12131  stloc.s  9
0x12133  br.s     loc_12138
0x12135  ldc.i4.1
0x12136  stloc.s  9
0x12138  ldloc.0
0x12139  ldloc.s  4
0x1213b  callvirt instance class System.Web.UI.Design.IProjectItem System.Web.UI.Design.IWebApplication::GetProjectItemFromUrl(string appRelativeUrl)
0x12140  isinst   System.Web.UI.Design.IDocumentProjectItem
0x12145  stloc.s  0xC
0x12147  ldloc.s  0xC
0x12149  brfalse  loc_12503
0x1214e  ldarg.0
0x1214f  ldc.i4.1
0x12150  stfld    bool System.Web.UI.Design.UserControlDesigner::_userControlFound
0x12155  ldloc.s  0xC
0x12157  callvirt instance class [mscorlib]System.IO.Stream System.Web.UI.Design.IDocumentProjectItem::GetContents()
0x1215c  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x12161  stloc.s  0xE
0x12163  ldloc.s  0xE
0x12165  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x1216a  stloc.s  0xF
0x1216c  ldnull
0x1216d  stloc.s  0x10
0x1216f  ldloc.s  9
0x12171  brtrue.s loc_1219C
0x12173  ldarg.0
0x12174  ldloc.s  0xF
0x12176  ldloc.s  5
0x12178  call     instance string System.Web.UI.Design.UserControlDesigner::GenerateUserControlHashCode(string contents, class [System.Web]System.Web.UI.IThemeResolutionService themeService)
0x1217d  stloc.s  0x10
0x1217f  ldloc.s  0x10
0x12181  ldloc.s  7
0x12183  ldc.i4.5
0x12184  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x12189  brfalse.s loc_12199
0x1218b  ldloc.s  0xF
0x1218d  ldstr    aAscx// ".ascx"
0x12192  callvirt instance bool [mscorlib]System.String::Contains(string)
0x12197  br.s     loc_1219A
0x12199  ldc.i4.1
0x1219a  stloc.s  9
0x1219c  ldloc.s  9
0x1219e  brfalse  loc_12520
0x121a3  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.Design.UserControlDesigner::_antiRecursionDictionary
0x121a8  ldloc.s  6
0x121aa  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x121af  brfalse.s loc_121C2
0x121b1  ldarg.0
0x121b2  ldstr    aUsercontroldes// "UserControlDesigner_CyclicError"
0x121b7  call     string System.Design.SR::GetString(string name)
0x121bc  call     instance string System.Web.UI.Design.ControlDesigner::CreateErrorDesignTimeHtml(string errorMessage)
0x121c1  ret
0x121c2  ldsfld   class [mscorlib]System.Collections.IDictionary System.Web.UI.Design.UserControlDesigner::_antiRecursionDictionary
0x121c7  ldloc.s  6
0x121c9  ldarg.0
0x121ca  ldstr    aUsercontroldes// "UserControlDesigner_CyclicError"
0x121cf  call     string System.Design.SR::GetString(string name)
0x121d4  call     instance string System.Web.UI.Design.ControlDesigner::CreateErrorDesignTimeHtml(string errorMessage)
0x121d9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x121de  ldsfld   string [mscorlib]System.String::Empty
0x121e3  stloc.s  8
0x121e5  newobj   instance void [System.Web]System.Web.UI.Pair::.ctor()
0x121ea  stloc.s  0x11
0x121ec  ldloc.s  0x10
0x121ee  brtrue.s loc_121FC
0x121f0  ldarg.0
0x121f1  ldloc.s  0xF
0x121f3  ldloc.s  5
0x121f5  call     instance string System.Web.UI.Design.UserControlDesigner::GenerateUserControlHashCode(string contents, class [System.Web]System.Web.UI.IThemeResolutionService themeService)
0x121fa  stloc.s  0x10
0x121fc  ldloc.s  0x11
0x121fe  ldloc.s  0x10
0x12200  stfld    object [System.Web]System.Web.UI.Pair::First
0x12205  ldloc.s  0x11
0x12207  ldloc.s  8
0x12209  stfld    object [System.Web]System.Web.UI.Pair::Second
0x1220e  ldloc.s  0xA
0x12210  ldloc.s  6
0x12212  ldloc.s  0x11
0x12214  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x12219  ldarg.0
0x1221a  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0x1221f  castclass [System.Web]System.Web.UI.UserControl
0x12224  stloc.s  0x12
0x12226  newobj   instance void [System.Web]System.Web.UI.Page::.ctor()
0x1222b  stloc.s  0x13
0x1222d  ldloc.s  0x13
0x1222f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x12234  ldloc.s  0x12
0x12236  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1223b  ldloc.1
0x1223c  ldloc.s  0x13
0x1223e  ldloc.s  4
0x12240  newobj   instance void UserControlDesignerHost::.ctor(class [System]System.ComponentModel.Design.IDesignerHost host, class [System]System.ComponentModel.IComponent rootComponent, string userControlPath)
0x12245  stloc.s  0x14
0x12247  ldloc.s  0xF
0x12249  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1224e  brtrue   loc_124C5
0x12253  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Web]System.Web.UI.Triplet>::.ctor()
0x12258  stloc.s  0x15
0x1225a  ldloc.s  0xF
0x1225c  ldloc.s  0x14
0x1225e  ldloc.s  0x15
0x12260  call     class [System.Web]System.Web.UI.Control[] System.Web.UI.Design.ControlSerializer::DeserializeControlsInternal(string text, class [System]System.ComponentModel.Design.IDesignerHost host, class [mscorlib]System.Collections.Generic.List`1<class [System.Web]System.Web.UI.Triplet> userControlRegisterEntries)
0x12265  stloc.s  0x16
0x12267  ldloc.s  0x16
0x12269  stloc.s  0x18
0x1226b  ldc.i4.0
0x1226c  stloc.s  0x19
0x1226e  br       loc_122F4
0x12273  ldloc.s  0x18
0x12275  ldloc.s  0x19
0x12277  ldelem.ref
0x12278  stloc.s  0x1A
0x1227a  ldloc.s  0x1A
0x1227c  isinst   [System.Web]System.Web.UI.LiteralControl
0x12281  brtrue.s loc_122E0
0x12283  ldloc.s  0x1A
0x12285  isinst   [System.Web]System.Web.UI.DesignerDataBoundLiteralControl
0x1228a  brtrue.s loc_122E0
0x1228c  ldloc.s  0x1A
0x1228e  isinst   [System.Web]System.Web.UI.DataBoundLiteralControl
0x12293  brtrue.s loc_122E0
0x12295  ldloc.s  0x1A
0x12297  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1229c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x122a1  brfalse.s loc_122D2
0x122a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x122a8  ldstr    aUsercontroldes_0// "UserControlDesigner_MissingID"
0x122ad  call     string System.Design.SR::GetString(string name)
0x122b2  ldc.i4.1
0x122b3  newarr   [mscorlib]System.Object
0x122b8  dup
0x122b9  ldc.i4.0
0x122ba  ldloc.s  0x1A
0x122bc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x122c1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x122c6  stelem.ref
0x122c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x122cc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x122d1  throw
0x122d2  ldloc.s  0x14
0x122d4  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.Design.IDesignerHost::get_Container()
0x122d9  ldloc.s  0x1A
0x122db  callvirt instance void [System]System.ComponentModel.IContainer::Add(class [System]System.ComponentModel.IComponent)
0x122e0  ldloc.s  0x12
0x122e2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x122e7  ldloc.s  0x1A
0x122e9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x122ee  ldloc.s  0x19
0x122f0  ldc.i4.1
0x122f1  add
0x122f2  stloc.s  0x19
0x122f4  ldloc.s  0x19
0x122f6  ldloc.s  0x18
0x122f8  ldlen
0x122f9  conv.i4
0x122fa  blt      loc_12273
0x122ff  ldloc.s  0x15
0x12301  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.Web]System.Web.UI.Triplet>::GetEnumerator()
0x12306  stloc.s  0x1B
0x12308  br       loc_123A6
0x1230d  ldloca.s 0x1B
0x1230f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Web]System.Web.UI.Triplet>::get_Current()
0x12314  stloc.s  0x1C
0x12316  ldloc.s  0x1C
0x12318  ldfld    object [System.Web]System.Web.UI.Triplet::First
0x1231d  castclass [mscorlib]System.String
0x12322  stloc.s  0x1D
0x12324  ldloc.s  0x1C
0x12326  ldfld    object [System.Web]System.Web.UI.Triplet::Second
0x1232b  castclass [System.Web]System.Web.UI.Pair
0x12330  stloc.s  0x1E
0x12332  ldloc.s  0x1C
0x12334  ldfld    object [System.Web]System.Web.UI.Triplet::Third
0x12339  castclass [System.Web]System.Web.UI.Pair
0x1233e  stloc.s  0x1F
0x12340  ldloc.s  0x1E
0x12342  brfalse.s loc_12374
0x12344  ldloc.s  0x1E
  ... truncated ...
```
