# _Init_thread_wait_v2

- ea: `0x18000362c`
- end: `0x18000368a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003578`

## callees

- `0x18000362c`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003672`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003672`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000365e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000365e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003683`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180021650 )
  {
    qword_180021650(&qword_180021618, &CriticalSection, 0xFFFFFFFFLL);
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
0x18000362c  sub     rsp, 28h
0x180003630  mov     rax, cs:qword_180021650
0x180003637  test    rax, rax
0x18000363a  jz      short loc_180003657
0x18000363c  or      r8d, 0FFFFFFFFh
0x180003640  lea     rdx, CriticalSection
0x180003647  lea     rcx, qword_180021618
0x18000364e  add     rsp, 28h
0x180003652  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003657  lea     rcx, CriticalSection; lpCriticalSection
0x18000365e  call    cs:__imp_LeaveCriticalSection
0x180003664  mov     rcx, cs:hHandle; hHandle
0x18000366b  xor     r8d, r8d; bAlertable
0x18000366e  lea     edx, [r8+64h]; dwMilliseconds
0x180003672  call    cs:__imp_WaitForSingleObjectEx
0x180003678  lea     rcx, CriticalSection
0x18000367f  add     rsp, 28h
0x180003683  jmp     cs:__imp_EnterCriticalSection
```
