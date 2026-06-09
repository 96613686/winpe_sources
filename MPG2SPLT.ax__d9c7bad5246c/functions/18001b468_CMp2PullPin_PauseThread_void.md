# CMp2PullPin::PauseThread(void)

- ea: `0x18001b468`
- end: `0x18001b4ea`
- name: `?PauseThread@CMp2PullPin@@QEAAJXZ`
- size: `130`
- prototype: `__int64 __fastcall(CMp2PullPin *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bb8c`

## callees

- `0x180007054`
- `0x18001b468`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001b4d2`
- `KERNEL32!LeaveCriticalSection` at `0x18001b4d2`
- `KERNEL32!EnterCriticalSection` at `0x18001b47e`
- `KERNEL32!EnterCriticalSection` at `0x18001b47e`

## pseudocode

```c
__int64 __fastcall CMp2PullPin::PauseThread(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // edi

  EnterCriticalSection(this + 1);
  if ( this->SpinCount )
  {
    v2 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)this[3].DebugInfo + 72LL))(this[3].DebugInfo);
    if ( v2 >= 0 )
    {
      HIDWORD(this[4].OwningThread) = 0;
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
0x18001b468  mov     [rsp+arg_0], rbx
0x18001b46d  mov     [rsp+arg_8], rsi
0x18001b472  push    rdi
0x18001b473  sub     rsp, 20h
0x18001b477  mov     rbx, rcx
0x18001b47a  add     rcx, 28h ; '('; lpCriticalSection
0x18001b47e  call    cs:__imp_EnterCriticalSection
0x18001b484  cmp     qword ptr [rbx+20h], 0
0x18001b489  jnz     short loc_18001B492
0x18001b48b  mov     edi, 8000FFFFh
0x18001b490  jmp     short loc_18001B4CE
0x18001b492  mov     rcx, [rbx+78h]
0x18001b496  mov     rax, [rcx]
0x18001b499  mov     rax, [rax+48h]
0x18001b49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a2  mov     edi, eax
0x18001b4a4  test    eax, eax
0x18001b4a6  js      short loc_18001B4CE
0x18001b4a8  xor     edx, edx; unsigned int
0x18001b4aa  mov     dword ptr [rbx+0B4h], 0
0x18001b4b4  mov     rcx, rbx; this
0x18001b4b7  call    ?CallWorker@CAMThread@@QEAAKK@Z; CAMThread::CallWorker(ulong)
0x18001b4bc  mov     rcx, [rbx+78h]
0x18001b4c0  mov     edi, eax
0x18001b4c2  mov     rax, [rcx]
0x18001b4c5  mov     rax, [rax+50h]
0x18001b4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ce  lea     rcx, [rbx+28h]; lpCriticalSection
0x18001b4d2  call    cs:__imp_LeaveCriticalSection
0x18001b4d8  mov     rbx, [rsp+28h+arg_0]
0x18001b4dd  mov     eax, edi
0x18001b4df  mov     rsi, [rsp+28h+arg_8]
0x18001b4e4  add     rsp, 20h
0x18001b4e8  pop     rdi
0x18001b4e9  retn
```
