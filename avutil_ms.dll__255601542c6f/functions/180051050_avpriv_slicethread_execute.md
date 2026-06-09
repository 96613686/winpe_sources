# avpriv_slicethread_execute

- ea: `0x180051050`
- end: `0x18005119a`
- name: `avpriv_slicethread_execute`
- size: `330`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180042ad0`
- `0x180051050`
- `0x180051290`
- `0x180078c2c`
- `0x18007a900`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800510d7`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1800510d7`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051134`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051134`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800510e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005114a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800510e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005114a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800510c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005111e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800510c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005111e`

## string_xrefs

- `0x180051169`: `C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/slicethread.c`

## pseudocode

```c
void __fastcall avpriv_slicethread_execute(__int64 *a1, int a2, int a3)
{
  bool v5; // cc
  int v6; // eax
  __int64 v7; // r14
  __int64 v8; // rbp
  __int64 v9; // rbx
  RTL_SRWLOCK *v10; // rdi
  void (__fastcall *v11)(__int64); // rax
  signed __int32 v12[8]; // [rsp+0h] [rbp-48h] BYREF

  if ( a2 <= 0 )
  {
    av_log(
      0,
      0,
      "Assertion %s failed at %s:%d\n",
      "nb_jobs > 0",
      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/slicethread.c",
      195);
    abort();
  }
  v5 = a2 <= *((_DWORD *)a1 + 2);
  *((_DWORD *)a1 + 4) = a2;
  if ( !v5 )
    a2 = *((_DWORD *)a1 + 2);
  *((_DWORD *)a1 + 3) = a2;
  a1[3] = 0;
  _InterlockedOr(v12, 0);
  a1[4] = *((int *)a1 + 3);
  _InterlockedOr(v12, 0);
  v6 = *((_DWORD *)a1 + 3);
  if ( !a1[10] || !a3 )
    --v6;
  v7 = v6;
  if ( v6 > 0 )
  {
    v8 = 0;
    do
    {
      v9 = *a1;
      v10 = (RTL_SRWLOCK *)(*a1 + v8);
      AcquireSRWLockExclusive(v10 + 1);
      *(_DWORD *)(v9 + v8 + 32) = 0;
      WakeConditionVariable((PCONDITION_VARIABLE)(v8 + v9 + 16));
      ReleaseSRWLockExclusive(v10 + 1);
      v8 += 40;
      --v7;
    }
    while ( v7 );
  }
  v11 = (void (__fastcall *)(__int64))a1[10];
  if ( v11 && a3 )
  {
    v11(a1[8]);
  }
  else if ( (unsigned int)sub_180051290(a1) )
  {
    return;
  }
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 5);
  while ( !*((_DWORD *)a1 + 14) )
    SleepConditionVariableSRW((PCONDITION_VARIABLE)a1 + 6, (PSRWLOCK)a1 + 5, 0xFFFFFFFF, 0);
  *((_DWORD *)a1 + 14) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)a1 + 5);
}

```

## disassembly

```asm
0x180051050  mov     [rsp+arg_0], rbx
0x180051055  mov     [rsp+arg_8], rbp
0x18005105a  mov     [rsp+arg_10], rsi
0x18005105f  push    rdi
0x180051060  push    r14
0x180051062  push    r15
0x180051064  sub     rsp, 30h
0x180051068  mov     r15d, r8d
0x18005106b  mov     rsi, rcx
0x18005106e  test    edx, edx
0x180051070  jle     loc_180051169
0x180051076  cmp     edx, [rcx+8]
0x180051079  mov     [rcx+10h], edx
0x18005107c  cmovg   edx, [rcx+8]
0x180051080  mov     [rcx+0Ch], edx
0x180051083  mov     qword ptr [rcx+18h], 0
0x18005108b  lock or [rsp+48h+var_48], 0
0x180051090  movsxd  rax, dword ptr [rcx+0Ch]
0x180051094  mov     [rcx+20h], rax
0x180051098  lock or [rsp+48h+var_48], 0
0x18005109d  cmp     qword ptr [rcx+50h], 0
0x1800510a2  mov     eax, [rcx+0Ch]
0x1800510a5  jz      short loc_1800510AC
0x1800510a7  test    r8d, r8d
0x1800510aa  jnz     short loc_1800510AE
0x1800510ac  dec     eax
0x1800510ae  movsxd  r14, eax
0x1800510b1  test    eax, eax
0x1800510b3  jle     short loc_1800510F1
0x1800510b5  xor     ebp, ebp
0x1800510b7  mov     rbx, [rsi]
0x1800510ba  lea     rdi, [rbx+rbp]
0x1800510be  lea     rcx, [rdi+8]; SRWLock
0x1800510c2  call    cs:AcquireSRWLockExclusive
0x1800510c8  lea     rcx, [rbx+10h]
0x1800510cc  mov     dword ptr [rbx+rbp+20h], 0
0x1800510d4  add     rcx, rbp; ConditionVariable
0x1800510d7  call    cs:WakeConditionVariable
0x1800510dd  lea     rcx, [rdi+8]; SRWLock
0x1800510e1  call    cs:ReleaseSRWLockExclusive
0x1800510e7  add     rbp, 28h ; '('
0x1800510eb  sub     r14, 1
0x1800510ef  jnz     short loc_1800510B7
0x1800510f1  mov     rax, [rsi+50h]
0x1800510f5  test    rax, rax
0x1800510f8  jz      short loc_18005110B
0x1800510fa  test    r15d, r15d
0x1800510fd  jz      short loc_18005110B
0x1800510ff  mov     rcx, [rsi+40h]
0x180051103  call    cs:__guard_dispatch_icall_fptr
0x180051109  jmp     short loc_180051117
0x18005110b  mov     rcx, rsi
0x18005110e  call    sub_180051290
0x180051113  test    eax, eax
0x180051115  jnz     short loc_180051150
0x180051117  lea     rbx, [rsi+28h]
0x18005111b  mov     rcx, rbx; SRWLock
0x18005111e  call    cs:AcquireSRWLockExclusive
0x180051124  jmp     short loc_18005113A
0x180051126  xor     r9d, r9d; Flags
0x180051129  lea     rcx, [rsi+30h]; ConditionVariable
0x18005112d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180051131  mov     rdx, rbx; SRWLock
0x180051134  call    cs:SleepConditionVariableSRW
0x18005113a  cmp     dword ptr [rsi+38h], 0
0x18005113e  jz      short loc_180051126
0x180051140  mov     rcx, rbx; SRWLock
0x180051143  mov     dword ptr [rsi+38h], 0
0x18005114a  call    cs:ReleaseSRWLockExclusive
0x180051150  mov     rbx, [rsp+48h+arg_0]
0x180051155  mov     rbp, [rsp+48h+arg_8]
0x18005115a  mov     rsi, [rsp+48h+arg_10]
0x18005115f  add     rsp, 30h
0x180051163  pop     r15
0x180051165  pop     r14
0x180051167  pop     rdi
0x180051168  retn
0x180051169  lea     rax, aCW1SFfmpeginte_16; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x180051170  mov     [rsp+48h+var_20], 0C3h
0x180051178  lea     r9, aNbJobs0; "nb_jobs > 0"
0x18005117f  mov     [rsp+48h+var_28], rax
0x180051184  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x18005118b  xor     edx, edx
0x18005118d  xor     ecx, ecx
0x18005118f  call    av_log
0x180051194  call    abort
```
