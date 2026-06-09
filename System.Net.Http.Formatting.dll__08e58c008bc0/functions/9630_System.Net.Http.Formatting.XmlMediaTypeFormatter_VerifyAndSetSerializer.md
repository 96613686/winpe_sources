# System.Net.Http.Formatting.XmlMediaTypeFormatter::VerifyAndSetSerializer

- ea: `0x9630`
- end: `0x965b`
- name: `System.Net.Http.Formatting.XmlMediaTypeFormatter::VerifyAndSetSerializer`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x9190`
- `0x91c0`

## callees

- `0x9630`
- `0x9660`
- `0xb3c0`

## pseudocode

```c

```

## disassembly

```asm
0x9630  ldarg.1
0x9631  ldnull
0x9632  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9637  brfalse.s loc_9644
0x9639  ldstr    aType// "type"
0x963e  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9643  throw
0x9644  ldarg.2
0x9645  brtrue.s loc_9652
0x9647  ldstr    aSerializer// "serializer"
0x964c  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0x9651  throw
0x9652  ldarg.0
0x9653  ldarg.1
0x9654  ldarg.2
0x9655  call     instance void System.Net.Http.Formatting.XmlMediaTypeFormatter::SetSerializerInternal(class [mscorlib]System.Type type, object serializer)
0x965a  ret
```
