# Concurrency::details::_Task_impl_base::_RegisterCancellation(void)

- ea: `0x14001cafc`
- end: `0x14001cce0`
- name: `?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXXZ`
- size: `484`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140012518`
- `0x14001b758`

## callees

- `0x140001738`
- `0x1400017a0`
- `0x140012f84`
- `0x14001cafc`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001cc87`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001cc87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001cc45`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cbdb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001cbdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001cc50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001cc50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_Task_impl_base::_RegisterCancellation(
        Concurrency::details::_Task_impl_base *this)
{
  __int64 v2; // rdi
  volatile __int32 *v3; // rax
  volatile signed __int32 *v4; // rbx
  char v5; // r14
  volatile signed __int32 *v6; // rsi
  signed __int32 v7; // eax
  signed __int32 v8; // ett
  unsigned __int32 v9; // eax
  __int64 v10; // rcx
  unsigned __int32 v11; // ett
  __int64 v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // rax
  DWORD CurrentThreadId; // edi
  signed __int32 v16; // eax
  volatile signed __int32 *v17; // [rsp+28h] [rbp-40h] BYREF

  v2 = *((_QWORD *)this + 14);
  v3 = (volatile __int32 *)operator new(0x38u);
  v4 = v3;
  v17 = v3;
  v5 = 1;
  if ( v3 )
  {
    *(_OWORD *)v3 = 0;
    *((_OWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *(_QWORD *)v3 = &pplx::details::_RefCounterBase::`vftable';
    _InterlockedExchange(v3 + 2, 1);
    *(_QWORD *)v3 = &pplx::details::_CancellationTokenRegistration::`vftable';
    _InterlockedExchange(v3 + 4, 3);
    *((_QWORD *)v3 + 4) = 0;
    *(_QWORD *)v3 = &pplx::details::CancellationTokenRegistration_TaskProc::`vftable';
    *((_QWORD *)v3 + 5) = Concurrency::details::_Task_impl_base::_CancelViaToken;
    *((_QWORD *)v3 + 6) = this;
  }
  else
  {
    v4 = 0;
  }
  v6 = v4;
  v17 = v4;
  _InterlockedExchange(v4 + 4, 0);
  _InterlockedIncrement(v4 + 2);
  *((_QWORD *)v4 + 4) = v2;
  _m_prefetchw((const void *)(v2 + 16));
  v7 = *(_DWORD *)(v2 + 16);
  do
  {
    v8 = v7;
    v7 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 16), v7, v7);
  }
  while ( v8 != v7 );
  if ( v7 )
    goto LABEL_13;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 32));
  _m_prefetchw((const void *)(v2 + 16));
  v9 = *(_DWORD *)(v2 + 16);
  do
  {
    v10 = v9;
    v11 = v9;
    v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 16), v9, v9);
  }
  while ( v11 != v9 );
  if ( !v9 )
  {
    v12 = *(_QWORD *)(v2 + 96);
    v13 = std::_List_buy<pplx::details::_CancellationTokenRegistration *>::_Buynode<pplx::details::_CancellationTokenRegistration * const &>(
            v10,
            v12,
            *(_QWORD *)(v12 + 8),
            &v17,
            v2 + 32);
    v14 = *(_QWORD *)(v2 + 104);
    if ( 0xAAAAAAAAAAAAAA9LL == v14 )
      std::_Xlength_error("list<T> too long");
    v5 = 0;
    *(_QWORD *)(v2 + 104) = v14 + 1;
    *(_QWORD *)(v12 + 8) = v13;
    **(_QWORD **)(v13 + 8) = v13;
    v6 = v17;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 32));
  if ( v5 )
  {
LABEL_13:
    CurrentThreadId = GetCurrentThreadId();
    if ( !_InterlockedCompareExchange(v6 + 4, CurrentThreadId, 0) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      v16 = _InterlockedCompareExchange(v6 + 4, 3, CurrentThreadId);
      if ( CurrentThreadId != v16 )
        CurrentThreadId = v16;
      if ( CurrentThreadId == 2 )
        SetEvent(**((HANDLE **)v6 + 3));
    }
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
  }
  *((_QWORD *)this + 15) = v4;
}

```

## disassembly

```asm
0x14001cafc  mov     [rsp+arg_8], rbx
0x14001cb01  mov     [rsp+arg_10], rbp
0x14001cb06  push    rsi
0x14001cb07  push    rdi
0x14001cb08  push    r13
0x14001cb0a  push    r14
0x14001cb0c  push    r15
0x14001cb0e  sub     rsp, 40h
0x14001cb12  mov     rax, cs:__security_cookie
0x14001cb19  xor     rax, rsp
0x14001cb1c  mov     [rsp+68h+var_38], rax
0x14001cb21  mov     r15, rcx
0x14001cb24  mov     rdi, [rcx+70h]
0x14001cb28  mov     ecx, 38h ; '8'; Size
0x14001cb2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001cb32  mov     rbx, rax
0x14001cb35  mov     [rsp+68h+var_40], rax
0x14001cb3a  mov     r14d, 1
0x14001cb40  lea     r13d, [r14+2]
0x14001cb44  test    rax, rax
0x14001cb47  jz      short loc_14001CBA0
0x14001cb49  xorps   xmm0, xmm0
0x14001cb4c  xor     eax, eax
0x14001cb4e  movups  xmmword ptr [rbx], xmm0
0x14001cb51  movups  xmmword ptr [rbx+10h], xmm0
0x14001cb55  movups  xmmword ptr [rbx+20h], xmm0
0x14001cb59  mov     [rbx+30h], rax
0x14001cb5d  lea     rax, ??_7_RefCounterBase@details@pplx@@6B@; const pplx::details::_RefCounterBase::`vftable'
0x14001cb64  mov     [rbx], rax
0x14001cb67  mov     eax, r14d
0x14001cb6a  xchg    eax, [rbx+8]
0x14001cb6d  lea     rcx, ??_7_CancellationTokenRegistration@details@pplx@@6B@; const pplx::details::_CancellationTokenRegistration::`vftable'
0x14001cb74  mov     [rbx], rcx
0x14001cb77  mov     eax, r13d
0x14001cb7a  xchg    eax, [rbx+10h]
0x14001cb7d  mov     qword ptr [rbx+20h], 0
0x14001cb85  lea     rax, ??_7CancellationTokenRegistration_TaskProc@details@pplx@@6B@; const pplx::details::CancellationTokenRegistration_TaskProc::`vftable'
0x14001cb8c  mov     [rbx], rax
0x14001cb8f  lea     rax, ?_CancelViaToken@_Task_impl_base@details@Concurrency@@SAXPEAX@Z; Concurrency::details::_Task_impl_base::_CancelViaToken(void *)
0x14001cb96  mov     [rbx+28h], rax
0x14001cb9a  mov     [rbx+30h], r15
0x14001cb9e  jmp     short loc_14001CBA2
0x14001cba0  xor     ebx, ebx
0x14001cba2  mov     rsi, rbx
0x14001cba5  mov     [rsp+68h+var_40], rbx
0x14001cbaa  xor     eax, eax
0x14001cbac  xchg    eax, [rbx+10h]
0x14001cbaf  lock inc dword ptr [rbx+8]
0x14001cbb3  mov     [rbx+20h], rdi
0x14001cbb7  prefetchw byte ptr [rdi+10h]
0x14001cbbb  mov     eax, [rdi+10h]
0x14001cbbe  mov     ecx, eax
0x14001cbc0  lock cmpxchg [rdi+10h], ecx
0x14001cbc5  jnz     short loc_14001CBBE
0x14001cbc7  test    eax, eax
0x14001cbc9  jnz     loc_14001CC50
0x14001cbcf  lea     rbp, [rdi+20h]
0x14001cbd3  mov     [rsp+68h+var_48], rbp
0x14001cbd8  mov     rcx, rbp; lpCriticalSection
0x14001cbdb  call    cs:__imp_EnterCriticalSection
0x14001cbe1  nop
0x14001cbe2  prefetchw byte ptr [rdi+10h]
0x14001cbe6  mov     eax, [rdi+10h]
0x14001cbe9  mov     ecx, eax
0x14001cbeb  lock cmpxchg [rdi+10h], ecx
0x14001cbf0  jnz     short loc_14001CBE9
0x14001cbf2  test    eax, eax
0x14001cbf4  jnz     short loc_14001CC42
0x14001cbf6  mov     rsi, [rdi+60h]
0x14001cbfa  lea     r9, [rsp+68h+var_40]
0x14001cbff  mov     r8, [rsi+8]
0x14001cc03  mov     rdx, rsi
0x14001cc06  call    ??$_Buynode@AEBQEAV_CancellationTokenRegistration@details@pplx@@@?$_List_buy@PEAV_CancellationTokenRegistration@details@pplx@@V?$allocator@PEAV_CancellationTokenRegistration@details@pplx@@@std@@@std@@QEAAPEAU?$_List_node@PEAV_CancellationTokenRegistration@details@pplx@@PEAX@1@PEAU21@0AEBQEAV_CancellationTokenRegistration@details@pplx@@@Z; std::_List_buy<pplx::details::_CancellationTokenRegistration *>::_Buynode<pplx::details::_CancellationTokenRegistration * const &>(std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *,std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *,pplx::details::_CancellationTokenRegistration * const &)
0x14001cc0b  mov     rdx, rax
0x14001cc0e  mov     rax, [rdi+68h]
0x14001cc12  mov     rcx, 0AAAAAAAAAAAAAA9h
0x14001cc1c  sub     rcx, rax
0x14001cc1f  cmp     rcx, r14
0x14001cc22  jb      loc_14001CCD3
0x14001cc28  xor     r14b, r14b
0x14001cc2b  inc     rax
0x14001cc2e  mov     [rdi+68h], rax
0x14001cc32  mov     [rsi+8], rdx
0x14001cc36  mov     rax, [rdx+8]
0x14001cc3a  mov     [rax], rdx
0x14001cc3d  mov     rsi, [rsp+68h+var_40]
0x14001cc42  mov     rcx, rbp; lpCriticalSection
0x14001cc45  call    cs:__imp_LeaveCriticalSection
0x14001cc4b  test    r14b, r14b
0x14001cc4e  jz      short loc_14001CCA9
0x14001cc50  call    cs:__imp_GetCurrentThreadId
0x14001cc56  mov     edi, eax
0x14001cc58  xor     eax, eax
0x14001cc5a  lock cmpxchg [rsi+10h], edi
0x14001cc5f  jnz     short loc_14001CC8D
0x14001cc61  mov     rcx, [rsi]
0x14001cc64  mov     rax, [rcx+10h]
0x14001cc68  mov     rcx, rsi
0x14001cc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cc70  mov     eax, edi
0x14001cc72  lock cmpxchg [rsi+10h], r13d
0x14001cc78  cmovnz  edi, eax
0x14001cc7b  cmp     edi, 2
0x14001cc7e  jnz     short loc_14001CC8D
0x14001cc80  mov     rcx, [rsi+18h]
0x14001cc84  mov     rcx, [rcx]; hEvent
0x14001cc87  call    cs:__imp_SetEvent
0x14001cc8d  or      eax, 0FFFFFFFFh
0x14001cc90  lock xadd [rsi+8], eax
0x14001cc95  cmp     eax, 1
0x14001cc98  jnz     short loc_14001CCA9
0x14001cc9a  mov     rax, [rsi]
0x14001cc9d  mov     rcx, rsi
0x14001cca0  mov     rax, [rax+8]
0x14001cca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cca9  mov     [r15+78h], rbx
0x14001ccad  mov     rcx, [rsp+68h+var_38]
0x14001ccb2  xor     rcx, rsp; StackCookie
0x14001ccb5  call    __security_check_cookie
0x14001ccba  lea     r11, [rsp+68h+var_28]
0x14001ccbf  mov     rbx, [r11+38h]
0x14001ccc3  mov     rbp, [r11+40h]
0x14001ccc7  mov     rsp, r11
0x14001ccca  pop     r15
0x14001cccc  pop     r14
0x14001ccce  pop     r13
0x14001ccd0  pop     rdi
0x14001ccd1  pop     rsi
0x14001ccd2  retn
0x14001ccd3  lea     rcx, aListTTooLong; "list<T> too long"
0x14001ccda  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
