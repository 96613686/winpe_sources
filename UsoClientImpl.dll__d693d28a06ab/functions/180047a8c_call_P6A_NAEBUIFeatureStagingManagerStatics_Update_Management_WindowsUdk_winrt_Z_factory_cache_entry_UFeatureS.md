# ??$call@P6A_NAEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@winrt@@@Z@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@2@@Z@Z

- ea: `0x180047a8c`
- end: `0x180047bab`
- name: `??$call@P6A_NAEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@winrt@@@Z@?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A_NAEBUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@2@@Z@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041480`

## callees

- `0x18002d1a4`
- `0x180047a8c`
- `0x180047e08`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x180047ab8`: `WindowsUdk.Management.Update.FeatureStagingManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall winrt::impl::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::call<bool (*)(winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics const &)>(
        __int64 a1,
        __int64 (__fastcall **a2)(__int64 *))
{
  char v3; // bl
  _DWORD *v5; // [rsp+20h] [rbp-40h] BYREF
  _DWORD v6[4]; // [rsp+28h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+38h] [rbp-28h]
  void (__fastcall ***v8)(_QWORD, __int64 *, __int64 **); // [rsp+40h] [rbp-20h] BYREF
  __int64 *v9; // [rsp+48h] [rbp-18h] BYREF

  v6[0] = 1;
  v6[1] = 50;
  v7 = L"WindowsUdk.Management.Update.FeatureStagingManager";
  v5 = v6;
  winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(&v8, &v5);
  if ( v8 && (v9 = 0, (**v8)(v8, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v9);
    v9 = &qword_18009FB18;
    _InterlockedIncrement64(&qword_18009FB18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>,
            (signed __int64)v8,
            0) )
    {
      v8 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009FB20);
    }
    v3 = (*a2)(&winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>);
    _InterlockedDecrement64(&qword_18009FB18);
  }
  else
  {
    v3 = (*a2)((__int64 *)&v8);
  }
  if ( v8 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
  return v3;
}

```

## disassembly

```asm
0x180047a8c  mov     [rsp-8+arg_0], rbx
0x180047a91  push    rbp
0x180047a92  mov     rbp, rsp
0x180047a95  sub     rsp, 60h
0x180047a99  mov     rax, cs:__security_cookie
0x180047aa0  xor     rax, rsp
0x180047aa3  mov     [rbp+var_10], rax
0x180047aa7  mov     rbx, rdx
0x180047aaa  mov     [rbp+var_38], 1
0x180047ab1  mov     [rbp+var_34], 32h ; '2'
0x180047ab8  lea     rax, aWindowsudkMana; "WindowsUdk.Management.Update.FeatureSta"...
0x180047abf  mov     [rbp+var_28], rax
0x180047ac3  lea     rax, [rbp+var_38]
0x180047ac7  mov     [rbp+var_40], rax
0x180047acb  lea     rdx, [rbp+var_40]
0x180047acf  lea     rcx, [rbp+var_20]
0x180047ad3  call    ??$get_activation_factory@UIFeatureStagingManagerStatics@Update@Management@WindowsUdk@winrt@@@winrt@@YA?AUIFeatureStagingManagerStatics@Update@Management@WindowsUdk@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>(winrt::param::hstring const &)
0x180047ad8  nop
0x180047ad9  mov     rcx, [rbp+var_20]
0x180047add  test    rcx, rcx
0x180047ae0  jz      loc_180047B74
0x180047ae6  mov     [rbp+var_18], 0
0x180047aee  mov     rax, [rcx]
0x180047af1  lea     r8, [rbp+var_18]
0x180047af5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180047afc  mov     rax, [rax]
0x180047aff  call    _guard_dispatch_icall
0x180047b04  mov     rax, [rbp+var_18]
0x180047b08  mov     [rbp+var_18], rax
0x180047b0c  test    rax, rax
0x180047b0f  jz      short loc_180047B74
0x180047b11  lea     rcx, [rbp+var_18]
0x180047b15  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047b1a  lea     rax, qword_18009FB18
0x180047b21  mov     [rbp+var_18], rax
0x180047b25  lock inc cs:qword_18009FB18
0x180047b2d  mov     rcx, [rbp+var_20]
0x180047b31  xor     eax, eax
0x180047b33  lock cmpxchg cs:??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047b3c  jnz     short loc_180047B59
0x180047b3e  mov     [rbp+var_20], 0
0x180047b46  lea     rdx, stru_18009FB20; ListEntry
0x180047b4d  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180047b54  call    WINRT_IMPL_InterlockedPushEntrySList
0x180047b59  lea     rcx, ??$factory_cache_entry_v@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UFeatureStagingManager@Update@Management@WindowsUdk@winrt@@UIFeatureStagingManagerStatics@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>::winrt::factory_cache_entry<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::Management::Update::FeatureStagingManager,winrt::WindowsUdk::Management::Update::IFeatureStagingManagerStatics>
0x180047b60  mov     rax, [rbx]
0x180047b63  call    _guard_dispatch_icall
0x180047b68  mov     bl, al
0x180047b6a  lock dec cs:qword_18009FB18
0x180047b72  jmp     short loc_180047B82
0x180047b74  lea     rcx, [rbp+var_20]
0x180047b78  mov     rax, [rbx]
0x180047b7b  call    _guard_dispatch_icall
0x180047b80  mov     bl, al
0x180047b82  cmp     [rbp+var_20], 0
0x180047b87  jz      short loc_180047B92
0x180047b89  lea     rcx, [rbp+var_20]
0x180047b8d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180047b92  mov     al, bl
0x180047b94  mov     rcx, [rbp+var_10]
0x180047b98  xor     rcx, rsp; StackCookie
0x180047b9b  call    __security_check_cookie
0x180047ba0  mov     rbx, [rsp+60h+arg_0]
0x180047ba5  add     rsp, 60h
0x180047ba9  pop     rbp
0x180047baa  retn
```
