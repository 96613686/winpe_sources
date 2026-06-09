# _Init_thread_wait_v2

- ea: `0x180003ff8`
- end: `0x180004056`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f44`

## callees

- `0x180003ff8`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000404f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000402a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000403e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000403e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18002D850 )
  {
    qword_18002D850(&qword_18002D818, &CriticalSection, 0xFFFFFFFFLL);
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
0x180003ff8  sub     rsp, 28h
0x180003ffc  mov     rax, cs:qword_18002D850
0x180004003  test    rax, rax
0x180004006  jz      short loc_180004023
0x180004008  or      r8d, 0FFFFFFFFh
0x18000400c  lea     rdx, CriticalSection
0x180004013  lea     rcx, qword_18002D818
0x18000401a  add     rsp, 28h
0x18000401e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004023  lea     rcx, CriticalSection; lpCriticalSection
0x18000402a  call    cs:__imp_LeaveCriticalSection
0x180004030  mov     rcx, cs:hHandle; hHandle
0x180004037  xor     r8d, r8d; bAlertable
0x18000403a  lea     edx, [r8+64h]; dwMilliseconds
0x18000403e  call    cs:__imp_WaitForSingleObjectEx
0x180004044  lea     rcx, CriticalSection
0x18000404b  add     rsp, 28h
0x18000404f  jmp     cs:__imp_EnterCriticalSection
```
