# wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800208d8`
- end: `0x180020a50`
- name: `?Stop@?$ActivityBase@VReliability@Providers@TraceLog@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `376`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18001fd0c`
- `0x180020a58`

## callees

- `0x1800015d0`
- `0x180003d14`
- `0x18000a4f0`
- `0x180010810`
- `0x1800203f8`
- `0x1800204b8`
- `0x1800208d8`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002092e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002092e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800209c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800209c5`

## string_xrefs

- `0x1800209e4`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
const struct _tlgProvider_t *__fastcall wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // esi
  int v6; // edi
  int v7; // esi
  const struct _tlgProvider_t *result; // rax
  __int64 v9; // rdi
  __int64 v10; // r9
  __int64 v11; // rbx
  const struct _tlgProvider_t **v12; // rcx
  const struct wil::FailureInfo *v13; // rdx
  _BYTE v14[184]; // [rsp+40h] [rbp-B8h] BYREF
  void *retaddr; // [rsp+F8h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+100h] [rbp+8h] BYREF
  int v17; // [rsp+110h] [rbp+18h] BYREF
  __int64 v18; // [rsp+118h] [rbp+20h] BYREF

  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v14, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v14, v13);
  }
  v6 = *(_DWORD *)(v4 + 72);
  if ( v6 >= 0 )
  {
    *(_DWORD *)(v4 + 72) = a2;
    v6 = a2;
  }
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v7 )
  {
    result = TraceLog::Providers::Reliability::Provider();
    v9 = (__int64)result;
    if ( *(_DWORD *)result > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v17 = a2;
      v18 = 0x1000000;
      result = (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                                v9,
                                                (__int64)byte_18003D315,
                                                *(_QWORD *)(a1 + 272) + 8LL,
                                                v10,
                                                (__int64)&v18,
                                                (__int64)&v17,
                                                (__int64)&SRWLock);
    }
  }
  else
  {
    result = (const struct _tlgProvider_t *)wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                                              (_QWORD *)a1,
                                              v6);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v11 = a1 + 288;
    if ( *(_DWORD *)(v11 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *(_DWORD *)(v11 + 24) = 0;
    v12 = *(const struct _tlgProvider_t ***)v11;
    while ( 1 )
    {
      result = *v12;
      if ( !*v12 )
        break;
      if ( result == (const struct _tlgProvider_t *)v11 )
      {
        result = *(const struct _tlgProvider_t **)(v11 + 16);
        *v12 = result;
        break;
      }
      v12 = (const struct _tlgProvider_t **)((char *)result + 16);
      *(_QWORD *)v11 = (char *)result + 16;
    }
    *(_QWORD *)v11 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800208d8  mov     rax, rsp
0x1800208db  mov     [rax+10h], rbx
0x1800208df  push    rbp
0x1800208e0  push    rsi
0x1800208e1  push    rdi
0x1800208e2  sub     rsp, 0E0h
0x1800208e9  mov     ebp, edx
0x1800208eb  mov     rbx, rcx
0x1800208ee  lea     rdx, [rax+8]
0x1800208f2  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800208f7  mov     rax, [rbx+110h]
0x1800208fe  mov     esi, [rax+0F8h]
0x180020904  cmp     esi, 1
0x180020907  jl      loc_180020A33
0x18002090d  mov     edi, [rax+48h]
0x180020910  test    edi, edi
0x180020912  js      short loc_180020919
0x180020914  mov     [rax+48h], ebp
0x180020917  mov     edi, ebp
0x180020919  dec     esi
0x18002091b  mov     [rax+0F8h], esi
0x180020921  mov     rcx, [rsp+0F8h+SRWLock]; SRWLock
0x180020929  test    rcx, rcx
0x18002092c  jz      short loc_180020934
0x18002092e  call    cs:__imp_ReleaseSRWLockExclusive
0x180020934  test    esi, esi
0x180020936  jnz     short loc_180020944
0x180020938  mov     edx, edi
0x18002093a  mov     rcx, rbx
0x18002093d  call    ?ReportStopActivity@?$ActivityBase@VReliability@Providers@TraceLog@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<TraceLog::Providers::Reliability,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x180020942  jmp     short loc_1800209B5
0x180020944  call    ?Provider@Reliability@Providers@TraceLog@@SAPEBU_tlgProvider_t@@XZ; TraceLog::Providers::Reliability::Provider(void)
0x180020949  mov     rdi, rax
0x18002094c  mov     ecx, [rax]
0x18002094e  cmp     ecx, 5
0x180020951  jbe     short loc_1800209B5
0x180020953  call    cs:__imp_GetCurrentThreadId
0x180020959  mov     dword ptr [rsp+0F8h+SRWLock], eax
0x180020960  mov     [rsp+0F8h+arg_10], ebp
0x180020967  mov     [rsp+0F8h+arg_18], 1000000h
0x180020973  mov     r8, [rbx+110h]
0x18002097a  add     r8, 8
0x18002097e  lea     rax, [rsp+0F8h+SRWLock]
0x180020986  mov     [rsp+0F8h+var_C8], rax
0x18002098b  lea     rax, [rsp+0F8h+arg_10]
0x180020993  mov     [rsp+0F8h+var_D0], rax
0x180020998  lea     rax, [rsp+0F8h+arg_18]
0x1800209a0  mov     [rsp+0F8h+var_D8], rax
0x1800209a5  lea     rdx, byte_18003D315
0x1800209ac  mov     rcx, rdi
0x1800209af  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800209b4  nop
0x1800209b5  cmp     dword ptr [rbx+138h], 0
0x1800209bc  jz      short loc_180020A20
0x1800209be  add     rbx, 120h
0x1800209c5  call    cs:__imp_GetCurrentThreadId
0x1800209cb  cmp     [rbx+18h], eax
0x1800209ce  jz      short loc_1800209F0
0x1800209d0  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800209d7  test    rax, rax
0x1800209da  jz      short loc_1800209F0
0x1800209dc  mov     rdx, [rsp+0F8h]
0x1800209e4  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800209eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209f0  mov     dword ptr [rbx+18h], 0
0x1800209f7  mov     rcx, [rbx]
0x1800209fa  jmp     short loc_180020A08
0x1800209fc  cmp     rax, rbx
0x1800209ff  jz      short loc_180020A12
0x180020a01  lea     rcx, [rax+10h]
0x180020a05  mov     [rbx], rcx
0x180020a08  mov     rax, [rcx]
0x180020a0b  test    rax, rax
0x180020a0e  jnz     short loc_1800209FC
0x180020a10  jmp     short loc_180020A19
0x180020a12  mov     rax, [rbx+10h]
0x180020a16  mov     [rcx], rax
0x180020a19  mov     qword ptr [rbx], 0
0x180020a20  mov     rbx, [rsp+0F8h+arg_8]
0x180020a28  add     rsp, 0E0h
0x180020a2f  pop     rdi
0x180020a30  pop     rsi
0x180020a31  pop     rbp
0x180020a32  retn
0x180020a33  xor     edx, edx; Val
0x180020a35  mov     r8d, 98h; Size
0x180020a3b  lea     rcx, [rsp+0F8h+var_B8]; void *
0x180020a40  call    memset_0
0x180020a45  lea     rcx, [rsp+0F8h+var_B8]; this
0x180020a4a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
