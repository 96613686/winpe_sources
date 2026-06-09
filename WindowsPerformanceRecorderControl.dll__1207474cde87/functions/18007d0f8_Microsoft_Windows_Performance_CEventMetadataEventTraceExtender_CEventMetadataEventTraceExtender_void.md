# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x18007d0f8`
- end: `0x18007d284`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `396`
- prototype: `Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d70c`

## callees

- `0x180009b40`
- `0x18001c820`
- `0x18007d0f8`
- `0x18007dbfc`
- `0x18007dc30`

## string_xrefs

- `0x18007d170`: `tdh.dll`
- `0x18007d165`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18007d1f0`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x18007d24a`: `TdhLoadManifestFromBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  _QWORD *v2; // rcx

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable';
  *((_BYTE *)this + 32) = 0;
  v2 = (_QWORD *)((char *)this + 40);
  *v2 = 0;
  v2[1] = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Alloc_sentinel_and_proxy(v2);
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 17) = L"tdh.dll";
  *((_BYTE *)this + 144) = 0;
  *((_QWORD *)this + 19) = (char *)this + 120;
  *((_QWORD *)this + 20) = "TdhQueryProviderFieldInformation";
  *((_QWORD *)this + 21) = 0;
  *((_BYTE *)this + 176) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 200);
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Alloc_sentinel_and_proxy((char *)this + 208);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 30) = L"tdh.dll";
  *((_BYTE *)this + 248) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = L"ext-ms-win-eventing-tdh-ext-l1-1-0.dll";
  *((_QWORD *)this + 34) = L"tdh.dll";
  *((_BYTE *)this + 280) = 0;
  *((_QWORD *)this + 36) = (char *)this + 224;
  *((_QWORD *)this + 37) = "TdhGetEventInformation";
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *((_QWORD *)this + 40) = (char *)this + 224;
  *((_QWORD *)this + 41) = "TdhGetEventMapInformation";
  *((_QWORD *)this + 42) = 0;
  *((_BYTE *)this + 344) = 0;
  *((_QWORD *)this + 44) = (char *)this + 256;
  *((_QWORD *)this + 45) = "TdhLoadManifestFromBinary";
  *((_QWORD *)this + 46) = 0;
  *((_BYTE *)this + 376) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 288) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x18007d0f8  mov     [rsp+arg_0], rcx
0x18007d0fd  push    rbp
0x18007d0fe  push    rsi
0x18007d0ff  push    rdi
0x18007d100  sub     rsp, 30h
0x18007d104  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18007d10d  mov     [rsp+48h+arg_10], rbx
0x18007d112  mov     rbx, rcx
0x18007d115  xor     ebp, ebp
0x18007d117  mov     [rcx+18h], ebp
0x18007d11a  mov     [rcx+8], rbp
0x18007d11e  mov     [rcx+10h], rbp
0x18007d122  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x18007d129  mov     [rcx], rax
0x18007d12c  mov     [rcx+20h], bpl
0x18007d130  add     rcx, 28h ; '('
0x18007d134  mov     [rcx], rbp
0x18007d137  mov     [rcx+8], rbp
0x18007d13b  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18007d140  nop
0x18007d141  mov     [rbx+38h], rbp
0x18007d145  mov     [rbx+40h], ebp
0x18007d148  mov     [rbx+48h], rbp
0x18007d14c  mov     [rbx+50h], ebp
0x18007d14f  mov     [rbx+58h], rbp
0x18007d153  mov     [rbx+60h], ebp
0x18007d156  mov     [rbx+68h], rbp
0x18007d15a  mov     [rbx+70h], rbp
0x18007d15e  lea     rax, [rbx+78h]
0x18007d162  mov     [rax], rbp
0x18007d165  lea     rdi, aApiMsWinEventi_5; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x18007d16c  mov     [rax+8], rdi
0x18007d170  lea     rsi, aTdhDll; "tdh.dll"
0x18007d177  mov     [rax+10h], rsi
0x18007d17b  mov     [rax+18h], bpl
0x18007d17f  mov     [rbx+98h], rax
0x18007d186  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x18007d18d  mov     [rbx+0A0h], rax
0x18007d194  mov     [rbx+0A8h], rbp
0x18007d19b  mov     [rbx+0B0h], bpl
0x18007d1a2  mov     [rbx+0B8h], rbp
0x18007d1a9  mov     [rbx+0C0h], rbp
0x18007d1b0  lea     rcx, [rbx+0C8h]; void *
0x18007d1b7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18007d1bc  nop
0x18007d1bd  lea     rcx, [rbx+0D0h]
0x18007d1c4  mov     [rcx], rbp
0x18007d1c7  mov     [rcx+8], rbp
0x18007d1cb  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18007d1d0  lea     rdx, [rbx+0E0h]
0x18007d1d7  mov     [rdx], rbp
0x18007d1da  mov     [rdx+8], rdi
0x18007d1de  mov     [rdx+10h], rsi
0x18007d1e2  mov     [rdx+18h], bpl
0x18007d1e6  lea     rax, [rbx+100h]
0x18007d1ed  mov     [rax], rbp
0x18007d1f0  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x18007d1f7  mov     [rax+8], rcx
0x18007d1fb  mov     [rax+10h], rsi
0x18007d1ff  mov     [rax+18h], bpl
0x18007d203  lea     rcx, [rbx+120h]
0x18007d20a  mov     [rcx], rdx
0x18007d20d  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x18007d214  mov     [rcx+8], r8
0x18007d218  mov     [rcx+10h], rbp
0x18007d21c  mov     [rcx+18h], bpl
0x18007d220  mov     [rbx+140h], rdx
0x18007d227  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x18007d22e  mov     [rbx+148h], rdx
0x18007d235  mov     [rbx+150h], rbp
0x18007d23c  mov     [rbx+158h], bpl
0x18007d243  mov     [rbx+160h], rax
0x18007d24a  lea     rax, aTdhloadmanifes_0; "TdhLoadManifestFromBinary"
0x18007d251  mov     [rbx+168h], rax
0x18007d258  mov     [rbx+170h], rbp
0x18007d25f  mov     [rbx+178h], bpl
0x18007d266  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18007d26b  test    rax, rax
0x18007d26e  jnz     short loc_18007D274
0x18007d270  mov     byte ptr [rbx+20h], 1
0x18007d274  mov     rax, rbx
0x18007d277  mov     rbx, [rsp+48h+arg_10]
0x18007d27c  add     rsp, 30h
0x18007d280  pop     rdi
0x18007d281  pop     rsi
0x18007d282  pop     rbp
0x18007d283  retn
```
