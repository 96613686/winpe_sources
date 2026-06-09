# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(void)

- ea: `0x180017710`
- end: `0x180017909`
- name: `??0CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `505`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019690`

## callees

- `0x180017710`
- `0x1800185f8`
- `0x18001a2c0`
- `0x18001a364`
- `0x180027910`

## string_xrefs

- `0x1800177b8`: `tdh.dll`
- `0x1800177ad`: `api-ms-win-eventing-tdh-l1-1-0.dll`
- `0x18001786f`: `ext-ms-win-eventing-tdh-ext-l1-1-0.dll`
- `0x1800178c9`: `TdhLoadManifestFromBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CEventMetadataEventTraceExtender(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)
{
  char *v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rax

  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable';
  *((_BYTE *)this + 32) = 0;
  v2 = (char *)this + 40;
  v3 = std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Buynode(this);
  *((_QWORD *)v2 + 1) = v3;
  *(_BYTE *)(v3 + 137) = 1;
  *(_QWORD *)(*((_QWORD *)v2 + 1) + 8LL) = *((_QWORD *)v2 + 1);
  **((_QWORD **)v2 + 1) = *((_QWORD *)v2 + 1);
  *(_QWORD *)(*((_QWORD *)v2 + 1) + 16LL) = *((_QWORD *)v2 + 1);
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 18) = L"tdh.dll";
  *((_BYTE *)this + 152) = 0;
  *((_QWORD *)this + 20) = (char *)this + 128;
  *((_QWORD *)this + 21) = "TdhQueryProviderFieldInformation";
  *((_QWORD *)this + 22) = 0;
  *((_BYTE *)this + 184) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v5 = std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Buynode(v4);
  *((_QWORD *)this + 28) = v5;
  *(_BYTE *)(v5 + 105) = 1;
  *(_QWORD *)(*((_QWORD *)this + 28) + 8LL) = *((_QWORD *)this + 28);
  **((_QWORD **)this + 28) = *((_QWORD *)this + 28);
  *(_QWORD *)(*((_QWORD *)this + 28) + 16LL) = *((_QWORD *)this + 28);
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = L"api-ms-win-eventing-tdh-l1-1-0.dll";
  *((_QWORD *)this + 32) = L"tdh.dll";
  *((_BYTE *)this + 264) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = L"ext-ms-win-eventing-tdh-ext-l1-1-0.dll";
  *((_QWORD *)this + 36) = L"tdh.dll";
  *((_BYTE *)this + 296) = 0;
  *((_QWORD *)this + 38) = (char *)this + 240;
  *((_QWORD *)this + 39) = "TdhGetEventInformation";
  *((_QWORD *)this + 40) = 0;
  *((_BYTE *)this + 328) = 0;
  *((_QWORD *)this + 42) = (char *)this + 240;
  *((_QWORD *)this + 43) = "TdhGetEventMapInformation";
  *((_QWORD *)this + 44) = 0;
  *((_BYTE *)this + 360) = 0;
  *((_QWORD *)this + 46) = (char *)this + 272;
  *((_QWORD *)this + 47) = "TdhLoadManifestFromBinary";
  *((_QWORD *)this + 48) = 0;
  *((_BYTE *)this + 392) = 0;
  if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 38) )
    *((_BYTE *)this + 32) = 1;
  return this;
}

```

## disassembly

```asm
0x180017710  mov     rax, rsp
0x180017713  mov     [rax+8], rcx
0x180017717  push    rsi
0x180017718  push    rdi
0x180017719  push    r14
0x18001771b  sub     rsp, 30h
0x18001771f  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180017727  mov     [rax+18h], rbx
0x18001772b  mov     [rax+20h], rbp
0x18001772f  mov     rdi, rcx
0x180017732  xor     r14d, r14d
0x180017735  mov     [rcx+18h], r14d
0x180017739  mov     [rcx+8], r14
0x18001773d  mov     [rcx+10h], r14
0x180017741  lea     rax, ??_7CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@6B@; const Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::`vftable'
0x180017748  mov     [rcx], rax
0x18001774b  mov     [rcx+20h], r14b
0x18001774f  lea     rbx, [rcx+28h]
0x180017753  mov     [rsp+48h+arg_8], rbx
0x180017758  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>,0>>::_Buynode(void)
0x18001775d  mov     [rbx+8], rax
0x180017761  mov     byte ptr [rax+89h], 1
0x180017768  mov     rax, [rbx+8]
0x18001776c  mov     [rax+8], rax
0x180017770  mov     rax, [rbx+8]
0x180017774  mov     [rax], rax
0x180017777  mov     rax, [rbx+8]
0x18001777b  mov     [rax+10h], rax
0x18001777f  mov     [rbx+10h], r14
0x180017783  mov     [rdi+40h], r14
0x180017787  mov     [rdi+48h], r14d
0x18001778b  mov     [rdi+50h], r14
0x18001778f  mov     [rdi+58h], r14d
0x180017793  mov     [rdi+60h], r14
0x180017797  mov     [rdi+68h], r14d
0x18001779b  mov     [rdi+70h], r14
0x18001779f  mov     [rdi+78h], r14
0x1800177a3  lea     rax, [rdi+80h]
0x1800177aa  mov     [rax], r14
0x1800177ad  lea     rsi, aApiMsWinEventi; "api-ms-win-eventing-tdh-l1-1-0.dll"
0x1800177b4  mov     [rax+8], rsi
0x1800177b8  lea     rbp, aTdhDll; "tdh.dll"
0x1800177bf  mov     [rax+10h], rbp
0x1800177c3  mov     [rax+18h], r14b
0x1800177c7  mov     [rdi+0A0h], rax
0x1800177ce  lea     rax, aTdhqueryprovid; "TdhQueryProviderFieldInformation"
0x1800177d5  mov     [rdi+0A8h], rax
0x1800177dc  mov     [rdi+0B0h], r14
0x1800177e3  mov     [rdi+0B8h], r14b
0x1800177ea  mov     [rdi+0C0h], r14
0x1800177f1  mov     [rdi+0C8h], r14
0x1800177f8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800177ff  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180017806  mov     rax, [rax+18h]
0x18001780a  call    cs:__guard_dispatch_icall_fptr
0x180017810  add     rax, 18h
0x180017814  mov     [rdi+0D0h], rax
0x18001781b  lea     rbx, [rdi+0D8h]
0x180017822  mov     [rsp+48h+arg_8], rbx
0x180017827  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@U_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@U_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderState@CEventSourceHandler@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventSourceHandler::CProviderState>>,0>>::_Buynode(void)
0x18001782c  mov     [rbx+8], rax
0x180017830  mov     byte ptr [rax+69h], 1
0x180017834  mov     rax, [rbx+8]
0x180017838  mov     [rax+8], rax
0x18001783c  mov     rax, [rbx+8]
0x180017840  mov     [rax], rax
0x180017843  mov     rax, [rbx+8]
0x180017847  mov     [rax+10h], rax
0x18001784b  mov     [rbx+10h], r14
0x18001784f  lea     rdx, [rdi+0F0h]
0x180017856  mov     [rdx], r14
0x180017859  mov     [rdx+8], rsi
0x18001785d  mov     [rdx+10h], rbp
0x180017861  mov     [rdx+18h], r14b
0x180017865  lea     rax, [rdi+110h]
0x18001786c  mov     [rax], r14
0x18001786f  lea     rcx, aExtMsWinEventi; "ext-ms-win-eventing-tdh-ext-l1-1-0.dll"
0x180017876  mov     [rax+8], rcx
0x18001787a  mov     [rax+10h], rbp
0x18001787e  mov     [rax+18h], r14b
0x180017882  lea     rcx, [rdi+130h]
0x180017889  mov     [rcx], rdx
0x18001788c  lea     r8, aTdhgeteventinf; "TdhGetEventInformation"
0x180017893  mov     [rcx+8], r8
0x180017897  mov     [rcx+10h], r14
0x18001789b  mov     [rcx+18h], r14b
0x18001789f  mov     [rdi+150h], rdx
0x1800178a6  lea     rdx, aTdhgeteventmap; "TdhGetEventMapInformation"
0x1800178ad  mov     [rdi+158h], rdx
0x1800178b4  mov     [rdi+160h], r14
0x1800178bb  mov     [rdi+168h], r14b
0x1800178c2  mov     [rdi+170h], rax
0x1800178c9  lea     rax, aTdhloadmanifes; "TdhLoadManifestFromBinary"
0x1800178d0  mov     [rdi+178h], rax
0x1800178d7  mov     [rdi+180h], r14
0x1800178de  mov     [rdi+188h], r14b
0x1800178e5  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800178ea  test    rax, rax
0x1800178ed  jnz     short loc_1800178F3
0x1800178ef  mov     byte ptr [rdi+20h], 1
0x1800178f3  mov     rax, rdi
0x1800178f6  mov     rbx, [rsp+48h+arg_10]
0x1800178fb  mov     rbp, [rsp+48h+arg_18]
0x180017900  add     rsp, 30h
0x180017904  pop     r14
0x180017906  pop     rdi
0x180017907  pop     rsi
0x180017908  retn
```
