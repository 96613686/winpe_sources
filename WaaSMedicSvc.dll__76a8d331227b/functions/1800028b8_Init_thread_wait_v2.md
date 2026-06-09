# _Init_thread_wait_v2

- ea: `0x1800028b8`
- end: `0x180002916`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002804`

## callees

- `0x1800028b8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800028fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800028fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800028ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000290f`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180013430 )
  {
    qword_180013430(&qword_1800133F8, &CriticalSection, 0xFFFFFFFFLL);
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
0x1800028b8  sub     rsp, 28h
0x1800028bc  mov     rax, cs:qword_180013430
0x1800028c3  test    rax, rax
0x1800028c6  jz      short loc_1800028E3
0x1800028c8  or      r8d, 0FFFFFFFFh
0x1800028cc  lea     rdx, CriticalSection
0x1800028d3  lea     rcx, qword_1800133F8
0x1800028da  add     rsp, 28h
0x1800028de  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e3  lea     rcx, CriticalSection; lpCriticalSection
0x1800028ea  call    cs:__imp_LeaveCriticalSection
0x1800028f0  mov     rcx, cs:hHandle; hHandle
0x1800028f7  xor     r8d, r8d; bAlertable
0x1800028fa  lea     edx, [r8+64h]; dwMilliseconds
0x1800028fe  call    cs:__imp_WaitForSingleObjectEx
0x180002904  lea     rcx, CriticalSection
0x18000290b  add     rsp, 28h
0x18000290f  jmp     cs:__imp_EnterCriticalSection
```
