# ??$call@AEAV_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@@?$factory_cache_entry@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@@Z

- ea: `0x18001d4a8`
- end: `0x18001d5b8`
- name: `??$call@AEAV_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@@?$factory_cache_entry@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001ec7c`

## callees

- `0x180004ba1`
- `0x18001d4a8`
- `0x18001dc28`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fc8c`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>::call<_lambda_c6f09f6df91fe981d174a291f9ea28f0_ &>(
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
  v7[0] = L"Windows.AI.MachineLearning.LearningModelDevice";
  v7[1] = 46;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042B38;
    _InterlockedIncrement64(&qword_180042B38);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042B40);
    }
    _lambda_c6f09f6df91fe981d174a291f9ea28f0_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>);
    _InterlockedDecrement64(&qword_180042B38);
  }
  else
  {
    _lambda_c6f09f6df91fe981d174a291f9ea28f0_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d4a8  mov     [rsp-18h+arg_8], rbx
0x18001d4ad  mov     [rsp-18h+arg_0], rcx
0x18001d4b2  push    rbp
0x18001d4b3  push    rsi
0x18001d4b4  push    rdi
0x18001d4b5  mov     rbp, rsp
0x18001d4b8  sub     rsp, 60h
0x18001d4bc  mov     rsi, r8
0x18001d4bf  mov     rbx, rdx
0x18001d4c2  lea     rax, aWindowsAiMachi_0; "Windows.AI.MachineLearning.LearningMode"...
0x18001d4c9  mov     [rbp+var_38], rax
0x18001d4cd  mov     [rbp+var_30], 2Eh ; '.'
0x18001d4d5  lea     rdx, [rbp+var_38]
0x18001d4d9  lea     rcx, [rbp+var_28]
0x18001d4dd  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d4e2  lea     rdx, [rbp+var_28]
0x18001d4e6  lea     rcx, [rbp+arg_0]
0x18001d4ea  call    ??$get_activation_factory@UILearningModelDeviceFactory@MachineLearning@AI@Windows@winrt@@@winrt@@YA?AUILearningModelDeviceFactory@MachineLearning@AI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>(winrt::param::hstring const &)
0x18001d4ef  nop
0x18001d4f0  mov     rdi, [rbp+arg_0]
0x18001d4f4  test    rdi, rdi
0x18001d4f7  jz      loc_18001D58C
0x18001d4fd  mov     [rbp+arg_18], 0
0x18001d505  mov     rax, [rdi]
0x18001d508  lea     r8, [rbp+arg_18]
0x18001d50c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d513  mov     rcx, rdi
0x18001d516  mov     rax, [rax]
0x18001d519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d51e  mov     rax, [rbp+arg_18]
0x18001d522  mov     [rbp+arg_18], rax
0x18001d526  test    rax, rax
0x18001d529  jz      short loc_18001D58C
0x18001d52b  lea     rcx, [rbp+arg_18]
0x18001d52f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d534  lea     rax, qword_180042B38
0x18001d53b  mov     [rbp+arg_18], rax
0x18001d53f  lock inc cs:qword_180042B38
0x18001d547  xor     eax, eax
0x18001d549  lock cmpxchg cs:??$factory_cache_entry_v@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>
0x18001d552  jnz     short loc_18001D56F
0x18001d554  mov     [rbp+arg_0], 0
0x18001d55c  lea     rdx, stru_180042B40; ListEntry
0x18001d563  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d56a  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d56f  lea     r8, ??$factory_cache_entry_v@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelDevice@MachineLearning@AI@Windows@winrt@@UILearningModelDeviceFactory@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelDevice,winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory>
0x18001d576  mov     rdx, rbx
0x18001d579  mov     rcx, rsi
0x18001d57c  call    ??R_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@QEBA@AEBUILearningModelDeviceFactory@MachineLearning@AI@Windows@winrt@@@Z; _lambda_c6f09f6df91fe981d174a291f9ea28f0_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory const &)
0x18001d581  nop
0x18001d582  lock dec cs:qword_180042B38
0x18001d58a  jmp     short loc_18001D59C
0x18001d58c  lea     r8, [rbp+arg_0]
0x18001d590  mov     rdx, rbx
0x18001d593  mov     rcx, rsi
0x18001d596  call    ??R_lambda_c6f09f6df91fe981d174a291f9ea28f0_@@QEBA@AEBUILearningModelDeviceFactory@MachineLearning@AI@Windows@winrt@@@Z; _lambda_c6f09f6df91fe981d174a291f9ea28f0_::operator()(winrt::Windows::AI::MachineLearning::ILearningModelDeviceFactory const &)
0x18001d59b  nop
0x18001d59c  lea     rcx, [rbp+arg_0]; this
0x18001d5a0  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d5a5  mov     rax, rbx
0x18001d5a8  mov     rbx, [rsp+60h+arg_8]
0x18001d5b0  add     rsp, 60h
0x18001d5b4  pop     rdi
0x18001d5b5  pop     rsi
0x18001d5b6  pop     rbp
0x18001d5b7  retn
```
