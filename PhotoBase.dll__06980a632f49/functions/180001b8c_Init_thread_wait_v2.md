# _Init_thread_wait_v2

- ea: `0x180001b8c`
- end: `0x180001bea`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ad8`

## callees

- `0x180001b8c`
- `0x180008010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x180001bd2`
- `KERNEL32!WaitForSingleObjectEx` at `0x180001bd2`
- `KERNEL32!LeaveCriticalSection` at `0x180001bbe`
- `KERNEL32!LeaveCriticalSection` at `0x180001bbe`
- `KERNEL32!EnterCriticalSection` at `0x180001be3`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18000D270 )
  {
    qword_18000D270(&qword_18000D238, &CriticalSection, 0xFFFFFFFFLL);
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
0x180001b8c  sub     rsp, 28h
0x180001b90  mov     rax, cs:qword_18000D270
0x180001b97  test    rax, rax
0x180001b9a  jz      short loc_180001BB7
0x180001b9c  or      r8d, 0FFFFFFFFh
0x180001ba0  lea     rdx, CriticalSection
0x180001ba7  lea     rcx, qword_18000D238
0x180001bae  add     rsp, 28h
0x180001bb2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb7  lea     rcx, CriticalSection; lpCriticalSection
0x180001bbe  call    cs:__imp_LeaveCriticalSection
0x180001bc4  mov     rcx, cs:hHandle; hHandle
0x180001bcb  xor     r8d, r8d; bAlertable
0x180001bce  lea     edx, [r8+64h]; dwMilliseconds
0x180001bd2  call    cs:__imp_WaitForSingleObjectEx
0x180001bd8  lea     rcx, CriticalSection
0x180001bdf  add     rsp, 28h
0x180001be3  jmp     cs:__imp_EnterCriticalSection
```
