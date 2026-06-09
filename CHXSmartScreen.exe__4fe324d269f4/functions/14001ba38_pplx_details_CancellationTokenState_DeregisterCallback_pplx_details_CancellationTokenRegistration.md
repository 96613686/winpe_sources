# pplx::details::_CancellationTokenState::_DeregisterCallback(pplx::details::_CancellationTokenRegistration *)

- ea: `0x14001ba38`
- end: `0x14001bb80`
- name: `?_DeregisterCallback@_CancellationTokenState@details@pplx@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `328`
- prototype: `void __fastcall(pplx::details::_CancellationTokenState *__hidden this, struct pplx::details::_CancellationTokenRegistration *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015790`
- `0x140015820`

## callees

- `0x14001ba38`
- `0x140023bd8`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14001bb4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14001bb4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001baf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001baf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001ba6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001ba6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001bb0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001bb0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bb55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001bb55`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001bab3`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001bab3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall pplx::details::_CancellationTokenState::_DeregisterCallback(
        pplx::details::_CancellationTokenState *this,
        struct pplx::details::_CancellationTokenRegistration *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  char v5; // r13
  _QWORD *v6; // r14
  _QWORD *v7; // rsi
  _QWORD *v8; // rdx
  void *v9; // rcx
  signed __int32 v10; // eax
  HANDLE hObject; // [rsp+20h] [rbp-48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  hObject = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_QWORD *)this + 13) )
  {
    v5 = 0;
    v6 = (_QWORD *)*((_QWORD *)this + 12);
    v7 = (_QWORD *)*v6;
    while ( v7 != v6 )
    {
      if ( (struct pplx::details::_CancellationTokenRegistration *)v7[2] == a2 )
      {
        v8 = (_QWORD *)v7[1];
        v9 = v7;
        v7 = (_QWORD *)*v7;
        *v8 = v7;
        v7[1] = v8;
        operator delete(v9);
        --*((_QWORD *)this + 13);
      }
      else
      {
        v7 = (_QWORD *)*v7;
      }
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(struct pplx::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v5 = 1;
  }
  LeaveCriticalSection(v4);
  if ( v5 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 )
    {
      if ( v10 != 3 && v10 != GetCurrentThreadId() )
      {
        hObject = 0;
        pplx::details::event_impl::event_impl((pplx::details::event_impl *)&hObject);
        *((_QWORD *)a2 + 3) = &hObject;
        if ( _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
          WaitForSingleObjectEx(**((HANDLE **)a2 + 3), 0xFFFFFFFF, 0);
        CloseHandle(hObject);
      }
    }
  }
}

```

## disassembly

```asm
0x14001ba38  mov     [rsp+arg_10], rbx
0x14001ba3d  push    rbp
0x14001ba3e  push    rsi
0x14001ba3f  push    rdi
0x14001ba40  push    r12
0x14001ba42  push    r13
0x14001ba44  push    r14
0x14001ba46  push    r15
0x14001ba48  sub     rsp, 30h
0x14001ba4c  mov     rax, cs:__security_cookie
0x14001ba53  xor     rax, rsp
0x14001ba56  mov     [rsp+68h+var_40], rax
0x14001ba5b  mov     rdi, rdx
0x14001ba5e  mov     rbp, rcx
0x14001ba61  lea     rbx, [rcx+20h]
0x14001ba65  mov     [rsp+68h+hObject], rbx
0x14001ba6a  mov     rcx, rbx; lpCriticalSection
0x14001ba6d  call    cs:__imp_EnterCriticalSection
0x14001ba73  nop
0x14001ba74  mov     esi, 1
0x14001ba79  lea     r12d, [rsi+1]
0x14001ba7d  cmp     qword ptr [rbp+68h], 0
0x14001ba82  jnz     short loc_14001BA89
0x14001ba84  mov     r13b, sil
0x14001ba87  jmp     short loc_14001BAEF
0x14001ba89  xor     r13b, r13b
0x14001ba8c  mov     r14, [rbp+60h]
0x14001ba90  mov     rsi, [r14]
0x14001ba93  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001ba97  jmp     short loc_14001BAC2
0x14001ba99  cmp     [rsi+10h], rdi
0x14001ba9d  jnz     short loc_14001BABF
0x14001ba9f  mov     rdx, [rsi+8]
0x14001baa3  mov     rcx, rsi
0x14001baa6  mov     rax, [rsi]
0x14001baa9  mov     rsi, rax
0x14001baac  mov     [rdx], rax
0x14001baaf  mov     [rax+8], rdx
0x14001bab3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001bab9  add     [rbp+68h], r15
0x14001babd  jmp     short loc_14001BAC2
0x14001babf  mov     rsi, [rsi]
0x14001bac2  cmp     rsi, r14
0x14001bac5  jnz     short loc_14001BA99
0x14001bac7  mov     eax, r12d
0x14001baca  xchg    eax, [rdi+10h]
0x14001bacd  lock xadd [rdi+8], r15d
0x14001bad3  lea     eax, [r15-1]
0x14001bad7  test    eax, eax
0x14001bad9  jnz     short loc_14001BAEA
0x14001badb  mov     rax, [rdi]
0x14001bade  mov     rcx, rdi
0x14001bae1  mov     rax, [rax+8]
0x14001bae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001baea  mov     esi, 1
0x14001baef  mov     rcx, rbx; lpCriticalSection
0x14001baf2  call    cs:__imp_LeaveCriticalSection
0x14001baf8  test    r13b, r13b
0x14001bafb  jz      short loc_14001BB5B
0x14001bafd  xor     eax, eax
0x14001baff  lock cmpxchg [rdi+10h], esi
0x14001bb04  mov     ebx, eax
0x14001bb06  jz      short loc_14001BB5B
0x14001bb08  cmp     eax, 3
0x14001bb0b  jz      short loc_14001BB5B
0x14001bb0d  call    cs:__imp_GetCurrentThreadId
0x14001bb13  cmp     ebx, eax
0x14001bb15  jz      short loc_14001BB5B
0x14001bb17  mov     [rsp+68h+hObject], 0
0x14001bb20  lea     rcx, [rsp+68h+hObject]; this
0x14001bb25  call    ??0event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::event_impl(void)
0x14001bb2a  lea     rax, [rsp+68h+hObject]
0x14001bb2f  mov     [rdi+18h], rax
0x14001bb33  xchg    r12d, [rdi+10h]
0x14001bb37  cmp     r12d, 3
0x14001bb3b  jz      short loc_14001BB50
0x14001bb3d  mov     rcx, [rdi+18h]
0x14001bb41  xor     r8d, r8d; bAlertable
0x14001bb44  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001bb47  mov     rcx, [rcx]; hHandle
0x14001bb4a  call    cs:__imp_WaitForSingleObjectEx
0x14001bb50  mov     rcx, [rsp+68h+hObject]; hObject
0x14001bb55  call    cs:__imp_CloseHandle
0x14001bb5b  mov     rcx, [rsp+68h+var_40]
0x14001bb60  xor     rcx, rsp; StackCookie
0x14001bb63  call    __security_check_cookie
0x14001bb68  mov     rbx, [rsp+68h+arg_10]
0x14001bb70  add     rsp, 30h
0x14001bb74  pop     r15
0x14001bb76  pop     r14
0x14001bb78  pop     r13
0x14001bb7a  pop     r12
0x14001bb7c  pop     rdi
0x14001bb7d  pop     rsi
0x14001bb7e  pop     rbp
0x14001bb7f  retn
```
