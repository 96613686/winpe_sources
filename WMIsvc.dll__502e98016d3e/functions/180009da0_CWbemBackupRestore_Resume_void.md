# CWbemBackupRestore::Resume(void)

- ea: `0x180009da0`
- end: `0x180009f70`
- name: `?Resume@CWbemBackupRestore@@UEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(CWbemBackupRestore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004f44`

## callees

- `0x180009da0`
- `0x180009f78`
- `0x180014d24`
- `0x180014ddc`
- `0x180014f74`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ee4`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180009e38`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180009e38`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009ead`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180009ead`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009dcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e5c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009dcb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009e5c`
- `wbemcomn!GetMemLogObject` at `0x180009dbb`
- `wbemcomn!GetMemLogObject` at `0x180009e4c`
- `wbemcomn!GetMemLogObject` at `0x180009dbb`
- `wbemcomn!GetMemLogObject` at `0x180009e4c`

## pseudocode

```c
__int64 __fastcall CWbemBackupRestore::Resume(CWbemBackupRestore *this)
{
  CMemoryLog *MemLogObject; // rax
  unsigned int v3; // ebx
  __int64 v4; // r8
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  CMemoryLog *v8; // rax
  __int64 v9; // r8
  void *v10; // rdx
  __int64 v11; // r14
  _QWORD *v12; // rcx
  __int64 v13; // rbx
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  ULONG BackTraceHash; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_DWORD *)this + 16) )
  {
    MemLogObject = GetMemLogObject();
    v3 = -2147217386;
    CMemoryLog::Write(MemLogObject, -2147217386);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v4, this, -2147217386);
    }
    return v3;
  }
  *((_DWORD *)this + 22) |= 8u;
  CurrentThreadId = GetCurrentThreadId();
  BackTraceHash = 0;
  *((_DWORD *)this + 23) = CurrentThreadId;
  RtlCaptureStackBackTrace(0, 8u, (PVOID *)this + 12, &BackTraceHash);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 17, 1, 0) )
  {
    v8 = GetMemLogObject();
    v3 = -2147217303;
    CMemoryLog::Write(v8, -2147217303);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v9, this, -2147217303);
    }
    return v3;
  }
  v10 = (void *)*((_QWORD *)this + 5);
  v11 = 0;
  if ( !v10 )
    goto LABEL_20;
  v11 = *((_QWORD *)this + 5);
  if ( DeleteTimerQueueTimer(0, v10, (HANDLE)0xFFFFFFFFFFFFFFFFLL) || GetLastError() == 997 )
  {
    _InterlockedExchange64((volatile __int64 *)this + 5, 0);
    (*(void (__fastcall **)(CWbemBackupRestore *))(*(_QWORD *)this + 16LL))(this);
    goto LABEL_20;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
LABEL_21:
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 && *((_BYTE *)v12 + 25) >= 5u )
        WPP_SF_qqq(v12[2], v10, v7, this, *((_QWORD *)this + 7), v11);
      return CWbemBackupRestore::pResume(this);
    }
    v13 = *((_QWORD *)this + 7);
    LastError = GetLastError();
    WPP_SF_qDqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, *((_QWORD *)this + 5), LastError, this, v13);
LABEL_20:
    v12 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  return CWbemBackupRestore::pResume(this);
}

```

## disassembly

```asm
0x180009da0  mov     [rsp+arg_8], rbx
0x180009da5  mov     [rsp+arg_10], rbp
0x180009daa  push    rsi
0x180009dab  push    rdi
0x180009dac  push    r14
0x180009dae  sub     rsp, 40h
0x180009db2  cmp     dword ptr [rcx+40h], 0
0x180009db6  mov     rdi, rcx
0x180009db9  jnz     short loc_180009E13
0x180009dbb  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009dc1  mov     ebx, 80041016h
0x180009dc6  mov     rcx, rax
0x180009dc9  mov     edx, ebx
0x180009dcb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dd8  lea     rsi, WPP_GLOBAL_Control
0x180009ddf  cmp     rcx, rsi
0x180009de2  jz      short loc_180009E0C
0x180009de4  mov     ebp, 1
0x180009de9  test    [rcx+1Ch], bpl
0x180009ded  jz      short loc_180009E0C
0x180009def  cmp     byte ptr [rcx+19h], 2
0x180009df3  jb      short loc_180009E0C
0x180009df5  lea     edx, [rbp+20h]
0x180009df8  mov     dword ptr [rsp+58h+var_38], 80041016h
0x180009e00  mov     rcx, [rcx+10h]
0x180009e04  mov     r9, rdi
0x180009e07  call    WPP_SF_qD
0x180009e0c  mov     eax, ebx
0x180009e0e  jmp     loc_180009F5D
0x180009e13  or      dword ptr [rcx+58h], 8
0x180009e17  call    cs:__imp_GetCurrentThreadId
0x180009e1d  lea     r8, [rdi+60h]; BackTrace
0x180009e21  mov     [rsp+58h+BackTraceHash], 0
0x180009e29  lea     r9, [rsp+58h+BackTraceHash]; BackTraceHash
0x180009e2e  mov     [rdi+5Ch], eax
0x180009e31  mov     edx, 8; FramesToCapture
0x180009e36  xor     ecx, ecx; FramesToSkip
0x180009e38  call    cs:__imp_RtlCaptureStackBackTrace
0x180009e3e  xor     eax, eax
0x180009e40  mov     ebp, 1
0x180009e45  lock cmpxchg [rdi+44h], ebp
0x180009e4a  jz      short loc_180009E91
0x180009e4c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009e52  mov     ebx, 80041069h
0x180009e57  mov     rcx, rax
0x180009e5a  mov     edx, ebx
0x180009e5c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180009e62  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e69  lea     rsi, WPP_GLOBAL_Control
0x180009e70  cmp     rcx, rsi
0x180009e73  jz      short loc_180009E0C
0x180009e75  test    [rcx+1Ch], bpl
0x180009e79  jz      short loc_180009E0C
0x180009e7b  cmp     byte ptr [rcx+19h], 2
0x180009e7f  jb      short loc_180009E0C
0x180009e81  lea     edx, [rbp+21h]
0x180009e84  mov     dword ptr [rsp+58h+var_38], 80041069h
0x180009e8c  jmp     loc_180009E00
0x180009e91  mov     rdx, [rdi+28h]; Timer
0x180009e95  lea     rsi, WPP_GLOBAL_Control
0x180009e9c  xor     r14d, r14d
0x180009e9f  test    rdx, rdx
0x180009ea2  jz      short loc_180009F23
0x180009ea4  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180009ea8  xor     ecx, ecx; TimerQueue
0x180009eaa  mov     r14, rdx
0x180009ead  call    cs:__imp_DeleteTimerQueueTimer
0x180009eb3  test    eax, eax
0x180009eb5  jnz     short loc_180009F0E
0x180009eb7  call    cs:__imp_GetLastError
0x180009ebd  cmp     eax, 3E5h
0x180009ec2  jz      short loc_180009F0E
0x180009ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ecb  cmp     rcx, rsi
0x180009ece  jz      loc_180009F55
0x180009ed4  test    [rcx+1Ch], bpl
0x180009ed8  jz      short loc_180009F2A
0x180009eda  cmp     byte ptr [rcx+19h], 5
0x180009ede  jb      short loc_180009F2A
0x180009ee0  mov     rbx, [rdi+38h]
0x180009ee4  call    cs:__imp_GetLastError
0x180009eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ef1  mov     r9, [rdi+28h]
0x180009ef5  mov     [rsp+58h+var_28], rbx
0x180009efa  mov     [rsp+58h+var_30], rdi
0x180009eff  mov     rcx, [rcx+10h]
0x180009f03  mov     dword ptr [rsp+58h+var_38], eax
0x180009f07  call    WPP_SF_qDqq
0x180009f0c  jmp     short loc_180009F23
0x180009f0e  xor     eax, eax
0x180009f10  mov     rcx, rdi
0x180009f13  xchg    rax, [rdi+28h]
0x180009f17  mov     rax, [rdi]
0x180009f1a  mov     rax, [rax+10h]
0x180009f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f23  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f2a  cmp     rcx, rsi
0x180009f2d  jz      short loc_180009F55
0x180009f2f  test    [rcx+1Ch], bpl
0x180009f33  jz      short loc_180009F55
0x180009f35  cmp     byte ptr [rcx+19h], 5
0x180009f39  jb      short loc_180009F55
0x180009f3b  mov     rax, [rdi+38h]
0x180009f3f  mov     r9, rdi
0x180009f42  mov     rcx, [rcx+10h]
0x180009f46  mov     [rsp+58h+var_30], r14
0x180009f4b  mov     [rsp+58h+var_38], rax
0x180009f50  call    WPP_SF_qqq
0x180009f55  mov     rcx, rdi; this
0x180009f58  call    ?pResume@CWbemBackupRestore@@QEAAJXZ; CWbemBackupRestore::pResume(void)
0x180009f5d  mov     rbx, [rsp+58h+arg_8]
0x180009f62  mov     rbp, [rsp+58h+arg_10]
0x180009f67  add     rsp, 40h
0x180009f6b  pop     r14
0x180009f6d  pop     rdi
0x180009f6e  pop     rsi
0x180009f6f  retn
```
