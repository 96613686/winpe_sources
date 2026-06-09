# CMMPullPin::StartThread(void)

- ea: `0x18000ed0c`
- end: `0x18000edb5`
- name: `?StartThread@CMMPullPin@@QEAAJXZ`
- size: `169`
- prototype: `__int64 __fastcall(CMMPullPin *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180008110`
- `0x18000bbd0`

## callees

- `0x180007054`
- `0x180007114`
- `0x18000ed0c`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ed6b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed8d`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed9a`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed6b`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed8d`
- `KERNEL32!LeaveCriticalSection` at `0x18000ed9a`
- `KERNEL32!EnterCriticalSection` at `0x18000ed25`
- `KERNEL32!EnterCriticalSection` at `0x18000ed25`

## pseudocode

```c
__int64 __fastcall CMMPullPin::StartThread(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  ULONG_PTR SpinCount; // rcx
  int v4; // esi
  unsigned int v6; // ebx

  v1 = this + 1;
  EnterCriticalSection(this + 1);
  SpinCount = this[3].SpinCount;
  if ( SpinCount && this[3].DebugInfo )
  {
    if ( !this->SpinCount )
    {
      v4 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 40LL))(SpinCount);
      if ( v4 < 0 )
      {
LABEL_7:
        LeaveCriticalSection(v1);
        return (unsigned int)v4;
      }
      if ( !CAMThread::Create(this) )
      {
        v4 = -2147467259;
        goto LABEL_7;
      }
    }
    HIDWORD(this[4].DebugInfo) = 1;
    v6 = CAMThread::CallWorker(this, 1);
    LeaveCriticalSection(v1);
    return v6;
  }
  else
  {
    LeaveCriticalSection(v1);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x18000ed0c  mov     [rsp+arg_0], rbx
0x18000ed11  mov     [rsp+arg_8], rsi
0x18000ed16  push    rdi
0x18000ed17  sub     rsp, 20h
0x18000ed1b  lea     rdi, [rcx+28h]
0x18000ed1f  mov     rbx, rcx
0x18000ed22  mov     rcx, rdi; lpCriticalSection
0x18000ed25  call    cs:__imp_EnterCriticalSection
0x18000ed2b  mov     rcx, [rbx+98h]
0x18000ed32  test    rcx, rcx
0x18000ed35  jz      short loc_18000ED97
0x18000ed37  cmp     qword ptr [rbx+78h], 0
0x18000ed3c  jz      short loc_18000ED97
0x18000ed3e  cmp     qword ptr [rbx+20h], 0
0x18000ed43  jnz     short loc_18000ED75
0x18000ed45  mov     rax, [rcx]
0x18000ed48  mov     rax, [rax+28h]
0x18000ed4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed51  mov     esi, eax
0x18000ed53  test    eax, eax
0x18000ed55  js      short loc_18000ED68
0x18000ed57  mov     rcx, rbx; this
0x18000ed5a  call    ?Create@CAMThread@@QEAAHXZ; CAMThread::Create(void)
0x18000ed5f  test    eax, eax
0x18000ed61  jnz     short loc_18000ED75
0x18000ed63  mov     esi, 80004005h
0x18000ed68  mov     rcx, rdi; lpCriticalSection
0x18000ed6b  call    cs:__imp_LeaveCriticalSection
0x18000ed71  mov     eax, esi
0x18000ed73  jmp     short loc_18000EDA5
0x18000ed75  mov     edx, 1; unsigned int
0x18000ed7a  mov     rcx, rbx; this
0x18000ed7d  mov     [rbx+0A4h], edx
0x18000ed83  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18000ed88  mov     rcx, rdi; lpCriticalSection
0x18000ed8b  mov     ebx, eax
0x18000ed8d  call    cs:__imp_LeaveCriticalSection
0x18000ed93  mov     eax, ebx
0x18000ed95  jmp     short loc_18000EDA5
0x18000ed97  mov     rcx, rdi; lpCriticalSection
0x18000ed9a  call    cs:__imp_LeaveCriticalSection
0x18000eda0  mov     eax, 8000FFFFh
0x18000eda5  mov     rbx, [rsp+28h+arg_0]
0x18000edaa  mov     rsi, [rsp+28h+arg_8]
0x18000edaf  add     rsp, 20h
0x18000edb3  pop     rdi
0x18000edb4  retn
```
