# AppV::Client::Host::UserManagerImpl::GetInstance(void)

- ea: `0x140049250`
- end: `0x1400493a9`
- name: `?GetInstance@UserManagerImpl@Host@Client@AppV@@CA?AV?$shared_ptr@VUserManagerImpl@Host@Client@AppV@@@std@@XZ`
- size: `345`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140007e20`
- `0x1400491d0`
- `0x14004a950`

## callees

- `0x1400042a4`
- `0x140047e80`
- `0x140047f94`
- `0x140049250`
- `0x14004b4b4`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400492b9`
- `KERNEL32!GetCurrentThreadId` at `0x1400492b9`
- `KERNEL32!LeaveCriticalSection` at `0x140049389`
- `KERNEL32!LeaveCriticalSection` at `0x140049389`
- `KERNEL32!EnterCriticalSection` at `0x1400492a0`
- `KERNEL32!EnterCriticalSection` at `0x1400492a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall AppV::Client::Host::UserManagerImpl::GetInstance(_QWORD *a1)
{
  struct AppV::Client::Host::UserManagerImpl *v2; // rdx
  struct _RTL_CRITICAL_SECTION *v3; // rax
  __int64 v4; // r8
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+58h] [rbp+10h]

  *a1 = 0;
  a1[1] = 0;
  EnterCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  LODWORD(qword_1400B0FA8) = qword_1400B0FA8 + 1;
  if ( (_DWORD)qword_1400B0FA8 == 1 )
    HIDWORD(qword_1400B0FA8) = GetCurrentThreadId();
  v2 = AppV::Client::Host::UserManagerImpl::st_singleton;
  if ( AppV::Client::Host::UserManagerImpl::st_singleton )
  {
    v4 = *((_QWORD *)AppV::Client::Host::UserManagerImpl::st_singleton + 2);
    if ( !v4 )
LABEL_17:
      std::_Throw_bad_weak_ptr();
    v5 = *(_DWORD *)(v4 + 8);
    do
    {
      if ( !v5 )
        goto LABEL_17;
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
    }
    while ( v6 != v5 );
    v7 = *((_QWORD *)v2 + 2);
    *a1 = *((_QWORD *)v2 + 1);
    v8 = (volatile signed __int32 *)a1[1];
    a1[1] = v7;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  else
  {
    v10 = (struct _RTL_CRITICAL_SECTION *)operator new(0xB8u);
    v3 = AppV::Client::Host::UserManagerImpl::UserManagerImpl(v10);
    std::shared_ptr<AppV::Client::Host::UserManagerImpl>::reset<AppV::Client::Host::UserManagerImpl,0>(a1, v3);
  }
  LODWORD(qword_1400B0FA8) = qword_1400B0FA8 - 1;
  if ( !(_DWORD)qword_1400B0FA8 )
    qword_1400B0FA8 = 0;
  LeaveCriticalSection(&AppV::Client::Host::UserManagerImpl::st_lockSingleton);
  return a1;
}

```

## disassembly

```asm
0x140049250  mov     rax, rsp
0x140049253  mov     [rax+18h], rbx
0x140049257  mov     [rax+20h], rdi
0x14004925b  mov     [rax+8], rcx
0x14004925f  push    r15
0x140049261  sub     rsp, 40h
0x140049265  mov     rdi, rcx
0x140049268  mov     dword ptr [rax-28h], 0
0x14004926f  mov     qword ptr [rcx], 0
0x140049276  mov     qword ptr [rcx+8], 0
0x14004927e  mov     dword ptr [rax-28h], 1
0x140049285  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14004928c  mov     [rsp+48h+var_20], rax
0x140049291  lea     r15, ?st_lockSingleton@UserManagerImpl@Host@Client@AppV@@0Vcritical_section@shared@softricity@@A; softricity::shared::critical_section AppV::Client::Host::UserManagerImpl::st_lockSingleton
0x140049298  mov     [rsp+48h+var_10], r15
0x14004929d  mov     rcx, r15; lpCriticalSection
0x1400492a0  call    cs:__imp_EnterCriticalSection
0x1400492a6  mov     eax, dword ptr cs:qword_1400B0FA8
0x1400492ac  inc     eax
0x1400492ae  mov     dword ptr cs:qword_1400B0FA8, eax
0x1400492b4  cmp     eax, 1
0x1400492b7  jnz     short loc_1400492C5
0x1400492b9  call    cs:__imp_GetCurrentThreadId
0x1400492bf  mov     dword ptr cs:qword_1400B0FA8+4, eax
0x1400492c5  mov     [rsp+48h+var_18], 1
0x1400492ca  mov     rdx, cs:?st_singleton@UserManagerImpl@Host@Client@AppV@@0PEAV1234@EA; AppV::Client::Host::UserManagerImpl * AppV::Client::Host::UserManagerImpl::st_singleton
0x1400492d1  test    rdx, rdx
0x1400492d4  jnz     short loc_1400492FB
0x1400492d6  mov     ecx, 0B8h; Size
0x1400492db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400492e0  mov     [rsp+48h+arg_8], rax
0x1400492e5  mov     rcx, rax; this
0x1400492e8  call    ??0UserManagerImpl@Host@Client@AppV@@AEAA@XZ; AppV::Client::Host::UserManagerImpl::UserManagerImpl(void)
0x1400492ed  nop
0x1400492ee  mov     rdx, rax
0x1400492f1  mov     rcx, rdi
0x1400492f4  call    ??$reset@VUserManagerImpl@Host@Client@AppV@@$0A@@?$shared_ptr@VUserManagerImpl@Host@Client@AppV@@@std@@QEAAXPEAVUserManagerImpl@Host@Client@AppV@@@Z; std::shared_ptr<AppV::Client::Host::UserManagerImpl>::reset<AppV::Client::Host::UserManagerImpl,0>(AppV::Client::Host::UserManagerImpl *)
0x1400492f9  jmp     short loc_140049373
0x1400492fb  mov     r8, [rdx+10h]
0x1400492ff  test    r8, r8
0x140049302  jz      loc_1400493A3
0x140049308  mov     eax, [r8+8]
0x14004930c  jmp     short loc_140049319
0x14004930e  lea     ecx, [rax+1]
0x140049311  lock cmpxchg [r8+8], ecx
0x140049317  jz      short loc_140049323
0x140049319  test    eax, eax
0x14004931b  jz      loc_1400493A3
0x140049321  jmp     short loc_14004930E
0x140049323  mov     rcx, [rdx+10h]
0x140049327  mov     rax, [rdx+8]
0x14004932b  mov     [rdi], rax
0x14004932e  mov     rbx, [rdi+8]
0x140049332  mov     [rdi+8], rcx
0x140049336  test    rbx, rbx
0x140049339  jz      short loc_140049373
0x14004933b  or      eax, 0FFFFFFFFh
0x14004933e  lock xadd [rbx+8], eax
0x140049343  cmp     eax, 1
0x140049346  jnz     short loc_140049373
0x140049348  mov     rax, [rbx]
0x14004934b  mov     rcx, rbx
0x14004934e  mov     rax, [rax]
0x140049351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049356  or      eax, 0FFFFFFFFh
0x140049359  lock xadd [rbx+0Ch], eax
0x14004935e  cmp     eax, 1
0x140049361  jnz     short loc_140049373
0x140049363  mov     rax, [rbx]
0x140049366  mov     rcx, rbx
0x140049369  mov     rax, [rax+8]
0x14004936d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049372  nop
0x140049373  sub     dword ptr cs:qword_1400B0FA8, 1
0x14004937a  jnz     short loc_140049386
0x14004937c  mov     dword ptr cs:qword_1400B0FA8+4, 0
0x140049386  mov     rcx, r15; lpCriticalSection
0x140049389  call    cs:__imp_LeaveCriticalSection
0x14004938f  mov     rax, rdi
0x140049392  mov     rbx, [rsp+48h+arg_10]
0x140049397  mov     rdi, [rsp+48h+arg_18]
0x14004939c  add     rsp, 40h
0x1400493a0  pop     r15
0x1400493a2  retn
0x1400493a3  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
```
