# SystemSettings::PenSettings::PenUtils::GetPenAndInkSettings(void)

- ea: `0x180013fc0`
- end: `0x1800140bf`
- name: `?GetPenAndInkSettings@PenUtils@PenSettings@SystemSettings@@SA?AV?$ComPtr@UIPenAndInkSettings@Inking@Input@UI@Windows@@@WRL@Microsoft@@XZ`
- size: `255`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800106d8`
- `0x180010788`
- `0x180033b58`
- `0x180034224`

## callees

- `0x1800030e0`
- `0x180008128`
- `0x1800127cc`
- `0x180013fc0`
- `0x180019a20`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001402a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001402a`

## string_xrefs

- `0x18001403c`: `shellcommon\shell\settingshandlers\pen\lib\PenUtils.h`
- `0x180014083`: `shellcommon\shell\settingshandlers\pen\lib\PenUtils.h`

## pseudocode

```c
_QWORD *__fastcall SystemSettings::PenSettings::PenUtils::GetPenAndInkSettings(_QWORD *a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD *); // rbx
  int v6; // eax
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v9; // [rsp+28h] [rbp-30h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  v10 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v9,
    L"Windows.UI.Input.Inking.PenAndInkSettings",
    0x2Au,
    0x29u);
  v2 = v10;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_ed6dd036_5708_5c3c_96db_f2f552eab641, &v8);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\PenUtils.h",
      (const char *)(unsigned int)ActivationFactory,
      v8);
  *a1 = 0;
  v4 = v8;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v8 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  v6 = v5(v4, a1);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\PenUtils.h",
      (const char *)(unsigned int)v6,
      v8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
  return a1;
}

```

## disassembly

```asm
0x180013fc0  mov     r11, rsp
0x180013fc3  mov     [r11+10h], rbx
0x180013fc7  mov     [r11+18h], rsi
0x180013fcb  push    rdi
0x180013fcc  sub     rsp, 50h
0x180013fd0  mov     rax, cs:__security_cookie
0x180013fd7  xor     rax, rsp
0x180013fda  mov     [rsp+58h+var_10], rax
0x180013fdf  mov     rsi, rcx
0x180013fe2  mov     qword ptr [r11-38h], 0
0x180013fea  mov     qword ptr [r11-18h], 0
0x180013ff2  mov     r9d, 29h ; ')'; unsigned int
0x180013ff8  lea     r8d, [r9+1]; unsigned int
0x180013ffc  lea     rdx, ?RuntimeClass_Windows_UI_Input_Inking_PenAndInkSettings@@3QBGB; "Windows.UI.Input.Inking.PenAndInkSettin"...
0x180014003  lea     rcx, [r11-30h]; hstringHeader
0x180014007  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001400c  mov     rbx, [rsp+58h+var_18]
0x180014011  lea     rcx, [rsp+58h+var_38]
0x180014016  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001401b  lea     r8, [rsp+58h+var_38]
0x180014020  lea     rdx, _GUID_ed6dd036_5708_5c3c_96db_f2f552eab641
0x180014027  mov     rcx, rbx
0x18001402a  call    cs:__imp_RoGetActivationFactory
0x180014030  test    eax, eax
0x180014032  jns     short loc_18001404E
0x180014034  mov     rcx, [rsp+58h]; this
0x180014039  mov     r9d, eax; char *
0x18001403c  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\p"...
0x180014043  mov     edx, 16h; void *
0x180014048  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001404e  mov     qword ptr [rsi], 0
0x180014055  mov     rdi, [rsp+58h+var_38]
0x18001405a  mov     rax, [rdi]
0x18001405d  mov     rbx, [rax+30h]
0x180014061  mov     rcx, rsi
0x180014064  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014069  mov     rdx, rsi
0x18001406c  mov     rcx, rdi
0x18001406f  mov     rax, rbx
0x180014072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014077  test    eax, eax
0x180014079  jns     short loc_180014095
0x18001407b  mov     rcx, [rsp+58h]; this
0x180014080  mov     r9d, eax; char *
0x180014083  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\p"...
0x18001408a  mov     edx, 18h; void *
0x18001408f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014095  lea     rcx, [rsp+58h+var_38]
0x18001409a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001409f  mov     rax, rsi
0x1800140a2  mov     rcx, [rsp+58h+var_10]
0x1800140a7  xor     rcx, rsp; StackCookie
0x1800140aa  call    __security_check_cookie
0x1800140af  mov     rbx, [rsp+58h+arg_8]
0x1800140b4  mov     rsi, [rsp+58h+arg_10]
0x1800140b9  add     rsp, 50h
0x1800140bd  pop     rdi
0x1800140be  retn
```
