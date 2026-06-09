# CMidi2MidiSrvSessionTracker::UpdateClientSessionName(_GUID,ushort const *)

- ea: `0x18000c9a0`
- end: `0x18000ca4c`
- name: `?UpdateClientSessionName@CMidi2MidiSrvSessionTracker@@UEAAJU_GUID@@PEBG@Z`
- size: `172`
- prototype: `int(CMidi2MidiSrvSessionTracker *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800017d0`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c9a0`
- `0x180013a3c`

## string_xrefs

- `0x18000c9c8`: `CMidi2MidiSrvSessionTracker::UpdateClientSessionName`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvSessionTracker::UpdateClientSessionName(
        CMidi2MidiSrv **this,
        struct _GUID *a2,
        const unsigned __int16 *a3)
{
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  CMidi2MidiSrv *v9; // rcx
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-28h]
  struct _GUID v13; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2MidiSrvSessionTracker *v15; // [rsp+50h] [rbp+8h] BYREF
  const char *v16; // [rsp+68h] [rbp+20h] BYREF

  v6 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v6 > 4u )
  {
    v15 = (CMidi2MidiSrvSessionTracker *)this;
    v16 = "CMidi2MidiSrvSessionTracker::UpdateClientSessionName";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v6,
      (unsigned int)qword_18001A1D8,
      v7,
      v8,
      (__int64)&v16,
      (__int64)&v15);
  }
  v9 = this[2];
  if ( v9 )
  {
    v13 = *a2;
    return (unsigned int)CMidi2MidiSrv::UpdateClientSessionName(v9, &v13, a3);
  }
  else
  {
    v10 = -2147221008;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvsessiontracker.cpp",
      (const char *)0x800401F0LL,
      v12);
  }
  return v10;
}

```

## disassembly

```asm
0x18000c9a0  mov     [rsp+arg_8], rbx
0x18000c9a5  mov     [rsp+arg_10], rsi
0x18000c9aa  push    rdi
0x18000c9ab  sub     rsp, 40h
0x18000c9af  mov     rdi, r8
0x18000c9b2  mov     rsi, rdx
0x18000c9b5  mov     rbx, rcx
0x18000c9b8  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c9bd  mov     rcx, [rax+8]
0x18000c9c1  mov     eax, [rcx]
0x18000c9c3  cmp     eax, 4
0x18000c9c6  jbe     short loc_18000C9F9
0x18000c9c8  lea     rax, aCmidi2midisrvs_0; "CMidi2MidiSrvSessionTracker::UpdateClie"...
0x18000c9cf  mov     [rsp+48h+arg_0], rbx
0x18000c9d4  mov     [rsp+48h+arg_18], rax
0x18000c9d9  lea     rdx, qword_18001A1D8
0x18000c9e0  lea     rax, [rsp+48h+arg_0]
0x18000c9e5  mov     [rsp+48h+var_20], rax
0x18000c9ea  lea     rax, [rsp+48h+arg_18]
0x18000c9ef  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c9f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c9f9  mov     rcx, [rbx+10h]; this
0x18000c9fd  test    rcx, rcx
0x18000ca00  jnz     short loc_18000CA22
0x18000ca02  mov     rcx, [rsp+48h]; this
0x18000ca07  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000ca0e  mov     ebx, 800401F0h
0x18000ca13  mov     edx, 42h ; 'B'; void *
0x18000ca18  mov     r9d, ebx; char *
0x18000ca1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ca20  jmp     short loc_18000CA3A
0x18000ca22  movups  xmm0, xmmword ptr [rsi]
0x18000ca25  mov     r8, rdi; unsigned __int16 *
0x18000ca28  lea     rdx, [rsp+48h+var_18]; struct _GUID
0x18000ca2d  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18000ca33  call    ?UpdateClientSessionName@CMidi2MidiSrv@@QEAAJU_GUID@@PEBG@Z; CMidi2MidiSrv::UpdateClientSessionName(_GUID,ushort const *)
0x18000ca38  mov     ebx, eax
0x18000ca3a  mov     rsi, [rsp+48h+arg_10]
0x18000ca3f  mov     eax, ebx
0x18000ca41  mov     rbx, [rsp+48h+arg_8]
0x18000ca46  add     rsp, 40h
0x18000ca4a  pop     rdi
0x18000ca4b  retn
```
