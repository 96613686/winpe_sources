# CMidiPipe::RemoveClient(unsigned __int64)

- ea: `0x14001ce50`
- end: `0x14001d0a9`
- name: `?RemoveClient@CMidiPipe@@UEAAX_K@Z`
- size: `601`
- prototype: `void __fastcall(CMidiPipe *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x140001bc0`
- `0x140005180`
- `0x1400060ec`
- `0x14000984c`
- `0x14000c598`
- `0x14001ce50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001cf28`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001cf28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001d098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001d098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cf0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cf1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cf0c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001cf1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cee4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14001cee4`

## string_xrefs

- `0x14001cf95`: `avcore\midi2\service\Inc\MidiPipe.h`
- `0x14001cf88`: `Client removed from internal list`
- `0x14001ce69`: `CMidiPipe::RemoveClient`

## pseudocode

```c
void __fastcall CMidiPipe::RemoveClient(RTL_SRWLOCK *this, __int64 a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  RTL_SRWLOCK *v7; // rax
  __int64 trivial_8; // rax
  PVOID Ptr; // r8
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  RTL_SRWLOCK *v13; // rax
  char *v14; // rdx
  const wchar_t *v15; // rax
  RTL_SRWLOCK *v16; // rax
  _DWORD *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  RTL_SRWLOCK *v20; // rax
  const char *v21; // [rsp+50h] [rbp-10h] BYREF
  int v22[2]; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  RTL_SRWLOCK *v24; // [rsp+90h] [rbp+30h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+40h] BYREF
  const wchar_t *v26; // [rsp+A8h] [rbp+48h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    v7 = this + 2;
    if ( this[5].Ptr > (PVOID)7 )
      v7 = (RTL_SRWLOCK *)v7->Ptr;
    v24 = v7;
    v25 = a2;
    v26 = L"Enter";
    v21 = (const char *)this;
    *(_QWORD *)v22 = "CMidiPipe::RemoveClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_140088153,
      v5,
      v6,
      v22,
      (__int64)&v21,
      &v26,
      (__int64)&v25,
      &v24);
  }
  AcquireSRWLockShared(this + 8);
  if ( (PVOID)_std_find_trivial_8(this[11].Ptr, this[12].Ptr, a2) == this[12].Ptr )
  {
    if ( this != (RTL_SRWLOCK *)-64LL )
      ReleaseSRWLockShared(this + 8);
    return;
  }
  if ( this != (RTL_SRWLOCK *)-64LL )
    ReleaseSRWLockShared(this + 8);
  AcquireSRWLockExclusive(this + 8);
  trivial_8 = _std_find_trivial_8(this[11].Ptr, this[12].Ptr, a2);
  Ptr = this[12].Ptr;
  if ( (PVOID)trivial_8 == Ptr )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x128,
      (int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
      (const char *)0x80070490LL);
    v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v10 > 3u )
    {
      v16 = this + 2;
      if ( this[5].Ptr > (PVOID)7 )
        v16 = (RTL_SRWLOCK *)v16->Ptr;
      v24 = v16;
      v14 = byte_140087359;
      v15 = L"Client not found";
      goto LABEL_19;
    }
  }
  else
  {
    memmove_0((void *)trivial_8, (const void *)(trivial_8 + 8), (size_t)Ptr - trivial_8 - 8);
    this[12].Ptr = (char *)this[12].Ptr - 8;
    v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v10 > 4u )
    {
      v13 = this + 2;
      if ( this[5].Ptr > (PVOID)7 )
        v13 = (RTL_SRWLOCK *)v13->Ptr;
      v24 = v13;
      v14 = byte_14008831D;
      v15 = L"Client removed from internal list";
LABEL_19:
      v26 = v15;
      v25 = a2;
      *(_QWORD *)v22 = this;
      v21 = "CMidiPipe::RemoveClient";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)v14,
        v11,
        v12,
        &v21,
        (__int64)v22,
        &v26,
        (__int64)&v25,
        &v24);
    }
  }
  v17 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v17 > 4u )
  {
    v20 = this + 2;
    if ( this[5].Ptr > (PVOID)7 )
      v20 = (RTL_SRWLOCK *)v20->Ptr;
    v24 = v20;
    v25 = a2;
    v26 = L"Exit";
    *(_QWORD *)v22 = this;
    v21 = "CMidiPipe::RemoveClient";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      (__int64)v17,
      (__int64)byte_140087623,
      v18,
      v19,
      &v21,
      (__int64)v22,
      &v26,
      (__int64)&v25,
      &v24);
  }
  if ( this != (RTL_SRWLOCK *)-64LL )
    ReleaseSRWLockExclusive(this + 8);
}

```

## disassembly

```asm
0x14001ce50  push    rbp
0x14001ce52  push    rbx
0x14001ce53  push    rsi
0x14001ce54  push    rdi
0x14001ce55  push    r14
0x14001ce57  mov     rbp, rsp
0x14001ce5a  sub     rsp, 60h
0x14001ce5e  mov     rsi, rdx
0x14001ce61  mov     rbx, rcx
0x14001ce64  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001ce69  lea     r14, aCmidipipeRemov; "CMidiPipe::RemoveClient"
0x14001ce70  mov     rcx, [rax+8]
0x14001ce74  mov     eax, [rcx]
0x14001ce76  cmp     eax, 4
0x14001ce79  jbe     short loc_14001CEDD
0x14001ce7b  lea     rax, [rbx+10h]
0x14001ce7f  cmp     qword ptr [rax+18h], 7
0x14001ce84  jbe     short loc_14001CE89
0x14001ce86  mov     rax, [rax]
0x14001ce89  mov     [rbp+arg_0], rax
0x14001ce8d  lea     rdx, byte_140088153
0x14001ce94  lea     rax, aEnter; "Enter"
0x14001ce9b  mov     [rbp+arg_10], rsi
0x14001ce9f  mov     [rbp+arg_18], rax
0x14001cea3  lea     rax, [rbp+arg_0]
0x14001cea7  mov     [rsp+60h+var_20], rax
0x14001ceac  lea     rax, [rbp+arg_10]
0x14001ceb0  mov     [rsp+60h+var_28], rax
0x14001ceb5  lea     rax, [rbp+arg_18]
0x14001ceb9  mov     [rsp+60h+var_30], rax
0x14001cebe  lea     rax, [rbp+var_10]
0x14001cec2  mov     [rsp+60h+var_38], rax
0x14001cec7  lea     rax, [rbp+var_8]
0x14001cecb  mov     qword ptr [rsp+60h+var_40], rax; int
0x14001ced0  mov     [rbp+var_10], rbx
0x14001ced4  mov     qword ptr [rbp+var_8], r14
0x14001ced8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001cedd  lea     rdi, [rbx+40h]
0x14001cee1  mov     rcx, rdi; SRWLock
0x14001cee4  call    cs:__imp_AcquireSRWLockShared
0x14001ceea  mov     rdx, [rbx+60h]
0x14001ceee  mov     r8, rsi
0x14001cef1  mov     rcx, [rbx+58h]
0x14001cef5  call    __std_find_trivial_8
0x14001cefa  cmp     rax, [rbx+60h]
0x14001cefe  jnz     short loc_14001CF17
0x14001cf00  test    rdi, rdi
0x14001cf03  jz      loc_14001D09E
0x14001cf09  mov     rcx, rdi; SRWLock
0x14001cf0c  call    cs:__imp_ReleaseSRWLockShared
0x14001cf12  jmp     loc_14001D09E
0x14001cf17  test    rdi, rdi
0x14001cf1a  jz      short loc_14001CF25
0x14001cf1c  mov     rcx, rdi; SRWLock
0x14001cf1f  call    cs:__imp_ReleaseSRWLockShared
0x14001cf25  mov     rcx, rdi; SRWLock
0x14001cf28  call    cs:__imp_AcquireSRWLockExclusive
0x14001cf2e  mov     rdx, [rbx+60h]
0x14001cf32  mov     r8, rsi
0x14001cf35  mov     rcx, [rbx+58h]
0x14001cf39  call    __std_find_trivial_8
0x14001cf3e  mov     r8, [rbx+60h]
0x14001cf42  cmp     rax, r8
0x14001cf45  jz      short loc_14001CF91
0x14001cf47  lea     rdx, [rax+8]; Src
0x14001cf4b  mov     rcx, rax; void *
0x14001cf4e  sub     r8, rdx; Size
0x14001cf51  call    memmove_0
0x14001cf56  add     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFF8h
0x14001cf5b  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001cf60  mov     rcx, [rax+8]
0x14001cf64  mov     eax, [rcx]
0x14001cf66  cmp     eax, 4
0x14001cf69  jbe     loc_14001D01E
0x14001cf6f  lea     rax, [rbx+10h]
0x14001cf73  cmp     qword ptr [rax+18h], 7
0x14001cf78  jbe     short loc_14001CF7D
0x14001cf7a  mov     rax, [rax]
0x14001cf7d  mov     [rbp+arg_0], rax
0x14001cf81  lea     rdx, byte_14008831D
0x14001cf88  lea     rax, aClientRemovedF; "Client removed from internal list"
0x14001cf8f  jmp     short loc_14001CFDC
0x14001cf91  mov     rcx, [rbp+28h]; this
0x14001cf95  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x14001cf9c  mov     r9d, 80070490h; char *
0x14001cfa2  mov     edx, 128h; void *
0x14001cfa7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001cfac  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001cfb1  mov     rcx, [rax+8]
0x14001cfb5  mov     eax, [rcx]
0x14001cfb7  cmp     eax, 3
0x14001cfba  jbe     short loc_14001D01E
0x14001cfbc  lea     rax, [rbx+10h]
0x14001cfc0  cmp     qword ptr [rax+18h], 7
0x14001cfc5  jbe     short loc_14001CFCA
0x14001cfc7  mov     rax, [rax]
0x14001cfca  mov     [rbp+arg_0], rax
0x14001cfce  lea     rdx, byte_140087359
0x14001cfd5  lea     rax, aClientNotFound; "Client not found"
0x14001cfdc  mov     [rbp+arg_18], rax
0x14001cfe0  lea     rax, [rbp+arg_0]
0x14001cfe4  mov     [rsp+60h+var_20], rax
0x14001cfe9  lea     rax, [rbp+arg_10]
0x14001cfed  mov     [rsp+60h+var_28], rax
0x14001cff2  lea     rax, [rbp+arg_18]
0x14001cff6  mov     [rsp+60h+var_30], rax
0x14001cffb  lea     rax, [rbp+var_8]
0x14001cfff  mov     [rsp+60h+var_38], rax
0x14001d004  lea     rax, [rbp+var_10]
0x14001d008  mov     qword ptr [rsp+60h+var_40], rax
0x14001d00d  mov     [rbp+arg_10], rsi
0x14001d011  mov     qword ptr [rbp+var_8], rbx
0x14001d015  mov     [rbp+var_10], r14
0x14001d019  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001d01e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14001d023  mov     rcx, [rax+8]
0x14001d027  mov     eax, [rcx]
0x14001d029  cmp     eax, 4
0x14001d02c  jbe     short loc_14001D090
0x14001d02e  lea     rax, [rbx+10h]
0x14001d032  cmp     qword ptr [rax+18h], 7
0x14001d037  jbe     short loc_14001D03C
0x14001d039  mov     rax, [rax]
0x14001d03c  mov     [rbp+arg_0], rax
0x14001d040  lea     rdx, byte_140087623
0x14001d047  lea     rax, aExit; "Exit"
0x14001d04e  mov     [rbp+arg_10], rsi
0x14001d052  mov     [rbp+arg_18], rax
0x14001d056  lea     rax, [rbp+arg_0]
0x14001d05a  mov     [rsp+60h+var_20], rax
0x14001d05f  lea     rax, [rbp+arg_10]
0x14001d063  mov     [rsp+60h+var_28], rax
0x14001d068  lea     rax, [rbp+arg_18]
0x14001d06c  mov     [rsp+60h+var_30], rax
0x14001d071  lea     rax, [rbp+var_8]
0x14001d075  mov     [rsp+60h+var_38], rax
0x14001d07a  lea     rax, [rbp+var_10]
0x14001d07e  mov     qword ptr [rsp+60h+var_40], rax
0x14001d083  mov     qword ptr [rbp+var_8], rbx
0x14001d087  mov     [rbp+var_10], r14
0x14001d08b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x14001d090  test    rdi, rdi
0x14001d093  jz      short loc_14001D09E
0x14001d095  mov     rcx, rdi; SRWLock
0x14001d098  call    cs:__imp_ReleaseSRWLockExclusive
0x14001d09e  add     rsp, 60h
0x14001d0a2  pop     r14
0x14001d0a4  pop     rdi
0x14001d0a5  pop     rsi
0x14001d0a6  pop     rbx
0x14001d0a7  pop     rbp
0x14001d0a8  retn
```
