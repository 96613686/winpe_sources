# LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::StartActivity(ushort const *,uint,bool)

- ea: `0x14003fb48`
- end: `0x14003fc84`
- name: `?StartActivity@LanguagePackInstallationRequest@LanguagePackInstallSettingsTelemetryProvider@@QEAAXPEBGI_N@Z`
- size: `316`
- prototype: `void __fastcall(LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *__hidden this, const unsigned __int16 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x140040c30`

## callees

- `0x140001fcc`
- `0x14000215c`
- `0x14000ed94`
- `0x14001a814`
- `0x140025c6c`
- `0x14002ad8c`
- `0x14003f37c`
- `0x14003fb48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fbf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003fbf4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003fba1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14003fba1`

## pseudocode

```c
void __fastcall LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::StartActivity(
        LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *this,
        const unsigned __int16 *a2,
        int a3,
        char a4)
{
  __int64 v8; // rbx
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // rcx
  int v19; // [rsp+50h] [rbp-28h] BYREF
  DWORD v20; // [rsp+54h] [rbp-24h] BYREF
  const WCHAR *v21; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v22[3]; // [rsp+60h] [rbp-18h] BYREF
  RTL_SRWLOCK *v23; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v23);
  v8 = *((_QWORD *)this + 34);
  v9 = LanguagePackSettingsLogging::Provider();
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10, v11) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
  v12 = LanguagePackSettingsLogging::Provider();
  v15 = (__int64)v12;
  if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13, v14) )
  {
    LOBYTE(v23) = a4;
    v19 = a3;
    v21 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v17 = *((_QWORD *)this + 34);
    v20 = CurrentThreadId;
    v22[0] = 0;
    if ( !*(_BYTE *)(v17 + 4) || _tlgGuidIsZero((const struct _GUID *)(v17 + 24)) )
      v18 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
      v15,
      (__int64)byte_1400962E3,
      v17 + 8,
      v18,
      (__int64)v22,
      (__int64)&v20,
      &v21,
      (__int64)&v19,
      (__int64)&v23);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *)((char *)this + 288));
}

```

## disassembly

```asm
0x14003fb48  push    rbp
0x14003fb4a  push    rbx
0x14003fb4b  push    rsi
0x14003fb4c  push    rdi
0x14003fb4d  push    r14
0x14003fb4f  push    r15
0x14003fb51  mov     rbp, rsp
0x14003fb54  sub     rsp, 78h
0x14003fb58  mov     r15, rdx
0x14003fb5b  mov     sil, r9b
0x14003fb5e  lea     rdx, [rbp+arg_0]
0x14003fb62  mov     r14d, r8d
0x14003fb65  mov     rdi, rcx
0x14003fb68  call    ?LockExclusive@?$ActivityBase@VSettingsAdminFlowLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SettingsAdminFlowLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14003fb6d  mov     rbx, [rdi+110h]
0x14003fb74  call    ?Provider@LanguagePackSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; LanguagePackSettingsLogging::Provider(void)
0x14003fb79  mov     r10d, [rax]
0x14003fb7c  cmp     r10d, 5
0x14003fb80  jbe     short loc_14003FBA9
0x14003fb82  mov     rdx, 400000000000h
0x14003fb8c  mov     rcx, rax
0x14003fb8f  call    _tlgKeywordOn
0x14003fb94  test    al, al
0x14003fb96  jz      short loc_14003FBA9
0x14003fb98  lea     rdx, [rbx+8]; ActivityId
0x14003fb9c  mov     ecx, 3; ControlCode
0x14003fba1  call    cs:__imp_EventActivityIdControl
0x14003fba7  jmp     short loc_14003FBB0
0x14003fba9  xorps   xmm0, xmm0
0x14003fbac  movups  xmmword ptr [rbx+8], xmm0
0x14003fbb0  lea     rcx, [rbp+arg_0]
0x14003fbb4  mov     dword ptr [rbx], 1
0x14003fbba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14003fbbf  call    ?Provider@LanguagePackSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; LanguagePackSettingsLogging::Provider(void)
0x14003fbc4  mov     rbx, rax
0x14003fbc7  mov     ecx, [rax]
0x14003fbc9  cmp     ecx, 5
0x14003fbcc  jbe     loc_14003FC65
0x14003fbd2  mov     rdx, 400000000000h
0x14003fbdc  mov     rcx, rax
0x14003fbdf  call    _tlgKeywordOn
0x14003fbe4  test    al, al
0x14003fbe6  jz      short loc_14003FC65
0x14003fbe8  mov     byte ptr [rbp+arg_0], sil
0x14003fbec  mov     [rbp+var_28], r14d
0x14003fbf0  mov     [rbp+var_20], r15
0x14003fbf4  call    cs:__imp_GetCurrentThreadId
0x14003fbfa  mov     r8, [rdi+110h]
0x14003fc01  mov     [rbp+var_24], eax
0x14003fc04  mov     [rbp+var_18], 0
0x14003fc0c  cmp     byte ptr [r8+4], 0
0x14003fc11  jz      short loc_14003FC20
0x14003fc13  lea     rcx, [r8+18h]; struct _GUID *
0x14003fc17  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x14003fc1c  test    al, al
0x14003fc1e  jz      short loc_14003FC22
0x14003fc20  xor     ecx, ecx
0x14003fc22  lea     rax, [rbp+arg_0]
0x14003fc26  mov     r9, rcx
0x14003fc29  mov     [rsp+78h+var_38], rax
0x14003fc2e  lea     rdx, byte_1400962E3
0x14003fc35  lea     rax, [rbp+var_28]
0x14003fc39  add     r8, 8
0x14003fc3d  mov     [rsp+78h+var_40], rax
0x14003fc42  mov     rcx, rbx
0x14003fc45  lea     rax, [rbp+var_20]
0x14003fc49  mov     [rsp+78h+var_48], rax
0x14003fc4e  lea     rax, [rbp+var_24]
0x14003fc52  mov     [rsp+78h+var_50], rax
0x14003fc57  lea     rax, [rbp+var_18]
0x14003fc5b  mov     [rsp+78h+var_58], rax
0x14003fc60  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14003fc65  lea     rcx, [rdi+120h]; this
0x14003fc6c  cmp     dword ptr [rcx+18h], 0
0x14003fc70  jnz     short loc_14003FC77
0x14003fc72  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x14003fc77  add     rsp, 78h
0x14003fc7b  pop     r15
0x14003fc7d  pop     r14
0x14003fc7f  pop     rdi
0x14003fc80  pop     rsi
0x14003fc81  pop     rbx
0x14003fc82  pop     rbp
0x14003fc83  retn
```
