# StackLockGrant::~StackLockGrant(void)

- ea: `0x18005ca14`
- end: `0x18005ca6b`
- name: `??1StackLockGrant@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(RTL_CONDITION_VARIABLE **this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180085ca3`
- `0x180085cc7`
- `0x180085cd9`
- `0x180088261`

## callees

- `0x180033600`
- `0x180037e40`
- `0x18005ca14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005ca64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005ca3a`

## pseudocode

```c
void __fastcall StackLockGrant::~StackLockGrant(RTL_CONDITION_VARIABLE **this)
{
  RTL_CONDITION_VARIABLE *v1; // rdi
  RtlSrwLock *v2; // rbx
  DWORD CurrentThreadId; // eax
  _DWORD *Ptr; // rcx

  v1 = *this;
  v2 = (RtlSrwLock *)&(*this)[1];
  RtlSrwLock::AcquireExclusive(v2);
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    Ptr = v1[3].Ptr;
    if ( Ptr[3] == CurrentThreadId )
      break;
    RtlConditionVariable::SleepInfinite(v1, (PSRWLOCK)v2);
  }
  *(_QWORD *)Ptr = 0;
  *((_DWORD *)v2 + 2) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)v2);
}

```

## disassembly

```asm
0x18005ca14  mov     [rsp+arg_0], rbx
0x18005ca19  push    rdi
0x18005ca1a  sub     rsp, 20h
0x18005ca1e  mov     rdi, [rcx]
0x18005ca21  lea     rbx, [rdi+8]
0x18005ca25  mov     rcx, rbx; this
0x18005ca28  call    ?AcquireExclusive@RtlSrwLock@@QEAAXXZ; RtlSrwLock::AcquireExclusive(void)
0x18005ca2d  jmp     short loc_18005CA3A
0x18005ca2f  mov     rdx, rbx; SRWLock
0x18005ca32  mov     rcx, rdi; ConditionVariable
0x18005ca35  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x18005ca3a  call    cs:__imp_GetCurrentThreadId
0x18005ca40  mov     rcx, [rdi+18h]
0x18005ca44  cmp     [rcx+0Ch], eax
0x18005ca47  jnz     short loc_18005CA2F
0x18005ca49  mov     qword ptr [rcx], 0
0x18005ca50  mov     rcx, rbx
0x18005ca53  mov     dword ptr [rbx+8], 0
0x18005ca5a  mov     rbx, [rsp+28h+arg_0]
0x18005ca5f  add     rsp, 20h
0x18005ca63  pop     rdi
0x18005ca64  jmp     cs:__imp_ReleaseSRWLockExclusive
```
