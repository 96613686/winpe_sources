# Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StartActivity(Platform::String *,Platform::String *,int)

- ea: `0x18003d550`
- end: `0x18003d644`
- name: `?StartActivity@CSGSuggester_GetEntitiesAsJson@CSGSuggestionTelemetry@CSGSuggestion@ConstraintIndex@Cortana@@QEAAXPE$AAVString@Platform@@0H@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003e52c`

## callees

- `0x1800021d4`
- `0x18000619e`
- `0x18003b5d4`
- `0x18003c9b8`
- `0x18003d550`
- `0x18004000c`
- `0x180040b54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d5ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003d5ad`

## pseudocode

```c
__int64 __fastcall Cortana::ConstraintIndex::CSGSuggestion::CSGSuggestionTelemetry::CSGSuggester_GetEntitiesAsJson::StartActivity(
        __int64 a1,
        HSTRING a2,
        HSTRING a3,
        int a4)
{
  const struct _tlgProvider_t *v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 StringRawBuffer_0; // [rsp+58h] [rbp-30h] BYREF
  __int64 v15; // [rsp+60h] [rbp-28h] BYREF
  __int64 v16; // [rsp+68h] [rbp-20h] BYREF
  __int64 v17; // [rsp+90h] [rbp+8h] BYREF

  wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = CortanaSearchTelemetryLogging::Provider();
  v9 = (int)v8;
  if ( *(_DWORD *)v8 > 5u )
  {
    LODWORD(v17) = a4;
    StringRawBuffer_0 = (__int64)WindowsGetStringRawBuffer_0(a3, 0);
    v15 = (__int64)WindowsGetStringRawBuffer_0(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    LODWORD(v13) = CurrentThreadId;
    v16 = 0x2000000;
    if ( *(_BYTE *)(v11 + 4) )
      _tlgGuidIsZero((const struct _GUID *)(v11 + 24));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v9,
      (int)&unk_180111770,
      v11 + 8,
      (__int64)&v16,
      (__int64)&v13,
      (__int64)&v15,
      (__int64)&StringRawBuffer_0,
      (__int64)&v17);
  }
  return wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x18003d550  mov     [rsp+arg_8], rbx
0x18003d555  mov     [rsp+arg_10], rbp
0x18003d55a  push    rsi
0x18003d55b  push    rdi
0x18003d55c  push    r14
0x18003d55e  sub     rsp, 70h
0x18003d562  mov     esi, r9d
0x18003d565  mov     rbp, r8
0x18003d568  mov     r14, rdx
0x18003d56b  mov     rbx, rcx
0x18003d56e  call    ?zInternalStart@?$ActivityBase@VCortanaSearchTelemetryLogging@@$0A@$0A@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,0,0,5,33554432,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18003d573  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x18003d578  mov     rdi, rax
0x18003d57b  mov     r10d, [rax]
0x18003d57e  cmp     r10d, 5
0x18003d582  jbe     loc_18003D628
0x18003d588  xor     edx, edx; length
0x18003d58a  mov     dword ptr [rsp+88h+arg_0], esi
0x18003d591  mov     rcx, rbp; string
0x18003d594  call    WindowsGetStringRawBuffer_0
0x18003d599  xor     edx, edx; length
0x18003d59b  mov     [rsp+88h+var_30], rax
0x18003d5a0  mov     rcx, r14; string
0x18003d5a3  call    WindowsGetStringRawBuffer_0
0x18003d5a8  mov     [rsp+88h+var_28], rax
0x18003d5ad  call    cs:__imp_GetCurrentThreadId
0x18003d5b3  mov     r8, [rbx+110h]
0x18003d5ba  mov     dword ptr [rsp+88h+var_38], eax
0x18003d5be  mov     [rsp+88h+var_20], 2000000h
0x18003d5c7  cmp     byte ptr [r8+4], 0
0x18003d5cc  jz      short loc_18003D5DB
0x18003d5ce  lea     rcx, [r8+18h]; struct _GUID *
0x18003d5d2  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18003d5d7  test    al, al
0x18003d5d9  jz      short loc_18003D5DD
0x18003d5db  xor     ecx, ecx
0x18003d5dd  lea     rax, [rsp+88h+arg_0]
0x18003d5e5  mov     r9, rcx
0x18003d5e8  mov     [rsp+88h+var_48], rax; __int64
0x18003d5ed  lea     rdx, unk_180111770; int
0x18003d5f4  lea     rax, [rsp+88h+var_30]
0x18003d5f9  add     r8, 8; int
0x18003d5fd  mov     [rsp+88h+var_50], rax; __int64
0x18003d602  mov     rcx, rdi; int
0x18003d605  lea     rax, [rsp+88h+var_28]
0x18003d60a  mov     [rsp+88h+var_58], rax; __int64
0x18003d60f  lea     rax, [rsp+88h+var_38]
0x18003d614  mov     [rsp+88h+var_60], rax; __int64
0x18003d619  lea     rax, [rsp+88h+var_20]
0x18003d61e  mov     [rsp+88h+var_68], rax; __int64
0x18003d623  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x18003d628  mov     rcx, rbx
0x18003d62b  lea     r11, [rsp+88h+var_18]
0x18003d630  mov     rbx, [r11+28h]
0x18003d634  mov     rbp, [r11+30h]
0x18003d638  mov     rsp, r11
0x18003d63b  pop     r14
0x18003d63d  pop     rdi
0x18003d63e  pop     rsi
0x18003d63f  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
