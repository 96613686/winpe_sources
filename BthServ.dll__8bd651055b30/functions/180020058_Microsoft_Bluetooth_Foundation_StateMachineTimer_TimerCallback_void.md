# Microsoft::Bluetooth::Foundation::StateMachineTimer::TimerCallback(void)

- ea: `0x180020058`
- end: `0x180020251`
- name: `?TimerCallback@StateMachineTimer@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `505`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::StateMachineTimer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001e82c`

## callees

- `0x180001790`
- `0x180001cf0`
- `0x180001d58`
- `0x18000a9ec`
- `0x180020058`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800201b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020092`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020092`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18002016a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18002016a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800200ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800201a6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800200ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800201a6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002022e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18002022e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::TimerCallback(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rsi
  char Ptr; // al
  LARGE_INTEGER *v4; // rcx
  LARGE_INTEGER *v5; // r14
  LARGE_INTEGER v6; // rbx
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  PVOID v9; // rcx
  __int64 v10; // rcx
  char v11; // al
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-59h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+28h] [rbp-51h] BYREF
  RTL_SRWLOCK *v14; // [rsp+30h] [rbp-49h]
  _BYTE v15[112]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v16; // [rsp+A8h] [rbp+2Fh]

  v16 = 0;
  v2 = this + 4;
  AcquireSRWLockExclusive(this + 4);
  v14 = v2;
  if ( BYTE1(this[5].Ptr) )
  {
    wistd::function<void (void)>::operator=(v15, &this[6]);
    LOBYTE(this[5].Ptr) = 0;
    Ptr = (char)this[21].Ptr;
    LOBYTE(this[21].Ptr) = 0;
    if ( Ptr )
    {
      v4 = (LARGE_INTEGER *)&this[23];
LABEL_14:
      QueryPerformanceCounter(v4);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  PerformanceCount.QuadPart = 0;
  v5 = (LARGE_INTEGER *)&this[23];
  if ( LOBYTE(this[21].Ptr) )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v6 = PerformanceCount;
  }
  else
  {
    v6 = *v5;
    PerformanceCount = *v5;
  }
  v7 = v6.QuadPart - (unsigned __int64)this[22].Ptr;
  if ( __TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
  {
    Init_thread_header(&__TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA);
    if ( __TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA == -1 )
    {
      pftDueTime = 0;
      QueryPerformanceFrequency((LARGE_INTEGER *)&pftDueTime);
      `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>'::`2'::ticksPerSecond = (__int64)pftDueTime;
      Init_thread_footer(&__TSS0__1____QpcTicksToDuration__JU__ratio__00_0DOI__std___Stopwatch_Foundation_Bluetooth_Microsoft__AEBA_BV__duration__JU__ratio__00_0DOI__std___chrono_std___J_Z_4HA);
    }
  }
  v8 = (__int64)(1000 * v7)
     / `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>'::`2'::ticksPerSecond;
  v9 = this[24].Ptr;
  if ( v8 >= (__int64)v9 )
  {
    wistd::function<void (void)>::operator=(v15, &this[6]);
    LOBYTE(this[5].Ptr) = 0;
    v11 = (char)this[21].Ptr;
    LOBYTE(this[21].Ptr) = 0;
    if ( v11 )
    {
      v4 = (LARGE_INTEGER *)&this[23];
      goto LABEL_14;
    }
LABEL_15:
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v10 = v16;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
      v10 = v16;
    }
    goto LABEL_19;
  }
  pftDueTime = (struct _FILETIME)(-10000 * ((__int64)v9 - v8));
  SetThreadpoolTimerEx(*((PTP_TIMER *)this[3].Ptr + 10), &pftDueTime, 0, 0);
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  v10 = v16;
LABEL_19:
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
}

```

## disassembly

```asm
0x180020058  mov     [rsp-8+arg_8], rbx
0x18002005d  mov     [rsp-8+arg_10], rsi
0x180020062  push    rbp
0x180020063  push    rdi
0x180020064  push    r14
0x180020066  lea     rbp, [rsp-47h]
0x18002006b  sub     rsp, 0C0h
0x180020072  mov     rax, cs:__security_cookie
0x180020079  xor     rax, rsp
0x18002007c  mov     [rbp+57h+var_20], rax
0x180020080  mov     rdi, rcx
0x180020083  mov     [rbp+57h+var_28], 0
0x18002008b  lea     rsi, [rcx+20h]
0x18002008f  mov     rcx, rsi; SRWLock
0x180020092  call    cs:__imp_AcquireSRWLockExclusive
0x180020098  mov     [rbp+57h+var_A0], rsi
0x18002009c  cmp     byte ptr [rdi+29h], 0
0x1800200a0  jz      short loc_1800200CF
0x1800200a2  lea     rdx, [rdi+30h]
0x1800200a6  lea     rcx, [rbp+57h+var_98]
0x1800200aa  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x1800200af  mov     byte ptr [rdi+28h], 0
0x1800200b3  xor     eax, eax
0x1800200b5  xchg    al, [rdi+0A8h]
0x1800200bb  test    al, al
0x1800200bd  jz      loc_1800201AD
0x1800200c3  lea     rcx, [rdi+0B8h]
0x1800200ca  jmp     loc_1800201A6
0x1800200cf  mov     qword ptr [rbp+57h+PerformanceCount], 0
0x1800200d7  mov     al, [rdi+0A8h]
0x1800200dd  nop
0x1800200de  lea     r14, [rdi+0B8h]
0x1800200e5  test    al, al
0x1800200e7  jz      short loc_1800200F9
0x1800200e9  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800200ed  call    cs:__imp_QueryPerformanceCounter
0x1800200f3  mov     rbx, qword ptr [rbp+57h+PerformanceCount]
0x1800200f7  jmp     short loc_180020100
0x1800200f9  mov     rbx, [r14]
0x1800200fc  mov     qword ptr [rbp+57h+PerformanceCount], rbx
0x180020100  sub     rbx, [rdi+0B0h]
0x180020107  mov     ecx, cs:_tls_index
0x18002010d  mov     rax, gs:58h
0x180020116  mov     edx, 4
0x18002011b  mov     rax, [rax+rcx*8]
0x18002011f  mov     ecx, [rdx+rax]
0x180020122  cmp     cs:?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA, ecx
0x180020128  jg      loc_180020209
0x18002012e  imul    rax, rbx, 3E8h
0x180020135  cqo
0x180020137  idiv    cs:?ticksPerSecond@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4_JB; __int64 const `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>(__int64)'::`2'::ticksPerSecond
0x18002013e  mov     rcx, [rdi+0C0h]
0x180020145  cmp     rax, rcx
0x180020148  jge     short loc_180020186
0x18002014a  sub     rcx, rax
0x18002014d  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x180020154  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], rax
0x180020158  mov     rcx, [rdi+18h]
0x18002015c  xor     r9d, r9d; msWindowLength
0x18002015f  xor     r8d, r8d; msPeriod
0x180020162  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x180020166  mov     rcx, [rcx+50h]; pti
0x18002016a  call    cs:__imp_SetThreadpoolTimerEx
0x180020170  nop
0x180020171  test    rsi, rsi
0x180020174  jz      short loc_180020180
0x180020176  mov     rcx, rsi; SRWLock
0x180020179  call    cs:__imp_ReleaseSRWLockExclusive
0x18002017f  nop
0x180020180  mov     rcx, [rbp+57h+var_28]
0x180020184  jmp     short loc_1800201D4
0x180020186  lea     rdx, [rdi+30h]
0x18002018a  lea     rcx, [rbp+57h+var_98]
0x18002018e  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x180020193  mov     byte ptr [rdi+28h], 0
0x180020197  xor     eax, eax
0x180020199  xchg    al, [rdi+0A8h]
0x18002019f  test    al, al
0x1800201a1  jz      short loc_1800201AD
0x1800201a3  mov     rcx, r14; lpPerformanceCount
0x1800201a6  call    cs:__imp_QueryPerformanceCounter
0x1800201ac  nop
0x1800201ad  test    rsi, rsi
0x1800201b0  jz      short loc_1800201BB
0x1800201b2  mov     rcx, rsi; SRWLock
0x1800201b5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800201bb  mov     rcx, [rbp+57h+var_28]
0x1800201bf  test    rcx, rcx
0x1800201c2  jz      short loc_1800201D4
0x1800201c4  mov     rax, [rcx]
0x1800201c7  mov     rax, [rax+20h]
0x1800201cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d0  mov     rcx, [rbp+57h+var_28]
0x1800201d4  test    rcx, rcx
0x1800201d7  jz      short loc_1800201E5
0x1800201d9  mov     rax, [rcx]
0x1800201dc  mov     rax, [rax+18h]
0x1800201e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201e5  mov     rcx, [rbp+57h+var_20]
0x1800201e9  xor     rcx, rsp; StackCookie
0x1800201ec  call    __security_check_cookie
0x1800201f1  lea     r11, [rsp+0D0h+var_10]
0x1800201f9  mov     rbx, [r11+28h]
0x1800201fd  mov     rsi, [r11+30h]
0x180020201  mov     rsp, r11
0x180020204  pop     r14
0x180020206  pop     rdi
0x180020207  pop     rbp
0x180020208  retn
0x180020209  lea     rcx, ?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA
0x180020210  call    _Init_thread_header
0x180020215  cmp     cs:?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA, 0FFFFFFFFh
0x18002021c  jnz     loc_18002012E
0x180020222  mov     qword ptr [rbp+57h+pftDueTime.dwLowDateTime], 0
0x18002022a  lea     rcx, [rbp+57h+pftDueTime]; lpFrequency
0x18002022e  call    cs:__imp_QueryPerformanceFrequency
0x180020234  mov     rax, qword ptr [rbp+57h+pftDueTime.dwLowDateTime]
0x180020238  mov     cs:?ticksPerSecond@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4_JB, rax; __int64 const `Microsoft::Bluetooth::Foundation::Stopwatch::QpcTicksToDuration<__int64,std::ratio<1,1000>>(__int64)'::`2'::ticksPerSecond
0x18002023f  lea     rcx, ?$TSS0@?1???$QpcTicksToDuration@_JU?$ratio@$00$0DOI@@std@@@Stopwatch@Foundation@Bluetooth@Microsoft@@AEBA?BV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@_J@Z@4HA
0x180020246  call    _Init_thread_footer
0x18002024b  jmp     loc_18002012E
```
