# CMMPullPin::PauseThread(void)

- ea: `0x18000e8b0`
- end: `0x18000e932`
- name: `?PauseThread@CMMPullPin@@IEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CMMPullPin *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180008110`
- `0x18000bbd0`
- `0x18000daf0`

## callees

- `0x180007054`
- `0x18000e8b0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e91a`
- `KERNEL32!LeaveCriticalSection` at `0x18000e91a`
- `KERNEL32!EnterCriticalSection` at `0x18000e8c6`
- `KERNEL32!EnterCriticalSection` at `0x18000e8c6`

## pseudocode

```c
__int64 __fastcall CMMPullPin::PauseThread(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // edi

  EnterCriticalSection(this + 1);
  if ( this->SpinCount )
  {
    v2 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 72LL))(this[3].DebugInfo);
    if ( v2 >= 0 )
    {
      HIDWORD(this[4].DebugInfo) = 0;
      v2 = CAMThread::CallWorker(this, 0);
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 80LL))(this[3].DebugInfo);
    }
  }
  else
  {
    v2 = -2147418113;
  }
  LeaveCriticalSection(this + 1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000e8b0  mov     [rsp+arg_0], rbx
0x18000e8b5  mov     [rsp+arg_8], rsi
0x18000e8ba  push    rdi
0x18000e8bb  sub     rsp, 20h
0x18000e8bf  mov     rbx, rcx
0x18000e8c2  add     rcx, 28h ; '('; lpCriticalSection
0x18000e8c6  call    cs:__imp_EnterCriticalSection
0x18000e8cc  cmp     qword ptr [rbx+20h], 0
0x18000e8d1  jnz     short loc_18000E8DA
0x18000e8d3  mov     edi, 8000FFFFh
0x18000e8d8  jmp     short loc_18000E916
0x18000e8da  mov     rcx, [rbx+78h]
0x18000e8de  mov     rax, [rcx]
0x18000e8e1  mov     rax, [rax+48h]
0x18000e8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ea  mov     edi, eax
0x18000e8ec  test    eax, eax
0x18000e8ee  js      short loc_18000E916
0x18000e8f0  xor     edx, edx; unsigned int
0x18000e8f2  mov     dword ptr [rbx+0A4h], 0
0x18000e8fc  mov     rcx, rbx; this
0x18000e8ff  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18000e904  mov     rcx, [rbx+78h]
0x18000e908  mov     edi, eax
0x18000e90a  mov     rax, [rcx]
0x18000e90d  mov     rax, [rax+50h]
0x18000e911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e916  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000e91a  call    cs:__imp_LeaveCriticalSection
0x18000e920  mov     rbx, [rsp+28h+arg_0]
0x18000e925  mov     eax, edi
0x18000e927  mov     rsi, [rsp+28h+arg_8]
0x18000e92c  add     rsp, 20h
0x18000e930  pop     rdi
0x18000e931  retn
```
