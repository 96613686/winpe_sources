# System.Range::GetOffsetAndLength

- ea: `0x390`
- end: `0x3ef`
- name: `System.Range::GetOffsetAndLength`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x160`
- `0x180`
- `0x250`
- `0x260`
- `0x390`
- `0x1150`

## pseudocode

```c

```

## disassembly

```asm
0x390  ldarg.0
0x391  call     instance valuetype System.Index System.Range::get_Start()
0x396  stloc.1
0x397  ldloca.s 1
0x399  call     instance bool System.Index::get_IsFromEnd()
0x39e  brfalse.s loc_3AC
0x3a0  ldarg.1
0x3a1  ldloca.s 1
0x3a3  call     instance int32 System.Index::get_Value()
0x3a8  sub
0x3a9  stloc.0
0x3aa  br.s     loc_3B4
0x3ac  ldloca.s 1
0x3ae  call     instance int32 System.Index::get_Value()
0x3b3  stloc.0
0x3b4  ldarg.0
0x3b5  call     instance valuetype System.Index System.Range::get_End()
0x3ba  stloc.3
0x3bb  ldloca.s 3
0x3bd  call     instance bool System.Index::get_IsFromEnd()
0x3c2  brfalse.s loc_3D0
0x3c4  ldarg.1
0x3c5  ldloca.s 3
0x3c7  call     instance int32 System.Index::get_Value()
0x3cc  sub
0x3cd  stloc.2
0x3ce  br.s     loc_3D8
0x3d0  ldloca.s 3
0x3d2  call     instance int32 System.Index::get_Value()
0x3d7  stloc.2
0x3d8  ldloc.2
0x3d9  ldarg.1
0x3da  bgt.un.s loc_3E0
0x3dc  ldloc.0
0x3dd  ldloc.2
0x3de  ble.un.s loc_3E5
0x3e0  call     void ThrowHelper::ThrowArgumentOutOfRangeException()
0x3e5  ldloc.0
0x3e6  ldloc.2
0x3e7  ldloc.0
0x3e8  sub
0x3e9  newobj   instance void valuetype [mscorlib]System.ValueTuple`2<int32, int32>::.ctor(var<u1>, !!T0)
0x3ee  ret
```
