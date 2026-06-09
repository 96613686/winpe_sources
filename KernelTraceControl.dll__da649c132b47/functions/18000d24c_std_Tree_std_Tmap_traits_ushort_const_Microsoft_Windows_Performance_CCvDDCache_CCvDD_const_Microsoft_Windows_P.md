# std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(void)

- ea: `0x18000d24c`
- end: `0x18000d2ce`
- name: `?_Tidy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ`
- size: `130`
- prototype: ``
- caller_count: `20`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009e74`
- `0x180009fd4`
- `0x18000d2d0`
- `0x18000d48c`
- `0x18000db8c`
- `0x1800104b4`
- `0x18001866c`
- `0x180019008`
- `0x18001905c`
- `0x18001a3b4`
- `0x180027f33`
- `0x1800282ff`
- `0x1800292c0`
- `0x1800292cc`
- `0x1800292e4`
- `0x1800292f0`
- `0x18002930c`
- `0x180029318`
- `0x180029334`
- `0x180029340`

## callees

- `0x18000d24c`
- `0x1800103d8`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(
        __int64 a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi
  _QWORD *v4; // rax

  v2 = *(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL);
  for ( i = v2; !*((_BYTE *)i + 41); v2 = i )
  {
    std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Erase(
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
0x18000d24c  mov     [rsp+arg_0], rbx
0x18000d251  mov     [rsp+arg_8], rsi
0x18000d256  push    rdi
0x18000d257  sub     rsp, 20h
0x18000d25b  mov     rax, [rcx+8]
0x18000d25f  mov     rbx, rcx
0x18000d262  mov     rsi, [rax+8]
0x18000d266  mov     rdi, rsi
0x18000d269  cmp     byte ptr [rsi+29h], 0
0x18000d26d  jnz     short loc_18000D28F
0x18000d26f  mov     rdx, [rdi+10h]
0x18000d273  mov     rcx, rbx
0x18000d276  call    ?_Erase@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Erase(std::_Tree_nod<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Node *)
0x18000d27b  mov     rdi, [rdi]
0x18000d27e  mov     rcx, rsi; Block
0x18000d281  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d286  cmp     byte ptr [rdi+29h], 0
0x18000d28a  mov     rsi, rdi
0x18000d28d  jz      short loc_18000D26F
0x18000d28f  mov     rax, [rbx+8]
0x18000d293  mov     [rax+8], rax
0x18000d297  mov     rax, [rbx+8]
0x18000d29b  and     qword ptr [rbx+10h], 0
0x18000d2a0  mov     [rax], rax
0x18000d2a3  mov     rax, [rbx+8]
0x18000d2a7  mov     [rax+10h], rax
0x18000d2ab  mov     rcx, [rbx+8]; Block
0x18000d2af  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d2b4  and     qword ptr [rbx+8], 0
0x18000d2b9  and     qword ptr [rbx+10h], 0
0x18000d2be  mov     rbx, [rsp+28h+arg_0]
0x18000d2c3  mov     rsi, [rsp+28h+arg_8]
0x18000d2c8  add     rsp, 20h
0x18000d2cc  pop     rdi
0x18000d2cd  retn
```
