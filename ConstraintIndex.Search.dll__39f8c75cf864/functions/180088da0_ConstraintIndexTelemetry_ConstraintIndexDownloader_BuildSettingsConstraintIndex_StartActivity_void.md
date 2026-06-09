# ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex::StartActivity(void)

- ea: `0x180088da0`
- end: `0x180088e40`
- name: `?StartActivity@ConstraintIndexDownloader_BuildSettingsConstraintIndex@ConstraintIndexTelemetry@@QEAAXXZ`
- size: `160`
- prototype: `void __fastcall(ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800866f0`

## callees

- `0x18000197c`
- `0x18000243c`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18004000c`
- `0x180088da0`
- `0x180093fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180088dd2`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex::StartActivity(
        ConstraintIndexTelemetry::ConstraintIndexDownloader_BuildSettingsConstraintIndex *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // edi
  __int64 v6; // r8
  int v7; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = CortanaSearchTelemetryLogging::Provider();
  v5 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 1, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)&word_180111C96,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&CurrentThreadId);
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180088da0  mov     [rsp+arg_10], rbx
0x180088da5  push    rdi
0x180088da6  sub     rsp, 30h
0x180088daa  mov     rbx, rcx
0x180088dad  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180088db2  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x180088db7  mov     rdi, rax
0x180088dba  mov     edx, [rax]
0x180088dbc  cmp     edx, 5
0x180088dbf  jbe     short loc_180088E2C
0x180088dc1  mov     edx, 1
0x180088dc6  mov     rcx, rax
0x180088dc9  call    _tlgKeywordOn
0x180088dce  test    al, al
0x180088dd0  jz      short loc_180088E2C
0x180088dd2  call    cs:__imp_GetCurrentThreadId
0x180088dd8  mov     [rsp+38h+arg_0], eax
0x180088ddc  mov     [rsp+38h+arg_8], 0
0x180088de5  mov     r8, [rbx+110h]
0x180088dec  cmp     byte ptr [r8+4], 0
0x180088df1  jz      short loc_180088E00
0x180088df3  lea     rcx, [r8+18h]; struct _GUID *
0x180088df7  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180088dfc  test    al, al
0x180088dfe  jz      short loc_180088E02
0x180088e00  xor     ecx, ecx
0x180088e02  add     r8, 8
0x180088e06  lea     rax, [rsp+38h+arg_0]
0x180088e0b  mov     [rsp+38h+var_10], rax
0x180088e10  lea     rax, [rsp+38h+arg_8]
0x180088e15  mov     [rsp+38h+var_18], rax
0x180088e1a  mov     r9, rcx
0x180088e1d  lea     rdx, word_180111C96
0x180088e24  mov     rcx, rdi
0x180088e27  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180088e2c  mov     rcx, rbx
0x180088e2f  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180088e34  nop
0x180088e35  mov     rbx, [rsp+38h+arg_10]
0x180088e3a  add     rsp, 30h
0x180088e3e  pop     rdi
0x180088e3f  retn
```
