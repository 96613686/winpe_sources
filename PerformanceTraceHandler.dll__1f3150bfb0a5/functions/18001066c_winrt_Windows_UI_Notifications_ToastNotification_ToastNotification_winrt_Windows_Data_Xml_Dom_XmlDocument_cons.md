# winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)

- ea: `0x18001066c`
- end: `0x1800106d8`
- name: `??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z`
- size: `108`
- prototype: `winrt::Windows::UI::Notifications::ToastNotification *__fastcall(winrt::Windows::UI::Notifications::ToastNotification *this, const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011e50`
- `0x1800120b8`
- `0x180016a30`
- `0x180016b6c`
- `0x18001874c`

## callees

- `0x18000f9d4`
- `0x18001066c`
- `0x180010e00`

## pseudocode

```c
winrt::Windows::UI::Notifications::ToastNotification *__fastcall winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
        winrt::Windows::UI::Notifications::ToastNotification *this,
        const struct winrt::Windows::Data::Xml::Dom::XmlDocument *a2)
{
  const struct winrt::Windows::Data::Xml::Dom::XmlDocument *v4; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v5; // [rsp+38h] [rbp+10h]

  v4 = a2;
  v5 = &qword_180027A18;
  _InterlockedIncrement64(&qword_180027A18);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> )
  {
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(
      &v4,
      this,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>);
    _InterlockedDecrement64(&qword_180027A18);
  }
  else
  {
    _InterlockedDecrement64(&qword_180027A18);
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
      (__int64 *)this,
      (__int64)this,
      (__int64)&v4);
  }
  return this;
}

```

## disassembly

```asm
0x18001066c  mov     r11, rsp
0x18001066f  mov     [r11+8], rcx
0x180010673  push    rbx
0x180010674  sub     rsp, 20h
0x180010678  mov     rbx, rcx
0x18001067b  mov     [r11+8], rdx
0x18001067f  lea     rax, qword_180027A18
0x180010686  mov     [r11+10h], rax
0x18001068a  lock inc cs:qword_180027A18
0x180010692  cmp     cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18001069a  jz      short loc_1800106BA
0x18001069c  lea     r8, ??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x1800106a3  mov     rdx, rcx
0x1800106a6  lea     rcx, [r11+8]
0x1800106aa  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x1800106af  nop
0x1800106b0  lock dec cs:qword_180027A18
0x1800106b8  jmp     short loc_1800106CF
0x1800106ba  lock dec cs:qword_180027A18
0x1800106c2  lea     r8, [rsp+28h+arg_0]
0x1800106c7  mov     rdx, rbx
0x1800106ca  call    ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z
0x1800106cf  mov     rax, rbx
0x1800106d2  add     rsp, 20h
0x1800106d6  pop     rbx
0x1800106d7  retn
```
