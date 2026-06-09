# _Init_thread_wait_v2

- ea: `0x1400037bc`
- end: `0x14000381a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003708`

## callees

- `0x1400037bc`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400037ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400037ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003813`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003802`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003802`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_1400244B0 )
  {
    qword_1400244B0(&qword_140024478, &CriticalSection, 0xFFFFFFFFLL);
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
0x1400037bc  sub     rsp, 28h
0x1400037c0  mov     rax, cs:qword_1400244B0
0x1400037c7  test    rax, rax
0x1400037ca  jz      short loc_1400037E7
0x1400037cc  or      r8d, 0FFFFFFFFh
0x1400037d0  lea     rdx, CriticalSection
0x1400037d7  lea     rcx, qword_140024478
0x1400037de  add     rsp, 28h
0x1400037e2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400037e7  lea     rcx, CriticalSection; lpCriticalSection
0x1400037ee  call    cs:__imp_LeaveCriticalSection
0x1400037f4  mov     rcx, cs:hHandle; hHandle
0x1400037fb  xor     r8d, r8d; bAlertable
0x1400037fe  lea     edx, [r8+64h]; dwMilliseconds
0x140003802  call    cs:__imp_WaitForSingleObjectEx
0x140003808  lea     rcx, CriticalSection
0x14000380f  add     rsp, 28h
0x140003813  jmp     cs:__imp_EnterCriticalSection
```
