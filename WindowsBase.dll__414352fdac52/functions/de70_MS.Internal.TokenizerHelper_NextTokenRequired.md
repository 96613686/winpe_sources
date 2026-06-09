# MS.Internal.TokenizerHelper::NextTokenRequired

- ea: `0xde70`
- end: `0xde9f`
- name: `MS.Internal.TokenizerHelper::NextTokenRequired`
- size: `47`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x35f90`
- `0x36470`
- `0x36950`
- `0x37710`
- `0x37b70`
- `0x3f8b0`

## callees

- `0xddf0`
- `0xde70`
- `0xded0`
- `0x2c130`

## string_xrefs

- `0xde79`: `TokenizerHelperPrematureStringTermination`

## pseudocode

```c

```

## disassembly

```asm
0xde70  ldarg.0
0xde71  ldc.i4.0
0xde72  call     instance bool MS.Internal.TokenizerHelper::NextToken(bool allowQuotedToken)
0xde77  brtrue.s loc_DE98
0xde79  ldstr    aTokenizerhelpe_0// "TokenizerHelperPrematureStringTerminati"...
0xde7e  ldc.i4.1
0xde7f  newarr   [mscorlib]System.Object
0xde84  dup
0xde85  ldc.i4.0
0xde86  ldarg.0
0xde87  ldfld    string MS.Internal.TokenizerHelper::_str
0xde8c  stelem.ref
0xde8d  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0xde92  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xde97  throw
0xde98  ldarg.0
0xde99  call     instance string MS.Internal.TokenizerHelper::GetCurrentToken()
0xde9e  ret
```
