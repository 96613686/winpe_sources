# pplx::details::_CancellationTokenState::_DeregisterCallback(pplx::details::_CancellationTokenRegistration *)

- ea: `0x1800149e8`
- end: `0x180014ae6`
- name: `?_DeregisterCallback@_CancellationTokenState@details@pplx@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `254`
- prototype: `void(pplx::details::_CancellationTokenState *__hidden this, struct pplx::details::_CancellationTokenRegistration *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014aec`
- `0x180037fc0`

## callees

- `0x1800149e8`
- `0x180015320`
- `0x180030cd0`
- `0x180031110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014a5a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180014a5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ad3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014a9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall pplx::details::_CancellationTokenState::_DeregisterCallback(
        pplx::details::_CancellationTokenState *this,
        struct pplx::details::_CancellationTokenRegistration *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct pplx::details::_CancellationTokenRegistration **v5; // rcx
  char v6; // r14
  struct pplx::details::_CancellationTokenRegistration **v7; // rax
  struct pplx::details::_CancellationTokenRegistration *v8; // rdx
  unsigned __int32 v9; // eax
  HANDLE hObject; // [rsp+60h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  hObject = (char *)this + 32;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v5 = (struct pplx::details::_CancellationTokenRegistration **)*((_QWORD *)this + 12);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( v5 )
    {
      v8 = v5[1];
      if ( *v5 == a2 )
      {
        if ( v7 )
          v7[1] = v8;
        else
          *((_QWORD *)this + 12) = v8;
        if ( !v5[1] )
          *((_QWORD *)this + 13) = v7;
        free(v5);
        break;
      }
      v7 = v5;
      v5 = (struct pplx::details::_CancellationTokenRegistration **)v5[1];
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    pplx::details::_RefCounter::_Release(a2);
  }
  else
  {
    v6 = 1;
  }
  LeaveCriticalSection(v4);
  if ( v6 )
  {
    v9 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v9 >= 2 && v9 - 2 >= 2 && v9 != GetCurrentThreadId() )
    {
      pplx::details::event_impl::event_impl((pplx::details::event_impl *)&hObject);
      *((_QWORD *)a2 + 3) = &hObject;
      if ( _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
        pplx::details::event_impl::wait(*((pplx::details::event_impl **)a2 + 3), 0xFFFFFFFF);
      CloseHandle(hObject);
    }
  }
}

```

## disassembly

```asm
0x1800149e8  push    rbx
0x1800149ea  push    rbp
0x1800149eb  push    rsi
0x1800149ec  push    rdi
0x1800149ed  push    r14
0x1800149ef  push    r15
0x1800149f1  sub     rsp, 28h
0x1800149f5  mov     rdi, rdx
0x1800149f8  mov     rsi, rcx
0x1800149fb  lea     rbx, [rcx+20h]
0x1800149ff  mov     [rsp+58h+hObject], rbx
0x180014a04  mov     rcx, rbx; lpCriticalSection
0x180014a07  call    cs:__imp_EnterCriticalSection
0x180014a0d  nop
0x180014a0e  mov     rcx, [rsi+60h]; Block
0x180014a12  mov     ebp, 2
0x180014a17  lea     r15d, [rbp-1]
0x180014a1b  test    rcx, rcx
0x180014a1e  jnz     short loc_180014A25
0x180014a20  mov     r14b, r15b
0x180014a23  jmp     short loc_180014A6E
0x180014a25  xor     r14b, r14b
0x180014a28  xor     eax, eax
0x180014a2a  test    rcx, rcx
0x180014a2d  jz      short loc_180014A60
0x180014a2f  mov     rdx, [rcx+8]
0x180014a33  cmp     [rcx], rdi
0x180014a36  jz      short loc_180014A40
0x180014a38  mov     rax, rcx
0x180014a3b  mov     rcx, rdx
0x180014a3e  jmp     short loc_180014A2A
0x180014a40  test    rax, rax
0x180014a43  jnz     short loc_180014A4B
0x180014a45  mov     [rsi+60h], rdx
0x180014a49  jmp     short loc_180014A4F
0x180014a4b  mov     [rax+8], rdx
0x180014a4f  cmp     qword ptr [rcx+8], 0
0x180014a54  jnz     short loc_180014A5A
0x180014a56  mov     [rsi+68h], rax
0x180014a5a  call    cs:__imp_free
0x180014a60  mov     eax, ebp
0x180014a62  xchg    eax, [rdi+10h]
0x180014a65  mov     rcx, rdi; this
0x180014a68  call    ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
0x180014a6d  nop
0x180014a6e  mov     rcx, rbx; lpCriticalSection
0x180014a71  call    cs:__imp_LeaveCriticalSection
0x180014a77  test    r14b, r14b
0x180014a7a  jz      short loc_180014AD9
0x180014a7c  xor     eax, eax
0x180014a7e  lock cmpxchg [rdi+10h], r15d
0x180014a84  mov     ebx, eax
0x180014a86  jz      short loc_180014AD9
0x180014a88  mov     edx, eax
0x180014a8a  test    eax, eax
0x180014a8c  jz      short loc_180014AD9
0x180014a8e  sub     edx, 1
0x180014a91  jz      short loc_180014AD9
0x180014a93  sub     edx, 1
0x180014a96  jz      short loc_180014AD9
0x180014a98  cmp     edx, 1
0x180014a9b  jz      short loc_180014AD9
0x180014a9d  call    cs:__imp_GetCurrentThreadId
0x180014aa3  cmp     ebx, eax
0x180014aa5  jz      short loc_180014AD9
0x180014aa7  lea     rcx, [rsp+58h+hObject]; this
0x180014aac  call    ??0event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::event_impl(void)
0x180014ab1  lea     rax, [rsp+58h+hObject]
0x180014ab6  mov     [rdi+18h], rax
0x180014aba  xchg    ebp, [rdi+10h]
0x180014abd  cmp     ebp, 3
0x180014ac0  jz      short loc_180014ACE
0x180014ac2  or      edx, 0FFFFFFFFh; unsigned int
0x180014ac5  mov     rcx, [rdi+18h]; this
0x180014ac9  call    ?wait@event_impl@details@pplx@@QEAAII@Z; pplx::details::event_impl::wait(uint)
0x180014ace  mov     rcx, [rsp+58h+hObject]; hObject
0x180014ad3  call    cs:__imp_CloseHandle
0x180014ad9  add     rsp, 28h
0x180014add  pop     r15
0x180014adf  pop     r14
0x180014ae1  pop     rdi
0x180014ae2  pop     rsi
0x180014ae3  pop     rbp
0x180014ae4  pop     rbx
0x180014ae5  retn
```
