# EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)

- ea: `0x18000d7ec`
- end: `0x18000d89e`
- name: `?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `54`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd98`
- `0x18000c20c`
- `0x18000e86c`
- `0x18000f034`
- `0x18000f624`
- `0x18000f7bc`
- `0x180010dc4`
- `0x18002faf0`
- `0x18004d664`
- `0x180067bfc`
- `0x180068628`
- `0x180069650`
- `0x18006ae00`
- `0x18006da7c`
- `0x18006ed34`
- `0x18009e458`
- `0x18009f78c`
- `0x18009ffa4`
- `0x1800a0058`
- `0x1800a0130`
- `0x1800a02b0`
- `0x1800a1c08`
- `0x1800a20d0`
- `0x1800a2180`
- `0x1800a26e8`
- `0x1800a36b4`
- `0x1800a422c`
- `0x1800a47d4`
- `0x1800a52ec`
- `0x1800a9538`
- `0x1800b0140`
- `0x1800b04c4`
- `0x1800b0ef8`
- `0x1800b24c0`
- `0x1800b2858`
- `0x1800b2b5c`
- `0x1800b2f84`
- `0x1800b3034`
- `0x1800b3b3c`
- `0x1800b3c24`
- `0x1800b3d58`
- `0x1800b41a0`
- `0x1800b46c4`
- `0x1800b4790`
- `0x1800b4ae0`
- `0x1800b5110`
- `0x1800b5858`
- `0x1800b61b4`
- `0x1800b8630`
- `0x1800b92dc`

## callees

- `0x18000d7ec`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d809`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d886`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d886`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d82a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d82a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EventLogger::LogGenericEvent(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  DWORD CurrentThreadId; // r12d
  _QWORD *v10; // rsi
  __int64 v11; // rbp

  CurrentThreadId = GetCurrentThreadId();
  if ( dword_180142E08 )
  {
    EnterCriticalSection(&EventLogger::lock_);
    v10 = (_QWORD *)EventLogger::eventSinks_;
    v11 = EventLogger::eventSinks_ + 8 * ((__int64)(*(&EventLogger::eventSinks_ + 1) - EventLogger::eventSinks_) >> 3);
    while ( v10 != (_QWORD *)v11 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int))(*(_QWORD *)*v10 + 24LL))(
        *v10,
        0,
        CurrentThreadId,
        a1,
        a2,
        a3,
        a4,
        a5);
      ++v10;
    }
    LeaveCriticalSection(&EventLogger::lock_);
  }
}

```

## disassembly

```asm
0x18000d7ec  push    rbx
0x18000d7ee  push    rbp
0x18000d7ef  push    rsi
0x18000d7f0  push    rdi
0x18000d7f1  push    r12
0x18000d7f3  push    r13
0x18000d7f5  push    r14
0x18000d7f7  push    r15
0x18000d7f9  sub     rsp, 58h
0x18000d7fd  mov     r14, r9
0x18000d800  mov     rbx, r8
0x18000d803  mov     rdi, rdx
0x18000d806  mov     r15d, ecx
0x18000d809  call    cs:__imp_GetCurrentThreadId
0x18000d80f  mov     r12d, eax
0x18000d812  cmp     cs:dword_180142E08, 0
0x18000d819  jz      short loc_18000D88D
0x18000d81b  mov     r13, [rsp+98h+arg_20]
0x18000d823  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000d82a  call    cs:__imp_EnterCriticalSection
0x18000d830  mov     rsi, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000d837  mov     rcx, qword ptr cs:?eventSinks_@EventLogger@@0VEventSinkVec@1@A+8; EventLogger::EventSinkVec EventLogger::eventSinks_
0x18000d83e  sub     rcx, rsi
0x18000d841  sar     rcx, 3
0x18000d845  lea     rbp, [rsi+rcx*8]
0x18000d849  jmp     short loc_18000D87A
0x18000d84b  mov     rcx, [rsi]
0x18000d84e  mov     rax, [rcx]
0x18000d851  mov     [rsp+98h+var_60], r13d
0x18000d856  mov     [rsp+98h+var_68], r14
0x18000d85b  mov     [rsp+98h+var_70], rbx
0x18000d860  mov     [rsp+98h+var_78], rdi
0x18000d865  mov     r9d, r15d
0x18000d868  mov     r8d, r12d
0x18000d86b  xor     edx, edx
0x18000d86d  mov     rax, [rax+18h]
0x18000d871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d876  add     rsi, 8
0x18000d87a  cmp     rsi, rbp
0x18000d87d  jnz     short loc_18000D84B
0x18000d87f  lea     rcx, ?lock_@EventLogger@@0VLock@@A; lpCriticalSection
0x18000d886  call    cs:__imp_LeaveCriticalSection
0x18000d88c  nop
0x18000d88d  add     rsp, 58h
0x18000d891  pop     r15
0x18000d893  pop     r14
0x18000d895  pop     r13
0x18000d897  pop     r12
0x18000d899  pop     rdi
0x18000d89a  pop     rsi
0x18000d89b  pop     rbp
0x18000d89c  pop     rbx
0x18000d89d  retn
```
