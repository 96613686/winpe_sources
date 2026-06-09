# CMidi2DiagnosticsMidiConfigurationManager::Initialize(_GUID,IMidiDeviceManager *,IMidiServiceConfigurationManager *)

- ea: `0x1800112d0`
- end: `0x1800113a6`
- name: `?Initialize@CMidi2DiagnosticsMidiConfigurationManager@@UEAAJU_GUID@@PEAUIMidiDeviceManager@@PEAUIMidiServiceConfigurationManager@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsMidiConfigurationManager *__hidden this, struct _GUID *__struct_ptr, struct IMidiDeviceManager *, struct IMidiServiceConfigurationManager *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800016dc`
- `0x180008f64`
- `0x18000add8`
- `0x1800112d0`
- `0x180013010`

## string_xrefs

- `0x1800112fa`: `CMidi2DiagnosticsMidiConfigurationManager::Initialize`
- `0x180011335`: `avcore\midi2\transport\diagnosticstransport\midi2.diagnosticsmidiconfigurationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2DiagnosticsMidiConfigurationManager::Initialize(
        CMidi2DiagnosticsMidiConfigurationManager *this,
        struct _GUID *a2,
        __int64 (__fastcall ***a3)(struct IMidiDeviceManager *, GUID *, char *),
        struct IMidiServiceConfigurationManager *a4)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  __int64 v10; // rdx
  __int64 (__fastcall *v12)(struct IMidiDeviceManager *, GUID *, char *); // rsi
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  int v15[2]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2DiagnosticsMidiConfigurationManager *v17; // [rsp+60h] [rbp+18h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v17 = this;
    *(_QWORD *)v15 = "CMidi2DiagnosticsMidiConfigurationManager::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)&word_180016ED6,
      v7,
      v8,
      (__int64)v15,
      (__int64)&v17);
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    v10 = 33;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\transport\\diagnosticstransport\\midi2.diagnosticsmidiconfigurationmanager.cpp",
      (const char *)(unsigned int)v9,
      v14);
    return (unsigned int)v9;
  }
  v12 = **a3;
  v13 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v9 = v12((struct IMidiDeviceManager *)a3, &GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f, (char *)this + 16);
  if ( v9 < 0 )
  {
    v10 = 34;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800112d0  mov     [rsp+arg_0], rbx
0x1800112d5  mov     [rsp+arg_8], rsi
0x1800112da  push    rdi
0x1800112db  sub     rsp, 40h
0x1800112df  mov     rbx, r8
0x1800112e2  mov     rdi, rcx
0x1800112e5  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x1800112ea  mov     rcx, [rax+8]
0x1800112ee  mov     eax, [rcx]
0x1800112f0  cmp     eax, 4
0x1800112f3  jbe     short loc_180011326
0x1800112f5  mov     [rsp+48h+arg_10], rdi
0x1800112fa  lea     rax, aCmidi2diagnost_0; "CMidi2DiagnosticsMidiConfigurationManag"...
0x180011301  mov     qword ptr [rsp+48h+var_18], rax
0x180011306  lea     rax, [rsp+48h+arg_10]
0x18001130b  mov     [rsp+48h+var_20], rax
0x180011310  lea     rax, [rsp+48h+var_18]
0x180011315  mov     qword ptr [rsp+48h+var_28], rax; int
0x18001131a  lea     rdx, word_180016ED6
0x180011321  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180011326  test    rbx, rbx
0x180011329  jnz     short loc_18001134D
0x18001132b  mov     ebx, 80070057h
0x180011330  mov     edx, 21h ; '!'; void *
0x180011335  lea     r8, aAvcoreMidi2Tra_2; "avcore\\midi2\\transport\\diagnosticstr"...
0x18001133c  mov     r9d, ebx; char *
0x18001133f  mov     rcx, [rsp+48h]; this
0x180011344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011349  mov     eax, ebx
0x18001134b  jmp     short loc_180011396
0x18001134d  mov     rax, [rbx]
0x180011350  mov     rsi, [rax]
0x180011353  mov     rcx, [rdi+10h]
0x180011357  mov     qword ptr [rdi+10h], 0
0x18001135f  test    rcx, rcx
0x180011362  jz      short loc_180011371
0x180011364  mov     rdx, [rcx]
0x180011367  mov     rax, [rdx+10h]
0x18001136b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011370  nop
0x180011371  lea     r8, [rdi+10h]
0x180011375  lea     rdx, _GUID_a04374d3_4514_44e1_a2f9_7d8b907aef1f
0x18001137c  mov     rcx, rbx
0x18001137f  mov     rax, rsi
0x180011382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011387  mov     ebx, eax
0x180011389  test    eax, eax
0x18001138b  jns     short loc_180011394
0x18001138d  mov     edx, 22h ; '"'
0x180011392  jmp     short loc_180011335
0x180011394  xor     eax, eax
0x180011396  mov     rbx, [rsp+48h+arg_0]
0x18001139b  mov     rsi, [rsp+48h+arg_8]
0x1800113a0  add     rsp, 40h
0x1800113a4  pop     rdi
0x1800113a5  retn
```
