# std::set<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>::~set<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(void)

- ea: `0x180009fdc`
- end: `0x18000a05e`
- name: `??1?$set@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027f4f`
- `0x180027f5b`
- `0x180028989`
- `0x18002977c`
- `0x1800297a8`

## callees

- `0x180009fdc`
- `0x180010388`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::set<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>::~set<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>(
        __int64 a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  _QWORD *v4; // rax

  v2 = *(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL);
  for ( i = v2; !*((_BYTE *)i + 33); v2 = i )
  {
    std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    operator delete(v2);
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD **)(a1 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  *v4 = v4;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  operator delete(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180009fdc  mov     [rsp+arg_0], rbx
0x180009fe1  mov     [rsp+arg_8], rsi
0x180009fe6  push    rdi
0x180009fe7  sub     rsp, 20h
0x180009feb  mov     rax, [rcx+8]
0x180009fef  mov     rbx, rcx
0x180009ff2  mov     rsi, [rax+8]
0x180009ff6  mov     rdi, rsi
0x180009ff9  cmp     byte ptr [rsi+21h], 0
0x180009ffd  jnz     short loc_18000A01F
0x180009fff  mov     rdx, [rdi+10h]
0x18000a003  mov     rcx, rbx
0x18000a006  call    ?_Erase@?$_Tree@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessCCvDDPtrByImageId@2345@V?$allocator@PEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessCCvDDPtrByImageId,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>,0>>::_Node *)
0x18000a00b  mov     rdi, [rdi]
0x18000a00e  mov     rcx, rsi; Block
0x18000a011  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a016  cmp     byte ptr [rdi+21h], 0
0x18000a01a  mov     rsi, rdi
0x18000a01d  jz      short loc_180009FFF
0x18000a01f  mov     rax, [rbx+8]
0x18000a023  mov     [rax+8], rax
0x18000a027  mov     rax, [rbx+8]
0x18000a02b  and     qword ptr [rbx+10h], 0
0x18000a030  mov     [rax], rax
0x18000a033  mov     rax, [rbx+8]
0x18000a037  mov     [rax+10h], rax
0x18000a03b  mov     rcx, [rbx+8]; Block
0x18000a03f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a044  and     qword ptr [rbx+8], 0
0x18000a049  and     qword ptr [rbx+10h], 0
0x18000a04e  mov     rbx, [rsp+28h+arg_0]
0x18000a053  mov     rsi, [rsp+28h+arg_8]
0x18000a058  add     rsp, 20h
0x18000a05c  pop     rdi
0x18000a05d  retn
```
