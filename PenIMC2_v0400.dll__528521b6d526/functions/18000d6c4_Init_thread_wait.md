# _Init_thread_wait

- ea: `0x18000d6c4`
- end: `0x18000d727`
- name: `_Init_thread_wait`
- size: `99`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d618`

## callees

- `0x18000d6c4`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d720`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6fc`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6fc`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000d70e`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000d70e`

## pseudocode

```c
void __fastcall Init_thread_wait(DWORD dwMilliseconds)
{
  if ( qword_180018910 )
  {
    qword_180018910(&qword_1800188D8, &stru_1800188E8, dwMilliseconds);
  }
  else
  {
    LeaveCriticalSection(&stru_1800188E8);
    WaitForSingleObjectEx(hHandle, dwMilliseconds, 0);
    EnterCriticalSection(&stru_1800188E8);
  }
}

```

## disassembly

```asm
0x18000d6c4  push    rbx
0x18000d6c6  sub     rsp, 20h
0x18000d6ca  mov     rax, cs:qword_180018910
0x18000d6d1  mov     ebx, ecx
0x18000d6d3  test    rax, rax
0x18000d6d6  jz      short loc_18000D6F5
0x18000d6d8  mov     r8d, ecx
0x18000d6db  lea     rdx, stru_1800188E8
0x18000d6e2  lea     rcx, qword_1800188D8
0x18000d6e9  add     rsp, 20h
0x18000d6ed  pop     rbx
0x18000d6ee  jmp     cs:__guard_dispatch_icall_fptr
0x18000d6f5  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d6fc  call    cs:__imp_LeaveCriticalSection
0x18000d702  mov     rcx, cs:hHandle; hHandle
0x18000d709  xor     r8d, r8d; bAlertable
0x18000d70c  mov     edx, ebx; dwMilliseconds
0x18000d70e  call    cs:__imp_WaitForSingleObjectEx
0x18000d714  lea     rcx, stru_1800188E8
0x18000d71b  add     rsp, 20h
0x18000d71f  pop     rbx
0x18000d720  jmp     cs:__imp_EnterCriticalSection
```
