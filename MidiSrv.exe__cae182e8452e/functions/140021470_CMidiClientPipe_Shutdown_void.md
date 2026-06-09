# CMidiClientPipe::Shutdown(void)

- ea: `0x140021470`
- end: `0x140021566`
- name: `?Shutdown@CMidiClientPipe@@UEAAJXZ`
- size: `246`
- prototype: `__int64 __fastcall(CMidiClientPipe *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task`

## callees

- `0x14000183c`
- `0x140005868`
- `0x14000984c`
- `0x14000a6b4`
- `0x14001dc20`
- `0x140021470`
- `0x14004616c`
- `0x140047b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400214ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400214ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002153c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002154e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002153c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14002154e`

## string_xrefs

- `0x140021520`: `avcore\midi2\service\exe\midiclientpipe.cpp`

## pseudocode

```c
__int64 __fastcall CMidiClientPipe::Shutdown(RTL_SRWLOCK *this)
{
  _DWORD *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  RTL_SRWLOCK *v5; // rbx
  CMidiXProc *Ptr; // rcx
  CMidiXProc *v7; // rsi
  int v8; // eax
  unsigned int v9; // edi
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const char *v13; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v13 = "CMidiClientPipe::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)v2,
      (__int64)&dword_140088514,
      v3,
      v4,
      &v13);
  }
  v5 = this + 15;
  AcquireSRWLockExclusive(this + 15);
  Ptr = (CMidiXProc *)this[17].Ptr;
  if ( Ptr )
  {
    CMidiXProc::Shutdown(Ptr);
    v7 = (CMidiXProc *)this[17].Ptr;
    this[17].Ptr = 0;
    if ( v7 )
    {
      CMidiXProc::~CMidiXProc(v7);
      operator delete(v7);
    }
  }
  v8 = CMidiPipe::Shutdown((CMidiPipe *)this);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiclientpipe.cpp",
      (const char *)(unsigned int)v8,
      v11);
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    return v9;
  }
}

```

## disassembly

```asm
0x140021470  mov     [rsp+arg_10], rbx
0x140021475  mov     [rsp+arg_18], rsi
0x14002147a  push    rdi
0x14002147b  sub     rsp, 30h
0x14002147f  mov     rdi, rcx
0x140021482  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140021487  mov     rcx, [rax+8]
0x14002148b  mov     eax, [rcx]
0x14002148d  cmp     eax, 4
0x140021490  jbe     short loc_1400214C3
0x140021492  lea     rax, aCmidiclientpip_1; "CMidiClientPipe::Shutdown"
0x140021499  mov     [rsp+38h+arg_0], rdi
0x14002149e  mov     [rsp+38h+arg_8], rax
0x1400214a3  lea     rdx, dword_140088514
0x1400214aa  lea     rax, [rsp+38h+arg_0]
0x1400214af  mov     [rsp+38h+var_10], rax
0x1400214b4  lea     rax, [rsp+38h+arg_8]
0x1400214b9  mov     qword ptr [rsp+38h+var_18], rax; int
0x1400214be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1400214c3  lea     rbx, [rdi+78h]
0x1400214c7  mov     rcx, rbx; SRWLock
0x1400214ca  call    cs:__imp_AcquireSRWLockExclusive
0x1400214d0  mov     rcx, [rdi+88h]; this
0x1400214d7  test    rcx, rcx
0x1400214da  jz      short loc_14002150D
0x1400214dc  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x1400214e1  mov     rsi, [rdi+88h]
0x1400214e8  mov     qword ptr [rdi+88h], 0
0x1400214f3  test    rsi, rsi
0x1400214f6  jz      short loc_14002150D
0x1400214f8  mov     rcx, rsi; this
0x1400214fb  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x140021500  mov     edx, 90h
0x140021505  mov     rcx, rsi; Block
0x140021508  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002150d  mov     rcx, rdi; this
0x140021510  call    ?Shutdown@CMidiPipe@@UEAAJXZ; CMidiPipe::Shutdown(void)
0x140021515  mov     edi, eax
0x140021517  test    eax, eax
0x140021519  jns     short loc_140021546
0x14002151b  mov     rcx, [rsp+38h]; this
0x140021520  lea     r8, aAvcoreMidi2Ser_2; "avcore\\midi2\\service\\exe\\midiclient"...
0x140021527  mov     r9d, eax; char *
0x14002152a  mov     edx, 0D1h; void *
0x14002152f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021534  test    rbx, rbx
0x140021537  jz      short loc_140021542
0x140021539  mov     rcx, rbx; SRWLock
0x14002153c  call    cs:__imp_ReleaseSRWLockExclusive
0x140021542  mov     eax, edi
0x140021544  jmp     short loc_140021556
0x140021546  test    rbx, rbx
0x140021549  jz      short loc_140021554
0x14002154b  mov     rcx, rbx; SRWLock
0x14002154e  call    cs:__imp_ReleaseSRWLockExclusive
0x140021554  xor     eax, eax
0x140021556  mov     rbx, [rsp+38h+arg_10]
0x14002155b  mov     rsi, [rsp+38h+arg_18]
0x140021560  add     rsp, 30h
0x140021564  pop     rdi
0x140021565  retn
```
