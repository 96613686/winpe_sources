# _anonymous_namespace_::SetShutdownTimer

- ea: `0x180007124`
- end: `0x18000716d`
- name: `_anonymous_namespace_::SetShutdownTimer`
- size: `73`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bc4`
- `0x180007660`
- `0x180007d20`

## callees

- `0x180007124`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000715d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000715d`

## pseudocode

```c
__int64 anonymous_namespace_::SetShutdownTimer()
{
  __int64 result; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  result = 0;
  if ( pti )
  {
    pftDueTime = (struct _FILETIME)-(__int64)(unsigned int)(10000000 * dword_18000E1FC);
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0x3E8u);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180007124  sub     rsp, 28h
0x180007128  mov     rcx, cs:pti; pti
0x18000712f  xor     eax, eax
0x180007131  test    rcx, rcx
0x180007134  jz      short loc_180007168
0x180007136  imul    eax, cs:dword_18000E1FC, 989680h
0x180007140  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180007145  mov     r9d, 3E8h; msWindowLength
0x18000714b  xor     r8d, r8d; msPeriod
0x18000714e  neg     rax
0x180007151  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180007155  shr     rax, 20h
0x180007159  mov     [rsp+28h+pftDueTime.dwHighDateTime], eax
0x18000715d  call    cs:__imp_SetThreadpoolTimer
0x180007163  mov     eax, 1
0x180007168  add     rsp, 28h
0x18000716c  retn
```
