# ??$call@AEAV_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@@?$factory_cache_entry@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@@Z

- ea: `0x18001d048`
- end: `0x18001d158`
- name: `??$call@AEAV_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@@?$factory_cache_entry@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001eb90`

## callees

- `0x180004ba1`
- `0x18001d048`
- `0x18001db68`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fbbc`
- `0x180022a18`
- `0x180031010`

## string_xrefs

- `0x18001d062`: `Windows.Storage.Streams.DataWriter`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>::call<_lambda_07ca5c86cbc46a427a1a75ae15bd8481_ &>(
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
  v7[0] = L"Windows.Storage.Streams.DataWriter";
  v7[1] = 34;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Storage::Streams::IDataWriterFactory>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042BB8;
    _InterlockedIncrement64(&qword_180042BB8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    }
    _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>);
    _InterlockedDecrement64(&qword_180042BB8);
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
0x18001d048  mov     [rsp-18h+arg_8], rbx
0x18001d04d  mov     [rsp-18h+arg_0], rcx
0x18001d052  push    rbp
0x18001d053  push    rsi
0x18001d054  push    rdi
0x18001d055  mov     rbp, rsp
0x18001d058  sub     rsp, 60h
0x18001d05c  mov     rsi, r8
0x18001d05f  mov     rbx, rdx
0x18001d062  lea     rax, aWindowsStorage; "Windows.Storage.Streams.DataWriter"
0x18001d069  mov     [rbp+var_38], rax
0x18001d06d  mov     [rbp+var_30], 22h ; '"'
0x18001d075  lea     rdx, [rbp+var_38]
0x18001d079  lea     rcx, [rbp+var_28]
0x18001d07d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d082  lea     rdx, [rbp+var_28]
0x18001d086  lea     rcx, [rbp+arg_0]
0x18001d08a  call    ??$get_activation_factory@UIDataWriterFactory@Streams@Storage@Windows@winrt@@@winrt@@YA?AUIDataWriterFactory@Streams@Storage@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Storage::Streams::IDataWriterFactory>(winrt::param::hstring const &)
0x18001d08f  nop
0x18001d090  mov     rdi, [rbp+arg_0]
0x18001d094  test    rdi, rdi
0x18001d097  jz      loc_18001D12C
0x18001d09d  mov     [rbp+arg_18], 0
0x18001d0a5  mov     rax, [rdi]
0x18001d0a8  lea     r8, [rbp+arg_18]
0x18001d0ac  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d0b3  mov     rcx, rdi
0x18001d0b6  mov     rax, [rax]
0x18001d0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0be  mov     rax, [rbp+arg_18]
0x18001d0c2  mov     [rbp+arg_18], rax
0x18001d0c6  test    rax, rax
0x18001d0c9  jz      short loc_18001D12C
0x18001d0cb  lea     rcx, [rbp+arg_18]
0x18001d0cf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d0d4  lea     rax, qword_180042BB8
0x18001d0db  mov     [rbp+arg_18], rax
0x18001d0df  lock inc cs:qword_180042BB8
0x18001d0e7  xor     eax, eax
0x18001d0e9  lock cmpxchg cs:??$factory_cache_entry_v@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>
0x18001d0f2  jnz     short loc_18001D10F
0x18001d0f4  mov     [rbp+arg_0], 0
0x18001d0fc  lea     rdx, ListEntry; ListEntry
0x18001d103  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d10a  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d10f  lea     r8, ??$factory_cache_entry_v@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UDataWriter@Streams@Storage@Windows@winrt@@UIDataWriterFactory@2345@@12@A; factory_cache_entry<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::DataWriter,winrt::Windows::Storage::Streams::IDataWriterFactory>
0x18001d116  mov     rdx, rbx
0x18001d119  mov     rcx, rsi
0x18001d11c  call    ??R_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@QEBA@AEBUIDataWriterFactory@Streams@Storage@Windows@winrt@@@Z; _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(winrt::Windows::Storage::Streams::IDataWriterFactory const &)
0x18001d121  nop
0x18001d122  lock dec cs:qword_180042BB8
0x18001d12a  jmp     short loc_18001D13C
0x18001d12c  lea     r8, [rbp+arg_0]
0x18001d130  mov     rdx, rbx
0x18001d133  mov     rcx, rsi
0x18001d136  call    ??R_lambda_07ca5c86cbc46a427a1a75ae15bd8481_@@QEBA@AEBUIDataWriterFactory@Streams@Storage@Windows@winrt@@@Z; _lambda_07ca5c86cbc46a427a1a75ae15bd8481_::operator()(winrt::Windows::Storage::Streams::IDataWriterFactory const &)
0x18001d13b  nop
0x18001d13c  lea     rcx, [rbp+arg_0]; this
0x18001d140  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d145  mov     rax, rbx
0x18001d148  mov     rbx, [rsp+60h+arg_8]
0x18001d150  add     rsp, 60h
0x18001d154  pop     rdi
0x18001d155  pop     rsi
0x18001d156  pop     rbp
0x18001d157  retn
```
