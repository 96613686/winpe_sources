# CMidi2VirtualMidiConfigurationManager::Shutdown(void)

- ea: `0x18001d430`
- end: `0x18001d4ed`
- name: `?Shutdown@CMidi2VirtualMidiConfigurationManager@@UEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(CMidi2VirtualMidiConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800017d0`
- `0x18000b5f8`
- `0x18001adc4`
- `0x18001d430`
- `0x180021010`

## string_xrefs

- `0x18001d452`: `CMidi2VirtualMidiConfigurationManager::Shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2VirtualMidiConfigurationManager::Shutdown(CMidi2VirtualMidiConfigurationManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  struct TransportState *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  CMidi2VirtualMidiConfigurationManager *v10; // [rsp+40h] [rbp+8h] BYREF
  const char *v11; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiVirtualMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v10 = this;
    v11 = "CMidi2VirtualMidiConfigurationManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)byte_180027309,
      v3,
      v4,
      (__int64)&v11,
      (__int64)&v10);
  }
  v5 = TransportState::Current();
  v6 = *((_QWORD *)v5 + 2);
  *((_QWORD *)v5 + 2) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)v5 + 3);
  *((_QWORD *)v5 + 3) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x18001d430  mov     [rsp+arg_10], rbx
0x18001d435  push    rdi
0x18001d436  sub     rsp, 30h
0x18001d43a  mov     rdi, rcx
0x18001d43d  call    ?Instance@MidiVirtualMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiVirtualMidiTransportTelemetryProvider::Instance(void)
0x18001d442  mov     rcx, [rax+8]
0x18001d446  mov     eax, [rcx]
0x18001d448  cmp     eax, 4
0x18001d44b  jbe     short loc_18001D47E
0x18001d44d  mov     [rsp+38h+arg_0], rdi
0x18001d452  lea     rax, aCmidi2virtualm_11; "CMidi2VirtualMidiConfigurationManager::"...
0x18001d459  mov     [rsp+38h+arg_8], rax
0x18001d45e  lea     rax, [rsp+38h+arg_0]
0x18001d463  mov     [rsp+38h+var_10], rax
0x18001d468  lea     rax, [rsp+38h+arg_8]
0x18001d46d  mov     [rsp+38h+var_18], rax
0x18001d472  lea     rdx, byte_180027309
0x18001d479  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001d47e  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x18001d483  mov     rbx, rax
0x18001d486  mov     rcx, [rax+10h]
0x18001d48a  mov     qword ptr [rax+10h], 0
0x18001d492  test    rcx, rcx
0x18001d495  jz      short loc_18001D4A4
0x18001d497  mov     rdx, [rcx]
0x18001d49a  mov     rax, [rdx+10h]
0x18001d49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4a3  nop
0x18001d4a4  mov     rcx, [rbx+18h]
0x18001d4a8  mov     qword ptr [rbx+18h], 0
0x18001d4b0  test    rcx, rcx
0x18001d4b3  jz      short loc_18001D4C2
0x18001d4b5  mov     rax, [rcx]
0x18001d4b8  mov     rax, [rax+10h]
0x18001d4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c1  nop
0x18001d4c2  mov     rcx, [rdi+10h]
0x18001d4c6  mov     qword ptr [rdi+10h], 0
0x18001d4ce  test    rcx, rcx
0x18001d4d1  jz      short loc_18001D4E0
0x18001d4d3  mov     rax, [rcx]
0x18001d4d6  mov     rax, [rax+10h]
0x18001d4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4df  nop
0x18001d4e0  xor     eax, eax
0x18001d4e2  mov     rbx, [rsp+38h+arg_10]
0x18001d4e7  add     rsp, 30h
0x18001d4eb  pop     rdi
0x18001d4ec  retn
```
