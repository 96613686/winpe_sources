# EnableFlushTimer

- ea: `0x18000b658`
- end: `0x18000b6a9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aa90`
- `0x18000b0d0`
- `0x18000bdb0`

## callees

- `0x18000b658`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b691`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b691`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180026678 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18000b658  sub     rsp, 28h
0x18000b65c  test    rcx, rcx
0x18000b65f  jz      short loc_18000B6A4
0x18000b661  mov     eax, cs:dword_180026678
0x18000b667  test    eax, eax
0x18000b669  jnz     short loc_18000B6A4
0x18000b66b  mov     eax, edx
0x18000b66d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000b674  mov     rdx, rax
0x18000b677  shr     rdx, 20h
0x18000b67b  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18000b67f  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000b683  mov     r9d, 1388h; msWindowLength
0x18000b689  xor     r8d, r8d; msPeriod
0x18000b68c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b691  call    cs:__imp_SetThreadpoolTimer
0x18000b697  jmp     short loc_18000B6A4
0x18000b699  mov     eax, 1
0x18000b69e  xchg    eax, cs:dword_180026678
0x18000b6a4  add     rsp, 28h
0x18000b6a8  retn
0x18001ab67  push    rbp
0x18001ab69  sub     rsp, 20h
0x18001ab6d  mov     rbp, rdx
0x18001ab70  mov     rax, [rcx]
0x18001ab73  xor     ecx, ecx
0x18001ab75  cmp     dword ptr [rax], 0C000000Dh
0x18001ab7b  setz    cl
0x18001ab7e  mov     eax, ecx
0x18001ab80  add     rsp, 20h
0x18001ab84  pop     rbp
0x18001ab85  retn
```
