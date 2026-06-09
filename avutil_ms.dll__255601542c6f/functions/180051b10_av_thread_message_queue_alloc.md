# av_thread_message_queue_alloc

- ea: `0x180051b10`
- end: `0x180051bb8`
- name: `av_thread_message_queue_alloc`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180039a40`
- `0x1800449c0`
- `0x180044aa0`
- `0x180051b10`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180051b68`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180051b72`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180051b68`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180051b72`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180051b5e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180051b5e`

## pseudocode

```c
__int64 __fastcall av_thread_message_queue_alloc(RTL_CONDITION_VARIABLE **a1, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 result; // rax
  RTL_SRWLOCK *v7; // rax
  RTL_CONDITION_VARIABLE *v8; // rbx
  __int64 v9; // rax

  v3 = a2;
  v4 = a3;
  if ( a2 > 0x7FFFFFFF / a3 )
    return 4294967274LL;
  v7 = (RTL_SRWLOCK *)av_mallocz(0x38u);
  v8 = (RTL_CONDITION_VARIABLE *)v7;
  if ( !v7 )
    return 4294967284LL;
  InitializeSRWLock(v7 + 1);
  InitializeConditionVariable(v8 + 2);
  InitializeConditionVariable(v8 + 3);
  _mm_lfence();
  v9 = av_fifo_alloc2(v3, v4, 0);
  v8->Ptr = (PVOID)v9;
  if ( !v9 )
  {
    av_free(v8);
    return 4294967284LL;
  }
  LODWORD(v8[5].Ptr) = v4;
  result = 0;
  *a1 = v8;
  return result;
}

```

## disassembly

```asm
0x180051b10  mov     [rsp+arg_0], rbx
0x180051b15  mov     [rsp+arg_8], rbp
0x180051b1a  mov     [rsp+arg_10], rsi
0x180051b1f  push    rdi
0x180051b20  sub     rsp, 20h
0x180051b24  mov     ebp, edx
0x180051b26  mov     eax, 7FFFFFFFh
0x180051b2b  xor     edx, edx
0x180051b2d  mov     edi, r8d
0x180051b30  div     r8d
0x180051b33  mov     rsi, rcx
0x180051b36  cmp     ebp, eax
0x180051b38  jbe     short loc_180051B41
0x180051b3a  mov     eax, 0FFFFFFEAh
0x180051b3f  jmp     short loc_180051BA3
0x180051b41  mov     ecx, 38h ; '8'
0x180051b46  call    av_mallocz
0x180051b4b  mov     rbx, rax
0x180051b4e  test    rax, rax
0x180051b51  jnz     short loc_180051B5A
0x180051b53  mov     eax, 0FFFFFFF4h
0x180051b58  jmp     short loc_180051BA3
0x180051b5a  lea     rcx, [rax+8]; SRWLock
0x180051b5e  call    cs:InitializeSRWLock
0x180051b64  lea     rcx, [rbx+10h]; ConditionVariable
0x180051b68  call    cs:InitializeConditionVariable
0x180051b6e  lea     rcx, [rbx+18h]; ConditionVariable
0x180051b72  call    cs:InitializeConditionVariable
0x180051b78  lfence
0x180051b7b  mov     rdx, rdi
0x180051b7e  mov     rcx, rbp
0x180051b81  xor     r8d, r8d
0x180051b84  call    av_fifo_alloc2
0x180051b89  mov     [rbx], rax
0x180051b8c  test    rax, rax
0x180051b8f  jnz     short loc_180051B9B
0x180051b91  mov     rcx, rbx; Block
0x180051b94  call    av_free
0x180051b99  jmp     short loc_180051B53
0x180051b9b  mov     [rbx+28h], edi
0x180051b9e  xor     eax, eax
0x180051ba0  mov     [rsi], rbx
0x180051ba3  mov     rbx, [rsp+28h+arg_0]
0x180051ba8  mov     rbp, [rsp+28h+arg_8]
0x180051bad  mov     rsi, [rsp+28h+arg_10]
0x180051bb2  add     rsp, 20h
0x180051bb6  pop     rdi
0x180051bb7  retn
```
