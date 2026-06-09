# CMPEG2PushClock::~CMPEG2PushClock(void)

- ea: `0x180021698`
- end: `0x180021850`
- name: `??1CMPEG2PushClock@@QEAA@XZ`
- size: `440`
- prototype: `void __fastcall(CMPEG2PushClock *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002166c`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180021698`
- `0x180021d84`
- `0x18002d514`
- `0x1800511bc`
- `0x180073d4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021739`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021739`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021723`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021723`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021831`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217e7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800217fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002174c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002177d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002174c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002177d`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180021762`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180021762`

## pseudocode

```c
void __fastcall CMPEG2PushClock::~CMPEG2PushClock(CMPEG2PushClock *this)
{
  UINT v2; // ecx
  __int64 v3; // rdi
  void *v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rcx
  CMpeg2Stats *v7; // rcx
  char v8; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CMPEG2PushClock::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 1) = &CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'};
  *((_QWORD *)this + 2) = &CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'};
  *((_QWORD *)this + 3) = &CMPEG2PushClock::`vftable'{for `CIPTSConvert'};
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v8, "CMPEG2PushClock::~CMPEG2PushClock", 1016);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 23, &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids, this);
  if ( *((_QWORD *)this + 37) )
  {
    SetEvent(*((HANDLE *)this + 38));
    WaitForSingleObject(*((HANDLE *)this + 37), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 37));
    v2 = *((_DWORD *)this + 114);
    if ( v2 )
      timeEndPeriod(v2);
  }
  v3 = 0;
  do
  {
    v4 = (void *)*((_QWORD *)this + v3 + 38);
    if ( !v4 )
      break;
    CloseHandle(v4);
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < 2 );
  while ( 1 )
  {
    v5 = (_QWORD *)*((_QWORD *)this + 34);
    if ( !v5 )
      break;
    *((_QWORD *)this + 34) = *v5;
    operator delete(v5);
  }
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 33);
    if ( !v6 )
      break;
    *((_QWORD *)this + 33) = *v6;
    operator delete(v6);
  }
  CMpeg2Stats::Release(*((CMpeg2Stats **)this + 35));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v8);
  v7 = (CMpeg2Stats *)*((_QWORD *)this + 86);
  *((_QWORD *)this + 78) = &CMpeg2Time::`vftable';
  CMpeg2Stats::Release(v7);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 552));
  CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>((char *)this + 32);
}

```

## disassembly

```asm
0x180021698  mov     [rsp+arg_8], rbx
0x18002169d  push    rdi
0x18002169e  sub     rsp, 20h
0x1800216a2  lea     rax, ??_7CMPEG2PushClock@@6BIReferenceClock@@@; const CMPEG2PushClock::`vftable'{for `IReferenceClock'}
0x1800216a9  mov     rbx, rcx
0x1800216ac  mov     [rcx], rax
0x1800216af  lea     rdx, aCmpeg2pushcloc_7; "CMPEG2PushClock::~CMPEG2PushClock"
0x1800216b6  lea     rax, ??_7CMPEG2PushClock@@6BCIPCRValueNotify@@@; const CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'}
0x1800216bd  mov     r8d, 3F8h; int
0x1800216c3  mov     [rcx+8], rax
0x1800216c7  lea     rax, ??_7CMPEG2PushClock@@6B?$CTIGetTime@_J@@@; const CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'}
0x1800216ce  mov     [rcx+10h], rax
0x1800216d2  lea     rax, ??_7CMPEG2PushClock@@6BCIPTSConvert@@@; const CMPEG2PushClock::`vftable'{for `CIPTSConvert'}
0x1800216d9  mov     [rcx+18h], rax
0x1800216dd  lea     rcx, [rsp+28h+arg_0]; this
0x1800216e2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800216e7  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800216ee  jb      short loc_180021712
0x1800216f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216f7  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x1800216fe  mov     edx, 17h
0x180021703  mov     r9, rbx
0x180021706  mov     rcx, [rcx+88h]
0x18002170d  call    WPP_SF_q
0x180021712  cmp     qword ptr [rbx+128h], 0
0x18002171a  jz      short loc_18002176E
0x18002171c  mov     rcx, [rbx+130h]; hEvent
0x180021723  call    cs:__imp_SetEvent
0x18002172a  nop     dword ptr [rax+rax+00h]
0x18002172f  mov     rcx, [rbx+128h]; hHandle
0x180021736  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021739  call    cs:__imp_WaitForSingleObject
0x180021740  nop     dword ptr [rax+rax+00h]
0x180021745  mov     rcx, [rbx+128h]; hObject
0x18002174c  call    cs:__imp_CloseHandle
0x180021753  nop     dword ptr [rax+rax+00h]
0x180021758  mov     ecx, [rbx+1C8h]; uPeriod
0x18002175e  test    ecx, ecx
0x180021760  jz      short loc_18002176E
0x180021762  call    cs:__imp_timeEndPeriod
0x180021769  nop     dword ptr [rax+rax+00h]
0x18002176e  xor     edi, edi
0x180021770  mov     rcx, [rbx+rdi*8+130h]; hObject
0x180021778  test    rcx, rcx
0x18002177b  jz      short loc_1800217A6
0x18002177d  call    cs:__imp_CloseHandle
0x180021784  nop     dword ptr [rax+rax+00h]
0x180021789  inc     edi
0x18002178b  cmp     edi, 2
0x18002178e  jb      short loc_180021770
0x180021790  jmp     short loc_1800217A6
0x180021792  mov     rax, [rcx]
0x180021795  mov     edx, 20h ; ' '
0x18002179a  mov     [rbx+110h], rax
0x1800217a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800217a6  mov     rcx, [rbx+110h]; Block
0x1800217ad  test    rcx, rcx
0x1800217b0  jnz     short loc_180021792
0x1800217b2  jmp     short loc_1800217C8
0x1800217b4  mov     rax, [rcx]
0x1800217b7  mov     edx, 20h ; ' '
0x1800217bc  mov     [rbx+108h], rax
0x1800217c3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800217c8  mov     rcx, [rbx+108h]; Block
0x1800217cf  test    rcx, rcx
0x1800217d2  jnz     short loc_1800217B4
0x1800217d4  mov     rcx, [rbx+118h]; this
0x1800217db  call    ?Release@CMpeg2Stats@@QEAAKXZ; CMpeg2Stats::Release(void)
0x1800217e0  lea     rcx, [rbx+140h]; lpCriticalSection
0x1800217e7  call    cs:__imp_DeleteCriticalSection
0x1800217ee  nop     dword ptr [rax+rax+00h]
0x1800217f3  lea     rcx, [rbx+168h]; lpCriticalSection
0x1800217fa  call    cs:__imp_DeleteCriticalSection
0x180021801  nop     dword ptr [rax+rax+00h]
0x180021806  lea     rcx, [rsp+28h+arg_0]; this
0x18002180b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180021810  mov     rcx, [rbx+2B0h]; this
0x180021817  lea     rax, ??_7CMpeg2Time@@6B@; const CMpeg2Time::`vftable'
0x18002181e  mov     [rbx+270h], rax
0x180021825  call    ?Release@CMpeg2Stats@@QEAAKXZ; CMpeg2Stats::Release(void)
0x18002182a  lea     rcx, [rbx+228h]; lpCriticalSection
0x180021831  call    cs:__imp_DeleteCriticalSection
0x180021838  nop     dword ptr [rax+rax+00h]
0x18002183d  lea     rcx, [rbx+20h]
0x180021841  mov     rbx, [rsp+28h+arg_8]
0x180021846  add     rsp, 20h
0x18002184a  pop     rdi
0x18002184b  jmp     ??1?$CTClockSubordinate@_J_J@@QEAA@XZ; CTClockSubordinate<__int64,__int64>::~CTClockSubordinate<__int64,__int64>(void)
```
