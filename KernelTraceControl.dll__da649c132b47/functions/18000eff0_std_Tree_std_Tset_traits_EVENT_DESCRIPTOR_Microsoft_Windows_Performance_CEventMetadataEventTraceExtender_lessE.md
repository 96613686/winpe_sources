# std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>> const &)

- ea: `0x18000eff0`
- end: `0x18000f0bf`
- name: `??0?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA@AEBV01@@Z`
- size: `207`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d48c`
- `0x18000fe00`
- `0x18001866c`
- `0x18001a1d8`

## callees

- `0x18000eff0`
- `0x18000fdb0`
- `0x180010428`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  __int64 **v7; // rax
  __int64 *i; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 j; // rcx

  v4 = std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::_Buynode(a1);
  *(_QWORD *)(a1 + 8) = v4;
  *(_BYTE *)(v4 + 41) = 1;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  **(_QWORD **)(a1 + 8) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  try
  {
    v5 = *(_QWORD *)(a1 + 8);
    *(_QWORD *)(v5 + 8) = std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(
                            a1,
                            *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
                            v5);
    *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
    v6 = *(_QWORD **)(a1 + 8);
    v7 = (__int64 **)v6[1];
    if ( *((_BYTE *)v7 + 41) )
    {
      *v6 = v6;
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
    }
    else
    {
      for ( i = *v7; !*((_BYTE *)i + 41); i = (__int64 *)*i )
        v7 = (__int64 **)i;
      *v6 = v7;
      v9 = *(_QWORD *)(a1 + 8);
      v10 = *(_QWORD *)(v9 + 8);
      for ( j = *(_QWORD *)(v10 + 16); !*(_BYTE *)(j + 41); j = *(_QWORD *)(j + 16) )
        v10 = j;
      *(_QWORD *)(v9 + 16) = v10;
    }
  }
  catch ( ... )
  {
    std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::_Tidy(a1);
    throw;
  }
  return a1;
}

```

## disassembly

```asm
0x18000eff0  mov     rax, rsp
0x18000eff3  mov     [rax+8], rcx
0x18000eff7  push    rdi
0x18000eff8  sub     rsp, 30h
0x18000effc  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18000f004  mov     [rax+10h], rbx
0x18000f008  mov     [rax+18h], rsi
0x18000f00c  mov     rdi, rdx
0x18000f00f  mov     rbx, rcx
0x18000f012  call    ?_Buynode@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@2@XZ; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::_Buynode(void)
0x18000f017  mov     [rbx+8], rax
0x18000f01b  mov     byte ptr [rax+29h], 1
0x18000f01f  mov     rax, [rbx+8]
0x18000f023  mov     [rax+8], rax
0x18000f027  mov     rax, [rbx+8]
0x18000f02b  mov     [rax], rax
0x18000f02e  mov     rax, [rbx+8]
0x18000f032  mov     [rax+10h], rax
0x18000f036  and     qword ptr [rbx+10h], 0
0x18000f03b  mov     rdx, [rdi+8]
0x18000f03f  mov     rsi, [rbx+8]
0x18000f043  mov     r8, rsi
0x18000f046  mov     rdx, [rdx+8]
0x18000f04a  mov     rcx, rbx
0x18000f04d  call    ?_Copy@?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@2@PEAU342@0@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Copy(std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Node *)
0x18000f052  mov     [rsi+8], rax
0x18000f056  mov     rax, [rdi+10h]
0x18000f05a  mov     [rbx+10h], rax
0x18000f05e  mov     rdx, [rbx+8]
0x18000f062  mov     rax, [rdx+8]
0x18000f066  cmp     byte ptr [rax+29h], 0
0x18000f06a  jnz     short loc_18000F0A1
0x18000f06c  mov     rcx, [rax]
0x18000f06f  jmp     short loc_18000F077
0x18000f071  mov     rax, rcx
0x18000f074  mov     rcx, [rcx]
0x18000f077  cmp     byte ptr [rcx+29h], 0
0x18000f07b  jz      short loc_18000F071
0x18000f07d  mov     [rdx], rax
0x18000f080  mov     rdx, [rbx+8]
0x18000f084  mov     rax, [rdx+8]
0x18000f088  mov     rcx, [rax+10h]
0x18000f08c  jmp     short loc_18000F095
0x18000f08e  mov     rax, rcx
0x18000f091  mov     rcx, [rcx+10h]
0x18000f095  cmp     byte ptr [rcx+29h], 0
0x18000f099  jz      short loc_18000F08E
0x18000f09b  mov     [rdx+10h], rax
0x18000f09f  jmp     short loc_18000F0AC
0x18000f0a1  mov     [rdx], rdx
0x18000f0a4  mov     rax, [rbx+8]
0x18000f0a8  mov     [rax+10h], rax
0x18000f0ac  mov     rax, rbx
0x18000f0af  mov     rbx, [rsp+38h+arg_8]
0x18000f0b4  mov     rsi, [rsp+38h+arg_10]
0x18000f0b9  add     rsp, 30h
0x18000f0bd  pop     rdi
0x18000f0be  retn
```
