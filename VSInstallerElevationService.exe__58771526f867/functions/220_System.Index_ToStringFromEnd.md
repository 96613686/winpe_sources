# System.Index::ToStringFromEnd

- ea: `0x220`
- end: `0x239`
- name: `System.Index::ToStringFromEnd`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x200`

## callees

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x220  ldstr    asc_3000// "^"
0x225  ldarg.0
0x226  call     instance int32 System.Index::get_Value()
0x22b  stloc.0
0x22c  ldloca.s 0
0x22e  call     instance string [mscorlib]System.Int32::ToString()
0x233  call     string [mscorlib]System.String::Concat(string, string)
0x238  ret
```
