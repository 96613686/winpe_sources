# ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StartActivity(uint,uint)

- ea: `0x1800c4888`
- end: `0x1800c498a`
- name: `?StartActivity@SettingsFilterCacheManager_FilterDeviceItems@ConstraintIndexTelemetry@@QEAAXII@Z`
- size: `258`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800c29e0`

## callees

- `0x18000243c`
- `0x180003698`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x1800925ec`
- `0x180093fa0`
- `0x1800c4888`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c48f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c48f5`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems::StartActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_FilterDeviceItems *this,
        int a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rax
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // [rsp+50h] [rbp-38h] BYREF
  __int64 StringRawBuffer_0; // [rsp+58h] [rbp-30h] BYREF
  __int64 v16[5]; // [rsp+60h] [rbp-28h] BYREF
  __int64 v17; // [rsp+90h] [rbp+8h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+20h] BYREF

  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = CortanaSearchTelemetryLogging::Provider();
  v8 = (int)v6;
  v9 = *(unsigned int *)v6;
  if ( (unsigned int)v9 > 5 && (unsigned __int8)tlgKeywordOn(v6, 1, v7, v9) )
  {
    LODWORD(v17) = a3;
    LODWORD(v18) = a2;
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
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (__int64)v16,
      (__int64)&v14,
      (__int64)&StringRawBuffer_0,
      (__int64)&v18,
      (__int64)&v17);
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x1800c4888  mov     [rsp+arg_8], rbx
0x1800c488d  push    rbp
0x1800c488e  push    rsi
0x1800c488f  push    rdi
0x1800c4890  sub     rsp, 70h
0x1800c4894  mov     esi, r8d
0x1800c4897  mov     ebp, edx
0x1800c4899  mov     rbx, rcx
0x1800c489c  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800c48a1  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c48a6  mov     rdi, rax
0x1800c48a9  mov     r9d, [rax]
0x1800c48ac  cmp     r9d, 5
0x1800c48b0  jbe     loc_1800C4973
0x1800c48b6  mov     edx, 1
0x1800c48bb  mov     rcx, rax
0x1800c48be  call    _tlgKeywordOn
0x1800c48c3  test    al, al
0x1800c48c5  jz      loc_1800C4973
0x1800c48cb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x1800c48d2  mov     dword ptr [rsp+88h+arg_0], esi
0x1800c48d9  mov     dword ptr [rsp+88h+arg_18], ebp
0x1800c48e0  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x1800c48e5  xor     edx, edx; length
0x1800c48e7  mov     rcx, [rax+18h]; string
0x1800c48eb  call    WindowsGetStringRawBuffer_0
0x1800c48f0  mov     [rsp+88h+var_30], rax
0x1800c48f5  call    cs:__imp_GetCurrentThreadId
0x1800c48fb  mov     r8, [rbx+110h]
0x1800c4902  mov     dword ptr [rsp+88h+var_38], eax
0x1800c4906  mov     [rsp+88h+var_28], 0
0x1800c490f  cmp     byte ptr [r8+4], 0
0x1800c4914  jz      short loc_1800C4923
0x1800c4916  lea     rcx, [r8+18h]; struct _GUID *
0x1800c491a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800c491f  test    al, al
0x1800c4921  jz      short loc_1800C4925
0x1800c4923  xor     ecx, ecx
0x1800c4925  lea     rax, [rsp+88h+arg_0]
0x1800c492d  mov     r9, rcx
0x1800c4930  mov     [rsp+88h+var_48], rax; __int64
0x1800c4935  lea     rdx, unk_180113CE8
0x1800c493c  lea     rax, [rsp+88h+arg_18]
0x1800c4944  add     r8, 8
0x1800c4948  mov     [rsp+88h+var_50], rax; __int64
0x1800c494d  mov     rcx, rdi; int
0x1800c4950  lea     rax, [rsp+88h+var_30]
0x1800c4955  mov     [rsp+88h+var_58], rax; __int64
0x1800c495a  lea     rax, [rsp+88h+var_38]
0x1800c495f  mov     [rsp+88h+var_60], rax; __int64
0x1800c4964  lea     rax, [rsp+88h+var_28]
0x1800c4969  mov     [rsp+88h+var_68], rax; __int64
0x1800c496e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c4973  mov     rcx, rbx
0x1800c4976  mov     rbx, [rsp+88h+arg_8]
0x1800c497e  add     rsp, 70h
0x1800c4982  pop     rdi
0x1800c4983  pop     rsi
0x1800c4984  pop     rbp
0x1800c4985  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
