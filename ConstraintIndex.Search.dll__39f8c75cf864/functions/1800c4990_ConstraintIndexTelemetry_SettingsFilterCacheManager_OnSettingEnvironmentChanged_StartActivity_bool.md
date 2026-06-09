# ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::StartActivity(bool)

- ea: `0x1800c4990`
- end: `0x1800c4a60`
- name: `?StartActivity@SettingsFilterCacheManager_OnSettingEnvironmentChanged@ConstraintIndexTelemetry@@QEAAX_N@Z`
- size: `208`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c3d60`

## callees

- `0x18000243c`
- `0x180003198`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x1800925ec`
- `0x180093fa0`
- `0x1800c4990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c49ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c49ea`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged::StartActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_OnSettingEnvironmentChanged *this,
        char a2)
{
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rax
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 StringRawBuffer_0; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v12) = a2;
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v3 = CortanaSearchTelemetryLogging::Provider();
  v6 = (int)v3;
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 1, v4, v5) )
  {
    v8 = wil::details::static_lazy<ConstraintIndexTelemetry>::get(
           v7,
           _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_);
    StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(*(HSTRING *)(v8 + 24), 0);
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    LODWORD(v12) = CurrentThreadId;
    v13 = 0;
    if ( *(_BYTE *)(v10 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v10 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
      v6,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&StringRawBuffer_0);
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x1800c4990  mov     [rsp+arg_18], rbx
0x1800c4995  mov     byte ptr [rsp+arg_8], dl
0x1800c4999  push    rdi
0x1800c499a  sub     rsp, 40h
0x1800c499e  mov     rbx, rcx
0x1800c49a1  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c49a6  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c49ab  mov     rdi, rax
0x1800c49ae  mov     edx, [rax]
0x1800c49b0  cmp     edx, 5
0x1800c49b3  jbe     loc_1800C4A4E
0x1800c49b9  mov     edx, 1
0x1800c49be  mov     rcx, rax
0x1800c49c1  call    _tlgKeywordOn
0x1800c49c6  test    al, al
0x1800c49c8  jz      loc_1800C4A4E
0x1800c49ce  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800c49d5  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800c49da  xor     edx, edx; length
0x1800c49dc  mov     rcx, [rax+18h]; string
0x1800c49e0  call    WindowsGetStringRawBuffer_0
0x1800c49e5  mov     [rsp+48h+arg_0], rax
0x1800c49ea  call    cs:__imp_GetCurrentThreadId
0x1800c49f0  mov     r8, [rbx+110h]
0x1800c49f7  mov     dword ptr [rsp+48h+arg_8], eax
0x1800c49fb  mov     [rsp+48h+arg_10], 0
0x1800c4a04  cmp     byte ptr [r8+4], 0
0x1800c4a09  jz      short loc_1800C4A18
0x1800c4a0b  lea     rcx, [r8+18h]; struct _GUID *
0x1800c4a0f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c4a14  test    al, al
0x1800c4a16  jz      short loc_1800C4A1A
0x1800c4a18  xor     ecx, ecx
0x1800c4a1a  lea     rax, [rsp+48h+arg_0]
0x1800c4a1f  mov     r9, rcx
0x1800c4a22  mov     [rsp+48h+var_18], rax; __int64
0x1800c4a27  lea     rdx, byte_180113D79
0x1800c4a2e  lea     rax, [rsp+48h+arg_8]
0x1800c4a33  add     r8, 8
0x1800c4a37  mov     [rsp+48h+var_20], rax; __int64
0x1800c4a3c  mov     rcx, rdi; int
0x1800c4a3f  lea     rax, [rsp+48h+arg_10]
0x1800c4a44  mov     [rsp+48h+var_28], rax; __int64
0x1800c4a49  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800c4a4e  mov     rcx, rbx
0x1800c4a51  mov     rbx, [rsp+48h+arg_18]
0x1800c4a56  add     rsp, 40h
0x1800c4a5a  pop     rdi
0x1800c4a5b  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
