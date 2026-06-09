# pplx::details::_CancellationTokenState::_RegisterCallback(pplx::details::_CancellationTokenRegistration *)

- ea: `0x18001c58c`
- end: `0x18001c6a8`
- name: `?_RegisterCallback@_CancellationTokenState@details@pplx@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `284`
- prototype: `void(pplx::details::_CancellationTokenState *__hidden this, struct pplx::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c6b0`

## callees

- `0x18000dce0`
- `0x18001c58c`
- `0x18001c758`
- `0x18001d594`
- `0x180098010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c5e3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c5e3`
- `BingOnlineServices!?lock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001c5c5`
- `BingOnlineServices!?lock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001c5c5`
- `BingOnlineServices!?set@event_impl@details@pplx@@QEAAXXZ` at `0x18001c691`
- `BingOnlineServices!?set@event_impl@details@pplx@@QEAAXXZ` at `0x18001c691`
- `BingOnlineServices!?unlock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001c64d`
- `BingOnlineServices!?unlock@critical_section_impl@details@pplx@@QEAAXXZ` at `0x18001c64d`
- `BingOnlineServices!?GetCurrentThreadId@platform@details@pplx@@YAJXZ` at `0x18001c659`
- `BingOnlineServices!?GetCurrentThreadId@platform@details@pplx@@YAJXZ` at `0x18001c659`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall pplx::details::_CancellationTokenState::_RegisterCallback(
        pplx::details::_CancellationTokenState *this,
        struct pplx::details::_CancellationTokenRegistration *a2)
{
  pplx::details::platform *v4; // rcx
  char v5; // bp
  _QWORD *v6; // rax
  signed __int32 CurrentThreadId; // edi
  signed __int32 v8; // eax
  _QWORD pExceptionObject[9]; // [rsp+20h] [rbp-48h] BYREF

  _InterlockedExchange((volatile __int32 *)a2 + 4, 0);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  *((_QWORD *)a2 + 4) = this;
  if ( (unsigned int)std::_Atomic_storage<enum MapControl::NetworkUsagePolicy,4>::load((char *)this + 16) )
    goto LABEL_11;
  pplx::details::critical_section_impl::lock((pplx::details::_CancellationTokenState *)((char *)this + 32));
  if ( (unsigned int)std::_Atomic_storage<enum MapControl::NetworkUsagePolicy,4>::load((char *)this + 16) )
  {
    v5 = 1;
  }
  else
  {
    v6 = malloc(0x10u);
    if ( !v6 )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v5 = 0;
    *v6 = a2;
    v6[1] = 0;
    if ( *((_QWORD *)this + 12) )
      *(_QWORD *)(*((_QWORD *)this + 13) + 8LL) = v6;
    else
      *((_QWORD *)this + 12) = v6;
    *((_QWORD *)this + 13) = v6;
  }
  pplx::details::critical_section_impl::unlock((pplx::details::_CancellationTokenState *)((char *)this + 32));
  if ( v5 )
  {
LABEL_11:
    CurrentThreadId = pplx::details::platform::GetCurrentThreadId(v4);
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(struct pplx::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 16LL))(a2);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v8 )
        CurrentThreadId = v8;
      if ( CurrentThreadId == 2 )
        pplx::details::event_impl::set(*((pplx::details::event_impl **)a2 + 3));
    }
    pplx::details::_RefCounter::_Release(a2);
  }
}

```

## disassembly

```asm
0x18001c58c  push    rbx
0x18001c58e  push    rbp
0x18001c58f  push    rsi
0x18001c590  push    rdi
0x18001c591  sub     rsp, 48h
0x18001c595  mov     rbx, rdx
0x18001c598  mov     rdi, rcx
0x18001c59b  xor     eax, eax
0x18001c59d  xchg    eax, [rdx+10h]
0x18001c5a0  lock inc dword ptr [rdx+8]
0x18001c5a4  mov     [rdx+20h], rcx
0x18001c5a8  add     rcx, 10h
0x18001c5ac  call    ?load@?$_Atomic_storage@W4NetworkUsagePolicy@MapControl@@$03@std@@QEBA?AW4NetworkUsagePolicy@MapControl@@W4memory_order@2@@Z; std::_Atomic_storage<MapControl::NetworkUsagePolicy,4>::load(std::memory_order)
0x18001c5b1  test    eax, eax
0x18001c5b3  jnz     loc_18001C659
0x18001c5b9  lea     rsi, [rdi+20h]
0x18001c5bd  mov     [rsp+68h+arg_0], rsi
0x18001c5c2  mov     rcx, rsi
0x18001c5c5  call    cs:__imp_?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18001c5cb  nop
0x18001c5cc  lea     rcx, [rdi+10h]
0x18001c5d0  call    ?load@?$_Atomic_storage@W4NetworkUsagePolicy@MapControl@@$03@std@@QEBA?AW4NetworkUsagePolicy@MapControl@@W4memory_order@2@@Z; std::_Atomic_storage<MapControl::NetworkUsagePolicy,4>::load(std::memory_order)
0x18001c5d5  test    eax, eax
0x18001c5d7  jz      short loc_18001C5DE
0x18001c5d9  mov     bpl, 1
0x18001c5dc  jmp     short loc_18001C64A
0x18001c5de  mov     ecx, 10h; Size
0x18001c5e3  call    cs:__imp_malloc
0x18001c5e9  mov     rcx, rax
0x18001c5ec  test    rax, rax
0x18001c5ef  jnz     short loc_18001C623
0x18001c5f1  xorps   xmm0, xmm0
0x18001c5f4  movups  [rsp+68h+var_40], xmm0
0x18001c5f9  lea     rax, aBadAllocation; "bad allocation"
0x18001c600  mov     qword ptr [rsp+68h+var_40], rax
0x18001c605  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001c60c  mov     [rsp+68h+pExceptionObject], rax
0x18001c611  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001c618  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001c61d  call    _CxxThrowException_0
0x18001c623  xor     bpl, bpl
0x18001c626  mov     [rax], rbx
0x18001c629  mov     qword ptr [rax+8], 0
0x18001c631  cmp     qword ptr [rdi+60h], 0
0x18001c636  jnz     short loc_18001C63E
0x18001c638  mov     [rdi+60h], rcx
0x18001c63c  jmp     short loc_18001C646
0x18001c63e  mov     rax, [rdi+68h]
0x18001c642  mov     [rax+8], rcx
0x18001c646  mov     [rdi+68h], rcx
0x18001c64a  mov     rcx, rsi
0x18001c64d  call    cs:__imp_?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18001c653  nop
0x18001c654  test    bpl, bpl
0x18001c657  jz      short loc_18001C69F
0x18001c659  call    cs:__imp_?GetCurrentThreadId@platform@details@pplx@@YAJXZ; pplx::details::platform::GetCurrentThreadId(void)
0x18001c65f  mov     edi, eax
0x18001c661  xor     eax, eax
0x18001c663  lock cmpxchg [rbx+10h], edi
0x18001c668  jnz     short loc_18001C697
0x18001c66a  mov     rcx, [rbx]
0x18001c66d  mov     rax, [rcx+10h]
0x18001c671  mov     rcx, rbx
0x18001c674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c679  mov     ecx, 3
0x18001c67e  mov     eax, edi
0x18001c680  lock cmpxchg [rbx+10h], ecx
0x18001c685  cmovnz  edi, eax
0x18001c688  cmp     edi, 2
0x18001c68b  jnz     short loc_18001C697
0x18001c68d  mov     rcx, [rbx+18h]
0x18001c691  call    cs:__imp_?set@event_impl@details@pplx@@QEAAXXZ; pplx::details::event_impl::set(void)
0x18001c697  mov     rcx, rbx; this
0x18001c69a  call    ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
0x18001c69f  add     rsp, 48h
0x18001c6a3  pop     rdi
0x18001c6a4  pop     rsi
0x18001c6a5  pop     rbp
0x18001c6a6  pop     rbx
0x18001c6a7  retn
```
