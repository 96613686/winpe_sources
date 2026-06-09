# Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage

- ea: `0x3960`
- end: `0x3976`
- name: `Microsoft.BIServer.Configuration.UrlEndpoints::GetProductUsage`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3990`
- `0x3aa0`
- `0x3ac0`
- `0x3ae0`

## callees

- `0x3960`

## pseudocode

```c

```

## disassembly

```asm
0x3960  ldarg.0
0x3961  callvirt instance string [mscorlib]System.Object::ToString()
0x3966  ldstr    aSsrs// "SSRS"
0x396b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3970  brtrue.s loc_3974
0x3972  ldc.i4.8
0x3973  ret
0x3974  ldc.i4.4
0x3975  ret
```
