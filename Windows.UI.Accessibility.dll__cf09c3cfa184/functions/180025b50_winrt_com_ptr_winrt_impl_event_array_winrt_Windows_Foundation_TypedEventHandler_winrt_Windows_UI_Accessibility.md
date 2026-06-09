# winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>>::~com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>>(void)

- ea: `0x180025b50`
- end: `0x180025b64`
- name: `??1?$com_ptr@U?$event_array@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033999`
- `0x180033a34`
- `0x180033a92`
- `0x180033ab6`
- `0x180033ada`
- `0x180033aec`
- `0x180033bab`

## callees

- `0x180025b50`
- `0x180026744`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>>::~com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>>(
        unsigned int **a1)
{
  if ( *a1 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(a1);
}

```

## disassembly

```asm
0x180025b50  sub     rsp, 28h
0x180025b54  cmp     qword ptr [rcx], 0
0x180025b58  jz      short loc_180025B5F
0x180025b5a  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180025b5f  add     rsp, 28h
0x180025b63  retn
```
