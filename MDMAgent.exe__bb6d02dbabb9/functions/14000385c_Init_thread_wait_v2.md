# _Init_thread_wait_v2

- ea: `0x14000385c`
- end: `0x1400038ba`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400037a8`

## callees

- `0x14000385c`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000388e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000388e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400038b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400038a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400038a2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1400255B0 )
  {
    qword_1400255B0(&qword_140025578, &CriticalSection, 0xFFFFFFFFLL);
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
0x14000385c  sub     rsp, 28h
0x140003860  mov     rax, cs:qword_1400255B0
0x140003867  test    rax, rax
0x14000386a  jz      short loc_140003887
0x14000386c  or      r8d, 0FFFFFFFFh
0x140003870  lea     rdx, CriticalSection
0x140003877  lea     rcx, qword_140025578
0x14000387e  add     rsp, 28h
0x140003882  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003887  lea     rcx, CriticalSection; lpCriticalSection
0x14000388e  call    cs:__imp_LeaveCriticalSection
0x140003894  mov     rcx, cs:hHandle; hHandle
0x14000389b  xor     r8d, r8d; bAlertable
0x14000389e  lea     edx, [r8+64h]; dwMilliseconds
0x1400038a2  call    cs:__imp_WaitForSingleObjectEx
0x1400038a8  lea     rcx, CriticalSection
0x1400038af  add     rsp, 28h
0x1400038b3  jmp     cs:__imp_EnterCriticalSection
```
