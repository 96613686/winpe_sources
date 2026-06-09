# MS.Internal.TokenizerHelper::NextToken_1

- ea: `0xdee0`
- end: `0xe01a`
- name: `MS.Internal.TokenizerHelper::NextToken_1`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0xded0`

## callees

- `0xdee0`
- `0xe020`
- `0x2c130`

## string_xrefs

- `0xdfae`: `TokenizerHelperMissingEndQuote`
- `0xdfeb`: `TokenizerHelperEmptyToken`

## pseudocode

```c

```

## disassembly

```asm
0xdee0  ldarg.0
0xdee1  ldc.i4.m1
0xdee2  stfld    int32 MS.Internal.TokenizerHelper::_currentTokenIndex
0xdee7  ldarg.0
0xdee8  ldc.i4.0
0xdee9  stfld    bool MS.Internal.TokenizerHelper::_foundSeparator
0xdeee  ldarg.0
0xdeef  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdef4  ldarg.0
0xdef5  ldfld    int32 MS.Internal.TokenizerHelper::_strLen
0xdefa  blt.s    loc_DEFE
0xdefc  ldc.i4.0
0xdefd  ret
0xdefe  ldarg.0
0xdeff  ldfld    string MS.Internal.TokenizerHelper::_str
0xdf04  ldarg.0
0xdf05  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf0a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xdf0f  stloc.0
0xdf10  ldc.i4.0
0xdf11  stloc.1
0xdf12  ldarg.1
0xdf13  brfalse.s loc_DF30
0xdf15  ldloc.0
0xdf16  ldarg.0
0xdf17  ldfld    char MS.Internal.TokenizerHelper::_quoteChar
0xdf1c  bne.un.s loc_DF30
0xdf1e  ldloc.1
0xdf1f  ldc.i4.1
0xdf20  add
0xdf21  stloc.1
0xdf22  ldarg.0
0xdf23  ldarg.0
0xdf24  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf29  ldc.i4.1
0xdf2a  add
0xdf2b  stfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf30  ldarg.0
0xdf31  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf36  stloc.2
0xdf37  ldc.i4.0
0xdf38  stloc.3
0xdf39  br.s     loc_DF9C
0xdf3b  ldarg.0
0xdf3c  ldfld    string MS.Internal.TokenizerHelper::_str
0xdf41  ldarg.0
0xdf42  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf47  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xdf4c  stloc.0
0xdf4d  ldloc.1
0xdf4e  ldc.i4.0
0xdf4f  ble.s    loc_DF71
0xdf51  ldloc.0
0xdf52  ldarg.0
0xdf53  ldfld    char MS.Internal.TokenizerHelper::_quoteChar
0xdf58  bne.un.s loc_DF8A
0xdf5a  ldloc.1
0xdf5b  ldc.i4.1
0xdf5c  sub
0xdf5d  stloc.1
0xdf5e  ldloc.1
0xdf5f  brtrue.s loc_DF8A
0xdf61  ldarg.0
0xdf62  ldarg.0
0xdf63  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf68  ldc.i4.1
0xdf69  add
0xdf6a  stfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf6f  br.s     loc_DFAA
0xdf71  ldloc.0
0xdf72  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0xdf77  brtrue.s loc_DF7D
0xdf79  ldloc.0
0xdf7a  ldarg.2
0xdf7b  bne.un.s loc_DF8A
0xdf7d  ldloc.0
0xdf7e  ldarg.2
0xdf7f  bne.un.s loc_DFAA
0xdf81  ldarg.0
0xdf82  ldc.i4.1
0xdf83  stfld    bool MS.Internal.TokenizerHelper::_foundSeparator
0xdf88  br.s     loc_DFAA
0xdf8a  ldarg.0
0xdf8b  ldarg.0
0xdf8c  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf91  ldc.i4.1
0xdf92  add
0xdf93  stfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdf98  ldloc.3
0xdf99  ldc.i4.1
0xdf9a  add
0xdf9b  stloc.3
0xdf9c  ldarg.0
0xdf9d  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdfa2  ldarg.0
0xdfa3  ldfld    int32 MS.Internal.TokenizerHelper::_strLen
0xdfa8  blt.s    loc_DF3B
0xdfaa  ldloc.1
0xdfab  ldc.i4.0
0xdfac  ble.s    loc_DFCD
0xdfae  ldstr    aTokenizerhelpe_1// "TokenizerHelperMissingEndQuote"
0xdfb3  ldc.i4.1
0xdfb4  newarr   [mscorlib]System.Object
0xdfb9  dup
0xdfba  ldc.i4.0
0xdfbb  ldarg.0
0xdfbc  ldfld    string MS.Internal.TokenizerHelper::_str
0xdfc1  stelem.ref
0xdfc2  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0xdfc7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xdfcc  throw
0xdfcd  ldarg.0
0xdfce  ldarg.2
0xdfcf  call     instance void MS.Internal.TokenizerHelper::ScanToNextToken(char separator)
0xdfd4  ldarg.0
0xdfd5  ldloc.2
0xdfd6  stfld    int32 MS.Internal.TokenizerHelper::_currentTokenIndex
0xdfdb  ldarg.0
0xdfdc  ldloc.3
0xdfdd  stfld    int32 MS.Internal.TokenizerHelper::_currentTokenLength
0xdfe2  ldarg.0
0xdfe3  ldfld    int32 MS.Internal.TokenizerHelper::_currentTokenLength
0xdfe8  ldc.i4.1
0xdfe9  bge.s    loc_E018
0xdfeb  ldstr    aTokenizerhelpe_2// "TokenizerHelperEmptyToken"
0xdff0  ldc.i4.2
0xdff1  newarr   [mscorlib]System.Object
0xdff6  dup
0xdff7  ldc.i4.0
0xdff8  ldarg.0
0xdff9  ldfld    int32 MS.Internal.TokenizerHelper::_charIndex
0xdffe  box      [mscorlib]System.Int32
0xe003  stelem.ref
0xe004  dup
0xe005  ldc.i4.1
0xe006  ldarg.0
0xe007  ldfld    string MS.Internal.TokenizerHelper::_str
0xe00c  stelem.ref
0xe00d  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0xe012  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xe017  throw
0xe018  ldc.i4.1
0xe019  ret
```
