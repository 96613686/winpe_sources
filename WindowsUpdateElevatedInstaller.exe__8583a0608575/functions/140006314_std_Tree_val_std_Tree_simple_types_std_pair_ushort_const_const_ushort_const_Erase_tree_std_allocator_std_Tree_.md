# std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,ushort const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *> *)

- ea: `0x140006314`
- end: `0x140006368`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBG@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@1@@Z`
- size: `84`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140006314`
- `0x140006444`
- `0x140007650`

## callees

- `0x140001714`
- `0x140006314`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,unsigned short const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,unsigned short const *>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  void *v6; // rcx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,unsigned short const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned short const * const,unsigned short const *>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v3 = (_QWORD *)*v3;
      operator delete(v6);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x140006314  mov     [rsp+arg_0], rbx
0x140006319  mov     [rsp+arg_8], rsi
0x14000631e  push    rdi
0x14000631f  sub     rsp, 20h
0x140006323  cmp     byte ptr [r8+19h], 0
0x140006328  mov     rbx, r8
0x14000632b  mov     rdi, rdx
0x14000632e  mov     rsi, rcx
0x140006331  jnz     short loc_140006358
0x140006333  mov     r8, [rbx+10h]
0x140006337  mov     rdx, rdi
0x14000633a  mov     rcx, rsi
0x14000633d  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGPEBG@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEBGPEBG@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,ushort const *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *>> &,std::_Tree_node<std::pair<ushort const * const,ushort const *>,void *> *)
0x140006342  mov     rcx, rbx; Block
0x140006345  mov     edx, 30h ; '0'
0x14000634a  mov     rbx, [rbx]
0x14000634d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006352  cmp     byte ptr [rbx+19h], 0
0x140006356  jz      short loc_140006333
0x140006358  mov     rbx, [rsp+28h+arg_0]
0x14000635d  mov     rsi, [rsp+28h+arg_8]
0x140006362  add     rsp, 20h
0x140006366  pop     rdi
0x140006367  retn
```
