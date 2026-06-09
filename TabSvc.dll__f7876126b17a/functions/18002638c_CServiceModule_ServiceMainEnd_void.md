# CServiceModule::ServiceMainEnd(void)

- ea: `0x18002638c`
- end: `0x1800265b3`
- name: `?ServiceMainEnd@CServiceModule@@QEAAXXZ`
- size: `551`
- prototype: `void __fastcall(CServiceModule *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025bbc`
- `0x1800265c0`

## callees

- `0x1800010f8`
- `0x180011ae0`
- `0x180012c70`
- `0x180012dc0`
- `0x180015630`
- `0x1800197dc`
- `0x18001a174`
- `0x18002638c`
- `0x180028a24`
- `0x18002a1b4`
- `0x18002b3a8`
- `0x180031010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180026525`
- `api-ms-win-crt-private-l1-1-0!_o__aligned_free` at `0x180026525`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002649a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002649a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800264a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800264a7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180026482`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800264dc`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180026482`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800264dc`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180026514`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180026514`

## string_xrefs

- `0x1800263e2`: `PENSERVICE_CServiceModule::ServiceMainEnd`
- `0x180026573`: `PENSERVICE_CServiceModule::ServiceMainEnd`

## pseudocode

```c
void __fastcall CServiceModule::ServiceMainEnd(CServiceModule *this)
{
  CServiceModule *v1; // rdi
  CServiceModule *v2; // rsi
  struct _GUID *v3; // rcx
  unsigned __int64 v4; // r8
  __int64 v5; // rcx
  char *v6; // rbx
  __int64 v7; // rcx
  void *v8; // rcx
  unsigned int i; // r14d
  __int64 v10; // rbx
  PSLIST_ENTRY v11; // rax
  struct _SLIST_ENTRY *Next; // rbx
  __int64 j; // rcx
  int v14; // edx
  const struct _GUID *v15; // rcx
  struct _GUID *v16; // rax
  unsigned __int64 v17; // r8
  char *v22; // [rsp+60h] [rbp+18h]

  v1 = this;
  v2 = this;
  v3 = WPP_GLOBAL_Control;
  v4 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v4 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x612u, v4, 1u);
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != (struct _GUID *)&WPP_GLOBAL_Control && (v3[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v3[1].Data1,
      137,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ServiceMainEnd");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      (int)word_18003A1EA);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl'::`2'::impl) )
  {
    v6 = (char *)v1 + 632;
    v22 = (char *)v1 + 632;
    v7 = *((_QWORD *)v1 + 79);
    if ( v7 )
    {
      try
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7);
      }
      catch ( ... )
      {
        v1 = this;
        v2 = this;
        v6 = v22;
      }
      wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHost,wil::err_returncode_policy>::reset(v6);
    }
  }
  v8 = (void *)*((_QWORD *)v1 + 23);
  if ( v8 )
  {
    UnregisterWait(v8);
    *((_QWORD *)v1 + 23) = 0;
  }
  SetEvent(*((HANDLE *)v1 + 18));
  WaitForSingleObject(*((HANDLE *)v1 + 15), 0xFFFFFFFF);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
  {
    for ( i = 0; i < *((_DWORD *)v1 + 139); ++i )
    {
      v10 = 16LL * i;
      UnregisterWait(*(HANDLE *)(v10 + *((_QWORD *)v2 + 68) + 8));
      *(_QWORD *)(*((_QWORD *)v2 + 68) + v10 + 8) = 0;
      SH<void *,SH_HANDLE>::Reset(v10 + *((_QWORD *)v2 + 68));
    }
  }
  v11 = InterlockedFlushSList((PSLIST_HEADER)v1 + 38);
  if ( v11 )
  {
    do
    {
      Next = v11->Next;
      _aligned_free(v11);
      v11 = Next;
    }
    while ( Next );
  }
  for ( j = 0; j != 6; ++j )
    *(_DWORD *)(*((_QWORD *)v2 + j + 70) + 12LL) = 0;
  CTabTipProcessInfo::_AddRemoveUserAgentStringKey(0);
  CServiceModule::ShutdownDisabledPenProcesses(v1, v14);
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      138,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ServiceMainEnd");
    v16 = WPP_GLOBAL_Control;
  }
  v17 = *(_QWORD *)v16[3].Data4;
  if ( v17 )
    PrivateTraceEvent(v15, 0x612u, v17, 2u);
}

```

## disassembly

```asm
0x18002638c  mov     [rsp+arg_0], rcx
0x180026391  push    rbx
0x180026392  push    rsi
0x180026393  push    rdi
0x180026394  push    r14
0x180026396  push    r15
0x180026398  sub     rsp, 20h
0x18002639c  mov     rdi, rcx
0x18002639f  mov     rsi, rcx
0x1800263a2  mov     [rsp+48h+arg_8], rcx
0x1800263a7  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x1800263ae  mov     r8, [rcx+38h]; unsigned __int64
0x1800263b2  test    r8, r8
0x1800263b5  jz      short loc_1800263CB
0x1800263b7  mov     r9b, 1; unsigned __int8
0x1800263ba  mov     edx, 612h; unsigned int
0x1800263bf  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800263c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263cb  lea     r15, WPP_GLOBAL_Control
0x1800263d2  cmp     rcx, r15
0x1800263d5  jz      short loc_1800263F9
0x1800263d7  test    byte ptr [rcx+1Ch], 10h
0x1800263db  jz      short loc_1800263F9
0x1800263dd  mov     edx, 89h
0x1800263e2  lea     r9, aPenserviceCser_22; "PENSERVICE_CServiceModule::ServiceMainE"...
0x1800263e9  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800263f0  mov     rcx, [rcx+10h]
0x1800263f4  call    WPP_SF_s
0x1800263f9  mov     eax, cs:dword_1800411A8
0x1800263ff  cmp     eax, 5
0x180026402  jbe     short loc_180026425
0x180026404  mov     edx, 4000000h
0x180026409  lea     rcx, dword_1800411A8
0x180026410  call    _tlgKeywordOn
0x180026415  test    al, al
0x180026417  jz      short loc_180026425
0x180026419  lea     rdx, word_18003A1EA
0x180026420  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180026425  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KBBLS_55832275@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275> `wil::Feature<__WilFeatureTraits_Feature_KBBLS_55832275>::GetImpl(void)'::`2'::impl
0x18002642c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KBBLS_55832275@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KBBLS_55832275>::__private_IsEnabled(void)
0x180026431  test    al, al
0x180026433  jz      short loc_180026476
0x180026435  lea     rbx, [rdi+278h]
0x18002643c  mov     [rsp+48h+arg_10], rbx
0x180026441  mov     rcx, [rbx]
0x180026444  test    rcx, rcx
0x180026447  jz      short loc_180026476
0x180026449  mov     rax, [rcx]
0x18002644c  mov     rax, [rax+38h]
0x180026450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026455  nop
0x180026456  jmp     short loc_18002646E
0x180026458  lea     r15, WPP_GLOBAL_Control
0x18002645f  mov     rdi, [rsp+48h+arg_0]
0x180026464  mov     rsi, [rsp+48h+arg_8]
0x180026469  mov     rbx, [rsp+48h+arg_10]
0x18002646e  mov     rcx, rbx
0x180026471  call    ?reset@?$com_ptr_t@UIBacklightServerHost@BacklightServer@Lights@Devices@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::Devices::Lights::BacklightServer::IBacklightServerHost,wil::err_returncode_policy>::reset(void)
0x180026476  mov     rcx, [rdi+0B8h]; WaitHandle
0x18002647d  test    rcx, rcx
0x180026480  jz      short loc_180026493
0x180026482  call    cs:__imp_UnregisterWait
0x180026488  mov     qword ptr [rdi+0B8h], 0
0x180026493  mov     rcx, [rdi+90h]; hEvent
0x18002649a  call    cs:__imp_SetEvent
0x1800264a0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800264a3  mov     rcx, [rdi+78h]; hHandle
0x1800264a7  call    cs:__imp_WaitForSingleObject
0x1800264ad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59994706@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl(void)'::`2'::impl
0x1800264b4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(void)
0x1800264b9  test    al, al
0x1800264bb  jnz     short loc_18002650D
0x1800264bd  xor     r14d, r14d
0x1800264c0  cmp     [rdi+22Ch], r14d
0x1800264c7  jbe     short loc_18002650D
0x1800264c9  mov     ebx, r14d
0x1800264cc  shl     rbx, 4
0x1800264d0  mov     rcx, [rsi+220h]
0x1800264d7  mov     rcx, [rbx+rcx+8]; WaitHandle
0x1800264dc  call    cs:__imp_UnregisterWait
0x1800264e2  mov     rax, [rsi+220h]
0x1800264e9  mov     qword ptr [rax+rbx+8], 0
0x1800264f2  mov     rcx, [rsi+220h]
0x1800264f9  add     rcx, rbx
0x1800264fc  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180026501  inc     r14d
0x180026504  cmp     r14d, [rdi+22Ch]
0x18002650b  jb      short loc_1800264C9
0x18002650d  lea     rcx, [rdi+260h]; ListHead
0x180026514  call    cs:__imp_InterlockedFlushSList
0x18002651a  test    rax, rax
0x18002651d  jz      short loc_180026533
0x18002651f  mov     rbx, [rax]
0x180026522  mov     rcx, rax; Block
0x180026525  call    cs:__imp__aligned_free
0x18002652b  mov     rax, rbx
0x18002652e  test    rbx, rbx
0x180026531  jnz     short loc_18002651F
0x180026533  xor     ecx, ecx
0x180026535  mov     rax, [rsi+rcx*8+230h]
0x18002653d  mov     dword ptr [rax+0Ch], 0
0x180026544  inc     rcx
0x180026547  cmp     rcx, 6
0x18002654b  jnz     short loc_180026535
0x18002654d  xor     ecx, ecx; int
0x18002654f  call    ?_AddRemoveUserAgentStringKey@CTabTipProcessInfo@@CAXH@Z; CTabTipProcessInfo::_AddRemoveUserAgentStringKey(int)
0x180026554  mov     rcx, rdi; this
0x180026557  call    ?ShutdownDisabledPenProcesses@CServiceModule@@QEAAXH@Z; CServiceModule::ShutdownDisabledPenProcesses(int)
0x18002655c  mov     rax, cs:WPP_GLOBAL_Control
0x180026563  cmp     rax, r15
0x180026566  jz      short loc_180026591
0x180026568  test    byte ptr [rax+1Ch], 10h
0x18002656c  jz      short loc_180026591
0x18002656e  mov     edx, 8Ah
0x180026573  lea     r9, aPenserviceCser_22; "PENSERVICE_CServiceModule::ServiceMainE"...
0x18002657a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180026581  mov     rcx, [rax+10h]
0x180026585  call    WPP_SF_s
0x18002658a  mov     rax, cs:WPP_GLOBAL_Control
0x180026591  mov     r8, [rax+38h]; unsigned __int64
0x180026595  test    r8, r8
0x180026598  jz      short loc_1800265A7
0x18002659a  mov     r9b, 2; unsigned __int8
0x18002659d  mov     edx, 612h; unsigned int
0x1800265a2  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x1800265a7  add     rsp, 20h
0x1800265ab  pop     r15
0x1800265ad  pop     r14
0x1800265af  pop     rdi
0x1800265b0  pop     rsi
0x1800265b1  pop     rbx
0x1800265b2  retn
```
