# _Init_thread_wait

- ea: `0x1400250f4`
- end: `0x140025157`
- name: `_Init_thread_wait`
- size: `99`
- prototype: `void __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025048`

## callees

- `0x1400250f4`
- `0x1400ae030`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140025150`
- `KERNEL32!LeaveCriticalSection` at `0x14002512c`
- `KERNEL32!LeaveCriticalSection` at `0x14002512c`
- `KERNEL32!WaitForSingleObjectEx` at `0x14002513e`
- `KERNEL32!WaitForSingleObjectEx` at `0x14002513e`

## pseudocode

```c
void __fastcall Init_thread_wait(DWORD dwMilliseconds)
{
  if ( qword_1400D7C48 )
  {
    qword_1400D7C48(&qword_1400D7C10, &CriticalSection, dwMilliseconds);
  }
  else
  {
    LeaveCriticalSection(&CriticalSection);
    WaitForSingleObjectEx(hHandle, dwMilliseconds, 0);
    EnterCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x1400250f4  push    rbx
0x1400250f6  sub     rsp, 20h
0x1400250fa  mov     rax, cs:qword_1400D7C48
0x140025101  mov     ebx, ecx
0x140025103  test    rax, rax
0x140025106  jz      short loc_140025125
0x140025108  mov     r8d, ecx
0x14002510b  lea     rdx, CriticalSection
0x140025112  lea     rcx, qword_1400D7C10
0x140025119  add     rsp, 20h
0x14002511d  pop     rbx
0x14002511e  jmp     cs:__guard_dispatch_icall_fptr
0x140025125  lea     rcx, CriticalSection; lpCriticalSection
0x14002512c  call    cs:LeaveCriticalSection
0x140025132  mov     rcx, cs:hHandle; hHandle
0x140025139  xor     r8d, r8d; bAlertable
0x14002513c  mov     edx, ebx; dwMilliseconds
0x14002513e  call    cs:WaitForSingleObjectEx
0x140025144  lea     rcx, CriticalSection
0x14002514b  add     rsp, 20h
0x14002514f  pop     rbx
0x140025150  jmp     cs:EnterCriticalSection
```
