# FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::StartActivity(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800aa960`
- end: `0x1800aaad7`
- name: `?StartActivity@UpdateResourceProvisioningTrackingStatusTelemetry@FirstSyncStatusProvider@@QEAAXPEBG000@Z`
- size: `375`
- prototype: `void __fastcall(FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800a96bc`

## callees

- `0x180001350`
- `0x1800042e8`
- `0x18000dcbc`
- `0x18002eec4`
- `0x180035c88`
- `0x18003989c`
- `0x1800a0fd8`
- `0x1800aa960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aaa2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aaa2b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800aa9be`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800aa9be`

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
  int v12; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // ecx
  __int64 v16; // [rsp+60h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+68h] [rbp-9h] BYREF
  const unsigned __int16 *v18; // [rsp+70h] [rbp-1h] BYREF
  const unsigned __int16 *v19; // [rsp+78h] [rbp+7h] BYREF
  const unsigned __int16 *v20; // [rsp+80h] [rbp+Fh] BYREF
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
  v12 = (int)v11;
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
      (unsigned int)&dword_1800EDCD4,
      v14 + 8,
      v15,
      (__int64)v21,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v16);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800aa960  push    rbp
0x1800aa962  push    rbx
0x1800aa963  push    rsi
0x1800aa964  push    rdi
0x1800aa965  push    r14
0x1800aa967  push    r15
0x1800aa969  lea     rbp, [rsp-27h]
0x1800aa96e  sub     rsp, 98h
0x1800aa975  mov     r15, rdx
0x1800aa978  mov     rsi, r9
0x1800aa97b  lea     rdx, [rbp+4Fh+arg_0]
0x1800aa97f  mov     r14, r8
0x1800aa982  mov     rdi, rcx
0x1800aa985  call    ?LockExclusive@?$ActivityBase@VEnrollmentLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EnrollmentLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800aa98a  mov     rbx, [rdi+110h]
0x1800aa991  call    ?Provider@FirstSyncProvider@@SAPEBU_tlgProvider_t@@XZ; FirstSyncProvider::Provider(void)
0x1800aa996  mov     r10d, [rax]
0x1800aa999  cmp     r10d, 5
0x1800aa99d  jbe     short loc_1800AA9CC
0x1800aa99f  mov     rdx, 800000000000h
0x1800aa9a9  mov     rcx, rax
0x1800aa9ac  call    _tlgKeywordOn
0x1800aa9b1  test    al, al
0x1800aa9b3  jz      short loc_1800AA9CC
0x1800aa9b5  lea     rdx, [rbx+8]; ActivityId
0x1800aa9b9  mov     ecx, 3; ControlCode
0x1800aa9be  call    cs:__imp_EventActivityIdControl
0x1800aa9c5  nop     dword ptr [rax+rax+00h]
0x1800aa9ca  jmp     short loc_1800AA9D3
0x1800aa9cc  xorps   xmm0, xmm0
0x1800aa9cf  movups  xmmword ptr [rbx+8], xmm0
0x1800aa9d3  lea     rcx, [rbp+4Fh+arg_0]
0x1800aa9d7  mov     dword ptr [rbx], 1
0x1800aa9dd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800aa9e2  call    ?Provider@FirstSyncProvider@@SAPEBU_tlgProvider_t@@XZ; FirstSyncProvider::Provider(void)
0x1800aa9e7  mov     rbx, rax
0x1800aa9ea  mov     ecx, [rax]
0x1800aa9ec  cmp     ecx, 5
0x1800aa9ef  jbe     loc_1800AAAB4
0x1800aa9f5  mov     rdx, 800000000000h
0x1800aa9ff  mov     rcx, rax
0x1800aaa02  call    _tlgKeywordOn
0x1800aaa07  test    al, al
0x1800aaa09  jz      loc_1800AAAB4
0x1800aaa0f  mov     rax, [rbp+4Fh+arg_20]
0x1800aaa13  mov     [rbp+4Fh+var_50], rax
0x1800aaa17  mov     [rbp+4Fh+var_60], 2000000h
0x1800aaa1f  mov     [rbp+4Fh+var_58], r14
0x1800aaa23  mov     [rbp+4Fh+var_48], rsi
0x1800aaa27  mov     [rbp+4Fh+var_40], r15
0x1800aaa2b  call    cs:__imp_GetCurrentThreadId
0x1800aaa32  nop     dword ptr [rax+rax+00h]
0x1800aaa37  mov     r8, [rdi+110h]
0x1800aaa3e  mov     [rbp+4Fh+arg_0], eax
0x1800aaa41  mov     [rbp+4Fh+var_38], 0
0x1800aaa49  cmp     byte ptr [r8+4], 0
0x1800aaa4e  jz      short loc_1800AAA5D
0x1800aaa50  lea     rcx, [r8+18h]; struct _GUID *
0x1800aaa54  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800aaa59  test    al, al
0x1800aaa5b  jz      short loc_1800AAA5F
0x1800aaa5d  xor     ecx, ecx
0x1800aaa5f  lea     rax, [rbp+4Fh+var_60]
0x1800aaa63  mov     r9, rcx
0x1800aaa66  mov     [rsp+0C0h+var_70], rax
0x1800aaa6b  lea     rdx, dword_1800EDCD4
0x1800aaa72  lea     rax, [rbp+4Fh+var_58]
0x1800aaa76  add     r8, 8
0x1800aaa7a  mov     [rsp+0C0h+var_78], rax
0x1800aaa7f  mov     rcx, rbx
0x1800aaa82  lea     rax, [rbp+4Fh+var_50]
0x1800aaa86  mov     [rsp+0C0h+var_80], rax
0x1800aaa8b  lea     rax, [rbp+4Fh+var_48]
0x1800aaa8f  mov     [rsp+0C0h+var_88], rax
0x1800aaa94  lea     rax, [rbp+4Fh+var_40]
0x1800aaa98  mov     [rsp+0C0h+var_90], rax
0x1800aaa9d  lea     rax, [rbp+4Fh+arg_0]
0x1800aaaa1  mov     [rsp+0C0h+var_98], rax
0x1800aaaa6  lea     rax, [rbp+4Fh+var_38]
0x1800aaaaa  mov     [rsp+0C0h+var_A0], rax
0x1800aaaaf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5553@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800aaab4  lea     rcx, [rdi+120h]; this
0x1800aaabb  cmp     dword ptr [rcx+18h], 0
0x1800aaabf  jnz     short loc_1800AAAC6
0x1800aaac1  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800aaac6  add     rsp, 98h
0x1800aaacd  pop     r15
0x1800aaacf  pop     r14
0x1800aaad1  pop     rdi
0x1800aaad2  pop     rsi
0x1800aaad3  pop     rbx
0x1800aaad4  pop     rbp
0x1800aaad5  retn
```
