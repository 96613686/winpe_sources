# _Init_thread_wait_v2

- ea: `0x180002358`
- end: `0x1800023b6`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022a4`

## callees

- `0x180002358`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000238a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000238a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800023af`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000239e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000239e`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180010410 )
  {
    qword_180010410(&qword_1800103D8, &stru_1800103E8, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_1800103E8);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_1800103E8);
  }
}

```

## disassembly

```asm
0x180002358  sub     rsp, 28h
0x18000235c  mov     rax, cs:qword_180010410
0x180002363  test    rax, rax
0x180002366  jz      short loc_180002383
0x180002368  or      r8d, 0FFFFFFFFh
0x18000236c  lea     rdx, stru_1800103E8
0x180002373  lea     rcx, qword_1800103D8
0x18000237a  add     rsp, 28h
0x18000237e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180002383  lea     rcx, stru_1800103E8; lpCriticalSection
0x18000238a  call    cs:__imp_LeaveCriticalSection
0x180002390  mov     rcx, cs:hHandle; hHandle
0x180002397  xor     r8d, r8d; bAlertable
0x18000239a  lea     edx, [r8+64h]; dwMilliseconds
0x18000239e  call    cs:__imp_WaitForSingleObjectEx
0x1800023a4  lea     rcx, stru_1800103E8
0x1800023ab  add     rsp, 28h
0x1800023af  jmp     cs:__imp_EnterCriticalSection
```
