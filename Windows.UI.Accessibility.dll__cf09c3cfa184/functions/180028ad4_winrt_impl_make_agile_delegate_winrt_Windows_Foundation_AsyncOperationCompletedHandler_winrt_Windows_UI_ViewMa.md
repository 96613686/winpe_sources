# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController> const &)

- ea: `0x180028ad4`
- end: `0x180028bd2`
- name: `??$make_agile_delegate@U?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@1@AEBU2341@@Z`
- size: `254`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800293b0`

## callees

- `0x180003980`
- `0x1800072d8`
- `0x180025890`
- `0x18002636c`
- `0x1800264cc`
- `0x18002873c`
- `0x180028ad4`
- `0x180035010`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>(
        winrt::Windows::Foundation::IUnknown *this,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  __int64 v8; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v9[24]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v10; // [rsp+48h] [rbp-18h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*a2;
  if ( *a2 && (v8 = 0, (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v8), v8) )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
    *(_QWORD *)this = *a2;
    winrt::Windows::Foundation::IUnknown::add_ref(this);
  }
  else
  {
    v10 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>;
    v7 = 0;
    winrt::impl::get_agile_reference(&v8, &v10, *a2, &v7);
    if ( v7 )
    {
      v5 = _lambda_2d8be16596ea8fbaef0dee832d8245dc_::_lambda_2d8be16596ea8fbaef0dee832d8245dc_(v9, &v7, &v10);
      winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>(
        this,
        v5);
    }
    else
    {
      *(_QWORD *)this = *a2;
      winrt::Windows::Foundation::IUnknown::add_ref(this);
    }
    if ( v7 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v7);
  }
  return this;
}

```

## disassembly

```asm
0x180028ad4  mov     [rsp-8+arg_10], rbx
0x180028ad9  mov     [rsp-8+arg_18], rdi
0x180028ade  push    rbp
0x180028adf  mov     rbp, rsp
0x180028ae2  sub     rsp, 60h
0x180028ae6  mov     rax, cs:__security_cookie
0x180028aed  xor     rax, rsp
0x180028af0  mov     [rbp+var_8], rax
0x180028af4  mov     rdi, rdx
0x180028af7  mov     rbx, rcx
0x180028afa  mov     rcx, [rdx]
0x180028afd  test    rcx, rcx
0x180028b00  jz      short loc_180028B46
0x180028b02  mov     [rbp+var_38], 0
0x180028b0a  mov     rax, [rcx]
0x180028b0d  lea     r8, [rbp+var_38]
0x180028b11  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180028b18  mov     rax, [rax]
0x180028b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b20  mov     rcx, [rbp+var_38]
0x180028b24  mov     [rbp+var_38], rcx
0x180028b28  test    rcx, rcx
0x180028b2b  jz      short loc_180028B46
0x180028b2d  lea     rcx, [rbp+var_38]
0x180028b31  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028b36  mov     rcx, [rdi]
0x180028b39  mov     [rbx], rcx
0x180028b3c  mov     rcx, rbx; this
0x180028b3f  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180028b44  jmp     short loc_180028BB1
0x180028b46  movups  xmm0, cs:??$guid_v@U?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>>
0x180028b4d  movdqu  [rbp+var_18], xmm0
0x180028b52  mov     [rbp+var_40], 0
0x180028b5a  lea     r9, [rbp+var_40]
0x180028b5e  mov     r8, [rdi]
0x180028b61  lea     rdx, [rbp+var_18]
0x180028b65  lea     rcx, [rbp+var_38]
0x180028b69  call    ?get_agile_reference@impl@winrt@@YA?AUhresult@2@AEBUguid@2@PEAXPEAPEAX@Z; winrt::impl::get_agile_reference(winrt::guid const &,void *,void * *)
0x180028b6e  cmp     [rbp+var_40], 0
0x180028b73  jnz     short loc_180028B85
0x180028b75  mov     rax, [rdi]
0x180028b78  mov     [rbx], rax
0x180028b7b  mov     rcx, rbx; this
0x180028b7e  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180028b83  jmp     short loc_180028BA1
0x180028b85  lea     r8, [rbp+var_18]
0x180028b89  lea     rdx, [rbp+var_40]
0x180028b8d  lea     rcx, [rbp+var_30]
0x180028b91  call    ??0_lambda_2d8be16596ea8fbaef0dee832d8245dc_@@QEAA@$$QEAU?$com_ptr@UIAgileReference@impl@winrt@@@winrt@@AEBUguid@2@@Z; _lambda_2d8be16596ea8fbaef0dee832d8245dc_::_lambda_2d8be16596ea8fbaef0dee832d8245dc_(winrt::com_ptr<winrt::impl::IAgileReference> &&,winrt::guid const &)
0x180028b96  mov     rdx, rax
0x180028b99  mov     rcx, rbx
0x180028b9c  call    ??$?0V_lambda_49cc262f2c2f085434b521599bde9f4e_@@@?$AsyncOperationCompletedHandler@UUISettingsController@Core@ViewManagement@UI@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@V_lambda_49cc262f2c2f085434b521599bde9f4e_@@@Z; winrt::Windows::Foundation::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>::AsyncOperationCompletedHandler<winrt::Windows::UI::ViewManagement::Core::UISettingsController>(_lambda_49cc262f2c2f085434b521599bde9f4e_)
0x180028ba1  cmp     [rbp+var_40], 0
0x180028ba6  jz      short loc_180028BB1
0x180028ba8  lea     rcx, [rbp+var_40]
0x180028bac  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028bb1  mov     rax, rbx
0x180028bb4  mov     rcx, [rbp+var_8]
0x180028bb8  xor     rcx, rsp; StackCookie
0x180028bbb  call    __security_check_cookie
0x180028bc0  lea     r11, [rsp+60h+var_s0]
0x180028bc5  mov     rbx, [r11+20h]
0x180028bc9  mov     rdi, [r11+28h]
0x180028bcd  mov     rsp, r11
0x180028bd0  pop     rbp
0x180028bd1  retn
```
