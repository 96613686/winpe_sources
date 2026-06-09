# std::_Tree<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Node *,std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>> const &,char)

- ea: `0x18000fe00`
- end: `0x18000fe93`
- name: `?_Buynode@?$_Tree@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@$0A@@std@@@2@PEAU342@00AEBU?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@2@D@Z`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f0c0`

## callees

- `0x18000eff0`
- `0x18000fe00`
- `0x18002687c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>,0>>::_Buynode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  _QWORD *v12; // [rsp+50h] [rbp+8h]

  v8 = operator new(0x40u);
  v10 = v8;
  v12 = v8;
  try
  {
    if ( v8 )
    {
      *v8 = a2;
      v8[1] = a3;
      v8[2] = a4;
      *((_DWORD *)v8 + 6) = *a5;
      std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(
        (__int64)(v8 + 4),
        (__int64)(a5 + 2));
      *((_WORD *)v10 + 28) = 0;
    }
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v9, v12);
    throw;
  }
  return v10;
}

```

## disassembly

```asm
0x18000fe00  mov     rax, rsp
0x18000fe03  mov     [rax+8], rcx
0x18000fe07  push    r14
0x18000fe09  sub     rsp, 40h
0x18000fe0d  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000fe15  mov     [rax+10h], rbx
0x18000fe19  mov     [rax+18h], rsi
0x18000fe1d  mov     [rax+20h], rdi
0x18000fe21  mov     rdi, r9
0x18000fe24  mov     rsi, r8
0x18000fe27  mov     r14, rdx
0x18000fe2a  mov     ecx, 40h ; '@'; Size
0x18000fe2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe34  mov     rbx, rax
0x18000fe37  mov     [rsp+48h+arg_0], rax
0x18000fe3c  mov     [rsp+48h+var_20], rax
0x18000fe41  test    rax, rax
0x18000fe44  jz      short loc_18000FE7A
0x18000fe46  mov     [rax], r14
0x18000fe49  mov     [rax+8], rsi
0x18000fe4d  mov     [rax+10h], rdi
0x18000fe51  lea     rcx, [rax+18h]
0x18000fe55  mov     [rsp+48h+var_18], rcx
0x18000fe5a  mov     rdx, [rsp+48h+arg_20]
0x18000fe5f  mov     eax, [rdx]
0x18000fe61  mov     [rcx], eax
0x18000fe63  add     rcx, 8
0x18000fe67  mov     [rsp+48h+var_18], rcx
0x18000fe6c  add     rdx, 8
0x18000fe70  call    ??0?$_Tree@V?$_Tset_traits@U_EVENT_DESCRIPTOR@@UlessEVENT_DESCRIPTOR@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@V?$allocator@U_EVENT_DESCRIPTOR@@@std@@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>>(std::_Tree<std::_Tset_traits<_EVENT_DESCRIPTOR,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::lessEVENT_DESCRIPTOR,std::allocator<_EVENT_DESCRIPTOR>,0>> const &)
0x18000fe75  and     word ptr [rbx+38h], 0
0x18000fe7a  mov     rax, rbx
0x18000fe7d  mov     rbx, [rsp+48h+arg_8]
0x18000fe82  mov     rsi, [rsp+48h+arg_10]
0x18000fe87  mov     rdi, [rsp+48h+arg_18]
0x18000fe8c  add     rsp, 40h
0x18000fe90  pop     r14
0x18000fe92  retn
```
