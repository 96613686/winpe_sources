# SearchIndexerDiagnosticTelemetry::QueryParserLoadFromPropertySystem::StartActivity(void)

- ea: `0x180069868`
- end: `0x180069981`
- name: `?StartActivity@QueryParserLoadFromPropertySystem@SearchIndexerDiagnosticTelemetry@@QEAAXXZ`
- size: `281`
- prototype: `void __fastcall(SearchIndexerDiagnosticTelemetry::QueryParserLoadFromPropertySystem *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800277a0`

## callees

- `0x18000172c`
- `0x18004f390`
- `0x18004fbd4`
- `0x18005a854`
- `0x18005ab98`
- `0x18005c03c`
- `0x180069868`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800698b1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800698b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800698f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800698f9`

## pseudocode

```c
void __fastcall SearchIndexerDiagnosticTelemetry::QueryParserLoadFromPropertySystem::StartActivity(
        SearchIndexerDiagnosticTelemetry::QueryParserLoadFromPropertySystem *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<SearchIndexerDiagnosticsLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v13);
  v2 = *((_QWORD *)this + 34);
  v3 = SearchIndexerDiagnosticsLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v6 = SearchIndexerDiagnosticsLogging::Provider();
  v10 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v8, v9) )
  {
    LODWORD(v13) = GetCurrentThreadId();
    v14 = 0x1000000;
    v11 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)word_1800A4A1A,
      v11 + 8,
      v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (SearchIndexerDiagnosticTelemetry::QueryParserLoadFromPropertySystem *)((char *)this + 288),
      v7);
}

```

## disassembly

```asm
0x180069868  mov     [rsp+arg_10], rbx
0x18006986d  push    rdi
0x18006986e  sub     rsp, 30h
0x180069872  mov     rdi, rcx
0x180069875  lea     rdx, [rsp+38h+arg_0]
0x18006987a  call    ?LockExclusive@?$ActivityBase@VSearchIndexerDiagnosticsLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SearchIndexerDiagnosticsLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006987f  mov     rbx, [rdi+110h]
0x180069886  call    ?Provider@SearchIndexerDiagnosticsLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerDiagnosticsLogging::Provider(void)
0x18006988b  mov     edx, [rax]
0x18006988d  cmp     edx, 5
0x180069890  jbe     short loc_1800698B9
0x180069892  mov     rdx, 400000000000h
0x18006989c  mov     rcx, rax
0x18006989f  call    _tlgKeywordOn
0x1800698a4  test    al, al
0x1800698a6  jz      short loc_1800698B9
0x1800698a8  lea     rdx, [rbx+8]; ActivityId
0x1800698ac  mov     ecx, 3; ControlCode
0x1800698b1  call    cs:__imp_EventActivityIdControl
0x1800698b7  jmp     short loc_1800698C0
0x1800698b9  xorps   xmm0, xmm0
0x1800698bc  movups  xmmword ptr [rbx+8], xmm0
0x1800698c0  mov     dword ptr [rbx], 1
0x1800698c6  lea     rcx, [rsp+38h+arg_0]
0x1800698cb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800698d0  call    ?Provider@SearchIndexerDiagnosticsLogging@@SAPEBU_tlgProvider_t@@XZ; SearchIndexerDiagnosticsLogging::Provider(void)
0x1800698d5  mov     rbx, rax
0x1800698d8  mov     ecx, [rax]
0x1800698da  cmp     ecx, 5
0x1800698dd  jbe     loc_180069963
0x1800698e3  mov     rdx, 400000000000h
0x1800698ed  mov     rcx, rax
0x1800698f0  call    _tlgKeywordOn
0x1800698f5  test    al, al
0x1800698f7  jz      short loc_180069963
0x1800698f9  call    cs:__imp_GetCurrentThreadId
0x1800698ff  mov     dword ptr [rsp+38h+arg_0], eax
0x180069903  mov     [rsp+38h+arg_8], 1000000h
0x18006990c  mov     r8, [rdi+110h]
0x180069913  cmp     byte ptr [r8+4], 0
0x180069918  jz      short loc_180069939
0x18006991a  lea     r9, [r8+18h]
0x18006991e  cmp     dword ptr [r9], 0
0x180069922  jnz     short loc_18006993C
0x180069924  cmp     dword ptr [r9+4], 0
0x180069929  jnz     short loc_18006993C
0x18006992b  cmp     dword ptr [r9+8], 0
0x180069930  jnz     short loc_18006993C
0x180069932  cmp     dword ptr [r9+0Ch], 0
0x180069937  jnz     short loc_18006993C
0x180069939  xor     r9d, r9d
0x18006993c  add     r8, 8
0x180069940  lea     rax, [rsp+38h+arg_0]
0x180069945  mov     [rsp+38h+var_10], rax
0x18006994a  lea     rax, [rsp+38h+arg_8]
0x18006994f  mov     [rsp+38h+var_18], rax
0x180069954  lea     rdx, word_1800A4A1A
0x18006995b  mov     rcx, rbx
0x18006995e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180069963  lea     rcx, [rdi+120h]; this
0x18006996a  cmp     dword ptr [rcx+18h], 0
0x18006996e  jnz     short loc_180069976
0x180069970  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180069975  nop
0x180069976  mov     rbx, [rsp+38h+arg_10]
0x18006997b  add     rsp, 30h
0x18006997f  pop     rdi
0x180069980  retn
```
