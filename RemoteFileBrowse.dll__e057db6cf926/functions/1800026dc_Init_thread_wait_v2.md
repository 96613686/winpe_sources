# _Init_thread_wait_v2

- ea: `0x1800026dc`
- end: `0x18000273a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002628`

## callees

- `0x1800026dc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000270e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000270e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002722`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002722`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002733`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Init_thread_wait_v2()
{
  if ( qword_1800234F0 )
  {
    qword_1800234F0(&qword_1800234B8, &CriticalSection, 0xFFFFFFFFLL);
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
0x1800026dc  sub     rsp, 28h
0x1800026e0  mov     rax, cs:qword_1800234F0
0x1800026e7  test    rax, rax
0x1800026ea  jz      short loc_180002707
0x1800026ec  or      r8d, 0FFFFFFFFh
0x1800026f0  lea     rdx, CriticalSection
0x1800026f7  lea     rcx, qword_1800234B8
0x1800026fe  add     rsp, 28h
0x180002702  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002707  lea     rcx, CriticalSection; lpCriticalSection
0x18000270e  call    cs:__imp_LeaveCriticalSection
0x180002714  mov     rcx, cs:hHandle; hHandle
0x18000271b  xor     r8d, r8d; bAlertable
0x18000271e  lea     edx, [r8+64h]; dwMilliseconds
0x180002722  call    cs:__imp_WaitForSingleObjectEx
0x180002728  lea     rcx, CriticalSection
0x18000272f  add     rsp, 28h
0x180002733  jmp     cs:__imp_EnterCriticalSection
```
