# _Init_thread_wait_v2

- ea: `0x18002258c`
- end: `0x1800225ea`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800224d8`

## callees

- `0x18002258c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800225be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800225e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800225d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800225d2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_180040258 )
  {
    qword_180040258(&unk_180040220, &stru_180040230, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_180040230);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_180040230);
  }
}

```

## disassembly

```asm
0x18002258c  sub     rsp, 28h
0x180022590  mov     rax, cs:qword_180040258
0x180022597  test    rax, rax
0x18002259a  jz      short loc_1800225B7
0x18002259c  or      r8d, 0FFFFFFFFh
0x1800225a0  lea     rdx, stru_180040230
0x1800225a7  lea     rcx, unk_180040220
0x1800225ae  add     rsp, 28h
0x1800225b2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b7  lea     rcx, stru_180040230; lpCriticalSection
0x1800225be  call    cs:__imp_LeaveCriticalSection
0x1800225c4  mov     rcx, cs:hHandle; hHandle
0x1800225cb  xor     r8d, r8d; bAlertable
0x1800225ce  lea     edx, [r8+64h]; dwMilliseconds
0x1800225d2  call    cs:__imp_WaitForSingleObjectEx
0x1800225d8  lea     rcx, stru_180040230
0x1800225df  add     rsp, 28h
0x1800225e3  jmp     cs:__imp_EnterCriticalSection
```
