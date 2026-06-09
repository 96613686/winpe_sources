# EnableFlushTimer

- ea: `0x18000b3e4`
- end: `0x18000b435`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b560`

## callees

- `0x18000b3e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b41d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b41d`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180014508 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18000b3e4  sub     rsp, 28h
0x18000b3e8  test    rcx, rcx
0x18000b3eb  jz      short loc_18000B430
0x18000b3ed  mov     eax, cs:dword_180014508
0x18000b3f3  test    eax, eax
0x18000b3f5  jnz     short loc_18000B430
0x18000b3f7  mov     eax, edx
0x18000b3f9  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000b400  mov     rdx, rax
0x18000b403  shr     rdx, 20h
0x18000b407  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18000b40b  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000b40f  mov     r9d, 1388h; msWindowLength
0x18000b415  xor     r8d, r8d; msPeriod
0x18000b418  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b41d  call    cs:__imp_SetThreadpoolTimer
0x18000b423  jmp     short loc_18000B430
0x18000b425  mov     eax, 1
0x18000b42a  xchg    eax, cs:dword_180014508
0x18000b430  add     rsp, 28h
0x18000b434  retn
0x18000c73c  push    rbp
0x18000c73e  sub     rsp, 20h
0x18000c742  mov     rbp, rdx
0x18000c745  mov     rax, [rcx]
0x18000c748  xor     ecx, ecx
0x18000c74a  cmp     dword ptr [rax], 0C000000Dh
0x18000c750  setz    cl
0x18000c753  mov     eax, ecx
0x18000c755  add     rsp, 20h
0x18000c759  pop     rbp
0x18000c75a  retn
```
