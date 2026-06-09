# _Init_thread_wait_v2

- ea: `0x180003638`
- end: `0x180003696`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003584`

## callees

- `0x180003638`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000368f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000366a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000366a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000367e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000367e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180025CB8 )
  {
    qword_180025CB8(&qword_180025C80, &stru_180025C90, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180025C90);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180025C90);
  }
}

```

## disassembly

```asm
0x180003638  sub     rsp, 28h
0x18000363c  mov     rax, cs:qword_180025CB8
0x180003643  test    rax, rax
0x180003646  jz      short loc_180003663
0x180003648  or      r8d, 0FFFFFFFFh
0x18000364c  lea     rdx, stru_180025C90
0x180003653  lea     rcx, qword_180025C80
0x18000365a  add     rsp, 28h
0x18000365e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003663  lea     rcx, stru_180025C90; lpCriticalSection
0x18000366a  call    cs:__imp_LeaveCriticalSection
0x180003670  mov     rcx, cs:hHandle; hHandle
0x180003677  xor     r8d, r8d; bAlertable
0x18000367a  lea     edx, [r8+64h]; dwMilliseconds
0x18000367e  call    cs:__imp_WaitForSingleObjectEx
0x180003684  lea     rcx, stru_180025C90
0x18000368b  add     rsp, 28h
0x18000368f  jmp     cs:__imp_EnterCriticalSection
```
