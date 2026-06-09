# ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StartActivity(Platform::String *)

- ea: `0x1800989ec`
- end: `0x180098ae2`
- name: `?StartActivity@ConstraintIndexManager_GetEntitiesJSONInMemory@ConstraintIndexTelemetry@@QEAAXPE$AAVString@Platform@@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180096a68`

## callees

- `0x18000243c`
- `0x18000284c`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x1800925ec`
- `0x1800989ec`
- `0x18009a380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098a5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098a5f`

## pseudocode

```c
__int64 __fastcall ConstraintIndexTelemetry::ConstraintIndexManager_GetEntitiesJSONInMemory::StartActivity(
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

  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v4 = CortanaSearchTelemetryLogging::Provider();
  v6 = (int)v4;
  v7 = *(unsigned int *)v4;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v7, v5) )
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
      (int)&word_180112BE6,
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
0x1800989ec  push    rbx
0x1800989ee  push    rsi
0x1800989ef  push    rdi
0x1800989f0  sub     rsp, 50h
0x1800989f4  mov     rsi, rdx
0x1800989f7  mov     rbx, rcx
0x1800989fa  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800989ff  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180098a04  mov     rdi, rax
0x180098a07  mov     r8d, [rax]
0x180098a0a  cmp     r8d, 5
0x180098a0e  jbe     loc_180098AD3
0x180098a14  mov     rdx, 200000000000h
0x180098a1e  mov     rcx, rax
0x180098a21  call    _tlgKeywordOn
0x180098a26  test    al, al
0x180098a28  jz      loc_180098AD3
0x180098a2e  xor     edx, edx; length
0x180098a30  mov     rcx, rsi; string
0x180098a33  call    WindowsGetStringRawBuffer_0
0x180098a38  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_3f32e471ee4016ff12f12bcbf8a58c4e_@@CA@XZ; _lambda_3f32e471ee4016ff12f12bcbf8a58c4e_::_lambda_invoker_cdecl_(void)
0x180098a3f  mov     [rsp+68h+arg_10], rax
0x180098a47  call    ?get@?$static_lazy@VConstraintIndexTelemetry@@@details@wil@@QEAAPEAVConstraintIndexTelemetry@@P6AXXZ@Z; wil::details::static_lazy<ConstraintIndexTelemetry>::get(void (*)(void))
0x180098a4c  xor     edx, edx; length
0x180098a4e  mov     rcx, [rax+18h]; string
0x180098a52  call    WindowsGetStringRawBuffer_0
0x180098a57  mov     [rsp+68h+arg_18], rax
0x180098a5f  call    cs:__imp_GetCurrentThreadId
0x180098a65  mov     r8, [rbx+110h]
0x180098a6c  mov     dword ptr [rsp+68h+arg_0], eax
0x180098a70  mov     [rsp+68h+var_28], 0
0x180098a79  cmp     byte ptr [r8+4], 0
0x180098a7e  jz      short loc_180098A8D
0x180098a80  lea     rcx, [r8+18h]; struct _GUID *
0x180098a84  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180098a89  test    al, al
0x180098a8b  jz      short loc_180098A8F
0x180098a8d  xor     ecx, ecx
0x180098a8f  lea     rax, [rsp+68h+arg_10]
0x180098a97  mov     r9, rcx
0x180098a9a  mov     [rsp+68h+var_30], rax; __int64
0x180098a9f  lea     rdx, word_180112BE6; int
0x180098aa6  lea     rax, [rsp+68h+arg_18]
0x180098aae  add     r8, 8; int
0x180098ab2  mov     [rsp+68h+var_38], rax; __int64
0x180098ab7  mov     rcx, rdi; int
0x180098aba  lea     rax, [rsp+68h+arg_0]
0x180098abf  mov     [rsp+68h+var_40], rax; __int64
0x180098ac4  lea     rax, [rsp+68h+var_28]
0x180098ac9  mov     [rsp+68h+var_48], rax; __int64
0x180098ace  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180098ad3  mov     rcx, rbx
0x180098ad6  add     rsp, 50h
0x180098ada  pop     rdi
0x180098adb  pop     rsi
0x180098adc  pop     rbx
0x180098add  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
