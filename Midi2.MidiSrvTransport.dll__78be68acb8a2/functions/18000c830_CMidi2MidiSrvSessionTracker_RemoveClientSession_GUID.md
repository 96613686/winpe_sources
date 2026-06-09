# CMidi2MidiSrvSessionTracker::RemoveClientSession(_GUID)

- ea: `0x18000c830`
- end: `0x18000c8ca`
- name: `?RemoveClientSession@CMidi2MidiSrvSessionTracker@@UEAAJU_GUID@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(CMidi2MidiSrvSessionTracker *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800017d0`
- `0x180007e24`
- `0x180009bf8`
- `0x18000c830`
- `0x180013730`

## string_xrefs

- `0x18000c850`: `CMidi2MidiSrvSessionTracker::RemoveClientSession`

## pseudocode

```c
__int64 __fastcall CMidi2MidiSrvSessionTracker::RemoveClientSession(CMidi2MidiSrv **this, struct _GUID *a2)
{
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  CMidi2MidiSrv *v7; // rcx
  int v9; // [rsp+20h] [rbp-28h]
  struct _GUID v10; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  CMidi2MidiSrvSessionTracker *v12; // [rsp+50h] [rbp+8h] BYREF
  const char *v13; // [rsp+60h] [rbp+18h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTransportTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v12 = (CMidi2MidiSrvSessionTracker *)this;
    v13 = "CMidi2MidiSrvSessionTracker::RemoveClientSession";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v4,
      (unsigned int)&byte_18001A1AF,
      v5,
      v6,
      (__int64)&v13,
      (__int64)&v12);
  }
  v7 = this[2];
  if ( v7 )
  {
    v10 = *a2;
    return CMidi2MidiSrv::RemoveClientSession(v7, &v10);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"avcore\\midi2\\transport\\midisrvtransport\\midi2.midisrvsessiontracker.cpp",
      (const char *)0x800401F0LL,
      v9);
    return 2147746288LL;
  }
}

```

## disassembly

```asm
0x18000c830  mov     [rsp+arg_8], rbx
0x18000c835  push    rdi
0x18000c836  sub     rsp, 40h
0x18000c83a  mov     rdi, rdx
0x18000c83d  mov     rbx, rcx
0x18000c840  call    ?Instance@MidiSrvTransportTelemetryProvider@@KAPEAV1@XZ; MidiSrvTransportTelemetryProvider::Instance(void)
0x18000c845  mov     rcx, [rax+8]
0x18000c849  mov     eax, [rcx]
0x18000c84b  cmp     eax, 4
0x18000c84e  jbe     short loc_18000C881
0x18000c850  lea     rax, aCmidi2midisrvs_3; "CMidi2MidiSrvSessionTracker::RemoveClie"...
0x18000c857  mov     [rsp+48h+arg_0], rbx
0x18000c85c  mov     [rsp+48h+arg_10], rax
0x18000c861  lea     rdx, byte_18001A1AF
0x18000c868  lea     rax, [rsp+48h+arg_0]
0x18000c86d  mov     [rsp+48h+var_20], rax
0x18000c872  lea     rax, [rsp+48h+arg_10]
0x18000c877  mov     qword ptr [rsp+48h+var_28], rax; int
0x18000c87c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18000c881  mov     rcx, [rbx+10h]; this
0x18000c885  test    rcx, rcx
0x18000c888  jnz     short loc_18000C8AC
0x18000c88a  mov     rcx, [rsp+48h]; this
0x18000c88f  lea     r8, aAvcoreMidi2Tra_3; "avcore\\midi2\\transport\\midisrvtransp"...
0x18000c896  mov     ebx, 800401F0h
0x18000c89b  mov     edx, 55h ; 'U'; void *
0x18000c8a0  mov     r9d, ebx; char *
0x18000c8a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c8a8  mov     eax, ebx
0x18000c8aa  jmp     short loc_18000C8BF
0x18000c8ac  movups  xmm0, xmmword ptr [rdi]
0x18000c8af  lea     rdx, [rsp+48h+var_18]; struct _GUID
0x18000c8b4  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18000c8ba  call    ?RemoveClientSession@CMidi2MidiSrv@@QEAAJU_GUID@@@Z; CMidi2MidiSrv::RemoveClientSession(_GUID)
0x18000c8bf  mov     rbx, [rsp+48h+arg_8]
0x18000c8c4  add     rsp, 40h
0x18000c8c8  pop     rdi
0x18000c8c9  retn
```
