# avpriv_slicethread_free

- ea: `0x1800511a0`
- end: `0x180051290`
- name: `avpriv_slicethread_free`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180050df0`

## callees

- `0x1800449c0`
- `0x1800449d0`
- `0x1800511a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18005120f`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18005120f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005123c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18005123c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051219`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051219`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800511f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800511f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051249`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051249`

## pseudocode

```c
_UNKNOWN **__fastcall avpriv_slicethread_free(__int64 **a1)
{
  _UNKNOWN **result; // rax
  __int64 *v2; // rsi
  int v4; // edx
  bool v5; // zf
  int v6; // eax
  __int64 v7; // rbp
  __int64 v8; // r14
  __int64 v9; // r12
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  __int64 v12; // rbx
  HANDLE *v13; // rdi
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF

  result = &retaddr;
  v2 = *a1;
  if ( *a1 )
  {
    v4 = *((_DWORD *)v2 + 2);
    v5 = v2[10] == 0;
    *((_DWORD *)v2 + 15) = 1;
    v6 = v4 - 1;
    if ( !v5 )
      v6 = v4;
    v7 = v6;
    if ( v6 > 0 )
    {
      v8 = 0;
      v9 = v6;
      do
      {
        v10 = *v2;
        v11 = (RTL_SRWLOCK *)(v8 + *v2);
        AcquireSRWLockExclusive(v11 + 1);
        *(_DWORD *)(v8 + v10 + 32) = 0;
        WakeConditionVariable((PCONDITION_VARIABLE)(v8 + v10 + 16));
        ReleaseSRWLockExclusive(v11 + 1);
        v8 += 40;
        --v9;
      }
      while ( v9 );
      v12 = 0;
      do
      {
        v13 = *(HANDLE **)(v12 + *v2 + 24);
        if ( !WaitForSingleObjectEx(*v13, 0xFFFFFFFF, 0) )
        {
          CloseHandle(*v13);
          av_free(v13);
        }
        v12 += 40;
        --v7;
      }
      while ( v7 );
    }
    av_freep(v2);
    return (_UNKNOWN **)av_freep(a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800511a0  mov     rax, rsp
0x1800511a3  mov     [rax+8], rbx
0x1800511a7  mov     [rax+10h], rbp
0x1800511ab  mov     [rax+18h], rsi
0x1800511af  mov     [rax+20h], rdi
0x1800511b3  push    r12
0x1800511b5  push    r14
0x1800511b7  push    r15
0x1800511b9  sub     rsp, 20h
0x1800511bd  mov     rsi, [rcx]
0x1800511c0  mov     r15, rcx
0x1800511c3  test    rsi, rsi
0x1800511c6  jz      loc_180051271
0x1800511cc  mov     edx, [rsi+8]
0x1800511cf  cmp     qword ptr [rsi+50h], 0
0x1800511d4  mov     dword ptr [rsi+3Ch], 1
0x1800511db  lea     eax, [rdx-1]
0x1800511de  cmovnz  eax, edx
0x1800511e1  movsxd  rbp, eax
0x1800511e4  test    eax, eax
0x1800511e6  jle     short loc_180051261
0x1800511e8  xor     r14d, r14d
0x1800511eb  mov     r12, rbp
0x1800511ee  mov     rbx, [rsi]
0x1800511f1  lea     rdi, [r14+rbx]
0x1800511f5  lea     rcx, [rdi+8]; SRWLock
0x1800511f9  call    cs:AcquireSRWLockExclusive
0x1800511ff  lea     rcx, [rbx+10h]
0x180051203  mov     dword ptr [r14+rbx+20h], 0
0x18005120c  add     rcx, r14; ConditionVariable
0x18005120f  call    cs:WakeConditionVariable
0x180051215  lea     rcx, [rdi+8]; SRWLock
0x180051219  call    cs:ReleaseSRWLockExclusive
0x18005121f  add     r14, 28h ; '('
0x180051223  sub     r12, 1
0x180051227  jnz     short loc_1800511EE
0x180051229  xor     ebx, ebx
0x18005122b  mov     rax, [rsi]
0x18005122e  xor     r8d, r8d; bAlertable
0x180051231  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180051234  mov     rdi, [rbx+rax+18h]
0x180051239  mov     rcx, [rdi]; hHandle
0x18005123c  call    cs:WaitForSingleObjectEx
0x180051242  test    eax, eax
0x180051244  jnz     short loc_180051257
0x180051246  mov     rcx, [rdi]; hObject
0x180051249  call    cs:CloseHandle
0x18005124f  mov     rcx, rdi; Block
0x180051252  call    av_free
0x180051257  add     rbx, 28h ; '('
0x18005125b  sub     rbp, 1
0x18005125f  jnz     short loc_18005122B
0x180051261  mov     rcx, rsi
0x180051264  call    av_freep
0x180051269  mov     rcx, r15
0x18005126c  call    av_freep
0x180051271  mov     rbx, [rsp+38h+arg_0]
0x180051276  mov     rbp, [rsp+38h+arg_8]
0x18005127b  mov     rsi, [rsp+38h+arg_10]
0x180051280  mov     rdi, [rsp+38h+arg_18]
0x180051285  add     rsp, 20h
0x180051289  pop     r15
0x18005128b  pop     r14
0x18005128d  pop     r12
0x18005128f  retn
```
