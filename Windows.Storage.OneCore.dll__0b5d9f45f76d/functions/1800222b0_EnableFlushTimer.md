# EnableFlushTimer

- ea: `0x1800222b0`
- end: `0x180022301`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180022460`
- `0x1800224b0`

## callees

- `0x1800222b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800222e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800222e9`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180033880 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x1800222b0  sub     rsp, 28h
0x1800222b4  test    rcx, rcx
0x1800222b7  jz      short loc_1800222FC
0x1800222b9  mov     eax, cs:dword_180033880
0x1800222bf  test    eax, eax
0x1800222c1  jnz     short loc_1800222FC
0x1800222c3  mov     eax, edx
0x1800222c5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800222cc  mov     rdx, rax
0x1800222cf  shr     rdx, 20h
0x1800222d3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x1800222d7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x1800222db  mov     r9d, 1388h; msWindowLength
0x1800222e1  xor     r8d, r8d; msPeriod
0x1800222e4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x1800222e9  call    cs:__imp_SetThreadpoolTimer
0x1800222ef  jmp     short loc_1800222FC
0x1800222f1  mov     eax, 1
0x1800222f6  xchg    eax, cs:dword_180033880
0x1800222fc  add     rsp, 28h
0x180022300  retn
0x1800248b4  push    rbp
0x1800248b6  sub     rsp, 20h
0x1800248ba  mov     rbp, rdx
0x1800248bd  mov     rax, [rcx]
0x1800248c0  xor     ecx, ecx
0x1800248c2  cmp     dword ptr [rax], 0C000000Dh
0x1800248c8  setz    cl
0x1800248cb  mov     eax, ecx
0x1800248cd  add     rsp, 20h
0x1800248d1  pop     rbp
0x1800248d2  retn
```
