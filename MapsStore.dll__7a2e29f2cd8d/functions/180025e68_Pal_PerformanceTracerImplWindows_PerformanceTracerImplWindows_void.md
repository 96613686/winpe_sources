# Pal::PerformanceTracerImplWindows::~PerformanceTracerImplWindows(void)

- ea: `0x180025e68`
- end: `0x180025f5e`
- name: `??1PerformanceTracerImplWindows@Pal@@UEAA@XZ`
- size: `246`
- prototype: `void __fastcall(Pal::PerformanceTracerImplWindows *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026e20`

## callees

- `0x180014c64`
- `0x180022f68`
- `0x1800257cc`
- `0x1800257ec`
- `0x180025e68`
- `0x18002a978`
- `0x18002b9f8`
- `0x18002ba34`
- `0x18002dc7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f39`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025f39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025eac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025eac`

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
    Pal::ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>::~ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>(&v8);
  }
  Pal::ScopedLockableValue_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______::_ScopedLockableValue_std::unordered_map__GUID__anonymous_namespace_::EventHandle_A0x8d5497d8::GUIDHasher_std::equal_to__GUID__std::allocator_std::pair__GUID_const___anonymous_namespace_::EventHandle_______(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &Pal::PerformanceTracerImpl::`vftable';
}

```

## disassembly

```asm
0x180025e68  mov     [rsp-18h+arg_8], rbx
0x180025e6d  mov     [rsp-18h+arg_10], rsi
0x180025e72  push    rbp
0x180025e73  push    rdi
0x180025e74  push    r14
0x180025e76  mov     rbp, rsp
0x180025e79  sub     rsp, 50h
0x180025e7d  lea     rax, ??_7PerformanceTracerImplWindows@Pal@@6B@; const Pal::PerformanceTracerImplWindows::`vftable'
0x180025e84  mov     rdi, rcx
0x180025e87  lea     rdx, [rbp+var_18]
0x180025e8b  mov     [rcx], rax
0x180025e8e  call    Pal__Lockable_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle_________getScopedLock
0x180025e93  lea     rsi, [rdi+18h]
0x180025e97  mov     rcx, rsi; lpCriticalSection
0x180025e9a  call    cs:__imp_EnterCriticalSection
0x180025ea0  movups  xmm0, xmmword ptr [rsi+28h]
0x180025ea4  mov     rcx, rsi; lpCriticalSection
0x180025ea7  movdqu  [rbp+var_28], xmm0
0x180025eac  call    cs:__imp_LeaveCriticalSection
0x180025eb2  mov     rbx, [rbp+var_18]
0x180025eb6  lea     r8, [rbp+var_28]
0x180025eba  mov     rcx, rbx
0x180025ebd  lea     rdx, [rbp+var_30]
0x180025ec1  call    std___Hash_std___Umap_traits__GUID__anonymous_namespace___EventHandle_std___Uhash_compare__GUID__anonymous_namespace___GUIDHasher_std__equal_to__GUID____std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle____0_____find
0x180025ec6  mov     r8, [rbp+var_30]
0x180025eca  cmp     r8, [rbx+8]
0x180025ece  jz      short loc_180025F2D
0x180025ed0  lea     r14, [r8+20h]
0x180025ed4  lea     rcx, [r14+18h]
0x180025ed8  lea     rdx, [rbp+var_28]
0x180025edc  call    ?getScopedLock@?$Lockable@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@Pal@@QEAA?AV?$ScopedLockableValue@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@@2@XZ; Pal::Lockable<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>>::getScopedLock(void)
0x180025ee1  mov     rbx, qword ptr [rbp+var_28]
0x180025ee5  lea     r8, [rbp+var_30]
0x180025ee9  mov     [rbp+var_30], rdi
0x180025eed  mov     rdx, [rbx+8]
0x180025ef1  mov     rcx, [rbx]
0x180025ef4  call    ??$_Find_unchecked@PEAPEAVPerformanceTracerImplWindows@Pal@@PEBV12@@std@@YAPEAPEAVPerformanceTracerImplWindows@Pal@@PEAPEAV12@QEAPEAV12@AEBQEBV12@@Z; std::_Find_unchecked<Pal::PerformanceTracerImplWindows * *,Pal::PerformanceTracerImplWindows const *>(Pal::PerformanceTracerImplWindows * *,Pal::PerformanceTracerImplWindows * * const,Pal::PerformanceTracerImplWindows const * const &)
0x180025ef9  mov     rdx, [rbx+8]
0x180025efd  cmp     rax, rdx
0x180025f00  jz      short loc_180025F13
0x180025f02  lea     rcx, [rax+8]; Src
0x180025f06  mov     r8, rax
0x180025f09  call    ??$_Copy_memmove@PEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@@std@@YAPEAV?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@PEAV12@00@Z; std::_Copy_memmove<Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *>(Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *,Pal::EventHandlerAndId<Core::EventHandler<>> *)
0x180025f0e  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFF8h
0x180025f13  mov     rax, [rbx+8]
0x180025f17  cmp     [rbx], rax
0x180025f1a  jnz     short loc_180025F24
0x180025f1c  mov     rcx, r14
0x180025f1f  call    _anonymous_namespace___EventHandle__unregisterEventNotifications
0x180025f24  lea     rcx, [rbp+var_28]
0x180025f28  call    ??1?$ScopedLockableValue@V?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@AEBVExceptionEventArgs@Pal@@@Core@@@Pal@@$01@Core@@@Pal@@QEAA@XZ; Pal::ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>::~ScopedLockableValue<Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<Pal::ExceptionEventArgs const &>>,2>>(void)
0x180025f2d  lea     rcx, [rbp+var_18]
0x180025f31  call    Pal__ScopedLockableValue_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle__________ScopedLockableValue_std__unordered_map__GUID__anonymous_namespace___EventHandle_A0x8d5497d8__GUIDHasher_std__equal_to__GUID__std__allocator_std__pair__GUID_const___anonymous_namespace___EventHandle_______
0x180025f36  mov     rcx, rsi; lpCriticalSection
0x180025f39  call    cs:__imp_DeleteCriticalSection
0x180025f3f  lea     r11, [rsp+50h+var_s0]
0x180025f44  mov     rbx, [r11+28h]
0x180025f48  lea     rax, ??_7PerformanceTracerImpl@Pal@@6B@; const Pal::PerformanceTracerImpl::`vftable'
0x180025f4f  mov     rsi, [r11+30h]
0x180025f53  mov     [rdi], rax
0x180025f56  mov     rsp, r11
0x180025f59  pop     r14
0x180025f5b  pop     rdi
0x180025f5c  pop     rbp
0x180025f5d  retn
```
