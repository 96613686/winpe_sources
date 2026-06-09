# CMPEG2PushClock::~CMPEG2PushClock(void)

- ea: `0x180025570`
- end: `0x1800256c1`
- name: `??1CMPEG2PushClock@@QEAA@XZ`
- size: `337`
- prototype: `void __fastcall(CMPEG2PushClock *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180013168`
- `0x1800156e4`
- `0x180015a0c`

## callees

- `0x180001048`
- `0x180010ea8`
- `0x1800254b8`
- `0x180025570`
- `0x180025710`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800255c9`
- `KERNEL32!WaitForSingleObject` at `0x1800255c9`
- `KERNEL32!SetEvent` at `0x1800255b9`
- `KERNEL32!SetEvent` at `0x1800255b9`
- `KERNEL32!CloseHandle` at `0x1800255d6`
- `KERNEL32!CloseHandle` at `0x1800255fb`
- `KERNEL32!CloseHandle` at `0x1800255d6`
- `KERNEL32!CloseHandle` at `0x1800255fb`
- `KERNEL32!DeleteCriticalSection` at `0x180025682`
- `KERNEL32!DeleteCriticalSection` at `0x18002568f`
- `KERNEL32!DeleteCriticalSection` at `0x1800256a8`
- `KERNEL32!DeleteCriticalSection` at `0x180025682`
- `KERNEL32!DeleteCriticalSection` at `0x18002568f`
- `KERNEL32!DeleteCriticalSection` at `0x1800256a8`
- `WINMM!timeEndPeriod` at `0x1800255e6`
- `WINMM!timeEndPeriod` at `0x1800255e6`

## pseudocode

```c
void __fastcall CMPEG2PushClock::~CMPEG2PushClock(CMPEG2PushClock *this)
{
  bool v1; // zf
  UINT v3; // ecx
  __int64 v4; // rdi
  void *v5; // rcx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  volatile signed __int32 *v8; // rdi

  v1 = *((_QWORD *)this + 37) == 0;
  *(_QWORD *)this = &CMPEG2PushClock::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 1) = &CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'};
  *((_QWORD *)this + 2) = &CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'};
  *((_QWORD *)this + 3) = &CMPEG2PushClock::`vftable'{for `CIPTSConvert'};
  if ( !v1 )
  {
    SetEvent(*((HANDLE *)this + 38));
    WaitForSingleObject(*((HANDLE *)this + 37), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 37));
    v3 = *((_DWORD *)this + 114);
    if ( v3 )
      timeEndPeriod(v3);
  }
  v4 = 0;
  do
  {
    v5 = (void *)*((_QWORD *)this + v4 + 38);
    if ( !v5 )
      break;
    CloseHandle(v5);
    v4 = (unsigned int)(v4 + 1);
  }
  while ( (unsigned int)v4 < 2 );
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 34);
    if ( !v6 )
      break;
    *((_QWORD *)this + 34) = *v6;
    operator delete(v6, 0x20u);
  }
  while ( 1 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 33);
    if ( !v7 )
      break;
    *((_QWORD *)this + 33) = *v7;
    operator delete(v7, 0x20u);
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 35);
  if ( _InterlockedExchangeAdd(v8 + 10, 0xFFFFFFFF) == 1 && v8 )
  {
    CMpeg2Stats::~CMpeg2Stats((CMpeg2Stats *)v8);
    operator delete((void *)v8, 0x2530u);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  CMpeg2Time::~CMpeg2Time((CMPEG2PushClock *)((char *)this + 608));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>((char *)this + 32);
}

```

## disassembly

```asm
0x180025570  mov     [rsp+arg_8], rbx
0x180025575  push    rdi
0x180025576  sub     rsp, 20h
0x18002557a  cmp     qword ptr [rcx+128h], 0
0x180025582  lea     rax, ??_7CMPEG2PushClock@@6BIReferenceClock@@@; const CMPEG2PushClock::`vftable'{for `IReferenceClock'}
0x180025589  mov     [rcx], rax
0x18002558c  mov     rbx, rcx
0x18002558f  lea     rax, ??_7CMPEG2PushClock@@6BCIPCRValueNotify@@@; const CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'}
0x180025596  mov     [rcx+8], rax
0x18002559a  lea     rax, ??_7CMPEG2PushClock@@6B?$CTIGetTime@_J@@@; const CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'}
0x1800255a1  mov     [rcx+10h], rax
0x1800255a5  lea     rax, ??_7CMPEG2PushClock@@6BCIPTSConvert@@@; const CMPEG2PushClock::`vftable'{for `CIPTSConvert'}
0x1800255ac  mov     [rcx+18h], rax
0x1800255b0  jz      short loc_1800255EC
0x1800255b2  mov     rcx, [rcx+130h]; hEvent
0x1800255b9  call    cs:__imp_SetEvent
0x1800255bf  mov     rcx, [rbx+128h]; hHandle
0x1800255c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800255c9  call    cs:__imp_WaitForSingleObject
0x1800255cf  mov     rcx, [rbx+128h]; hObject
0x1800255d6  call    cs:__imp_CloseHandle
0x1800255dc  mov     ecx, [rbx+1C8h]; uPeriod
0x1800255e2  test    ecx, ecx
0x1800255e4  jz      short loc_1800255EC
0x1800255e6  call    cs:__imp_timeEndPeriod
0x1800255ec  xor     edi, edi
0x1800255ee  mov     rcx, [rbx+rdi*8+130h]; hObject
0x1800255f6  test    rcx, rcx
0x1800255f9  jz      short loc_180025608
0x1800255fb  call    cs:__imp_CloseHandle
0x180025601  inc     edi
0x180025603  cmp     edi, 2
0x180025606  jb      short loc_1800255EE
0x180025608  mov     edi, 20h ; ' '
0x18002560d  jmp     short loc_180025621
0x18002560f  mov     rax, [rcx]
0x180025612  mov     rdx, rdi; unsigned __int64
0x180025615  mov     [rbx+110h], rax
0x18002561c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025621  mov     rcx, [rbx+110h]; void *
0x180025628  test    rcx, rcx
0x18002562b  jnz     short loc_18002560F
0x18002562d  jmp     short loc_180025641
0x18002562f  mov     rax, [rcx]
0x180025632  mov     rdx, rdi; unsigned __int64
0x180025635  mov     [rbx+108h], rax
0x18002563c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025641  mov     rcx, [rbx+108h]; void *
0x180025648  test    rcx, rcx
0x18002564b  jnz     short loc_18002562F
0x18002564d  mov     rdi, [rbx+118h]
0x180025654  or      eax, 0FFFFFFFFh
0x180025657  lock xadd [rdi+28h], eax
0x18002565c  cmp     eax, 1
0x18002565f  jnz     short loc_18002567B
0x180025661  test    rdi, rdi
0x180025664  jz      short loc_18002567B
0x180025666  mov     rcx, rdi; this
0x180025669  call    ??1CMpeg2Stats@@QEAA@XZ; CMpeg2Stats::~CMpeg2Stats(void)
0x18002566e  mov     edx, 2530h; unsigned __int64
0x180025673  mov     rcx, rdi; void *
0x180025676  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002567b  lea     rcx, [rbx+140h]; lpCriticalSection
0x180025682  call    cs:__imp_DeleteCriticalSection
0x180025688  lea     rcx, [rbx+168h]; lpCriticalSection
0x18002568f  call    cs:__imp_DeleteCriticalSection
0x180025695  lea     rcx, [rbx+260h]; this
0x18002569c  call    ??1CMpeg2Time@@UEAA@XZ; CMpeg2Time::~CMpeg2Time(void)
0x1800256a1  lea     rcx, [rbx+218h]; lpCriticalSection
0x1800256a8  call    cs:__imp_DeleteCriticalSection
0x1800256ae  lea     rcx, [rbx+20h]
0x1800256b2  mov     rbx, [rsp+28h+arg_8]
0x1800256b7  add     rsp, 20h
0x1800256bb  pop     rdi
0x1800256bc  jmp     ??1?$CTClockSubordinate@_J_J@@QEAA@XZ; CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>(void)
```
