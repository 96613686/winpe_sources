# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanReadType

- ea: `0x5590`
- end: `0x55a6`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanReadType`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x78f0`

## callees

- `0x5590`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x5590  ldarg.1
0x5591  ldnull
0x5592  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5597  brfalse.s loc_55A4
0x5599  ldstr    aType// "type"
0x559e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x55a3  throw
0x55a4  ldc.i4.1
0x55a5  ret
```
