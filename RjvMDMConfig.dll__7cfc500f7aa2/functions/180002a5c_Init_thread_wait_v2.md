# _Init_thread_wait_v2

- ea: `0x180002a5c`
- end: `0x180002aba`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029a8`

## callees

- `0x180002a5c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002ab3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002aa2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002aa2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a8e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800298B8 )
  {
    qword_1800298B8(&qword_180029880, &CriticalSection, 0xFFFFFFFFLL);
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
0x180002a5c  sub     rsp, 28h
0x180002a60  mov     rax, cs:qword_1800298B8
0x180002a67  test    rax, rax
0x180002a6a  jz      short loc_180002A87
0x180002a6c  or      r8d, 0FFFFFFFFh
0x180002a70  lea     rdx, CriticalSection
0x180002a77  lea     rcx, qword_180029880
0x180002a7e  add     rsp, 28h
0x180002a82  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002a87  lea     rcx, CriticalSection; lpCriticalSection
0x180002a8e  call    cs:__imp_LeaveCriticalSection
0x180002a94  mov     rcx, cs:hHandle; hHandle
0x180002a9b  xor     r8d, r8d; bAlertable
0x180002a9e  lea     edx, [r8+64h]; dwMilliseconds
0x180002aa2  call    cs:__imp_WaitForSingleObjectEx
0x180002aa8  lea     rcx, CriticalSection
0x180002aaf  add     rsp, 28h
0x180002ab3  jmp     cs:__imp_EnterCriticalSection
```
