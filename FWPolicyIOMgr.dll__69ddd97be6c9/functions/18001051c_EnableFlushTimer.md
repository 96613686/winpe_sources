# EnableFlushTimer

- ea: `0x18001051c`
- end: `0x18001056d`
- name: `EnableFlushTimer`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180010214`
- `0x1800118f0`

## callees

- `0x18001051c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010555`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010555`

## pseudocode

```c
void __fastcall EnableFlushTimer(struct _TP_TIMER *a1, unsigned int a2)
{
  _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( !dword_1800537B0 )
    {
      pftDueTime = (_FILETIME)(-10000LL * a2);
      SetThreadpoolTimer(a1, &pftDueTime, 0, 0x1388u);
    }
  }
}

```

## disassembly

```asm
0x18001051c  sub     rsp, 28h
0x180010520  test    rcx, rcx
0x180010523  jz      short loc_180010568
0x180010525  mov     eax, cs:dword_1800537B0
0x18001052b  test    eax, eax
0x18001052d  jnz     short loc_180010568
0x18001052f  mov     eax, edx
0x180010531  imul    rax, 0FFFFFFFFFFFFD8F0h
0x180010538  mov     rdx, rax
0x18001053b  shr     rdx, 20h
0x18001053f  mov     [rsp+28h+pftDueTime.dwHighDateTime], edx
0x180010543  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180010547  mov     r9d, 1388h; msWindowLength
0x18001054d  xor     r8d, r8d; msPeriod
0x180010550  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180010555  call    cs:__imp_SetThreadpoolTimer
0x18001055b  jmp     short loc_180010568
0x18001055d  mov     eax, 1
0x180010562  xchg    eax, cs:dword_1800537B0
0x180010568  add     rsp, 28h
0x18001056c  retn
0x180039c3c  push    rbp
0x180039c3e  sub     rsp, 20h
0x180039c42  mov     rbp, rdx
0x180039c45  mov     rax, [rcx]
0x180039c48  xor     ecx, ecx
0x180039c4a  cmp     dword ptr [rax], 0C000000Dh
0x180039c50  setz    cl
0x180039c53  mov     eax, ecx
0x180039c55  add     rsp, 20h
0x180039c59  pop     rbp
0x180039c5a  retn
```
