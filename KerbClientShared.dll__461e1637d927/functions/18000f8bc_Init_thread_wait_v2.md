# _Init_thread_wait_v2

- ea: `0x18000f8bc`
- end: `0x18000f91a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f808`

## callees

- `0x18000f8bc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f902`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f902`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f913`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800332A0 )
  {
    qword_1800332A0(&qword_180033268, &CriticalSection, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x18000f8bc  sub     rsp, 28h
0x18000f8c0  mov     rax, cs:qword_1800332A0
0x18000f8c7  test    rax, rax
0x18000f8ca  jz      short loc_18000F8E7
0x18000f8cc  or      r8d, 0FFFFFFFFh
0x18000f8d0  lea     rdx, CriticalSection
0x18000f8d7  lea     rcx, qword_180033268
0x18000f8de  add     rsp, 28h
0x18000f8e2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8e7  lea     rcx, CriticalSection; lpCriticalSection
0x18000f8ee  call    cs:__imp_LeaveCriticalSection
0x18000f8f4  mov     rcx, cs:hHandle; hHandle
0x18000f8fb  xor     r8d, r8d; bAlertable
0x18000f8fe  lea     edx, [r8+64h]; dwMilliseconds
0x18000f902  call    cs:__imp_WaitForSingleObjectEx
0x18000f908  lea     rcx, CriticalSection
0x18000f90f  add     rsp, 28h
0x18000f913  jmp     cs:__imp_EnterCriticalSection
```
