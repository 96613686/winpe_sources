# System.Range::ToString

- ea: `0x320`
- end: `0x353`
- name: `System.Range::ToString`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x250`
- `0x260`

## pseudocode

```c

```

## disassembly

```asm
0x320  ldarg.0
0x321  call     instance valuetype System.Index System.Range::get_Start()
0x326  stloc.0
0x327  ldloca.s 0
0x329  constrained. System.Index
0x32f  callvirt instance string [mscorlib]System.Object::ToString()
0x334  ldstr    asc_2004// ".."
0x339  ldarg.0
0x33a  call     instance valuetype System.Index System.Range::get_End()
0x33f  stloc.0
0x340  ldloca.s 0
0x342  constrained. System.Index
0x348  callvirt instance string [mscorlib]System.Object::ToString()
0x34d  call     string [mscorlib]System.String::Concat(string, string, string)
0x352  ret
```
