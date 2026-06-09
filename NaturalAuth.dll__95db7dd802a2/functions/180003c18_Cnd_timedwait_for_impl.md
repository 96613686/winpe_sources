# _Cnd_timedwait_for_impl

- ea: `0x180003c18`
- end: `0x180003c98`
- name: `_Cnd_timedwait_for_impl`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ca0`

## callees

- `0x180003c18`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003c5b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003c6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003c6a`

## pseudocode

```c
__int64 __fastcall Cnd_timedwait_for_impl(RTL_CONDITION_VARIABLE *a1, __int64 a2, unsigned int a3, char a4)
{
  unsigned int v4; // edi
  ULONGLONG v5; // r14
  ULONGLONG TickCount64; // rsi
  DWORD CurrentThreadId; // eax

  v4 = 0;
  v5 = a3;
  TickCount64 = 0;
  if ( a4 )
    TickCount64 = GetTickCount64();
  --*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = -1;
  if ( !SleepConditionVariableSRW(a1 + 1, (PSRWLOCK)(a2 + 16), v5, 0) && (!a4 || GetTickCount64() - TickCount64 >= v5) )
    v4 = 2;
  CurrentThreadId = GetCurrentThreadId();
  ++*(_DWORD *)(a2 + 76);
  *(_DWORD *)(a2 + 72) = CurrentThreadId;
  return v4;
}

```

## disassembly

```asm
0x180003c18  push    rbx
0x180003c1a  push    rbp
0x180003c1b  push    rsi
0x180003c1c  push    rdi
0x180003c1d  push    r14
0x180003c1f  push    r15
0x180003c21  sub     rsp, 28h
0x180003c25  xor     edi, edi
0x180003c27  mov     r14d, r8d
0x180003c2a  xor     esi, esi
0x180003c2c  mov     bpl, r9b
0x180003c2f  mov     rbx, rdx
0x180003c32  mov     r15, rcx
0x180003c35  test    r9b, r9b
0x180003c38  jz      short loc_180003C43
0x180003c3a  call    cs:__imp_GetTickCount64
0x180003c40  mov     rsi, rax
0x180003c43  dec     dword ptr [rbx+4Ch]
0x180003c46  lea     rdx, [rbx+10h]; SRWLock
0x180003c4a  lea     rcx, [r15+8]; ConditionVariable
0x180003c4e  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180003c55  xor     r9d, r9d; Flags
0x180003c58  mov     r8d, r14d; dwMilliseconds
0x180003c5b  call    cs:__imp_SleepConditionVariableSRW
0x180003c61  test    eax, eax
0x180003c63  jnz     short loc_180003C7D
0x180003c65  test    bpl, bpl
0x180003c68  jz      short loc_180003C78
0x180003c6a  call    cs:__imp_GetTickCount64
0x180003c70  sub     rax, rsi
0x180003c73  cmp     rax, r14
0x180003c76  jb      short loc_180003C7D
0x180003c78  mov     edi, 2
0x180003c7d  call    cs:__imp_GetCurrentThreadId
0x180003c83  inc     dword ptr [rbx+4Ch]
0x180003c86  mov     [rbx+48h], eax
0x180003c89  mov     eax, edi
0x180003c8b  add     rsp, 28h
0x180003c8f  pop     r15
0x180003c91  pop     r14
0x180003c93  pop     rdi
0x180003c94  pop     rsi
0x180003c95  pop     rbp
0x180003c96  pop     rbx
0x180003c97  retn
```
