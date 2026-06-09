# EnableFlushTimer

- ea: `0x18007287c`
- end: `0x1800728cd`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180072a30`
- `0x180072a80`

## callees

- `0x18007287c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800728b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800728b5`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_1800B2D48 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18007287c  sub     rsp, 28h
0x180072880  test    rcx, rcx
0x180072883  jz      short loc_1800728C8
0x180072885  mov     eax, cs:dword_1800B2D48
0x18007288b  test    eax, eax
0x18007288d  jnz     short loc_1800728C8
0x18007288f  mov     eax, edx
0x180072891  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180072898  mov     rdx, rax
0x18007289b  shr     rdx, 20h
0x18007289f  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800728a3  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800728a7  mov     r9d, 1388h; msWindowLength
0x1800728ad  xor     r8d, r8d; msPeriod
0x1800728b0  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800728b5  call    cs:__imp_SetThreadpoolTimer
0x1800728bb  jmp     short loc_1800728C8
0x1800728bd  mov     eax, 1
0x1800728c2  xchg    eax, cs:dword_1800B2D48
0x1800728c8  add     rsp, 28h
0x1800728cc  retn
0x18009bd9c  push    rbp
0x18009bd9e  sub     rsp, 20h
0x18009bda2  mov     rbp, rdx
0x18009bda5  mov     rax, [rcx]
0x18009bda8  xor     ecx, ecx
0x18009bdaa  cmp     dword ptr [rax], 0C000000Dh
0x18009bdb0  setz    cl
0x18009bdb3  mov     eax, ecx
0x18009bdb5  add     rsp, 20h
0x18009bdb9  pop     rbp
0x18009bdba  retn
```
