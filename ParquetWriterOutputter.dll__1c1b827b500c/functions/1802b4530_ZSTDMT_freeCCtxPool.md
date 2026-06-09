# ZSTDMT_freeCCtxPool

- ea: `0x1802b4530`
- end: `0x1802b459d`
- name: `ZSTDMT_freeCCtxPool`
- size: `109`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1802b3820`
- `0x1802b4010`
- `0x1802b4440`

## callees

- `0x1802aa650`
- `0x1802af0e0`
- `0x1802b4530`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1802b456b`
- `KERNEL32!DeleteCriticalSection` at `0x1802b456b`

## pseudocode

```c
__int64 __fastcall ZSTDMT_freeCCtxPool(LPCRITICAL_SECTION lpCriticalSection)
{
  int v1; // edi
  ULONG_PTR *p_SpinCount; // rbx
  HANDLE LockSemaphore; // xmm1_8
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  HANDLE v7; // [rsp+30h] [rbp-18h]

  v1 = 0;
  if ( SLODWORD(lpCriticalSection[1].DebugInfo) > 0 )
  {
    p_SpinCount = &lpCriticalSection[1].SpinCount;
    do
    {
      ZSTD_freeCCtx(*p_SpinCount);
      ++v1;
      ++p_SpinCount;
    }
    while ( v1 < SLODWORD(lpCriticalSection[1].DebugInfo) );
  }
  DeleteCriticalSection(lpCriticalSection);
  LockSemaphore = lpCriticalSection[1].LockSemaphore;
  v6 = *(_OWORD *)&lpCriticalSection[1].LockCount;
  v7 = LockSemaphore;
  return ZSTD_free(lpCriticalSection, &v6);
}

```

## disassembly

```asm
0x1802b4530  mov     [rsp+arg_8], rsi
0x1802b4535  push    rdi
0x1802b4536  sub     rsp, 40h
0x1802b453a  xor     edi, edi
0x1802b453c  mov     rsi, rcx
0x1802b453f  cmp     [rcx+28h], edi
0x1802b4542  jle     short loc_1802B4568
0x1802b4544  mov     [rsp+48h+arg_0], rbx
0x1802b4549  lea     rbx, [rcx+48h]
0x1802b454d  nop     dword ptr [rax]
0x1802b4550  mov     rcx, [rbx]
0x1802b4553  call    ZSTD_freeCCtx
0x1802b4558  inc     edi
0x1802b455a  lea     rbx, [rbx+8]
0x1802b455e  cmp     edi, [rsi+28h]
0x1802b4561  jl      short loc_1802B4550
0x1802b4563  mov     rbx, [rsp+48h+arg_0]
0x1802b4568  mov     rcx, rsi; lpCriticalSection
0x1802b456b  call    cs:__imp_DeleteCriticalSection
0x1802b4571  movups  xmm0, xmmword ptr [rsi+30h]
0x1802b4575  lea     rdx, [rsp+48h+var_28]
0x1802b457a  mov     rcx, rsi
0x1802b457d  movsd   xmm1, qword ptr [rsi+40h]
0x1802b4582  movaps  [rsp+48h+var_28], xmm0
0x1802b4587  movsd   [rsp+48h+var_18], xmm1
0x1802b458d  call    ZSTD_free
0x1802b4592  mov     rsi, [rsp+48h+arg_8]
0x1802b4597  add     rsp, 40h
0x1802b459b  pop     rdi
0x1802b459c  retn
```
