# UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_DisplayLanguageDeprecationToast(void)

- ea: `0x18005bd28`
- end: `0x18005c21d`
- name: `?_DisplayLanguageDeprecationToast@UserPreferredUILanguagesDeprecatedLanguageMigrationTask@@CAJXZ`
- size: `1269`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005c80c`

## callees

- `0x180003a00`
- `0x180009084`
- `0x18003771c`
- `0x18005b90c`
- `0x18005bd28`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bde7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005be9b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005bde7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005be9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005be61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bfe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bdad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005be61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bfe2`

## string_xrefs

- `0x18005bd5e`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005bdfa`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005beae`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005bf40`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005c015`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005c0d3`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_DisplayLanguageDeprecationToast(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rcx
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  HSTRING v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  _QWORD *v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rbx
  __int64 v25; // rdi
  HRESULT v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  _QWORD *v33; // rcx
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  _QWORD *v44; // rcx
  __int64 v45; // rcx
  _QWORD *v46; // [rsp+20h] [rbp-58h] BYREF
  __int64 v47; // [rsp+28h] [rbp-50h] BYREF
  __int64 v48; // [rsp+30h] [rbp-48h] BYREF
  __int64 v49; // [rsp+38h] [rbp-40h] BYREF
  __int64 v50; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v47 = 0;
  v0 = UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_CreateLanguageDeprecationToastDocument(&v47);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v0,
      (int)v46);
    v2 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    }
    return v1;
  }
  v46 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.UI.Notifications.ToastNotificationManager",
         0x31u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
    goto LABEL_70;
  ActivationFactory = RoGetActivationFactory(string, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v46);
  v1 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v46);
    v8 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    v9 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v1;
  }
  v48 = 0;
  string = 0;
  v10 = WindowsCreateStringReference(L"Windows.UI.Notifications.ToastNotification", 0x2Au, &hstringHeader, &string);
  if ( v10 < 0 )
  {
LABEL_71:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
    JUMPOUT(0x18005C21CLL);
  }
  v13 = string;
  v14 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = RoGetActivationFactory(v13, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v48);
  v1 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v15,
      (int)v46);
    v16 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v17 + 16LL))(v17);
    }
    v18 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v1;
  }
  v49 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v48 + 48LL))(v48, v47, &v49);
  v1 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v19,
      (int)v46);
    v20 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
    }
    v23 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v1;
  }
  v50 = 0;
  v24 = v46;
  v25 = *v46;
  string = 0;
  v26 = WindowsCreateStringReference(L"Windows.SystemToast.LanguageSettings", 0x24u, &hstringHeader, &string);
  if ( v26 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
LABEL_70:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    goto LABEL_71;
  }
  v29 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v25 + 56))(v24, string, &v50);
  v1 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v30 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v32 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
    }
    v34 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    return v1;
  }
  v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 48LL))(v50, v49);
  v1 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v35,
      (int)v46);
    v36 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    v37 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    v39 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
    }
    v40 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v1;
  }
  v41 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
  }
  v45 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  return 0;
}

```

## disassembly

```asm
0x18005bd28  push    rbp
0x18005bd2a  push    rbx
0x18005bd2b  push    rsi
0x18005bd2c  push    rdi
0x18005bd2d  mov     rbp, rsp
0x18005bd30  sub     rsp, 78h
0x18005bd34  mov     rax, cs:__security_cookie
0x18005bd3b  xor     rax, rsp
0x18005bd3e  mov     [rbp+var_10], rax
0x18005bd42  xor     esi, esi
0x18005bd44  mov     [rbp+var_50], rsi
0x18005bd48  lea     rcx, [rbp+var_50]
0x18005bd4c  call    ?_CreateLanguageDeprecationToastDocument@UserPreferredUILanguagesDeprecatedLanguageMigrationTask@@CAJAEAV?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Z; UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_CreateLanguageDeprecationToastDocument(Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument> &)
0x18005bd51  mov     ebx, eax
0x18005bd53  test    eax, eax
0x18005bd55  jns     short loc_18005BD91
0x18005bd57  mov     rcx, [rbp+20h]; this
0x18005bd5b  mov     r9d, eax; char *
0x18005bd5e  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005bd65  mov     edx, 9Ch; void *
0x18005bd6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bd6f  nop
0x18005bd70  mov     rcx, [rbp+var_50]
0x18005bd74  test    rcx, rcx
0x18005bd77  jz      short loc_18005BD8A
0x18005bd79  mov     [rbp+var_50], rsi
0x18005bd7d  mov     rax, [rcx]
0x18005bd80  mov     rax, [rax+10h]
0x18005bd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd89  nop
0x18005bd8a  mov     eax, ebx
0x18005bd8c  jmp     loc_18005C1F0
0x18005bd91  mov     [rbp+var_58], rsi
0x18005bd95  mov     [rbp+string], rsi
0x18005bd99  lea     r9, [rbp+string]; string
0x18005bd9d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005bda1  mov     edx, 31h ; '1'; length
0x18005bda6  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x18005bdad  call    cs:__imp_WindowsCreateStringReference
0x18005bdb3  test    eax, eax
0x18005bdb5  js      loc_18005C20D
0x18005bdbb  mov     rbx, [rbp+string]
0x18005bdbf  mov     rcx, [rbp+var_58]
0x18005bdc3  test    rcx, rcx
0x18005bdc6  jz      short loc_18005BDD9
0x18005bdc8  mov     [rbp+var_58], rsi
0x18005bdcc  mov     rax, [rcx]
0x18005bdcf  mov     rax, [rax+10h]
0x18005bdd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdd8  nop
0x18005bdd9  lea     r8, [rbp+var_58]
0x18005bddd  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x18005bde4  mov     rcx, rbx
0x18005bde7  call    cs:__imp_RoGetActivationFactory
0x18005bded  mov     ebx, eax
0x18005bdef  test    eax, eax
0x18005bdf1  jns     short loc_18005BE45
0x18005bdf3  mov     rcx, [rbp+20h]; this
0x18005bdf7  mov     r9d, eax; char *
0x18005bdfa  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005be01  mov     edx, 0A1h; void *
0x18005be06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005be0b  nop
0x18005be0c  mov     rcx, [rbp+var_58]
0x18005be10  test    rcx, rcx
0x18005be13  jz      short loc_18005BE26
0x18005be15  mov     [rbp+var_58], rsi
0x18005be19  mov     rax, [rcx]
0x18005be1c  mov     rax, [rax+10h]
0x18005be20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be25  nop
0x18005be26  mov     rcx, [rbp+var_50]
0x18005be2a  test    rcx, rcx
0x18005be2d  jz      short loc_18005BE40
0x18005be2f  mov     [rbp+var_50], rsi
0x18005be33  mov     rax, [rcx]
0x18005be36  mov     rax, [rax+10h]
0x18005be3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be3f  nop
0x18005be40  jmp     loc_18005BD8A
0x18005be45  mov     [rbp+var_48], rsi
0x18005be49  mov     [rbp+string], rsi
0x18005be4d  lea     r9, [rbp+string]; string
0x18005be51  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005be55  mov     edx, 2Ah ; '*'; length
0x18005be5a  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotification@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x18005be61  call    cs:__imp_WindowsCreateStringReference
0x18005be67  test    eax, eax
0x18005be69  js      loc_18005C215
0x18005be6f  mov     rbx, [rbp+string]
0x18005be73  mov     rcx, [rbp+var_48]
0x18005be77  test    rcx, rcx
0x18005be7a  jz      short loc_18005BE8D
0x18005be7c  mov     [rbp+var_48], rsi
0x18005be80  mov     rax, [rcx]
0x18005be83  mov     rax, [rax+10h]
0x18005be87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be8c  nop
0x18005be8d  lea     r8, [rbp+var_48]
0x18005be91  lea     rdx, _GUID_04124b20_82c6_4229_b109_fd9ed4662b53
0x18005be98  mov     rcx, rbx
0x18005be9b  call    cs:__imp_RoGetActivationFactory
0x18005bea1  mov     ebx, eax
0x18005bea3  test    eax, eax
0x18005bea5  jns     short loc_18005BF13
0x18005bea7  mov     rcx, [rbp+20h]; this
0x18005beab  mov     r9d, eax; char *
0x18005beae  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005beb5  mov     edx, 0A6h; void *
0x18005beba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bebf  nop
0x18005bec0  mov     rcx, [rbp+var_48]
0x18005bec4  test    rcx, rcx
0x18005bec7  jz      short loc_18005BEDA
0x18005bec9  mov     [rbp+var_48], rsi
0x18005becd  mov     rax, [rcx]
0x18005bed0  mov     rax, [rax+10h]
0x18005bed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bed9  nop
0x18005beda  mov     rcx, [rbp+var_58]
0x18005bede  test    rcx, rcx
0x18005bee1  jz      short loc_18005BEF4
0x18005bee3  mov     [rbp+var_58], rsi
0x18005bee7  mov     rax, [rcx]
0x18005beea  mov     rax, [rax+10h]
0x18005beee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bef3  nop
0x18005bef4  mov     rcx, [rbp+var_50]
0x18005bef8  test    rcx, rcx
0x18005befb  jz      short loc_18005BF0E
0x18005befd  mov     [rbp+var_50], rsi
0x18005bf01  mov     rax, [rcx]
0x18005bf04  mov     rax, [rax+10h]
0x18005bf08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf0d  nop
0x18005bf0e  jmp     loc_18005BD8A
0x18005bf13  mov     [rbp+var_40], rsi
0x18005bf17  mov     rcx, [rbp+var_48]
0x18005bf1b  mov     rax, [rcx]
0x18005bf1e  lea     r8, [rbp+var_40]
0x18005bf22  mov     rdx, [rbp+var_50]
0x18005bf26  mov     rax, [rax+30h]
0x18005bf2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf2f  mov     ebx, eax
0x18005bf31  test    eax, eax
0x18005bf33  jns     loc_18005BFBF
0x18005bf39  mov     rcx, [rbp+20h]; this
0x18005bf3d  mov     r9d, eax; char *
0x18005bf40  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005bf47  mov     edx, 0A9h; void *
0x18005bf4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bf51  nop
0x18005bf52  mov     rcx, [rbp+var_40]
0x18005bf56  test    rcx, rcx
0x18005bf59  jz      short loc_18005BF6C
0x18005bf5b  mov     [rbp+var_40], rsi
0x18005bf5f  mov     rax, [rcx]
0x18005bf62  mov     rax, [rax+10h]
0x18005bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf6b  nop
0x18005bf6c  mov     rcx, [rbp+var_48]
0x18005bf70  test    rcx, rcx
0x18005bf73  jz      short loc_18005BF86
0x18005bf75  mov     [rbp+var_48], rsi
0x18005bf79  mov     rax, [rcx]
0x18005bf7c  mov     rax, [rax+10h]
0x18005bf80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf85  nop
0x18005bf86  mov     rcx, [rbp+var_58]
0x18005bf8a  test    rcx, rcx
0x18005bf8d  jz      short loc_18005BFA0
0x18005bf8f  mov     [rbp+var_58], rsi
0x18005bf93  mov     rax, [rcx]
0x18005bf96  mov     rax, [rax+10h]
0x18005bf9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf9f  nop
0x18005bfa0  mov     rcx, [rbp+var_50]
0x18005bfa4  test    rcx, rcx
0x18005bfa7  jz      short loc_18005BFBA
0x18005bfa9  mov     [rbp+var_50], rsi
0x18005bfad  mov     rax, [rcx]
0x18005bfb0  mov     rax, [rax+10h]
0x18005bfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfb9  nop
0x18005bfba  jmp     loc_18005BD8A
0x18005bfbf  mov     [rbp+var_38], rsi
0x18005bfc3  mov     rbx, [rbp+var_58]
0x18005bfc7  mov     rdi, [rbx]
0x18005bfca  mov     [rbp+string], rsi
0x18005bfce  lea     r9, [rbp+string]; string
0x18005bfd2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005bfd6  mov     edx, 24h ; '$'; length
0x18005bfdb  lea     rcx, aWindowsSystemt; "Windows.SystemToast.LanguageSettings"
0x18005bfe2  call    cs:__imp_WindowsCreateStringReference
0x18005bfe8  test    eax, eax
0x18005bfea  js      loc_18005C205
0x18005bff0  lea     r8, [rbp+var_38]
0x18005bff4  mov     rdx, [rbp+string]
0x18005bff8  mov     rcx, rbx
0x18005bffb  mov     rax, [rdi+38h]
0x18005bfff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c004  mov     ebx, eax
0x18005c006  test    eax, eax
0x18005c008  jns     loc_18005C0AE
0x18005c00e  mov     rcx, [rbp+20h]; this
0x18005c012  mov     r9d, eax; char *
0x18005c015  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005c01c  mov     edx, 0ACh; void *
0x18005c021  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c026  nop
0x18005c027  mov     rcx, [rbp+var_38]
0x18005c02b  test    rcx, rcx
0x18005c02e  jz      short loc_18005C041
0x18005c030  mov     [rbp+var_38], rsi
0x18005c034  mov     rax, [rcx]
0x18005c037  mov     rax, [rax+10h]
0x18005c03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c040  nop
0x18005c041  mov     rcx, [rbp+var_40]
0x18005c045  test    rcx, rcx
0x18005c048  jz      short loc_18005C05B
0x18005c04a  mov     [rbp+var_40], rsi
0x18005c04e  mov     rax, [rcx]
0x18005c051  mov     rax, [rax+10h]
0x18005c055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c05a  nop
0x18005c05b  mov     rcx, [rbp+var_48]
0x18005c05f  test    rcx, rcx
0x18005c062  jz      short loc_18005C075
0x18005c064  mov     [rbp+var_48], rsi
0x18005c068  mov     rax, [rcx]
0x18005c06b  mov     rax, [rax+10h]
0x18005c06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c074  nop
0x18005c075  mov     rcx, [rbp+var_58]
0x18005c079  test    rcx, rcx
0x18005c07c  jz      short loc_18005C08F
0x18005c07e  mov     [rbp+var_58], rsi
0x18005c082  mov     rax, [rcx]
0x18005c085  mov     rax, [rax+10h]
0x18005c089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c08e  nop
0x18005c08f  mov     rcx, [rbp+var_50]
0x18005c093  test    rcx, rcx
0x18005c096  jz      short loc_18005C0A9
0x18005c098  mov     [rbp+var_50], rsi
0x18005c09c  mov     rax, [rcx]
0x18005c09f  mov     rax, [rax+10h]
0x18005c0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0a8  nop
0x18005c0a9  jmp     loc_18005BD8A
0x18005c0ae  mov     rcx, [rbp+var_38]
0x18005c0b2  mov     rax, [rcx]
0x18005c0b5  mov     rdx, [rbp+var_40]
0x18005c0b9  mov     rax, [rax+30h]
0x18005c0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0c2  mov     ebx, eax
0x18005c0c4  test    eax, eax
0x18005c0c6  jns     loc_18005C16C
0x18005c0cc  mov     rcx, [rbp+20h]; this
0x18005c0d0  mov     r9d, eax; char *
0x18005c0d3  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005c0da  mov     edx, 0ADh; void *
0x18005c0df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c0e4  nop
0x18005c0e5  mov     rcx, [rbp+var_38]
0x18005c0e9  test    rcx, rcx
0x18005c0ec  jz      short loc_18005C0FF
0x18005c0ee  mov     [rbp+var_38], rsi
0x18005c0f2  mov     rax, [rcx]
0x18005c0f5  mov     rax, [rax+10h]
0x18005c0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0fe  nop
0x18005c0ff  mov     rcx, [rbp+var_40]
0x18005c103  test    rcx, rcx
0x18005c106  jz      short loc_18005C119
0x18005c108  mov     [rbp+var_40], rsi
0x18005c10c  mov     rax, [rcx]
0x18005c10f  mov     rax, [rax+10h]
0x18005c113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c118  nop
0x18005c119  mov     rcx, [rbp+var_48]
0x18005c11d  test    rcx, rcx
0x18005c120  jz      short loc_18005C133
0x18005c122  mov     [rbp+var_48], rsi
0x18005c126  mov     rax, [rcx]
0x18005c129  mov     rax, [rax+10h]
0x18005c12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c132  nop
0x18005c133  mov     rcx, [rbp+var_58]
0x18005c137  test    rcx, rcx
0x18005c13a  jz      short loc_18005C14D
0x18005c13c  mov     [rbp+var_58], rsi
0x18005c140  mov     rax, [rcx]
0x18005c143  mov     rax, [rax+10h]
0x18005c147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c14c  nop
0x18005c14d  mov     rcx, [rbp+var_50]
0x18005c151  test    rcx, rcx
0x18005c154  jz      short loc_18005C167
  ... truncated ...
```
