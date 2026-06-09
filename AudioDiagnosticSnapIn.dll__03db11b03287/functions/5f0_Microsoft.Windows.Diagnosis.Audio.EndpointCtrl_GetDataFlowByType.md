# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDataFlowByType

- ea: `0x5f0`
- end: `0x606`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDataFlowByType`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x160`
- `0x730`

## callees

- `0x5f0`

## pseudocode

```c

```

## disassembly

```asm
0x5f0  ldarg.1
0x5f1  ldstr    aRender// "render"
0x5f6  ldc.i4.5
0x5f7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5fc  brfalse.s loc_602
0x5fe  ldc.i4.0
0x5ff  stloc.0
0x600  br.s     loc_604
0x602  ldc.i4.1
0x603  stloc.0
0x604  ldloc.0
0x605  ret
```
