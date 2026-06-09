# CRealTimePen::FinalRelease(void)

- ea: `0x1800f8db0`
- end: `0x1800f8ed7`
- name: `?FinalRelease@CRealTimePen@@QEAAXXZ`
- size: `295`
- prototype: `void __fastcall(CRealTimePen *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800486cc`
- `0x180049254`

## callees

- `0x1800217b0`
- `0x1800f88dc`
- `0x1800f8db0`
- `0x1800fa3a8`
- `0x180101ca8`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8ea6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8eb3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8ebc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8ea6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8eb3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8ebc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f8dcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f8dcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8e02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f8e02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f8dd6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800f8dee`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableCS` at `0x1800f8dee`

## pseudocode

```c
void __fastcall CRealTimePen::FinalRelease(CRealTimePen *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  *((_BYTE *)this + 116) = 1;
  *((_DWORD *)this + 30) = GetCurrentThreadId();
  while ( _InterlockedCompareExchange((volatile signed __int32 *)this + 28, 0, 0) )
    SleepConditionVariableCS((PCONDITION_VARIABLE)this + 13, v2, 0x32u);
  LeaveCriticalSection(v2);
  try
  {
    (*(void (**)(void))(*(_QWORD *)this + 56LL))();
    (*(void (__fastcall **)(char *, _QWORD, __int64))(*((_QWORD *)this + 1) + 56LL))((char *)this + 8, 0, 1);
    CRealTimePen::RemoveAllSinks(this);
    ATL::AtlComPtrAssign((struct IUnknown **)this + 36, 0);
    CSubWndMgr::UnsubclassRtp(this);
    v3 = *((_QWORD *)this + 42);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 64LL))(v3, 0);
      ATL::AtlComPtrAssign((struct IUnknown **)this + 42, 0);
    }
    *((_QWORD *)this + 44) = 0;
    CRealTimePen::DestroyQueueThread(this);
    (*(void (__fastcall **)(CRealTimePen *, __int64))(*(_QWORD *)this + 64LL))(this, 15);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
    DeleteCriticalSection(v2);
  }
  catch ( long v4 )
  {
    return;
  }
  catch ( ... )
  {
    ReportWispException();
  }
}

```

## disassembly

```asm
0x1800f8db0  mov     [rsp+arg_8], rbx
0x1800f8db5  mov     [rsp+arg_10], rsi
0x1800f8dba  push    rdi
0x1800f8dbb  sub     rsp, 30h
0x1800f8dbf  mov     rbx, rcx
0x1800f8dc2  lea     rsi, [rcx+80h]
0x1800f8dc9  mov     rcx, rsi; lpCriticalSection
0x1800f8dcc  call    cs:__imp_EnterCriticalSection
0x1800f8dd2  mov     byte ptr [rbx+74h], 1
0x1800f8dd6  call    cs:__imp_GetCurrentThreadId
0x1800f8ddc  mov     [rbx+78h], eax
0x1800f8ddf  jmp     short loc_1800F8DF4
0x1800f8de1  mov     r8d, 32h ; '2'; dwMilliseconds
0x1800f8de7  mov     rdx, rsi; CriticalSection
0x1800f8dea  lea     rcx, [rbx+68h]; ConditionVariable
0x1800f8dee  call    cs:__imp_SleepConditionVariableCS
0x1800f8df4  xor     ecx, ecx
0x1800f8df6  xor     eax, eax
0x1800f8df8  lock cmpxchg [rbx+70h], ecx
0x1800f8dfd  jnz     short loc_1800F8DE1
0x1800f8dff  mov     rcx, rsi; lpCriticalSection
0x1800f8e02  call    cs:__imp_LeaveCriticalSection
0x1800f8e08  nop
0x1800f8e09  mov     rax, [rbx]
0x1800f8e0c  mov     edx, 0Fh
0x1800f8e11  mov     rcx, rbx
0x1800f8e14  mov     rax, [rax+38h]
0x1800f8e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8e1d  lea     rcx, [rbx+8]
0x1800f8e21  mov     rax, [rcx]
0x1800f8e24  xor     edx, edx
0x1800f8e26  lea     r8d, [rdx+1]
0x1800f8e2a  mov     rax, [rax+38h]
0x1800f8e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8e33  mov     rcx, rbx; this
0x1800f8e36  call    ?RemoveAllSinks@CRealTimePen@@AEAAJXZ; CRealTimePen::RemoveAllSinks(void)
0x1800f8e3b  lea     rcx, [rbx+120h]; struct IUnknown **
0x1800f8e42  xor     edx, edx; struct IUnknown *
0x1800f8e44  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f8e49  mov     rcx, rbx; struct IRealTimePen *
0x1800f8e4c  call    ?UnsubclassRtp@CSubWndMgr@@SAJPEAUIRealTimePen@@@Z; CSubWndMgr::UnsubclassRtp(IRealTimePen *)
0x1800f8e51  lea     rdi, [rbx+150h]
0x1800f8e58  mov     rcx, [rdi]
0x1800f8e5b  test    rcx, rcx
0x1800f8e5e  jz      short loc_1800F8E78
0x1800f8e60  mov     rax, [rcx]
0x1800f8e63  xor     edx, edx
0x1800f8e65  mov     rax, [rax+40h]
0x1800f8e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8e6e  xor     edx, edx; struct IUnknown *
0x1800f8e70  mov     rcx, rdi; struct IUnknown **
0x1800f8e73  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f8e78  mov     qword ptr [rbx+160h], 0
0x1800f8e83  mov     rcx, rbx; this
0x1800f8e86  call    ?DestroyQueueThread@CRealTimePen@@AEAAJXZ; CRealTimePen::DestroyQueueThread(void)
0x1800f8e8b  mov     rax, [rbx]
0x1800f8e8e  mov     edx, 0Fh
0x1800f8e93  mov     rcx, rbx
0x1800f8e96  mov     rax, [rax+40h]
0x1800f8e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8e9f  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x1800f8ea6  call    cs:__imp_DeleteCriticalSection
0x1800f8eac  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x1800f8eb3  call    cs:__imp_DeleteCriticalSection
0x1800f8eb9  mov     rcx, rsi; lpCriticalSection
0x1800f8ebc  call    cs:__imp_DeleteCriticalSection
0x1800f8ec2  nop
0x1800f8ec3  jmp     short loc_1800F8EC7
0x1800f8ec5  jmp     short $+2
0x1800f8ec7  mov     rbx, [rsp+38h+arg_8]
0x1800f8ecc  mov     rsi, [rsp+38h+arg_10]
0x1800f8ed1  add     rsp, 30h
0x1800f8ed5  pop     rdi
0x1800f8ed6  retn
```
