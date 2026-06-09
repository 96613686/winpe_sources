# std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *)

- ea: `0x180010388`
- end: `0x1800103d6`
- name: `?_Erase@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@2@@Z`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009e74`
- `0x180009fdc`
- `0x180010388`
- `0x180015ce8`
- `0x180024798`

## callees

- `0x180010388`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 33) )
  {
    do
    {
      std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      operator delete(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 33) );
  }
}

```

## disassembly

```asm
0x180010388  mov     [rsp+arg_0], rbx
0x18001038d  mov     [rsp+arg_8], rsi
0x180010392  push    rdi
0x180010393  sub     rsp, 20h
0x180010397  cmp     byte ptr [rdx+21h], 0
0x18001039b  mov     rdi, rdx
0x18001039e  mov     rsi, rcx
0x1800103a1  mov     rbx, rdx
0x1800103a4  jnz     short loc_1800103C6
0x1800103a6  mov     rdx, [rbx+10h]
0x1800103aa  mov     rcx, rsi
0x1800103ad  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *)
0x1800103b2  mov     rbx, [rbx]
0x1800103b5  mov     rcx, rdi; Block
0x1800103b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800103bd  cmp     byte ptr [rbx+21h], 0
0x1800103c1  mov     rdi, rbx
0x1800103c4  jz      short loc_1800103A6
0x1800103c6  mov     rbx, [rsp+28h+arg_0]
0x1800103cb  mov     rsi, [rsp+28h+arg_8]
0x1800103d0  add     rsp, 20h
0x1800103d4  pop     rdi
0x1800103d5  retn
```
