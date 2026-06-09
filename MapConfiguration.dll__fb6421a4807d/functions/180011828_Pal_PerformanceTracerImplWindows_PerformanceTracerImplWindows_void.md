# Pal::PerformanceTracerImplWindows::~PerformanceTracerImplWindows(void)

- ea: `0x180011828`
- end: `0x18001191e`
- name: `??1PerformanceTracerImplWindows@Pal@@UEAA@XZ`
- size: `246`
- prototype: `void __fastcall(Pal::PerformanceTracerImplWindows *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012a70`

## callees

- `0x18000d980`
- `0x18000e288`
- `0x180010f54`
- `0x180010f74`
- `0x180011828`
- `0x180017078`
- `0x180018368`
- `0x1800183a4`
- `0x18001ab80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800118f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800118f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001185a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001185a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001186c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001186c`

## pseudocode

```c
void __fastcall Pal::PerformanceTracerImplWindows::~PerformanceTracerImplWindows(
        Pal::PerformanceTracerImplWindows *this)
{
  __int64 v2; // rbx
  char *v3; // r14
  _QWORD *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  Pal::PerformanceTracerImplWindows *v7; // [rsp+20h] [rbp-30h] BYREF
  __int128 v8; // [rsp+28h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-18h] BYREF

  *(_QWORD *)this = &Pal::PerformanceTracerImplWindows::`vftable';
  Pal::Lockable_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::getScopedLock(
    this,
    v9);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = *((_OWORD *)this + 4);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = v9[0];
  std::_Hash_std::_Umap_traits__GUID__anonymous_namespace_::EventHandle_std::_Uhash_compare__GUID__anonymous_namespace_::GUIDHasher_std::equal_to__GUID____std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle____0___::find(
    v9[0],
    &v7,
    &v8);
  if ( v7 != *(Pal::PerformanceTracerImplWindows **)(v2 + 8) )
  {
    v3 = (char *)v7 + 32;
    Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::getScopedLock(
      (char *)v7 + 56,
      &v8);
    v4 = (_QWORD *)v8;
    v7 = this;
    v5 = std::_Find_unchecked<Pal::PerformanceTracerImplWindows * *,Pal::PerformanceTracerImplWindows const *>(
           *(_QWORD *)v8,
           *(_QWORD *)(v8 + 8),
           &v7);
    v6 = v4[1];
    if ( v5 != v6 )
    {
      std::_Copy_memmove<Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *>(
        (void *)(v5 + 8),
        v6,
        (void *)v5);
      v4[1] -= 8LL;
    }
    if ( *v4 == v4[1] )
      anonymous_namespace_::EventHandle::unregisterEventNotifications(v3);
    Pal::ScopedLockableValue<std::vector<Pal::PerformanceTracerImplWindows *>>::~ScopedLockableValue<std::vector<Pal::PerformanceTracerImplWindows *>>(&v8);
  }
  Pal::ScopedLockableValue_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::_ScopedLockableValue_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &Pal::PerformanceTracerImpl::`vftable';
}

```

## disassembly

```asm
0x180011828  mov     [rsp-18h+arg_8], rbx
0x18001182d  mov     [rsp-18h+arg_10], rsi
0x180011832  push    rbp
0x180011833  push    rdi
0x180011834  push    r14
0x180011836  mov     rbp, rsp
0x180011839  sub     rsp, 50h
0x18001183d  lea     rax, ??_7PerformanceTracerImplWindows@Pal@@6B@; const Pal::PerformanceTracerImplWindows::`vftable'
0x180011844  mov     rdi, rcx
0x180011847  lea     rdx, [rbp+var_18]
0x18001184b  mov     [rcx], rax
0x18001184e  call    Pal__Lockable_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle_________getScopedLock
0x180011853  lea     rsi, [rdi+18h]
0x180011857  mov     rcx, rsi; lpCriticalSection
0x18001185a  call    cs:__imp_EnterCriticalSection
0x180011860  movups  xmm0, xmmword ptr [rsi+28h]
0x180011864  mov     rcx, rsi; lpCriticalSection
0x180011867  movdqu  [rbp+var_28], xmm0
0x18001186c  call    cs:__imp_LeaveCriticalSection
0x180011872  mov     rbx, [rbp+var_18]
0x180011876  lea     r8, [rbp+var_28]
0x18001187a  mov     rcx, rbx
0x18001187d  lea     rdx, [rbp+var_30]
0x180011881  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0_____find
0x180011886  mov     r8, [rbp+var_30]
0x18001188a  cmp     r8, [rbx+8]
0x18001188e  jz      short loc_1800118ED
0x180011890  lea     r14, [r8+20h]
0x180011894  lea     rcx, [r14+18h]
0x180011898  lea     rdx, [rbp+var_28]
0x18001189c  call    ?getScopedLock@?$Lockable@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@Pal@@QEAA?AV?$ScopedLockableValue@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@2@XZ; Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::getScopedLock(void)
0x1800118a1  mov     rbx, qword ptr [rbp+var_28]
0x1800118a5  lea     r8, [rbp+var_30]
0x1800118a9  mov     [rbp+var_30], rdi
0x1800118ad  mov     rdx, [rbx+8]
0x1800118b1  mov     rcx, [rbx]
0x1800118b4  call    ??$_Find_unchecked@PEAPEAVPerformanceTracerImplWindows@Pal@@PEBV12@@std@@YAPEAPEAVPerformanceTracerImplWindows@Pal@@PEAPEAV12@QEAPEAV12@AEBQEBV12@@Z; std::_Find_unchecked<Pal::PerformanceTracerImplWindows * *,Pal::PerformanceTracerImplWindows const *>(Pal::PerformanceTracerImplWindows * *,Pal::PerformanceTracerImplWindows * * const,Pal::PerformanceTracerImplWindows const * const &)
0x1800118b9  mov     rdx, [rbx+8]
0x1800118bd  cmp     rax, rdx
0x1800118c0  jz      short loc_1800118D3
0x1800118c2  lea     rcx, [rax+8]; Src
0x1800118c6  mov     r8, rax
0x1800118c9  call    ??$_Copy_memmove@PEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@@std@@YAPEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@00@Z; std::_Copy_memmove<Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *>(Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *)
0x1800118ce  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFF8h
0x1800118d3  mov     rax, [rbx+8]
0x1800118d7  cmp     [rbx], rax
0x1800118da  jnz     short loc_1800118E4
0x1800118dc  mov     rcx, r14
0x1800118df  call    _anonymous_namespace___EventHandle__unregisterEventNotifications
0x1800118e4  lea     rcx, [rbp+var_28]
0x1800118e8  call    ??1?$ScopedLockableValue@V?$vector@PEAVPerformanceTracerImplWindows@Pal@@V?$allocator@PEAVPerformanceTracerImplWindows@Pal@@@std@@@std@@@Pal@@QEAA@XZ; Pal::ScopedLockableValue<std::vector<Pal::PerformanceTracerImplWindows *>>::~ScopedLockableValue<std::vector<Pal::PerformanceTracerImplWindows *>>(void)
0x1800118ed  lea     rcx, [rbp+var_18]
0x1800118f1  call    Pal__ScopedLockableValue_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle__________ScopedLockableValue_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle_______
0x1800118f6  mov     rcx, rsi; lpCriticalSection
0x1800118f9  call    cs:__imp_DeleteCriticalSection
0x1800118ff  lea     r11, [rsp+50h+var_s0]
0x180011904  mov     rbx, [r11+28h]
0x180011908  lea     rax, ??_7PerformanceTracerImpl@Pal@@6B@; const Pal::PerformanceTracerImpl::`vftable'
0x18001190f  mov     rsi, [r11+30h]
0x180011913  mov     [rdi], rax
0x180011916  mov     rsp, r11
0x180011919  pop     r14
0x18001191b  pop     rdi
0x18001191c  pop     rbp
0x18001191d  retn
```
