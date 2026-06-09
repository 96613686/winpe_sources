# _Init_thread_wait_v2

- ea: `0x14000a01c`
- end: `0x14000a07a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140009f68`

## callees

- `0x14000a01c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a04e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000a04e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a062`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000a062`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000a073`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140018480 )
  {
    qword_140018480(&qword_140018448, &CriticalSection, 0xFFFFFFFFLL);
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
0x14000a01c  sub     rsp, 28h
0x14000a020  mov     rax, cs:qword_140018480
0x14000a027  test    rax, rax
0x14000a02a  jz      short loc_14000A047
0x14000a02c  or      r8d, 0FFFFFFFFh
0x14000a030  lea     rdx, CriticalSection
0x14000a037  lea     rcx, qword_140018448
0x14000a03e  add     rsp, 28h
0x14000a042  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x14000a047  lea     rcx, CriticalSection; lpCriticalSection
0x14000a04e  call    cs:__imp_LeaveCriticalSection
0x14000a054  mov     rcx, cs:hHandle; hHandle
0x14000a05b  xor     r8d, r8d; bAlertable
0x14000a05e  lea     edx, [r8+64h]; dwMilliseconds
0x14000a062  call    cs:__imp_WaitForSingleObjectEx
0x14000a068  lea     rcx, CriticalSection
0x14000a06f  add     rsp, 28h
0x14000a073  jmp     cs:__imp_EnterCriticalSection
```
