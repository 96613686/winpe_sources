# wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18002aa80`
- end: `0x18002abfe`
- name: `?Stop@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `382`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002980c`

## callees

- `0x1800029d8`
- `0x1800042f4`
- `0x18000bcd0`
- `0x180028738`
- `0x18002939c`
- `0x180029b74`
- `0x18002aa80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aae0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab7b`

## string_xrefs

- `0x18002ab9a`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        DWORD a2)
{
  __int64 v3; // rax
  int v4; // esi
  int v5; // edi
  int v6; // esi
  const struct _tlgProvider_t *result; // rax
  int v8; // edi
  __int64 v9; // r9
  __int64 v10; // rbx
  const struct _tlgProvider_t **v11; // rcx
  const struct wil::FailureInfo *v12; // rdx
  _BYTE v13[184]; // [rsp+50h] [rbp-B8h] BYREF
  void *retaddr; // [rsp+108h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+110h] [rbp+8h] BYREF
  DWORD CurrentThreadId; // [rsp+118h] [rbp+10h] BYREF
  __int64 v17; // [rsp+120h] [rbp+18h] BYREF

  CurrentThreadId = a2;
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
    result = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    v8 = (int)result;
    if ( *(_DWORD *)result > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(SRWLock) = 0;
      v17 = 0x1000000;
      result = (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                                                v8,
                                                (int)word_18004350A,
                                                (unsigned int)*(_QWORD *)(a1 + 272) + 8,
                                                v9,
                                                (__int64)&v17,
                                                (__int64)&SRWLock,
                                                (__int64)&CurrentThreadId);
    }
  }
  else
  {
    result = (const struct _tlgProvider_t *)wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                                              (_QWORD *)a1,
                                              v5);
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
0x18002aa80  mov     rax, rsp
0x18002aa83  mov     [rax+10h], edx
0x18002aa86  push    rbx
0x18002aa87  push    rsi
0x18002aa88  push    rdi
0x18002aa89  sub     rsp, 0F0h
0x18002aa90  mov     [rsp+108h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18002aa99  mov     rbx, rcx
0x18002aa9c  lea     rdx, [rax+8]
0x18002aaa0  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002aaa5  mov     rax, [rbx+110h]
0x18002aaac  mov     esi, [rax+0F8h]
0x18002aab2  cmp     esi, 1
0x18002aab5  jl      loc_18002ABE1
0x18002aabb  mov     edi, [rax+48h]
0x18002aabe  test    edi, edi
0x18002aac0  js      short loc_18002AACB
0x18002aac2  mov     dword ptr [rax+48h], 0
0x18002aac9  xor     edi, edi
0x18002aacb  dec     esi
0x18002aacd  mov     [rax+0F8h], esi
0x18002aad3  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x18002aadb  test    rcx, rcx
0x18002aade  jz      short loc_18002AAE7
0x18002aae0  call    cs:__imp_ReleaseSRWLockExclusive
0x18002aae6  nop
0x18002aae7  test    esi, esi
0x18002aae9  jnz     short loc_18002AAF7
0x18002aaeb  mov     edx, edi
0x18002aaed  mov     rcx, rbx
0x18002aaf0  call    ?ReportStopActivity@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18002aaf5  jmp     short loc_18002AB6B
0x18002aaf7  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002aafc  mov     rdi, rax
0x18002aaff  mov     ecx, [rax]
0x18002ab01  cmp     ecx, 5
0x18002ab04  jbe     short loc_18002AB6B
0x18002ab06  call    cs:__imp_GetCurrentThreadId
0x18002ab0c  mov     [rsp+108h+arg_8], eax
0x18002ab13  mov     dword ptr [rsp+108h+SRWLock], 0
0x18002ab1e  mov     [rsp+108h+arg_10], 1000000h
0x18002ab2a  mov     r8, [rbx+110h]
0x18002ab31  add     r8, 8
0x18002ab35  lea     rax, [rsp+108h+arg_8]
0x18002ab3d  mov     [rsp+108h+var_D8], rax
0x18002ab42  lea     rax, [rsp+108h+SRWLock]
0x18002ab4a  mov     [rsp+108h+var_E0], rax
0x18002ab4f  lea     rax, [rsp+108h+arg_10]
0x18002ab57  mov     [rsp+108h+var_E8], rax
0x18002ab5c  lea     rdx, word_18004350A
0x18002ab63  mov     rcx, rdi
0x18002ab66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002ab6b  cmp     dword ptr [rbx+138h], 0
0x18002ab72  jz      short loc_18002ABD6
0x18002ab74  add     rbx, 120h
0x18002ab7b  call    cs:__imp_GetCurrentThreadId
0x18002ab81  cmp     [rbx+18h], eax
0x18002ab84  jz      short loc_18002ABA6
0x18002ab86  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x18002ab8d  test    rax, rax
0x18002ab90  jz      short loc_18002ABA6
0x18002ab92  mov     rdx, [rsp+108h]
0x18002ab9a  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18002aba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aba6  mov     dword ptr [rbx+18h], 0
0x18002abad  mov     rcx, [rbx]
0x18002abb0  jmp     short loc_18002ABBE
0x18002abb2  cmp     rax, rbx
0x18002abb5  jz      short loc_18002ABC8
0x18002abb7  lea     rcx, [rax+10h]
0x18002abbb  mov     [rbx], rcx
0x18002abbe  mov     rax, [rcx]
0x18002abc1  test    rax, rax
0x18002abc4  jnz     short loc_18002ABB2
0x18002abc6  jmp     short loc_18002ABCF
0x18002abc8  mov     rax, [rbx+10h]
0x18002abcc  mov     [rcx], rax
0x18002abcf  mov     qword ptr [rbx], 0
0x18002abd6  add     rsp, 0F0h
0x18002abdd  pop     rdi
0x18002abde  pop     rsi
0x18002abdf  pop     rbx
0x18002abe0  retn
0x18002abe1  xor     edx, edx; Val
0x18002abe3  mov     r8d, 98h; Size
0x18002abe9  lea     rcx, [rsp+108h+var_B8]; void *
0x18002abee  call    memset_0
0x18002abf3  lea     rcx, [rsp+108h+var_B8]; this
0x18002abf8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
