# Microsoft.ReportingServices.Modeling.DsvColumn::get_ComputedColumnExpression

- ea: `0xe4f0`
- end: `0xe505`
- name: `Microsoft.ReportingServices.Modeling.DsvColumn::get_ComputedColumnExpression`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c280`

## callees

- `0xda00`
- `0xe4f0`

## string_xrefs

- `0xe4f1`: `ComputedColumnExpression`

## pseudocode

```c

```

## disassembly

```asm
0xe4f0  ldarg.0
0xe4f1  ldstr    aComputedcolumn// "ComputedColumnExpression"
0xe4f6  call     instance string Microsoft.ReportingServices.Modeling.DsvItem::GetString(string propertyName)
0xe4fb  dup
0xe4fc  brtrue.s loc_E504
0xe4fe  pop
0xe4ff  ldsfld   string [mscorlib]System.String::Empty
0xe504  ret
```
