# winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)

- ea: `0x180010f20`
- end: `0x180010f8c`
- name: `?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z`
- size: `108`
- prototype: `const struct winrt::param::hstring *__fastcall(const struct winrt::param::hstring *, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e50`
- `0x1800120b8`
- `0x180016a30`
- `0x180016b6c`
- `0x18001874c`

## callees

- `0x18000f888`
- `0x180010d4c`
- `0x180010f20`

## pseudocode

```c
const struct winrt::param::hstring *__fastcall winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(
        const struct winrt::param::hstring *a1,
        __int64 a2)
{
  __int64 v4; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v5; // [rsp+48h] [rbp+10h]

  v4 = a2;
  v5 = &qword_180027A38;
  _InterlockedIncrement64(&qword_180027A38);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> )
  {
    _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(
      &v4,
      a1,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>);
    _InterlockedDecrement64(&qword_180027A38);
  }
  else
  {
    _InterlockedDecrement64(&qword_180027A38);
    winrt::impl::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::call<_lambda_9963adada1db90a1e471b6d32fa55098_ &>(
      (__int64 *)a1,
      (__int64)a1,
      (__int64)&v4);
  }
  return a1;
}

```

## disassembly

```asm
0x180010f20  mov     r11, rsp
0x180010f23  mov     [r11+8], rcx
0x180010f27  push    rbx
0x180010f28  sub     rsp, 30h
0x180010f2c  mov     rbx, rcx
0x180010f2f  mov     [r11+8], rdx
0x180010f33  lea     rax, qword_180027A38
0x180010f3a  mov     [r11+10h], rax
0x180010f3e  lock inc cs:qword_180027A38
0x180010f46  cmp     cs:??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x180010f4e  jz      short loc_180010F6E
0x180010f50  lea     r8, ??$factory_cache_entry_v@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>::winrt::factory_cache_entry<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::UI::Notifications::ToastNotificationManager,winrt::Windows::UI::Notifications::IToastNotificationManagerStatics>
0x180010f57  mov     rdx, rcx
0x180010f5a  lea     rcx, [r11+8]
0x180010f5e  call    ??R_lambda_9963adada1db90a1e471b6d32fa55098_@@QEBA@AEBUIToastNotificationManagerStatics@Notifications@UI@Windows@winrt@@@Z; _lambda_9963adada1db90a1e471b6d32fa55098_::operator()(winrt::Windows::UI::Notifications::IToastNotificationManagerStatics const &)
0x180010f63  nop
0x180010f64  lock dec cs:qword_180027A38
0x180010f6c  jmp     short loc_180010F83
0x180010f6e  lock dec cs:qword_180027A38
0x180010f76  lea     r8, [rsp+38h+arg_0]
0x180010f7b  mov     rdx, rbx
0x180010f7e  call    ??$call@AEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@?$factory_cache_entry@UToastNotificationManager@Notifications@UI@Windows@winrt@@UIToastNotificationManagerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9963adada1db90a1e471b6d32fa55098_@@@Z
0x180010f83  mov     rax, rbx
0x180010f86  add     rsp, 30h
0x180010f8a  pop     rbx
0x180010f8b  retn
```
