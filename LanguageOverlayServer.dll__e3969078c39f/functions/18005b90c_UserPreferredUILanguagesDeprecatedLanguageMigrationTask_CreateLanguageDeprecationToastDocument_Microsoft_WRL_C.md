# UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_CreateLanguageDeprecationToastDocument(Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument> &)

- ea: `0x18005b90c`
- end: `0x18005bd22`
- name: `?_CreateLanguageDeprecationToastDocument@UserPreferredUILanguagesDeprecatedLanguageMigrationTask@@CAJAEAV?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1046`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005bd28`

## callees

- `0x180003a00`
- `0x180003ea0`
- `0x180005df8`
- `0x180005ee2`
- `0x180009084`
- `0x180009a74`
- `0x1800137bc`
- `0x180014ed0`
- `0x18003771c`
- `0x18005b90c`
- `0x1800633f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b954`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005b954`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005b997`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005ba3b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005b997`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005ba3b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b9f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bcef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005b9f7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005bcef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ba45`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18005bb41`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18005bb41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bb07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bc4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bb07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005bc4d`

## string_xrefs

- `0x18005bb00`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x18005b94d`: `LanguageOverlayServer.dll`
- `0x18005b9c6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005bac8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005bbda`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005bc7b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\deprecatedlanguagemigrationtask.cpp`
- `0x18005ba84`: `<toast launch="ms-settings:regionlanguage" activationType="protocol"><visual><binding template="ToastGeneric"><text>%ls</text><text>%ls</text></binding></visual></toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserPreferredUILanguagesDeprecatedLanguageMigrationTask::_CreateLanguageDeprecationToastDocument(
        _QWORD *a1)
{
  HMODULE Library; // rbx
  WCHAR *v3; // r14
  void *v4; // rsi
  signed int LastError; // eax
  unsigned __int64 v6; // rdx
  signed int v7; // edi
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  signed int v11; // eax
  const unsigned __int16 *v12; // r8
  __int64 v13; // rdx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  HSTRING v17; // rdi
  __int64 (__fastcall ***v18)(_QWORD, GUID *, _QWORD **); // rcx
  int v19; // eax
  unsigned int v20; // r8d
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rdx
  _QWORD *v23; // rdi
  __int64 v24; // r15
  HRESULT v25; // eax
  int v26; // edx
  unsigned int v27; // r8d
  int v28; // eax
  _QWORD *v29; // rcx
  _QWORD *v30; // rcx
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  _QWORD *v35; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v36[4]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h]
  unsigned __int64 v39; // [rsp+70h] [rbp-90h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string[2]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR sourceString[4096]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+20D8h] [rbp+1FD8h]

  Library = LoadLibraryExW(L"LanguageOverlayServer.dll", 0, 0x22u);
  v36[1] = Library;
  v3 = (WCHAR *)operator new[](0x200u);
  v36[2] = v3;
  v4 = operator new[](0x800u);
  v36[3] = v4;
  if ( !LoadStringW(Library, 0x68u, v3, 256) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_7;
    v8 = 187;
    goto LABEL_6;
  }
  if ( !LoadStringW(Library, 0x69u, (LPWSTR)v4, 1024) )
  {
    v11 = GetLastError();
    v7 = v11;
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_7;
    v8 = 188;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v7,
      v33);
LABEL_7:
    operator delete(v4, v6);
    operator delete(v3, v9);
    if ( Library )
      FreeLibrary(Library);
    return (unsigned int)v7;
  }
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    v37,
    L"<toast launch=\"ms-settings:regionlanguage\" activationType=\"protocol\"><visual><binding template=\"ToastGeneric\">"
     "<text>%ls</text><text>%ls</text></binding></visual></toast>",
    169);
  v12 = (const unsigned __int16 *)v37;
  if ( v39 > 7 )
    v12 = v37[0];
  v7 = StringCchPrintfW(sourceString, 0x1000u, v12, v3, v4);
  if ( v7 < 0 )
  {
    v13 = 200;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v7,
      v34);
LABEL_20:
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v37);
    goto LABEL_7;
  }
  string[0] = 0;
  v14 = WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, string);
  if ( v14 < 0 )
    goto LABEL_50;
  v17 = string[0];
  v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))*a1;
  if ( *a1 )
  {
    *a1 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v18)[2])(v18);
  }
  *a1 = 0;
  v36[0] = 0;
  v7 = RoActivateInstance(v17, v36);
  if ( v7 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      *a1 = v36[0];
    }
    else
    {
      v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v36[0])(
             v36[0],
             &GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494,
             a1);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v36[0] + 16LL))(v36[0]);
    }
  }
  if ( v7 < 0 )
  {
    v13 = 201;
    goto LABEL_19;
  }
  v35 = 0;
  v19 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **))*a1)(
          *a1,
          &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637,
          &v35);
  v7 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v19,
      v34);
    v21 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    goto LABEL_20;
  }
  v22 = -1;
  do
    ++v22;
  while ( sourceString[v22] );
  if ( v22 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v20);
LABEL_50:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
    goto LABEL_51;
  }
  if ( (int)v22 + 1 < (unsigned int)v22 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v22, v20);
    __debugbreak();
  }
  v23 = v35;
  v24 = *v35;
  v25 = WindowsCreateStringReference(sourceString, v22, &hstringHeader, string);
  if ( v25 < 0 )
  {
LABEL_51:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v25, v26, v27);
    JUMPOUT(0x18005BD21LL);
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING))(v24 + 48))(v23, string[0]);
  v7 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\deprecatedlanguagemigrationtask.cpp",
      (const char *)(unsigned int)v28,
      v34);
    v29 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    goto LABEL_20;
  }
  v30 = v35;
  if ( v35 )
  {
    v35 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  }
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v37);
  operator delete(v4, v31);
  operator delete(v3, v32);
  if ( Library )
    FreeLibrary(Library);
  return 0;
}

```

## disassembly

```asm
0x18005b90c  mov     [rsp-8+arg_8], rbx
0x18005b911  mov     [rsp-8+arg_10], rsi
0x18005b916  push    rbp
0x18005b917  push    rdi
0x18005b918  push    r12
0x18005b91a  push    r14
0x18005b91c  push    r15
0x18005b91e  lea     rbp, [rsp-1FB0h]
0x18005b926  mov     eax, 20B0h
0x18005b92b  call    _alloca_probe
0x18005b930  sub     rsp, rax
0x18005b933  mov     rax, cs:__security_cookie
0x18005b93a  xor     rax, rsp
0x18005b93d  mov     [rbp+1FD0h+var_30], rax
0x18005b944  mov     r15, rcx
0x18005b947  xor     edx, edx; hFile
0x18005b949  lea     r8d, [rdx+22h]; dwFlags
0x18005b94d  lea     rcx, aLanguageoverla_0; "LanguageOverlayServer.dll"
0x18005b954  call    cs:__imp_LoadLibraryExW
0x18005b95a  mov     rbx, rax
0x18005b95d  mov     [rsp+20D0h+var_2090], rax
0x18005b962  mov     ecx, 200h; unsigned __int64
0x18005b967  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005b96c  mov     r14, rax
0x18005b96f  mov     [rsp+20D0h+var_2088], rax
0x18005b974  mov     ecx, 800h; unsigned __int64
0x18005b979  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005b97e  mov     rsi, rax
0x18005b981  mov     [rsp+20D0h+var_2080], rax
0x18005b986  mov     r9d, 100h; cchBufferMax
0x18005b98c  mov     r8, r14; lpBuffer
0x18005b98f  mov     edx, 68h ; 'h'; uID
0x18005b994  mov     rcx, rbx; hInstance
0x18005b997  call    cs:__imp_LoadStringW
0x18005b99d  xor     r12d, r12d
0x18005b9a0  test    eax, eax
0x18005b9a2  jnz     loc_18005BA2A
0x18005b9a8  call    cs:__imp_GetLastError
0x18005b9ae  mov     edi, eax
0x18005b9b0  test    eax, eax
0x18005b9b2  jle     short loc_18005B9BD
0x18005b9b4  movzx   edi, ax
0x18005b9b7  or      edi, 80070000h
0x18005b9bd  test    edi, edi
0x18005b9bf  jns     short loc_18005B9DD
0x18005b9c1  mov     edx, 0BBh; void *
0x18005b9c6  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005b9cd  mov     r9d, edi; char *
0x18005b9d0  mov     rcx, [rbp+1FD8h]; this
0x18005b9d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b9dc  nop
0x18005b9dd  mov     rcx, rsi; void *
0x18005b9e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b9e5  nop
0x18005b9e6  mov     rcx, r14; void *
0x18005b9e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005b9ee  nop
0x18005b9ef  test    rbx, rbx
0x18005b9f2  jz      short loc_18005B9FD
0x18005b9f4  mov     rcx, rbx; hLibModule
0x18005b9f7  call    cs:__imp_FreeLibrary
0x18005b9fd  mov     eax, edi
0x18005b9ff  mov     rcx, [rbp+1FD0h+var_30]
0x18005ba06  xor     rcx, rsp; StackCookie
0x18005ba09  call    __security_check_cookie
0x18005ba0e  lea     r11, [rsp+20D0h+var_20]
0x18005ba16  mov     rbx, [r11+38h]
0x18005ba1a  mov     rsi, [r11+40h]
0x18005ba1e  mov     rsp, r11
0x18005ba21  pop     r15
0x18005ba23  pop     r14
0x18005ba25  pop     r12
0x18005ba27  pop     rdi
0x18005ba28  pop     rbp
0x18005ba29  retn
0x18005ba2a  mov     r9d, 400h; cchBufferMax
0x18005ba30  mov     r8, rsi; lpBuffer
0x18005ba33  mov     edx, 69h ; 'i'; uID
0x18005ba38  mov     rcx, rbx; hInstance
0x18005ba3b  call    cs:__imp_LoadStringW
0x18005ba41  test    eax, eax
0x18005ba43  jnz     short loc_18005BA6C
0x18005ba45  call    cs:__imp_GetLastError
0x18005ba4b  mov     edi, eax
0x18005ba4d  test    eax, eax
0x18005ba4f  jle     short loc_18005BA5A
0x18005ba51  movzx   edi, ax
0x18005ba54  or      edi, 80070000h
0x18005ba5a  test    edi, edi
0x18005ba5c  jns     loc_18005B9DD
0x18005ba62  mov     edx, 0BCh
0x18005ba67  jmp     loc_18005B9C6
0x18005ba6c  xorps   xmm0, xmm0
0x18005ba6f  movups  xmmword ptr [rsp+20D0h+var_2078], xmm0
0x18005ba74  mov     [rsp+20D0h+var_2068], r12
0x18005ba79  mov     [rsp+20D0h+var_2060], r12
0x18005ba7e  mov     r8d, 0A9h
0x18005ba84  lea     rdx, aToastLaunchMsS; "<toast launch=\"ms-settings:regionlangu"...
0x18005ba8b  lea     rcx, [rsp+20D0h+var_2078]
0x18005ba90  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005ba95  nop
0x18005ba96  lea     r8, [rsp+20D0h+var_2078]
0x18005ba9b  cmp     [rsp+20D0h+var_2060], 7
0x18005baa1  cmova   r8, [rsp+20D0h+var_2078]; unsigned __int16 *
0x18005baa7  mov     qword ptr [rsp+20D0h+var_20B0], rsi; int
0x18005baac  mov     r9, r14
0x18005baaf  mov     edx, 1000h; unsigned __int64
0x18005bab4  lea     rcx, [rbp+1FD0h+sourceString]; unsigned __int16 *
0x18005bab8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005babd  mov     edi, eax
0x18005babf  test    eax, eax
0x18005bac1  jns     short loc_18005BAEE
0x18005bac3  mov     edx, 0C8h; void *
0x18005bac8  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005bacf  mov     r9d, edi; char *
0x18005bad2  mov     rcx, [rbp+1FD8h]; this
0x18005bad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bade  nop
0x18005badf  lea     rcx, [rsp+20D0h+var_2078]; void *
0x18005bae4  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005bae9  jmp     loc_18005B9DD
0x18005baee  mov     [rbp+1FD0h+string], r12
0x18005baf2  lea     r9, [rbp+1FD0h+string]; string
0x18005baf6  lea     r8, [rsp+20D0h+hstringHeader]; hstringHeader
0x18005bafb  mov     edx, 20h ; ' '; length
0x18005bb00  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x18005bb07  call    cs:__imp_WindowsCreateStringReference
0x18005bb0d  test    eax, eax
0x18005bb0f  js      loc_18005BD12
0x18005bb15  mov     rdi, [rbp+1FD0h+string]
0x18005bb19  mov     rcx, [r15]
0x18005bb1c  test    rcx, rcx
0x18005bb1f  jz      short loc_18005BB31
0x18005bb21  mov     [r15], r12
0x18005bb24  mov     rax, [rcx]
0x18005bb27  mov     rax, [rax+10h]
0x18005bb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb30  nop
0x18005bb31  mov     [r15], r12
0x18005bb34  mov     [rsp+20D0h+var_2098], r12
0x18005bb39  lea     rdx, [rsp+20D0h+var_2098]
0x18005bb3e  mov     rcx, rdi
0x18005bb41  call    cs:__imp_RoActivateInstance
0x18005bb47  mov     edi, eax
0x18005bb49  test    eax, eax
0x18005bb4b  js      short loc_18005BB9D
0x18005bb4d  mov     r8d, 10h; Size
0x18005bb53  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18005bb5a  lea     rcx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494; Buf1
0x18005bb61  call    memcmp_0
0x18005bb66  mov     rcx, [rsp+20D0h+var_2098]
0x18005bb6b  test    eax, eax
0x18005bb6d  jnz     short loc_18005BB74
0x18005bb6f  mov     [r15], rcx
0x18005bb72  jmp     short loc_18005BB9D
0x18005bb74  mov     rax, [rcx]
0x18005bb77  mov     r8, r15
0x18005bb7a  lea     rdx, _GUID_f7f3a506_1e87_42d6_bcfb_b8c809fa5494
0x18005bb81  mov     rax, [rax]
0x18005bb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb89  mov     edi, eax
0x18005bb8b  mov     rcx, [rsp+20D0h+var_2098]
0x18005bb90  mov     rax, [rcx]
0x18005bb93  mov     rax, [rax+10h]
0x18005bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb9c  nop
0x18005bb9d  test    edi, edi
0x18005bb9f  jns     short loc_18005BBAB
0x18005bba1  mov     edx, 0C9h
0x18005bba6  jmp     loc_18005BAC8
0x18005bbab  mov     [rsp+20D0h+var_20A0], r12
0x18005bbb0  mov     rcx, [r15]
0x18005bbb3  mov     rax, [rcx]
0x18005bbb6  lea     r8, [rsp+20D0h+var_20A0]
0x18005bbbb  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x18005bbc2  mov     rax, [rax]
0x18005bbc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbca  mov     edi, eax
0x18005bbcc  test    eax, eax
0x18005bbce  jns     short loc_18005BC0D
0x18005bbd0  mov     rcx, [rbp+1FD8h]; this
0x18005bbd7  mov     r9d, eax; char *
0x18005bbda  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005bbe1  mov     edx, 0CCh; void *
0x18005bbe6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bbeb  nop
0x18005bbec  mov     rcx, [rsp+20D0h+var_20A0]
0x18005bbf1  test    rcx, rcx
0x18005bbf4  jz      short loc_18005BC08
0x18005bbf6  mov     [rsp+20D0h+var_20A0], r12
0x18005bbfb  mov     rax, [rcx]
0x18005bbfe  mov     rax, [rax+10h]
0x18005bc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc07  nop
0x18005bc08  jmp     loc_18005BADF
0x18005bc0d  lea     rax, [rbp+1FD0h+sourceString]
0x18005bc11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005bc15  inc     rdx; int
0x18005bc18  cmp     [rax+rdx*2], r12w
0x18005bc1d  jnz     short loc_18005BC15
0x18005bc1f  mov     eax, 0FFFFFFFFh
0x18005bc24  cmp     rdx, rax
0x18005bc27  ja      loc_18005BD07
0x18005bc2d  lea     eax, [rdx+1]
0x18005bc30  cmp     eax, edx
0x18005bc32  jb      loc_18005BCFC
0x18005bc38  mov     rdi, [rsp+20D0h+var_20A0]
0x18005bc3d  mov     r15, [rdi]
0x18005bc40  lea     r9, [rbp+1FD0h+string]; string
0x18005bc44  lea     r8, [rsp+20D0h+hstringHeader]; hstringHeader
0x18005bc49  lea     rcx, [rbp+1FD0h+sourceString]; sourceString
0x18005bc4d  call    cs:__imp_WindowsCreateStringReference
0x18005bc53  test    eax, eax
0x18005bc55  js      loc_18005BD1A
0x18005bc5b  mov     rdx, [rbp+1FD0h+string]
0x18005bc5f  mov     rcx, rdi
0x18005bc62  mov     rax, [r15+30h]
0x18005bc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc6b  mov     edi, eax
0x18005bc6d  test    eax, eax
0x18005bc6f  jns     short loc_18005BCAE
0x18005bc71  mov     rcx, [rbp+1FD8h]; this
0x18005bc78  mov     r9d, eax; char *
0x18005bc7b  lea     r8, aOnecoreBaseLan_30; "onecore\\base\\languageoverlay\\service"...
0x18005bc82  mov     edx, 0CDh; void *
0x18005bc87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005bc8c  nop
0x18005bc8d  mov     rcx, [rsp+20D0h+var_20A0]
0x18005bc92  test    rcx, rcx
0x18005bc95  jz      short loc_18005BCA9
0x18005bc97  mov     [rsp+20D0h+var_20A0], r12
0x18005bc9c  mov     rax, [rcx]
0x18005bc9f  mov     rax, [rax+10h]
0x18005bca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bca8  nop
0x18005bca9  jmp     loc_18005BADF
0x18005bcae  mov     rcx, [rsp+20D0h+var_20A0]
0x18005bcb3  test    rcx, rcx
0x18005bcb6  jz      short loc_18005BCCA
0x18005bcb8  mov     [rsp+20D0h+var_20A0], r12
0x18005bcbd  mov     rax, [rcx]
0x18005bcc0  mov     rax, [rax+10h]
0x18005bcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcc9  nop
0x18005bcca  lea     rcx, [rsp+20D0h+var_2078]; void *
0x18005bccf  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x18005bcd4  nop
0x18005bcd5  mov     rcx, rsi; void *
0x18005bcd8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005bcdd  nop
0x18005bcde  mov     rcx, r14; void *
0x18005bce1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005bce6  nop
0x18005bce7  test    rbx, rbx
0x18005bcea  jz      short loc_18005BCF5
0x18005bcec  mov     rcx, rbx; hLibModule
0x18005bcef  call    cs:__imp_FreeLibrary
0x18005bcf5  xor     eax, eax
0x18005bcf7  jmp     loc_18005B9FF
0x18005bcfc  mov     ecx, 80070216h; this
0x18005bd01  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18005bd06  int     3; Trap to Debugger
0x18005bd07  mov     ecx, 80070216h; this
0x18005bd0c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18005bd11  nop
0x18005bd12  mov     ecx, eax; this
0x18005bd14  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18005bd19  nop
0x18005bd1a  mov     ecx, eax; this
0x18005bd1c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
