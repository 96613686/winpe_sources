# CMPEG2PushClock::CMPEG2PushClock(int,HKEY__ *,CMpeg2Stats *,CMPEG2Demultiplexer *,ulong,ulong,ulong,ulong,ulong,long *)

- ea: `0x18002506c`
- end: `0x1800254af`
- name: `??0CMPEG2PushClock@@QEAA@HPEAUHKEY__@@PEAVCMpeg2Stats@@PEAVCMPEG2Demultiplexer@@KKKKKPEAJ@Z`
- size: `1091`
- prototype: `CMPEG2PushClock *(CMPEG2PushClock *__hidden this, int, HKEY, struct CMpeg2Stats *, struct CMPEG2Demultiplexer *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800156e4`
- `0x180015a0c`

## callees

- `0x18001991c`
- `0x18002506c`
- `0x180026100`
- `0x1800270f0`
- `0x18002717c`
- `0x180027340`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025487`
- `KERNEL32!GetLastError` at `0x180025487`
- `KERNEL32!CreateEventW` at `0x18002538d`
- `KERNEL32!CreateEventW` at `0x18002538d`
- `KERNEL32!InitializeCriticalSection` at `0x180025158`
- `KERNEL32!InitializeCriticalSection` at `0x1800252bb`
- `KERNEL32!InitializeCriticalSection` at `0x180025365`
- `KERNEL32!InitializeCriticalSection` at `0x180025372`
- `KERNEL32!InitializeCriticalSection` at `0x180025158`
- `KERNEL32!InitializeCriticalSection` at `0x1800252bb`
- `KERNEL32!InitializeCriticalSection` at `0x180025365`
- `KERNEL32!InitializeCriticalSection` at `0x180025372`
- `KERNEL32!LeaveCriticalSection` at `0x1800252f0`
- `KERNEL32!LeaveCriticalSection` at `0x1800252f0`
- `KERNEL32!EnterCriticalSection` at `0x1800252c4`
- `KERNEL32!EnterCriticalSection` at `0x1800252c4`
- `WINMM!timeGetTime` at `0x1800252e1`
- `WINMM!timeGetTime` at `0x1800252e1`

## pseudocode

```c
CMPEG2PushClock *__fastcall CMPEG2PushClock::CMPEG2PushClock(
        CMPEG2PushClock *this,
        int a2,
        HKEY a3,
        struct CMpeg2Stats *a4,
        struct CMPEG2Demultiplexer *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        int *a11)
{
  CMPEG2PushClock *v12; // r15
  char *v16; // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  double v20; // xmm0_8
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int *v25; // rdi
  unsigned int v26; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax

  v12 = (CMPEG2PushClock *)((char *)this + 16);
  *(_QWORD *)this = &CMPEG2PushClock::`vftable'{for `IReferenceClock'};
  *((_QWORD *)this + 1) = &CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'};
  *((_QWORD *)this + 2) = &CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'};
  *((_QWORD *)this + 3) = &CMPEG2PushClock::`vftable'{for `CIPTSConvert'};
  *((_QWORD *)this + 4) = &CTDynQueue<CTClockSubordinate<__int64,__int64>::CLOCK_SUBORDINATE_BRACKET *>::`vftable';
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 30;
  *(_QWORD *)((char *)this + 60) = 0x7FFFFFFF;
  *((_DWORD *)this + 17) = 0;
  v16 = (char *)this + 72;
  *((_QWORD *)this + 17) = 27000000;
  *((_QWORD *)this + 19) = 0x3FF0000000000000LL;
  *((_DWORD *)v16 + 12) = 0;
  *((_QWORD *)v16 + 3) = v16 + 16;
  *((_QWORD *)v16 + 2) = v16 + 16;
  *((_QWORD *)v16 + 5) = v16 + 32;
  *((_QWORD *)v16 + 4) = v16 + 32;
  *((_QWORD *)v16 + 1) = v16;
  v17 = a6;
  *(_QWORD *)v16 = v16;
  *((_DWORD *)this + 40) = v17;
  v18 = a7;
  *((_QWORD *)this + 16) = (unsigned __int64)v12 & -(__int64)(this != 0);
  *((_DWORD *)this + 41) = v18;
  *((_QWORD *)this + 23) = a4;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 23) + 40LL), 1u);
  v19 = a8;
  if ( a8 >= 0x64 )
    v19 = 100;
  v20 = (double)v19;
  v21 = a9;
  if ( a9 <= 0x64 )
    v21 = 100;
  v22 = *((_QWORD *)this + 16);
  *((double *)this + 21) = v20 / 100.0;
  *((double *)this + 22) = (double)v21 / 100.0;
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
  v24 = 330000 * a10;
  *((_QWORD *)this + 18) = v23;
  *((_QWORD *)this + 36) = a5;
  *((_QWORD *)this + 35) = a4;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 52) = 1;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 62) = 2000000;
  *((_QWORD *)this + 64) = 500000;
  *((_DWORD *)this + 100) = a2;
  *((_QWORD *)this + 72) = v24 / 0x36EE80;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 75) = 0x3FE999999999999ALL;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 60) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 63) = -1;
  *((_DWORD *)this + 146) = 0;
  *((_DWORD *)this + 147) = 10;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 146) = timeGetTime();
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  *((_QWORD *)this + 77) = 24300000;
  *((_QWORD *)this + 76) = &CMpeg2Time::`vftable';
  *((_QWORD *)this + 80) = (char *)this + 632;
  *((_QWORD *)this + 79) = (char *)this + 632;
  *((_QWORD *)this + 84) = a4;
  _InterlockedAdd((volatile signed __int32 *)a4 + 10, 1u);
  CMpeg2Time::Reset((CMPEG2PushClock *)((char *)this + 608));
  v25 = a11;
  v26 = 0;
  *((_DWORD *)this + 170) = -1;
  *(_QWORD *)((char *)this + 684) = 1;
  *v25 = 0;
  a7 = 0;
  a6 = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 8);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 9);
  *((_OWORD *)this + 19) = 0;
  while ( 1 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + v26 + 38) = EventW;
    if ( !EventW )
      break;
    if ( ++v26 >= 2 )
    {
      *((_QWORD *)this + 53) = 0;
      *((_QWORD *)this + 51) = -1;
      CTClockSubordinate<__int64,__int64>::Reset((char *)this + 32);
      *((_QWORD *)this + 52) = CMPEG2PushClock::GetFreq(v12);
      RegGetValIfExist(a3, L"OverPadMillis", 0x32u, 1, &a6);
      *((_QWORD *)this + 64) = 10000 * a6;
      RegGetValIfExist(a3, L"MinDownstreamBufferingMillis", 0xC8u, 1, &a7);
      *((_QWORD *)this + 62) = 10000 * a7;
      RegGetValIfExist(a3, L"ClockSubordinateSettlingMillis", 0x2710u, 1, (unsigned int *)this + 172);
      *((_QWORD *)this + 59) = -CMPEG2PushClock::SampleClock(v12);
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 35) + 40LL), 1u);
      return this;
    }
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  *v25 = LastError;
  return this;
}

```

## disassembly

```asm
0x18002506c  push    rbx
0x18002506e  push    rbp
0x18002506f  push    rsi
0x180025070  push    rdi
0x180025071  push    r12
0x180025073  push    r13
0x180025075  push    r14
0x180025077  push    r15
0x180025079  sub     rsp, 38h
0x18002507d  mov     rsi, rcx
0x180025080  lea     r15, [rcx+10h]
0x180025084  lea     rax, ??_7CMPEG2PushClock@@6BIReferenceClock@@@; const CMPEG2PushClock::`vftable'{for `IReferenceClock'}
0x18002508b  mov     ebx, edx
0x18002508d  mov     [rcx], rax
0x180025090  xor     edx, edx
0x180025092  lea     rax, ??_7CMPEG2PushClock@@6BCIPCRValueNotify@@@; const CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'}
0x180025099  mov     r12, 3FF0000000000000h
0x1800250a3  mov     [rcx+8], rax
0x1800250a7  mov     rdi, r9
0x1800250aa  lea     rax, ??_7CMPEG2PushClock@@6B?$CTIGetTime@_J@@@; const CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'}
0x1800250b1  mov     rbp, r8
0x1800250b4  mov     [r15], rax
0x1800250b7  lea     rax, ??_7CMPEG2PushClock@@6BCIPTSConvert@@@; const CMPEG2PushClock::`vftable'{for `CIPTSConvert'}
0x1800250be  mov     [rcx+18h], rax
0x1800250c2  lea     rax, ??_7?$CTDynQueue@PEAUCLOCK_SUBORDINATE_BRACKET@?$CTClockSubordinate@_J_J@@@@6B@; const CTDynQueue<CTClockSubordinate<__int64,__int64>::CLOCK_SUBORDINATE_BRACKET *>::`vftable'
0x1800250c9  mov     [rcx+20h], rax
0x1800250cd  mov     [rcx+28h], rdx
0x1800250d1  mov     [rcx+30h], rdx
0x1800250d5  mov     dword ptr [rcx+38h], 1Eh
0x1800250dc  mov     qword ptr [rcx+3Ch], 7FFFFFFFh
0x1800250e4  mov     [rcx+44h], edx
0x1800250e7  add     rcx, 48h ; 'H'
0x1800250eb  mov     qword ptr [rsi+88h], 19BFCC0h
0x1800250f6  mov     [rsi+98h], r12
0x1800250fd  lea     rax, [rcx+10h]
0x180025101  mov     [rcx+30h], edx
0x180025104  mov     [rcx+18h], rax
0x180025108  mov     [rax], rax
0x18002510b  lea     rax, [rcx+20h]
0x18002510f  mov     [rcx+28h], rax
0x180025113  mov     [rax], rax
0x180025116  mov     rax, rsi
0x180025119  mov     [rcx+8], rcx
0x18002511d  neg     rax
0x180025120  mov     eax, [rsp+78h+arg_28]
0x180025127  mov     [rcx], rcx
0x18002512a  sbb     rcx, rcx
0x18002512d  and     rcx, r15
0x180025130  mov     [rsi+0A0h], eax
0x180025136  mov     eax, [rsp+78h+arg_30]
0x18002513d  mov     [rsi+80h], rcx
0x180025144  lea     rcx, [rsi+0C0h]; lpCriticalSection
0x18002514b  mov     [rsi+0A4h], eax
0x180025151  mov     [rsi+0B8h], r9
0x180025158  call    cs:__imp_InitializeCriticalSection
0x18002515e  mov     rax, [rsi+0B8h]
0x180025165  mov     r13d, 1
0x18002516b  lock add [rax+28h], r13d
0x180025170  mov     eax, [rsp+78h+arg_38]
0x180025177  lea     ecx, [r13+63h]
0x18002517b  cmp     eax, ecx
0x18002517d  xorps   xmm0, xmm0
0x180025180  cmovnb  eax, ecx
0x180025183  cvtsi2sd xmm0, rax
0x180025188  mov     eax, [rsp+78h+arg_40]
0x18002518f  cmp     eax, ecx
0x180025191  cmovbe  eax, ecx
0x180025194  mov     rcx, [rsi+80h]
0x18002519b  divsd   xmm0, cs:__real@4059000000000000
0x1800251a3  movsd   qword ptr [rsi+0A8h], xmm0
0x1800251ab  xorps   xmm0, xmm0
0x1800251ae  cvtsi2sd xmm0, rax
0x1800251b3  divsd   xmm0, cs:__real@4059000000000000
0x1800251bb  movsd   qword ptr [rsi+0B0h], xmm0
0x1800251c3  mov     rax, [rcx]
0x1800251c6  mov     rax, [rax+8]
0x1800251ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251cf  imul    ecx, [rsp+78h+arg_48], 50910h
0x1800251da  xor     r8d, r8d
0x1800251dd  mov     [rsi+90h], rax
0x1800251e4  mov     rax, [rsp+78h+arg_20]
0x1800251ec  mov     [rsi+120h], rax
0x1800251f3  mov     eax, 95217CB1h
0x1800251f8  mov     [rsi+118h], rdi
0x1800251ff  mul     ecx
0x180025201  mov     [rsi+198h], r8
0x180025208  mov     [rsi+1A0h], r13
0x18002520f  mov     [rsi+1A8h], r8
0x180025216  mov     qword ptr [rsi+1F0h], 1E8480h
0x180025221  mov     qword ptr [rsi+200h], 7A120h
0x18002522c  shr     edx, 15h
0x18002522f  mov     eax, edx
0x180025231  mov     [rsi+190h], ebx
0x180025237  lea     rbx, [rsi+218h]
0x18002523e  mov     [rsi+240h], rax
0x180025245  mov     rcx, rbx; lpCriticalSection
0x180025248  mov     rax, 3FE999999999999Ah
0x180025252  mov     [rsi+100h], r8
0x180025259  mov     [rsi+258h], rax
0x180025260  mov     [rsi+108h], r8
0x180025267  mov     [rsi+110h], r8
0x18002526e  mov     [rsi+128h], r8
0x180025275  mov     [rsi+1B0h], r8
0x18002527c  mov     [rsi+1B8h], r8
0x180025283  mov     [rsi+1C0h], r8
0x18002528a  mov     [rsi+1C8h], r8d
0x180025291  mov     [rsi+1D0h], r8
0x180025298  mov     [rsi+1E0h], r12
0x18002529f  mov     qword ptr [rsi+1F8h], 0FFFFFFFFFFFFFFFFh
0x1800252aa  mov     [rsi+248h], r8d
0x1800252b1  mov     dword ptr [rsi+24Ch], 0Ah
0x1800252bb  call    cs:__imp_InitializeCriticalSection
0x1800252c1  mov     rcx, rbx; lpCriticalSection
0x1800252c4  call    cs:__imp_EnterCriticalSection
0x1800252ca  xor     eax, eax
0x1800252cc  mov     [rsi+208h], rax
0x1800252d3  mov     [rsi+210h], rax
0x1800252da  mov     [rsi+250h], rax
0x1800252e1  call    cs:__imp_timeGetTime
0x1800252e7  mov     rcx, rbx; lpCriticalSection
0x1800252ea  mov     [rsi+248h], eax
0x1800252f0  call    cs:__imp_LeaveCriticalSection
0x1800252f6  lea     rcx, [rsi+260h]; this
0x1800252fd  lea     rax, ??_7CMpeg2Time@@6B@; const CMpeg2Time::`vftable'
0x180025304  mov     qword ptr [rcx+8], 172C9E0h
0x18002530c  mov     [rcx], rax
0x18002530f  lea     rax, [rcx+18h]
0x180025313  mov     [rcx+20h], rax
0x180025317  mov     [rax], rax
0x18002531a  mov     [rcx+40h], rdi
0x18002531e  lock add [rdi+28h], r13d
0x180025323  call    ?Reset@CMpeg2Time@@QEAAXXZ; CMpeg2Time::Reset(void)
0x180025328  mov     rdi, [rsp+78h+arg_50]
0x180025330  lea     r12, [rsi+2B0h]
0x180025337  xor     ebx, ebx
0x180025339  mov     dword ptr [rsi+2A8h], 0FFFFFFFFh
0x180025343  lea     rcx, [rsi+140h]; lpCriticalSection
0x18002534a  mov     [rsi+2ACh], r13d
0x180025351  mov     [r12], ebx
0x180025355  mov     [rdi], ebx
0x180025357  mov     [rsp+78h+arg_30], ebx
0x18002535e  mov     [rsp+78h+arg_28], ebx
0x180025365  call    cs:__imp_InitializeCriticalSection
0x18002536b  lea     rcx, [rsi+168h]; lpCriticalSection
0x180025372  call    cs:__imp_InitializeCriticalSection
0x180025378  xorps   xmm0, xmm0
0x18002537b  movups  xmmword ptr [rsi+130h], xmm0
0x180025382  xor     r9d, r9d; lpName
0x180025385  xor     r8d, r8d; bInitialState
0x180025388  mov     edx, r13d; bManualReset
0x18002538b  xor     ecx, ecx; lpEventAttributes
0x18002538d  call    cs:__imp_CreateEventW
0x180025393  mov     edx, ebx
0x180025395  mov     [rsi+rdx*8+130h], rax
0x18002539d  test    rax, rax
0x1800253a0  jz      loc_180025487
0x1800253a6  add     ebx, r13d
0x1800253a9  cmp     ebx, 2
0x1800253ac  jb      short loc_180025382
0x1800253ae  lea     rcx, [rsi+20h]
0x1800253b2  mov     qword ptr [rsi+1A8h], 0
0x1800253bd  mov     qword ptr [rsi+198h], 0FFFFFFFFFFFFFFFFh
0x1800253c8  call    ?Reset@?$CTClockSubordinate@_J_J@@QEAAXH@Z; CTClockSubordinate<__int64,__int64>::Reset(int)
0x1800253cd  mov     rcx, r15; this
0x1800253d0  call    ?GetFreq@CMPEG2PushClock@@UEAA_JXZ; CMPEG2PushClock::GetFreq(void)
0x1800253d5  mov     [rsi+1A0h], rax
0x1800253dc  lea     rdx, aOverpadmillis; "OverPadMillis"
0x1800253e3  lea     rax, [rsp+78h+arg_28]
0x1800253eb  mov     r9d, r13d; int
0x1800253ee  mov     r8d, 32h ; '2'; unsigned int
0x1800253f4  mov     [rsp+78h+var_58], rax; unsigned int *
0x1800253f9  mov     rcx, rbp; hKey
0x1800253fc  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180025401  imul    ecx, [rsp+78h+arg_28], 2710h
0x18002540c  lea     rax, [rsp+78h+arg_30]
0x180025414  mov     r9d, r13d; int
0x180025417  mov     [rsp+78h+var_58], rax; unsigned int *
0x18002541c  mov     r8d, 0C8h; unsigned int
0x180025422  lea     rdx, aMindownstreamb; "MinDownstreamBufferingMillis"
0x180025429  mov     [rsi+200h], rcx
0x180025430  mov     rcx, rbp; hKey
0x180025433  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180025438  imul    edx, [rsp+78h+arg_30], 2710h
0x180025443  mov     r9d, r13d; int
0x180025446  mov     r8d, 2710h; unsigned int
0x18002544c  mov     [rsp+78h+var_58], r12; unsigned int *
0x180025451  mov     rcx, rbp; hKey
0x180025454  mov     [rsi+1F0h], rdx
0x18002545b  lea     rdx, aClocksubordina_2; "ClockSubordinateSettlingMillis"
0x180025462  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180025467  mov     rcx, r15; this
0x18002546a  call    ?SampleClock@CMPEG2PushClock@@UEAA_JXZ; CMPEG2PushClock::SampleClock(void)
0x18002546f  neg     rax
0x180025472  mov     [rsi+1D8h], rax
0x180025479  mov     rax, [rsi+118h]
0x180025480  lock add [rax+28h], r13d
0x180025485  jmp     short loc_18002549B
0x180025487  call    cs:__imp_GetLastError
0x18002548d  test    eax, eax
0x18002548f  jle     short loc_180025499
0x180025491  movzx   eax, ax
0x180025494  or      eax, 80070000h
0x180025499  mov     [rdi], eax
0x18002549b  mov     rax, rsi
0x18002549e  add     rsp, 38h
0x1800254a2  pop     r15
0x1800254a4  pop     r14
0x1800254a6  pop     r13
0x1800254a8  pop     r12
0x1800254aa  pop     rdi
0x1800254ab  pop     rsi
0x1800254ac  pop     rbp
0x1800254ad  pop     rbx
0x1800254ae  retn
```
