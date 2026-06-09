# ??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z

- ea: `0x18002b010`
- end: `0x18002b165`
- name: `??$call@P6A?AUJsonObject@Json@Data@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUJsonObject@Json@Data@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, __int64, void (__fastcall **)(__int64, __int64 *))`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b250`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180014870`
- `0x18002b010`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## string_xrefs

- `0x18002b047`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall winrt::impl::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Data::Json::JsonObject (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        __int64 a1,
        __int64 a2,
        void (__fastcall **a3)(__int64, __int64 *))
{
  __int64 *v5; // rcx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  _DWORD *v8; // [rsp+28h] [rbp-38h] BYREF
  _DWORD v9[4]; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-20h]
  __int64 *v11; // [rsp+48h] [rbp-18h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-10h] BYREF

  v9[0] = 1;
  v9[1] = 28;
  v10 = L"Windows.Data.Json.JsonObject";
  v8 = v9;
  v11 = 0;
  winrt::impl::get_runtime_activation_factory_impl<1>(&v7, &v8, "5", &v11);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7);
  }
  v5 = v11;
  v12 = v11;
  if ( v11
    && (v11 = 0,
        (*(void (__fastcall **)(__int64 *, __int64 *, __int64 **))*v5)(
          v5,
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
    v11 = &qword_180059FB8;
    _InterlockedIncrement64(&qword_180059FB8);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>,
            (signed __int64)v12,
            0) )
    {
      v12 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180059FC0);
    }
    (*a3)(
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059FB8);
  }
  else
  {
    (*a3)(a2, (__int64 *)&v12);
  }
  if ( v12 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  return a2;
}

```

## disassembly

```asm
0x18002b010  mov     [rsp-18h+arg_0], rbx
0x18002b015  push    rbp
0x18002b016  push    rsi
0x18002b017  push    rdi
0x18002b018  mov     rbp, rsp
0x18002b01b  sub     rsp, 60h
0x18002b01f  mov     rax, cs:__security_cookie
0x18002b026  xor     rax, rsp
0x18002b029  mov     [rbp+var_8], rax
0x18002b02d  mov     rdi, r8
0x18002b030  mov     rbx, rdx
0x18002b033  mov     [rbp+var_18], rdx
0x18002b037  xor     esi, esi
0x18002b039  mov     [rbp+var_30], 1
0x18002b040  mov     [rbp+var_2C], 1Ch
0x18002b047  lea     rax, aWindowsDataJso; "Windows.Data.Json.JsonObject"
0x18002b04e  mov     [rbp+var_20], rax
0x18002b052  lea     rax, [rbp+var_30]
0x18002b056  mov     [rbp+var_38], rax
0x18002b05a  mov     [rbp+var_18], rsi
0x18002b05e  lea     r9, [rbp+var_18]
0x18002b062  lea     r8, ??$guid_v@UIActivationFactory@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; "5"
0x18002b069  lea     rdx, [rbp+var_38]
0x18002b06d  lea     rcx, [rbp+var_40]
0x18002b071  call    ??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18002b076  mov     ecx, [rbp+var_40]
0x18002b079  test    ecx, ecx
0x18002b07b  js      loc_18002B15C
0x18002b081  mov     rcx, [rbp+var_18]
0x18002b085  mov     [rbp+var_10], rcx
0x18002b089  test    rcx, rcx
0x18002b08c  jz      loc_18002B11C
0x18002b092  mov     [rbp+var_18], rsi
0x18002b096  mov     rax, [rcx]
0x18002b099  lea     r8, [rbp+var_18]
0x18002b09d  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18002b0a4  mov     rax, [rax]
0x18002b0a7  call    cs:__guard_dispatch_icall_fptr
0x18002b0ad  mov     rax, [rbp+var_18]
0x18002b0b1  mov     [rbp+var_18], rax
0x18002b0b5  test    rax, rax
0x18002b0b8  jz      short loc_18002B11C
0x18002b0ba  lea     rcx, [rbp+var_18]
0x18002b0be  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002b0c3  lea     rax, qword_180059FB8
0x18002b0ca  mov     [rbp+var_18], rax
0x18002b0ce  lock inc cs:qword_180059FB8
0x18002b0d6  mov     rcx, [rbp+var_10]
0x18002b0da  xor     eax, eax
0x18002b0dc  lock cmpxchg cs:??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, rcx; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002b0e5  jnz     short loc_18002B0FE
0x18002b0e7  mov     [rbp+var_10], rsi
0x18002b0eb  lea     rdx, stru_180059FC0; ListEntry
0x18002b0f2  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18002b0f9  call    WINRT_IMPL_InterlockedPushEntrySList
0x18002b0fe  lea     rdx, ??$factory_cache_entry_v@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UJsonObject@Json@Data@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Data::Json::JsonObject,winrt::Windows::Foundation::IActivationFactory>
0x18002b105  mov     rcx, rbx
0x18002b108  mov     rax, [rdi]
0x18002b10b  call    cs:__guard_dispatch_icall_fptr
0x18002b111  nop
0x18002b112  lock dec cs:qword_180059FB8
0x18002b11a  jmp     short loc_18002B12D
0x18002b11c  lea     rdx, [rbp+var_10]
0x18002b120  mov     rcx, rbx
0x18002b123  mov     rax, [rdi]
0x18002b126  call    cs:__guard_dispatch_icall_fptr
0x18002b12c  nop
0x18002b12d  cmp     [rbp+var_10], 0
0x18002b132  jz      short loc_18002B13D
0x18002b134  lea     rcx, [rbp+var_10]
0x18002b138  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002b13d  mov     rax, rbx
0x18002b140  mov     rcx, [rbp+var_8]
0x18002b144  xor     rcx, rsp; StackCookie
0x18002b147  call    __security_check_cookie
0x18002b14c  mov     rbx, [rsp+60h+arg_0]
0x18002b154  add     rsp, 60h
0x18002b158  pop     rdi
0x18002b159  pop     rsi
0x18002b15a  pop     rbp
0x18002b15b  retn
0x18002b15c  lfence
0x18002b15f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
