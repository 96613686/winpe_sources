# EnableFlushTimer

- ea: `0x180011464`
- end: `0x1800114bc`
- name: `EnableFlushTimer`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011104`
- `0x18001b020`

## callees

- `0x180011464`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001149d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001149d`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180024B08 )
    {
      pftDueTime = (_FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180011464  sub     rsp, 28h
0x180011468  test    rcx, rcx
0x18001146b  jz      short loc_1800114B6
0x18001146d  mov     eax, cs:dword_180024B08
0x180011473  test    eax, eax
0x180011475  jnz     short loc_1800114B6
0x180011477  mov     eax, edx
0x180011479  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180011480  mov     rdx, rax
0x180011483  shr     rdx, 20h
0x180011487  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18001148b  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001148f  mov     r9d, 1388h; msWindowLength
0x180011495  xor     r8d, r8d; msPeriod
0x180011498  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001149d  call    cs:__imp_SetThreadpoolTimer
0x1800114a4  nop     dword ptr [rax+rax+00h]
0x1800114a9  jmp     short loc_1800114B6
0x1800114ab  mov     eax, 1
0x1800114b0  xchg    eax, cs:dword_180024B08
0x1800114b6  add     rsp, 28h
0x1800114ba  retn
0x18001b91d  push    rbp
0x18001b91f  sub     rsp, 20h
0x18001b923  mov     rbp, rdx
0x18001b926  mov     rax, [rcx]
0x18001b929  xor     ecx, ecx
0x18001b92b  cmp     dword ptr [rax], 0C000000Dh
0x18001b931  setz    cl
0x18001b934  mov     eax, ecx
0x18001b936  add     rsp, 20h
0x18001b93a  pop     rbp
0x18001b93b  retn
```
