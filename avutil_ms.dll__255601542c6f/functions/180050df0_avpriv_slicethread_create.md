# avpriv_slicethread_create

- ea: `0x180050df0`
- end: `0x180051050`
- name: `avpriv_slicethread_create`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180033ae0`
- `0x180042ad0`
- `0x180044670`
- `0x1800449c0`
- `0x1800449d0`
- `0x180044aa0`
- `0x180050df0`
- `0x1800511a0`
- `0x180078c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180050f96`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180050f96`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180050ede`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180050f19`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180050ede`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180050f19`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180050ed4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180050f0f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180050ed4`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180050f0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050fa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005100f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050fa6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005100f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050f22`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050f22`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180050f74`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180050f74`

## string_xrefs

- `0x18005101f`: `C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/slicethread.c`
- `0x18005102e`: `nb_threads >= 0`

## pseudocode

```c
__int64 __fastcall avpriv_slicethread_create(char **a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v5; // edi
  int v10; // eax
  int v11; // esi
  char *v12; // rax
  char *v13; // rbx
  __int64 v15; // rax
  int v16; // ebp
  __int64 v17; // r15
  __int64 v18; // rcx
  __int64 v19; // r14
  _QWORD *v20; // rsi
  HANDLE Thread; // rax
  int v22; // eax
  __int64 v23; // [rsp+30h] [rbp-38h]
  __int64 v24; // [rsp+38h] [rbp-30h]

  v5 = a5;
  if ( a5 < 0 )
  {
    av_log(
      0,
      0,
      "Assertion %s failed at %s:%d\n",
      "nb_threads >= 0",
      "C:/__w/1/s/FFmpegInterop/ffmpeg/libavutil/slicethread.c",
      108);
    abort();
  }
  if ( !a5 )
  {
    v10 = av_cpu_count();
    if ( v10 <= 1 )
    {
      v5 = 1;
    }
    else
    {
      v5 = v10 + 1;
      if ( v10 + 1 > 16 )
        v5 = 16;
    }
  }
  v11 = v5 - 1;
  if ( a4 )
    v11 = v5;
  v12 = (char *)av_mallocz(0x58u);
  *a1 = v12;
  v13 = v12;
  if ( !v12 )
    return 4294967284LL;
  v24 = v11;
  if ( v11 )
  {
    _mm_lfence();
    v15 = av_calloc(v11, 40);
    *(_QWORD *)v13 = v15;
    if ( !v15 )
    {
      av_freep(a1);
      return 4294967284LL;
    }
  }
  *((_QWORD *)v13 + 8) = a2;
  *((_QWORD *)v13 + 9) = a3;
  *((_QWORD *)v13 + 10) = a4;
  *((_DWORD *)v13 + 2) = v5;
  *(_QWORD *)(v13 + 12) = 0;
  *((_DWORD *)v13 + 15) = 0;
  *((_QWORD *)v13 + 3) = 0;
  *((_QWORD *)v13 + 4) = 0;
  InitializeSRWLock((PSRWLOCK)v13 + 5);
  InitializeConditionVariable((PCONDITION_VARIABLE)v13 + 6);
  v16 = 0;
  *((_DWORD *)v13 + 14) = 0;
  if ( v11 <= 0 )
  {
LABEL_23:
    _mm_lfence();
  }
  else
  {
    v17 = 0;
    v18 = 0;
    v23 = 0;
    while ( 1 )
    {
      v19 = v18 + *(_QWORD *)v13;
      *(_QWORD *)v19 = v13;
      InitializeSRWLock((PSRWLOCK)(v19 + 8));
      InitializeConditionVariable((PCONDITION_VARIABLE)(v19 + 16));
      AcquireSRWLockExclusive((PSRWLOCK)(v19 + 8));
      *(_DWORD *)(v19 + 32) = 0;
      v20 = av_mallocz(0x20u);
      if ( !v20 )
        break;
      v20[1] = sub_180051310;
      v20[2] = v19;
      Thread = CreateThread(0, 0, StartAddress, v20, 0, 0);
      *v20 = Thread;
      if ( !Thread )
      {
        av_free(v20);
        break;
      }
      *(_QWORD *)(v19 + 24) = v20;
      while ( !*(_DWORD *)(v19 + 32) )
        SleepConditionVariableSRW((PCONDITION_VARIABLE)(v19 + 16), (PSRWLOCK)(v19 + 8), 0xFFFFFFFF, 0);
      ReleaseSRWLockExclusive((PSRWLOCK)(v19 + 8));
      ++v16;
      v18 = v23 + 40;
      ++v17;
      v23 += 40;
      if ( v17 >= v24 )
        goto LABEL_23;
    }
    v22 = v16 + 1;
    v5 = -11;
    if ( a4 )
      v22 = v16;
    *((_DWORD *)v13 + 2) = v22;
    ReleaseSRWLockExclusive((PSRWLOCK)(v19 + 8));
    avpriv_slicethread_free(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x180050df0  mov     rax, rsp
0x180050df3  mov     [rax+8], rbx
0x180050df7  mov     [rax+10h], rbp
0x180050dfb  mov     [rax+18h], rsi
0x180050dff  mov     [rax+20h], r9
0x180050e03  push    rdi
0x180050e04  push    r12
0x180050e06  push    r13
0x180050e08  push    r14
0x180050e0a  push    r15
0x180050e0c  sub     rsp, 40h
0x180050e10  mov     edi, [rsp+68h+arg_20]
0x180050e17  mov     rbp, r9
0x180050e1a  mov     r15, r8
0x180050e1d  mov     r13, rdx
0x180050e20  mov     r12, rcx
0x180050e23  test    edi, edi
0x180050e25  js      loc_18005101F
0x180050e2b  jnz     short loc_180050E4B
0x180050e2d  call    av_cpu_count
0x180050e32  cmp     eax, 1
0x180050e35  jle     short loc_180050E46
0x180050e37  lea     edi, [rax+1]
0x180050e3a  mov     eax, 10h
0x180050e3f  cmp     edi, eax
0x180050e41  cmovg   edi, eax
0x180050e44  jmp     short loc_180050E4B
0x180050e46  mov     edi, 1
0x180050e4b  test    rbp, rbp
0x180050e4e  lea     esi, [rdi-1]
0x180050e51  mov     ecx, 58h ; 'X'
0x180050e56  cmovnz  esi, edi
0x180050e59  call    av_mallocz
0x180050e5e  mov     [r12], rax
0x180050e62  mov     rbx, rax
0x180050e65  test    rax, rax
0x180050e68  jnz     short loc_180050E74
0x180050e6a  mov     eax, 0FFFFFFF4h
0x180050e6f  jmp     loc_180050FCF
0x180050e74  movsxd  r14, esi
0x180050e77  mov     [rsp+68h+var_30], r14
0x180050e7c  test    esi, esi
0x180050e7e  jz      short loc_180050EA2
0x180050e80  lfence
0x180050e83  mov     edx, 28h ; '('
0x180050e88  mov     rcx, r14
0x180050e8b  call    av_calloc
0x180050e90  mov     [rbx], rax
0x180050e93  test    rax, rax
0x180050e96  jnz     short loc_180050EA2
0x180050e98  mov     rcx, r12
0x180050e9b  call    av_freep
0x180050ea0  jmp     short loc_180050E6A
0x180050ea2  lea     rcx, [rbx+28h]; SRWLock
0x180050ea6  mov     [rbx+40h], r13
0x180050eaa  mov     [rbx+48h], r15
0x180050eae  mov     [rbx+50h], rbp
0x180050eb2  mov     [rbx+8], edi
0x180050eb5  mov     qword ptr [rbx+0Ch], 0
0x180050ebd  mov     dword ptr [rbx+3Ch], 0
0x180050ec4  mov     qword ptr [rbx+18h], 0
0x180050ecc  mov     qword ptr [rbx+20h], 0
0x180050ed4  call    cs:InitializeSRWLock
0x180050eda  lea     rcx, [rbx+30h]; ConditionVariable
0x180050ede  call    cs:InitializeConditionVariable
0x180050ee4  xor     ebp, ebp
0x180050ee6  mov     dword ptr [rbx+38h], 0
0x180050eed  test    esi, esi
0x180050eef  jle     loc_180050FCA
0x180050ef5  xor     r15d, r15d
0x180050ef8  xor     ecx, ecx
0x180050efa  mov     [rsp+68h+var_38], rcx
0x180050eff  mov     r14, [rbx]
0x180050f02  add     r14, rcx
0x180050f05  lea     r13, [r14+8]
0x180050f09  mov     [r14], rbx
0x180050f0c  mov     rcx, r13; SRWLock
0x180050f0f  call    cs:InitializeSRWLock
0x180050f15  lea     rcx, [r14+10h]; ConditionVariable
0x180050f19  call    cs:InitializeConditionVariable
0x180050f1f  mov     rcx, r13; SRWLock
0x180050f22  call    cs:AcquireSRWLockExclusive
0x180050f28  mov     ecx, 20h ; ' '
0x180050f2d  mov     dword ptr [r14+20h], 0
0x180050f35  call    av_mallocz
0x180050f3a  mov     rsi, rax
0x180050f3d  test    rax, rax
0x180050f40  jz      loc_180050FF5
0x180050f46  lea     rax, sub_180051310
0x180050f4d  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x180050f56  mov     r9, rsi; lpParameter
0x180050f59  mov     [rsi+8], rax
0x180050f5d  lea     r8, StartAddress; lpStartAddress
0x180050f64  mov     [rsi+10h], r14
0x180050f68  xor     edx, edx; dwStackSize
0x180050f6a  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x180050f72  xor     ecx, ecx; lpThreadAttributes
0x180050f74  call    cs:CreateThread
0x180050f7a  mov     [rsi], rax
0x180050f7d  test    rax, rax
0x180050f80  jz      short loc_180050FED
0x180050f82  mov     [r14+18h], rsi
0x180050f86  jmp     short loc_180050F9C
0x180050f88  xor     r9d, r9d; Flags
0x180050f8b  lea     rcx, [r14+10h]; ConditionVariable
0x180050f8f  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180050f93  mov     rdx, r13; SRWLock
0x180050f96  call    cs:SleepConditionVariableSRW
0x180050f9c  cmp     dword ptr [r14+20h], 0
0x180050fa1  jz      short loc_180050F88
0x180050fa3  mov     rcx, r13; SRWLock
0x180050fa6  call    cs:ReleaseSRWLockExclusive
0x180050fac  mov     rcx, [rsp+68h+var_38]
0x180050fb1  inc     ebp
0x180050fb3  add     rcx, 28h ; '('
0x180050fb7  inc     r15
0x180050fba  mov     [rsp+68h+var_38], rcx
0x180050fbf  cmp     r15, [rsp+68h+var_30]
0x180050fc4  jl      loc_180050EFF
0x180050fca  lfence
0x180050fcd  mov     eax, edi
0x180050fcf  lea     r11, [rsp+68h+var_28]
0x180050fd4  mov     rbx, [r11+30h]
0x180050fd8  mov     rbp, [r11+38h]
0x180050fdc  mov     rsi, [r11+40h]
0x180050fe0  mov     rsp, r11
0x180050fe3  pop     r15
0x180050fe5  pop     r14
0x180050fe7  pop     r13
0x180050fe9  pop     r12
0x180050feb  pop     rdi
0x180050fec  retn
0x180050fed  mov     rcx, rsi; Block
0x180050ff0  call    av_free
0x180050ff5  cmp     [rsp+68h+arg_18], 0
0x180050ffe  lea     eax, [rbp+1]
0x180051001  mov     rcx, r13; SRWLock
0x180051004  mov     edi, 0FFFFFFF5h
0x180051009  cmovnz  eax, ebp
0x18005100c  mov     [rbx+8], eax
0x18005100f  call    cs:ReleaseSRWLockExclusive
0x180051015  mov     rcx, r12
0x180051018  call    avpriv_slicethread_free
0x18005101d  jmp     short loc_180050FCD
0x18005101f  lea     rax, aCW1SFfmpeginte_16; "C:/__w/1/s/FFmpegInterop/ffmpeg/libavut"...
0x180051026  mov     dword ptr [rsp+68h+lpThreadId], 6Ch ; 'l'
0x18005102e  lea     r9, aNbThreads0; "nb_threads >= 0"
0x180051035  mov     qword ptr [rsp+68h+dwCreationFlags], rax
0x18005103a  lea     r8, aAssertionSFail; "Assertion %s failed at %s:%d\n"
0x180051041  xor     edx, edx
0x180051043  xor     ecx, ecx
0x180051045  call    av_log
0x18005104a  call    abort
```
