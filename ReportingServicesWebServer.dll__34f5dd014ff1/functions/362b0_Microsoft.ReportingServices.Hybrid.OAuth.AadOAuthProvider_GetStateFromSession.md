# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::GetStateFromSession

- ea: `0x362b0`
- end: `0x362d6`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::GetStateFromSession`
- size: `38`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x361b0`
- `0x36210`

## callees

- `0x365b0`

## string_xrefs

- `0x362ca`: `State value not found in session cache. Will not be able to verify authenticity of authorization codes.`

## pseudocode

```c

```

## disassembly

```asm
0x362b0  ldarg.0
0x362b1  ldfld    class Microsoft.ReportingServices.Hybrid.OAuth.IAadCache Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::m_cache
0x362b6  callvirt instance string Microsoft.ReportingServices.Hybrid.OAuth.IAadCache::GetSessionState()
0x362bb  stloc.0
0x362bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x362c1  ldloc.0
0x362c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x362c7  ldc.i4.0
0x362c8  ceq
0x362ca  ldstr    aStateValueNotF// "State value not found in session cache."...
0x362cf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x362d4  ldloc.0
0x362d5  ret
```
