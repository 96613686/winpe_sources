# CMp2PullPin::StopThread(void)

- ea: `0x18001bd30`
- end: `0x18001bde9`
- name: `?StopThread@CMp2PullPin@@IEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CMp2PullPin *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b068`
- `0x18001b300`
- `0x18001b320`

## callees

- `0x180007054`
- `0x18001bd30`
- `0x180034010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001bda4`
- `KERNEL32!WaitForSingleObject` at `0x18001bda4`
- `KERNEL32!CloseHandle` at `0x18001bdad`
- `KERNEL32!CloseHandle` at `0x18001bdad`
- `KERNEL32!LeaveCriticalSection` at `0x18001bdd1`
- `KERNEL32!LeaveCriticalSection` at `0x18001bdd1`
- `KERNEL32!EnterCriticalSection` at `0x18001bd46`
- `KERNEL32!EnterCriticalSection` at `0x18001bd46`

## pseudocode

```c
__int64 __fastcall CMp2PullPin::StopThread(struct _RTL_CRITICAL_SECTION *this)
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
      HIDWORD(this[4].OwningThread) = 2;
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
0x18001bd30  mov     [rsp+arg_0], rbx
0x18001bd35  mov     [rsp+arg_8], rsi
0x18001bd3a  push    rdi
0x18001bd3b  sub     rsp, 20h
0x18001bd3f  mov     rbx, rcx
0x18001bd42  add     rcx, 28h ; '('; lpCriticalSection
0x18001bd46  call    cs:__imp_EnterCriticalSection
0x18001bd4c  cmp     qword ptr [rbx+20h], 0
0x18001bd51  jnz     short loc_18001BD5A
0x18001bd53  mov     edi, 1
0x18001bd58  jmp     short loc_18001BDCD
0x18001bd5a  mov     rcx, [rbx+78h]
0x18001bd5e  mov     rax, [rcx]
0x18001bd61  mov     rax, [rax+48h]
0x18001bd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd6a  mov     edi, eax
0x18001bd6c  test    eax, eax
0x18001bd6e  js      short loc_18001BDCD
0x18001bd70  mov     edx, 2; unsigned int
0x18001bd75  mov     rcx, rbx; this
0x18001bd78  mov     [rbx+0B4h], edx
0x18001bd7e  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18001bd83  mov     rcx, [rbx+78h]
0x18001bd87  mov     rax, [rcx]
0x18001bd8a  mov     rax, [rax+50h]
0x18001bd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd93  xor     edi, edi
0x18001bd95  xchg    rdi, [rbx+20h]
0x18001bd99  test    rdi, rdi
0x18001bd9c  jz      short loc_18001BDB3
0x18001bd9e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001bda1  mov     rcx, rdi; hHandle
0x18001bda4  call    cs:__imp_WaitForSingleObject
0x18001bdaa  mov     rcx, rdi; hObject
0x18001bdad  call    cs:__imp_CloseHandle
0x18001bdb3  mov     rcx, [rbx+98h]
0x18001bdba  test    rcx, rcx
0x18001bdbd  jz      short loc_18001BDCB
0x18001bdbf  mov     rax, [rcx]
0x18001bdc2  mov     rax, [rax+30h]
0x18001bdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdcb  xor     edi, edi
0x18001bdcd  lea     rcx, [rbx+28h]; lpCriticalSection
0x18001bdd1  call    cs:__imp_LeaveCriticalSection
0x18001bdd7  mov     rbx, [rsp+28h+arg_0]
0x18001bddc  mov     eax, edi
0x18001bdde  mov     rsi, [rsp+28h+arg_8]
0x18001bde3  add     rsp, 20h
0x18001bde7  pop     rdi
0x18001bde8  retn
```
