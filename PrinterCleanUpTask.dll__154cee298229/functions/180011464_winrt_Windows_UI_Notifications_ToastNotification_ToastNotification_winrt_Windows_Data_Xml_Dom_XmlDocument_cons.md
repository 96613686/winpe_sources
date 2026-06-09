# winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)

- ea: `0x180011464`
- end: `0x1800114d0`
- name: `??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z`
- size: `108`
- prototype: `winrt::Windows::UI::Notifications::ToastNotification *__fastcall(winrt::Windows::UI::Notifications::ToastNotification *this, const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011a10`
- `0x180015a9c`

## callees

- `0x180010e20`
- `0x180011464`
- `0x18001192c`

## pseudocode

```c
winrt::Windows::UI::Notifications::ToastNotification *__fastcall winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
        winrt::Windows::UI::Notifications::ToastNotification *this,
        const struct winrt::Windows::Data::Xml::Dom::XmlDocument *a2)
{
  const struct winrt::Windows::Data::Xml::Dom::XmlDocument *v4; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v5; // [rsp+38h] [rbp+10h]

  v4 = a2;
  v5 = &qword_1800227F8;
  _InterlockedIncrement64(&qword_1800227F8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> )
  {
    _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(
      &v4,
      this,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>);
    _InterlockedDecrement64(&qword_1800227F8);
  }
  else
  {
    _InterlockedDecrement64(&qword_1800227F8);
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::call<_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_ &>(
      (void (__fastcall ***)(_QWORD, __int64 *, __int64 **))this,
      (__int64)this,
      (__int64)&v4);
  }
  return this;
}

```

## disassembly

```asm
0x180011464  mov     r11, rsp
0x180011467  mov     [r11+8], rcx
0x18001146b  push    rbx
0x18001146c  sub     rsp, 20h
0x180011470  mov     rbx, rcx
0x180011473  mov     [r11+8], rdx
0x180011477  lea     rax, qword_1800227F8
0x18001147e  mov     [r11+10h], rax
0x180011482  lock inc cs:qword_1800227F8
0x18001148a  cmp     cs:??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x180011492  jz      short loc_1800114B2
0x180011494  lea     r8, ??$factory_cache_entry_v@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotification,winrt::Windows::UI::Notifications::IToastNotificationFactory>
0x18001149b  mov     rdx, rcx
0x18001149e  lea     rcx, [r11+8]
0x1800114a2  call    ??R_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@QEBA@AEBUIToastNotificationFactory@Notifications@UI@Windows@winrt@@@Z; _lambda_e7825ad3ff420bc6a1e9d59d2abf4009_::operator()(winrt::Windows::UI::Notifications::IToastNotificationFactory const &)
0x1800114a7  nop
0x1800114a8  lock dec cs:qword_1800227F8
0x1800114b0  jmp     short loc_1800114C7
0x1800114b2  lock dec cs:qword_1800227F8
0x1800114ba  lea     r8, [rsp+28h+arg_0]
0x1800114bf  mov     rdx, rbx
0x1800114c2  call    ??$call@AEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@?$factory_cache_entry@UToastNotification@Notifications@UI@Windows@winrt@@UIToastNotificationFactory@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e7825ad3ff420bc6a1e9d59d2abf4009_@@@Z
0x1800114c7  mov     rax, rbx
0x1800114ca  add     rsp, 20h
0x1800114ce  pop     rbx
0x1800114cf  retn
```
