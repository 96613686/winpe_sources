# EnableFlushTimer

- ea: `0x18001ab08`
- end: `0x18001ab59`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ac90`
- `0x18001ace0`

## callees

- `0x18001ab08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ab41`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180028B98 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18001ab08  sub     rsp, 28h
0x18001ab0c  test    rcx, rcx
0x18001ab0f  jz      short loc_18001AB54
0x18001ab11  mov     eax, cs:dword_180028B98
0x18001ab17  test    eax, eax
0x18001ab19  jnz     short loc_18001AB54
0x18001ab1b  mov     eax, edx
0x18001ab1d  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18001ab24  mov     rdx, rax
0x18001ab27  shr     rdx, 20h
0x18001ab2b  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x18001ab2f  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x18001ab33  mov     r9d, 1388h; msWindowLength
0x18001ab39  xor     r8d, r8d; msPeriod
0x18001ab3c  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001ab41  call    cs:__imp_SetThreadpoolTimer
0x18001ab47  jmp     short loc_18001AB54
0x18001ab49  mov     eax, 1
0x18001ab4e  xchg    eax, cs:dword_180028B98
0x18001ab54  add     rsp, 28h
0x18001ab58  retn
0x18001bf86  push    rbp
0x18001bf88  sub     rsp, 20h
0x18001bf8c  mov     rbp, rdx
0x18001bf8f  mov     rax, [rcx]
0x18001bf92  xor     ecx, ecx
0x18001bf94  cmp     dword ptr [rax], 0C000000Dh
0x18001bf9a  setz    cl
0x18001bf9d  mov     eax, ecx
0x18001bf9f  add     rsp, 20h
0x18001bfa3  pop     rbp
0x18001bfa4  retn
```
