# CMidi2LoopbackMidiConfigurationManager::Shutdown(void)

- ea: `0x180018400`
- end: `0x1800184bb`
- name: `?Shutdown@CMidi2LoopbackMidiConfigurationManager@@UEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CMidi2LoopbackMidiConfigurationManager *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001a38`
- `0x18000bfe4`
- `0x18000ccd8`
- `0x180018400`
- `0x180032010`

## string_xrefs

- `0x180018422`: `CMidi2LoopbackMidiConfigurationManager::Shutdown`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2LoopbackMidiConfigurationManager::Shutdown(CMidi2LoopbackMidiConfigurationManager *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  struct TransportState *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  CMidi2LoopbackMidiConfigurationManager *v10; // [rsp+40h] [rbp+8h] BYREF
  const char *v11; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiLoopbackMidiTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v10 = this;
    v11 = "CMidi2LoopbackMidiConfigurationManager::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)byte_1800580B3,
      v3,
      v4,
      (__int64)&v11,
      (__int64)&v10);
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
  v8 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x180018400  mov     [rsp+arg_10], rbx
0x180018405  push    rdi
0x180018406  sub     rsp, 30h
0x18001840a  mov     rdi, rcx
0x18001840d  call    ?Instance@MidiLoopbackMidiTransportTelemetryProvider@@KAPEAV1@XZ; MidiLoopbackMidiTransportTelemetryProvider::Instance(void)
0x180018412  mov     rcx, [rax+8]
0x180018416  mov     eax, [rcx]
0x180018418  cmp     eax, 4
0x18001841b  jbe     short loc_18001844E
0x18001841d  mov     [rsp+38h+arg_0], rdi
0x180018422  lea     rax, aCmidi2loopback_9; "CMidi2LoopbackMidiConfigurationManager:"...
0x180018429  mov     [rsp+38h+arg_8], rax
0x18001842e  lea     rax, [rsp+38h+arg_0]
0x180018433  mov     [rsp+38h+var_10], rax
0x180018438  lea     rax, [rsp+38h+arg_8]
0x18001843d  mov     [rsp+38h+var_18], rax
0x180018442  lea     rdx, byte_1800580B3
0x180018449  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001844e  call    ?Current@TransportState@@SAAEAV1@XZ; TransportState::Current(void)
0x180018453  mov     rbx, rax
0x180018456  mov     rcx, [rax]
0x180018459  mov     qword ptr [rax], 0
0x180018460  test    rcx, rcx
0x180018463  jz      short loc_180018472
0x180018465  mov     rdx, [rcx]
0x180018468  mov     rax, [rdx+10h]
0x18001846c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018471  nop
0x180018472  mov     rcx, [rbx+8]
0x180018476  mov     qword ptr [rbx+8], 0
0x18001847e  test    rcx, rcx
0x180018481  jz      short loc_180018490
0x180018483  mov     rax, [rcx]
0x180018486  mov     rax, [rax+10h]
0x18001848a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001848f  nop
0x180018490  mov     rcx, [rdi+10h]
0x180018494  mov     qword ptr [rdi+10h], 0
0x18001849c  test    rcx, rcx
0x18001849f  jz      short loc_1800184AE
0x1800184a1  mov     rax, [rcx]
0x1800184a4  mov     rax, [rax+10h]
0x1800184a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ad  nop
0x1800184ae  xor     eax, eax
0x1800184b0  mov     rbx, [rsp+38h+arg_10]
0x1800184b5  add     rsp, 30h
0x1800184b9  pop     rdi
0x1800184ba  retn
```
