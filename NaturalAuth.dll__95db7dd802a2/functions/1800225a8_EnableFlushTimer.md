# EnableFlushTimer

- ea: `0x1800225a8`
- end: `0x1800225f9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180022750`
- `0x1800227a0`

## callees

- `0x1800225a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800225e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800225e1`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_18005FA08 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x1800225a8  sub     rsp, 28h
0x1800225ac  test    rcx, rcx
0x1800225af  jz      short loc_1800225F4
0x1800225b1  mov     eax, cs:dword_18005FA08
0x1800225b7  test    eax, eax
0x1800225b9  jnz     short loc_1800225F4
0x1800225bb  mov     eax, edx
0x1800225bd  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800225c4  mov     rdx, rax
0x1800225c7  shr     rdx, 20h
0x1800225cb  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800225cf  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800225d3  mov     r9d, 1388h; msWindowLength
0x1800225d9  xor     r8d, r8d; msPeriod
0x1800225dc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800225e1  call    cs:__imp_SetThreadpoolTimer
0x1800225e7  jmp     short loc_1800225F4
0x1800225e9  mov     eax, 1
0x1800225ee  xchg    eax, cs:dword_18005FA08
0x1800225f4  add     rsp, 28h
0x1800225f8  retn
0x180043733  push    rbp
0x180043735  sub     rsp, 20h
0x180043739  mov     rbp, rdx
0x18004373c  mov     rax, [rcx]
0x18004373f  xor     ecx, ecx
0x180043741  cmp     dword ptr [rax], 0C000000Dh
0x180043747  setz    cl
0x18004374a  mov     eax, ecx
0x18004374c  add     rsp, 20h
0x180043750  pop     rbp
0x180043751  retn
```
