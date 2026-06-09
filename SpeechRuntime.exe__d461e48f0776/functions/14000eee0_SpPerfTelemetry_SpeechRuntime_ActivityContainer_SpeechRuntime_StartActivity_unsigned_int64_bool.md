# SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::StartActivity(unsigned __int64,bool)

- ea: `0x14000eee0`
- end: `0x14000f07c`
- name: `?StartActivity@SpeechRuntime@ActivityContainer@1SpPerfTelemetry@@QEAAX_K_N@Z`
- size: `412`
- prototype: `void __fastcall(SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *__hidden this, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000f090`

## callees

- `0x140001058`
- `0x140001ffc`
- `0x140002d30`
- `0x140007fa8`
- `0x14000c848`
- `0x14000d3cc`
- `0x14000eee0`
- `0x14000f590`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ef4e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000ef4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000efa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000efa1`

## pseudocode

```c
void __fastcall SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime::StartActivity(
        SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *this,
        __int64 a2,
        char a3)
{
  __int64 v6; // rbx
  const struct _tlgProvider_t *v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  const GUID *v13; // r9
  char v14; // [rsp+30h] [rbp-49h] BYREF
  DWORD v15; // [rsp+38h] [rbp-41h] BYREF
  __int64 v16; // [rsp+40h] [rbp-39h] BYREF
  __int64 v17; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v19; // [rsp+70h] [rbp-9h]
  __int64 v20; // [rsp+78h] [rbp-1h]
  DWORD *v21; // [rsp+80h] [rbp+7h]
  __int64 v22; // [rsp+88h] [rbp+Fh]
  __int64 *v23; // [rsp+90h] [rbp+17h]
  __int64 v24; // [rsp+98h] [rbp+1Fh]
  char *v25; // [rsp+A0h] [rbp+27h]
  __int64 v26; // [rsp+A8h] [rbp+2Fh]

  wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v15);
  v6 = *((_QWORD *)this + 34);
  v7 = FlightDataRecorderActivityClass::Provider();
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  else
    *(_OWORD *)(v6 + 8) = 0;
  *(_DWORD *)v6 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v8 = FlightDataRecorderActivityClass::Provider();
  v10 = (__int64)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
  {
    v14 = a3;
    v16 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v12 = *((_QWORD *)this + 34);
    v15 = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v12 + 4)
      || (v13 = (const GUID *)(v12 + 24), !*(_DWORD *)(v12 + 24))
      && !*(_DWORD *)(v12 + 28)
      && !*(_DWORD *)(v12 + 32)
      && !*(_DWORD *)(v12 + 36) )
    {
      v13 = 0;
    }
    v26 = 1;
    v25 = &v14;
    v24 = 8;
    v23 = &v16;
    v22 = 4;
    v21 = &v15;
    v20 = 8;
    v19 = &v17;
    tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)byte_140042FEB, (const GUID *)(v12 + 8), v13, 6u, &v18);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (SpPerfTelemetry::SpeechRuntime::ActivityContainer::SpeechRuntime *)((char *)this + 288),
      v9);
}

```

## disassembly

```asm
0x14000eee0  mov     [rsp-8+arg_8], rbx
0x14000eee5  mov     [rsp-8+arg_10], rsi
0x14000eeea  push    rbp
0x14000eeeb  push    rdi
0x14000eeec  push    r14
0x14000eeee  lea     rbp, [rsp-47h]
0x14000eef3  sub     rsp, 0C0h
0x14000eefa  mov     rax, cs:__security_cookie
0x14000ef01  xor     rax, rsp
0x14000ef04  mov     [rbp+57h+var_20], rax
0x14000ef08  mov     r14, rdx
0x14000ef0b  mov     sil, r8b
0x14000ef0e  lea     rdx, [rbp+57h+var_98]
0x14000ef12  mov     rdi, rcx
0x14000ef15  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000ef1a  mov     rbx, [rdi+110h]
0x14000ef21  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000ef26  mov     r9d, [rax]
0x14000ef29  cmp     r9d, 5
0x14000ef2d  jbe     short loc_14000EF56
0x14000ef2f  mov     rdx, 400000000000h
0x14000ef39  mov     rcx, rax
0x14000ef3c  call    _tlgKeywordOn
0x14000ef41  test    al, al
0x14000ef43  jz      short loc_14000EF56
0x14000ef45  lea     rdx, [rbx+8]; ActivityId
0x14000ef49  mov     ecx, 3; ControlCode
0x14000ef4e  call    cs:__imp_EventActivityIdControl
0x14000ef54  jmp     short loc_14000EF5D
0x14000ef56  xorps   xmm0, xmm0
0x14000ef59  movups  xmmword ptr [rbx+8], xmm0
0x14000ef5d  lea     rcx, [rbp+57h+var_98]
0x14000ef61  mov     dword ptr [rbx], 1
0x14000ef67  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000ef6c  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14000ef71  mov     rbx, rax
0x14000ef74  mov     ecx, [rax]
0x14000ef76  cmp     ecx, 5
0x14000ef79  jbe     loc_14000F046
0x14000ef7f  mov     rdx, 400000000000h
0x14000ef89  mov     rcx, rax
0x14000ef8c  call    _tlgKeywordOn
0x14000ef91  test    al, al
0x14000ef93  jz      loc_14000F046
0x14000ef99  mov     [rbp+57h+var_A0], sil
0x14000ef9d  mov     [rbp+57h+var_90], r14
0x14000efa1  call    cs:__imp_GetCurrentThreadId
0x14000efa7  mov     r8, [rdi+110h]
0x14000efae  mov     [rbp+57h+var_98], eax
0x14000efb1  mov     [rbp+57h+var_88], 0
0x14000efb9  cmp     byte ptr [r8+4], 0
0x14000efbe  jz      short loc_14000EFDF
0x14000efc0  lea     r9, [r8+18h]
0x14000efc4  cmp     dword ptr [r9], 0
0x14000efc8  jnz     short loc_14000EFE2
0x14000efca  cmp     dword ptr [r9+4], 0
0x14000efcf  jnz     short loc_14000EFE2
0x14000efd1  cmp     dword ptr [r9+8], 0
0x14000efd6  jnz     short loc_14000EFE2
0x14000efd8  cmp     dword ptr [r9+0Ch], 0
0x14000efdd  jnz     short loc_14000EFE2
0x14000efdf  xor     r9d, r9d
0x14000efe2  lea     rax, [rbp+57h+var_A0]
0x14000efe6  mov     [rbp+57h+var_28], 1
0x14000efee  mov     [rbp+57h+var_30], rax
0x14000eff2  lea     rdx, byte_140042FEB
0x14000eff9  lea     rax, [rbp+57h+var_90]
0x14000effd  mov     [rbp+57h+var_38], 8
0x14000f005  mov     [rbp+57h+var_40], rax
0x14000f009  add     r8, 8
0x14000f00d  lea     rax, [rbp+57h+var_98]
0x14000f011  mov     [rbp+57h+var_48], 4
0x14000f019  mov     [rbp+57h+var_50], rax
0x14000f01d  mov     rcx, rbx
0x14000f020  lea     rax, [rbp+57h+var_88]
0x14000f024  mov     [rbp+57h+var_58], 8
0x14000f02c  mov     [rbp+57h+var_60], rax
0x14000f030  lea     rax, [rbp+57h+var_80]
0x14000f034  mov     [rsp+0D0h+var_A8], rax
0x14000f039  mov     [rsp+0D0h+var_B0], 6
0x14000f041  call    _tlgWriteTransfer_EventWriteTransfer
0x14000f046  lea     rcx, [rdi+120h]; this
0x14000f04d  cmp     dword ptr [rcx+18h], 0
0x14000f051  jnz     short loc_14000F058
0x14000f053  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14000f058  mov     rcx, [rbp+57h+var_20]
0x14000f05c  xor     rcx, rsp; StackCookie
0x14000f05f  call    __security_check_cookie
0x14000f064  lea     r11, [rsp+0D0h+var_10]
0x14000f06c  mov     rbx, [r11+28h]
0x14000f070  mov     rsi, [r11+30h]
0x14000f074  mov     rsp, r11
0x14000f077  pop     r14
0x14000f079  pop     rdi
0x14000f07a  pop     rbp
0x14000f07b  retn
```
