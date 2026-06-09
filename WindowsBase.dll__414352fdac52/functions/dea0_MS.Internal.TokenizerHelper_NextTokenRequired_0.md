# MS.Internal.TokenizerHelper::NextTokenRequired_0

- ea: `0xdea0`
- end: `0xdecf`
- name: `MS.Internal.TokenizerHelper::NextTokenRequired_0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xddf0`
- `0xdea0`
- `0xded0`
- `0x2c130`

## string_xrefs

- `0xdea9`: `TokenizerHelperPrematureStringTermination`

## pseudocode

```c

```

## disassembly

```asm
0xdea0  ldarg.0
0xdea1  ldarg.1
0xdea2  call     instance bool MS.Internal.TokenizerHelper::NextToken(bool allowQuotedToken)
0xdea7  brtrue.s loc_DEC8
0xdea9  ldstr    aTokenizerhelpe_0// "TokenizerHelperPrematureStringTerminati"...
0xdeae  ldc.i4.1
0xdeaf  newarr   [mscorlib]System.Object
0xdeb4  dup
0xdeb5  ldc.i4.0
0xdeb6  ldarg.0
0xdeb7  ldfld    string MS.Internal.TokenizerHelper::_str
0xdebc  stelem.ref
0xdebd  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0xdec2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdec7  throw
0xdec8  ldarg.0
0xdec9  call     instance string MS.Internal.TokenizerHelper::GetCurrentToken()
0xdece  ret
```
