# Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromCode

- ea: `0x3e0`
- end: `0x46c`
- name: `Microsoft.BIServer.Management.WebApi.DatabaseUpgrade.DatabaseUpgrader::GetProductInfoFromCode`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2f0`

## callees

- `0x50`
- `0x70`
- `0x90`
- `0xa0`
- `0x3e0`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldarg.0
0x3e1  call     string [Microsoft.ReportingServices.UpgradeScripts]Microsoft.ReportingServices.UpgradeScripts::GetUpgradeScript(string)
0x3e6  stloc.0
0x3e7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x3ec  ldloc.0
0x3ed  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x3f2  stloc.1
0x3f3  newobj   instance void [System.Core]System.Security.Cryptography.SHA256Cng::.ctor()
0x3f8  ldloc.1
0x3f9  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.HashAlgorithm::ComputeHash(unsigned int8[])
0x3fe  stloc.2
0x3ff  ldsfld   string [mscorlib]System.String::Empty
0x404  ldloc.2
0x405  ldsfld   class [mscorlib]System.Converter`2<unsigned int8, string> <>c::<>9__3_0
0x40a  dup
0x40b  brtrue.s loc_424
0x40d  pop
0x40e  ldsfld   class <>c <>c::<>9
0x413  ldftn    instance string <>c::<GetProductInfoFromCode>b__3_0(unsigned int8 x)
0x419  newobj   instance void class [mscorlib]System.Converter`2<unsigned int8, string>::.ctor(object, native int)
0x41e  dup
0x41f  stsfld   class [mscorlib]System.Converter`2<unsigned int8, string> <>c::<>9__3_0
0x424  call     T0x2B000003
0x429  call     string [mscorlib]System.String::Join(string, string[])
0x42e  stloc.3
0x42f  newobj   instance void Microsoft.BIServer.Management.WebApi.ProductInfo::.ctor()
0x434  dup
0x435  ldloc.3
0x436  callvirt instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_DbSchemaHash(string value)
0x43b  dup
0x43c  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0x441  ldarg.1
0x442  call     instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0x447  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x44c  callvirt instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_ServerSku(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType value)
0x451  dup
0x452  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x457  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x45c  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x461  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_ProductVersion()
0x466  callvirt instance void Microsoft.BIServer.Management.WebApi.ProductInfo::set_BuildNumber(string value)
0x46b  ret
```
