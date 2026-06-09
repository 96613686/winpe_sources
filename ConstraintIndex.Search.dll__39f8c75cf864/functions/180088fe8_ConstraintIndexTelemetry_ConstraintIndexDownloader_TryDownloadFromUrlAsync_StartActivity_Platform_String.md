# ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::StartActivity(Platform::String *)

- ea: `0x180088fe8`
- end: `0x1800890d9`
- name: `?StartActivity@ConstraintIndexDownloader_TryDownloadFromUrlAsync@ConstraintIndexTelemetry@@QEAAXPE$AAVString@Platform@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180089e10`

## callees

- `0x18000243c`
- `0x18000284c`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x180088fe8`
- `0x1800925ec`
- `0x180093fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180089056`

## pseudocode

```c
__int64 __fastcall ConstraintIndexTelemetry::ConstraintIndexDownloader_TryDownloadFromUrlAsync::StartActivity(
        __int64 a1,
        HSTRING a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  int v6; // edi
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rax
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v13[5]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF
  __int64 StringRawBuffer_0; // [rsp+80h] [rbp+18h] BYREF
  __int64 v16; // [rsp+88h] [rbp+20h] BYREF

  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = CortanaSearchTelemetryLogging::Provider();
  v6 = (int)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 1, v7, v5) )
  {
    StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(a2, 0);
    v9 = wil::details::static_lazy<ConstraintIndexTelemetry>::get(
           v8,
           _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_);
    v16 = (__int64)WindowsGetStringRawBuffer_0(*(HSTRING *)(v9 + 24), 0);
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    LODWORD(v14) = CurrentThreadId;
    v13[0] = 0;
    if ( *(_BYTE *)(v11 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v11 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v6,
      (int)&byte_180111D75,
      v11 + 8,
      (__int64)v13,
      (__int64)&v14,
      (__int64)&v16,
      (__int64)&StringRawBuffer_0);
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x180088fe8  push    rbx
0x180088fea  push    rsi
0x180088feb  push    rdi
0x180088fec  sub     rsp, 50h
0x180088ff0  mov     rsi, rdx
0x180088ff3  mov     rbx, rcx
0x180088ff6  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180088ffb  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180089000  mov     rdi, rax
0x180089003  mov     r8d, [rax]
0x180089006  cmp     r8d, 5
0x18008900a  jbe     loc_1800890CA
0x180089010  mov     edx, 1
0x180089015  mov     rcx, rax
0x180089018  call    _tlgKeywordOn
0x18008901d  test    al, al
0x18008901f  jz      loc_1800890CA
0x180089025  xor     edx, edx; length
0x180089027  mov     rcx, rsi; string
0x18008902a  call    WindowsGetStringRawBuffer_0
0x18008902f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x180089036  mov     [rsp+68h+arg_10], rax
0x18008903e  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x180089043  xor     edx, edx; length
0x180089045  mov     rcx, [rax+18h]; string
0x180089049  call    WindowsGetStringRawBuffer_0
0x18008904e  mov     [rsp+68h+arg_18], rax
0x180089056  call    cs:__imp_GetCurrentThreadId
0x18008905c  mov     r8, [rbx+110h]
0x180089063  mov     dword ptr [rsp+68h+arg_0], eax
0x180089067  mov     [rsp+68h+var_28], 0
0x180089070  cmp     byte ptr [r8+4], 0
0x180089075  jz      short loc_180089084
0x180089077  lea     rcx, [r8+18h]; struct _GUID *
0x18008907b  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180089080  test    al, al
0x180089082  jz      short loc_180089086
0x180089084  xor     ecx, ecx
0x180089086  lea     rax, [rsp+68h+arg_10]
0x18008908e  mov     r9, rcx
0x180089091  mov     [rsp+68h+var_30], rax; __int64
0x180089096  lea     rdx, byte_180111D75; int
0x18008909d  lea     rax, [rsp+68h+arg_18]
0x1800890a5  add     r8, 8; int
0x1800890a9  mov     [rsp+68h+var_38], rax; __int64
0x1800890ae  mov     rcx, rdi; int
0x1800890b1  lea     rax, [rsp+68h+arg_0]
0x1800890b6  mov     [rsp+68h+var_40], rax; __int64
0x1800890bb  lea     rax, [rsp+68h+var_28]
0x1800890c0  mov     [rsp+68h+var_48], rax; __int64
0x1800890c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1800890ca  mov     rcx, rbx
0x1800890cd  add     rsp, 50h
0x1800890d1  pop     rdi
0x1800890d2  pop     rsi
0x1800890d3  pop     rbx
0x1800890d4  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
