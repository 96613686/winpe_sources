# _Init_thread_wait_v2

- ea: `0x14000326c`
- end: `0x1400032ca`
- name: `_Init_thread_wait_v2`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031b8`

## callees

- `0x14000326c`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000329e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000329e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400032c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400032b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400032b2`

## pseudocode

```c
void Init_thread_wait_v2()
{
  if ( qword_140050330 )
  {
    qword_140050330(&unk_1400502F8, &CriticalSection, 0xFFFFFFFFLL);
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
0x14000326c  sub     rsp, 28h
0x140003270  mov     rax, cs:qword_140050330
0x140003277  test    rax, rax
0x14000327a  jz      short loc_140003297
0x14000327c  or      r8d, 0FFFFFFFFh
0x140003280  lea     rdx, CriticalSection
0x140003287  lea     rcx, unk_1400502F8
0x14000328e  add     rsp, 28h
0x140003292  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x140003297  lea     rcx, CriticalSection; lpCriticalSection
0x14000329e  call    cs:__imp_LeaveCriticalSection
0x1400032a4  mov     rcx, cs:hHandle; hHandle
0x1400032ab  xor     r8d, r8d; bAlertable
0x1400032ae  lea     edx, [r8+64h]; dwMilliseconds
0x1400032b2  call    cs:__imp_WaitForSingleObjectEx
0x1400032b8  lea     rcx, CriticalSection
0x1400032bf  add     rsp, 28h
0x1400032c3  jmp     cs:__imp_EnterCriticalSection
```
