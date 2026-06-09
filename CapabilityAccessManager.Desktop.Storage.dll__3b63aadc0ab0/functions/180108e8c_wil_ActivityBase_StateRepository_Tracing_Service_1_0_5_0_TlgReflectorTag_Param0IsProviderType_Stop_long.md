# wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180108e8c`
- end: `0x180109001`
- name: `?Stop@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `373`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180108030`

## callees

- `0x180001e6c`
- `0x180003a40`
- `0x1800ec390`
- `0x1800f9e44`
- `0x1800fb134`
- `0x180108aac`
- `0x180108e8c`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180108ee3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180108ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108f7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180108f7e`

## string_xrefs

- `0x180108f9d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const struct _tlgProvider_t *__fastcall wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // esi
  int v5; // edi
  int v6; // esi
  const struct _tlgProvider_t *result; // rax
  __int64 v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rbx
  const struct _tlgProvider_t **v11; // rcx
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[184]; // [rsp+40h] [rbp-B8h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+108h] [rbp+10h] BYREF
  __int64 v17; // [rsp+110h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v3 = *(_QWORD *)(a1 + 272);
  v4 = *(_DWORD *)(v3 + 248);
  if ( v4 < 1 )
  {
    memset_0(v13, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v13, v12);
  }
  v5 = *(_DWORD *)(v3 + 72);
  if ( v5 >= 0 )
  {
    *(_DWORD *)(v3 + 72) = 0;
    v5 = 0;
  }
  v6 = v4 - 1;
  *(_DWORD *)(v3 + 248) = v6;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v6 )
  {
    result = StateRepository::Tracing::Service::Provider();
    v8 = (__int64)result;
    if ( *(_DWORD *)result > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v17 = 0x1000000;
      result = (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                                v8,
                                                (__int64)&word_18012A5EE,
                                                *(_QWORD *)(a1 + 272) + 8LL,
                                                v9,
                                                (__int64)&v17,
                                                (__int64)&SRWLock,
                                                (__int64)&CurrentThreadId);
    }
  }
  else
  {
    result = (const struct _tlgProvider_t *)wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                                              a1,
                                              (unsigned int)v5);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v10 = a1 + 288;
    if ( *(_DWORD *)(v10 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v10 + 24) = 0;
    v11 = *(const struct _tlgProvider_t ***)v10;
    while ( 1 )
    {
      result = *v11;
      if ( !*v11 )
        break;
      if ( result == (const struct _tlgProvider_t *)v10 )
      {
        result = *(const struct _tlgProvider_t **)(v10 + 16);
        *v11 = result;
        break;
      }
      v11 = (const struct _tlgProvider_t **)((char *)result + 16);
      *(_QWORD *)v10 = (char *)result + 16;
    }
    *(_QWORD *)v10 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180108e8c  mov     rax, rsp
0x180108e8f  mov     [rax+10h], edx
0x180108e92  push    rbx
0x180108e93  push    rsi
0x180108e94  push    rdi
0x180108e95  sub     rsp, 0E0h
0x180108e9c  mov     rbx, rcx
0x180108e9f  lea     rdx, [rax+8]
0x180108ea3  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180108ea8  mov     rax, [rbx+110h]
0x180108eaf  mov     esi, [rax+0F8h]
0x180108eb5  cmp     esi, 1
0x180108eb8  jl      loc_180108FE4
0x180108ebe  mov     edi, [rax+48h]
0x180108ec1  test    edi, edi
0x180108ec3  js      short loc_180108ECE
0x180108ec5  mov     dword ptr [rax+48h], 0
0x180108ecc  xor     edi, edi
0x180108ece  dec     esi
0x180108ed0  mov     [rax+0F8h], esi
0x180108ed6  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180108ede  test    rcx, rcx
0x180108ee1  jz      short loc_180108EEA
0x180108ee3  call    cs:__imp_ReleaseSRWLockExclusive
0x180108ee9  nop
0x180108eea  test    esi, esi
0x180108eec  jnz     short loc_180108EFA
0x180108eee  mov     edx, edi
0x180108ef0  mov     rcx, rbx
0x180108ef3  call    ?ReportStopActivity@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180108ef8  jmp     short loc_180108F6E
0x180108efa  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x180108eff  mov     rdi, rax
0x180108f02  mov     ecx, [rax]
0x180108f04  cmp     ecx, 5
0x180108f07  jbe     short loc_180108F6E
0x180108f09  call    cs:__imp_GetCurrentThreadId
0x180108f0f  mov     [rsp+0F8h+arg_8], eax
0x180108f16  mov     dword ptr [rsp+0F8h+SRWLock], 0
0x180108f21  mov     [rsp+0F8h+arg_10], 1000000h
0x180108f2d  mov     r8, [rbx+110h]
0x180108f34  add     r8, 8
0x180108f38  lea     rax, [rsp+0F8h+arg_8]
0x180108f40  mov     [rsp+0F8h+var_C8], rax
0x180108f45  lea     rax, [rsp+0F8h+SRWLock]
0x180108f4d  mov     [rsp+0F8h+var_D0], rax
0x180108f52  lea     rax, [rsp+0F8h+arg_10]
0x180108f5a  mov     [rsp+0F8h+var_D8], rax
0x180108f5f  lea     rdx, word_18012A5EE
0x180108f66  mov     rcx, rdi
0x180108f69  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180108f6e  cmp     dword ptr [rbx+138h], 0
0x180108f75  jz      short loc_180108FD9
0x180108f77  add     rbx, 120h
0x180108f7e  call    cs:__imp_GetCurrentThreadId
0x180108f84  cmp     [rbx+18h], eax
0x180108f87  jz      short loc_180108FA9
0x180108f89  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180108f90  test    rax, rax
0x180108f93  jz      short loc_180108FA9
0x180108f95  mov     rdx, [rsp+0F8h]
0x180108f9d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x180108fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108fa9  mov     dword ptr [rbx+18h], 0
0x180108fb0  mov     rcx, [rbx]
0x180108fb3  jmp     short loc_180108FC1
0x180108fb5  cmp     rax, rbx
0x180108fb8  jz      short loc_180108FCB
0x180108fba  lea     rcx, [rax+10h]
0x180108fbe  mov     [rbx], rcx
0x180108fc1  mov     rax, [rcx]
0x180108fc4  test    rax, rax
0x180108fc7  jnz     short loc_180108FB5
0x180108fc9  jmp     short loc_180108FD2
0x180108fcb  mov     rax, [rbx+10h]
0x180108fcf  mov     [rcx], rax
0x180108fd2  mov     qword ptr [rbx], 0
0x180108fd9  add     rsp, 0E0h
0x180108fe0  pop     rdi
0x180108fe1  pop     rsi
0x180108fe2  pop     rbx
0x180108fe3  retn
0x180108fe4  xor     edx, edx; Val
0x180108fe6  mov     r8d, 98h; Size
0x180108fec  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180108ff1  call    memset_0
0x180108ff6  lea     rcx, [rsp+0F8h+var_B8]; this
0x180108ffb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
