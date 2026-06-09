# ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState::StartActivity(bool)

- ea: `0x1800c47b0`
- end: `0x1800c4880`
- name: `?StartActivity@SettingsFilterCacheManager_ComputeModernFilterState@ConstraintIndexTelemetry@@QEAAX_N@Z`
- size: `208`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bc7e0`

## callees

- `0x18000243c`
- `0x180003198`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x1800925ec`
- `0x180093fa0`
- `0x1800c47b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c480a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c480a`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState::StartActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState *this,
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
0x1800c47b0  mov     [rsp+arg_18], rbx
0x1800c47b5  mov     byte ptr [rsp+arg_8], dl
0x1800c47b9  push    rdi
0x1800c47ba  sub     rsp, 40h
0x1800c47be  mov     rbx, rcx
0x1800c47c1  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c47c6  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c47cb  mov     rdi, rax
0x1800c47ce  mov     edx, [rax]
0x1800c47d0  cmp     edx, 5
0x1800c47d3  jbe     loc_1800C486E
0x1800c47d9  mov     edx, 1
0x1800c47de  mov     rcx, rax
0x1800c47e1  call    _tlgKeywordOn
0x1800c47e6  test    al, al
0x1800c47e8  jz      loc_1800C486E
0x1800c47ee  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800c47f5  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800c47fa  xor     edx, edx; length
0x1800c47fc  mov     rcx, [rax+18h]; string
0x1800c4800  call    WindowsGetStringRawBuffer_0
0x1800c4805  mov     [rsp+48h+arg_0], rax
0x1800c480a  call    cs:__imp_GetCurrentThreadId
0x1800c4810  mov     r8, [rbx+110h]
0x1800c4817  mov     dword ptr [rsp+48h+arg_8], eax
0x1800c481b  mov     [rsp+48h+arg_10], 0
0x1800c4824  cmp     byte ptr [r8+4], 0
0x1800c4829  jz      short loc_1800C4838
0x1800c482b  lea     rcx, [r8+18h]; struct _GUID *
0x1800c482f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c4834  test    al, al
0x1800c4836  jz      short loc_1800C483A
0x1800c4838  xor     ecx, ecx
0x1800c483a  lea     rax, [rsp+48h+arg_0]
0x1800c483f  mov     r9, rcx
0x1800c4842  mov     [rsp+48h+var_18], rax; __int64
0x1800c4847  lea     rdx, byte_180113BF9
0x1800c484e  lea     rax, [rsp+48h+arg_8]
0x1800c4853  add     r8, 8
0x1800c4857  mov     [rsp+48h+var_20], rax; __int64
0x1800c485c  mov     rcx, rdi; int
0x1800c485f  lea     rax, [rsp+48h+arg_10]
0x1800c4864  mov     [rsp+48h+var_28], rax; __int64
0x1800c4869  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x1800c486e  mov     rcx, rbx
0x1800c4871  mov     rbx, [rsp+48h+arg_18]
0x1800c4876  add     rsp, 40h
0x1800c487a  pop     rdi
0x1800c487b  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
