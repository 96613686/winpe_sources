# winrt::impl::consume_Windows_UI_Notifications_IToastNotificationFactory<winrt::Windows::UI::Notifications::IToastNotificationFactory>::CreateToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)

- ea: `0x1800123dc`
- end: `0x180012439`
- name: `?CreateToastNotification@?$consume_Windows_UI_Notifications_IToastNotificationFactory@UIToastNotificationFactory@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUXmlDocument@Dom@Xml@Data@Windows@3@@Z`
- size: `93`
- prototype: `_QWORD *__fastcall(__int64 **, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001192c`

## callees

- `0x18000f38c`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Notifications_IToastNotificationFactory<winrt::Windows::UI::Notifications::IToastNotificationFactory>::CreateToastNotification(
        __int64 **a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = a2;
  v3 = *a1;
  v11 = 0;
  v9 = 0;
  v5 = *v3;
  v6 = *a3;
  v10 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 48))(v3, v6, &v11);
  winrt::check_hresult((int *)&v12, v7, (__int64)&v9);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x1800123dc  mov     [rsp+arg_8], rdx
0x1800123e1  push    rbx
0x1800123e2  sub     rsp, 40h
0x1800123e6  mov     rcx, [rcx]
0x1800123e9  xor     eax, eax
0x1800123eb  mov     [rsp+48h+arg_0], rax
0x1800123f0  mov     r9, r8
0x1800123f3  mov     [rsp+48h+var_20], eax
0x1800123f7  lea     r8, [rsp+48h+arg_0]
0x1800123fc  mov     rbx, rdx
0x1800123ff  xorps   xmm0, xmm0
0x180012402  mov     rax, [rcx]
0x180012405  mov     rdx, [r9]
0x180012408  movdqu  [rsp+48h+var_18], xmm0
0x18001240e  mov     rax, [rax+30h]
0x180012412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012417  lea     r8, [rsp+48h+var_20]
0x18001241c  mov     edx, eax
0x18001241e  lea     rcx, [rsp+48h+arg_8]
0x180012423  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180012428  mov     rax, [rsp+48h+arg_0]
0x18001242d  mov     [rbx], rax
0x180012430  mov     rax, rbx
0x180012433  add     rsp, 40h
0x180012437  pop     rbx
0x180012438  retn
```
