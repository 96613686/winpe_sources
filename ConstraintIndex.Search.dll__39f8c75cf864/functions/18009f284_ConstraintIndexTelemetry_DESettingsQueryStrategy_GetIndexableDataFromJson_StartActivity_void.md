# ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StartActivity(void)

- ea: `0x18009f284`
- end: `0x18009f368`
- name: `?StartActivity@DESettingsQueryStrategy_GetIndexableDataFromJson@ConstraintIndexTelemetry@@QEAAXXZ`
- size: `228`
- prototype: `void __fastcall(ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18009dfe0`

## callees

- `0x18000197c`
- `0x18003a900`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d6e4`
- `0x18004000c`
- `0x18009f284`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f2f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f2f0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009f2c2`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18009f2c2`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson::StartActivity(
        ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // r8
  int v6; // ecx
  __int64 v7; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+38h] [rbp-10h] BYREF

  v7 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v7);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)CortanaSearchTelemetryLogging::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  v3 = CortanaSearchTelemetryLogging::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(v7) = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_18011337B,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ConstraintIndexTelemetry::DESettingsQueryStrategy_GetIndexableDataFromJson *)((char *)this + 288));
}

```

## disassembly

```asm
0x18009f284  mov     [rsp+arg_8], rbx
0x18009f289  push    rdi
0x18009f28a  sub     rsp, 40h
0x18009f28e  mov     rbx, rcx
0x18009f291  mov     [rsp+48h+var_18], 0
0x18009f29a  lea     rdx, [rsp+48h+var_18]
0x18009f29f  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18009f2a4  mov     rdi, [rbx+110h]
0x18009f2ab  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f2b0  mov     r8d, [rax]
0x18009f2b3  cmp     r8d, 5
0x18009f2b7  jbe     short loc_18009F2CA
0x18009f2b9  lea     rdx, [rdi+8]; ActivityId
0x18009f2bd  mov     ecx, 3; ControlCode
0x18009f2c2  call    cs:__imp_EventActivityIdControl
0x18009f2c8  jmp     short loc_18009F2D1
0x18009f2ca  xorps   xmm0, xmm0
0x18009f2cd  movups  xmmword ptr [rdi+8], xmm0
0x18009f2d1  mov     dword ptr [rdi], 1
0x18009f2d7  lea     rcx, [rsp+48h+var_18]
0x18009f2dc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18009f2e1  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f2e6  mov     rdi, rax
0x18009f2e9  mov     ecx, [rax]
0x18009f2eb  cmp     ecx, 5
0x18009f2ee  jbe     short loc_18009F34A
0x18009f2f0  call    cs:__imp_GetCurrentThreadId
0x18009f2f6  mov     dword ptr [rsp+48h+var_18], eax
0x18009f2fa  mov     [rsp+48h+var_10], 0
0x18009f303  mov     r8, [rbx+110h]
0x18009f30a  cmp     byte ptr [r8+4], 0
0x18009f30f  jz      short loc_18009F31E
0x18009f311  lea     rcx, [r8+18h]; struct _GUID *
0x18009f315  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18009f31a  test    al, al
0x18009f31c  jz      short loc_18009F320
0x18009f31e  xor     ecx, ecx
0x18009f320  add     r8, 8
0x18009f324  lea     rax, [rsp+48h+var_18]
0x18009f329  mov     [rsp+48h+var_20], rax
0x18009f32e  lea     rax, [rsp+48h+var_10]
0x18009f333  mov     [rsp+48h+var_28], rax
0x18009f338  mov     r9, rcx
0x18009f33b  lea     rdx, byte_18011337B
0x18009f342  mov     rcx, rdi
0x18009f345  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18009f34a  lea     rcx, [rbx+120h]; this
0x18009f351  cmp     dword ptr [rcx+18h], 0
0x18009f355  jnz     short loc_18009F35D
0x18009f357  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18009f35c  nop
0x18009f35d  mov     rbx, [rsp+48h+arg_8]
0x18009f362  add     rsp, 40h
0x18009f366  pop     rdi
0x18009f367  retn
```
