# TransactionStackLock::TransactionStackLock(NetSetupTransaction &)

- ea: `0x180013c20`
- end: `0x180013d0f`
- name: `??0TransactionStackLock@@QEAA@AEAVNetSetupTransaction@@@Z`
- size: `239`
- prototype: `TransactionStackLock *__fastcall(TransactionStackLock *__hidden this, struct NetSetupTransaction *)`
- caller_count: `9`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011e54`
- `0x180012220`
- `0x1800154ac`
- `0x180045544`
- `0x180067594`
- `0x180067670`
- `0x180067b00`
- `0x180067c60`
- `0x180067cc0`

## callees

- `0x180013c20`
- `0x180033600`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013cce`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013c77`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013c77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013c5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013c5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013cb1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
TransactionStackLock *__fastcall TransactionStackLock::TransactionStackLock(
        TransactionStackLock *this,
        struct NetSetupTransaction *a2)
{
  char *v2; // rsi
  __int64 v5; // r13
  DWORD v6; // ecx
  unsigned int Value; // eax
  __int64 v8; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  TransactionStackLock *result; // rax

  v2 = (char *)this + 8;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v5 = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 32) = 0;
  v6 = *((_DWORD *)a2 + 214);
  if ( v6 != -1 )
  {
    Value = (unsigned int)TlsGetValue(v6);
    if ( Value )
      v5 = Value;
  }
  v8 = *((_QWORD *)a2 + 113);
  *(_QWORD *)this = v8;
  AcquireSRWLockExclusive((PSRWLOCK)(v8 + 8));
  *(_DWORD *)(v8 + 16) = GetCurrentThreadId();
  while ( 1 )
  {
    if ( !*(_QWORD *)(v8 + 24) )
    {
LABEL_8:
      *((_DWORD *)v2 + 2) = 1;
      *(_QWORD *)v2 = 0;
      *((_DWORD *)v2 + 3) = GetCurrentThreadId();
      *((_QWORD *)v2 + 2) = *(_QWORD *)(v8 + 24);
      *(_QWORD *)(v8 + 24) = v2;
      goto LABEL_9;
    }
    CurrentThreadId = GetCurrentThreadId();
    v10 = *(_QWORD *)(v8 + 24);
    if ( *(_DWORD *)(v10 + 12) == CurrentThreadId )
      break;
    if ( !v10 || v5 == *(_QWORD *)v10 && v5 )
      goto LABEL_8;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)v8, (PSRWLOCK)(v8 + 8));
  }
  ++*(_DWORD *)(v10 + 8);
LABEL_9:
  *(_DWORD *)(v8 + 16) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v8 + 8));
  result = this;
  *((_BYTE *)this + 32) = 1;
  return result;
}

```

## disassembly

```asm
0x180013c20  push    rbx
0x180013c22  push    rbp
0x180013c23  push    rsi
0x180013c24  push    rdi
0x180013c25  push    r12
0x180013c27  push    r13
0x180013c29  push    r14
0x180013c2b  push    r15
0x180013c2d  sub     rsp, 28h
0x180013c31  xor     eax, eax
0x180013c33  lea     rsi, [rcx+8]
0x180013c37  mov     [rcx], rax
0x180013c3a  mov     rbx, rcx
0x180013c3d  mov     [rsi], rax
0x180013c40  mov     rbp, rdx
0x180013c43  mov     [rsi+8], rax
0x180013c47  mov     r13d, eax
0x180013c4a  mov     [rsi+10h], rax
0x180013c4e  mov     [rcx+20h], al
0x180013c51  mov     ecx, [rdx+358h]; dwTlsIndex
0x180013c57  cmp     ecx, 0FFFFFFFFh
0x180013c5a  jz      short loc_180013C69
0x180013c5c  call    cs:__imp_TlsGetValue
0x180013c62  test    eax, eax
0x180013c64  jz      short loc_180013C69
0x180013c66  mov     r13d, eax
0x180013c69  mov     rbp, [rbp+388h]
0x180013c70  mov     [rbx], rbp
0x180013c73  lea     rcx, [rbp+8]; SRWLock
0x180013c77  call    cs:__imp_AcquireSRWLockExclusive
0x180013c7d  call    cs:__imp_GetCurrentThreadId
0x180013c83  mov     [rbp+10h], eax
0x180013c86  cmp     qword ptr [rbp+18h], 0
0x180013c8b  jz      short loc_180013CA1
0x180013c8d  call    cs:__imp_GetCurrentThreadId
0x180013c93  mov     rcx, [rbp+18h]
0x180013c97  cmp     [rcx+0Ch], eax
0x180013c9a  jz      short loc_180013CEC
0x180013c9c  test    rcx, rcx
0x180013c9f  jnz     short loc_180013CF4
0x180013ca1  mov     rax, rsi
0x180013ca4  mov     dword ptr [rsi+8], 1
0x180013cab  xor     r13d, r13d
0x180013cae  mov     [rax], r13
0x180013cb1  call    cs:__imp_GetCurrentThreadId
0x180013cb7  mov     [rsi+0Ch], eax
0x180013cba  mov     rax, [rbp+18h]
0x180013cbe  mov     [rsi+10h], rax
0x180013cc2  mov     [rbp+18h], rsi
0x180013cc6  lea     rcx, [rbp+8]; SRWLock
0x180013cca  mov     [rbp+10h], r13d
0x180013cce  call    cs:__imp_ReleaseSRWLockExclusive
0x180013cd4  mov     rax, rbx
0x180013cd7  mov     byte ptr [rbx+20h], 1
0x180013cdb  add     rsp, 28h
0x180013cdf  pop     r15
0x180013ce1  pop     r14
0x180013ce3  pop     r13
0x180013ce5  pop     r12
0x180013ce7  pop     rdi
0x180013ce8  pop     rsi
0x180013ce9  pop     rbp
0x180013cea  pop     rbx
0x180013ceb  retn
0x180013cec  inc     dword ptr [rcx+8]
0x180013cef  xor     r13d, r13d
0x180013cf2  jmp     short loc_180013CC6
0x180013cf4  cmp     r13, [rcx]
0x180013cf7  jnz     short loc_180013CFE
0x180013cf9  test    r13, r13
0x180013cfc  jnz     short loc_180013CA1
0x180013cfe  lea     rdx, [rbp+8]; SRWLock
0x180013d02  mov     rcx, rbp; ConditionVariable
0x180013d05  call    ?SleepInfinite@RtlConditionVariable@@QEAAXAEAVRtlSrwLock@@@Z; RtlConditionVariable::SleepInfinite(RtlSrwLock &)
0x180013d0a  jmp     loc_180013C86
```
