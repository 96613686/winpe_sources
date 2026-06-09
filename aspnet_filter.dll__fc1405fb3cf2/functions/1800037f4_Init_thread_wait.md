# _Init_thread_wait

- ea: `0x1800037f4`
- end: `0x180003857`
- name: `_Init_thread_wait`
- size: `99`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003748`

## callees

- `0x1800037f4`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000382c`
- `KERNEL32!LeaveCriticalSection` at `0x18000382c`
- `KERNEL32!EnterCriticalSection` at `0x180003850`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000383e`
- `KERNEL32!WaitForSingleObjectEx` at `0x18000383e`

## pseudocode

```c
void __fastcall Init_thread_wait(DWORD dwMilliseconds)
{
  if ( qword_180007218 )
  {
    qword_180007218(&qword_1800071E0, &CriticalSection, dwMilliseconds);
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
0x1800037f4  push    rbx
0x1800037f6  sub     rsp, 20h
0x1800037fa  mov     rax, cs:qword_180007218
0x180003801  mov     ebx, ecx
0x180003803  test    rax, rax
0x180003806  jz      short loc_180003825
0x180003808  mov     r8d, ecx
0x18000380b  lea     rdx, CriticalSection
0x180003812  lea     rcx, qword_1800071E0
0x180003819  add     rsp, 20h
0x18000381d  pop     rbx
0x18000381e  jmp     cs:__guard_dispatch_icall_fptr
0x180003825  lea     rcx, CriticalSection; lpCriticalSection
0x18000382c  call    cs:__imp_LeaveCriticalSection
0x180003832  mov     rcx, cs:hHandle; hHandle
0x180003839  xor     r8d, r8d; bAlertable
0x18000383c  mov     edx, ebx; dwMilliseconds
0x18000383e  call    cs:__imp_WaitForSingleObjectEx
0x180003844  lea     rcx, CriticalSection
0x18000384b  add     rsp, 20h
0x18000384f  pop     rbx
0x180003850  jmp     cs:__imp_EnterCriticalSection
```
