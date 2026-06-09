# ??$call@P6A?AUInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUInMemoryRandomAccessStream@Streams@Storage@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001d7f0`
- end: `0x18001d906`
- name: `??$call@P6A?AUInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUInMemoryRandomAccessStream@Streams@Storage@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `278`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ec04`

## callees

- `0x180004ba1`
- `0x18001d7f0`
- `0x18001db08`
- `0x18001f840`
- `0x18001f90c`
- `0x180022a18`
- `0x180031010`

## string_xrefs

- `0x18001d80d`: `Windows.Storage.Streams.InMemoryRandomAccessStream`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.Storage.Streams.InMemoryRandomAccessStream";
  v6[1] = 50;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_180042BD8;
    _InterlockedIncrement64(&qword_180042BD8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042BE0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180042BD8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v8);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v8);
  return a2;
}

```

## disassembly

```asm
0x18001d7f0  mov     [rsp-8+arg_8], rbx
0x18001d7f5  mov     [rsp-8+arg_10], rdi
0x18001d7fa  mov     [rsp-8+arg_0], rcx
0x18001d7ff  push    rbp
0x18001d800  mov     rbp, rsp
0x18001d803  sub     rsp, 60h
0x18001d807  mov     rdi, r8
0x18001d80a  mov     rbx, rdx
0x18001d80d  lea     rax, aWindowsStorage_0; "Windows.Storage.Streams.InMemoryRandomA"...
0x18001d814  mov     [rbp+var_38], rax
0x18001d818  mov     [rbp+var_30], 32h ; '2'
0x18001d820  lea     rdx, [rbp+var_38]
0x18001d824  lea     rcx, [rbp+var_28]
0x18001d828  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d82d  lea     rdx, [rbp+var_28]
0x18001d831  lea     rcx, [rbp+arg_0]
0x18001d835  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18001d83a  nop
0x18001d83b  mov     rcx, [rbp+arg_0]
0x18001d83f  test    rcx, rcx
0x18001d842  jz      loc_18001D8D8
0x18001d848  mov     [rbp+arg_18], 0
0x18001d850  mov     rax, [rcx]
0x18001d853  lea     r8, [rbp+arg_18]
0x18001d857  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d85e  mov     rax, [rax]
0x18001d861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d866  mov     rax, [rbp+arg_18]
0x18001d86a  mov     [rbp+arg_18], rax
0x18001d86e  test    rax, rax
0x18001d871  jz      short loc_18001D8D8
0x18001d873  lea     rcx, [rbp+arg_18]
0x18001d877  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d87c  lea     rax, qword_180042BD8
0x18001d883  mov     [rbp+arg_18], rax
0x18001d887  lock inc cs:qword_180042BD8
0x18001d88f  mov     rcx, [rbp+arg_0]
0x18001d893  xor     eax, eax
0x18001d895  lock cmpxchg cs:??$factory_cache_entry_v@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>
0x18001d89e  jnz     short loc_18001D8BB
0x18001d8a0  mov     [rbp+arg_0], 0
0x18001d8a8  lea     rdx, stru_180042BE0; ListEntry
0x18001d8af  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d8b6  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d8bb  lea     rdx, ??$factory_cache_entry_v@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UInMemoryRandomAccessStream@Streams@Storage@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::InMemoryRandomAccessStream,winrt::Windows::Foundation::IActivationFactory>
0x18001d8c2  mov     rcx, rbx
0x18001d8c5  mov     rax, [rdi]
0x18001d8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8cd  nop
0x18001d8ce  lock dec cs:qword_180042BD8
0x18001d8d6  jmp     short loc_18001D8E8
0x18001d8d8  lea     rdx, [rbp+arg_0]
0x18001d8dc  mov     rcx, rbx
0x18001d8df  mov     rax, [rdi]
0x18001d8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e7  nop
0x18001d8e8  lea     rcx, [rbp+arg_0]; this
0x18001d8ec  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d8f1  mov     rax, rbx
0x18001d8f4  lea     r11, [rsp+60h+var_s0]
0x18001d8f9  mov     rbx, [r11+18h]
0x18001d8fd  mov     rdi, [r11+20h]
0x18001d901  mov     rsp, r11
0x18001d904  pop     rbp
0x18001d905  retn
```
