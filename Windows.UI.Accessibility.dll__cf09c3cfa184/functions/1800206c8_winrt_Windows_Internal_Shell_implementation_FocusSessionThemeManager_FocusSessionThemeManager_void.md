# winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::~FocusSessionThemeManager(void)

- ea: `0x1800206c8`
- end: `0x180020715`
- name: `??1FocusSessionThemeManager@implementation@Shell@Internal@Windows@winrt@@UEAA@XZ`
- size: `77`
- prototype: `void __fastcall(winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020c60`

## callees

- `0x18000df2c`
- `0x18000dfc0`
- `0x18001381c`
- `0x180020460`
- `0x1800205a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800206f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800206f0`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::~FocusSessionThemeManager(
        winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *this)
{
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>((char *)this + 192);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>((char *)this + 184);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>((char *)this + 64);
  wil::cloud_store::~cloud_store((winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager *)((char *)this + 24));
  winrt::impl::root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>::~root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>(this);
}

```

## disassembly

```asm
0x1800206c8  push    rbx
0x1800206ca  sub     rsp, 20h
0x1800206ce  mov     rbx, rcx
0x1800206d1  add     rcx, 0C0h
0x1800206d8  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x1800206dd  lea     rcx, [rbx+0B8h]
0x1800206e4  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800206e9  lea     rcx, [rbx+90h]; lpCriticalSection
0x1800206f0  call    cs:__imp_DeleteCriticalSection
0x1800206f6  lea     rcx, [rbx+40h]
0x1800206fa  call    ??1?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>::~cloud_store_data<Windows::Data::Shell::FocusActiveSessions>(void)
0x1800206ff  lea     rcx, [rbx+18h]; this
0x180020703  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x180020708  mov     rcx, rbx
0x18002070b  add     rsp, 20h
0x18002070f  pop     rbx
0x180020710  jmp     ??1?$root_implements@UScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>::~root_implements<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderService>(void)
```
