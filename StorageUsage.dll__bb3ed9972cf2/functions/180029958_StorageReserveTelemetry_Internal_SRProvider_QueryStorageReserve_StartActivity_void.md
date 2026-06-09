# StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(void)

- ea: `0x180029958`
- end: `0x180029a32`
- name: `?StartActivity@QueryStorageReserve@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180026acc`

## callees

- `0x1800039e4`
- `0x18001f178`
- `0x180026f90`
- `0x180027bdc`
- `0x18002832c`
- `0x180029958`
- `0x180029a38`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002998d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002998d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800299bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800299bb`

## pseudocode

```c
void __fastcall StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  __int64 v6; // rcx
  RTL_SRWLOCK *v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v7);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StorageReserveTelemetry::Internal::StorageReserveProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  v3 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    LODWORD(v7) = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v3,
      (__int64)word_180038B2A,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *)((char *)this + 288));
}

```

## disassembly

```asm
0x180029958  mov     [rsp+arg_10], rbx
0x18002995d  push    rdi
0x18002995e  sub     rsp, 30h
0x180029962  lea     rdx, [rsp+38h+arg_0]
0x180029967  mov     rbx, rcx
0x18002996a  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002996f  mov     rdi, [rbx+110h]
0x180029976  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18002997b  mov     r8d, [rax]
0x18002997e  cmp     r8d, 5
0x180029982  jbe     short loc_180029995
0x180029984  lea     rdx, [rdi+8]; ActivityId
0x180029988  mov     ecx, 3; ControlCode
0x18002998d  call    cs:__imp_EventActivityIdControl
0x180029993  jmp     short loc_18002999C
0x180029995  xorps   xmm0, xmm0
0x180029998  movups  xmmword ptr [rdi+8], xmm0
0x18002999c  lea     rcx, [rsp+38h+arg_0]
0x1800299a1  mov     dword ptr [rdi], 1
0x1800299a7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800299ac  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x1800299b1  mov     rdi, rax
0x1800299b4  mov     ecx, [rax]
0x1800299b6  cmp     ecx, 5
0x1800299b9  jbe     short loc_180029A15
0x1800299bb  call    cs:__imp_GetCurrentThreadId
0x1800299c1  mov     r8, [rbx+110h]
0x1800299c8  mov     dword ptr [rsp+38h+arg_0], eax
0x1800299cc  mov     [rsp+38h+arg_8], 0
0x1800299d5  cmp     byte ptr [r8+4], 0
0x1800299da  jz      short loc_1800299E9
0x1800299dc  lea     rcx, [r8+18h]; struct _GUID *
0x1800299e0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800299e5  test    al, al
0x1800299e7  jz      short loc_1800299EB
0x1800299e9  xor     ecx, ecx
0x1800299eb  lea     rax, [rsp+38h+arg_0]
0x1800299f0  mov     r9, rcx
0x1800299f3  mov     [rsp+38h+var_10], rax
0x1800299f8  lea     rdx, word_180038B2A
0x1800299ff  lea     rax, [rsp+38h+arg_8]
0x180029a04  add     r8, 8
0x180029a08  mov     rcx, rdi
0x180029a0b  mov     [rsp+38h+var_18], rax
0x180029a10  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180029a15  lea     rcx, [rbx+120h]; this
0x180029a1c  cmp     dword ptr [rcx+18h], 0
0x180029a20  jnz     short loc_180029A27
0x180029a22  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180029a27  mov     rbx, [rsp+38h+arg_10]
0x180029a2c  add     rsp, 30h
0x180029a30  pop     rdi
0x180029a31  retn
```
