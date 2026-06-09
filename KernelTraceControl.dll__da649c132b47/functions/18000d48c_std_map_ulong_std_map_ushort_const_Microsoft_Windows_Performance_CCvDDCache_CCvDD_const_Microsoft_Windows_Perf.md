# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::operator[](ulong const &)

- ea: `0x18000d48c`
- end: `0x18000d55d`
- name: `??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800091c0`
- `0x1800093c0`
- `0x180009704`

## callees

- `0x18000d24c`
- `0x18000d48c`
- `0x18000e278`
- `0x18000eff0`
- `0x18000fdb0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
        __int64 a1,
        unsigned int *a2)
{
  __int64 *v4; // rax
  __int64 *v5; // r8
  __int64 *v6; // rbx
  unsigned int v7; // edx
  _BYTE v9[8]; // [rsp+28h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-30h]
  __int64 v11; // [rsp+38h] [rbp-28h]
  unsigned int v12; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v13[24]; // [rsp+48h] [rbp-18h] BYREF
  char v14; // [rsp+90h] [rbp+30h] BYREF

  v4 = *(__int64 **)(a1 + 8);
  v5 = (__int64 *)v4[1];
  v6 = v4;
  if ( !*((_BYTE *)v5 + 57) )
  {
    v7 = *a2;
    do
    {
      if ( *((_DWORD *)v5 + 6) >= v7 )
      {
        v6 = v5;
        v5 = (__int64 *)*v5;
      }
      else
      {
        v5 = (__int64 *)v5[2];
      }
    }
    while ( !*((_BYTE *)v5 + 57) );
  }
  if ( v6 == v4 || *a2 < *((_DWORD *)v6 + 6) )
  {
    v10 = std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Buynode(a1);
    *(_BYTE *)(v10 + 41) = 1;
    *(_QWORD *)(v10 + 8) = v10;
    *(_QWORD *)v10 = v10;
    *(_QWORD *)(v10 + 16) = v10;
    v11 = 0;
    v12 = *a2;
    std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(
      v13,
      v9);
    v6 = *(__int64 **)std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::insert(
                        a1,
                        &v14,
                        v6,
                        &v12,
                        -2);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy((__int64)v13);
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy((__int64)v9);
  }
  return v6 + 4;
}

```

## disassembly

```asm
0x18000d48c  mov     rax, rsp
0x18000d48f  push    rbp
0x18000d490  push    rsi
0x18000d491  push    rdi
0x18000d492  mov     rbp, rsp
0x18000d495  sub     rsp, 60h
0x18000d499  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18000d4a1  mov     [rax+10h], rbx
0x18000d4a5  mov     rdi, rdx
0x18000d4a8  mov     rsi, rcx
0x18000d4ab  mov     rax, [rcx+8]
0x18000d4af  mov     r8, [rax+8]
0x18000d4b3  mov     rbx, rax
0x18000d4b6  cmp     byte ptr [r8+39h], 0
0x18000d4bb  jnz     short loc_18000D4D8
0x18000d4bd  mov     edx, [rdx]
0x18000d4bf  cmp     [r8+18h], edx
0x18000d4c3  jnb     short loc_18000D4CB
0x18000d4c5  mov     r8, [r8+10h]
0x18000d4c9  jmp     short loc_18000D4D1
0x18000d4cb  mov     rbx, r8
0x18000d4ce  mov     r8, [r8]
0x18000d4d1  cmp     byte ptr [r8+39h], 0
0x18000d4d6  jz      short loc_18000D4BF
0x18000d4d8  cmp     rbx, rax
0x18000d4db  jz      short loc_18000D4E4
0x18000d4dd  mov     eax, [rbx+18h]
0x18000d4e0  cmp     [rdi], eax
0x18000d4e2  jnb     short loc_18000D549
0x18000d4e4  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@2@XZ; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Buynode(void)
0x18000d4e9  mov     [rbp+var_30], rax
0x18000d4ed  mov     byte ptr [rax+29h], 1
0x18000d4f1  mov     rax, [rbp+var_30]
0x18000d4f5  mov     [rax+8], rax
0x18000d4f9  mov     rax, [rbp+var_30]
0x18000d4fd  mov     [rax], rax
0x18000d500  mov     rax, [rbp+var_30]
0x18000d504  mov     [rax+10h], rax
0x18000d508  and     [rbp+var_28], 0
0x18000d50d  mov     eax, [rdi]
0x18000d50f  mov     [rbp+var_20], eax
0x18000d512  lea     rdx, [rbp+var_38]
0x18000d516  lea     rcx, [rbp+var_18]
0x18000d51a  call    ??0?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>> const &)
0x18000d51f  nop
0x18000d520  lea     r9, [rbp+var_20]
0x18000d524  mov     r8, rbx
0x18000d527  lea     rdx, [rbp+arg_10]
0x18000d52b  mov     rcx, rsi
0x18000d52e  call    ?insert@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::insert(std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::iterator,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &)
0x18000d533  mov     rbx, [rax]
0x18000d536  lea     rcx, [rbp+var_18]
0x18000d53a  call    ?_Tidy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(void)
0x18000d53f  nop
0x18000d540  lea     rcx, [rbp+var_38]
0x18000d544  call    ?_Tidy@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(void)
0x18000d549  lea     rax, [rbx+20h]
0x18000d54d  mov     rbx, [rsp+60h+arg_8]
0x18000d555  add     rsp, 60h
0x18000d559  pop     rdi
0x18000d55a  pop     rsi
0x18000d55b  pop     rbp
0x18000d55c  retn
```
