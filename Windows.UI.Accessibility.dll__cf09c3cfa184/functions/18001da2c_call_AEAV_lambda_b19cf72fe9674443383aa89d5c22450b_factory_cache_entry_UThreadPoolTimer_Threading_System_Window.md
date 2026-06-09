# ??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z

- ea: `0x18001da2c`
- end: `0x18001db3c`
- name: `??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180022b40`

## callees

- `0x180005236`
- `0x1800072d8`
- `0x18000dfc0`
- `0x18001da2c`
- `0x18001e6d8`
- `0x180020388`
- `0x180020974`
- `0x180035010`

## string_xrefs

- `0x18001da46`: `Windows.System.Threading.ThreadPoolTimer`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::call<_lambda_b19cf72fe9674443383aa89d5c22450b_ &>(
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
  v7[0] = L"Windows.System.Threading.ThreadPoolTimer";
  v7[1] = 40;
  winrt::param::hstring::hstring(v8, v7);
  winrt::get_activation_factory<winrt::Windows::System::Threading::IThreadPoolTimerStatics>(&v9, v8);
  v5 = (signed __int64)v9;
  if ( v9 && (v10 = 0, (**v9)(v9, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v10), v10) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
    v10 = &qword_180046CB8;
    _InterlockedIncrement64(&qword_180046CB8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>,
            v5,
            0) )
    {
      v9 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180046CC0);
    }
    _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(
      a3,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>);
    _InterlockedDecrement64(&qword_180046CB8);
  }
  else
  {
    _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(a3, a2, &v9);
  }
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
  return a2;
}

```

## disassembly

```asm
0x18001da2c  mov     [rsp-18h+arg_8], rbx
0x18001da31  mov     [rsp-18h+arg_0], rcx
0x18001da36  push    rbp
0x18001da37  push    rsi
0x18001da38  push    rdi
0x18001da39  mov     rbp, rsp
0x18001da3c  sub     rsp, 60h
0x18001da40  mov     rsi, r8
0x18001da43  mov     rbx, rdx
0x18001da46  lea     rax, aWindowsSystemT; "Windows.System.Threading.ThreadPoolTime"...
0x18001da4d  mov     [rbp+var_38], rax
0x18001da51  mov     [rbp+var_30], 28h ; '('
0x18001da59  lea     rdx, [rbp+var_38]
0x18001da5d  lea     rcx, [rbp+var_28]
0x18001da61  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::param::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001da66  lea     rdx, [rbp+var_28]
0x18001da6a  lea     rcx, [rbp+arg_0]
0x18001da6e  call    ??$get_activation_factory@UIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@winrt@@YA?AUIThreadPoolTimerStatics@Threading@System@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::System::Threading::IThreadPoolTimerStatics>(winrt::param::hstring const &)
0x18001da73  nop
0x18001da74  mov     rdi, [rbp+arg_0]
0x18001da78  test    rdi, rdi
0x18001da7b  jz      loc_18001DB10
0x18001da81  mov     [rbp+arg_18], 0
0x18001da89  mov     rax, [rdi]
0x18001da8c  lea     r8, [rbp+arg_18]
0x18001da90  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18001da97  mov     rcx, rdi
0x18001da9a  mov     rax, [rax]
0x18001da9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daa2  mov     rax, [rbp+arg_18]
0x18001daa6  mov     [rbp+arg_18], rax
0x18001daaa  test    rax, rax
0x18001daad  jz      short loc_18001DB10
0x18001daaf  lea     rcx, [rbp+arg_18]
0x18001dab3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001dab8  lea     rax, qword_180046CB8
0x18001dabf  mov     [rbp+arg_18], rax
0x18001dac3  lock inc cs:qword_180046CB8
0x18001dacb  xor     eax, eax
0x18001dacd  lock cmpxchg cs:??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A, rdi; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x18001dad6  jnz     short loc_18001DAF3
0x18001dad8  mov     [rbp+arg_0], 0
0x18001dae0  lea     rdx, stru_180046CC0; ListEntry
0x18001dae7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18001daee  call    WINRT_IMPL_InterlockedPushEntrySList
0x18001daf3  lea     r8, ??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x18001dafa  mov     rdx, rbx
0x18001dafd  mov     rcx, rsi
0x18001db00  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x18001db05  nop
0x18001db06  lock dec cs:qword_180046CB8
0x18001db0e  jmp     short loc_18001DB20
0x18001db10  lea     r8, [rbp+arg_0]
0x18001db14  mov     rdx, rbx
0x18001db17  mov     rcx, rsi
0x18001db1a  call    ??R_lambda_b19cf72fe9674443383aa89d5c22450b_@@QEBA@AEBUIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@Z; _lambda_b19cf72fe9674443383aa89d5c22450b_::operator()(winrt::Windows::System::Threading::IThreadPoolTimerStatics const &)
0x18001db1f  nop
0x18001db20  lea     rcx, [rbp+arg_0]
0x18001db24  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001db29  mov     rax, rbx
0x18001db2c  mov     rbx, [rsp+60h+arg_8]
0x18001db34  add     rsp, 60h
0x18001db38  pop     rdi
0x18001db39  pop     rsi
0x18001db3a  pop     rbp
0x18001db3b  retn
```
