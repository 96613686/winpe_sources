# AcquiredStackLock::Initialize(StackLock &,unsigned __int64)

- ea: `0x180033540`
- end: `0x1800335f8`
- name: `?Initialize@AcquiredStackLock@@IEAAXAEAVStackLock@@_K@Z`
- size: `184`
- prototype: `void(AcquiredStackLock *__hidden this, struct StackLock *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180029628`

## callees

- `0x180033540`
- `0x180033600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800335ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800335ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033562`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180033562`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033568`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003359e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033568`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003359e`

## pseudocode

```c
void __fastcall AcquiredStackLock::Initialize(RTL_SRWLOCK *this, RTL_SRWLOCK *a2, __int64 a3)
{
  DWORD CurrentThreadId; // eax
  _DWORD *Ptr; // rcx

  this->Ptr = a2;
  AcquireSRWLockExclusive(a2 + 1);
  LODWORD(a2[2].Ptr) = GetCurrentThreadId();
  while ( 1 )
  {
    if ( !a2[3].Ptr )
    {
LABEL_5:
      this[1].Ptr = 0;
      LODWORD(this[2].Ptr) = 1;
      HIDWORD(this[2].Ptr) = GetCurrentThreadId();
      this[3].Ptr = a2[3].Ptr;
      a2[3].Ptr = &this[1];
      goto LABEL_6;
    }
    CurrentThreadId = GetCurrentThreadId();
    Ptr = a2[3].Ptr;
    if ( Ptr[3] == CurrentThreadId )
      break;
    if ( !Ptr || a3 == *(_QWORD *)Ptr && a3 )
      goto LABEL_5;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)a2, a2 + 1);
  }
  ++Ptr[2];
LABEL_6:
  LODWORD(a2[2].Ptr) = 0;
  ReleaseSRWLockExclusive(a2 + 1);
  LOBYTE(this[4].Ptr) = 1;
}

```

## disassembly

```asm
0x180033540  mov     [rsp+arg_8], rbx
0x180033545  mov     [rsp+arg_10], rbp
0x18003354a  push    rsi
0x18003354b  push    rdi
0x18003354c  push    r14
0x18003354e  sub     rsp, 20h
0x180033552  mov     r14, rcx
0x180033555  mov     [rcx], rdx
0x180033558  lea     rcx, [rdx+8]; SRWLock
0x18003355c  mov     rbx, r8
0x18003355f  mov     rsi, rdx
0x180033562  call    cs:__imp_AcquireSRWLockExclusive
0x180033568  call    cs:__imp_GetCurrentThreadId
0x18003356e  mov     [rsi+10h], eax
0x180033571  xor     ebp, ebp
0x180033573  cmp     [rsi+18h], rbp
0x180033577  jz      short loc_18003358D
0x180033579  call    cs:__imp_GetCurrentThreadId
0x18003357f  mov     rcx, [rsi+18h]
0x180033583  cmp     [rcx+0Ch], eax
0x180033586  jz      short loc_1800335D8
0x180033588  test    rcx, rcx
0x18003358b  jnz     short loc_1800335DD
0x18003358d  lea     rax, [r14+8]
0x180033591  mov     rbx, rax
0x180033594  mov     [rax], rbp
0x180033597  mov     dword ptr [rax+8], 1
0x18003359e  call    cs:__imp_GetCurrentThreadId
0x1800335a4  mov     [rbx+0Ch], eax
0x1800335a7  mov     rax, [rsi+18h]
0x1800335ab  mov     [rbx+10h], rax
0x1800335af  mov     [rsi+18h], rbx
0x1800335b3  lea     rcx, [rsi+8]; SRWLock
0x1800335b7  mov     [rsi+10h], ebp
0x1800335ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800335c0  mov     rbx, [rsp+38h+arg_8]
0x1800335c5  mov     rbp, [rsp+38h+arg_10]
0x1800335ca  mov     byte ptr [r14+20h], 1
0x1800335cf  add     rsp, 20h
0x1800335d3  pop     r14
0x1800335d5  pop     rdi
0x1800335d6  pop     rsi
0x1800335d7  retn
0x1800335d8  inc     dword ptr [rcx+8]
0x1800335db  jmp     short loc_1800335B3
0x1800335dd  cmp     rbx, [rcx]
0x1800335e0  jnz     short loc_1800335E7
0x1800335e2  test    rbx, rbx
0x1800335e5  jnz     short loc_18003358D
0x1800335e7  lea     rdx, [rsi+8]; SRWLock
0x1800335eb  mov     rcx, rsi; ConditionVariable
0x1800335ee  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x1800335f3  jmp     loc_180033571
```
