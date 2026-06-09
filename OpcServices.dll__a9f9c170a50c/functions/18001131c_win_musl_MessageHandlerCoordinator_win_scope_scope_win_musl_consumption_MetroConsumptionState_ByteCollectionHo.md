# win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::EventQueueEmpty(void)

- ea: `0x18001131c`
- end: `0x18001139e`
- name: `?EventQueueEmpty@?$MessageHandlers@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@QEAA_NXZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011438`

## callees

- `0x18001131c`
- `0x180015114`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011358`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011345`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011345`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::MessageHandlers<win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>::EventQueueEmpty(
        __int64 a1)
{
  __int64 v2; // rbx
  win_dox *v3; // rcx
  int v4; // edx
  bool v5; // si

  v2 = a1 + 136;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 136));
  v4 = *(_DWORD *)(v2 + 44);
  *(_DWORD *)(v2 + 44) = v4 + 1;
  if ( !v4 )
    *(_DWORD *)(v2 + 40) = GetCurrentThreadId();
  LOBYTE(v3) = *(_BYTE *)(a1 + 128);
  win_dox::ThrowIfFailed(v3, v4);
  v5 = *(_QWORD *)(a1 + 120) == 0;
  if ( (*(_DWORD *)(v2 + 44))-- == 1 )
    *(_DWORD *)(v2 + 40) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
  return v5;
}

```

## disassembly

```asm
0x18001131c  mov     rax, rsp
0x18001131f  push    rdi
0x180011320  sub     rsp, 30h
0x180011324  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x18001132c  mov     [rax+10h], rbx
0x180011330  mov     [rax+18h], rsi
0x180011334  mov     rsi, rcx
0x180011337  lea     rbx, [rcx+88h]
0x18001133e  mov     [rax+8], rbx
0x180011342  mov     rcx, rbx; lpCriticalSection
0x180011345  call    cs:__imp_EnterCriticalSection
0x18001134b  mov     edx, [rbx+2Ch]
0x18001134e  lea     eax, [rdx+1]
0x180011351  mov     [rbx+2Ch], eax
0x180011354  test    edx, edx
0x180011356  jnz     short loc_180011361
0x180011358  call    cs:__imp_GetCurrentThreadId
0x18001135e  mov     [rbx+28h], eax
0x180011361  mov     cl, [rsi+80h]; this
0x180011367  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x18001136c  cmp     qword ptr [rsi+78h], 0
0x180011371  setz    sil
0x180011375  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x180011379  jnz     short loc_180011382
0x18001137b  mov     dword ptr [rbx+28h], 0
0x180011382  mov     rcx, rbx; lpCriticalSection
0x180011385  call    cs:__imp_LeaveCriticalSection
0x18001138b  mov     al, sil
0x18001138e  mov     rbx, [rsp+38h+arg_8]
0x180011393  mov     rsi, [rsp+38h+arg_10]
0x180011398  add     rsp, 30h
0x18001139c  pop     rdi
0x18001139d  retn
```
