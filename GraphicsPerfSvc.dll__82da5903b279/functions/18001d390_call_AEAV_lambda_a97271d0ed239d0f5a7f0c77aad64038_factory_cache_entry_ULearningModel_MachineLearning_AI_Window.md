# ??$call@AEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@Z

- ea: `0x18001d390`
- end: `0x18001d4a0`
- name: `??$call@AEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020d5c`

## callees

- `0x180004ba1`
- `0x18001d390`
- `0x18001dce8`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fc18`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::call<_lambda_a97271d0ed239d0f5a7f0c77aad64038_ &>(
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
  v7[0] = L"Windows.AI.MachineLearning.LearningModel";
  v7[1] = 40;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042AF8;
    _InterlockedIncrement64(&qword_180042AF8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042B00);
    }
    _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>);
    _InterlockedDecrement64(&qword_180042AF8);
  }
  else
  {
    _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d390  mov     [rsp-18h+arg_8], rbx
0x18001d395  mov     [rsp-18h+arg_0], rcx
0x18001d39a  push    rbp
0x18001d39b  push    rsi
0x18001d39c  push    rdi
0x18001d39d  mov     rbp, rsp
0x18001d3a0  sub     rsp, 60h
0x18001d3a4  mov     rsi, r8
0x18001d3a7  mov     rbx, rdx
0x18001d3aa  lea     rax, aWindowsAiMachi_3; "Windows.AI.MachineLearning.LearningMode"...
0x18001d3b1  mov     [rbp+var_38], rax
0x18001d3b5  mov     [rbp+var_30], 28h ; '('
0x18001d3bd  lea     rdx, [rbp+var_38]
0x18001d3c1  lea     rcx, [rbp+var_28]
0x18001d3c5  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d3ca  lea     rdx, [rbp+var_28]
0x18001d3ce  lea     rcx, [rbp+arg_0]
0x18001d3d2  call    ??$get_activation_factory@UILearningModelStatics@MachineLearning@AI@Windows@winrt@@@winrt@@YA?AUILearningModelStatics@MachineLearning@AI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelStatics>(winrt::param::hstring const &)
0x18001d3d7  nop
0x18001d3d8  mov     rdi, [rbp+arg_0]
0x18001d3dc  test    rdi, rdi
0x18001d3df  jz      loc_18001D474
0x18001d3e5  mov     [rbp+arg_18], 0
0x18001d3ed  mov     rax, [rdi]
0x18001d3f0  lea     r8, [rbp+arg_18]
0x18001d3f4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d3fb  mov     rcx, rdi
0x18001d3fe  mov     rax, [rax]
0x18001d401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d406  mov     rax, [rbp+arg_18]
0x18001d40a  mov     [rbp+arg_18], rax
0x18001d40e  test    rax, rax
0x18001d411  jz      short loc_18001D474
0x18001d413  lea     rcx, [rbp+arg_18]
0x18001d417  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d41c  lea     rax, qword_180042AF8
0x18001d423  mov     [rbp+arg_18], rax
0x18001d427  lock inc cs:qword_180042AF8
0x18001d42f  xor     eax, eax
0x18001d431  lock cmpxchg cs:??$factory_cache_entry_v@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>
0x18001d43a  jnz     short loc_18001D457
0x18001d43c  mov     [rbp+arg_0], 0
0x18001d444  lea     rdx, stru_180042B00; ListEntry
0x18001d44b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d452  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d457  lea     r8, ??$factory_cache_entry_v@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModel@MachineLearning@AI@Windows@winrt@@UILearningModelStatics@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModel,winrt::Windows::AI::MachineLearning::ILearningModelStatics>
0x18001d45e  mov     rdx, rbx
0x18001d461  mov     rcx, rsi
0x18001d464  call    ??R_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@QEBA@AEBUILearningModelStatics@MachineLearning@AI@Windows@winrt@@@Z; _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelStatics const &)
0x18001d469  nop
0x18001d46a  lock dec cs:qword_180042AF8
0x18001d472  jmp     short loc_18001D484
0x18001d474  lea     r8, [rbp+arg_0]
0x18001d478  mov     rdx, rbx
0x18001d47b  mov     rcx, rsi
0x18001d47e  call    ??R_lambda_a97271d0ed239d0f5a7f0c77aad64038_@@QEBA@AEBUILearningModelStatics@MachineLearning@AI@Windows@winrt@@@Z; _lambda_a97271d0ed239d0f5a7f0c77aad64038_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelStatics const &)
0x18001d483  nop
0x18001d484  lea     rcx, [rbp+arg_0]; this
0x18001d488  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d48d  mov     rax, rbx
0x18001d490  mov     rbx, [rsp+60h+arg_8]
0x18001d498  add     rsp, 60h
0x18001d49c  pop     rdi
0x18001d49d  pop     rsi
0x18001d49e  pop     rbp
0x18001d49f  retn
```
