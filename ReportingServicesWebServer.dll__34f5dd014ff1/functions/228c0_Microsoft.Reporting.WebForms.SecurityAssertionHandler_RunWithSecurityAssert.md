# Microsoft.Reporting.WebForms.SecurityAssertionHandler::RunWithSecurityAssert

- ea: `0x228c0`
- end: `0x228f4`
- name: `Microsoft.Reporting.WebForms.SecurityAssertionHandler::RunWithSecurityAssert`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x65f0`
- `0x67c0`
- `0x14d90`
- `0x22900`

## callees

- `0x228c0`

## string_xrefs

- `0x228d5`: `Security Assertions disabled due to exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x228c0  ldsfld   bool Microsoft.Reporting.WebForms.SecurityAssertionHandler::m_assumeFullTrust
0x228c5  brfalse.s loc_228ED
0x228c7  ldarg.0
0x228c8  callvirt instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x228cd  leave.s  loc_228ED
0x228cf  stloc.0
0x228d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x228d5  ldstr    aSecurityAssert// "Security Assertions disabled due to exc"...
0x228da  ldloc.0
0x228db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x228e0  call     void [System]System.Diagnostics.Trace::WriteLine(string)
0x228e5  ldc.i4.0
0x228e6  stsfld   bool Microsoft.Reporting.WebForms.SecurityAssertionHandler::m_assumeFullTrust
0x228eb  leave.s  loc_228ED
0x228ed  ldarg.1
0x228ee  callvirt instance void [mscorlib]System.Action::Invoke()
0x228f3  ret
```
