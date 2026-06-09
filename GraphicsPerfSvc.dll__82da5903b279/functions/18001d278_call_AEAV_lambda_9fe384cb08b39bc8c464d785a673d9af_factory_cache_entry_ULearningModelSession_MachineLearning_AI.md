# ??$call@AEAV_lambda_9fe384cb08b39bc8c464d785a673d9af_@@@?$factory_cache_entry@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9fe384cb08b39bc8c464d785a673d9af_@@@Z

- ea: `0x18001d278`
- end: `0x18001d388`
- name: `??$call@AEAV_lambda_9fe384cb08b39bc8c464d785a673d9af_@@@?$factory_cache_entry@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9fe384cb08b39bc8c464d785a673d9af_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001cc70`

## callees

- `0x180004ba1`
- `0x18001d278`
- `0x18001dc88`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fbe4`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>::call<_lambda_9fe384cb08b39bc8c464d785a673d9af_ &>(
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
  v7[0] = L"Windows.AI.MachineLearning.LearningModelSession";
  v7[1] = 47;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042B58;
    _InterlockedIncrement64(&qword_180042B58);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042B60);
    }
    _lambda_9fe384cb08b39bc8c464d785a673d9af_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>);
    _InterlockedDecrement64(&qword_180042B58);
  }
  else
  {
    _lambda_9fe384cb08b39bc8c464d785a673d9af_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d278  mov     [rsp-18h+arg_8], rbx
0x18001d27d  mov     [rsp-18h+arg_0], rcx
0x18001d282  push    rbp
0x18001d283  push    rsi
0x18001d284  push    rdi
0x18001d285  mov     rbp, rsp
0x18001d288  sub     rsp, 60h
0x18001d28c  mov     rsi, r8
0x18001d28f  mov     rbx, rdx
0x18001d292  lea     rax, aWindowsAiMachi_2; "Windows.AI.MachineLearning.LearningMode"...
0x18001d299  mov     [rbp+var_38], rax
0x18001d29d  mov     [rbp+var_30], 2Fh ; '/'
0x18001d2a5  lea     rdx, [rbp+var_38]
0x18001d2a9  lea     rcx, [rbp+var_28]
0x18001d2ad  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d2b2  lea     rdx, [rbp+var_28]
0x18001d2b6  lea     rcx, [rbp+arg_0]
0x18001d2ba  call    ??$get_activation_factory@UILearningModelSessionFactory2@MachineLearning@AI@Windows@winrt@@@winrt@@YA?AUILearningModelSessionFactory2@MachineLearning@AI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>(winrt::param::hstring const &)
0x18001d2bf  nop
0x18001d2c0  mov     rdi, [rbp+arg_0]
0x18001d2c4  test    rdi, rdi
0x18001d2c7  jz      loc_18001D35C
0x18001d2cd  mov     [rbp+arg_18], 0
0x18001d2d5  mov     rax, [rdi]
0x18001d2d8  lea     r8, [rbp+arg_18]
0x18001d2dc  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d2e3  mov     rcx, rdi
0x18001d2e6  mov     rax, [rax]
0x18001d2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ee  mov     rax, [rbp+arg_18]
0x18001d2f2  mov     [rbp+arg_18], rax
0x18001d2f6  test    rax, rax
0x18001d2f9  jz      short loc_18001D35C
0x18001d2fb  lea     rcx, [rbp+arg_18]
0x18001d2ff  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d304  lea     rax, qword_180042B58
0x18001d30b  mov     [rbp+arg_18], rax
0x18001d30f  lock inc cs:qword_180042B58
0x18001d317  xor     eax, eax
0x18001d319  lock cmpxchg cs:??$factory_cache_entry_v@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>
0x18001d322  jnz     short loc_18001D33F
0x18001d324  mov     [rbp+arg_0], 0
0x18001d32c  lea     rdx, stru_180042B60; ListEntry
0x18001d333  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d33a  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d33f  lea     r8, ??$factory_cache_entry_v@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelSession@MachineLearning@AI@Windows@winrt@@UILearningModelSessionFactory2@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelSession,winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2>
0x18001d346  mov     rdx, rbx
0x18001d349  mov     rcx, rsi
0x18001d34c  call    ??R_lambda_9fe384cb08b39bc8c464d785a673d9af_@@QEBA@AEBUILearningModelSessionFactory2@MachineLearning@AI@Windows@winrt@@@Z; _lambda_9fe384cb08b39bc8c464d785a673d9af_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2 const &)
0x18001d351  nop
0x18001d352  lock dec cs:qword_180042B58
0x18001d35a  jmp     short loc_18001D36C
0x18001d35c  lea     r8, [rbp+arg_0]
0x18001d360  mov     rdx, rbx
0x18001d363  mov     rcx, rsi
0x18001d366  call    ??R_lambda_9fe384cb08b39bc8c464d785a673d9af_@@QEBA@AEBUILearningModelSessionFactory2@MachineLearning@AI@Windows@winrt@@@Z; _lambda_9fe384cb08b39bc8c464d785a673d9af_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelSessionFactory2 const &)
0x18001d36b  nop
0x18001d36c  lea     rcx, [rbp+arg_0]; this
0x18001d370  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d375  mov     rax, rbx
0x18001d378  mov     rbx, [rsp+60h+arg_8]
0x18001d380  add     rsp, 60h
0x18001d384  pop     rdi
0x18001d385  pop     rsi
0x18001d386  pop     rbp
0x18001d387  retn
```
