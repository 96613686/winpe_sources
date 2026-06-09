# CMidi2KSMidiConfigurationManager::Shutdown(void)

- ea: `0x180023850`
- end: `0x180023929`
- name: `?Shutdown@CMidi2KSMidiConfigurationManager@@UEAAJXZ`
- size: `217`
- prototype: `__int64 __fastcall(CMidi2KSMidiConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001918`
- `0x18000cdcc`
- `0x18000db18`
- `0x180023850`
- `0x180041010`

## string_xrefs

- `0x180023872`: `CMidi2KSMidiConfigurationManager::Shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSMidiConfigurationManager::Shutdown(CMidi2KSMidiConfigurationManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  struct TransportState *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  CMidi2KSMidiConfigurationManager *v11; // [rsp+40h] [rbp+8h] BYREF
  const char *v12; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiKSTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v11 = this;
    v12 = "CMidi2KSMidiConfigurationManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)word_180068C6A,
      v3,
      v4,
      (__int64)&v12,
      (__int64)&v11);
  }
  v5 = TransportState::Current();
  v6 = *(_QWORD *)v5;
  *(_QWORD *)v5 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)v5 + 1);
  *((_QWORD *)v5 + 1) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return 0;
}

```

## disassembly

```asm
0x180023850  mov     [rsp+arg_10], rbx
0x180023855  push    rdi
0x180023856  sub     rsp, 30h
0x18002385a  mov     rbx, rcx
0x18002385d  call    ?Instance@MidiKSTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSTransportTelemetryProvider::Instance(void)
0x180023862  mov     rcx, [rax+8]
0x180023866  mov     eax, [rcx]
0x180023868  cmp     eax, 4
0x18002386b  jbe     short loc_18002389E
0x18002386d  mov     [rsp+38h+arg_0], rbx
0x180023872  lea     rax, aCmidi2ksmidico_0; "CMidi2KSMidiConfigurationManager::Shutd"...
0x180023879  mov     [rsp+38h+arg_8], rax
0x18002387e  lea     rax, [rsp+38h+arg_0]
0x180023883  mov     [rsp+38h+var_10], rax
0x180023888  lea     rax, [rsp+38h+arg_8]
0x18002388d  mov     [rsp+38h+var_18], rax
0x180023892  lea     rdx, word_180068C6A
0x180023899  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18002389e  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x1800238a3  mov     rdi, rax
0x1800238a6  mov     rcx, [rax]
0x1800238a9  mov     qword ptr [rax], 0
0x1800238b0  test    rcx, rcx
0x1800238b3  jz      short loc_1800238C2
0x1800238b5  mov     rdx, [rcx]
0x1800238b8  mov     rax, [rdx+10h]
0x1800238bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238c1  nop
0x1800238c2  mov     rcx, [rdi+8]
0x1800238c6  mov     qword ptr [rdi+8], 0
0x1800238ce  test    rcx, rcx
0x1800238d1  jz      short loc_1800238E0
0x1800238d3  mov     rax, [rcx]
0x1800238d6  mov     rax, [rax+10h]
0x1800238da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238df  nop
0x1800238e0  mov     rcx, [rbx+20h]
0x1800238e4  mov     qword ptr [rbx+20h], 0
0x1800238ec  test    rcx, rcx
0x1800238ef  jz      short loc_1800238FE
0x1800238f1  mov     rax, [rcx]
0x1800238f4  mov     rax, [rax+10h]
0x1800238f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238fd  nop
0x1800238fe  mov     rcx, [rbx+28h]
0x180023902  mov     qword ptr [rbx+28h], 0
0x18002390a  test    rcx, rcx
0x18002390d  jz      short loc_18002391C
0x18002390f  mov     rax, [rcx]
0x180023912  mov     rax, [rax+10h]
0x180023916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002391b  nop
0x18002391c  xor     eax, eax
0x18002391e  mov     rbx, [rsp+38h+arg_10]
0x180023923  add     rsp, 30h
0x180023927  pop     rdi
0x180023928  retn
```
