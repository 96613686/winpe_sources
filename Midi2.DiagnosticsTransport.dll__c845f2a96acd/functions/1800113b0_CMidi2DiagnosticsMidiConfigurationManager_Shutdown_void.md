# CMidi2DiagnosticsMidiConfigurationManager::Shutdown(void)

- ea: `0x1800113b0`
- end: `0x180011421`
- name: `?Shutdown@CMidi2DiagnosticsMidiConfigurationManager@@UEAAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(CMidi2DiagnosticsMidiConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800016dc`
- `0x18000add8`
- `0x1800113b0`
- `0x180013010`

## string_xrefs

- `0x1800113ce`: `CMidi2DiagnosticsMidiConfigurationManager::Shutdown`

## pseudocode

```c
__int64 __fastcall CMidi2DiagnosticsMidiConfigurationManager::Shutdown(CMidi2DiagnosticsMidiConfigurationManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rcx
  CMidi2DiagnosticsMidiConfigurationManager *v7; // [rsp+40h] [rbp+8h] BYREF
  const char *v8; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiDiagnosticsTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v7 = this;
    v8 = "CMidi2DiagnosticsMidiConfigurationManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)&dword_180016E84,
      v3,
      v4,
      (__int64)&v8,
      (__int64)&v7);
  }
  v5 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x1800113b0  push    rbx
0x1800113b2  sub     rsp, 30h
0x1800113b6  mov     rbx, rcx
0x1800113b9  call    ?Instance@MidiDiagnosticsTransportTelemetryProvider@@KAPEAV1@XZ; MidiDiagnosticsTransportTelemetryProvider::Instance(void)
0x1800113be  mov     rcx, [rax+8]
0x1800113c2  mov     eax, [rcx]
0x1800113c4  cmp     eax, 4
0x1800113c7  jbe     short loc_1800113FB
0x1800113c9  mov     [rsp+38h+arg_0], rbx
0x1800113ce  lea     rax, aCmidi2diagnost_7; "CMidi2DiagnosticsMidiConfigurationManag"...
0x1800113d5  mov     [rsp+38h+arg_8], rax
0x1800113da  lea     rax, [rsp+38h+arg_0]
0x1800113df  mov     [rsp+38h+var_10], rax
0x1800113e4  lea     rax, [rsp+38h+arg_8]
0x1800113e9  mov     [rsp+38h+var_18], rax
0x1800113ee  lea     rdx, dword_180016E84
0x1800113f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800113fa  nop
0x1800113fb  mov     rcx, [rbx+10h]
0x1800113ff  mov     qword ptr [rbx+10h], 0
0x180011407  test    rcx, rcx
0x18001140a  jz      short loc_180011419
0x18001140c  mov     rax, [rcx]
0x18001140f  mov     rax, [rax+10h]
0x180011413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011418  nop
0x180011419  xor     eax, eax
0x18001141b  add     rsp, 30h
0x18001141f  pop     rbx
0x180011420  retn
```
