# ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::StartActivity(bool)

- ea: `0x1800cf5a4`
- end: `0x1800cf6df`
- name: `?StartActivity@SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync@ConstraintIndexTelemetry@@QEAAX_N@Z`
- size: `315`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *__hidden this, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800cfa90`

## callees

- `0x18000243c`
- `0x180003198`
- `0x18000619e`
- `0x18003a900`
- `0x18003c234`
- `0x18003c9b8`
- `0x18003d6e4`
- `0x18004000c`
- `0x1800925ec`
- `0x1800cf5a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf65e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cf65e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800cf5f6`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800cf5f6`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync::StartActivity(
        ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF
  __int64 StringRawBuffer_0; // [rsp+48h] [rbp-20h] BYREF
  __int64 v16[3]; // [rsp+50h] [rbp-18h] BYREF

  v14 = 0;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v14);
  v2 = *((_QWORD *)this + 34);
  v3 = CortanaSearchTelemetryLogging::Provider();
  if ( *(_DWORD *)v3 > 4u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  v6 = CortanaSearchTelemetryLogging::Provider();
  v9 = (int)v6;
  if ( *(_DWORD *)v6 > 4u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v8) )
  {
    v11 = wil::details::static_lazy<ConstraintIndexTelemetry>::get(
            v10,
            _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_);
    StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(*(HSTRING *)(v11 + 24), 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v14) = CurrentThreadId;
    v16[0] = 0;
    if ( *(_BYTE *)(v13 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v13 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v9,
      (__int64)v16,
      (__int64)&v14,
      (__int64)&StringRawBuffer_0);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((ConstraintIndexTelemetry::SettingsJsonGenerator_UpdateSettingsCacheOnDiskAsync *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800cf5a4  mov     [rsp+arg_8], rbx
0x1800cf5a9  push    rdi
0x1800cf5aa  sub     rsp, 60h
0x1800cf5ae  lea     rdx, [rsp+68h+var_28]
0x1800cf5b3  mov     [rsp+68h+var_28], 0
0x1800cf5bc  mov     rdi, rcx
0x1800cf5bf  call    ?LockExclusive@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800cf5c4  mov     rbx, [rdi+110h]
0x1800cf5cb  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800cf5d0  mov     edx, [rax]
0x1800cf5d2  cmp     edx, 4
0x1800cf5d5  jbe     short loc_1800CF5FE
0x1800cf5d7  mov     rdx, 400000000000h
0x1800cf5e1  mov     rcx, rax
0x1800cf5e4  call    _tlgKeywordOn
0x1800cf5e9  test    al, al
0x1800cf5eb  jz      short loc_1800CF5FE
0x1800cf5ed  lea     rdx, [rbx+8]; ActivityId
0x1800cf5f1  mov     ecx, 3; ControlCode
0x1800cf5f6  call    cs:__imp_EventActivityIdControl
0x1800cf5fc  jmp     short loc_1800CF605
0x1800cf5fe  xorps   xmm0, xmm0
0x1800cf601  movups  xmmword ptr [rbx+8], xmm0
0x1800cf605  lea     rcx, [rsp+68h+var_28]
0x1800cf60a  mov     dword ptr [rbx], 1
0x1800cf610  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cf615  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800cf61a  mov     rbx, rax
0x1800cf61d  mov     ecx, [rax]
0x1800cf61f  cmp     ecx, 4
0x1800cf622  jbe     loc_1800CF6C2
0x1800cf628  mov     rdx, 400000000000h
0x1800cf632  mov     rcx, rax
0x1800cf635  call    _tlgKeywordOn
0x1800cf63a  test    al, al
0x1800cf63c  jz      loc_1800CF6C2
0x1800cf642  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800cf649  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800cf64e  xor     edx, edx; length
0x1800cf650  mov     rcx, [rax+18h]; string
0x1800cf654  call    WindowsGetStringRawBuffer_0
0x1800cf659  mov     [rsp+68h+var_20], rax
0x1800cf65e  call    cs:__imp_GetCurrentThreadId
0x1800cf664  mov     r8, [rdi+110h]
0x1800cf66b  mov     dword ptr [rsp+68h+var_28], eax
0x1800cf66f  mov     [rsp+68h+var_18], 0
0x1800cf678  cmp     byte ptr [r8+4], 0
0x1800cf67d  jz      short loc_1800CF68C
0x1800cf67f  lea     rcx, [r8+18h]; struct _GUID *
0x1800cf683  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800cf688  test    al, al
0x1800cf68a  jz      short loc_1800CF68E
0x1800cf68c  xor     ecx, ecx
0x1800cf68e  lea     rax, [rsp+68h+var_20]
0x1800cf693  mov     r9, rcx
0x1800cf696  mov     [rsp+68h+var_38], rax; __int64
0x1800cf69b  lea     rdx, dword_18011496C
0x1800cf6a2  lea     rax, [rsp+68h+var_28]
0x1800cf6a7  add     r8, 8
0x1800cf6ab  mov     [rsp+68h+var_40], rax; __int64
0x1800cf6b0  mov     rcx, rbx; int
0x1800cf6b3  lea     rax, [rsp+68h+var_18]
0x1800cf6b8  mov     [rsp+68h+var_48], rax; __int64
0x1800cf6bd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800cf6c2  lea     rcx, [rdi+120h]; this
0x1800cf6c9  cmp     dword ptr [rcx+18h], 0
0x1800cf6cd  jnz     short loc_1800CF6D4
0x1800cf6cf  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800cf6d4  mov     rbx, [rsp+68h+arg_8]
0x1800cf6d9  add     rsp, 60h
0x1800cf6dd  pop     rdi
0x1800cf6de  retn
```
