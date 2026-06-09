# Microsoft::Bluetooth::Foundation::StateMachineTimer::Init(void)

- ea: `0x18001f1c8`
- end: `0x18001f513`
- name: `?Init@StateMachineTimer@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `843`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::StateMachineTimer *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001f51c`

## callees

- `0x180001790`
- `0x180001b9c`
- `0x180001e70`
- `0x180007bc4`
- `0x180007be4`
- `0x180010cac`
- `0x18001d95c`
- `0x18001e1ac`
- `0x18001e4bc`
- `0x18001f1c8`
- `0x18001f99c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f32f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f32f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f203`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f43a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f43a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f3db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f44c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f3db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f44c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f3b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001f3b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f3d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f3d3`

## string_xrefs

- `0x18001f396`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x18001f3f1`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x18001f501`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::Init(
        Microsoft::Bluetooth::Foundation::StateMachineTimer *this)
{
  char *v2; // xmm0_8
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  char *v6; // rsi
  char *v7; // rdi
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v10; // rbx
  struct wil::details::threadpool_timer_context *v11; // r14
  wil::details::threadpool_object_context *v12; // rax
  RTL_SRWLOCK *v13; // rsi
  int v14; // ebx
  __int64 v15; // rdx
  const char *v16; // r9
  PTP_TIMER ThreadpoolTimer; // r15
  struct _TP_TIMER *Ptr; // r12
  DWORD LastError; // ebx
  const char *v20; // r9
  struct wil::details::threadpool_timer_context **v21; // rsi
  struct wil::details::threadpool_timer_context *v22; // r15
  DWORD v23; // ebx
  _QWORD *v24; // rdx
  RTL_SRWLOCK *v25; // [rsp+20h] [rbp-69h] BYREF
  int v26; // [rsp+28h] [rbp-61h]
  __int128 v27; // [rsp+30h] [rbp-59h]
  char v28; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v29[7]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD *v30; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v26 = 0;
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock);
  v25 = &Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock;
  v2 = 0;
  v27 = 0;
  v3 = *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
       + 1);
  if ( *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
       + 1) )
  {
    v4 = *(_DWORD *)(*((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
                     + 1)
                   + 8LL);
    while ( v4 )
    {
      v5 = v4;
      v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
      if ( v5 == v4 )
      {
        v2 = (char *)Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance;
        v27 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance;
        break;
      }
    }
  }
  v26 = 1;
  v6 = v2;
  if ( v2 )
  {
    v7 = (char *)*((_QWORD *)&v27 + 1);
  }
  else
  {
    v7 = (char *)operator new(0x28u);
    v25 = (RTL_SRWLOCK *)v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable';
    v6 = v7 + 16;
    *((_QWORD *)v7 + 2) = &Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`vftable';
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    v26 = 7;
    *(_QWORD *)&v27 = v7 + 16;
    v8 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
    *((_QWORD *)&v27 + 1) = v7;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    _InterlockedAdd((volatile signed __int32 *)v7 + 3, 1u);
    *(_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance = v7 + 16;
    v9 = (volatile signed __int32 *)*((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
                                    + 1);
    *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
    + 1) = v7;
    if ( v9 && _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  ReleaseSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock);
  v29[0] = &std::_Func_impl_no_alloc<_lambda_f604df4af10e482d3da48bf7aa3884e9_,void,>::`vftable';
  v29[1] = this;
  v30 = v29;
  v10 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)v6 + 1);
  v11 = 0;
  v12 = (wil::details::threadpool_object_context *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v25 = (RTL_SRWLOCK *)v12;
  if ( v12 )
    v13 = (RTL_SRWLOCK *)wil::details::threadpool_timer_context::threadpool_timer_context((__int64)v12, (__int64)v29);
  else
    v13 = 0;
  v25 = v13;
  if ( v13 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_25492e723f3fb512063019ab9c6aa90a_::_lambda_invoker_cdecl_, v13, v10);
    Ptr = (struct _TP_TIMER *)v13[10].Ptr;
    if ( Ptr )
    {
      LastError = GetLastError();
      CloseThreadpoolTimer(Ptr);
      SetLastError(LastError);
    }
    v13[10].Ptr = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v25 = 0;
      v11 = (struct wil::details::threadpool_timer_context *)v13;
      v14 = 0;
    }
    else
    {
      v14 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x182,
              (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
              v16);
    }
  }
  else
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)0x8007000ELL,
      0);
  }
  std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(
    (wil::details::threadpool_object_context **)&v25,
    v15);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)(unsigned int)v14,
      (int)v25);
  v21 = (struct wil::details::threadpool_timer_context **)((char *)this + 24);
  if ( (char *)this + 24 == &v28 )
  {
    if ( v11 )
      wil::details::threadpool_timer_context::RequestRelease(v11);
  }
  else
  {
    v22 = *v21;
    if ( *v21 )
    {
      v23 = GetLastError();
      wil::details::threadpool_timer_context::RequestRelease(v22);
      SetLastError(v23);
    }
    *v21 = v11;
  }
  if ( v30 )
  {
    v24 = v29;
    LOBYTE(v24) = v30 != v29;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v30 + 32LL))(v30, v24);
    v30 = 0;
  }
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v7)(v7);
      if ( !_InterlockedDecrement((volatile signed __int32 *)v7 + 3) )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( !*v21 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateMachines.h",
      v20);
}

```

## disassembly

```asm
0x18001f1c8  push    rbp
0x18001f1ca  push    rbx
0x18001f1cb  push    rsi
0x18001f1cc  push    rdi
0x18001f1cd  push    r12
0x18001f1cf  push    r13
0x18001f1d1  push    r14
0x18001f1d3  push    r15
0x18001f1d5  lea     rbp, [rsp-1Fh]
0x18001f1da  sub     rsp, 0A8h
0x18001f1e1  mov     rax, cs:__security_cookie
0x18001f1e8  xor     rax, rsp
0x18001f1eb  mov     [rbp+57h+var_50], rax
0x18001f1ef  mov     r13, rcx
0x18001f1f2  xor     r12d, r12d
0x18001f1f5  mov     [rbp+57h+var_B8], r12d
0x18001f1f9  lea     rdi, ?s_lock@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock
0x18001f200  mov     rcx, rdi; SRWLock
0x18001f203  call    cs:__imp_AcquireSRWLockExclusive
0x18001f209  mov     [rbp+57h+var_C0], rdi
0x18001f20d  xorps   xmm0, xmm0
0x18001f210  movdqu  [rbp+57h+var_B0], xmm0
0x18001f215  mov     rdx, qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18001f21c  test    rdx, rdx
0x18001f21f  jz      short loc_18001F242
0x18001f221  mov     eax, [rdx+8]
0x18001f224  jmp     short loc_18001F230
0x18001f226  lea     ecx, [rax+1]
0x18001f229  lock cmpxchg [rdx+8], ecx
0x18001f22e  jz      short loc_18001F236
0x18001f230  test    eax, eax
0x18001f232  jnz     short loc_18001F226
0x18001f234  jmp     short loc_18001F242
0x18001f236  movups  xmm0, cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18001f23d  movdqu  [rbp+57h+var_B0], xmm0
0x18001f242  mov     r15d, 1
0x18001f248  mov     [rbp+57h+var_B8], r15d
0x18001f24c  or      r14d, 0FFFFFFFFh
0x18001f250  movq    rsi, xmm0
0x18001f255  test    rsi, rsi
0x18001f258  jnz     loc_18001F324
0x18001f25e  lea     ecx, [rsi+28h]; Size
0x18001f261  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f266  mov     rdi, rax
0x18001f269  mov     [rbp+57h+var_C0], rax
0x18001f26d  xorps   xmm0, xmm0
0x18001f270  movups  xmmword ptr [rax], xmm0
0x18001f273  mov     [rax+8], r15d
0x18001f277  mov     [rax+0Ch], r15d
0x18001f27b  lea     rax, ??_7?$_Ref_count_obj2@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable'
0x18001f282  mov     [rdi], rax
0x18001f285  lea     rsi, [rdi+10h]
0x18001f289  lea     rax, ??_7ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`vftable'
0x18001f290  mov     [rsi], rax
0x18001f293  mov     [rsi+8], r12
0x18001f297  mov     [rsi+10h], r12
0x18001f29b  mov     [rbp+57h+var_B8], 7
0x18001f2a2  mov     qword ptr [rbp+57h+var_B0], rsi
0x18001f2a6  mov     rbx, qword ptr [rbp+57h+var_B0+8]
0x18001f2aa  mov     qword ptr [rbp+57h+var_B0+8], rdi
0x18001f2ae  test    rbx, rbx
0x18001f2b1  jz      short loc_18001F2EA
0x18001f2b3  mov     eax, r14d
0x18001f2b6  lock xadd [rbx+8], eax
0x18001f2bb  add     eax, r14d
0x18001f2be  jnz     short loc_18001F2EA
0x18001f2c0  mov     rax, [rbx]
0x18001f2c3  mov     rcx, rbx
0x18001f2c6  mov     rax, [rax]
0x18001f2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ce  mov     eax, r14d
0x18001f2d1  lock xadd [rbx+0Ch], eax
0x18001f2d6  add     eax, r14d
0x18001f2d9  jnz     short loc_18001F2EA
0x18001f2db  mov     rax, [rbx]
0x18001f2de  mov     rcx, rbx
0x18001f2e1  mov     rax, [rax+8]
0x18001f2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2ea  lock add [rdi+0Ch], r15d
0x18001f2ef  mov     qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A, rsi; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18001f2f6  mov     rcx, qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18001f2fd  mov     qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8, rdi; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18001f304  test    rcx, rcx
0x18001f307  jz      short loc_18001F328
0x18001f309  mov     eax, r14d
0x18001f30c  lock xadd [rcx+0Ch], eax
0x18001f311  add     eax, r14d
0x18001f314  jnz     short loc_18001F328
0x18001f316  mov     rax, [rcx]
0x18001f319  mov     rax, [rax+8]
0x18001f31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f322  jmp     short loc_18001F328
0x18001f324  mov     rdi, qword ptr [rbp+57h+var_B0+8]
0x18001f328  lea     rcx, ?s_lock@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; SRWLock
0x18001f32f  call    cs:__imp_ReleaseSRWLockExclusive
0x18001f335  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_f604df4af10e482d3da48bf7aa3884e9_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_f604df4af10e482d3da48bf7aa3884e9_,void,>::`vftable'
0x18001f33c  mov     [rbp+57h+var_90], rax
0x18001f340  mov     [rbp+57h+var_88], r13
0x18001f344  lea     rax, [rbp+57h+var_90]
0x18001f348  mov     [rbp+57h+var_58], rax
0x18001f34c  mov     rbx, [rsi+8]
0x18001f350  mov     r14, r12
0x18001f353  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f35a  mov     ecx, 68h ; 'h'; unsigned __int64
0x18001f35f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f364  mov     [rbp+57h+var_C0], rax
0x18001f368  test    rax, rax
0x18001f36b  jz      short loc_18001F37E
0x18001f36d  lea     rdx, [rbp+57h+var_90]
0x18001f371  mov     rcx, rax
0x18001f374  call    ??0threadpool_timer_context@details@wil@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@@Z; wil::details::threadpool_timer_context::threadpool_timer_context(std::function<void (void)> &&)
0x18001f379  mov     rsi, rax
0x18001f37c  jmp     short loc_18001F381
0x18001f37e  mov     rsi, r12
0x18001f381  mov     [rbp+57h+var_C0], rsi
0x18001f385  test    rsi, rsi
0x18001f388  jnz     short loc_18001F3A9
0x18001f38a  mov     rcx, [rbp+5Fh]; this
0x18001f38e  mov     ebx, 8007000Eh
0x18001f393  mov     r9d, ebx; char *
0x18001f396  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x18001f39d  mov     edx, 177h; void *
0x18001f3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3a7  jmp     short loc_18001F410
0x18001f3a9  mov     r8, rbx; pcbe
0x18001f3ac  mov     rdx, rsi; pv
0x18001f3af  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_25492e723f3fb512063019ab9c6aa90a_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001f3b6  call    cs:__imp_CreateThreadpoolTimer
0x18001f3bc  mov     r15, rax
0x18001f3bf  mov     r12, [rsi+50h]
0x18001f3c3  test    r12, r12
0x18001f3c6  jz      short loc_18001F3E1
0x18001f3c8  call    cs:__imp_GetLastError
0x18001f3ce  mov     ebx, eax
0x18001f3d0  mov     rcx, r12; pti
0x18001f3d3  call    cs:__imp_CloseThreadpoolTimer
0x18001f3d9  mov     ecx, ebx; dwErrCode
0x18001f3db  call    cs:__imp_SetLastError
0x18001f3e1  mov     [rsi+50h], r15
0x18001f3e5  xor     r12d, r12d
0x18001f3e8  test    r15, r15
0x18001f3eb  jnz     short loc_18001F406
0x18001f3ed  mov     rcx, [rbp+5Fh]; this
0x18001f3f1  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x18001f3f8  mov     edx, 182h; void *
0x18001f3fd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f402  mov     ebx, eax
0x18001f404  jmp     short loc_18001F410
0x18001f406  mov     [rbp+57h+var_C0], r12
0x18001f40a  mov     r14, rsi
0x18001f40d  mov     ebx, r12d
0x18001f410  lea     rcx, [rbp+57h+var_C0]
0x18001f414  call    ??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(void)
0x18001f419  mov     rcx, [rbp+5Fh]; this
0x18001f41d  test    ebx, ebx
0x18001f41f  js      loc_18001F4FE
0x18001f425  lea     rsi, [r13+18h]
0x18001f429  lea     rax, [rbp+57h+var_A0]
0x18001f42d  cmp     rsi, rax
0x18001f430  jz      short loc_18001F457
0x18001f432  mov     r15, [rsi]
0x18001f435  test    r15, r15
0x18001f438  jz      short loc_18001F452
0x18001f43a  call    cs:__imp_GetLastError
0x18001f440  mov     ebx, eax
0x18001f442  mov     rcx, r15; this
0x18001f445  call    ?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z; wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)
0x18001f44a  mov     ecx, ebx; dwErrCode
0x18001f44c  call    cs:__imp_SetLastError
0x18001f452  mov     [rsi], r14
0x18001f455  jmp     short loc_18001F465
0x18001f457  test    r14, r14
0x18001f45a  jz      short loc_18001F465
0x18001f45c  mov     rcx, r14; this
0x18001f45f  call    ?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z; wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)
0x18001f464  nop
0x18001f465  mov     rcx, [rbp+57h+var_58]
0x18001f469  test    rcx, rcx
0x18001f46c  jz      short loc_18001F488
0x18001f46e  mov     rax, [rcx]
0x18001f471  lea     rdx, [rbp+57h+var_90]
0x18001f475  cmp     rcx, rdx
0x18001f478  setnz   dl
0x18001f47b  mov     rax, [rax+20h]
0x18001f47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f484  mov     [rbp+57h+var_58], r12
0x18001f488  test    rdi, rdi
0x18001f48b  jz      short loc_18001F4C3
0x18001f48d  or      ebx, 0FFFFFFFFh
0x18001f490  mov     eax, ebx
0x18001f492  lock xadd [rdi+8], eax
0x18001f497  add     eax, ebx
0x18001f499  jnz     short loc_18001F4C3
0x18001f49b  mov     rax, [rdi]
0x18001f49e  mov     rcx, rdi
0x18001f4a1  mov     rax, [rax]
0x18001f4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4a9  mov     eax, ebx
0x18001f4ab  lock xadd [rdi+0Ch], eax
0x18001f4b0  add     eax, ebx
0x18001f4b2  jnz     short loc_18001F4C3
0x18001f4b4  mov     rax, [rdi]
0x18001f4b7  mov     rcx, rdi
0x18001f4ba  mov     rax, [rax+8]
0x18001f4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4c3  cmp     [rsi], r12
0x18001f4c6  jz      short loc_18001F4E8
0x18001f4c8  mov     rcx, [rbp+57h+var_50]
0x18001f4cc  xor     rcx, rsp; StackCookie
0x18001f4cf  call    __security_check_cookie
0x18001f4d4  add     rsp, 0A8h
0x18001f4db  pop     r15
0x18001f4dd  pop     r14
0x18001f4df  pop     r13
0x18001f4e1  pop     r12
0x18001f4e3  pop     rdi
0x18001f4e4  pop     rsi
0x18001f4e5  pop     rbx
0x18001f4e6  pop     rbp
0x18001f4e7  retn
0x18001f4e8  mov     rcx, [rbp+5Fh]; this
0x18001f4ec  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\bluetooth\\foundation"...
0x18001f4f3  mov     edx, 82h; void *
0x18001f4f8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001f4fe  mov     r9d, ebx; char *
0x18001f501  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x18001f508  mov     edx, 1AFh; void *
0x18001f50d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
