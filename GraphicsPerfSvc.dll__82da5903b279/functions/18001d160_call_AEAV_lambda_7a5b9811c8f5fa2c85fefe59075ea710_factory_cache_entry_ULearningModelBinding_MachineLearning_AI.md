# ??$call@AEAV_lambda_7a5b9811c8f5fa2c85fefe59075ea710_@@@?$factory_cache_entry@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_7a5b9811c8f5fa2c85fefe59075ea710_@@@Z

- ea: `0x18001d160`
- end: `0x18001d270`
- name: `??$call@AEAV_lambda_7a5b9811c8f5fa2c85fefe59075ea710_@@@?$factory_cache_entry@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_7a5b9811c8f5fa2c85fefe59075ea710_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001cc08`

## callees

- `0x180004ba1`
- `0x18001d160`
- `0x18001dbc8`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fbbc`
- `0x180022a18`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>::call<_lambda_7a5b9811c8f5fa2c85fefe59075ea710_ &>(
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
  v7[0] = L"Windows.AI.MachineLearning.LearningModelBinding";
  v7[1] = 47;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042B18;
    _InterlockedIncrement64(&qword_180042B18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042B20);
    }
    _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>);
    _InterlockedDecrement64(&qword_180042B18);
  }
  else
  {
    _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d160  mov     [rsp-18h+arg_8], rbx
0x18001d165  mov     [rsp-18h+arg_0], rcx
0x18001d16a  push    rbp
0x18001d16b  push    rsi
0x18001d16c  push    rdi
0x18001d16d  mov     rbp, rsp
0x18001d170  sub     rsp, 60h
0x18001d174  mov     rsi, r8
0x18001d177  mov     rbx, rdx
0x18001d17a  lea     rax, aWindowsAiMachi; "Windows.AI.MachineLearning.LearningMode"...
0x18001d181  mov     [rbp+var_38], rax
0x18001d185  mov     [rbp+var_30], 2Fh ; '/'
0x18001d18d  lea     rdx, [rbp+var_38]
0x18001d191  lea     rcx, [rbp+var_28]
0x18001d195  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d19a  lea     rdx, [rbp+var_28]
0x18001d19e  lea     rcx, [rbp+arg_0]
0x18001d1a2  call    ??$get_activation_factory@UILearningModelBindingFactory@MachineLearning@AI@Windows@winrt@@@winrt@@YA?AUILearningModelBindingFactory@MachineLearning@AI@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>(winrt::param::hstring const &)
0x18001d1a7  nop
0x18001d1a8  mov     rdi, [rbp+arg_0]
0x18001d1ac  test    rdi, rdi
0x18001d1af  jz      loc_18001D244
0x18001d1b5  mov     [rbp+arg_18], 0
0x18001d1bd  mov     rax, [rdi]
0x18001d1c0  lea     r8, [rbp+arg_18]
0x18001d1c4  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d1cb  mov     rcx, rdi
0x18001d1ce  mov     rax, [rax]
0x18001d1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d6  mov     rax, [rbp+arg_18]
0x18001d1da  mov     [rbp+arg_18], rax
0x18001d1de  test    rax, rax
0x18001d1e1  jz      short loc_18001D244
0x18001d1e3  lea     rcx, [rbp+arg_18]
0x18001d1e7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d1ec  lea     rax, qword_180042B18
0x18001d1f3  mov     [rbp+arg_18], rax
0x18001d1f7  lock inc cs:qword_180042B18
0x18001d1ff  xor     eax, eax
0x18001d201  lock cmpxchg cs:??$factory_cache_entry_v@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>
0x18001d20a  jnz     short loc_18001D227
0x18001d20c  mov     [rbp+arg_0], 0
0x18001d214  lea     rdx, stru_180042B20; ListEntry
0x18001d21b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d222  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d227  lea     r8, ??$factory_cache_entry_v@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@impl@winrt@@3U?$factory_cache_entry@ULearningModelBinding@MachineLearning@AI@Windows@winrt@@UILearningModelBindingFactory@2345@@12@A; factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>::winrt::factory_cache_entry<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::AI::MachineLearning::LearningModelBinding,winrt::Windows::AI::MachineLearning::ILearningModelBindingFactory>
0x18001d22e  mov     rdx, rbx
0x18001d231  mov     rcx, rsi
0x18001d234  call    ??R_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@QEBA@AEBUIDataWriterFactory@Streams@Storage@Windows@winrt@@@Z; _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(winrt::Windows::Storage::Streams::IDataWriterFactory const &)
0x18001d239  nop
0x18001d23a  lock dec cs:qword_180042B18
0x18001d242  jmp     short loc_18001D254
0x18001d244  lea     r8, [rbp+arg_0]
0x18001d248  mov     rdx, rbx
0x18001d24b  mov     rcx, rsi
0x18001d24e  call    ??R_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@QEBA@AEBUIDataWriterFactory@Streams@Storage@Windows@winrt@@@Z; _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(winrt::Windows::Storage::Streams::IDataWriterFactory const &)
0x18001d253  nop
0x18001d254  lea     rcx, [rbp+arg_0]; this
0x18001d258  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d25d  mov     rax, rbx
0x18001d260  mov     rbx, [rsp+60h+arg_8]
0x18001d268  add     rsp, 60h
0x18001d26c  pop     rdi
0x18001d26d  pop     rsi
0x18001d26e  pop     rbp
0x18001d26f  retn
```
