# WinSAT::DiskProfiler::DiskProfilerThreadProc(void *)

- ea: `0x140065760`
- end: `0x1400658e6`
- name: `?DiskProfilerThreadProc@DiskProfiler@WinSAT@@CAIPEAX@Z`
- size: `390`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140011d58`
- `0x14003ec14`
- `0x140060888`
- `0x140065760`
- `0x14006be5c`
- `0x14006dea8`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x140065779`
- `KERNEL32!GetThreadPriority` at `0x140065779`
- `KERNEL32!GetCurrentThread` at `0x140065770`
- `KERNEL32!GetCurrentThread` at `0x140065770`
- `KERNEL32!Sleep` at `0x14006586f`
- `KERNEL32!Sleep` at `0x14006586f`
- `msvcrt!time` at `0x1400657ef`
- `msvcrt!time` at `0x1400657ef`

## string_xrefs

- `0x14006578e`: `DiskProfilerThreadProc Launched with priority %d`
- `0x140065823`: `DiskProfilerThreadProc ::Disk Profile could not be completed - ERROR_INTERFERENCE_FROM_DRIVER `

## pseudocode

```c
__int64 __fastcall WinSAT::DiskProfiler::DiskProfilerThreadProc(_DWORD *a1)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  WinSAT::DiskProfiler *v4; // rcx
  unsigned int v5; // edi
  char v6; // r14
  char v7; // bp
  int i; // esi
  int v9; // eax
  WinSAT::DiskProfiler *v10; // rcx

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  Log_Text_F(
    "base\\winsat\\storage\\diskprof.cpp",
    677,
    "DiskProfilerThreadProc Launched with priority %d",
    ThreadPriority);
  if ( !a1 )
  {
    v5 = 87;
LABEL_17:
    WinSAT::DiskProfiler::addInterferenceIntoSQM(v4, a1[108], a1[112], a1[113]);
    return v5;
  }
  v6 = 0;
  v7 = 1;
  v5 = 0;
  for ( i = 1; i <= 3; ++i )
  {
    if ( !v7 )
      break;
    v7 = 0;
    Log_Text_F("base\\winsat\\storage\\diskprof.cpp", 690, "ITERATION NUMBER %d", i);
    if ( i == 3 )
      *((_BYTE *)a1 + 444) = 1;
    if ( !a1[68] )
    {
      v9 = time(0);
      a1[69] = v9;
      Log_Text_F("base\\winsat\\storage\\diskprof.cpp", 698, "Random seed is %u", v9);
    }
    v5 = WinSAT::DiskProfiler::PerformProfile((WinSAT::DiskProfiler *)a1);
    if ( v5 == 33619979 )
    {
      Log_Text_F(
        "base\\winsat\\storage\\diskprof.cpp",
        703,
        "DiskProfilerThreadProc ::Disk Profile could not be completed - ERROR_INTERFERENCE_FROM_DRIVER ");
      v7 = 1;
      v6 = 1;
      WinSAT::DiskProfiler::addInterferenceIntoSQM(v10, a1[108], a1[112], a1[113]);
      Log_Text_F(
        "base\\winsat\\storage\\diskprof.cpp",
        710,
        "Going to sleep for 20 seconds to avoid hitting interference again immediately");
      Sleep(0x4E20u);
    }
  }
  a1[16] = 6 - (v5 != 0);
  a1[50] = v5;
  if ( (unsigned __int64)(*((_QWORD *)a1 + 12) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    mlib::MEvent::Set((mlib::MEvent *)(a1 + 24));
  v4 = (WinSAT::DiskProfiler *)(a1 + 72);
  if ( *((_BYTE *)a1 + 381) )
    WinSAT::StorageDevice::Close(v4);
  if ( !v6 )
    goto LABEL_17;
  return v5;
}

```

## disassembly

```asm
0x140065760  push    rbx
0x140065762  push    rbp
0x140065763  push    rsi
0x140065764  push    rdi
0x140065765  push    r14
0x140065767  push    r15
0x140065769  sub     rsp, 28h
0x14006576d  mov     rbx, rcx
0x140065770  call    cs:__imp_GetCurrentThread
0x140065776  mov     rcx, rax; hThread
0x140065779  call    cs:__imp_GetThreadPriority
0x14006577f  lea     r15, aBaseWinsatStor; "base\\winsat\\storage\\diskprof.cpp"
0x140065786  mov     edx, 2A5h
0x14006578b  mov     r9d, eax
0x14006578e  lea     r8, aDiskprofilerth; "DiskProfilerThreadProc Launched with pr"...
0x140065795  mov     rcx, r15
0x140065798  call    Log_Text_F
0x14006579d  test    rbx, rbx
0x1400657a0  jnz     short loc_1400657AA
0x1400657a2  lea     edi, [rbx+57h]
0x1400657a5  jmp     loc_1400658BE
0x1400657aa  xor     r14b, r14b
0x1400657ad  mov     bpl, 1
0x1400657b0  xor     edi, edi
0x1400657b2  lea     esi, [rdi+1]
0x1400657b5  test    bpl, bpl
0x1400657b8  jz      loc_140065880
0x1400657be  mov     r9d, esi
0x1400657c1  lea     r8, aIterationNumbe; "ITERATION NUMBER %d"
0x1400657c8  mov     edx, 2B2h
0x1400657cd  mov     rcx, r15
0x1400657d0  xor     bpl, bpl
0x1400657d3  call    Log_Text_F
0x1400657d8  cmp     esi, 3
0x1400657db  jnz     short loc_1400657E4
0x1400657dd  mov     byte ptr [rbx+1BCh], 1
0x1400657e4  cmp     dword ptr [rbx+110h], 0
0x1400657eb  jnz     short loc_140065812
0x1400657ed  xor     ecx, ecx; Time
0x1400657ef  call    cs:__imp_time
0x1400657f5  lea     r8, aRandomSeedIsU; "Random seed is %u"
0x1400657fc  mov     edx, 2BAh
0x140065801  mov     r9d, eax
0x140065804  mov     [rbx+114h], eax
0x14006580a  mov     rcx, r15
0x14006580d  call    Log_Text_F
0x140065812  mov     rcx, rbx; this
0x140065815  call    ?PerformProfile@DiskProfiler@WinSAT@@AEAAKXZ; WinSAT::DiskProfiler::PerformProfile(void)
0x14006581a  mov     edi, eax
0x14006581c  cmp     eax, 201000Bh
0x140065821  jnz     short loc_140065875
0x140065823  lea     r8, aDiskprofilerth_0; "DiskProfilerThreadProc ::Disk Profile c"...
0x14006582a  mov     edx, 2BFh
0x14006582f  mov     rcx, r15
0x140065832  call    Log_Text_F
0x140065837  mov     r9d, [rbx+1C4h]; unsigned int
0x14006583e  mov     bpl, 1
0x140065841  mov     r8d, [rbx+1C0h]; unsigned int
0x140065848  mov     r14b, bpl
0x14006584b  mov     edx, [rbx+1B0h]; unsigned int
0x140065851  call    ?addInterferenceIntoSQM@DiskProfiler@WinSAT@@AEAAXIII@Z; WinSAT::DiskProfiler::addInterferenceIntoSQM(uint,uint,uint)
0x140065856  lea     r8, aGoingToSleepFo; "Going to sleep for 20 seconds to avoid "...
0x14006585d  mov     edx, 2C6h
0x140065862  mov     rcx, r15
0x140065865  call    Log_Text_F
0x14006586a  mov     ecx, 4E20h; dwMilliseconds
0x14006586f  call    cs:__imp_Sleep
0x140065875  inc     esi
0x140065877  cmp     esi, 3
0x14006587a  jle     loc_1400657B5
0x140065880  mov     eax, edi
0x140065882  neg     eax
0x140065884  sbb     ecx, ecx
0x140065886  add     ecx, 6
0x140065889  mov     [rbx+40h], ecx
0x14006588c  lea     rcx, [rbx+60h]; this
0x140065890  mov     [rbx+0C8h], edi
0x140065896  mov     rax, [rcx]
0x140065899  dec     rax
0x14006589c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400658a0  ja      short loc_1400658A7
0x1400658a2  call    ?Set@MEvent@mlib@@QEAA_NXZ; mlib::MEvent::Set(void)
0x1400658a7  lea     rcx, [rbx+120h]; this
0x1400658ae  cmp     byte ptr [rcx+5Dh], 0
0x1400658b2  jz      short loc_1400658B9
0x1400658b4  call    ?Close@StorageDevice@WinSAT@@QEAAXXZ; WinSAT::StorageDevice::Close(void)
0x1400658b9  test    r14b, r14b
0x1400658bc  jnz     short loc_1400658D7
0x1400658be  mov     r9d, [rbx+1C4h]; unsigned int
0x1400658c5  mov     r8d, [rbx+1C0h]; unsigned int
0x1400658cc  mov     edx, [rbx+1B0h]; unsigned int
0x1400658d2  call    ?addInterferenceIntoSQM@DiskProfiler@WinSAT@@AEAAXIII@Z; WinSAT::DiskProfiler::addInterferenceIntoSQM(uint,uint,uint)
0x1400658d7  mov     eax, edi
0x1400658d9  add     rsp, 28h
0x1400658dd  pop     r15
0x1400658df  pop     r14
0x1400658e1  pop     rdi
0x1400658e2  pop     rsi
0x1400658e3  pop     rbp
0x1400658e4  pop     rbx
0x1400658e5  retn
```
