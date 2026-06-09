# std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Erase(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)

- ea: `0x140008a80`
- end: `0x140008acf`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z`
- size: `79`
- prototype: `int __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008a80`
- `0x140008ba0`

## callees

- `0x140008a80`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140008ab0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140008ab0`

## pseudocode

```c
int __fastcall std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Erase(
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
      std::_Tree<std::_Tmap_traits<unsigned short *,CObject *,__CompareLPWSTR<unsigned short *>,RA_allocator<CObject *>,0>>::_Erase(
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
0x140008a80  mov     [rsp+arg_0], rbx
0x140008a85  mov     [rsp+arg_8], rsi
0x140008a8a  push    rdi
0x140008a8b  sub     rsp, 20h
0x140008a8f  cmp     byte ptr [rdx+19h], 0
0x140008a93  mov     rdi, rdx
0x140008a96  mov     rsi, rcx
0x140008a99  mov     rbx, rdx
0x140008a9c  jnz     short loc_140008ABF
0x140008a9e  mov     rdx, [rbx+10h]
0x140008aa2  mov     rcx, rsi
0x140008aa5  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEAGPEAVCObject@@U?$__CompareLPWSTR@PEAG@@V?$RA_allocator@PEAVCObject@@@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGPEAVCObject@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,CObject *,__CompareLPWSTR<ushort *>,RA_allocator<CObject *>,0>>::_Erase(std::_Tree_node<std::pair<ushort * const,CObject *>,void *> *)
0x140008aaa  mov     rbx, [rbx]
0x140008aad  mov     rcx, rdi
0x140008ab0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140008ab6  cmp     byte ptr [rbx+19h], 0
0x140008aba  mov     rdi, rbx
0x140008abd  jz      short loc_140008A9E
0x140008abf  mov     rbx, [rsp+28h+arg_0]
0x140008ac4  mov     rsi, [rsp+28h+arg_8]
0x140008ac9  add     rsp, 20h
0x140008acd  pop     rdi
0x140008ace  retn
```
