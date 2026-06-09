# ??$call@AEAV_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@@?$factory_cache_entry@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@@Z

- ea: `0x18001d6d8`
- end: `0x18001d7e8`
- name: `??$call@AEAV_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@@?$factory_cache_entry@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(void (__fastcall ***)(_QWORD, __int64 *, __int64 **), __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020454`

## callees

- `0x180004ba1`
- `0x18001d6d8`
- `0x18001dd48`
- `0x18001f840`
- `0x18001f90c`
- `0x18001fce0`
- `0x180022a18`
- `0x180031010`

## string_xrefs

- `0x18001d6f2`: `Windows.Storage.Streams.RandomAccessStreamReference`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>::call<_lambda_ed0b7a32649d79a086cc6cb7ea869b18_ &>(
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
  v7[0] = L"Windows.Storage.Streams.RandomAccessStreamReference";
  v7[1] = 51;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180042BF8;
    _InterlockedIncrement64(&qword_180042BF8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180042C00);
    }
    _lambda_ed0b7a32649d79a086cc6cb7ea869b18_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>);
    _InterlockedDecrement64(&qword_180042BF8);
  }
  else
  {
    _lambda_ed0b7a32649d79a086cc6cb7ea869b18_::operator()(a3, a2, &v9);
  }
  winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel((winrt::Windows::AI::MachineLearning::ILearningModel *)&v9);
  return a2;
}

```

## disassembly

```asm
0x18001d6d8  mov     [rsp-18h+arg_8], rbx
0x18001d6dd  mov     [rsp-18h+arg_0], rcx
0x18001d6e2  push    rbp
0x18001d6e3  push    rsi
0x18001d6e4  push    rdi
0x18001d6e5  mov     rbp, rsp
0x18001d6e8  sub     rsp, 60h
0x18001d6ec  mov     rsi, r8
0x18001d6ef  mov     rbx, rdx
0x18001d6f2  lea     rax, aWindowsStorage_1; "Windows.Storage.Streams.RandomAccessStr"...
0x18001d6f9  mov     [rbp+var_38], rax
0x18001d6fd  mov     [rbp+var_30], 33h ; '3'
0x18001d705  lea     rdx, [rbp+var_38]
0x18001d709  lea     rcx, [rbp+var_28]
0x18001d70d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001d712  lea     rdx, [rbp+var_28]
0x18001d716  lea     rcx, [rbp+arg_0]
0x18001d71a  call    ??$get_activation_factory@UIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@winrt@@@winrt@@YA?AUIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>(winrt::param::hstring const &)
0x18001d71f  nop
0x18001d720  mov     rdi, [rbp+arg_0]
0x18001d724  test    rdi, rdi
0x18001d727  jz      loc_18001D7BC
0x18001d72d  mov     [rbp+arg_18], 0
0x18001d735  mov     rax, [rdi]
0x18001d738  lea     r8, [rbp+arg_18]
0x18001d73c  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001d743  mov     rcx, rdi
0x18001d746  mov     rax, [rax]
0x18001d749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d74e  mov     rax, [rbp+arg_18]
0x18001d752  mov     [rbp+arg_18], rax
0x18001d756  test    rax, rax
0x18001d759  jz      short loc_18001D7BC
0x18001d75b  lea     rcx, [rbp+arg_18]
0x18001d75f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001d764  lea     rax, qword_180042BF8
0x18001d76b  mov     [rbp+arg_18], rax
0x18001d76f  lock inc cs:qword_180042BF8
0x18001d777  xor     eax, eax
0x18001d779  lock cmpxchg cs:??$factory_cache_entry_v@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@impl@winrt@@3U?$factory_cache_entry@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>
0x18001d782  jnz     short loc_18001D79F
0x18001d784  mov     [rbp+arg_0], 0
0x18001d78c  lea     rdx, stru_180042C00; ListEntry
0x18001d793  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001d79a  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001d79f  lea     r8, ??$factory_cache_entry_v@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@impl@winrt@@3U?$factory_cache_entry@URandomAccessStreamReference@Streams@Storage@Windows@winrt@@UIRandomAccessStreamReferenceStatics@2345@@12@A; factory_cache_entry<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>::winrt::factory_cache_entry<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Storage::Streams::RandomAccessStreamReference,winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics>
0x18001d7a6  mov     rdx, rbx
0x18001d7a9  mov     rcx, rsi
0x18001d7ac  call    ??R_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@QEBA@AEBUIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@winrt@@@Z; _lambda_ed0b7a32649d79a086cc6cb7ea869b18_::operator()(winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics const &)
0x18001d7b1  nop
0x18001d7b2  lock dec cs:qword_180042BF8
0x18001d7ba  jmp     short loc_18001D7CC
0x18001d7bc  lea     r8, [rbp+arg_0]
0x18001d7c0  mov     rdx, rbx
0x18001d7c3  mov     rcx, rsi
0x18001d7c6  call    ??R_lambda_ed0b7a32649d79a086cc6cb7ea869b18_@@QEBA@AEBUIRandomAccessStreamReferenceStatics@Streams@Storage@Windows@winrt@@@Z; _lambda_ed0b7a32649d79a086cc6cb7ea869b18_::operator()(winrt::Windows::Storage::Streams::IRandomAccessStreamReferenceStatics const &)
0x18001d7cb  nop
0x18001d7cc  lea     rcx, [rbp+arg_0]; this
0x18001d7d0  call    ??1ILearningModel@MachineLearning@AI@Windows@winrt@@QEAA@XZ; winrt::Windows::AI::MachineLearning::ILearningModel::~ILearningModel(void)
0x18001d7d5  mov     rax, rbx
0x18001d7d8  mov     rbx, [rsp+60h+arg_8]
0x18001d7e0  add     rsp, 60h
0x18001d7e4  pop     rdi
0x18001d7e5  pop     rsi
0x18001d7e6  pop     rbp
0x18001d7e7  retn
```
