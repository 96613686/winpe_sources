# Frame::TryLookupPrefix

- ea: `0x2cbd0`
- end: `0x2cbf4`
- name: `Frame::TryLookupPrefix`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xfc40`

## callees

- `0x2cbd0`

## string_xrefs

- `0x2cbd1`: `http://www.w3.org/XML/1998/namespace`

## pseudocode

```c

```

## disassembly

```asm
0x2cbd0  ldarg.1
0x2cbd1  ldstr    aHttpWwwW3OrgXm// "http://www.w3.org/XML/1998/namespace"
0x2cbd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2cbdb  brfalse.s loc_2CBE6
0x2cbdd  ldarg.2
0x2cbde  ldstr    aXml// "xml"
0x2cbe3  stind.ref
0x2cbe4  ldc.i4.1
0x2cbe5  ret
0x2cbe6  ldarg.0
0x2cbe7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Frame::namespaceMap
0x2cbec  ldarg.1
0x2cbed  ldarg.2
0x2cbee  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x2cbf3  ret
```
