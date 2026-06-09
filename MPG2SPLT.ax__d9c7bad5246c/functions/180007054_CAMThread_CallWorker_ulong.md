# CAMThread::CallWorker(ulong)

- ea: `0x180007054`
- end: `0x1800070bb`
- name: `?CallWorker@CAMThread@@QEAAKK@Z`
- size: `103`
- prototype: `unsigned int __fastcall(CAMThread *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8b0`
- `0x18000ed0c`
- `0x18000edbc`
- `0x18001b468`
- `0x18001bc80`
- `0x18001bd30`

## callees

- `0x180007054`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180007097`
- `KERNEL32!WaitForSingleObject` at `0x180007097`
- `KERNEL32!SetEvent` at `0x18000708a`
- `KERNEL32!SetEvent` at `0x18000708a`
- `KERNEL32!LeaveCriticalSection` at `0x1800070a3`
- `KERNEL32!LeaveCriticalSection` at `0x1800070a3`
- `KERNEL32!EnterCriticalSection` at `0x18000706f`
- `KERNEL32!EnterCriticalSection` at `0x18000706f`

## pseudocode

```c
__int64 __fastcall CAMThread::CallWorker(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  unsigned int LockSemaphore_high; // ebx
  void *v6; // rcx

  v2 = this + 1;
  EnterCriticalSection(this + 1);
  if ( this->SpinCount )
  {
    v6 = *(void **)&this->LockCount;
    LODWORD(this->LockSemaphore) = a2;
    SetEvent(v6);
    WaitForSingleObject(this->OwningThread, 0xFFFFFFFF);
    LockSemaphore_high = HIDWORD(this->LockSemaphore);
  }
  else
  {
    LockSemaphore_high = -2147467259;
  }
  LeaveCriticalSection(v2);
  return LockSemaphore_high;
}

```

## disassembly

```asm
0x180007054  mov     [rsp+arg_0], rbx
0x180007059  mov     [rsp+arg_8], rsi
0x18000705e  push    rdi
0x18000705f  sub     rsp, 20h
0x180007063  lea     rdi, [rcx+28h]
0x180007067  mov     rbx, rcx
0x18000706a  mov     rcx, rdi; lpCriticalSection
0x18000706d  mov     esi, edx
0x18000706f  call    cs:__imp_EnterCriticalSection
0x180007075  cmp     qword ptr [rbx+20h], 0
0x18000707a  jnz     short loc_180007083
0x18000707c  mov     ebx, 80004005h
0x180007081  jmp     short loc_1800070A0
0x180007083  mov     rcx, [rbx+8]; hEvent
0x180007087  mov     [rbx+18h], esi
0x18000708a  call    cs:__imp_SetEvent
0x180007090  mov     rcx, [rbx+10h]; hHandle
0x180007094  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180007097  call    cs:__imp_WaitForSingleObject
0x18000709d  mov     ebx, [rbx+1Ch]
0x1800070a0  mov     rcx, rdi; lpCriticalSection
0x1800070a3  call    cs:__imp_LeaveCriticalSection
0x1800070a9  mov     rsi, [rsp+28h+arg_8]
0x1800070ae  mov     eax, ebx
0x1800070b0  mov     rbx, [rsp+28h+arg_0]
0x1800070b5  add     rsp, 20h
0x1800070b9  pop     rdi
0x1800070ba  retn
```
