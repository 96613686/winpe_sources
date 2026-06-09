# _Init_thread_wait_v2

- ea: `0x140001b5c`
- end: `0x140001bba`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001aa8`

## callees

- `0x140001b5c`
- `0x140011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140001b8e`
- `KERNEL32!LeaveCriticalSection` at `0x140001b8e`
- `KERNEL32!EnterCriticalSection` at `0x140001bb3`
- `KERNEL32!WaitForSingleObjectEx` at `0x140001ba2`
- `KERNEL32!WaitForSingleObjectEx` at `0x140001ba2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140018C88 )
  {
    qword_140018C88(&qword_140018C50, &stru_140018C60, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_140018C60);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_140018C60);
  }
}

```

## disassembly

```asm
0x140001b5c  sub     rsp, 28h
0x140001b60  mov     rax, cs:qword_140018C88
0x140001b67  test    rax, rax
0x140001b6a  jz      short loc_140001B87
0x140001b6c  or      r8d, 0FFFFFFFFh
0x140001b70  lea     rdx, stru_140018C60
0x140001b77  lea     rcx, qword_140018C50
0x140001b7e  add     rsp, 28h
0x140001b82  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140001b87  lea     rcx, stru_140018C60; lpCriticalSection
0x140001b8e  call    cs:__imp_LeaveCriticalSection
0x140001b94  mov     rcx, cs:hHandle; hHandle
0x140001b9b  xor     r8d, r8d; bAlertable
0x140001b9e  lea     edx, [r8+64h]; dwMilliseconds
0x140001ba2  call    cs:__imp_WaitForSingleObjectEx
0x140001ba8  lea     rcx, stru_140018C60
0x140001baf  add     rsp, 28h
0x140001bb3  jmp     cs:__imp_EnterCriticalSection
```
