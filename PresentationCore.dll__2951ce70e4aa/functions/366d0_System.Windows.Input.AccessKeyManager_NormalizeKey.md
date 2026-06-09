# System.Windows.Input.AccessKeyManager::NormalizeKey

- ea: `0x366d0`
- end: `0x36713`
- name: `System.Windows.Input.AccessKeyManager::NormalizeKey`
- size: `67`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x36590`
- `0x36610`
- `0x36680`
- `0x366b0`

## callees

- `0x366d0`
- `0x146e70`

## string_xrefs

- `0x366ee`: `AccessKeyManager_NotAUnicodeCharacter`

## pseudocode

```c

```

## disassembly

```asm
0x366d0  ldarg.0
0x366d1  brtrue.s loc_366DE
0x366d3  ldstr    aKey// "key"
0x366d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x366dd  throw
0x366de  ldarg.0
0x366df  call     string [mscorlib]System.Globalization.StringInfo::GetNextTextElement(string)
0x366e4  stloc.0
0x366e5  ldarg.0
0x366e6  ldloc.0
0x366e7  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x366ec  brfalse.s loc_3670C
0x366ee  ldstr    aAccesskeymanag// "AccessKeyManager_NotAUnicodeCharacter"
0x366f3  ldc.i4.1
0x366f4  newarr   [mscorlib]System.Object
0x366f9  dup
0x366fa  ldc.i4.0
0x366fb  ldstr    aKey// "key"
0x36700  stelem.ref
0x36701  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x36706  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3670b  throw
0x3670c  ldloc.0
0x3670d  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x36712  ret
```
