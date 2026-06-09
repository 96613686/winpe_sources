# Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::GetScript

- ea: `0x362e0`
- end: `0x36304`
- name: `Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider::GetScript`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x362ef`: `Microsoft.ReportingServices.Hybrid.OAuth.Redirect_Util.js`

## pseudocode

```c

```

## disassembly

```asm
0x362e0  ldtoken  Microsoft.ReportingServices.Hybrid.OAuth.AadOAuthProvider
0x362e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x362ea  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetAssembly(class [mscorlib]System.Type)
0x362ef  ldstr    aMicrosoftRepor_140// "Microsoft.ReportingServices.Hybrid.OAut"...
0x362f4  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x362f9  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x362fe  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x36303  ret
```
