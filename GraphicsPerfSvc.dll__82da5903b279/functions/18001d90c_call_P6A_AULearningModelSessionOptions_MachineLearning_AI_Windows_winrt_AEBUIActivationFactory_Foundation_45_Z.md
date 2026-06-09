# ??$call@P6A?AULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AULearningModelSessionOptions@MachineLearning@AI@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18001d90c`
- end: `0x18001da22`
- name: `??$call@P6A?AULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AULearningModelSessionOptions@MachineLearning@AI@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `278`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ecf0`

## callees

- `0x180004ba1`
- `0x18001d90c`
- `0x18001db08`
- `0x18001f840`
- `0x18001f90c`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  _QWORD v6[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v7[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+70h] [rbp+10h] BYREF
  __int64 *v9; // [rsp+88h] [rbp+28h] BYREF

  v8 = a1;
  v6[0] = L"Windows.AI.MachineLearning.LearningModelSessionOptions";
  v6[1] = 54;
  winrt::param::hstring::hstring(v7, v6);
  winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(&v8, v7);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_180042B78;
    _InterlockedIncrement64(&qword_180042B78);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042B80);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180042B78);
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
0x18001d90c  mov     [rsp-8+arg_8], rbx
0x18001d911  mov     [rsp-8+arg_10], rdi
0x18001d916  mov     [rsp-8+arg_0], rcx
0x18001d91b  push    rbp
0x18001d91c  mov     rbp, rsp
0x18001d91f  sub     rsp, 60h
0x18001d923  mov     rdi, r8
0x18001d926  mov     rbx, rdx
0x18001d929  lea     rax, aWindowsAiMachi_4; "Windows.AI.MachineLearning.LearningMode"...
0x18001d930  mov     [rbp+var_38], rax
0x18001d934  mov     [rbp+var_30], 36h ; '6'
0x18001d93c  lea     rdx, [rbp+var_38]
0x18001d940  lea     rcx, [rbp+var_28]
0x18001d944  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d949  lea     rdx, [rbp+var_28]
0x18001d94d  lea     rcx, [rbp+arg_0]
0x18001d951  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x18001d956  nop
0x18001d957  mov     rcx, [rbp+arg_0]
0x18001d95b  test    rcx, rcx
0x18001d95e  jz      loc_18001D9F4
0x18001d964  mov     [rbp+arg_18], 0
0x18001d96c  mov     rax, [rcx]
0x18001d96f  lea     r8, [rbp+arg_18]
0x18001d973  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d97a  mov     rax, [rax]
0x18001d97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d982  mov     rax, [rbp+arg_18]
0x18001d986  mov     [rbp+arg_18], rax
0x18001d98a  test    rax, rax
0x18001d98d  jz      short loc_18001D9F4
0x18001d98f  lea     rcx, [rbp+arg_18]
0x18001d993  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d998  lea     rax, qword_180042B78
0x18001d99f  mov     [rbp+arg_18], rax
0x18001d9a3  lock inc cs:qword_180042B78
0x18001d9ab  mov     rcx, [rbp+arg_0]
0x18001d9af  xor     eax, eax
0x18001d9b1  lock cmpxchg cs:??$factory_cache_entry_v@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>
0x18001d9ba  jnz     short loc_18001D9D7
0x18001d9bc  mov     [rbp+arg_0], 0
0x18001d9c4  lea     rdx, stru_180042B80; ListEntry
0x18001d9cb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d9d2  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d9d7  lea     rdx, ??$factory_cache_entry_v@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@ULearningModelSessionOptions@MachineLearning@AI@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSessionOptions,winrt::Windows::Foundation::IActivationFactory>
0x18001d9de  mov     rcx, rbx
0x18001d9e1  mov     rax, [rdi]
0x18001d9e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9e9  nop
0x18001d9ea  lock dec cs:qword_180042B78
0x18001d9f2  jmp     short loc_18001DA04
0x18001d9f4  lea     rdx, [rbp+arg_0]
0x18001d9f8  mov     rcx, rbx
0x18001d9fb  mov     rax, [rdi]
0x18001d9fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da03  nop
0x18001da04  lea     rcx, [rbp+arg_0]; this
0x18001da08  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001da0d  mov     rax, rbx
0x18001da10  lea     r11, [rsp+60h+var_s0]
0x18001da15  mov     rbx, [r11+18h]
0x18001da19  mov     rdi, [r11+20h]
0x18001da1d  mov     rsp, r11
0x18001da20  pop     rbp
0x18001da21  retn
```
