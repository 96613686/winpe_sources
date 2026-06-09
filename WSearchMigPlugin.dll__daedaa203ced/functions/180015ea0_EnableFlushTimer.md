# EnableFlushTimer

- ea: `0x180015ea0`
- end: `0x180015ef1`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016020`
- `0x180016070`

## callees

- `0x180015ea0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015ed9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015ed9`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_180026140 )
    {
      pftDueTime = (struct _FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x180015ea0  sub     rsp, 28h
0x180015ea4  test    rcx, rcx
0x180015ea7  jz      short loc_180015EEC
0x180015ea9  mov     eax, cs:dword_180026140
0x180015eaf  test    eax, eax
0x180015eb1  jnz     short loc_180015EEC
0x180015eb3  mov     eax, edx
0x180015eb5  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180015ebc  mov     rdx, rax
0x180015ebf  shr     rdx, 20h
0x180015ec3  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180015ec7  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180015ecb  mov     r9d, 1388h; msWindowLength
0x180015ed1  xor     r8d, r8d; msPeriod
0x180015ed4  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180015ed9  call    cs:__imp_SetThreadpoolTimer
0x180015edf  jmp     short loc_180015EEC
0x180015ee1  mov     eax, 1
0x180015ee6  xchg    eax, cs:dword_180026140
0x180015eec  add     rsp, 28h
0x180015ef0  retn
0x180017bdf  push    rbp
0x180017be1  sub     rsp, 20h
0x180017be5  mov     rbp, rdx
0x180017be8  mov     rax, [rcx]
0x180017beb  xor     ecx, ecx
0x180017bed  cmp     dword ptr [rax], 0C000000Dh
0x180017bf3  setz    cl
0x180017bf6  mov     eax, ecx
0x180017bf8  add     rsp, 20h
0x180017bfc  pop     rbp
0x180017bfd  retn
```
