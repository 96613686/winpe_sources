# MS.Internal.TokenizerHelper::LastTokenRequired

- ea: `0xde20`
- end: `0xde5c`
- name: `MS.Internal.TokenizerHelper::LastTokenRequired`
- size: `60`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x35f90`
- `0x36470`
- `0x36950`
- `0x37710`
- `0x37b70`
- `0x3f8b0`

## callees

- `0xde20`
- `0x2c130`

## string_xrefs

- `0xde2e`: `TokenizerHelperExtraDataEncountered`

## pseudocode

```c

```

## disassembly

```asm
0xde20  ldarg.0
0xde21  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xde26  ldarg.0
0xde27  ldfld    int32 MS.Internal.TokenizerHelper::_strLen
0xde2c  beq.s    loc_DE5B
0xde2e  ldstr    aTokenizerhelpe// "TokenizerHelperExtraDataEncountered"
0xde33  ldc.i4.2
0xde34  newarr   [mscorlib]System.Object
0xde39  dup
0xde3a  ldc.i4.0
0xde3b  ldarg.0
0xde3c  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xde41  box      [mscorlib]System.Int32
0xde46  stelem.ref
0xde47  dup
0xde48  ldc.i4.1
0xde49  ldarg.0
0xde4a  ldfld    string MS.Internal.TokenizerHelper::_str
0xde4f  stelem.ref
0xde50  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0xde55  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xde5a  throw
0xde5b  ret
```
