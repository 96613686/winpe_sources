# ??$make@UFocusSession@implementation@Shell@UI@Windows@winrt@@AEAUguid@6@U?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@6@@winrt@@YA?A_PAEAUguid@0@$$QEAU?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@0@@Z

- ea: `0x180026f64`
- end: `0x180026fee`
- name: `??$make@UFocusSession@implementation@Shell@UI@Windows@winrt@@AEAUguid@6@U?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@6@@winrt@@YA?A_PAEAUguid@0@$$QEAU?$com_ptr@UFocusSessionManager@implementation@Shell@UI@Windows@winrt@@@0@@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027e6c`
- `0x1800281bc`

## callees

- `0x180004c8c`
- `0x18000dd40`
- `0x18000e0b8`
- `0x180026f64`
- `0x18002e518`

## pseudocode

```c
_QWORD *__fastcall winrt::make<winrt::Windows::UI::Shell::implementation::FocusSession,winrt::guid &,winrt::com_ptr<winrt::Windows::UI::Shell::implementation::FocusSessionManager>>(
        _QWORD *a1,
        _OWORD *a2,
        __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r9
  __int64 v10; // r10
  __int64 v11; // rcx
  _QWORD *result; // rax
  char *v13; // [rsp+40h] [rbp+8h]

  v13 = (char *)operator new(0x30u);
  winrt::impl::producers_base<winrt::Windows::UI::Shell::implementation::FocusSession,std::tuple<winrt::Windows::UI::Shell::FocusSession>>::producers_base<winrt::Windows::UI::Shell::implementation::FocusSession,std::tuple<winrt::Windows::UI::Shell::FocusSession>>(
    v13 + 16,
    v6,
    v7,
    v13);
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  std::atomic<unsigned __int64>::atomic<unsigned __int64>(v8 + 8);
  *(_QWORD *)v9 = &winrt::impl::heap_implements<winrt::Windows::UI::Shell::implementation::FocusSession>::`vftable';
  *(_OWORD *)(v9 + 24) = *a2;
  v11 = *a3;
  *(_QWORD *)(v9 + 40) = *a3;
  if ( v11 )
    winrt::impl::root_implements<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::AddRef();
  *(_QWORD *)v9 = &winrt::impl::heap_implements<winrt::Windows::UI::Shell::implementation::FocusSession>::`vftable';
  result = a1;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x180026f64  mov     [rsp+arg_8], rbx
0x180026f69  mov     [rsp+arg_10], rsi
0x180026f6e  push    rdi
0x180026f6f  sub     rsp, 30h
0x180026f73  mov     rsi, rcx
0x180026f76  mov     rdi, r8
0x180026f79  mov     ecx, 30h ; '0'; Size
0x180026f7e  mov     rbx, rdx
0x180026f81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026f86  mov     r9, rax
0x180026f89  mov     [rsp+38h+arg_0], rax
0x180026f8e  lea     r10, [rax+10h]
0x180026f92  mov     rcx, r10
0x180026f95  call    ??0?$producers_base@UFocusSession@implementation@Shell@UI@Windows@winrt@@V?$tuple@UFocusSession@Shell@UI@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<winrt::Windows::UI::Shell::implementation::FocusSession,std::tuple<winrt::Windows::UI::Shell::FocusSession>>::producers_base<winrt::Windows::UI::Shell::implementation::FocusSession,std::tuple<winrt::Windows::UI::Shell::FocusSession>>(void)
0x180026f9a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180026fa1  lea     rcx, [r9+8]
0x180026fa5  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x180026faa  lea     rcx, ??_7?$heap_implements@UFocusSession@implementation@Shell@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::Shell::implementation::FocusSession>::`vftable'
0x180026fb1  mov     [r9], rcx
0x180026fb4  movups  xmm0, xmmword ptr [rbx]
0x180026fb7  movdqu  xmmword ptr [r9+18h], xmm0
0x180026fbd  mov     rcx, [rdi]
0x180026fc0  mov     [r9+28h], rcx
0x180026fc4  test    rcx, rcx
0x180026fc7  jz      short loc_180026FCE
0x180026fc9  call    ?AddRef@?$root_implements@UUISettingsController@factory_implementation@Core@ViewManagement@UI@Windows@winrt@@UIActivationFactory@Foundation@67@UIUISettingsControllerStatics@34567@@impl@winrt@@QEAAIXZ; winrt::impl::root_implements<winrt::Windows::UI::ViewManagement::Core::factory_implementation::UISettingsController,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::UI::ViewManagement::Core::IUISettingsControllerStatics>::AddRef(void)
0x180026fce  mov     rbx, [rsp+38h+arg_8]
0x180026fd3  lea     rax, ??_7?$heap_implements@UFocusSession@implementation@Shell@UI@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Windows::UI::Shell::implementation::FocusSession>::`vftable'
0x180026fda  mov     [r9], rax
0x180026fdd  mov     rax, rsi
0x180026fe0  mov     [rsi], r10
0x180026fe3  mov     rsi, [rsp+38h+arg_10]
0x180026fe8  add     rsp, 30h
0x180026fec  pop     rdi
0x180026fed  retn
```
