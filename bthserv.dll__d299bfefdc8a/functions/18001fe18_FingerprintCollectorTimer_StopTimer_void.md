# FingerprintCollectorTimer::StopTimer(void)

- ea: `0x18001fe18`
- end: `0x18001ffc8`
- name: `?StopTimer@FingerprintCollectorTimer@@IEAA?AW4StopTimerResult@SmFx@@XZ`
- size: `432`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f1b0`

## callees

- `0x18001140c`
- `0x18001fe18`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ff63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ff63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fef1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18001ff07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18001ff07`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ff51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ff51`

## pseudocode

```c
__int64 __fastcall FingerprintCollectorTimer::StopTimer(__int64 a1)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  __int64 v7; // rbx
  int v8; // esi
  __int64 v9; // rcx
  char v10; // al

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v2 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v2 + 5));
  v7 = *(_QWORD *)(a1 + 80);
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 32));
  if ( SetThreadpoolTimerEx(*(PTP_TIMER *)(*(_QWORD *)(v7 + 24) + 80LL), 0, 0, 0) )
  {
    v9 = *(_QWORD *)(v7 + 160);
    *(_QWORD *)(v7 + 160) = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
    *(_BYTE *)(v7 + 40) = 0;
    v10 = *(_BYTE *)(v7 + 168);
    *(_BYTE *)(v7 + 168) = 0;
    v8 = 0;
    if ( v10 )
      QueryPerformanceCounter((LARGE_INTEGER *)(v7 + 184));
  }
  else
  {
    v8 = 1;
  }
  *(_BYTE *)(v7 + 41) = 1;
  if ( v7 != -32 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  return (unsigned int)(v8 + 1);
}

```

## disassembly

```asm
0x18001fe18  push    rbx
0x18001fe1a  push    rbp
0x18001fe1b  push    rsi
0x18001fe1c  push    rdi
0x18001fe1d  push    r12
0x18001fe1f  push    r13
0x18001fe21  push    r14
0x18001fe23  push    r15
0x18001fe25  sub     rsp, 58h
0x18001fe29  mov     r14, rcx
0x18001fe2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe33  lea     r15, WPP_GLOBAL_Control
0x18001fe3a  mov     edi, 1
0x18001fe3f  cmp     rcx, r15
0x18001fe42  jz      short loc_18001FE4F
0x18001fe44  cmp     byte ptr [rcx+19h], 5
0x18001fe48  jb      short loc_18001FE4F
0x18001fe4a  mov     dl, dil
0x18001fe4d  jmp     short loc_18001FE51
0x18001fe4f  xor     dl, dl
0x18001fe51  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18001fe58  lea     r12, WPP_RECORDER_INITIALIZED
0x18001fe5f  cmp     rax, r12
0x18001fe62  lea     r13, WPP_839c6382b2ad3f346a7c505e6bed1a32_Traceguids
0x18001fe69  setnz   r8b
0x18001fe6d  test    dl, dl
0x18001fe6f  jnz     short loc_18001FE76
0x18001fe71  test    r8b, r8b
0x18001fe74  jz      short loc_18001FEA2
0x18001fe76  mov     r9, [rcx+28h]
0x18001fe7a  mov     rcx, [rcx+10h]
0x18001fe7e  mov     [rsp+98h+var_50], r14
0x18001fe83  mov     [rsp+98h+var_60], r13
0x18001fe88  mov     [rsp+98h+var_68], 12h
0x18001fe8f  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001fe94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe9b  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18001fea2  cmp     rcx, r15
0x18001fea5  jz      short loc_18001FEB2
0x18001fea7  cmp     byte ptr [rcx+19h], 4
0x18001feab  jb      short loc_18001FEB2
0x18001fead  mov     dl, dil
0x18001feb0  jmp     short loc_18001FEB4
0x18001feb2  xor     dl, dl
0x18001feb4  cmp     rax, r12
0x18001feb7  setnz   r8b
0x18001febb  test    dl, dl
0x18001febd  jnz     short loc_18001FEC4
0x18001febf  test    r8b, r8b
0x18001fec2  jz      short loc_18001FEE6
0x18001fec4  mov     rax, [r14+48h]
0x18001fec8  mov     r9, [rcx+28h]
0x18001fecc  mov     rcx, [rcx+10h]
0x18001fed0  mov     [rsp+98h+var_50], rax
0x18001fed5  mov     [rsp+98h+var_60], r13
0x18001feda  mov     [rsp+98h+var_68], 13h
0x18001fee1  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001fee6  mov     rbx, [r14+50h]
0x18001feea  lea     rbp, [rbx+20h]
0x18001feee  mov     rcx, rbp; SRWLock
0x18001fef1  call    cs:__imp_AcquireSRWLockExclusive
0x18001fef7  mov     rcx, [rbx+18h]
0x18001fefb  xor     r9d, r9d; msWindowLength
0x18001fefe  xor     r8d, r8d; msPeriod
0x18001ff01  xor     edx, edx; pftDueTime
0x18001ff03  mov     rcx, [rcx+50h]; pti
0x18001ff07  call    cs:__imp_SetThreadpoolTimerEx
0x18001ff0d  test    eax, eax
0x18001ff0f  jnz     short loc_18001FF15
0x18001ff11  mov     esi, edi
0x18001ff13  jmp     short loc_18001FF57
0x18001ff15  mov     rcx, [rbx+0A0h]
0x18001ff1c  mov     qword ptr [rbx+0A0h], 0
0x18001ff27  test    rcx, rcx
0x18001ff2a  jz      short loc_18001FF38
0x18001ff2c  mov     rax, [rcx]
0x18001ff2f  mov     rax, [rax+18h]
0x18001ff33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff38  xor     eax, eax
0x18001ff3a  mov     byte ptr [rbx+28h], 0
0x18001ff3e  xchg    al, [rbx+0A8h]
0x18001ff44  xor     esi, esi
0x18001ff46  test    al, al
0x18001ff48  jz      short loc_18001FF57
0x18001ff4a  lea     rcx, [rbx+0B8h]; lpPerformanceCount
0x18001ff51  call    cs:__imp_QueryPerformanceCounter
0x18001ff57  mov     [rbx+29h], dil
0x18001ff5b  test    rbp, rbp
0x18001ff5e  jz      short loc_18001FF69
0x18001ff60  mov     rcx, rbp; SRWLock
0x18001ff63  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ff69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff70  cmp     rcx, r15
0x18001ff73  jz      short loc_18001FF7B
0x18001ff75  cmp     byte ptr [rcx+19h], 5
0x18001ff79  jnb     short loc_18001FF7E
0x18001ff7b  xor     dil, dil
0x18001ff7e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001ff85  setnz   r8b
0x18001ff89  test    dil, dil
0x18001ff8c  jnz     short loc_18001FF93
0x18001ff8e  test    r8b, r8b
0x18001ff91  jz      short loc_18001FFB4
0x18001ff93  mov     r9, [rcx+28h]
0x18001ff97  mov     dl, dil
0x18001ff9a  mov     rcx, [rcx+10h]
0x18001ff9e  mov     [rsp+98h+var_50], r14
0x18001ffa3  mov     [rsp+98h+var_60], r13
0x18001ffa8  mov     [rsp+98h+var_68], 14h
0x18001ffaf  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001ffb4  lea     eax, [rsi+1]
0x18001ffb7  add     rsp, 58h
0x18001ffbb  pop     r15
0x18001ffbd  pop     r14
0x18001ffbf  pop     r13
0x18001ffc1  pop     r12
0x18001ffc3  pop     rdi
0x18001ffc4  pop     rsi
0x18001ffc5  pop     rbp
0x18001ffc6  pop     rbx
0x18001ffc7  retn
```
