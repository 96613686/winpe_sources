# _Init_thread_wait_v2

- ea: `0x180046d08`
- end: `0x180046d66`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046c54`

## callees

- `0x180046d08`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180046d4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180046d4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046d3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046d5f`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1800B4C18 )
  {
    qword_1800B4C18(&qword_1800B4BE0, &CriticalSection, 0xFFFFFFFFLL);
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
0x180046d08  sub     rsp, 28h
0x180046d0c  mov     rax, cs:qword_1800B4C18
0x180046d13  test    rax, rax
0x180046d16  jz      short loc_180046D33
0x180046d18  or      r8d, 0FFFFFFFFh
0x180046d1c  lea     rdx, CriticalSection
0x180046d23  lea     rcx, qword_1800B4BE0
0x180046d2a  add     rsp, 28h
0x180046d2e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180046d33  lea     rcx, CriticalSection; lpCriticalSection
0x180046d3a  call    cs:__imp_LeaveCriticalSection
0x180046d40  mov     rcx, cs:hHandle; hHandle
0x180046d47  xor     r8d, r8d; bAlertable
0x180046d4a  lea     edx, [r8+64h]; dwMilliseconds
0x180046d4e  call    cs:__imp_WaitForSingleObjectEx
0x180046d54  lea     rcx, CriticalSection
0x180046d5b  add     rsp, 28h
0x180046d5f  jmp     cs:__imp_EnterCriticalSection
```
