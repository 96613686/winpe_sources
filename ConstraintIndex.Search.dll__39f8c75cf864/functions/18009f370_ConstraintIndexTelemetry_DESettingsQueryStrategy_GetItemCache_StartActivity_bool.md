# ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::StartActivity(bool)

- ea: `0x18009f370`
- end: `0x18009f440`
- name: `?StartActivity@DESettingsQueryStrategy_GetItemCache@ConstraintIndexTelemetry@@QEAAX_N@Z`
- size: `208`
- prototype: `void __fastcall(ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18009e800`

## callees

- `0x18000243c`
- `0x180003198`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x1800925ec`
- `0x180093fa0`
- `0x18009f370`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f3ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009f3ca`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache::StartActivity(
        ConstraintIndexTelemetry::DESettingsQueryStrategy_GetItemCache *this,
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
0x18009f370  mov     [rsp+arg_18], rbx
0x18009f375  mov     byte ptr [rsp+arg_8], dl
0x18009f379  push    rdi
0x18009f37a  sub     rsp, 40h
0x18009f37e  mov     rbx, rcx
0x18009f381  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18009f386  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18009f38b  mov     rdi, rax
0x18009f38e  mov     edx, [rax]
0x18009f390  cmp     edx, 5
0x18009f393  jbe     loc_18009F42E
0x18009f399  mov     edx, 1
0x18009f39e  mov     rcx, rax
0x18009f3a1  call    _tlgKeywordOn
0x18009f3a6  test    al, al
0x18009f3a8  jz      loc_18009F42E
0x18009f3ae  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x18009f3b5  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x18009f3ba  xor     edx, edx; length
0x18009f3bc  mov     rcx, [rax+18h]; string
0x18009f3c0  call    WindowsGetStringRawBuffer_0
0x18009f3c5  mov     [rsp+48h+arg_0], rax
0x18009f3ca  call    cs:__imp_GetCurrentThreadId
0x18009f3d0  mov     r8, [rbx+110h]
0x18009f3d7  mov     dword ptr [rsp+48h+arg_8], eax
0x18009f3db  mov     [rsp+48h+arg_10], 0
0x18009f3e4  cmp     byte ptr [r8+4], 0
0x18009f3e9  jz      short loc_18009F3F8
0x18009f3eb  lea     rcx, [r8+18h]; struct _GUID *
0x18009f3ef  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18009f3f4  test    al, al
0x18009f3f6  jz      short loc_18009F3FA
0x18009f3f8  xor     ecx, ecx
0x18009f3fa  lea     rax, [rsp+48h+arg_0]
0x18009f3ff  mov     r9, rcx
0x18009f402  mov     [rsp+48h+var_18], rax; __int64
0x18009f407  lea     rdx, byte_1801133E3
0x18009f40e  lea     rax, [rsp+48h+arg_8]
0x18009f413  add     r8, 8
0x18009f417  mov     [rsp+48h+var_20], rax; __int64
0x18009f41c  mov     rcx, rdi; int
0x18009f41f  lea     rax, [rsp+48h+arg_10]
0x18009f424  mov     [rsp+48h+var_28], rax; __int64
0x18009f429  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &)
0x18009f42e  mov     rcx, rbx
0x18009f431  mov     rbx, [rsp+48h+arg_18]
0x18009f436  add     rsp, 40h
0x18009f43a  pop     rdi
0x18009f43b  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
