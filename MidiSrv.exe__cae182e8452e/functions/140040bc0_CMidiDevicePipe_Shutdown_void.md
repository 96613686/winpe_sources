# CMidiDevicePipe::Shutdown(void)

- ea: `0x140040bc0`
- end: `0x140040dd0`
- name: `?Shutdown@CMidiDevicePipe@@UEAAJXZ`
- size: `528`
- prototype: `__int64 __fastcall(CMidiDevicePipe *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1400018e4`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14001dc20`
- `0x140040bc0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040c2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040c2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040d46`

## string_xrefs

- `0x140040c58`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040c8c`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040cc0`: `avcore\midi2\service\exe\mididevicepipe.cpp`
- `0x140040d61`: `avcore\midi2\service\exe\mididevicepipe.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMidiDevicePipe::Shutdown(RTL_SRWLOCK *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  PVOID Ptr; // rcx
  int v6; // eax
  PVOID v7; // rcx
  int v8; // eax
  PVOID v9; // rcx
  int v10; // eax
  PVOID v11; // rcx
  PVOID v12; // rcx
  PVOID v13; // rcx
  int v14; // eax
  unsigned int v15; // edi
  _DWORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  const wchar_t *v22; // [rsp+60h] [rbp+20h] BYREF
  RTL_SRWLOCK *v23; // [rsp+68h] [rbp+28h] BYREF
  const char *v24; // [rsp+70h] [rbp+30h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v22 = L"Enter";
    v23 = this;
    v24 = "CMidiDevicePipe::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_14008B689,
      v3,
      v4,
      &v24,
      (__int64)&v23,
      &v22);
  }
  AcquireSRWLockExclusive(this + 15);
  v22 = (const wchar_t *)&this[15];
  Ptr = this[18].Ptr;
  if ( Ptr )
  {
    v6 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Ptr + 32LL))(Ptr);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC,
        (int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v6);
  }
  v7 = this[19].Ptr;
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v7 + 32LL))(v7);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC0,
        (int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v8);
  }
  v9 = this[20].Ptr;
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v9 + 32LL))(v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC4,
        (int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
        (const char *)(unsigned int)v10);
  }
  v11 = this[18].Ptr;
  this[18].Ptr = 0;
  if ( v11 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = this[19].Ptr;
  this[19].Ptr = 0;
  if ( v12 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = this[20].Ptr;
  this[20].Ptr = 0;
  if ( v13 )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v13 + 16LL))(v13);
  if ( this != (RTL_SRWLOCK *)-120LL )
    ReleaseSRWLockExclusive(this + 15);
  v14 = CMidiPipe::Shutdown((CMidiPipe *)this);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v17 > 4u )
    {
      v22 = L"Exit success";
      v23 = this;
      v24 = "CMidiDevicePipe::Shutdown";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v17,
        (__int64)byte_14008B5AB,
        v18,
        v19,
        &v24,
        (__int64)&v23,
        &v22);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"avcore\\midi2\\service\\exe\\mididevicepipe.cpp",
      (const char *)(unsigned int)v14,
      v20);
    return v15;
  }
}

```

## disassembly

```asm
0x140040bc0  mov     [rsp-18h+arg_18], rbx
0x140040bc5  push    rbp
0x140040bc6  push    rdi
0x140040bc7  push    r15
0x140040bc9  mov     rbp, rsp
0x140040bcc  sub     rsp, 40h
0x140040bd0  mov     rbx, rcx
0x140040bd3  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140040bd8  mov     rcx, [rax+8]
0x140040bdc  mov     eax, [rcx]
0x140040bde  lea     r15, aCmididevicepip; "CMidiDevicePipe::Shutdown"
0x140040be5  cmp     eax, 4
0x140040be8  jbe     short loc_140040C24
0x140040bea  lea     rax, aEnter; "Enter"
0x140040bf1  mov     [rbp+arg_0], rax
0x140040bf5  mov     [rbp+arg_8], rbx
0x140040bf9  mov     [rbp+arg_10], r15
0x140040bfd  lea     rax, [rbp+arg_0]
0x140040c01  mov     [rsp+40h+var_10], rax
0x140040c06  lea     rax, [rbp+arg_8]
0x140040c0a  mov     [rsp+40h+var_18], rax
0x140040c0f  lea     rax, [rbp+arg_10]
0x140040c13  mov     qword ptr [rsp+40h+var_20], rax; int
0x140040c18  lea     rdx, byte_14008B689
0x140040c1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140040c24  lea     rdi, [rbx+78h]
0x140040c28  mov     rcx, rdi; SRWLock
0x140040c2b  call    cs:__imp_AcquireSRWLockExclusive
0x140040c31  mov     [rbp+arg_0], rdi
0x140040c35  mov     rcx, [rbx+90h]
0x140040c3c  test    rcx, rcx
0x140040c3f  jz      short loc_140040C69
0x140040c41  mov     rax, [rcx]
0x140040c44  mov     rax, [rax+20h]
0x140040c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040c4d  mov     rcx, [rbp+18h]; this
0x140040c51  test    eax, eax
0x140040c53  jns     short loc_140040C69
0x140040c55  mov     r9d, eax; char *
0x140040c58  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040c5f  mov     edx, 0BCh; void *
0x140040c64  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140040c69  mov     rcx, [rbx+98h]
0x140040c70  test    rcx, rcx
0x140040c73  jz      short loc_140040C9D
0x140040c75  mov     rax, [rcx]
0x140040c78  mov     rax, [rax+20h]
0x140040c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040c81  mov     rcx, [rbp+18h]; this
0x140040c85  test    eax, eax
0x140040c87  jns     short loc_140040C9D
0x140040c89  mov     r9d, eax; char *
0x140040c8c  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040c93  mov     edx, 0C0h; void *
0x140040c98  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140040c9d  mov     rcx, [rbx+0A0h]
0x140040ca4  test    rcx, rcx
0x140040ca7  jz      short loc_140040CD2
0x140040ca9  mov     rax, [rcx]
0x140040cac  mov     rax, [rax+20h]
0x140040cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040cb5  mov     rcx, [rbp+18h]; this
0x140040cb9  test    eax, eax
0x140040cbb  jns     short loc_140040CD2
0x140040cbd  mov     r9d, eax; char *
0x140040cc0  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040cc7  mov     edx, 0C4h; void *
0x140040ccc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140040cd1  nop
0x140040cd2  mov     rcx, [rbx+90h]
0x140040cd9  mov     qword ptr [rbx+90h], 0
0x140040ce4  test    rcx, rcx
0x140040ce7  jz      short loc_140040CF6
0x140040ce9  mov     rax, [rcx]
0x140040cec  mov     rax, [rax+10h]
0x140040cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040cf5  nop
0x140040cf6  mov     rcx, [rbx+98h]
0x140040cfd  mov     qword ptr [rbx+98h], 0
0x140040d08  test    rcx, rcx
0x140040d0b  jz      short loc_140040D1A
0x140040d0d  mov     rax, [rcx]
0x140040d10  mov     rax, [rax+10h]
0x140040d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040d19  nop
0x140040d1a  mov     rcx, [rbx+0A0h]
0x140040d21  mov     qword ptr [rbx+0A0h], 0
0x140040d2c  test    rcx, rcx
0x140040d2f  jz      short loc_140040D3E
0x140040d31  mov     rax, [rcx]
0x140040d34  mov     rax, [rax+10h]
0x140040d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040d3d  nop
0x140040d3e  test    rdi, rdi
0x140040d41  jz      short loc_140040D4C
0x140040d43  mov     rcx, rdi; SRWLock
0x140040d46  call    cs:__imp_ReleaseSRWLockExclusive
0x140040d4c  mov     rcx, rbx; this
0x140040d4f  call    ?Shutdown@CMidiPipe@@UEAAJXZ; CMidiPipe::Shutdown(void)
0x140040d54  mov     edi, eax
0x140040d56  test    eax, eax
0x140040d58  jns     short loc_140040D76
0x140040d5a  mov     rcx, [rbp+18h]; this
0x140040d5e  mov     r9d, eax; char *
0x140040d61  lea     r8, aAvcoreMidi2Ser_11; "avcore\\midi2\\service\\exe\\mididevice"...
0x140040d68  mov     edx, 0CCh; void *
0x140040d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140040d72  mov     eax, edi
0x140040d74  jmp     short loc_140040DC2
0x140040d76  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140040d7b  mov     rcx, [rax+8]
0x140040d7f  mov     eax, [rcx]
0x140040d81  cmp     eax, 4
0x140040d84  jbe     short loc_140040DC0
0x140040d86  lea     rax, aExitSuccess_0; "Exit success"
0x140040d8d  mov     [rbp+arg_0], rax
0x140040d91  mov     [rbp+arg_8], rbx
0x140040d95  mov     [rbp+arg_10], r15
0x140040d99  lea     rax, [rbp+arg_0]
0x140040d9d  mov     [rsp+40h+var_10], rax
0x140040da2  lea     rax, [rbp+arg_8]
0x140040da6  mov     [rsp+40h+var_18], rax
0x140040dab  lea     rax, [rbp+arg_10]
0x140040daf  mov     qword ptr [rsp+40h+var_20], rax
0x140040db4  lea     rdx, byte_14008B5AB
0x140040dbb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140040dc0  xor     eax, eax
0x140040dc2  mov     rbx, [rsp+40h+arg_18]
0x140040dc7  add     rsp, 40h
0x140040dcb  pop     r15
0x140040dcd  pop     rdi
0x140040dce  pop     rbp
0x140040dcf  retn
```
