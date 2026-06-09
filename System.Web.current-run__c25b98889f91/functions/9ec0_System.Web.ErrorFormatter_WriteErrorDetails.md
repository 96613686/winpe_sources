# System.Web.ErrorFormatter::WriteErrorDetails

- ea: `0x9ec0`
- end: `0xa034`
- name: `System.Web.ErrorFormatter::WriteErrorDetails`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x9bf0`
- `0xbcd0`

## callees

- `0x9ec0`
- `0xa040`
- `0xa100`
- `0xa120`
- `0xa2a0`
- `0xa2d0`
- `0xa2e0`
- `0x23fc0`
- `0x24240`
- `0x34fa0`

## string_xrefs

- `0x9f42`: `additionalConfigurationErrors`
- `0x9f4a`: `TmplConfigurationAdditionalError`

## pseudocode

```c

```

## disassembly

```asm
0x9ec0  ldarg.0
0x9ec1  callvirt instance string System.Web.ErrorFormatter::get_MiscSectionTitle()
0x9ec6  brfalse.s loc_9F04
0x9ec8  ldarg.1
0x9ec9  ldc.i4.5
0x9eca  newarr   [mscorlib]System.String
0x9ecf  dup
0x9ed0  ldc.i4.0
0x9ed1  ldstr    aB// "            <b> "
0x9ed6  stelem.ref
0x9ed7  dup
0x9ed8  ldc.i4.1
0x9ed9  ldarg.0
0x9eda  callvirt instance string System.Web.ErrorFormatter::get_MiscSectionTitle()
0x9edf  stelem.ref
0x9ee0  dup
0x9ee1  ldc.i4.2
0x9ee2  ldstr    aB_2// ": </b>"
0x9ee7  stelem.ref
0x9ee8  dup
0x9ee9  ldc.i4.3
0x9eea  ldarg.0
0x9eeb  callvirt instance string System.Web.ErrorFormatter::get_MiscSectionContent()
0x9ef0  stelem.ref
0x9ef1  dup
0x9ef2  ldc.i4.4
0x9ef3  ldstr    aBrBr_0// "<br><br>\r\n\r\n"
0x9ef8  stelem.ref
0x9ef9  call     string [mscorlib]System.String::Concat(string[])
0x9efe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9f03  pop
0x9f04  ldarg.0
0x9f05  ldarg.1
0x9f06  ldarg.2
0x9f07  callvirt instance void System.Web.ErrorFormatter::WritePrimaryBox(class [mscorlib]System.Text.StringBuilder sb, bool dontShowSensitiveInfo)
0x9f0c  ldarg.0
0x9f0d  callvirt instance class [mscorlib]System.Exception System.Web.ErrorFormatter::get_Exception()
0x9f12  isinst   [System.Configuration]System.Configuration.ConfigurationErrorsException
0x9f17  stloc.0
0x9f18  ldloc.0
0x9f19  brfalse  loc_A00D
0x9f1e  ldloc.0
0x9f1f  callvirt instance class [mscorlib]System.Collections.ICollection [System.Configuration]System.Configuration.ConfigurationErrorsException::get_Errors()
0x9f24  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x9f29  ldc.i4.1
0x9f2a  ble      loc_A00D
0x9f2f  ldarg.1
0x9f30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9f35  ldstr    aBrDivClassExpa// "<br><div class=\"expandable\" onclick="...
0x9f3a  ldc.i4.2
0x9f3b  newarr   [mscorlib]System.Object
0x9f40  dup
0x9f41  ldc.i4.0
0x9f42  ldstr    aAdditionalconf// "additionalConfigurationErrors"
0x9f47  stelem.ref
0x9f48  dup
0x9f49  ldc.i4.1
0x9f4a  ldstr    aTmplconfigurat// "TmplConfigurationAdditionalError"
0x9f4f  call     string System.Web.SR::GetString(string name)
0x9f54  stelem.ref
0x9f55  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9f5a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9f5f  pop
0x9f60  ldarg.1
0x9f61  ldstr    aTableWidth100B// "            <table width=100% bgcolor="...
0x9f66  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9f6b  pop
0x9f6c  ldc.i4.0
0x9f6d  stloc.1
0x9f6e  call     class [mscorlib]System.Security.NamedPermissionSet System.Web.HttpRuntime::get_NamedPermissionSet()
0x9f73  stloc.2
0x9f74  ldloc.2
0x9f75  brfalse.s loc_9F7F
0x9f77  ldloc.2
0x9f78  callvirt instance void [mscorlib]System.Security.PermissionSet::PermitOnly()
0x9f7d  ldc.i4.1
0x9f7e  stloc.1
0x9f7f  ldc.i4.0
0x9f80  stloc.3
0x9f81  ldloc.0
0x9f82  callvirt instance class [mscorlib]System.Collections.ICollection [System.Configuration]System.Configuration.ConfigurationErrorsException::get_Errors()
0x9f87  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x9f8c  stloc.s  4
0x9f8e  br.s     loc_9FC0
0x9f90  ldloc.s  4
0x9f92  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9f97  castclass [System]System.Configuration.ConfigurationException
0x9f9c  stloc.s  5
0x9f9e  ldloc.3
0x9f9f  ldc.i4.0
0x9fa0  ble.s    loc_9FBC
0x9fa2  ldarg.1
0x9fa3  ldloc.s  5
0x9fa5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9faa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9faf  pop
0x9fb0  ldarg.1
0x9fb1  ldstr    aBr_1// "<BR/>\r\n"
0x9fb6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9fbb  pop
0x9fbc  ldloc.3
0x9fbd  ldc.i4.1
0x9fbe  add
0x9fbf  stloc.3
0x9fc0  ldloc.s  4
0x9fc2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9fc7  brtrue.s loc_9F90
0x9fc9  leave.s  loc_9FE9
0x9fcb  ldloc.s  4
0x9fcd  isinst   [mscorlib]System.IDisposable
0x9fd2  stloc.s  6
0x9fd4  ldloc.s  6
0x9fd6  brfalse.s loc_9FDF
0x9fd8  ldloc.s  6
0x9fda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9fdf  endfinally
0x9fe0  ldloc.1
0x9fe1  brfalse.s loc_9FE8
0x9fe3  call     void [mscorlib]System.Security.CodeAccessPermission::RevertPermitOnly()
0x9fe8  endfinally
0x9fe9  ldarg.1
0x9fea  ldstr    aPreCodeTd// "</pre>                      </code>\r\n"...
0x9fef  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x9ff4  pop
0x9ff5  ldarg.1
0x9ff6  ldstr    aDiv// "            \r\n\r\n</div>\r\n"
0x9ffb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa000  pop
0xa001  ldarg.1
0xa002  ldstr    aScriptTypeText// "\r\n        <script type=\"text/javascr"...
0xa007  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa00c  pop
0xa00d  ldarg.2
0xa00e  brtrue.s loc_A02B
0xa010  ldarg.0
0xa011  callvirt instance class [mscorlib]System.Exception System.Web.ErrorFormatter::get_Exception()
0xa016  brfalse.s loc_A02B
0xa018  ldc.i4   0x190
0xa01d  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0xa022  brfalse.s loc_A02B
0xa024  ldarg.0
0xa025  ldarg.1
0xa026  call     instance void System.Web.ErrorFormatter::WriteFusionLogWithAssert(class [mscorlib]System.Text.StringBuilder sb)
0xa02b  ldarg.0
0xa02c  ldarg.1
0xa02d  ldarg.2
0xa02e  callvirt instance void System.Web.ErrorFormatter::WriteSecondaryBox(class [mscorlib]System.Text.StringBuilder sb, bool dontShowSensitiveInfo)
0xa033  ret
```
