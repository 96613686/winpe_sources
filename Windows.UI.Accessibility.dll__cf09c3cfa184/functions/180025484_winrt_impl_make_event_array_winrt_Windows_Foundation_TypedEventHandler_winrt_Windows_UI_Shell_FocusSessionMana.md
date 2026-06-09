# winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(uint)

- ea: `0x180025484`
- end: `0x180025506`
- name: `??$make_event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002624c`
- `0x18002652c`

## callees

- `0x180004c8c`
- `0x1800072d8`
- `0x18000deb8`
- `0x180025120`
- `0x180025134`
- `0x180025484`

## pseudocode

```c
winrt::impl::atomic_ref_count **__fastcall winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(
        winrt::impl::atomic_ref_count **a1,
        unsigned int a2)
{
  unsigned int v2; // esi
  winrt::impl::atomic_ref_count *v4; // rdi
  unsigned int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rbx
  winrt::impl::atomic_ref_count **v9; // [rsp+60h] [rbp+8h] BYREF

  v9 = a1;
  v2 = a2;
  v4 = (winrt::impl::atomic_ref_count *)operator new(8LL * a2 + 8);
  winrt::impl::atomic_ref_count::atomic_ref_count(v4, v5);
  *(_DWORD *)(v6 + 4) = v2;
  v9 = 0;
  if ( v2 )
  {
    v7 = v6 + 8;
    do
    {
      std::_Construct_in_place<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> const &>(
        v7,
        &v9);
      v7 += 8;
      --v2;
    }
    while ( v2 );
    std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *>(
      v7,
      v7);
    if ( v9 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)&v9);
  }
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x180025484  mov     [rsp+arg_0], rcx
0x180025489  push    rbx
0x18002548a  push    rsi
0x18002548b  push    rdi
0x18002548c  push    r14
0x18002548e  sub     rsp, 38h
0x180025492  mov     esi, edx
0x180025494  mov     r14, rcx
0x180025497  lea     rcx, ds:8[rsi*8]; Size
0x18002549f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800254a4  mov     rcx, rax; this
0x1800254a7  mov     rdi, rax
0x1800254aa  call    ??0atomic_ref_count@impl@winrt@@QEAA@I@Z; winrt::impl::atomic_ref_count::atomic_ref_count(uint)
0x1800254af  mov     [rcx+4], esi
0x1800254b2  mov     [rsp+58h+arg_0], 0
0x1800254bb  test    esi, esi
0x1800254bd  jz      short loc_1800254F6
0x1800254bf  lea     rbx, [rcx+8]
0x1800254c3  lea     rdx, [rsp+58h+arg_0]
0x1800254c8  mov     rcx, rbx
0x1800254cb  call    ??$_Construct_in_place@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@AEBU1234@@std@@YAXAEAU?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@AEBU1234@@Z; std::_Construct_in_place<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> const &>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> &,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> const &)
0x1800254d0  add     rbx, 8
0x1800254d4  add     esi, 0FFFFFFFFh
0x1800254d7  jnz     short loc_1800254C3
0x1800254d9  mov     rdx, rbx
0x1800254dc  mov     rcx, rbx
0x1800254df  call    ??$_Destroy_range@PEAU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@PEAU1234@@std@@YAXPEAU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@QEAU1234@@Z; std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> * const)
0x1800254e4  cmp     [rsp+58h+arg_0], 0
0x1800254ea  jz      short loc_1800254F6
0x1800254ec  lea     rcx, [rsp+58h+arg_0]
0x1800254f1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800254f6  mov     [r14], rdi
0x1800254f9  mov     rax, r14
0x1800254fc  add     rsp, 38h
0x180025500  pop     r14
0x180025502  pop     rdi
0x180025503  pop     rsi
0x180025504  pop     rbx
0x180025505  retn
```
