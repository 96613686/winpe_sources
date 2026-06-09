# _lambda_2ac8fe0392921df34437e8d03cccd24f_::operator()(void)

- ea: `0x1800223d4`
- end: `0x180022516`
- name: `??R_lambda_2ac8fe0392921df34437e8d03cccd24f_@@QEBA?AUhstring@winrt@@XZ`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180022c98`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000d810`
- `0x180020cac`
- `0x180022338`
- `0x180022380`
- `0x1800223d4`

## string_xrefs

- `0x18002247a`: `PackageFolderPath`
- `0x180022445`: `TaskbarIconPackageResource`
- `0x1800223fe`: `TaskbarIconResource`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall _lambda_2ac8fe0392921df34437e8d03cccd24f_::operator()(__int64 *a1, _QWORD *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rax
  _BYTE v10[16]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v11; // [rsp+30h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-18h] BYREF
  _QWORD *v13; // [rsp+40h] [rbp-10h] BYREF

  v13 = a2;
  v4 = *a1;
  winrt::hstring::hstring((winrt::hstring *)v10, L"TaskbarIconResource");
  ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v11, v10, v4);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
  v5 = v11;
  if ( v11 )
  {
    v11 = 0;
    *a2 = v5;
  }
  else
  {
    v6 = *a1;
    winrt::hstring::hstring((winrt::hstring *)v10, L"TaskbarIconPackageResource");
    ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v12, v10, v6);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
    if ( v12 )
    {
      v7 = *a1;
      winrt::hstring::hstring((winrt::hstring *)v10, L"PackageFolderPath");
      ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(&v13, v10, v7);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
      v8 = winrt::operator+(v10, &v13, L"\\");
      winrt::operator+(a2, v8, &v12);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v10);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v13);
    }
    else
    {
      *a2 = 0;
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v12);
  }
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v11);
  return a2;
}

```

## disassembly

```asm
0x1800223d4  mov     [rsp-18h+arg_10], rbx
0x1800223d9  push    rbp
0x1800223da  push    rsi
0x1800223db  push    rdi
0x1800223dc  mov     rbp, rsp
0x1800223df  sub     rsp, 50h
0x1800223e3  mov     rax, cs:__security_cookie
0x1800223ea  xor     rax, rsp
0x1800223ed  mov     [rbp+var_8], rax
0x1800223f1  mov     rdi, rdx
0x1800223f4  mov     rsi, rcx
0x1800223f7  mov     [rbp+var_10], rdx
0x1800223fb  mov     rbx, [rcx]
0x1800223fe  lea     rdx, aTaskbariconres; "TaskbarIconResource"
0x180022405  lea     rcx, [rbp+var_30]; this
0x180022409  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002240e  nop
0x18002240f  mov     r8, rbx
0x180022412  lea     rdx, [rbp+var_30]
0x180022416  lea     rcx, [rbp+var_20]
0x18002241a  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002241f  nop
0x180022420  lea     rcx, [rbp+var_30]
0x180022424  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022429  mov     rcx, [rbp+var_20]
0x18002242d  test    rcx, rcx
0x180022430  jz      short loc_180022442
0x180022432  mov     [rbp+var_20], 0
0x18002243a  mov     [rdi], rcx
0x18002243d  jmp     loc_1800224EE
0x180022442  mov     rbx, [rsi]
0x180022445  lea     rdx, aTaskbariconpac; "TaskbarIconPackageResource"
0x18002244c  lea     rcx, [rbp+var_30]; this
0x180022450  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180022455  nop
0x180022456  mov     r8, rbx
0x180022459  lea     rdx, [rbp+var_30]
0x18002245d  lea     rcx, [rbp+var_18]
0x180022461  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180022466  nop
0x180022467  lea     rcx, [rbp+var_30]
0x18002246b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180022470  cmp     [rbp+var_18], 0
0x180022475  jz      short loc_1800224DF
0x180022477  mov     rbx, [rsi]
0x18002247a  lea     rdx, aPackagefolderp; "PackageFolderPath"
0x180022481  lea     rcx, [rbp+var_30]; this
0x180022485  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18002248a  nop
0x18002248b  mov     r8, rbx
0x18002248e  lea     rdx, [rbp+var_30]
0x180022492  lea     rcx, [rbp+var_10]
0x180022496  call    ??$try_get_value@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@@Z; ValueSetUtils::try_get_value<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x18002249b  nop
0x18002249c  lea     rcx, [rbp+var_30]
0x1800224a0  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800224a5  lea     r8, asc_18005F868; "\\"
0x1800224ac  lea     rdx, [rbp+var_10]
0x1800224b0  lea     rcx, [rbp+var_30]
0x1800224b4  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@PEB_W@Z; winrt::operator+(winrt::hstring const &,wchar_t const *)
0x1800224b9  nop
0x1800224ba  lea     r8, [rbp+var_18]
0x1800224be  mov     rdx, rax
0x1800224c1  mov     rcx, rdi
0x1800224c4  call    ??Hwinrt@@YA?AUhstring@0@AEBU10@0@Z; winrt::operator+(winrt::hstring const &,winrt::hstring const &)
0x1800224c9  nop
0x1800224ca  lea     rcx, [rbp+var_30]
0x1800224ce  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800224d3  nop
0x1800224d4  lea     rcx, [rbp+var_10]
0x1800224d8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800224dd  jmp     short loc_1800224E4
0x1800224df  xor     eax, eax
0x1800224e1  mov     [rdi], rax
0x1800224e4  lea     rcx, [rbp+var_18]
0x1800224e8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800224ed  nop
0x1800224ee  lea     rcx, [rbp+var_20]
0x1800224f2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800224f7  mov     rax, rdi
0x1800224fa  mov     rcx, [rbp+var_8]
0x1800224fe  xor     rcx, rsp; StackCookie
0x180022501  call    __security_check_cookie
0x180022506  mov     rbx, [rsp+50h+arg_10]
0x18002250e  add     rsp, 50h
0x180022512  pop     rdi
0x180022513  pop     rsi
0x180022514  pop     rbp
0x180022515  retn
```
