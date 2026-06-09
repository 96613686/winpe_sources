# std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Erase(std::_Tree_node<ushort const *,void *> *)

- ea: `0x18001974c`
- end: `0x18001979b`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001974c`
- `0x180019890`

## callees

- `0x18001974c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001977c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001977c`

## pseudocode

```c
int __fastcall std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx
  int result; // eax

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 25) )
  {
    do
    {
      std::_Tree<std::_Tset_traits<unsigned short const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<unsigned short const *>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      result = CWin32DefaultArena::WbemMemFree(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 25) );
  }
  return result;
}

```

## disassembly

```asm
0x18001974c  mov     [rsp+arg_0], rbx
0x180019751  mov     [rsp+arg_8], rsi
0x180019756  push    rdi
0x180019757  sub     rsp, 20h
0x18001975b  cmp     byte ptr [rdx+19h], 0
0x18001975f  mov     rdi, rdx
0x180019762  mov     rsi, rcx
0x180019765  mov     rbx, rdx
0x180019768  jnz     short loc_18001978B
0x18001976a  mov     rdx, [rbx+10h]
0x18001976e  mov     rcx, rsi
0x180019771  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBGULPCWStrCompare@CFilterIgnoreSet@@V?$allocator@PEBG@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@PEBGPEAX@2@@Z; std::_Tree<std::_Tset_traits<ushort const *,CFilterIgnoreSet::LPCWStrCompare,std::allocator<ushort const *>,0>>::_Erase(std::_Tree_node<ushort const *,void *> *)
0x180019776  mov     rbx, [rbx]
0x180019779  mov     rcx, rdi
0x18001977c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180019782  cmp     byte ptr [rbx+19h], 0
0x180019786  mov     rdi, rbx
0x180019789  jz      short loc_18001976A
0x18001978b  mov     rbx, [rsp+28h+arg_0]
0x180019790  mov     rsi, [rsp+28h+arg_8]
0x180019795  add     rsp, 20h
0x180019799  pop     rdi
0x18001979a  retn
```
