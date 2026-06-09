# Persistence_ServiceStop(void)

- ea: `0x180057e6c`
- end: `0x180057fd9`
- name: `?Persistence_ServiceStop@@YAXXZ`
- size: `365`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180047380`

## callees

- `0x18001d560`
- `0x18001f374`
- `0x180021060`
- `0x180024190`
- `0x180024ca0`
- `0x180025dcc`
- `0x180026144`
- `0x1800368ec`
- `0x180057e6c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057eb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057eb5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180057fbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180057fbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180057fab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180057fab`

## pseudocode

```c
void Persistence_ServiceStop(void)
{
  const struct _tlgProvider_t *v0; // rax
  const struct _tlgProvider_t *v1; // rax
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  CPersistedControl *v5; // rbx
  __int128 v6; // [rsp+30h] [rbp-20h] BYREF
  int v7; // [rsp+40h] [rbp-10h]
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+60h] [rbp+10h] BYREF
  CPersistedControl *v9; // [rsp+68h] [rbp+18h] BYREF

  v7 = 0;
  v6 = 0;
  v9 = 0;
  v0 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v0 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v0,
      (unsigned __int8 *)byte_180077455);
  EnterCriticalSection(&g_PersistedControlListLock);
  v8 = &g_PersistedControlListLock;
  v1 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v1 > 4u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v1,
      (unsigned __int8 *)&dword_1800773F4);
  g_PersistenceInitialized = 0;
  while ( (unsigned int)TList<CPersistedControl>::RemoveHead(&g_PersistedControlList, &v9) )
    TList<CPersistedControl>::AddTail(&v6, v9);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v8);
  while ( (unsigned int)TList<CPersistedControl>::RemoveHead(&v6, &v9) )
  {
    v2 = AudioEndpointBuilderTelemetryProvider::Provider();
    v5 = v9;
    if ( *(_DWORD *)v2 > 4u )
    {
      LODWORD(v8) = *((_DWORD *)v9 + 16);
      v9 = (CPersistedControl *)*((_QWORD *)v9 + 9);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (__int64)v2,
        (unsigned __int8 *)byte_1800773A1,
        v3,
        v4,
        (const WCHAR **)&v9,
        (__int64)&v8);
    }
    CPersistedControl::UnregisterForControlChangeCallbacks(v5);
    CPersistedControl::WaitForPersistedChanges(v5);
    (*(void (__fastcall **)(CPersistedControl *))(*(_QWORD *)v5 + 48LL))(v5);
    (*(void (__fastcall **)(CPersistedControl *))(*(_QWORD *)v5 + 16LL))(v5);
    v9 = 0;
  }
  if ( g_PersistenceCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(g_PersistenceCleanupGroup, 1, 0);
    if ( g_PersistenceCleanupGroup )
    {
      CloseThreadpoolCleanupGroup(g_PersistenceCleanupGroup);
      g_PersistenceCleanupGroup = 0;
    }
  }
}

```

## disassembly

```asm
0x180057e6c  mov     [rsp-8+arg_10], rbx
0x180057e71  push    rbp
0x180057e72  mov     rbp, rsp
0x180057e75  sub     rsp, 50h
0x180057e79  xorps   xmm0, xmm0
0x180057e7c  mov     [rbp+var_10], 0
0x180057e83  movdqu  [rbp+var_20], xmm0
0x180057e88  mov     [rbp+arg_8], 0
0x180057e90  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180057e95  mov     ecx, [rax]
0x180057e97  cmp     ecx, 4
0x180057e9a  jbe     short loc_180057EAB
0x180057e9c  lea     rdx, byte_180077455
0x180057ea3  mov     rcx, rax
0x180057ea6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180057eab  lea     rbx, ?g_PersistedControlListLock@@3Vcritical_section@wil@@A; wil::critical_section g_PersistedControlListLock
0x180057eb2  mov     rcx, rbx; lpCriticalSection
0x180057eb5  call    cs:__imp_EnterCriticalSection
0x180057ebb  mov     [rbp+arg_0], rbx
0x180057ebf  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180057ec4  mov     ecx, [rax]
0x180057ec6  cmp     ecx, 4
0x180057ec9  jbe     short loc_180057EDA
0x180057ecb  lea     rdx, dword_1800773F4
0x180057ed2  mov     rcx, rax
0x180057ed5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180057eda  mov     cs:?g_PersistenceInitialized@@3_NA, 0; bool g_PersistenceInitialized
0x180057ee1  jmp     short loc_180057EF0
0x180057ee3  mov     rdx, [rbp+arg_8]
0x180057ee7  lea     rcx, [rbp+var_20]
0x180057eeb  call    ?AddTail@?$TList@VCPersistedControl@@@@QEAAPEAXPEAVCPersistedControl@@@Z; TList<CPersistedControl>::AddTail(CPersistedControl *)
0x180057ef0  lea     rdx, [rbp+arg_8]
0x180057ef4  lea     rcx, ?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A; TList<CPersistedControl> g_PersistedControlList
0x180057efb  call    ?RemoveHead@?$TList@VCPersistedControl@@@@QEAAHPEAPEAVCPersistedControl@@@Z; TList<CPersistedControl>::RemoveHead(CPersistedControl * *)
0x180057f00  test    eax, eax
0x180057f02  jnz     short loc_180057EE3
0x180057f04  lea     rcx, [rbp+arg_0]
0x180057f08  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x180057f0d  jmp     short loc_180057F84
0x180057f0f  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180057f14  mov     rbx, [rbp+arg_8]
0x180057f18  mov     ecx, [rax]
0x180057f1a  cmp     ecx, 4
0x180057f1d  jbe     short loc_180057F4E
0x180057f1f  mov     ecx, [rbx+40h]
0x180057f22  lea     rdx, byte_1800773A1
0x180057f29  mov     dword ptr [rbp+arg_0], ecx
0x180057f2c  mov     rcx, [rbx+48h]
0x180057f30  mov     [rbp+arg_8], rcx
0x180057f34  lea     rcx, [rbp+arg_0]
0x180057f38  mov     [rsp+50h+var_28], rcx
0x180057f3d  lea     rcx, [rbp+arg_8]
0x180057f41  mov     [rsp+50h+var_30], rcx
0x180057f46  mov     rcx, rax
0x180057f49  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180057f4e  mov     rcx, rbx; this
0x180057f51  call    ?UnregisterForControlChangeCallbacks@CPersistedControl@@QEAAJXZ; CPersistedControl::UnregisterForControlChangeCallbacks(void)
0x180057f56  mov     rcx, rbx; this
0x180057f59  call    ?WaitForPersistedChanges@CPersistedControl@@QEAAJXZ; CPersistedControl::WaitForPersistedChanges(void)
0x180057f5e  mov     rax, [rbx]
0x180057f61  mov     rcx, rbx
0x180057f64  mov     rax, [rax+30h]
0x180057f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f6d  mov     rax, [rbx]
0x180057f70  mov     rcx, rbx
0x180057f73  mov     rax, [rax+10h]
0x180057f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f7c  mov     [rbp+arg_8], 0
0x180057f84  lea     rdx, [rbp+arg_8]
0x180057f88  lea     rcx, [rbp+var_20]
0x180057f8c  call    ?RemoveHead@?$TList@VCPersistedControl@@@@QEAAHPEAPEAVCPersistedControl@@@Z; TList<CPersistedControl>::RemoveHead(CPersistedControl * *)
0x180057f91  test    eax, eax
0x180057f93  jnz     loc_180057F0F
0x180057f99  mov     rcx, cs:?g_PersistenceCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180057fa0  test    rcx, rcx
0x180057fa3  jz      short loc_180057FCE
0x180057fa5  xor     r8d, r8d; pvCleanupContext
0x180057fa8  lea     edx, [rax+1]; fCancelPendingCallbacks
0x180057fab  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180057fb1  mov     rcx, cs:?g_PersistenceCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180057fb8  test    rcx, rcx
0x180057fbb  jz      short loc_180057FCE
0x180057fbd  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180057fc3  mov     cs:?g_PersistenceCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * g_PersistenceCleanupGroup
0x180057fce  mov     rbx, [rsp+50h+arg_10]
0x180057fd3  add     rsp, 50h
0x180057fd7  pop     rbp
0x180057fd8  retn
```
