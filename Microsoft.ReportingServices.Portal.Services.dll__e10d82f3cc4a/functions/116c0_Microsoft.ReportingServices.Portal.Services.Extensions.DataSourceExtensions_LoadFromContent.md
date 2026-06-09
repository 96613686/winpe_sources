# Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::LoadFromContent

- ea: `0x116c0`
- end: `0x126c8`
- name: `Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions::LoadFromContent`
- size: `4104`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2850`
- `0x49e0`

## callees

- `0x116c0`
- `0x221d0`

## string_xrefs

- `0x11cba`: `Extension`
- `0x11d5e`: `Extension`
- `0x124bd`: `IntegratedSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x116c0  ldarg.0
0x116c1  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x116c6  brfalse  loc_126C7
0x116cb  ldarg.0
0x116cc  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x116d1  ldlen
0x116d2  brfalse  loc_126C7
0x116d7  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x116dc  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x116e1  ldarg.0
0x116e2  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x116e7  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x116ec  stloc.0
0x116ed  ldloc.0
0x116ee  ldloc.0
0x116ef  ldstr    asc_28492// "<"
0x116f4  callvirt instance int32 [mscorlib]System.String::IndexOf(string)
0x116f9  callvirt instance string [mscorlib]System.String::Substring(int32)
0x116fe  stloc.0
0x116ff  dup
0x11700  ldloc.0
0x11701  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentString(class [System.Xml]System.Xml.XmlDocument, string)
0x11706  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1170b  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeXmlNode(class [System.Xml]System.Xml.XmlNode)
0x11710  stloc.1
0x11711  ldloc.1
0x11712  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0x11717  stloc.2
0x11718  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__7
0x1171d  brtrue.s loc_1174B
0x1171f  ldc.i4.0
0x11720  ldc.i4.s 0x53
0x11722  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11727  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1172c  ldc.i4.1
0x1172d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x11732  dup
0x11733  ldc.i4.0
0x11734  ldc.i4.0
0x11735  ldnull
0x11736  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x1173b  stelem.ref
0x1173c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::UnaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x11741  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x11746  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__7
0x1174b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__7
0x11750  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x11755  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__7
0x1175a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__1
0x1175f  brtrue.s loc_11797
0x11761  ldc.i4.0
0x11762  ldc.i4.s 0x23
0x11764  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11769  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1176e  ldc.i4.2
0x1176f  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x11774  dup
0x11775  ldc.i4.0
0x11776  ldc.i4.0
0x11777  ldnull
0x11778  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x1177d  stelem.ref
0x1177e  dup
0x1177f  ldc.i4.1
0x11780  ldc.i4.2
0x11781  ldnull
0x11782  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11787  stelem.ref
0x11788  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::BinaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x1178d  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x11792  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__1
0x11797  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__1
0x1179c  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x117a1  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__1
0x117a6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__0
0x117ab  brtrue.s loc_117DC
0x117ad  ldc.i4.0
0x117ae  ldstr    aRptdatasource// "RptDataSource"
0x117b3  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x117b8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x117bd  ldc.i4.1
0x117be  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x117c3  dup
0x117c4  ldc.i4.0
0x117c5  ldc.i4.0
0x117c6  ldnull
0x117c7  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x117cc  stelem.ref
0x117cd  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x117d2  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x117d7  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__0
0x117dc  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__0
0x117e1  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x117e6  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__0
0x117eb  ldloc.2
0x117ec  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x117f1  ldnull
0x117f2  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x117f7  stloc.3
0x117f8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__6
0x117fd  brtrue.s loc_1182B
0x117ff  ldc.i4.0
0x11800  ldc.i4.s 0x54
0x11802  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11807  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1180c  ldc.i4.1
0x1180d  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x11812  dup
0x11813  ldc.i4.0
0x11814  ldc.i4.0
0x11815  ldnull
0x11816  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x1181b  stelem.ref
0x1181c  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::UnaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x11821  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x11826  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__6
0x1182b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__6
0x11830  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Target
0x11835  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__6
0x1183a  ldloc.3
0x1183b  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x11840  brtrue   loc_1197F
0x11845  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__5
0x1184a  brtrue.s loc_11881
0x1184c  ldc.i4.8
0x1184d  ldc.i4.2
0x1184e  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11853  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11858  ldc.i4.2
0x11859  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x1185e  dup
0x1185f  ldc.i4.0
0x11860  ldc.i4.0
0x11861  ldnull
0x11862  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11867  stelem.ref
0x11868  dup
0x11869  ldc.i4.1
0x1186a  ldc.i4.0
0x1186b  ldnull
0x1186c  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11871  stelem.ref
0x11872  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::BinaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x11877  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x1187c  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__5
0x11881  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__5
0x11886  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x1188b  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__5
0x11890  ldloc.3
0x11891  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__4
0x11896  brtrue.s loc_118CE
0x11898  ldc.i4.0
0x11899  ldc.i4.s 0x23
0x1189b  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x118a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x118a5  ldc.i4.2
0x118a6  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x118ab  dup
0x118ac  ldc.i4.0
0x118ad  ldc.i4.0
0x118ae  ldnull
0x118af  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x118b4  stelem.ref
0x118b5  dup
0x118b6  ldc.i4.1
0x118b7  ldc.i4.2
0x118b8  ldnull
0x118b9  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x118be  stelem.ref
0x118bf  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::BinaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x118c4  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Create(!!T0)
0x118c9  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__4
0x118ce  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__4
0x118d3  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>>::Target
0x118d8  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>> <>o__15::<>p__4
0x118dd  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__3
0x118e2  brtrue.s loc_11913
0x118e4  ldc.i4.0
0x118e5  ldstr    aConnectionprop// "ConnectionProperties"
0x118ea  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x118ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x118f4  ldc.i4.1
0x118f5  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x118fa  dup
0x118fb  ldc.i4.0
0x118fc  ldc.i4.0
0x118fd  ldnull
0x118fe  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11903  stelem.ref
0x11904  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x11909  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x1190e  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__3
0x11913  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__3
0x11918  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x1191d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__3
0x11922  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__2
0x11927  brtrue.s loc_11958
0x11929  ldc.i4.0
0x1192a  ldstr    aRptdatasource// "RptDataSource"
0x1192f  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11934  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11939  ldc.i4.1
0x1193a  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x1193f  dup
0x11940  ldc.i4.0
0x11941  ldc.i4.0
0x11942  ldnull
0x11943  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11948  stelem.ref
0x11949  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x1194e  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x11953  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__2
0x11958  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__2
0x1195d  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x11962  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__2
0x11967  ldloc.2
0x11968  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x1196d  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x11972  ldnull
0x11973  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x11978  callvirt instance var<u1> class [mscorlib]System.Func`4<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object, object>::Invoke(char, var<u1>, !!T0)
0x1197d  br.s     loc_11980
0x1197f  ldloc.3
0x11980  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>::Invoke(bool, var<u1>)
0x11985  brfalse  loc_12519
0x1198a  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__9
0x1198f  brtrue.s loc_119C0
0x11991  ldc.i4.0
0x11992  ldstr    aConnectionprop// "ConnectionProperties"
0x11997  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x1199c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x119a1  ldc.i4.1
0x119a2  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x119a7  dup
0x119a8  ldc.i4.0
0x119a9  ldc.i4.0
0x119aa  ldnull
0x119ab  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x119b0  stelem.ref
0x119b1  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x119b6  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x119bb  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__9
0x119c0  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__9
0x119c5  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x119ca  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__9
0x119cf  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__8
0x119d4  brtrue.s loc_11A05
0x119d6  ldc.i4.0
0x119d7  ldstr    aRptdatasource// "RptDataSource"
0x119dc  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x119e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x119e6  ldc.i4.1
0x119e7  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x119ec  dup
0x119ed  ldc.i4.0
0x119ee  ldc.i4.0
0x119ef  ldnull
0x119f0  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x119f5  stelem.ref
0x119f6  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::GetMember(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, string, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x119fb  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Create(!!T0)
0x11a00  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__8
0x11a05  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__8
0x11a0a  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>>::Target
0x11a0f  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>> <>o__15::<>p__8
0x11a14  ldloc.2
0x11a15  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x11a1a  callvirt instance var<u1> class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, object>::Invoke(bool, var<u1>)
0x11a1f  stloc.s  4
0x11a21  ldarg.0
0x11a22  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__15::<>p__15
0x11a27  brtrue.s loc_11A4D
0x11a29  ldc.i4.0
0x11a2a  ldtoken  [mscorlib]System.String
0x11a2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11a34  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11a39  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11a3e  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::Convert(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11a43  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Create(!!T0)
0x11a48  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__15::<>p__15
0x11a4d  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__15::<>p__15
0x11a52  ldfld    var<u1> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>>::Target
0x11a57  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, string>> <>o__15::<>p__15
0x11a5c  ldsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__12
0x11a61  brtrue.s loc_11A8F
0x11a63  ldc.i4.0
0x11a64  ldc.i4.s 0x53
0x11a66  ldtoken  Microsoft.ReportingServices.Portal.Services.Extensions.DataSourceExtensions
0x11a6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11a70  ldc.i4.1
0x11a71  newarr   [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo
0x11a76  dup
0x11a77  ldc.i4.0
0x11a78  ldc.i4.0
0x11a79  ldnull
0x11a7a  call     class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo::Create(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfoFlags, string)
0x11a7f  stelem.ref
0x11a80  call     class [System.Core]System.Runtime.CompilerServices.CallSiteBinder [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.Binder::UnaryOperation(valuetype [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpBinderFlags, valuetype [System.Core]System.Linq.Expressions.ExpressionType, class [mscorlib]System.Type, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.CSharp]Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo>)
0x11a85  call     class [System.Core]System.Runtime.CompilerServices.CallSite`1<var<u1>> class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>>::Create(!!T0)
0x11a8a  stsfld   class [System.Core]System.Runtime.CompilerServices.CallSite`1<class [mscorlib]System.Func`3<class [System.Core]System.Runtime.CompilerServices.CallSite, object, bool>> <>o__15::<>p__12
  ... truncated ...
```
