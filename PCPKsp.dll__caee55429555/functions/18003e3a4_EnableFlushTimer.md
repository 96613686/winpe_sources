# EnableFlushTimer

- ea: `0x18003e3a4`
- end: `0x18003e3fe`
- name: `EnableFlushTimer`
- size: `90`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003d800`
- `0x18003de10`
- `0x180068e40`

## callees

- `0x18003e3a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e3e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003e3e3`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180109BF8 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18003e3a4  sub     rsp, 28h
0x18003e3a8  test    rcx, rcx
0x18003e3ab  jnz     short loc_18003E3B3
0x18003e3ad  add     rsp, 28h
0x18003e3b1  retn
0x18003e3b3  mov     eax, cs:dword_180109BF8
0x18003e3b9  test    eax, eax
0x18003e3bb  jnz     short loc_18003E3AD
0x18003e3bd  mov     eax, edx
0x18003e3bf  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18003e3c6  mov     rdx, rax
0x18003e3c9  shr     rdx, 20h
0x18003e3cd  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18003e3d1  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18003e3d5  mov     r9d, 1388h; msWindowLength
0x18003e3db  xor     r8d, r8d; msPeriod
0x18003e3de  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18003e3e3  call    cs:__imp_SetThreadpoolTimer
0x18003e3ea  nop     dword ptr [rax+rax+00h]
0x18003e3ef  jmp     short loc_18003E3AD
0x18003e3f1  mov     eax, 1
0x18003e3f6  xchg    eax, cs:dword_180109BF8
0x18003e3fc  jmp     short loc_18003E3AD
0x1800c4da4  push    rbp
0x1800c4da6  sub     rsp, 20h
0x1800c4daa  mov     rbp, rdx
0x1800c4dad  mov     rax, [rcx]
0x1800c4db0  xor     ecx, ecx
0x1800c4db2  cmp     dword ptr [rax], 0C000000Dh
0x1800c4db8  setz    cl
0x1800c4dbb  mov     eax, ecx
0x1800c4dbd  add     rsp, 20h
0x1800c4dc1  pop     rbp
0x1800c4dc2  retn
```
