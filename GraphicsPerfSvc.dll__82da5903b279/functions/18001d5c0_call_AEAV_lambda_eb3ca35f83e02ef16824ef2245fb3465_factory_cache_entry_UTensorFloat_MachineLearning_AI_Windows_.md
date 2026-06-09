# ??$call@AEAV_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@@?$factory_cache_entry@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@@Z

- ea: `0x18001d5c0`
- end: `0x18001d6d0`
- name: `??$call@AEAV_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@@?$factory_cache_entry@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800202fc`

## callees

- `0x180004ba1`
- `0x18001d5c0`
- `0x18001dda8`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fcb4`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>::call<_lambda_eb3ca35f83e02ef16824ef2245fb3465_ &>(
        void (__fastcall ***a1)(_QWORD, __int64 *, __int64 **),
        __int64 a2,
        __int64 a3)
{
  signed __int64 v5; // rdi
  _QWORD v7[2]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall ***v9)(_QWORD, __int64 *, __int64 **); // [rsp+80h] [rbp+20h] BYREF
  __int64 *v10; // [rsp+98h] [rbp+38h] BYREF

  v9 = a1;
  v7[0] = L"Windows.AI.MachineLearning.TensorFloat";
  v7[1] = 38;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ITensorFloatStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042B98;
    _InterlockedIncrement64(&qword_180042B98);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042BA0);
    }
    _lambda_eb3ca35f83e02ef16824ef2245fb3465_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>);
    _InterlockedDecrement64(&qword_180042B98);
  }
  else
  {
    _lambda_eb3ca35f83e02ef16824ef2245fb3465_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d5c0  mov     [rsp-18h+arg_8], rbx
0x18001d5c5  mov     [rsp-18h+arg_0], rcx
0x18001d5ca  push    rbp
0x18001d5cb  push    rsi
0x18001d5cc  push    rdi
0x18001d5cd  mov     rbp, rsp
0x18001d5d0  sub     rsp, 60h
0x18001d5d4  mov     rsi, r8
0x18001d5d7  mov     rbx, rdx
0x18001d5da  lea     rax, aWindowsAiMachi_1; "Windows.AI.MachineLearning.TensorFloat"
0x18001d5e1  mov     [rbp+var_38], rax
0x18001d5e5  mov     [rbp+var_30], 26h ; '&'
0x18001d5ed  lea     rdx, [rbp+var_38]
0x18001d5f1  lea     rcx, [rbp+var_28]
0x18001d5f5  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d5fa  lea     rdx, [rbp+var_28]
0x18001d5fe  lea     rcx, [rbp+arg_0]
0x18001d602  call    ??$get_activation_factory@UITensorFloatStatics@MachineLearning@AI@Windows@winrt@@@winrt@@YA?AUITensorFloatStatics@MachineLearning@AI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ITensorFloatStatics>(winrt::param::hstring const &)
0x18001d607  nop
0x18001d608  mov     rdi, [rbp+arg_0]
0x18001d60c  test    rdi, rdi
0x18001d60f  jz      loc_18001D6A4
0x18001d615  mov     [rbp+arg_18], 0
0x18001d61d  mov     rax, [rdi]
0x18001d620  lea     r8, [rbp+arg_18]
0x18001d624  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d62b  mov     rcx, rdi
0x18001d62e  mov     rax, [rax]
0x18001d631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d636  mov     rax, [rbp+arg_18]
0x18001d63a  mov     [rbp+arg_18], rax
0x18001d63e  test    rax, rax
0x18001d641  jz      short loc_18001D6A4
0x18001d643  lea     rcx, [rbp+arg_18]
0x18001d647  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d64c  lea     rax, qword_180042B98
0x18001d653  mov     [rbp+arg_18], rax
0x18001d657  lock inc cs:qword_180042B98
0x18001d65f  xor     eax, eax
0x18001d661  lock cmpxchg cs:??$factory_cache_entry_v@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>
0x18001d66a  jnz     short loc_18001D687
0x18001d66c  mov     [rbp+arg_0], 0
0x18001d674  lea     rdx, stru_180042BA0; ListEntry
0x18001d67b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d682  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d687  lea     r8, ??$factory_cache_entry_v@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UTensorFloat@MachineLearning@AI@Windows@winrt@@UITensorFloatStatics@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::TensorFloat,winrt::Windows::AI::MachineLearning::ITensorFloatStatics>
0x18001d68e  mov     rdx, rbx
0x18001d691  mov     rcx, rsi
0x18001d694  call    ??R_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@QEBA@AEBUITensorFloatStatics@MachineLearning@AI@Windows@winrt@@@Z; _lambda_eb3ca35f83e02ef16824ef2245fb3465_::operator()(winrt::Windows::AI::MachineLearning::ITensorFloatStatics const &)
0x18001d699  nop
0x18001d69a  lock dec cs:qword_180042B98
0x18001d6a2  jmp     short loc_18001D6B4
0x18001d6a4  lea     r8, [rbp+arg_0]
0x18001d6a8  mov     rdx, rbx
0x18001d6ab  mov     rcx, rsi
0x18001d6ae  call    ??R_lambda_eb3ca35f83e02ef16824ef2245fb3465_@@QEBA@AEBUITensorFloatStatics@MachineLearning@AI@Windows@winrt@@@Z; _lambda_eb3ca35f83e02ef16824ef2245fb3465_::operator()(winrt::Windows::AI::MachineLearning::ITensorFloatStatics const &)
0x18001d6b3  nop
0x18001d6b4  lea     rcx, [rbp+arg_0]; this
0x18001d6b8  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d6bd  mov     rax, rbx
0x18001d6c0  mov     rbx, [rsp+60h+arg_8]
0x18001d6c8  add     rsp, 60h
0x18001d6cc  pop     rdi
0x18001d6cd  pop     rsi
0x18001d6ce  pop     rbp
0x18001d6cf  retn
```
