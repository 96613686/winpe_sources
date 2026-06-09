# CMMPullPin::StopThread(void)

- ea: `0x18000edbc`
- end: `0x18000ee75`
- name: `?StopThread@CMMPullPin@@IEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CMMPullPin *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf10`
- `0x18000e834`

## callees

- `0x180007054`
- `0x18000edbc`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000ee30`
- `KERNEL32!WaitForSingleObject` at `0x18000ee30`
- `KERNEL32!CloseHandle` at `0x18000ee39`
- `KERNEL32!CloseHandle` at `0x18000ee39`
- `KERNEL32!LeaveCriticalSection` at `0x18000ee5d`
- `KERNEL32!LeaveCriticalSection` at `0x18000ee5d`
- `KERNEL32!EnterCriticalSection` at `0x18000edd2`
- `KERNEL32!EnterCriticalSection` at `0x18000edd2`

## pseudocode

```c
__int64 __fastcall CMMPullPin::StopThread(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // edi
  void *v3; // rdi
  ULONG_PTR SpinCount; // rcx

  EnterCriticalSection(this + 1);
  if ( this->SpinCount )
  {
    v2 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 72LL))(this[3].DebugInfo);
    if ( v2 >= 0 )
    {
      HIDWORD(this[4].DebugInfo) = 2;
      CAMThread::CallWorker(this, 2);
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 80LL))(this[3].DebugInfo);
      v3 = (void *)_InterlockedExchange64((volatile __int64 *)&this->SpinCount, 0);
      if ( v3 )
      {
        WaitForSingleObject(v3, 0xFFFFFFFF);
        CloseHandle(v3);
      }
      SpinCount = this[3].SpinCount;
      if ( SpinCount )
        (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 48LL))(SpinCount);
      v2 = 0;
    }
  }
  else
  {
    v2 = 1;
  }
  LeaveCriticalSection(this + 1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000edbc  mov     [rsp+arg_0], rbx
0x18000edc1  mov     [rsp+arg_8], rsi
0x18000edc6  push    rdi
0x18000edc7  sub     rsp, 20h
0x18000edcb  mov     rbx, rcx
0x18000edce  add     rcx, 28h ; '('; lpCriticalSection
0x18000edd2  call    cs:__imp_EnterCriticalSection
0x18000edd8  cmp     qword ptr [rbx+20h], 0
0x18000eddd  jnz     short loc_18000EDE6
0x18000eddf  mov     edi, 1
0x18000ede4  jmp     short loc_18000EE59
0x18000ede6  mov     rcx, [rbx+78h]
0x18000edea  mov     rax, [rcx]
0x18000eded  mov     rax, [rax+48h]
0x18000edf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edf6  mov     edi, eax
0x18000edf8  test    eax, eax
0x18000edfa  js      short loc_18000EE59
0x18000edfc  mov     edx, 2; unsigned int
0x18000ee01  mov     rcx, rbx; this
0x18000ee04  mov     [rbx+0A4h], edx
0x18000ee0a  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18000ee0f  mov     rcx, [rbx+78h]
0x18000ee13  mov     rax, [rcx]
0x18000ee16  mov     rax, [rax+50h]
0x18000ee1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee1f  xor     edi, edi
0x18000ee21  xchg    rdi, [rbx+20h]
0x18000ee25  test    rdi, rdi
0x18000ee28  jz      short loc_18000EE3F
0x18000ee2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ee2d  mov     rcx, rdi; hHandle
0x18000ee30  call    cs:__imp_WaitForSingleObject
0x18000ee36  mov     rcx, rdi; hObject
0x18000ee39  call    cs:__imp_CloseHandle
0x18000ee3f  mov     rcx, [rbx+98h]
0x18000ee46  test    rcx, rcx
0x18000ee49  jz      short loc_18000EE57
0x18000ee4b  mov     rax, [rcx]
0x18000ee4e  mov     rax, [rax+30h]
0x18000ee52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee57  xor     edi, edi
0x18000ee59  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000ee5d  call    cs:__imp_LeaveCriticalSection
0x18000ee63  mov     rbx, [rsp+28h+arg_0]
0x18000ee68  mov     eax, edi
0x18000ee6a  mov     rsi, [rsp+28h+arg_8]
0x18000ee6f  add     rsp, 20h
0x18000ee73  pop     rdi
0x18000ee74  retn
```
