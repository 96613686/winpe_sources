# System.Web.Http.UriQueryUtility::ValidateUrlEncodingParameters

- ea: `0xb7b0`
- end: `0xb7f4`
- name: `System.Web.Http.UriQueryUtility::ValidateUrlEncodingParameters`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xb570`

## callees

- `0xb3c0`
- `0xb7b0`

## pseudocode

```c

```

## disassembly

```asm
0xb7b0  ldarg.0
0xb7b1  brtrue.s loc_B7B8
0xb7b3  ldarg.2
0xb7b4  brtrue.s loc_B7B8
0xb7b6  ldc.i4.0
0xb7b7  ret
0xb7b8  ldarg.0
0xb7b9  brtrue.s loc_B7C6
0xb7bb  ldstr    aBytes// "bytes"
0xb7c0  call     class [mscorlib]System.ArgumentNullException System.Web.Http.Error::ArgumentNull(string parameterName)
0xb7c5  throw
0xb7c6  ldarg.1
0xb7c7  ldc.i4.0
0xb7c8  blt.s    loc_B7D0
0xb7ca  ldarg.1
0xb7cb  ldarg.0
0xb7cc  ldlen
0xb7cd  conv.i4
0xb7ce  ble.s    loc_B7DB
0xb7d0  ldstr    aOffset// "offset"
0xb7d5  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb7da  throw
0xb7db  ldarg.2
0xb7dc  ldc.i4.0
0xb7dd  blt.s    loc_B7E7
0xb7df  ldarg.1
0xb7e0  ldarg.2
0xb7e1  add
0xb7e2  ldarg.0
0xb7e3  ldlen
0xb7e4  conv.i4
0xb7e5  ble.s    loc_B7F2
0xb7e7  ldstr    aCount// "count"
0xb7ec  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb7f1  throw
0xb7f2  ldc.i4.1
0xb7f3  ret
```
