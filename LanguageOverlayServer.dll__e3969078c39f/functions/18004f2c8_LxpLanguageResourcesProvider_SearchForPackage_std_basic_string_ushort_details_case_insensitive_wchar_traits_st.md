# LxpLanguageResourcesProvider::_SearchForPackage(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &)

- ea: `0x18004f2c8`
- end: `0x18004f520`
- name: `?_SearchForPackage@LxpLanguageResourcesProvider@@CA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@@Z`
- size: `600`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18004c500`
- `0x18004d440`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180004a44`
- `0x180012a98`
- `0x180034d9c`
- `0x18003771c`
- `0x18004b9c0`
- `0x18004e8ec`
- `0x18004f2c8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004f38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004f38b`
- `ext-ms-win-resources-languageoverlay-l1-1-0!GetLanguageOverlayPackageFamilyName` at `0x18004f33d`
- `ext-ms-win-resources-languageoverlay-l1-1-0!GetLanguageOverlayPackageFamilyName` at `0x18004f33d`

## string_xrefs

- `0x18004f384`: `Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`
- `0x18004f497`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f4af`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f4c7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f4e4`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f4f9`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`
- `0x18004f50e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\lxplanguageresourcesprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall LxpLanguageResourcesProvider::_SearchForPackage(_QWORD *a1, _QWORD *a2)
{
  int LanguageOverlayPackageFamilyName; // eax
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int v8; // eax
  wil::details::in1diag3 *v9; // rcx
  int v10; // eax
  __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  char v19[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[144]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  if ( !(unsigned __int8)IsGetLanguageOverlayPackageFamilyNamePresent() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x236,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)0x80004001LL,
      v16);
  memset_0(v22, 0, 0x82u);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  LanguageOverlayPackageFamilyName = GetLanguageOverlayPackageFamilyName(a2, &qword_180070100, v22, 64);
  if ( LanguageOverlayPackageFamilyName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23C,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)LanguageOverlayPackageFamilyName,
      v16);
  LxpLanguageResourcesProvider::_ConvertPackageFamilyNameToProductID(a1, v22);
  v21 = 0;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.ApplicationModel.Store.Preview.InstallControl.AppInstallManager",
         0x47u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
LABEL_21:
    wil::details::in1diag3::Throw_Hr(
      v9,
      (void *)0x243,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v8,
      v16);
  }
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(
         string,
         &v21);
  v9 = retaddr;
  if ( v8 < 0 )
    goto LABEL_21;
  v20 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v21 + 144LL))(v21, *a1, 0, &v20);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v10,
      v16);
  v19[0] = 1;
  v11 = v20;
  v12 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(v20);
  if ( v12 >= 0 )
    v12 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 64LL))(v11, v19);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24C,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v12,
      v16);
  if ( !v19[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\lxplanguageresourcesprovider.cpp",
      (const char *)0x80070032LL,
      v16);
  v13 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return a1;
}

```

## disassembly

```asm
0x18004f2c8  mov     [rsp-8+arg_10], rbx
0x18004f2cd  push    rbp
0x18004f2ce  push    rsi
0x18004f2cf  push    rdi
0x18004f2d0  lea     rbp, [rsp-20h]
0x18004f2d5  sub     rsp, 120h
0x18004f2dc  mov     rax, cs:__security_cookie
0x18004f2e3  xor     rax, rsp
0x18004f2e6  mov     [rbp+30h+var_20], rax
0x18004f2ea  mov     rbx, rdx
0x18004f2ed  mov     rdi, rcx
0x18004f2f0  mov     [rsp+130h+var_F8], rcx
0x18004f2f5  mov     [rsp+130h+var_100], 0
0x18004f2fd  mov     rsi, [rbp+38h]
0x18004f301  call    IsGetLanguageOverlayPackageFamilyNamePresent
0x18004f306  test    al, al
0x18004f308  jz      loc_18004F4A9
0x18004f30e  xor     edx, edx; Val
0x18004f310  mov     r8d, 82h; Size
0x18004f316  lea     rcx, [rbp+30h+var_B0]; void *
0x18004f31a  call    memset_0
0x18004f31f  cmp     qword ptr [rbx+18h], 7
0x18004f324  jbe     short loc_18004F329
0x18004f326  mov     rbx, [rbx]
0x18004f329  mov     r9d, 40h ; '@'
0x18004f32f  lea     r8, [rbp+30h+var_B0]
0x18004f333  lea     rdx, qword_180070100
0x18004f33a  mov     rcx, rbx
0x18004f33d  call    cs:__imp_GetLanguageOverlayPackageFamilyName
0x18004f343  mov     rcx, [rbp+38h]; this
0x18004f347  test    eax, eax
0x18004f349  js      loc_18004F4C4
0x18004f34f  lea     rdx, [rbp+30h+var_B0]
0x18004f353  mov     rcx, rdi
0x18004f356  call    ?_ConvertPackageFamilyNameToProductID@LxpLanguageResourcesProvider@@CA?AVHString@Wrappers@WRL@Microsoft@@PEBG@Z; LxpLanguageResourcesProvider::_ConvertPackageFamilyNameToProductID(ushort const *)
0x18004f35b  mov     [rsp+130h+var_100], 1
0x18004f363  mov     [rsp+130h+var_C0], 0
0x18004f36c  mov     [rsp+130h+string], 0
0x18004f375  lea     r9, [rsp+130h+string]; string
0x18004f37a  lea     r8, [rsp+130h+hstringHeader]; hstringHeader
0x18004f37f  mov     edx, 47h ; 'G'; length
0x18004f384  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Preview_InstallControl_AppInstallManager@@3QBGB; "Windows.ApplicationModel.Store.Preview."...
0x18004f38b  call    cs:__imp_WindowsCreateStringReference
0x18004f391  test    eax, eax
0x18004f393  js      loc_18004F4D9
0x18004f399  lea     rdx, [rsp+130h+var_C0]
0x18004f39e  mov     rcx, [rsp+130h+string]
0x18004f3a3  call    ??$ActivateInstance@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager>>)
0x18004f3a8  mov     rcx, [rbp+38h]
0x18004f3ac  test    eax, eax
0x18004f3ae  js      loc_18004F4E1
0x18004f3b4  mov     [rsp+130h+var_C8], 0
0x18004f3bd  mov     rcx, [rsp+130h+var_C0]
0x18004f3c2  mov     rax, [rcx]
0x18004f3c5  lea     r9, [rsp+130h+var_C8]
0x18004f3ca  xor     r8d, r8d
0x18004f3cd  mov     rdx, [rdi]
0x18004f3d0  mov     rax, [rax+90h]
0x18004f3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3dc  mov     rcx, [rbp+38h]; this
0x18004f3e0  test    eax, eax
0x18004f3e2  js      loc_18004F4F6
0x18004f3e8  mov     [rsp+130h+var_D0], 1
0x18004f3ed  mov     rbx, [rsp+130h+var_C8]
0x18004f3f2  mov     rcx, rbx
0x18004f3f5  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@_N@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@_N@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<bool> *>(Windows::Foundation::IAsyncOperation<bool> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004f3fa  test    eax, eax
0x18004f3fc  js      short loc_18004F413
0x18004f3fe  mov     rax, [rbx]
0x18004f401  lea     rdx, [rsp+130h+var_D0]
0x18004f406  mov     rcx, rbx
0x18004f409  mov     rax, [rax+40h]
0x18004f40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f412  nop
0x18004f413  mov     rcx, [rbp+38h]; this
0x18004f417  test    eax, eax
0x18004f419  js      loc_18004F50B
0x18004f41f  cmp     [rsp+130h+var_D0], 0
0x18004f424  setz    al
0x18004f427  mov     rcx, [rbp+38h]; this
0x18004f42b  test    al, al
0x18004f42d  jnz     short loc_18004F491
0x18004f42f  mov     rcx, [rsp+130h+var_C8]
0x18004f434  test    rcx, rcx
0x18004f437  jz      short loc_18004F44F
0x18004f439  mov     [rsp+130h+var_C8], 0
0x18004f442  mov     rax, [rcx]
0x18004f445  mov     rax, [rax+10h]
0x18004f449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f44e  nop
0x18004f44f  mov     rcx, [rsp+130h+var_C0]
0x18004f454  test    rcx, rcx
0x18004f457  jz      short loc_18004F46F
0x18004f459  mov     [rsp+130h+var_C0], 0
0x18004f462  mov     rdx, [rcx]
0x18004f465  mov     rax, [rdx+10h]
0x18004f469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f46e  nop
0x18004f46f  mov     rax, rdi
0x18004f472  mov     rcx, [rbp+30h+var_20]
0x18004f476  xor     rcx, rsp; StackCookie
0x18004f479  call    __security_check_cookie
0x18004f47e  mov     rbx, [rsp+130h+arg_10]
0x18004f486  add     rsp, 120h
0x18004f48d  pop     rdi
0x18004f48e  pop     rsi
0x18004f48f  pop     rbp
0x18004f490  retn
0x18004f491  mov     r9d, 80070032h; char *
0x18004f497  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f49e  mov     edx, 24Dh; void *
0x18004f4a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4a9  mov     r9d, 80004001h; char *
0x18004f4af  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f4b6  mov     edx, 236h; void *
0x18004f4bb  mov     rcx, rsi; this
0x18004f4be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4c4  mov     r9d, eax; char *
0x18004f4c7  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f4ce  mov     edx, 23Ch; void *
0x18004f4d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4d9  mov     ecx, eax; this
0x18004f4db  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004f4e0  nop
0x18004f4e1  mov     r9d, eax; char *
0x18004f4e4  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f4eb  mov     edx, 243h; void *
0x18004f4f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f4f6  mov     r9d, eax; char *
0x18004f4f9  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f500  mov     edx, 249h; void *
0x18004f505  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f50b  mov     r9d, eax; char *
0x18004f50e  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\service"...
0x18004f515  mov     edx, 24Ch; void *
0x18004f51a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
