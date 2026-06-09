# <>c__DisplayClass5_0::<WriteTo>b__0_0

- ea: `0x3b440`
- end: `0x3b452`
- name: `<>c__DisplayClass5_0::<WriteTo>b__0_0`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xb530`

## string_xrefs

- `0x3b446`: `MeasureName`

## pseudocode

```c

```

## disassembly

```asm
0x3b440  ldarg.0
0x3b441  ldfld    class Microsoft.ReportingServices.Modeling.ModelingXmlWriter <>c__DisplayClass5_0::xw
0x3b446  ldstr    aMeasurename// "MeasureName"
0x3b44b  ldarg.1
0x3b44c  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteReferenceElement(string name, object item)
0x3b451  ret
```
