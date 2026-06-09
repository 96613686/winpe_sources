# _Init_thread_wait_v2

- ea: `0x1800022ec`
- end: `0x18000234a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002238`

## callees

- `0x1800022ec`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002343`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002332`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180002332`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000231e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000231e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180012498 )
  {
    qword_180012498(&qword_180012460, &stru_180012470, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180012470);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180012470);
  }
}

```

## disassembly

```asm
0x1800022ec  sub     rsp, 28h
0x1800022f0  mov     rax, cs:qword_180012498
0x1800022f7  test    rax, rax
0x1800022fa  jz      short loc_180002317
0x1800022fc  or      r8d, 0FFFFFFFFh
0x180002300  lea     rdx, stru_180012470
0x180002307  lea     rcx, qword_180012460
0x18000230e  add     rsp, 28h
0x180002312  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002317  lea     rcx, stru_180012470; lpCriticalSection
0x18000231e  call    cs:__imp_LeaveCriticalSection
0x180002324  mov     rcx, cs:hHandle; hHandle
0x18000232b  xor     r8d, r8d; bAlertable
0x18000232e  lea     edx, [r8+64h]; dwMilliseconds
0x180002332  call    cs:__imp_WaitForSingleObjectEx
0x180002338  lea     rcx, stru_180012470
0x18000233f  add     rsp, 28h
0x180002343  jmp     cs:__imp_EnterCriticalSection
```
