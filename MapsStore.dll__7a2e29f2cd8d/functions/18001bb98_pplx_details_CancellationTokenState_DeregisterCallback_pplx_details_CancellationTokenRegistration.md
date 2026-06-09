# pplx::details::_CancellationTokenState::_DeregisterCallback(pplx::details::_CancellationTokenRegistration *)

- ea: `0x18001bb98`
- end: `0x18001bc9b`
- name: `?_DeregisterCallback@_CancellationTokenState@details@pplx@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `259`
- prototype: `void(pplx::details::_CancellationTokenState *__hidden this, struct pplx::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800170a8`

## callees

- `0x18001bb98`
- `0x18001c758`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001bc0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001bc0a`
- `BingOnlineServices!?lock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001bbb7`
- `BingOnlineServices!?lock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001bbb7`
- `BingOnlineServices!??1event_impl@details@pplx@@QEAA@XZ` at `0x18001bc88`
- `BingOnlineServices!??1event_impl@details@pplx@@QEAA@XZ` at `0x18001bc88`
- `BingOnlineServices!??0event_impl@details@pplx@@QEAA@XZ` at `0x18001bc5d`
- `BingOnlineServices!??0event_impl@details@pplx@@QEAA@XZ` at `0x18001bc5d`
- `BingOnlineServices!?unlock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001bc21`
- `BingOnlineServices!?unlock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001bc21`
- `BingOnlineServices!?GetCurrentThreadId@platform@details@pplx@@YAJXZ` at `0x18001bc4e`
- `BingOnlineServices!?GetCurrentThreadId@platform@details@pplx@@YAJXZ` at `0x18001bc4e`
- `BingOnlineServices!?wait@event_impl@details@pplx@@QEAAII@Z` at `0x18001bc7c`
- `BingOnlineServices!?wait@event_impl@details@pplx@@QEAAII@Z` at `0x18001bc7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall pplx::details::_CancellationTokenState::_DeregisterCallback(
        pplx::details::_CancellationTokenState *this,
        struct pplx::details::_CancellationTokenRegistration *a2)
{
  pplx::details::critical_section_impl *v4; // rbx
  struct pplx::details::_CancellationTokenRegistration **v5; // rcx
  char v6; // r14
  struct pplx::details::_CancellationTokenRegistration **v7; // rax
  struct pplx::details::_CancellationTokenRegistration *v8; // rdx
  pplx::details::platform *v9; // rcx
  unsigned __int32 v10; // eax
  char *v11; // [rsp+60h] [rbp+8h] BYREF

  v4 = (pplx::details::_CancellationTokenState *)((char *)this + 32);
  v11 = (char *)this + 32;
  pplx::details::critical_section_impl::lock((pplx::details::_CancellationTokenState *)((char *)this + 32));
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
  pplx::details::critical_section_impl::unlock(v4);
  if ( v6 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 >= 2 && v10 - 2 >= 2 && v10 != pplx::details::platform::GetCurrentThreadId(v9) )
    {
      pplx::details::event_impl::event_impl((pplx::details::event_impl *)&v11);
      *((_QWORD *)a2 + 3) = &v11;
      if ( _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
        pplx::details::event_impl::wait(*((pplx::details::event_impl **)a2 + 3), 0xFFFFFFFF);
      pplx::details::event_impl::~event_impl((pplx::details::event_impl *)&v11);
    }
  }
}

```

## disassembly

```asm
0x18001bb98  push    rbx
0x18001bb9a  push    rbp
0x18001bb9b  push    rsi
0x18001bb9c  push    rdi
0x18001bb9d  push    r14
0x18001bb9f  push    r15
0x18001bba1  sub     rsp, 28h
0x18001bba5  mov     rdi, rdx
0x18001bba8  mov     rsi, rcx
0x18001bbab  lea     rbx, [rcx+20h]
0x18001bbaf  mov     [rsp+58h+arg_0], rbx
0x18001bbb4  mov     rcx, rbx
0x18001bbb7  call    cs:__imp_?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18001bbbd  nop
0x18001bbbe  mov     rcx, [rsi+60h]; Block
0x18001bbc2  mov     ebp, 2
0x18001bbc7  lea     r15d, [rbp-1]
0x18001bbcb  test    rcx, rcx
0x18001bbce  jnz     short loc_18001BBD5
0x18001bbd0  mov     r14b, r15b
0x18001bbd3  jmp     short loc_18001BC1E
0x18001bbd5  xor     r14b, r14b
0x18001bbd8  xor     eax, eax
0x18001bbda  test    rcx, rcx
0x18001bbdd  jz      short loc_18001BC10
0x18001bbdf  mov     rdx, [rcx+8]
0x18001bbe3  cmp     [rcx], rdi
0x18001bbe6  jz      short loc_18001BBF0
0x18001bbe8  mov     rax, rcx
0x18001bbeb  mov     rcx, rdx
0x18001bbee  jmp     short loc_18001BBDA
0x18001bbf0  test    rax, rax
0x18001bbf3  jnz     short loc_18001BBFB
0x18001bbf5  mov     [rsi+60h], rdx
0x18001bbf9  jmp     short loc_18001BBFF
0x18001bbfb  mov     [rax+8], rdx
0x18001bbff  cmp     qword ptr [rcx+8], 0
0x18001bc04  jnz     short loc_18001BC0A
0x18001bc06  mov     [rsi+68h], rax
0x18001bc0a  call    cs:__imp_free
0x18001bc10  mov     eax, ebp
0x18001bc12  xchg    eax, [rdi+10h]
0x18001bc15  mov     rcx, rdi; this
0x18001bc18  call    ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
0x18001bc1d  nop
0x18001bc1e  mov     rcx, rbx
0x18001bc21  call    cs:__imp_?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18001bc27  nop
0x18001bc28  test    r14b, r14b
0x18001bc2b  jz      short loc_18001BC8E
0x18001bc2d  xor     eax, eax
0x18001bc2f  lock cmpxchg [rdi+10h], r15d
0x18001bc35  mov     ebx, eax
0x18001bc37  jz      short loc_18001BC8E
0x18001bc39  mov     edx, eax
0x18001bc3b  test    eax, eax
0x18001bc3d  jz      short loc_18001BC8E
0x18001bc3f  sub     edx, 1
0x18001bc42  jz      short loc_18001BC8E
0x18001bc44  sub     edx, 1
0x18001bc47  jz      short loc_18001BC8E
0x18001bc49  cmp     edx, 1
0x18001bc4c  jz      short loc_18001BC8E
0x18001bc4e  call    cs:__imp_?GetCurrentThreadId@platform@details@pplx@@YAJXZ; pplx::details::platform::GetCurrentThreadId(void)
0x18001bc54  cmp     ebx, eax
0x18001bc56  jz      short loc_18001BC8E
0x18001bc58  lea     rcx, [rsp+58h+arg_0]
0x18001bc5d  call    cs:__imp_??0event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::event_impl(void)
0x18001bc63  nop
0x18001bc64  lea     rax, [rsp+58h+arg_0]
0x18001bc69  mov     [rdi+18h], rax
0x18001bc6d  xchg    ebp, [rdi+10h]
0x18001bc70  cmp     ebp, 3
0x18001bc73  jz      short loc_18001BC83
0x18001bc75  or      edx, 0FFFFFFFFh
0x18001bc78  mov     rcx, [rdi+18h]
0x18001bc7c  call    cs:__imp_?wait@event_impl@details@pplx@@QEAAII@Z; pplx::details::event_impl::wait(uint)
0x18001bc82  nop
0x18001bc83  lea     rcx, [rsp+58h+arg_0]
0x18001bc88  call    cs:__imp_??1event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::~event_impl(void)
0x18001bc8e  add     rsp, 28h
0x18001bc92  pop     r15
0x18001bc94  pop     r14
0x18001bc96  pop     rdi
0x18001bc97  pop     rsi
0x18001bc98  pop     rbp
0x18001bc99  pop     rbx
0x18001bc9a  retn
```
