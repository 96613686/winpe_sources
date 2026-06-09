# _Init_thread_wait_v2

- ea: `0x1800023bc`
- end: `0x18000241a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002308`

## callees

- `0x1800023bc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002402`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002413`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180023550 )
  {
    qword_180023550(&qword_180023518, &stru_180023528, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180023528);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180023528);
  }
}

```

## disassembly

```asm
0x1800023bc  sub     rsp, 28h
0x1800023c0  mov     rax, cs:qword_180023550
0x1800023c7  test    rax, rax
0x1800023ca  jz      short loc_1800023E7
0x1800023cc  or      r8d, 0FFFFFFFFh
0x1800023d0  lea     rdx, stru_180023528
0x1800023d7  lea     rcx, qword_180023518
0x1800023de  add     rsp, 28h
0x1800023e2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e7  lea     rcx, stru_180023528; lpCriticalSection
0x1800023ee  call    cs:__imp_LeaveCriticalSection
0x1800023f4  mov     rcx, cs:hHandle; hHandle
0x1800023fb  xor     r8d, r8d; bAlertable
0x1800023fe  lea     edx, [r8+64h]; dwMilliseconds
0x180002402  call    cs:__imp_WaitForSingleObjectEx
0x180002408  lea     rcx, stru_180023528
0x18000240f  add     rsp, 28h
0x180002413  jmp     cs:__imp_EnterCriticalSection
```
