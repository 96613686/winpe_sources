# _Init_thread_wait_v2

- ea: `0x140003f58`
- end: `0x140003fb6`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ea4`

## callees

- `0x140003f58`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003f9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003f9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003faf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003f8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003f8a`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140039DE0 )
  {
    qword_140039DE0(&qword_140039DA8, &stru_140039DB8, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_140039DB8);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_140039DB8);
  }
}

```

## disassembly

```asm
0x140003f58  sub     rsp, 28h
0x140003f5c  mov     rax, cs:qword_140039DE0
0x140003f63  test    rax, rax
0x140003f66  jz      short loc_140003F83
0x140003f68  or      r8d, 0FFFFFFFFh
0x140003f6c  lea     rdx, stru_140039DB8
0x140003f73  lea     rcx, qword_140039DA8
0x140003f7a  add     rsp, 28h
0x140003f7e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003f83  lea     rcx, stru_140039DB8; lpCriticalSection
0x140003f8a  call    cs:__imp_LeaveCriticalSection
0x140003f90  mov     rcx, cs:hHandle; hHandle
0x140003f97  xor     r8d, r8d; bAlertable
0x140003f9a  lea     edx, [r8+64h]; dwMilliseconds
0x140003f9e  call    cs:__imp_WaitForSingleObjectEx
0x140003fa4  lea     rcx, stru_140039DB8
0x140003fab  add     rsp, 28h
0x140003faf  jmp     cs:__imp_EnterCriticalSection
```
