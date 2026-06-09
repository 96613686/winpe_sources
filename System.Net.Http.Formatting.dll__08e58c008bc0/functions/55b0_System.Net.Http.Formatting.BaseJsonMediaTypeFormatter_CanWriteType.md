# System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanWriteType

- ea: `0x55b0`
- end: `0x55c6`
- name: `System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::CanWriteType`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x7930`

## callees

- `0x55b0`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x55b0  ldarg.1
0x55b1  ldnull
0x55b2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x55b7  brfalse.s loc_55C4
0x55b9  ldstr    aType// "type"
0x55be  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x55c3  throw
0x55c4  ldc.i4.1
0x55c5  ret
```
