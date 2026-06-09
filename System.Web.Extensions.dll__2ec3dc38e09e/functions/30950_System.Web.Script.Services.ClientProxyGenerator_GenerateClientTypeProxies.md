# System.Web.Script.Services.ClientProxyGenerator::GenerateClientTypeProxies

- ea: `0x30950`
- end: `0x30a61`
- name: `System.Web.Script.Services.ClientProxyGenerator::GenerateClientTypeProxies`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x2fcc0`

## callees

- `0x2e050`
- `0x2ee40`
- `0x2ef30`
- `0x2f6b0`
- `0x2f6c0`
- `0x30950`
- `0x30c10`
- `0x30c20`
- `0x30cc0`
- `0x30d10`

## string_xrefs

- `0x30973`: `var gtc = Sys.Net.WebServiceProxy._generateTypedConstructor;\n`

## pseudocode

```c

```

## disassembly

```asm
0x30950  ldc.i4.1
0x30951  stloc.0
0x30952  ldarg.1
0x30953  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Script.Services.WebServiceTypeData> System.Web.Script.Services.WebServiceData::get_ClientTypes()
0x30958  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class System.Web.Script.Services.WebServiceTypeData>::GetEnumerator()
0x3095d  stloc.1
0x3095e  br       loc_30A49
0x30963  ldloc.1
0x30964  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class System.Web.Script.Services.WebServiceTypeData>::get_Current()
0x30969  stloc.2
0x3096a  ldloc.0
0x3096b  brfalse.s loc_30980
0x3096d  ldarg.0
0x3096e  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30973  ldstr    aVarGtcSysNetWe// "var gtc = Sys.Net.WebServiceProxy._gene"...
0x30978  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3097d  pop
0x3097e  ldc.i4.0
0x3097f  stloc.0
0x30980  ldarg.1
0x30981  ldloc.2
0x30982  callvirt instance string System.Web.Script.Services.WebServiceData::GetTypeStringRepresentation(class System.Web.Script.Services.WebServiceTypeData typeData)
0x30987  stloc.3
0x30988  ldarg.0
0x30989  ldloc.2
0x3098a  callvirt instance string System.Web.Script.Services.WebServiceTypeData::get_TypeName()
0x3098f  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetClientTypeNamespace(string ns)
0x30994  stloc.s  4
0x30996  ldloc.s  4
0x30998  call     string System.Web.Script.Services.ServicesUtilities::GetClientTypeName(string name)
0x3099d  stloc.s  5
0x3099f  ldarg.0
0x309a0  ldloc.2
0x309a1  callvirt instance string System.Web.Script.Services.WebServiceTypeData::get_TypeNamespace()
0x309a6  callvirt instance string System.Web.Script.Services.ClientProxyGenerator::GetClientTypeNamespace(string ns)
0x309ab  stloc.s  6
0x309ad  ldarg.0
0x309ae  ldloc.2
0x309af  callvirt instance string System.Web.Script.Services.WebServiceTypeData::get_TypeNamespace()
0x309b4  call     instance void System.Web.Script.Services.ClientProxyGenerator::EnsureNamespace(string ns)
0x309b9  ldarg.0
0x309ba  ldloc.s  6
0x309bc  ldloc.s  5
0x309be  call     instance void System.Web.Script.Services.ClientProxyGenerator::EnsureObjectGraph(string namespacePart, string typeName)
0x309c3  ldarg.0
0x309c4  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x309c9  ldstr    aIfTypeof// "if (typeof("
0x309ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x309d3  ldloc.s  5
0x309d5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x309da  ldstr    aUndefined// ") === 'undefined') {\r\n"
0x309df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x309e4  pop
0x309e5  ldarg.0
0x309e6  ldloc.s  6
0x309e8  ldloc.s  4
0x309ea  ldc.i4.0
0x309eb  ldc.i4.0
0x309ec  call     instance void System.Web.Script.Services.ClientProxyGenerator::AppendClientTypeDeclaration(string ns, string typeName, bool genClass, bool ensureNS)
0x309f1  ldarg.0
0x309f2  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x309f7  ldstr    aGtc// "gtc(\""
0x309fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a01  pop
0x30a02  ldarg.0
0x30a03  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30a08  ldloc.3
0x30a09  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a0e  pop
0x30a0f  ldarg.0
0x30a10  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30a15  ldstr    asc_4C358// "\");\r\n"
0x30a1a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a1f  pop
0x30a20  ldarg.0
0x30a21  ldfld    class [mscorlib]System.Text.StringBuilder System.Web.Script.Services.ClientProxyGenerator::_builder
0x30a26  ldloc.s  5
0x30a28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a2d  ldstr    aRegisterclass// ".registerClass('"
0x30a32  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a37  ldloc.s  5
0x30a39  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a3e  ldstr    asc_4C63C// "');\r\n}\r\n"
0x30a43  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x30a48  pop
0x30a49  ldloc.1
0x30a4a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x30a4f  brtrue   loc_30963
0x30a54  leave.s  loc_30A60
0x30a56  ldloc.1
0x30a57  brfalse.s loc_30A5F
0x30a59  ldloc.1
0x30a5a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x30a5f  endfinally
0x30a60  ret
```
