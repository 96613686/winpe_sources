# _Init_thread_wait_v2

- ea: `0x1400034dc`
- end: `0x14000353a`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003428`

## callees

- `0x1400034dc`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003533`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000350e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000350e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003522`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003522`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140030570 )
  {
    qword_140030570(&qword_140030538, &stru_140030548, 0xFFFFFFFFLL);
  }
  else
  {
    LeaveCriticalSection(&stru_140030548);
    WaitForSingleObjectEx(hHandle, 0x64u, 0);
    EnterCriticalSection(&stru_140030548);
  }
}

```

## disassembly

```asm
0x1400034dc  sub     rsp, 28h
0x1400034e0  mov     rax, cs:qword_140030570
0x1400034e7  test    rax, rax
0x1400034ea  jz      short loc_140003507
0x1400034ec  or      r8d, 0FFFFFFFFh
0x1400034f0  lea     rdx, stru_140030548
0x1400034f7  lea     rcx, qword_140030538
0x1400034fe  add     rsp, 28h
0x140003502  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003507  lea     rcx, stru_140030548; lpCriticalSection
0x14000350e  call    cs:__imp_LeaveCriticalSection
0x140003514  mov     rcx, cs:hHandle; hHandle
0x14000351b  xor     r8d, r8d; bAlertable
0x14000351e  lea     edx, [r8+64h]; dwMilliseconds
0x140003522  call    cs:__imp_WaitForSingleObjectEx
0x140003528  lea     rcx, stru_140030548
0x14000352f  add     rsp, 28h
0x140003533  jmp     cs:__imp_EnterCriticalSection
```
