# CMidi2DiagnosticsMidiConfigurationManager::UpdateConfiguration(ushort const *,ushort * *)

- ea: `0x180011430`
- end: `0x180011485`
- name: `?UpdateConfiguration@CMidi2DiagnosticsMidiConfigurationManager@@UEAAJPEBGPEAPEAG@Z`
- size: `85`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsMidiConfigurationManager *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x1800016dc`
- `0x18000add8`
- `0x180011430`

## string_xrefs

- `0x180011449`: `CMidi2DiagnosticsMidiConfigurationManager::UpdateConfiguration`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsMidiConfigurationManager::UpdateConfiguration(
        CMidi2DiagnosticsMidiConfigurationManager *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  const char *v8; // [rsp+30h] [rbp-18h] BYREF
  CMidi2DiagnosticsMidiConfigurationManager *v9; // [rsp+68h] [rbp+20h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v9 = this;
    v8 = "CMidi2DiagnosticsMidiConfigurationManager::UpdateConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (unsigned int)byte_180016EAD,
      v5,
      v6,
      (__int64)&v8,
      (__int64)&v9);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180011430  push    rbx
0x180011432  sub     rsp, 40h
0x180011436  mov     rbx, rcx
0x180011439  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x18001143e  mov     rcx, [rax+8]
0x180011442  mov     eax, [rcx]
0x180011444  cmp     eax, 4
0x180011447  jbe     short loc_18001147A
0x180011449  lea     rax, aCmidi2diagnost_2; "CMidi2DiagnosticsMidiConfigurationManag"...
0x180011450  mov     [rsp+48h+arg_18], rbx
0x180011455  mov     [rsp+48h+var_18], rax
0x18001145a  lea     rdx, byte_180016EAD
0x180011461  lea     rax, [rsp+48h+arg_18]
0x180011466  mov     [rsp+48h+var_20], rax
0x18001146b  lea     rax, [rsp+48h+var_18]
0x180011470  mov     [rsp+48h+var_28], rax
0x180011475  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001147a  mov     eax, 80004001h
0x18001147f  add     rsp, 40h
0x180011483  pop     rbx
0x180011484  retn
```
