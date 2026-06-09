# EnableFlushTimer

- ea: `0x18000b698`
- end: `0x18000b6e9`
- name: `EnableFlushTimer`
- size: `81`
- prototype: `void __fastcall(struct _TP_TIMER *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b820`
- `0x18000b870`

## callees

- `0x18000b698`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b6d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b6d1`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180015BB0 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18000b698  sub     rsp, 28h
0x18000b69c  test    rcx, rcx
0x18000b69f  jz      short loc_18000B6E4
0x18000b6a1  mov     eax, cs:dword_180015BB0
0x18000b6a7  test    eax, eax
0x18000b6a9  jnz     short loc_18000B6E4
0x18000b6ab  mov     eax, edx
0x18000b6ad  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000b6b4  mov     rdx, rax
0x18000b6b7  shr     rdx, 20h
0x18000b6bb  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18000b6bf  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18000b6c3  mov     r9d, 1388h; msWindowLength
0x18000b6c9  xor     r8d, r8d; msPeriod
0x18000b6cc  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000b6d1  call    cs:__imp_SetThreadpoolTimer
0x18000b6d7  jmp     short loc_18000B6E4
0x18000b6d9  mov     eax, 1
0x18000b6de  xchg    eax, cs:dword_180015BB0
0x18000b6e4  add     rsp, 28h
0x18000b6e8  retn
0x18000d090  push    rbp
0x18000d092  sub     rsp, 20h
0x18000d096  mov     rbp, rdx
0x18000d099  mov     rax, [rcx]
0x18000d09c  xor     ecx, ecx
0x18000d09e  cmp     dword ptr [rax], 0C000000Dh
0x18000d0a4  setz    cl
0x18000d0a7  mov     eax, ecx
0x18000d0a9  add     rsp, 20h
0x18000d0ad  pop     rbp
0x18000d0ae  retn
```
