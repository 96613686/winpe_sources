# AutoLockWithWatchdog::AutoLockWithWatchdog(utl::recursive_mutex *,char const *)

- ea: `0x18001de50`
- end: `0x18001df87`
- name: `??0AutoLockWithWatchdog@@QEAA@PEAVrecursive_mutex@utl@@PEBD@Z`
- size: `311`
- prototype: `AutoLockWithWatchdog *__fastcall(AutoLockWithWatchdog *this, struct _RTL_CRITICAL_SECTION *, const char *)`
- caller_count: `126`
- callee_count: `4`
- tags: ``

## callers

- `0x1800211b0`
- `0x180021a30`
- `0x180021b20`
- `0x1800222c0`
- `0x1800224d0`
- `0x1800225e0`
- `0x180022720`
- `0x1800227c0`
- `0x180022980`
- `0x180022b10`
- `0x180022c90`
- `0x180022ee0`
- `0x180022f70`
- `0x1800233e0`
- `0x180023670`
- `0x180024100`
- `0x180024230`
- `0x180024de0`
- `0x180024ef0`
- `0x180025920`
- `0x180025a10`
- `0x180025b90`
- `0x1800265e0`
- `0x180026770`
- `0x180026910`
- `0x180026d80`
- `0x180026e20`
- `0x1800273e0`
- `0x1800275e0`
- `0x1800276c0`
- `0x180027840`
- `0x180027e70`
- `0x180027f90`
- `0x1800281d0`
- `0x180028290`
- `0x180028500`
- `0x1800285a0`
- `0x180028760`
- `0x180028aa0`
- `0x180028b20`
- `0x180028ca0`
- `0x180028e00`
- `0x180029180`
- `0x180029390`
- `0x180029570`
- `0x180029990`
- `0x180029bc0`
- `0x180029ca0`
- `0x180029d30`
- `0x180029e40`

## callees

- `0x18001de50`
- `0x180025ae4`
- `0x180031f6c`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001deef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001deef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001df2b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001df45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001df45`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001df59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001df59`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001df50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001df50`

## pseudocode

```c
AutoLockWithWatchdog *__fastcall AutoLockWithWatchdog::AutoLockWithWatchdog(
        AutoLockWithWatchdog *this,
        struct _RTL_CRITICAL_SECTION *a2,
        const char *a3)
{
  char *v3; // rbx
  struct _TP_TIMER *v7; // rbx
  unsigned int v9; // [rsp+20h] [rbp-50h]
  unsigned int v10; // [rsp+20h] [rbp-50h]
  _QWORD pv[2]; // [rsp+30h] [rbp-40h] BYREF
  PTP_TIMER pti; // [rsp+40h] [rbp-30h]
  __int64 v13; // [rsp+48h] [rbp-28h]
  HLOCAL hMem; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+58h] [rbp-18h]

  v3 = (char *)this + 8;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 1) = &OperationWatchdog::`vftable';
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = 0;
  *((_QWORD *)this + 1) = &TelemetryOperationWatchdog::`vftable';
  *((_DWORD *)this + 14) = 180000;
  v13 = 0;
  v15 = 0;
  pv[0] = &OperationWatchdog::`vftable';
  pv[1] = 0;
  pti = 0;
  hMem = 0;
  OperationWatchdog::Start(pv, 2u, a3, 0x2710u, v9);
  *(_QWORD *)this = a2;
  EnterCriticalSection(a2);
  OperationWatchdog::End((OperationWatchdog *)pv);
  OperationWatchdog::Start(v3, 1u, a3, 0x2710u, v10);
  pv[0] = &OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)pv);
  if ( hMem )
    LocalFree(hMem);
  v7 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v7, 1);
    CloseThreadpoolTimer(v7);
  }
  return this;
}

```

## disassembly

```asm
0x18001de50  mov     [rsp-28h+arg_8], rbx
0x18001de55  mov     [rsp-28h+arg_18], rsi
0x18001de5a  push    rbp
0x18001de5b  push    rdi
0x18001de5c  push    r12
0x18001de5e  push    r13
0x18001de60  push    r14
0x18001de62  mov     rbp, rsp
0x18001de65  sub     rsp, 70h
0x18001de69  mov     rax, cs:__security_cookie
0x18001de70  xor     rax, rsp
0x18001de73  mov     [rbp+var_10], rax
0x18001de77  xor     r13d, r13d
0x18001de7a  lea     rbx, [rcx+8]
0x18001de7e  mov     [rbx+8], r13
0x18001de82  lea     r12, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x18001de89  mov     [rbx], r12
0x18001de8c  lea     rax, ??_7TelemetryOperationWatchdog@@6B@; const TelemetryOperationWatchdog::`vftable'
0x18001de93  mov     [rbx+10h], r13
0x18001de97  mov     rdi, rdx
0x18001de9a  mov     [rbx+18h], r13d
0x18001de9e  lea     edx, [r13+2]; unsigned int
0x18001dea2  mov     [rbx+20h], r13
0x18001dea6  mov     r14, rcx
0x18001dea9  mov     [rbx+28h], r13d
0x18001dead  lea     rcx, [rbp+pv]; pv
0x18001deb1  mov     [rbx+2Ch], r13d
0x18001deb5  mov     r9d, 2710h; unsigned int
0x18001debb  mov     [rbx], rax
0x18001debe  mov     rsi, r8
0x18001dec1  mov     dword ptr [rbx+30h], 2BF20h
0x18001dec8  mov     [rbp+var_28], r13
0x18001decc  mov     [rbp+var_18], r13
0x18001ded0  mov     [rbp+pv], r12
0x18001ded4  mov     [rbp+var_38], r13
0x18001ded8  mov     [rbp+pti], r13
0x18001dedc  mov     [rbp+hMem], r13
0x18001dee0  mov     dword ptr [rbp+var_18+4], r13d
0x18001dee4  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x18001dee9  mov     rcx, rdi; lpCriticalSection
0x18001deec  mov     [r14], rdi
0x18001deef  call    cs:__imp_EnterCriticalSection
0x18001def5  lea     rcx, [rbp+pv]; this
0x18001def9  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18001defe  lea     edi, [r13+1]
0x18001df02  mov     r9d, 2710h; unsigned int
0x18001df08  mov     edx, edi; unsigned int
0x18001df0a  mov     r8, rsi; char *
0x18001df0d  mov     rcx, rbx; pv
0x18001df10  call    ?Start@OperationWatchdog@@QEAAXIPEBDKK@Z; OperationWatchdog::Start(uint,char const *,ulong,ulong)
0x18001df15  lea     rcx, [rbp+pv]; this
0x18001df19  mov     [rbp+pv], r12
0x18001df1d  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x18001df22  mov     rcx, [rbp+hMem]; hMem
0x18001df26  test    rcx, rcx
0x18001df29  jz      short loc_18001DF31
0x18001df2b  call    cs:__imp_LocalFree
0x18001df31  mov     rbx, [rbp+pti]
0x18001df35  test    rbx, rbx
0x18001df38  jz      short loc_18001DF5F
0x18001df3a  xor     r9d, r9d; msWindowLength
0x18001df3d  xor     r8d, r8d; msPeriod
0x18001df40  xor     edx, edx; pftDueTime
0x18001df42  mov     rcx, rbx; pti
0x18001df45  call    cs:__imp_SetThreadpoolTimer
0x18001df4b  mov     edx, edi; fCancelPendingCallbacks
0x18001df4d  mov     rcx, rbx; pti
0x18001df50  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001df56  mov     rcx, rbx; pti
0x18001df59  call    cs:__imp_CloseThreadpoolTimer
0x18001df5f  mov     rax, r14
0x18001df62  mov     rcx, [rbp+var_10]
0x18001df66  xor     rcx, rsp; StackCookie
0x18001df69  call    __security_check_cookie
0x18001df6e  lea     r11, [rsp+70h+var_s0]
0x18001df73  mov     rbx, [r11+38h]
0x18001df77  mov     rsi, [r11+48h]
0x18001df7b  mov     rsp, r11
0x18001df7e  pop     r14
0x18001df80  pop     r13
0x18001df82  pop     r12
0x18001df84  pop     rdi
0x18001df85  pop     rbp
0x18001df86  retn
```
