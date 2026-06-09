# std::_Tree_comp<0,std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::~_Tree_comp<0,std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>(void)

- ea: `0x1800173e0`
- end: `0x1800173f2`
- name: `??1?$_Tree_comp@$0A@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `18`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e0f3`
- `0x18001ebf4`

## callees

- `0x1800173c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree_comp<0,std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::~_Tree_comp<0,std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>(
        __int64 a1)
{
  return std::_Tree_buy<unsigned short const *>::~_Tree_buy<unsigned short const *>(a1);
}

```

## disassembly

```asm
0x1800173e0  mov     [rsp+arg_0], rcx
0x1800173e5  sub     rsp, 28h
0x1800173e9  add     rsp, 28h
0x1800173ed  jmp     ??1?$_Tree_buy@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::_Tree_buy<ushort const *>::~_Tree_buy<ushort const *>(void)
```
