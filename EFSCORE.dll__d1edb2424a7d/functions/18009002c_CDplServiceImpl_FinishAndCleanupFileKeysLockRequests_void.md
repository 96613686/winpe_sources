# CDplServiceImpl::FinishAndCleanupFileKeysLockRequests(void)

- ea: `0x18009002c`
- end: `0x1800901d4`
- name: `?FinishAndCleanupFileKeysLockRequests@CDplServiceImpl@@AEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(CDplServiceImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180087f70`

## callees

- `0x1800637e8`
- `0x18009002c`
- `0x1800948e4`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009007d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009007d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800901a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180090120`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800901a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009009b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009009b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800900ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800900ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800900ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800900ad`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::FinishAndCleanupFileKeysLockRequests(CDplServiceImpl *this)
{
  struct _TP_TIMER *v2; // rcx
  void ****v3; // rcx
  void ***v4; // rax
  void **v5; // rdx
  void ****v6; // rdx
  int v7; // ecx
  void *v8; // rbx
  __int64 v9; // rax
  void *v11[2]; // [rsp+30h] [rbp-18h] BYREF

  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 71);
  v11[1] = v11;
  v11[0] = v11;
  AcquireSRWLockExclusive((PSRWLOCK)this + 35);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 31);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 31), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 31));
    v3 = (void ****)((char *)this + 264);
    *((_QWORD *)this + 31) = 0;
    while ( 1 )
    {
      v4 = *v3;
      if ( *v3 == (void ***)v3 )
        break;
      if ( v4[1] != (void **)v3
        || (v5 = *v4, (*v4)[1] != v4)
        || (*v3 = (void ***)v5, v5[1] = v3, v6 = (void ****)v11[1], *(void ***)v11[1] != v11) )
      {
LABEL_15:
        __fastfail(3u);
      }
      v4[1] = (void **)v11[1];
      *v4 = v11;
      *v6 = v4;
      v11[1] = v4;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
    while ( 1 )
    {
      v8 = v11[0];
      if ( v11[0] == v11 )
        break;
      if ( *((void ***)v11[0] + 1) != v11 )
        goto LABEL_15;
      v9 = *(_QWORD *)v11[0];
      if ( *(void **)(*(_QWORD *)v11[0] + 8LL) != v11[0] )
        goto LABEL_15;
      v11[0] = *(void **)v11[0];
      *(_QWORD *)(v9 + 8) = v11;
      CDplServiceImpl::LockUnlockFileKeys(
        this,
        1,
        *((const unsigned __int8 **)v8 + 2),
        *((_DWORD *)v8 + 6),
        *((_QWORD *)v8 + 4),
        *((_QWORD *)v8 + 5));
      if ( *((_QWORD *)v8 + 2) )
        DplibMemFree(*((void **)v8 + 2));
      *((_QWORD *)v8 + 2) = 0;
      DplibMemFree(v8);
    }
  }
  else
  {
    ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
  }
  fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_LEAVE_EVENT, (unsigned int)&sourceString, 37, 137);
  return 0;
}

```

## disassembly

```asm
0x18009002c  push    rbp
0x18009002e  push    rbx
0x18009002f  push    rsi
0x180090030  push    rdi
0x180090031  mov     rbp, rsp
0x180090034  sub     rsp, 48h
0x180090038  xorps   xmm0, xmm0
0x18009003b  mov     dword ptr [rsp+48h+var_28], 2247h
0x180090043  mov     r9d, 25h ; '%'
0x180090049  lea     r8, sourceString
0x180090050  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180090057  mov     rsi, rcx
0x18009005a  movups  xmmword ptr [rbp+var_18], xmm0
0x18009005e  call    fnEfsLogTrace1Strings
0x180090063  lea     rax, [rbp+var_18]
0x180090067  mov     [rbp+var_18+8], rax
0x18009006b  lea     rbx, [rsi+118h]
0x180090072  lea     rax, [rbp+var_18]
0x180090076  mov     rcx, rbx; SRWLock
0x180090079  mov     [rbp+var_18], rax
0x18009007d  call    cs:__imp_AcquireSRWLockExclusive
0x180090083  mov     rcx, [rsi+0F8h]; pti
0x18009008a  test    rcx, rcx
0x18009008d  jz      loc_18009019F
0x180090093  xor     r9d, r9d; msWindowLength
0x180090096  xor     r8d, r8d; msPeriod
0x180090099  xor     edx, edx; pftDueTime
0x18009009b  call    cs:__imp_SetThreadpoolTimer
0x1800900a1  mov     rcx, [rsi+0F8h]; pti
0x1800900a8  mov     edx, 1; fCancelPendingCallbacks
0x1800900ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800900b3  mov     rcx, [rsi+0F8h]; pti
0x1800900ba  call    cs:__imp_CloseThreadpoolTimer
0x1800900c0  lea     rcx, [rsi+108h]
0x1800900c7  mov     qword ptr [rsi+0F8h], 0
0x1800900d2  mov     rax, [rcx]
0x1800900d5  cmp     rax, rcx
0x1800900d8  jz      short loc_18009011D
0x1800900da  cmp     [rax+8], rcx
0x1800900de  jnz     loc_180090198
0x1800900e4  mov     rdx, [rax]
0x1800900e7  cmp     [rdx+8], rax
0x1800900eb  jnz     loc_180090198
0x1800900f1  mov     [rcx], rdx
0x1800900f4  lea     r8, [rbp+var_18]
0x1800900f8  mov     [rdx+8], rcx
0x1800900fc  mov     rdx, [rbp+var_18+8]
0x180090100  cmp     [rdx], r8
0x180090103  jnz     loc_180090198
0x180090109  mov     [rax+8], rdx
0x18009010d  lea     r8, [rbp+var_18]
0x180090111  mov     [rax], r8
0x180090114  mov     [rdx], rax
0x180090117  mov     [rbp+var_18+8], rax
0x18009011b  jmp     short loc_1800900D2
0x18009011d  mov     rcx, rbx; SRWLock
0x180090120  call    cs:__imp_ReleaseSRWLockExclusive
0x180090126  mov     rbx, [rbp+var_18]
0x18009012a  lea     rax, [rbp+var_18]
0x18009012e  cmp     rbx, rax
0x180090131  jz      short loc_1800901A8
0x180090133  lea     rax, [rbp+var_18]
0x180090137  cmp     [rbx+8], rax
0x18009013b  jnz     short loc_180090198
0x18009013d  mov     rax, [rbx]
0x180090140  cmp     [rax+8], rbx
0x180090144  jnz     short loc_180090198
0x180090146  mov     [rbp+var_18], rax
0x18009014a  lea     rcx, [rbp+var_18]
0x18009014e  mov     [rax+8], rcx
0x180090152  lea     rdi, [rbx+10h]
0x180090156  mov     rax, [rbx+28h]
0x18009015a  mov     edx, 1; int
0x18009015f  mov     r9d, [rbx+18h]; unsigned int
0x180090163  mov     rcx, rsi; this
0x180090166  mov     r8, [rdi]; unsigned __int8 *
0x180090169  mov     [rsp+48h+var_20], rax; unsigned __int64
0x18009016e  mov     rax, [rbx+20h]
0x180090172  mov     [rsp+48h+var_28], rax; unsigned __int64
0x180090177  call    ?LockUnlockFileKeys@CDplServiceImpl@@AEAAXHPEBEK_K1@Z; CDplServiceImpl::LockUnlockFileKeys(int,uchar const *,ulong,unsigned __int64,unsigned __int64)
0x18009017c  mov     rcx, [rdi]; void *
0x18009017f  test    rcx, rcx
0x180090182  jz      short loc_180090189
0x180090184  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180090189  xor     eax, eax
0x18009018b  mov     rcx, rbx; void *
0x18009018e  mov     [rdi], rax
0x180090191  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180090196  jmp     short loc_180090126
0x180090198  mov     ecx, 3
0x18009019d  int     29h; Win8: RtlFailFast(ecx)
0x18009019f  mov     rcx, rbx; SRWLock
0x1800901a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800901a8  mov     r9d, 25h ; '%'
0x1800901ae  mov     dword ptr [rsp+48h+var_28], 2289h
0x1800901b6  lea     r8, sourceString
0x1800901bd  lea     rdx, EFS_TRACE_LEAVE_EVENT
0x1800901c4  call    fnEfsLogTrace1Strings
0x1800901c9  xor     eax, eax
0x1800901cb  add     rsp, 48h
0x1800901cf  pop     rdi
0x1800901d0  pop     rsi
0x1800901d1  pop     rbx
0x1800901d2  pop     rbp
0x1800901d3  retn
```
