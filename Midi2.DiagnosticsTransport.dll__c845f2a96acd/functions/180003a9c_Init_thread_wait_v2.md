# _Init_thread_wait_v2

- ea: `0x180003a9c`
- end: `0x180003afa`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039e8`

## callees

- `0x180003a9c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ace`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003af3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ae2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003ae2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_18001A490 )
  {
    qword_18001A490(&qword_18001A458, &CriticalSection, 0xFFFFFFFFLL);
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
0x180003a9c  sub     rsp, 28h
0x180003aa0  mov     rax, cs:qword_18001A490
0x180003aa7  test    rax, rax
0x180003aaa  jz      short loc_180003AC7
0x180003aac  or      r8d, 0FFFFFFFFh
0x180003ab0  lea     rdx, CriticalSection
0x180003ab7  lea     rcx, qword_18001A458
0x180003abe  add     rsp, 28h
0x180003ac2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac7  lea     rcx, CriticalSection; lpCriticalSection
0x180003ace  call    cs:__imp_LeaveCriticalSection
0x180003ad4  mov     rcx, cs:hHandle; hHandle
0x180003adb  xor     r8d, r8d; bAlertable
0x180003ade  lea     edx, [r8+64h]; dwMilliseconds
0x180003ae2  call    cs:__imp_WaitForSingleObjectEx
0x180003ae8  lea     rcx, CriticalSection
0x180003aef  add     rsp, 28h
0x180003af3  jmp     cs:__imp_EnterCriticalSection
```
