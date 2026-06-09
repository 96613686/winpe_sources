# wil::details::threadpool_timer_context::threadpool_timer_context(std::function<void (void)> &&)

- ea: `0x18001e1ac`
- end: `0x18001e3c6`
- name: `??0threadpool_timer_context@details@wil@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f1c8`

## callees

- `0x180001b9c`
- `0x18000944c`
- `0x18001dd3c`
- `0x18001e1ac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e32a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e32a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e1dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e1dd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e337`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e337`

## pseudocode

```c
__int64 __fastcall wil::details::threadpool_timer_context::threadpool_timer_context(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rcx
  __int64 v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char *v18; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v20; // [rsp+70h] [rbp+18h] BYREF
  __int64 v21; // [rsp+78h] [rbp+20h]

  v21 = a1;
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v4 = qword_180044440;
  if ( qword_180044440 )
  {
    v5 = *(_DWORD *)(qword_180044440 + 8);
    while ( v5 )
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
      if ( v6 == v5 )
      {
        *(_QWORD *)a1 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance;
        *(_QWORD *)(a1 + 8) = qword_180044440;
        break;
      }
    }
  }
  if ( !*(_QWORD *)a1 )
  {
    v18 = (char *)operator new(0x28u);
    *(_OWORD *)v18 = 0;
    *((_DWORD *)v18 + 2) = 1;
    *((_DWORD *)v18 + 3) = 1;
    *(_QWORD *)v18 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable';
    *(_QWORD *)(v18 + 28) = 0;
    *((_DWORD *)v18 + 9) = 0;
    *((_QWORD *)v18 + 2) = &Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar::`vftable';
    *((_DWORD *)v18 + 6) = 0;
    v20 = 3;
    ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      (void **)v18 + 4,
      &v20);
    *(_QWORD *)a1 = v18 + 16;
    v7 = *(volatile signed __int32 **)(a1 + 8);
    *(_QWORD *)(a1 + 8) = v18;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = *(_QWORD *)(a1 + 8);
    if ( v8 )
    {
      v9 = *(_QWORD *)a1;
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 12));
    }
    else
    {
      v9 = 0;
      v8 = 0;
    }
    Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance = v9;
    v10 = (volatile signed __int32 *)qword_180044440;
    qword_180044440 = v8;
    if ( v10 && _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
  }
  ReleaseSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock);
  v11 = *(_QWORD *)a1;
  if ( !ResetEvent(*(HANDLE *)(*(_QWORD *)a1 + 16LL)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA06, v12, v13);
  _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)(a1 + 72) = 0;
  v14 = *(_QWORD *)(a2 + 56);
  if ( v14 )
  {
    if ( v14 != a2 )
    {
      *(_QWORD *)(a1 + 72) = v14;
      goto LABEL_24;
    }
    *(_QWORD *)(a1 + 72) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, a1 + 16);
    v16 = *(_QWORD *)(a2 + 56);
    if ( v16 )
    {
      LOBYTE(v15) = v16 != a2;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 32LL))(v16, v15);
LABEL_24:
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 100) = 0;
  return a1;
}

```

## disassembly

```asm
0x18001e1ac  mov     rax, rsp
0x18001e1af  mov     [rax+10h], rbx
0x18001e1b3  mov     [rax+8], rcx
0x18001e1b7  push    rbp
0x18001e1b8  push    rsi
0x18001e1b9  push    rdi
0x18001e1ba  push    r12
0x18001e1bc  push    r14
0x18001e1be  sub     rsp, 30h
0x18001e1c2  mov     rbp, rdx
0x18001e1c5  mov     rsi, rcx
0x18001e1c8  xor     r14d, r14d
0x18001e1cb  mov     [rax+8], r14d
0x18001e1cf  mov     [rax+20h], rcx
0x18001e1d3  lea     r12, ?s_lock@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_lock
0x18001e1da  mov     rcx, r12; SRWLock
0x18001e1dd  call    cs:__imp_AcquireSRWLockExclusive
0x18001e1e3  mov     [rsp+58h+var_38], r12
0x18001e1e8  mov     [rsi], r14
0x18001e1eb  mov     [rsi+8], r14
0x18001e1ef  mov     rdx, cs:qword_180044440
0x18001e1f6  test    rdx, rdx
0x18001e1f9  jz      short loc_18001E225
0x18001e1fb  mov     eax, [rdx+8]
0x18001e1fe  jmp     short loc_18001E20A
0x18001e200  lea     ecx, [rax+1]
0x18001e203  lock cmpxchg [rdx+8], ecx
0x18001e208  jz      short loc_18001E210
0x18001e20a  test    eax, eax
0x18001e20c  jnz     short loc_18001E200
0x18001e20e  jmp     short loc_18001E225
0x18001e210  mov     rax, cs:?s_instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@A; std::weak_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance
0x18001e217  mov     [rsi], rax
0x18001e21a  mov     rax, cs:qword_180044440
0x18001e221  mov     [rsi+8], rax
0x18001e225  mov     [rsp+58h+arg_0], 1
0x18001e22d  cmp     [rsi], r14
0x18001e230  jnz     loc_18001E327
0x18001e236  mov     ecx, 28h ; '('; Size
0x18001e23b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e240  mov     rdi, rax
0x18001e243  mov     [rsp+58h+var_30], rax
0x18001e248  xorps   xmm0, xmm0
0x18001e24b  movups  xmmword ptr [rax], xmm0
0x18001e24e  mov     dword ptr [rax+8], 1
0x18001e255  mov     dword ptr [rax+0Ch], 1
0x18001e25c  lea     rax, ??_7?$_Ref_count_obj2@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable'
0x18001e263  mov     [rdi], rax
0x18001e266  lea     rbx, [rdi+10h]
0x18001e26a  mov     [rbx+0Ch], r14
0x18001e26e  mov     [rbx+14h], r14d
0x18001e272  lea     rax, ??_7ThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar::`vftable'
0x18001e279  mov     [rbx], rax
0x18001e27c  mov     [rbx+8], r14d
0x18001e280  mov     [rsp+58h+arg_10], 3
0x18001e288  lea     rcx, [rbx+10h]
0x18001e28c  lea     rdx, [rsp+58h+arg_10]
0x18001e291  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18001e296  nop
0x18001e297  mov     [rsi], rbx
0x18001e29a  mov     rbx, [rsi+8]
0x18001e29e  mov     [rsi+8], rdi
0x18001e2a2  or      edi, 0FFFFFFFFh
0x18001e2a5  test    rbx, rbx
0x18001e2a8  jz      short loc_18001E2DD
0x18001e2aa  mov     eax, edi
0x18001e2ac  lock xadd [rbx+8], eax
0x18001e2b1  add     eax, edi
0x18001e2b3  jnz     short loc_18001E2DD
0x18001e2b5  mov     rax, [rbx]
0x18001e2b8  mov     rcx, rbx
0x18001e2bb  mov     rax, [rax]
0x18001e2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c3  mov     eax, edi
0x18001e2c5  lock xadd [rbx+0Ch], eax
0x18001e2ca  add     eax, edi
0x18001e2cc  jnz     short loc_18001E2DD
0x18001e2ce  mov     rax, [rbx]
0x18001e2d1  mov     rcx, rbx
0x18001e2d4  mov     rax, [rax+8]
0x18001e2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2dd  mov     rax, [rsi+8]
0x18001e2e1  test    rax, rax
0x18001e2e4  jz      short loc_18001E2EF
0x18001e2e6  mov     rcx, [rsi]
0x18001e2e9  lock inc dword ptr [rax+0Ch]
0x18001e2ed  jmp     short loc_18001E2F5
0x18001e2ef  mov     rcx, r14
0x18001e2f2  mov     rax, r14
0x18001e2f5  mov     cs:?s_instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@A, rcx; std::weak_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::s_instance
0x18001e2fc  mov     rcx, cs:qword_180044440
0x18001e303  mov     cs:qword_180044440, rax
0x18001e30a  test    rcx, rcx
0x18001e30d  jz      short loc_18001E327
0x18001e30f  mov     eax, edi
0x18001e311  lock xadd [rcx+0Ch], eax
0x18001e316  add     eax, edi
0x18001e318  jnz     short loc_18001E327
0x18001e31a  mov     rax, [rcx]
0x18001e31d  mov     rax, [rax+8]
0x18001e321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e326  nop
0x18001e327  mov     rcx, r12; SRWLock
0x18001e32a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e330  mov     rbx, [rsi]
0x18001e333  mov     rcx, [rbx+10h]; hEvent
0x18001e337  call    cs:__imp_ResetEvent
0x18001e33d  mov     rcx, [rsp+58h]; this
0x18001e342  test    eax, eax
0x18001e344  jz      short loc_18001E3BB
0x18001e346  lock inc dword ptr [rbx+8]
0x18001e34a  mov     [rsi+48h], r14
0x18001e34e  mov     rcx, [rbp+38h]
0x18001e352  test    rcx, rcx
0x18001e355  jz      short loc_18001E395
0x18001e357  cmp     rcx, rbp
0x18001e35a  jnz     short loc_18001E38D
0x18001e35c  mov     rax, [rcx]
0x18001e35f  lea     rdx, [rsi+10h]
0x18001e363  mov     rax, [rax+8]
0x18001e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e36c  mov     [rsi+48h], rax
0x18001e370  mov     rcx, [rbp+38h]
0x18001e374  test    rcx, rcx
0x18001e377  jz      short loc_18001E395
0x18001e379  mov     rax, [rcx]
0x18001e37c  cmp     rcx, rbp
0x18001e37f  setnz   dl
0x18001e382  mov     rax, [rax+20h]
0x18001e386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e38b  jmp     short loc_18001E391
0x18001e38d  mov     [rsi+48h], rcx
0x18001e391  mov     [rbp+38h], r14
0x18001e395  mov     [rsi+50h], r14
0x18001e399  xor     eax, eax
0x18001e39b  mov     [rsi+58h], rax
0x18001e39f  mov     [rsi+60h], r14d
0x18001e3a3  mov     [rsi+64h], r14b
0x18001e3a7  mov     rax, rsi
0x18001e3aa  mov     rbx, [rsp+58h+arg_8]
0x18001e3af  add     rsp, 30h
0x18001e3b3  pop     r14
0x18001e3b5  pop     r12
0x18001e3b7  pop     rdi
0x18001e3b8  pop     rsi
0x18001e3b9  pop     rbp
0x18001e3ba  retn
0x18001e3bb  mov     edx, 0A06h; void *
0x18001e3c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
