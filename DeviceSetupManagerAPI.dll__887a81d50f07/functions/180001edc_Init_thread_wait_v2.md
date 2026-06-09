# _Init_thread_wait_v2

- ea: `0x180001edc`
- end: `0x180001f3a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e28`

## callees

- `0x180001edc`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001f22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180001f22`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180017690 )
  {
    qword_180017690(&qword_180017658, &stru_180017668, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180017668);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180017668);
  }
}

```

## disassembly

```asm
0x180001edc  sub     rsp, 28h
0x180001ee0  mov     rax, cs:qword_180017690
0x180001ee7  test    rax, rax
0x180001eea  jz      short loc_180001F07
0x180001eec  or      r8d, 0FFFFFFFFh
0x180001ef0  lea     rdx, stru_180017668
0x180001ef7  lea     rcx, qword_180017658
0x180001efe  add     rsp, 28h
0x180001f02  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001f07  lea     rcx, stru_180017668; lpCriticalSection
0x180001f0e  call    cs:__imp_LeaveCriticalSection
0x180001f14  mov     rcx, cs:hHandle; hHandle
0x180001f1b  xor     r8d, r8d; bAlertable
0x180001f1e  lea     edx, [r8+64h]; dwMilliseconds
0x180001f22  call    cs:__imp_WaitForSingleObjectEx
0x180001f28  lea     rcx, stru_180017668
0x180001f2f  add     rsp, 28h
0x180001f33  jmp     cs:__imp_EnterCriticalSection
```
