# _Init_thread_wait_v2

- ea: `0x140001c48`
- end: `0x140001ca6`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b94`

## callees

- `0x140001c48`
- `0x140013010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x140001c8e`
- `KERNEL32!WaitForSingleObjectEx` at `0x140001c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001c7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001c9f`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_14001A470 )
  {
    qword_14001A470(&qword_14001A438, &CriticalSection, 0xFFFFFFFFLL);
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
0x140001c48  sub     rsp, 28h
0x140001c4c  mov     rax, cs:qword_14001A470
0x140001c53  test    rax, rax
0x140001c56  jz      short loc_140001C73
0x140001c58  or      r8d, 0FFFFFFFFh
0x140001c5c  lea     rdx, CriticalSection
0x140001c63  lea     rcx, qword_14001A438
0x140001c6a  add     rsp, 28h
0x140001c6e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140001c73  lea     rcx, CriticalSection; lpCriticalSection
0x140001c7a  call    cs:__imp_LeaveCriticalSection
0x140001c80  mov     rcx, cs:hHandle; hHandle
0x140001c87  xor     r8d, r8d; bAlertable
0x140001c8a  lea     edx, [r8+64h]; dwMilliseconds
0x140001c8e  call    cs:__imp_WaitForSingleObjectEx
0x140001c94  lea     rcx, CriticalSection
0x140001c9b  add     rsp, 28h
0x140001c9f  jmp     cs:__imp_EnterCriticalSection
```
