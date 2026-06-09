# Microsoft.ReportingServices.WebServer.WebServiceHelper::GetMethods

- ea: `0x33220`
- end: `0x33303`
- name: `Microsoft.ReportingServices.WebServer.WebServiceHelper::GetMethods`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x331a0`
- `0x331e0`

## callees

- `0x33160`
- `0x33220`

## string_xrefs

- `0x33233`: `Invalid secure connection setting found in configuration file`

## pseudocode

```c

```

## disassembly

```asm
0x33220  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x33225  stloc.0
0x33226  call     class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_Configuration()
0x3322b  callvirt instance int32 [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RequireHttpsLevel()
0x33230  stloc.1
0x33231  leave.s  loc_3323E
0x33233  ldstr    aInvalidSecureC// "Invalid secure connection setting found"...
0x33238  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x3323d  throw
0x3323e  ldarg.0
0x3323f  ldc.i4.s 0x16
0x33241  callvirt instance class [mscorlib]System.Reflection.MethodInfo[] [mscorlib]System.Type::GetMethods(valuetype [mscorlib]System.Reflection.BindingFlags)
0x33246  stloc.2
0x33247  ldc.i4.0
0x33248  stloc.3
0x33249  br       loc_332E4
0x3324e  ldloc.2
0x3324f  ldloc.3
0x33250  ldelem.ref
0x33251  stloc.s  4
0x33253  ldnull
0x33254  stloc.s  5
0x33256  ldloc.s  4
0x33258  ldtoken  [System.Web.Services]System.Web.Services.WebMethodAttribute
0x3325d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33262  ldc.i4.0
0x33263  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x33268  ldloc.s  4
0x3326a  ldtoken  Microsoft.ReportingServices.WebServer.UnexposedMethodAttribute
0x3326f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33274  ldc.i4.0
0x33275  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x3327a  stloc.s  6
0x3327c  ldlen
0x3327d  brtrue.s loc_33284
0x3327f  ldloc.s  6
0x33281  ldlen
0x33282  brfalse.s loc_332E0
0x33284  ldloc.s  4
0x33286  ldtoken  Microsoft.ReportingServices.WebServer.SecureConnectionLevelAttribute
0x3328b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x33290  ldc.i4.0
0x33291  callvirt instance object[] [mscorlib]System.Reflection.MemberInfo::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x33296  stloc.s  5
0x33298  ldloc.s  5
0x3329a  ldlen
0x3329b  brtrue.s loc_332B9
0x3329d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x332a2  ldstr    aFoundMethodWit// "Found method without SecureConnectionLe"...
0x332a7  ldloc.s  4
0x332a9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x332ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x332b3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x332b8  throw
0x332b9  ldloc.s  5
0x332bb  ldc.i4.0
0x332bc  ldelem.ref
0x332bd  castclass Microsoft.ReportingServices.WebServer.SecureConnectionLevelAttribute
0x332c2  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.HttpsLevel Microsoft.ReportingServices.WebServer.SecureConnectionLevelAttribute::get_Level()
0x332c7  stloc.s  7
0x332c9  ldloc.1
0x332ca  ldc.i4.0
0x332cb  ble.s    loc_332E0
0x332cd  ldc.i4.4
0x332ce  ldloc.s  7
0x332d0  beq.s    loc_332E0
0x332d2  ldloc.0
0x332d3  ldloc.s  4
0x332d5  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x332da  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x332df  pop
0x332e0  ldloc.3
0x332e1  ldc.i4.1
0x332e2  add
0x332e3  stloc.3
0x332e4  ldloc.3
0x332e5  ldloc.2
0x332e6  ldlen
0x332e7  conv.i4
0x332e8  blt      loc_3324E
0x332ed  ldloc.0
0x332ee  ldtoken  [mscorlib]System.String
0x332f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x332f8  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x332fd  castclass string[]
0x33302  ret
```
