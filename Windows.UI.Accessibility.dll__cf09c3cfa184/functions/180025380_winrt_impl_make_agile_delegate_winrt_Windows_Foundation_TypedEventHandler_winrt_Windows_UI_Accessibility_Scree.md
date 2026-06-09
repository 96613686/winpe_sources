# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> const &)

- ea: `0x180025380`
- end: `0x18002547e`
- name: `??$make_agile_delegate@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@1@AEBU2341@@Z`
- size: `254`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800261b4`

## callees

- `0x180003980`
- `0x1800072d8`
- `0x180024db8`
- `0x180025380`
- `0x180025890`
- `0x18002636c`
- `0x1800264cc`
- `0x180035010`

## pseudocode

```c
winrt::Windows::Foundation::IUnknown *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>(
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
    v10 = winrt::impl::guid_v<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>;
    v7 = 0;
    winrt::impl::get_agile_reference(&v8, &v10, *a2, &v7);
    if ( v7 )
    {
      v5 = _lambda_2d8be16596ea8fbaef0dee832d8245dc_::_lambda_2d8be16596ea8fbaef0dee832d8245dc_(v9, &v7, &v10);
      winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(
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
0x180025380  mov     [rsp-8+arg_10], rbx
0x180025385  mov     [rsp-8+arg_18], rdi
0x18002538a  push    rbp
0x18002538b  mov     rbp, rsp
0x18002538e  sub     rsp, 60h
0x180025392  mov     rax, cs:__security_cookie
0x180025399  xor     rax, rsp
0x18002539c  mov     [rbp+var_8], rax
0x1800253a0  mov     rdi, rdx
0x1800253a3  mov     rbx, rcx
0x1800253a6  mov     rcx, [rdx]
0x1800253a9  test    rcx, rcx
0x1800253ac  jz      short loc_1800253F2
0x1800253ae  mov     [rbp+var_38], 0
0x1800253b6  mov     rax, [rcx]
0x1800253b9  lea     r8, [rbp+var_38]
0x1800253bd  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800253c4  mov     rax, [rax]
0x1800253c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253cc  mov     rcx, [rbp+var_38]
0x1800253d0  mov     [rbp+var_38], rcx
0x1800253d4  test    rcx, rcx
0x1800253d7  jz      short loc_1800253F2
0x1800253d9  lea     rcx, [rbp+var_38]
0x1800253dd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800253e2  mov     rcx, [rdi]
0x1800253e5  mov     [rbx], rcx
0x1800253e8  mov     rcx, rbx; this
0x1800253eb  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x1800253f0  jmp     short loc_18002545D
0x1800253f2  movups  xmm0, cs:??$guid_v@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>
0x1800253f9  movdqu  [rbp+var_18], xmm0
0x1800253fe  mov     [rbp+var_40], 0
0x180025406  lea     r9, [rbp+var_40]
0x18002540a  mov     r8, [rdi]
0x18002540d  lea     rdx, [rbp+var_18]
0x180025411  lea     rcx, [rbp+var_38]
0x180025415  call    ?get_agile_reference@impl@winrt@@YA?AUhresult@2@AEBUguid@2@PEAXPEAPEAX@Z; winrt::impl::get_agile_reference(winrt::guid const &,void *,void * *)
0x18002541a  cmp     [rbp+var_40], 0
0x18002541f  jnz     short loc_180025431
0x180025421  mov     rax, [rdi]
0x180025424  mov     [rbx], rax
0x180025427  mov     rcx, rbx; this
0x18002542a  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18002542f  jmp     short loc_18002544D
0x180025431  lea     r8, [rbp+var_18]
0x180025435  lea     rdx, [rbp+var_40]
0x180025439  lea     rcx, [rbp+var_30]
0x18002543d  call    ??0_lambda_2d8be16596ea8fbaef0dee832d8245dc_@@QEAA@$$QEAU?$com_ptr@UIAgileReference@impl@winrt@@@winrt@@AEBUguid@2@@Z; _lambda_2d8be16596ea8fbaef0dee832d8245dc_::_lambda_2d8be16596ea8fbaef0dee832d8245dc_(winrt::com_ptr<winrt::impl::IAgileReference> &&,winrt::guid const &)
0x180025442  mov     rdx, rax
0x180025445  mov     rcx, rbx
0x180025448  call    ??$?0V_lambda_7999d173cb425bec7b2e88e6adb3955f_@@@?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@QEAA@V_lambda_7999d173cb425bec7b2e88e6adb3955f_@@@Z; winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(_lambda_7999d173cb425bec7b2e88e6adb3955f_)
0x18002544d  cmp     [rbp+var_40], 0
0x180025452  jz      short loc_18002545D
0x180025454  lea     rcx, [rbp+var_40]
0x180025458  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002545d  mov     rax, rbx
0x180025460  mov     rcx, [rbp+var_8]
0x180025464  xor     rcx, rsp; StackCookie
0x180025467  call    __security_check_cookie
0x18002546c  lea     r11, [rsp+60h+var_s0]
0x180025471  mov     rbx, [r11+20h]
0x180025475  mov     rdi, [r11+28h]
0x180025479  mov     rsp, r11
0x18002547c  pop     rbp
0x18002547d  retn
```
