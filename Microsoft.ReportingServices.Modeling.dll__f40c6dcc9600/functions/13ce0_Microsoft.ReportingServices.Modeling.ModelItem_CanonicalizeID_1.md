# Microsoft.ReportingServices.Modeling.ModelItem::CanonicalizeID_1

- ea: `0x13ce0`
- end: `0x13d25`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::CanonicalizeID_1`
- size: `69`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xab00`
- `0x13a20`
- `0x13cd0`

## callees

- `0xa120`
- `0xa130`
- `0xa280`
- `0x13ce0`
- `0x143e0`

## string_xrefs

- `0x13ce7`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x13ce0  ldarg.0
0x13ce1  call     valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.QName::Verify(valuetype Microsoft.ReportingServices.Modeling.QName qname)
0x13ce6  pop
0x13ce7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x13cec  ldarga.s 0
0x13cee  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Namespace()
0x13cf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13cf8  brtrue.s loc_13D0D
0x13cfa  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string> Microsoft.ReportingServices.Modeling.SemanticModelingSchema::PreviousNamespaces
0x13cff  ldarga.s 0
0x13d01  call     instance string Microsoft.ReportingServices.Modeling.QName::get_Namespace()
0x13d06  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<string>::Contains(var<u1>)
0x13d0b  brfalse.s loc_13D19
0x13d0d  ldarga.s 0
0x13d0f  ldsfld   string [mscorlib]System.String::Empty
0x13d14  call     instance void Microsoft.ReportingServices.Modeling.QName::set_Namespace(string value)
0x13d19  ldarg.1
0x13d1a  brtrue.s loc_13D23
0x13d1c  ldarg.0
0x13d1d  ldnull
0x13d1e  call     void Microsoft.ReportingServices.Modeling.ModelItem::CheckID(valuetype Microsoft.ReportingServices.Modeling.QName id, class Microsoft.ReportingServices.Modeling.CompilationContext ctx)
0x13d23  ldarg.0
0x13d24  ret
```
