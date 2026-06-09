# CMPEG2Demultiplexer::LoadMpeg2Program_(void)

- ea: `0x1800156e4`
- end: `0x180015a05`
- name: `?LoadMpeg2Program_@CMPEG2Demultiplexer@@AEAAJXZ`
- size: `801`
- prototype: `__int64 __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800176e8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180011d44`
- `0x1800156e4`
- `0x18001991c`
- `0x18001a160`
- `0x18001d040`
- `0x18002506c`
- `0x180025570`
- `0x180034010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800159e9`
- `ADVAPI32!RegCloseKey` at `0x1800159e9`
- `ADVAPI32!RegCreateKeyExW` at `0x18001575f`
- `ADVAPI32!RegCreateKeyExW` at `0x18001575f`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::LoadMpeg2Program_(CMPEG2Demultiplexer *this)
{
  HKEY *v1; // r15
  int v3; // esi
  CMPEG2ProgramController *v4; // rdi
  HKEY v5; // rcx
  struct CMpeg2Stats **v6; // rbx
  CMPEG2PushClock *v7; // r10
  CMPEG2PushClock *v8; // rax
  CMPEG2ProgramController *v9; // rax
  CMPEG2ProgramController *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  CMpeg2Stats *v13; // rbx
  int v14; // eax
  void *v15; // rbx
  HKEY v16; // rcx
  unsigned int v18; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+64h] [rbp-14h] BYREF
  unsigned int v20; // [rsp+68h] [rbp-10h] BYREF
  DWORD dwDisposition[3]; // [rsp+6Ch] [rbp-Ch] BYREF
  int v22; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v23; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v24; // [rsp+D0h] [rbp+58h] BYREF
  unsigned int v25; // [rsp+D8h] [rbp+60h] BYREF

  v1 = (HKEY *)((char *)this + 272);
  v22 = 0;
  v3 = 0;
  dwDisposition[0] = 0;
  v23 = 0;
  v4 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v25 = 0;
  v24 = 0;
  if ( RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Program",
         0,
         0,
         0,
         0x2001Fu,
         0,
         (PHKEY)this + 34,
         dwDisposition) )
  {
    *v1 = 0;
  }
  RegGetValIfExist(*v1, L"Clock", 1u, 1, &v23);
  v5 = *v1;
  *((_DWORD *)this + 72) = v23 != 0;
  RegGetValIfExist(v5, L"ClockSubordinateMinSamplingWindowMillis", 0x7D0u, 1, &v20);
  RegGetValIfExist(*v1, L"ClockSubordinateHistoryMillis", 0x3A980u, 1, &v19);
  RegGetValIfExist(*v1, L"ClockSubordinateMinSlavable", 0x5Fu, 1, &v18);
  RegGetValIfExist(*v1, L"ClockSubordinateMaxSlavable", 0x69u, 1, &v25);
  RegGetValIfExist(*v1, L"ShiftMaxGlitchesPerHour", 0x3Cu, 1, &v24);
  v6 = (struct CMpeg2Stats **)((char *)this + 264);
  v7 = (CMPEG2PushClock *)operator new(0x2B8u);
  if ( v7 )
  {
    v8 = CMPEG2PushClock::CMPEG2PushClock(v7, *((_DWORD *)this + 72), *v1, *v6, this, v20, v19, v18, v25, v24, &v22);
    v3 = v22;
  }
  else
  {
    v8 = 0;
  }
  *((_QWORD *)this + 35) = v8;
  if ( !v8 )
    goto LABEL_20;
  if ( v3 < 0 )
    goto LABEL_23;
  v9 = (CMPEG2ProgramController *)operator new(0xF0u);
  if ( !v9 )
    goto LABEL_17;
  v10 = CMPEG2ProgramController::CMPEG2ProgramController(
          v9,
          *v1,
          this,
          *v6,
          *((struct CMPEG2PushClock **)this + 35),
          &v22);
  v3 = v22;
  v4 = v10;
  if ( !v10 )
    goto LABEL_17;
  v11 = *(_QWORD *)v10;
  if ( v22 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(v11 + 40))(v4, 1);
LABEL_17:
    if ( v3 < 0 )
      goto LABEL_23;
    v3 = -2147024882;
    goto LABEL_19;
  }
  v3 = (*(__int64 (__fastcall **)(CMPEG2ProgramController *))(v11 + 48))(v4);
  if ( v3 >= 0 )
    v3 = (*(__int64 (__fastcall **)(CMPEG2ProgramController *))(*(_QWORD *)v4 + 56LL))(v4);
  if ( v3 < 0 )
  {
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
LABEL_19:
    v4 = 0;
    goto LABEL_20;
  }
  v12 = *((_QWORD *)this + 35);
  *((_QWORD *)this + 42) = v4;
  *(_QWORD *)(v12 + 624) = *((_QWORD *)v4 + 17);
  v13 = *v6;
  v14 = StatsEnabled(L"SOFTWARE\\Microsoft\\MPEG2Demultiplexer\\Program");
  CMpeg2Stats::Initialize(v13, v14, 2u);
LABEL_20:
  if ( v3 >= 0 )
    return (unsigned int)v3;
  if ( v4 )
    (*(void (__fastcall **)(CMPEG2ProgramController *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
LABEL_23:
  v15 = (void *)*((_QWORD *)this + 35);
  if ( v15 )
  {
    CMPEG2PushClock::~CMPEG2PushClock(*((CMPEG2PushClock **)this + 35));
    operator delete(v15, 0x2B8u);
  }
  v16 = *v1;
  *((_QWORD *)this + 35) = 0;
  if ( v16 )
  {
    RegCloseKey(v16);
    *v1 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800156e4  push    rbp
0x1800156e6  push    rbx
0x1800156e7  push    rsi
0x1800156e8  push    rdi
0x1800156e9  push    r12
0x1800156eb  push    r13
0x1800156ed  push    r14
0x1800156ef  push    r15
0x1800156f1  mov     rbp, rsp
0x1800156f4  sub     rsp, 78h
0x1800156f8  xor     r12d, r12d
0x1800156fb  lea     r15, [rcx+110h]
0x180015702  lea     rax, [rbp+dwDisposition]
0x180015706  mov     [rbp+arg_0], r12d
0x18001570a  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18001570f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180015716  mov     [rsp+78h+phkResult], r15; phkResult
0x18001571b  mov     r14, rcx
0x18001571e  mov     [rsp+78h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180015723  xor     r9d, r9d; lpClass
0x180015726  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x18001572e  xor     r8d, r8d; Reserved
0x180015731  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180015738  mov     [rsp+78h+dwOptions], r12d; dwOptions
0x18001573d  mov     esi, r12d
0x180015740  mov     [rbp+dwDisposition], r12d
0x180015744  mov     [rbp+arg_8], r12d
0x180015748  mov     edi, r12d
0x18001574b  mov     [rbp+var_10], r12d
0x18001574f  mov     [rbp+var_14], r12d
0x180015753  mov     [rbp+var_18], r12d
0x180015757  mov     [rbp+arg_18], r12d
0x18001575b  mov     [rbp+arg_10], r12d
0x18001575f  call    cs:__imp_RegCreateKeyExW
0x180015765  test    eax, eax
0x180015767  jz      short loc_18001576C
0x180015769  mov     [r15], r12
0x18001576c  mov     rcx, [r15]; hKey
0x18001576f  lea     rax, [rbp+arg_8]
0x180015773  mov     r13d, 1
0x180015779  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x18001577e  mov     r9d, r13d; int
0x180015781  lea     rdx, aClock; "Clock"
0x180015788  mov     r8d, r13d; unsigned int
0x18001578b  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015790  cmp     [rbp+arg_8], r12d
0x180015794  lea     rdx, aClocksubordina_0; "ClockSubordinateMinSamplingWindowMillis"
0x18001579b  mov     rcx, [r15]; hKey
0x18001579e  mov     eax, r12d
0x1800157a1  setnz   al
0x1800157a4  mov     r9d, r13d; int
0x1800157a7  mov     [r14+120h], eax
0x1800157ae  mov     r8d, 7D0h; unsigned int
0x1800157b4  lea     rax, [rbp+var_10]
0x1800157b8  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x1800157bd  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x1800157c2  mov     rcx, [r15]; hKey
0x1800157c5  lea     rax, [rbp+var_14]
0x1800157c9  mov     r9d, r13d; int
0x1800157cc  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x1800157d1  mov     r8d, 3A980h; unsigned int
0x1800157d7  lea     rdx, aClocksubordina; "ClockSubordinateHistoryMillis"
0x1800157de  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x1800157e3  mov     rcx, [r15]; hKey
0x1800157e6  lea     rax, [rbp+var_18]
0x1800157ea  mov     r9d, r13d; int
0x1800157ed  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x1800157f2  lea     r8d, [r13+5Eh]; unsigned int
0x1800157f6  lea     rdx, aClocksubordina_3; "ClockSubordinateMinSlavable"
0x1800157fd  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015802  mov     rcx, [r15]; hKey
0x180015805  lea     rax, [rbp+arg_18]
0x180015809  mov     r9d, r13d; int
0x18001580c  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015811  lea     r8d, [r13+68h]; unsigned int
0x180015815  lea     rdx, aClocksubordina_1; "ClockSubordinateMaxSlavable"
0x18001581c  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015821  mov     rcx, [r15]; hKey
0x180015824  lea     rax, [rbp+arg_10]
0x180015828  mov     r9d, r13d; int
0x18001582b  mov     qword ptr [rsp+78h+dwOptions], rax; unsigned int *
0x180015830  lea     r8d, [r13+3Bh]; unsigned int
0x180015834  lea     rdx, aShiftmaxglitch; "ShiftMaxGlitchesPerHour"
0x18001583b  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180015840  mov     ecx, 2B8h; Size
0x180015845  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001584a  lea     rbx, [r14+108h]
0x180015851  mov     r10, rax
0x180015854  test    rax, rax
0x180015857  jz      short loc_1800158A4
0x180015859  mov     ecx, [rbp+arg_10]
0x18001585c  lea     rax, [rbp+arg_0]
0x180015860  mov     r9, [rbx]; struct CMpeg2Stats *
0x180015863  mov     r8, [r15]; HKEY
0x180015866  mov     edx, [r14+120h]; int
0x18001586d  mov     [rsp+78h+var_28], rax; int *
0x180015872  mov     eax, [rbp+var_10]
0x180015875  mov     [rsp+78h+var_30], ecx; unsigned int
0x180015879  mov     ecx, [rbp+arg_18]
0x18001587c  mov     dword ptr [rsp+78h+lpdwDisposition], ecx; unsigned int
0x180015880  mov     ecx, [rbp+var_18]
0x180015883  mov     dword ptr [rsp+78h+phkResult], ecx; unsigned int
0x180015887  mov     ecx, [rbp+var_14]
0x18001588a  mov     dword ptr [rsp+78h+lpSecurityAttributes], ecx; unsigned int
0x18001588e  mov     rcx, r10; this
0x180015891  mov     [rsp+78h+samDesired], eax; unsigned int
0x180015895  mov     qword ptr [rsp+78h+dwOptions], r14; struct CMPEG2Demultiplexer *
0x18001589a  call    ??0CMPEG2PushClock@@QEAA@HPEAUHKEY__@@PEAVCMpeg2Stats@@PEAVCMPEG2Demultiplexer@@KKKKKPEAJ@Z; CMPEG2PushClock::CMPEG2PushClock(int,HKEY__ *,CMpeg2Stats *,CMPEG2Demultiplexer *,ulong,ulong,ulong,ulong,ulong,long *)
0x18001589f  mov     esi, [rbp+arg_0]
0x1800158a2  jmp     short loc_1800158A7
0x1800158a4  mov     rax, r12
0x1800158a7  mov     [r14+118h], rax
0x1800158ae  test    rax, rax
0x1800158b1  jz      loc_18001599E
0x1800158b7  test    esi, esi
0x1800158b9  js      loc_1800159B9
0x1800158bf  mov     ecx, 0F0h; Size
0x1800158c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800158c9  test    rax, rax
0x1800158cc  jz      loc_180015992
0x1800158d2  mov     r9, [rbx]; struct CMpeg2Stats *
0x1800158d5  lea     rcx, [rbp+arg_0]
0x1800158d9  mov     rdx, [r15]; HKEY
0x1800158dc  mov     r8, r14; struct CMPEG2Demultiplexer *
0x1800158df  mov     qword ptr [rsp+78h+samDesired], rcx; int *
0x1800158e4  mov     rcx, [r14+118h]
0x1800158eb  mov     qword ptr [rsp+78h+dwOptions], rcx; struct CMPEG2PushClock *
0x1800158f0  mov     rcx, rax; this
0x1800158f3  call    ??0CMPEG2ProgramController@@QEAA@PEAUHKEY__@@PEAVCMPEG2Demultiplexer@@PEAVCMpeg2Stats@@PEAVCMPEG2PushClock@@PEAJ@Z; CMPEG2ProgramController::CMPEG2ProgramController(HKEY__ *,CMPEG2Demultiplexer *,CMpeg2Stats *,CMPEG2PushClock *,long *)
0x1800158f8  mov     esi, [rbp+arg_0]
0x1800158fb  mov     rdi, rax
0x1800158fe  test    rax, rax
0x180015901  jz      loc_180015992
0x180015907  mov     rax, [rax]
0x18001590a  mov     rcx, rdi
0x18001590d  test    esi, esi
0x18001590f  js      short loc_180015986
0x180015911  mov     rax, [rax+30h]
0x180015915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001591a  mov     esi, eax
0x18001591c  test    eax, eax
0x18001591e  js      short loc_180015931
0x180015920  mov     rax, [rdi]
0x180015923  mov     rcx, rdi
0x180015926  mov     rax, [rax+38h]
0x18001592a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001592f  mov     esi, eax
0x180015931  test    esi, esi
0x180015933  js      short loc_180015972
0x180015935  mov     rdx, [r14+118h]
0x18001593c  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\MPEG2Demultiplexer"...
0x180015943  mov     [r14+150h], rdi
0x18001594a  mov     rax, [rdi+88h]
0x180015951  mov     [rdx+270h], rax
0x180015958  mov     rbx, [rbx]
0x18001595b  call    ?StatsEnabled@@YAHPEBG@Z; StatsEnabled(ushort const *)
0x180015960  mov     r8d, 2; unsigned int
0x180015966  mov     edx, eax; int
0x180015968  mov     rcx, rbx; this
0x18001596b  call    ?Initialize@CMpeg2Stats@@QEAAJHK@Z; CMpeg2Stats::Initialize(int,ulong)
0x180015970  jmp     short loc_18001599E
0x180015972  mov     rax, [rdi]
0x180015975  mov     edx, r13d
0x180015978  mov     rcx, rdi
0x18001597b  mov     rax, [rax+28h]
0x18001597f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015984  jmp     short loc_18001599B
0x180015986  mov     rax, [rax+28h]
0x18001598a  mov     edx, r13d
0x18001598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015992  test    esi, esi
0x180015994  js      short loc_1800159B9
0x180015996  mov     esi, 8007000Eh
0x18001599b  mov     rdi, r12
0x18001599e  test    esi, esi
0x1800159a0  jns     short loc_1800159F2
0x1800159a2  test    rdi, rdi
0x1800159a5  jz      short loc_1800159B9
0x1800159a7  mov     rax, [rdi]
0x1800159aa  mov     edx, r13d
0x1800159ad  mov     rcx, rdi
0x1800159b0  mov     rax, [rax+28h]
0x1800159b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159b9  mov     rbx, [r14+118h]
0x1800159c0  test    rbx, rbx
0x1800159c3  jz      short loc_1800159DA
0x1800159c5  mov     rcx, rbx; this
0x1800159c8  call    ??1CMPEG2PushClock@@QEAA@XZ; CMPEG2PushClock::~CMPEG2PushClock(void)
0x1800159cd  mov     edx, 2B8h; unsigned __int64
0x1800159d2  mov     rcx, rbx; void *
0x1800159d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800159da  mov     rcx, [r15]; hKey
0x1800159dd  mov     [r14+118h], r12
0x1800159e4  test    rcx, rcx
0x1800159e7  jz      short loc_1800159F2
0x1800159e9  call    cs:__imp_RegCloseKey
0x1800159ef  mov     [r15], r12
0x1800159f2  mov     eax, esi
0x1800159f4  add     rsp, 78h
0x1800159f8  pop     r15
0x1800159fa  pop     r14
0x1800159fc  pop     r13
0x1800159fe  pop     r12
0x180015a00  pop     rdi
0x180015a01  pop     rsi
0x180015a02  pop     rbx
0x180015a03  pop     rbp
0x180015a04  retn
```
