# CMidi2MidiSrvOut::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18000baa0`
- end: `0x18000bba2`
- name: `?SendMidiMessage@CMidi2MidiSrvOut@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001878`
- `0x180009bf8`
- `0x18000baa0`
- `0x18000bc80`
- `0x18001389c`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvOut::SendMidiMessage(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  struct MidiSrvTransportTelemetryProvider *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edi
  _DWORD *v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v17; // [rsp+60h] [rbp-11h] BYREF
  __int64 v18; // [rsp+68h] [rbp-9h] BYREF
  __int64 v19; // [rsp+70h] [rbp-1h] BYREF
  const wchar_t *v20; // [rsp+78h] [rbp+7h] BYREF
  __int64 v21; // [rsp+80h] [rbp+Fh] BYREF
  const char *v22; // [rsp+88h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  unsigned int v24; // [rsp+D0h] [rbp+5Fh] BYREF

  if ( !*(_QWORD *)(a1 + 16) )
    return 2147500036LL;
  v9 = MidiSrvTransportTelemetryProvider::Instance();
  v12 = a5;
  v13 = (_DWORD *)*((_QWORD *)v9 + 1);
  if ( *v13 > 5u )
  {
    v18 = a5;
    v20 = L"Sending MIDI Message.";
    v24 = a4;
    v22 = "CMidi2MidiSrvOut::SendMidiMessage";
    v19 = a3;
    v17 = a2;
    v21 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)v13,
      (unsigned __int8 *)&byte_180019EBF,
      v10,
      v11,
      (const unsigned __int16 **)&v22,
      (__int64)&v21,
      (__int64 **)&v20,
      (__int64)&v17,
      (__int64)&v19,
      (__int64)&v24,
      (__int64)&v18);
  }
  v14 = CMidi2MidiSrv::SendMidiMessage(*(_QWORD *)(a1 + 16), a2, a3, a4);
  v15 = v14;
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvout.cpp",
      (const char *)(unsigned int)v14,
      v12);
  return v15;
}

```

## disassembly

```asm
0x18000baa0  push    rbp
0x18000baa2  push    rbx
0x18000baa3  push    rsi
0x18000baa4  push    rdi
0x18000baa5  push    r14
0x18000baa7  push    r15
0x18000baa9  lea     rbp, [rsp-27h]
0x18000baae  sub     rsp, 98h
0x18000bab5  cmp     qword ptr [rcx+10h], 0
0x18000baba  mov     esi, r9d
0x18000babd  mov     r14, r8
0x18000bac0  mov     r15d, edx
0x18000bac3  mov     rbx, rcx
0x18000bac6  jz      loc_18000BB8D
0x18000bacc  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000bad1  mov     rdi, [rbp+4Fh+arg_20]
0x18000bad5  mov     rcx, [rax+8]
0x18000bad9  mov     eax, [rcx]
0x18000badb  cmp     eax, 5
0x18000bade  jbe     short loc_18000BB54
0x18000bae0  lea     rax, aSendingMidiMes; "Sending MIDI Message."
0x18000bae7  mov     [rbp+4Fh+var_58], rdi
0x18000baeb  mov     [rbp+4Fh+var_48], rax
0x18000baef  lea     rdx, byte_180019EBF
0x18000baf6  lea     rax, aCmidi2midisrvo; "CMidi2MidiSrvOut::SendMidiMessage"
0x18000bafd  mov     [rbp+4Fh+arg_0], esi
0x18000bb00  mov     [rbp+4Fh+var_38], rax
0x18000bb04  lea     rax, [rbp+4Fh+var_58]
0x18000bb08  mov     [rsp+0C0h+var_70], rax
0x18000bb0d  lea     rax, [rbp+4Fh+arg_0]
0x18000bb11  mov     [rsp+0C0h+var_78], rax
0x18000bb16  lea     rax, [rbp+4Fh+var_50]
0x18000bb1a  mov     [rsp+0C0h+var_80], rax
0x18000bb1f  lea     rax, [rbp+4Fh+var_60]
0x18000bb23  mov     [rsp+0C0h+var_88], rax
0x18000bb28  lea     rax, [rbp+4Fh+var_48]
0x18000bb2c  mov     [rsp+0C0h+var_90], rax
0x18000bb31  lea     rax, [rbp+4Fh+var_40]
0x18000bb35  mov     [rsp+0C0h+var_98], rax
0x18000bb3a  lea     rax, [rbp+4Fh+var_38]
0x18000bb3e  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18000bb43  mov     [rbp+4Fh+var_50], r14
0x18000bb47  mov     [rbp+4Fh+var_60], r15d
0x18000bb4b  mov     [rbp+4Fh+var_40], rbx
0x18000bb4f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18000bb54  mov     rcx, [rbx+10h]
0x18000bb58  mov     r9d, esi
0x18000bb5b  mov     r8, r14
0x18000bb5e  mov     qword ptr [rsp+0C0h+var_A0], rdi; int
0x18000bb63  mov     edx, r15d
0x18000bb66  call    ?SendMidiMessage@CMidi2MidiSrv@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidi2MidiSrv::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x18000bb6b  mov     ebx, eax
0x18000bb6d  test    eax, eax
0x18000bb6f  jns     short loc_18000BB89
0x18000bb71  mov     rcx, [rbp+57h]; this
0x18000bb75  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000bb7c  mov     r9d, eax; char *
0x18000bb7f  mov     edx, 66h ; 'f'; void *
0x18000bb84  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000bb89  mov     eax, ebx
0x18000bb8b  jmp     short loc_18000BB92
0x18000bb8d  mov     eax, 80004004h
0x18000bb92  add     rsp, 98h
0x18000bb99  pop     r15
0x18000bb9b  pop     r14
0x18000bb9d  pop     rdi
0x18000bb9e  pop     rsi
0x18000bb9f  pop     rbx
0x18000bba0  pop     rbp
0x18000bba1  retn
```
