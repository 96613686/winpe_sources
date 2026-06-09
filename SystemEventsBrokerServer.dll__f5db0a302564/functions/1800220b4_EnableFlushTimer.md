# EnableFlushTimer

- ea: `0x1800220b4`
- end: `0x180022105`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800150e0`

## callees

- `0x1800220b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800220ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800220ed`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180036E18 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x1800220b4  sub     rsp, 28h
0x1800220b8  test    rcx, rcx
0x1800220bb  jz      short loc_180022100
0x1800220bd  mov     eax, cs:dword_180036E18
0x1800220c3  test    eax, eax
0x1800220c5  jnz     short loc_180022100
0x1800220c7  mov     eax, edx
0x1800220c9  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800220d0  mov     rdx, rax
0x1800220d3  shr     rdx, 20h
0x1800220d7  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800220db  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800220df  mov     r9d, 1388h; msWindowLength
0x1800220e5  xor     r8d, r8d; msPeriod
0x1800220e8  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800220ed  call    cs:__imp_SetThreadpoolTimer
0x1800220f3  jmp     short loc_180022100
0x1800220f5  mov     eax, 1
0x1800220fa  xchg    eax, cs:dword_180036E18
0x180022100  add     rsp, 28h
0x180022104  retn
0x180026227  push    rbp
0x180026229  sub     rsp, 20h
0x18002622d  mov     rbp, rdx
0x180026230  mov     rax, [rcx]
0x180026233  xor     ecx, ecx
0x180026235  cmp     dword ptr [rax], 0C000000Dh
0x18002623b  setz    cl
0x18002623e  mov     eax, ecx
0x180026240  add     rsp, 20h
0x180026244  pop     rbp
0x180026245  retn
```
