# FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::StartActivity(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800a74bc`
- end: `0x1800a7626`
- name: `?StartActivity@UpdateResourceProvisioningTrackingStatusTelemetry@FirstSyncStatusProvider@@QEAAXPEBG000@Z`
- size: `362`
- prototype: `void __fastcall(FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800a6278`

## callees

- `0x18000133c`
- `0x1800041d8`
- `0x18000d7bc`
- `0x180030254`
- `0x18003697c`
- `0x18003a57c`
- `0x18009e014`
- `0x1800a74bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7581`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a7581`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a751a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800a751a`

## pseudocode

```c
void __fastcall FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::StartActivity(
        FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // [rsp+60h] [rbp-11h] BYREF
  const WCHAR *v17; // [rsp+68h] [rbp-9h] BYREF
  const WCHAR *v18; // [rsp+70h] [rbp-1h] BYREF
  const WCHAR *v19; // [rsp+78h] [rbp+7h] BYREF
  const WCHAR *v20; // [rsp+80h] [rbp+Fh] BYREF
  _QWORD v21[7]; // [rsp+88h] [rbp+17h] BYREF
  DWORD v22; // [rsp+D0h] [rbp+5Fh] BYREF

  wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v22);
  v9 = *((_QWORD *)this + 34);
  v10 = FirstSyncProvider::Provider();
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x800000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v9 + 8));
  else
    *(_OWORD *)(v9 + 8) = 0;
  *(_DWORD *)v9 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  v11 = FirstSyncProvider::Provider();
  v12 = (__int64)v11;
  if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x800000000000LL) )
  {
    v18 = a5;
    v16 = 0x2000000;
    v17 = a3;
    v19 = a4;
    v20 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v14 = *((_QWORD *)this + 34);
    v22 = CurrentThreadId;
    v21[0] = 0;
    if ( !*(_BYTE *)(v14 + 4) || _tlgGuidIsZero((const struct _GUID *)(v14 + 24)) )
      v15 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v12,
      (__int64)&dword_1800E9EF4,
      v14 + 8,
      v15,
      (__int64)v21,
      (__int64)&v22,
      &v20,
      &v19,
      &v18,
      &v17,
      (__int64)&v16);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800a74bc  push    rbp
0x1800a74be  push    rbx
0x1800a74bf  push    rsi
0x1800a74c0  push    rdi
0x1800a74c1  push    r14
0x1800a74c3  push    r15
0x1800a74c5  lea     rbp, [rsp-27h]
0x1800a74ca  sub     rsp, 98h
0x1800a74d1  mov     r15, rdx
0x1800a74d4  mov     rsi, r9
0x1800a74d7  lea     rdx, [rbp+4Fh+arg_0]
0x1800a74db  mov     r14, r8
0x1800a74de  mov     rdi, rcx
0x1800a74e1  call    ?LockExclusive@?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800a74e6  mov     rbx, [rdi+110h]
0x1800a74ed  call    ?Provider@FirstSyncProvider@@SAPEBU_tlgProvider_t@@XZ; FirstSyncProvider::Provider(void)
0x1800a74f2  mov     r10d, [rax]
0x1800a74f5  cmp     r10d, 5
0x1800a74f9  jbe     short loc_1800A7522
0x1800a74fb  mov     rdx, 800000000000h
0x1800a7505  mov     rcx, rax
0x1800a7508  call    _tlgKeywordOn
0x1800a750d  test    al, al
0x1800a750f  jz      short loc_1800A7522
0x1800a7511  lea     rdx, [rbx+8]; ActivityId
0x1800a7515  mov     ecx, 3; ControlCode
0x1800a751a  call    cs:__imp_EventActivityIdControl
0x1800a7520  jmp     short loc_1800A7529
0x1800a7522  xorps   xmm0, xmm0
0x1800a7525  movups  xmmword ptr [rbx+8], xmm0
0x1800a7529  lea     rcx, [rbp+4Fh+arg_0]
0x1800a752d  mov     dword ptr [rbx], 1
0x1800a7533  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800a7538  call    ?Provider@FirstSyncProvider@@SAPEBU_tlgProvider_t@@XZ; FirstSyncProvider::Provider(void)
0x1800a753d  mov     rbx, rax
0x1800a7540  mov     ecx, [rax]
0x1800a7542  cmp     ecx, 5
0x1800a7545  jbe     loc_1800A7604
0x1800a754b  mov     rdx, 800000000000h
0x1800a7555  mov     rcx, rax
0x1800a7558  call    _tlgKeywordOn
0x1800a755d  test    al, al
0x1800a755f  jz      loc_1800A7604
0x1800a7565  mov     rax, [rbp+4Fh+arg_20]
0x1800a7569  mov     [rbp+4Fh+var_50], rax
0x1800a756d  mov     [rbp+4Fh+var_60], 2000000h
0x1800a7575  mov     [rbp+4Fh+var_58], r14
0x1800a7579  mov     [rbp+4Fh+var_48], rsi
0x1800a757d  mov     [rbp+4Fh+var_40], r15
0x1800a7581  call    cs:__imp_GetCurrentThreadId
0x1800a7587  mov     r8, [rdi+110h]
0x1800a758e  mov     [rbp+4Fh+arg_0], eax
0x1800a7591  mov     [rbp+4Fh+var_38], 0
0x1800a7599  cmp     byte ptr [r8+4], 0
0x1800a759e  jz      short loc_1800A75AD
0x1800a75a0  lea     rcx, [r8+18h]; struct _GUID *
0x1800a75a4  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800a75a9  test    al, al
0x1800a75ab  jz      short loc_1800A75AF
0x1800a75ad  xor     ecx, ecx
0x1800a75af  lea     rax, [rbp+4Fh+var_60]
0x1800a75b3  mov     r9, rcx
0x1800a75b6  mov     [rsp+0C0h+var_70], rax
0x1800a75bb  lea     rdx, dword_1800E9EF4
0x1800a75c2  lea     rax, [rbp+4Fh+var_58]
0x1800a75c6  add     r8, 8
0x1800a75ca  mov     [rsp+0C0h+var_78], rax
0x1800a75cf  mov     rcx, rbx
0x1800a75d2  lea     rax, [rbp+4Fh+var_50]
0x1800a75d6  mov     [rsp+0C0h+var_80], rax
0x1800a75db  lea     rax, [rbp+4Fh+var_48]
0x1800a75df  mov     [rsp+0C0h+var_88], rax
0x1800a75e4  lea     rax, [rbp+4Fh+var_40]
0x1800a75e8  mov     [rsp+0C0h+var_90], rax
0x1800a75ed  lea     rax, [rbp+4Fh+arg_0]
0x1800a75f1  mov     [rsp+0C0h+var_98], rax
0x1800a75f6  lea     rax, [rbp+4Fh+var_38]
0x1800a75fa  mov     [rsp+0C0h+var_A0], rax
0x1800a75ff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5553@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800a7604  lea     rcx, [rdi+120h]; this
0x1800a760b  cmp     dword ptr [rcx+18h], 0
0x1800a760f  jnz     short loc_1800A7616
0x1800a7611  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800a7616  add     rsp, 98h
0x1800a761d  pop     r15
0x1800a761f  pop     r14
0x1800a7621  pop     rdi
0x1800a7622  pop     rsi
0x1800a7623  pop     rbx
0x1800a7624  pop     rbp
0x1800a7625  retn
```
