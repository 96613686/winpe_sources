# System.Web.Http.UriQueryUtility::UrlEncode_0

- ea: `0xb540`
- end: `0xb561`
- name: `System.Web.Http.UriQueryUtility::UrlEncode_0`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb4f0`

## callees

- `0xb540`
- `0xb570`

## pseudocode

```c

```

## disassembly

```asm
0xb540  ldarg.0
0xb541  ldarg.1
0xb542  ldarg.2
0xb543  call     unsigned int8[] System.Web.Http.UriQueryUtility::UrlEncode(unsigned int8[] bytes, int32 offset, int32 count)
0xb548  stloc.0
0xb549  ldarg.3
0xb54a  brfalse.s loc_B553
0xb54c  ldloc.0
0xb54d  brfalse.s loc_B553
0xb54f  ldloc.0
0xb550  ldarg.0
0xb551  beq.s    loc_B555
0xb553  ldloc.0
0xb554  ret
0xb555  ldloc.0
0xb556  callvirt instance object [mscorlib]System.Array::Clone()
0xb55b  castclass unsigned int8[]
0xb560  ret
```
