# System.Range::GetHashCode

- ea: `0x2f0`
- end: `0x31e`
- name: `System.Range::GetHashCode`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x250`
- `0x260`
- `0x1130`

## pseudocode

```c

```

## disassembly

```asm
0x2f0  ldarg.0
0x2f1  call     instance valuetype System.Index System.Range::get_Start()
0x2f6  stloc.0
0x2f7  ldloca.s 0
0x2f9  constrained. System.Index
0x2ff  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x304  ldarg.0
0x305  call     instance valuetype System.Index System.Range::get_End()
0x30a  stloc.0
0x30b  ldloca.s 0
0x30d  constrained. System.Index
0x313  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x318  call     int32 HashHelpers::Combine(int32 h1, int32 h2)
0x31d  ret
```
