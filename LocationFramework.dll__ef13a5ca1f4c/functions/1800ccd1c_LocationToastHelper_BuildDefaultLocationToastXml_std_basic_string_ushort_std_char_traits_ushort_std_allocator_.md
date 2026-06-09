# LocationToastHelper::BuildDefaultLocationToastXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800ccd1c`
- end: `0x1800cd041`
- name: `?BuildDefaultLocationToastXml@LocationToastHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `805`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cdff4`

## callees

- `0x18000f040`
- `0x18002085c`
- `0x180020994`
- `0x180020c64`
- `0x18005c458`
- `0x180060988`
- `0x180084ac8`
- `0x18008f888`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800cbf58`
- `0x1800ccd1c`
- `0x1800cd838`
- `0x1800d0160`
- `0x1800eec10`
- `0x180152970`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ccf76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ccfc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ccf76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800ccfc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ccd67`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ccf49`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ccd67`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ccf49`

## string_xrefs

- `0x1800ccd60`: `LocationFramework.dll`
- `0x1800ccf42`: `LocationFramework.dll`
- `0x1800cce42`: `<toast launch="ms-settings:privacy-location" activationType="protocol"><visual><binding template="ToastGeneric"><text id="1">{}</text><text id="2">{}</text></binding></visual></toast>`
- `0x1800ccf93`: `LocationToastHelper::BuildDefaultLocationToastXml`
- `0x1800ccff0`: `<toast launch="ms-settings:privacy-location" activationType="protocol"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall LocationToastHelper::BuildDefaultLocationToastXml(__int64 a1)
{
  HMODULE Library; // rax
  wil::details *v3; // rcx
  HMODULE v4; // rbx
  unsigned int LastErrorFailHr; // ebx
  __int64 result; // rax
  __int64 StringDynamic; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  HMODULE v11; // rax
  wil::details *v12; // rcx
  HINSTANCE v13; // rbx
  const char *v14; // rax
  __int64 v15; // rdx
  const char *v16; // [rsp+28h] [rbp-1500h]
  _QWORD v17[2]; // [rsp+30h] [rbp-14F8h] BYREF
  const wchar_t *v18; // [rsp+40h] [rbp-14E8h] BYREF
  __int64 v19; // [rsp+48h] [rbp-14E0h]
  _BYTE v20[32]; // [rsp+50h] [rbp-14D8h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-14B8h] BYREF
  _BYTE v22[16]; // [rsp+90h] [rbp-1498h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-1488h]
  _BYTE v24[16]; // [rsp+B0h] [rbp-1478h] BYREF
  __int64 v25; // [rsp+C0h] [rbp-1468h]
  _BYTE v26[32]; // [rsp+D0h] [rbp-1458h] BYREF
  WCHAR v27[264]; // [rsp+F0h] [rbp-1438h] BYREF
  WCHAR Buffer[264]; // [rsp+300h] [rbp-1228h] BYREF
  unsigned __int16 v29[2048]; // [rsp+510h] [rbp-1018h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1528h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::GetImpl'::`2'::impl) )
  {
    Library = LoadLibraryExW(L"LocationFramework.dll", 0, 0x802u);
    v4 = Library;
    v17[0] = Library;
    if ( !Library )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v17);
      return LastErrorFailHr;
    }
    StringDynamic = LocationToastHelper::LoadStringDynamic(v20, Library, 200);
    v18 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(StringDynamic, StringDynamic);
    v19 = *(_QWORD *)(v8 + 16);
    LSUtility::XmlEscape(v24, &v18);
    std::wstring::_Tidy_deallocate(v20);
    v9 = LocationToastHelper::LoadStringDynamic(v21, v4, 201);
    v18 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9, v9);
    v19 = *(_QWORD *)(v10 + 16);
    LSUtility::XmlEscape(v22, &v18);
    std::wstring::_Tidy_deallocate(v21);
    if ( !v25 || !v23 )
    {
      std::wstring::_Tidy_deallocate(v22);
      std::wstring::_Tidy_deallocate(v24);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v17);
      return 2147944212LL;
    }
    v18 = L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\"><visual><binding template=\"ToastGe"
           "neric\"><text id=\"1\">{}</text><text id=\"2\">{}</text></binding></visual></toast>";
    v19 = 183;
    std::format<std::wstring const &,std::wstring const &>(v26, &v18, v24, v22);
    std::wstring::append(a1, v26);
    std::wstring::_Tidy_deallocate(v26);
    std::wstring::_Tidy_deallocate(v22);
    std::wstring::_Tidy_deallocate(v24);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v17);
    return 0;
  }
  memset_0(v29, 0, sizeof(v29));
  memset_0(Buffer, 0, 0x208u);
  memset_0(v27, 0, 0x208u);
  v11 = LoadLibraryExW(L"LocationFramework.dll", 0, 2u);
  v13 = v11;
  if ( !v11 )
    return wil::details::GetLastErrorFailHr(v12);
  if ( !LoadStringW(v11, 0xC8u, Buffer, 260) )
  {
    v14 = "0 == LoadString(instRes, IDS_LOC_DEFAULTLOCATION_TOAST_TITLE, title, ARRAYSIZE(title))";
    v15 = 190;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v15,
             (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\LocationToastHelper.h",
             "LocationToastHelper::BuildDefaultLocationToastXml",
             v14,
             v16);
  }
  if ( !LoadStringW(v13, 0xC9u, v27, 260) )
  {
    v14 = "0 == LoadString(instRes, IDS_LOC_DEFAULTLOCATION_TOAST_BODY, body, ARRAYSIZE(body))";
    v15 = 191;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v15,
             (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\LocationToastHelper.h",
             "LocationToastHelper::BuildDefaultLocationToastXml",
             v14,
             v16);
  }
  result = StringCchPrintfW(
             v29,
             0x800u,
             L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\"><visual><binding template=\"Toas"
              "tGeneric\"><text id=\"1\">%s</text><text id=\"2\">%s</text></binding></visual></toast>",
             Buffer,
             v27);
  if ( (int)result < 0 )
    return result;
  std::wstring::append(a1, v29);
  return 0;
}

```

## disassembly

```asm
0x1800ccd1c  mov     [rsp+arg_8], rbx
0x1800ccd21  push    rdi
0x1800ccd22  mov     eax, 1520h
0x1800ccd27  call    _alloca_probe
0x1800ccd2c  sub     rsp, rax
0x1800ccd2f  mov     rax, cs:__security_cookie
0x1800ccd36  xor     rax, rsp
0x1800ccd39  mov     [rsp+1528h+var_18], rax
0x1800ccd41  mov     rdi, rcx
0x1800ccd44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast> `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::GetImpl(void)'::`2'::impl
0x1800ccd4b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::__private_IsEnabled(void)
0x1800ccd50  test    al, al
0x1800ccd52  jz      loc_1800CCEFE
0x1800ccd58  xor     edx, edx; hFile
0x1800ccd5a  mov     r8d, 802h; dwFlags
0x1800ccd60  lea     rcx, aLocationframew_0; "LocationFramework.dll"
0x1800ccd67  call    cs:__imp_LoadLibraryExW
0x1800ccd6d  mov     rbx, rax
0x1800ccd70  mov     [rsp+1528h+var_14F8], rax
0x1800ccd75  test    rax, rax
0x1800ccd78  jnz     short loc_1800CCD92
0x1800ccd7a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800ccd7f  mov     ebx, eax
0x1800ccd81  lea     rcx, [rsp+1528h+var_14F8]
0x1800ccd86  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800ccd8b  mov     eax, ebx
0x1800ccd8d  jmp     loc_1800CD01F
0x1800ccd92  mov     r8d, 0C8h
0x1800ccd98  mov     rdx, rbx
0x1800ccd9b  lea     rcx, [rsp+1528h+var_14D8]
0x1800ccda0  call    ?LoadStringDynamic@LocationToastHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@I@Z; LocationToastHelper::LoadStringDynamic(HINSTANCE__ *,uint)
0x1800ccda5  mov     rdx, rax
0x1800ccda8  mov     rcx, rax
0x1800ccdab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ccdb0  mov     [rsp+1528h+var_14E8], rax
0x1800ccdb5  mov     rax, [rdx+10h]
0x1800ccdb9  mov     [rsp+1528h+var_14E0], rax
0x1800ccdbe  lea     rdx, [rsp+1528h+var_14E8]
0x1800ccdc3  lea     rcx, [rsp+1528h+var_1478]
0x1800ccdcb  call    ?XmlEscape@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; LSUtility::XmlEscape(wil::basic_zstring_view<ushort>)
0x1800ccdd0  nop
0x1800ccdd1  lea     rcx, [rsp+1528h+var_14D8]
0x1800ccdd6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccddb  mov     r8d, 0C9h
0x1800ccde1  mov     rdx, rbx
0x1800ccde4  lea     rcx, [rsp+1528h+var_14B8]
0x1800ccde9  call    ?LoadStringDynamic@LocationToastHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@I@Z; LocationToastHelper::LoadStringDynamic(HINSTANCE__ *,uint)
0x1800ccdee  mov     rdx, rax
0x1800ccdf1  mov     rcx, rax
0x1800ccdf4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ccdf9  mov     [rsp+1528h+var_14E8], rax
0x1800ccdfe  mov     rax, [rdx+10h]
0x1800cce02  mov     [rsp+1528h+var_14E0], rax
0x1800cce07  lea     rdx, [rsp+1528h+var_14E8]
0x1800cce0c  lea     rcx, [rsp+1528h+var_1498]
0x1800cce14  call    ?XmlEscape@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; LSUtility::XmlEscape(wil::basic_zstring_view<ushort>)
0x1800cce19  nop
0x1800cce1a  lea     rcx, [rsp+1528h+var_14B8]
0x1800cce1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cce24  cmp     [rsp+1528h+var_1468], 0
0x1800cce2d  jz      loc_1800CCEC5
0x1800cce33  cmp     [rsp+1528h+var_1488], 0
0x1800cce3c  jz      loc_1800CCEC5
0x1800cce42  lea     rax, aToastLaunchMsS; "<toast launch=\"ms-settings:privacy-loc"...
0x1800cce49  mov     [rsp+1528h+var_14E8], rax
0x1800cce4e  mov     [rsp+1528h+var_14E0], 0B7h
0x1800cce57  lea     r9, [rsp+1528h+var_1498]
0x1800cce5f  lea     r8, [rsp+1528h+var_1478]
0x1800cce67  lea     rdx, [rsp+1528h+var_14E8]
0x1800cce6c  lea     rcx, [rsp+1528h+var_1458]
0x1800cce74  call    ??$format@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@0@AEBV10@1@Z; std::format<std::wstring const &,std::wstring const &>(std::basic_format_string<ushort,std::wstring const &,std::wstring const &>,std::wstring const &,std::wstring const &)
0x1800cce79  nop
0x1800cce7a  lea     rdx, [rsp+1528h+var_1458]
0x1800cce82  mov     rcx, rdi
0x1800cce85  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800cce8a  nop
0x1800cce8b  lea     rcx, [rsp+1528h+var_1458]
0x1800cce93  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cce98  nop
0x1800cce99  lea     rcx, [rsp+1528h+var_1498]
0x1800ccea1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccea6  nop
0x1800ccea7  lea     rcx, [rsp+1528h+var_1478]
0x1800cceaf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cceb4  nop
0x1800cceb5  lea     rcx, [rsp+1528h+var_14F8]
0x1800cceba  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800ccebf  nop
0x1800ccec0  jmp     loc_1800CD01D
0x1800ccec5  lea     rcx, [rsp+1528h+var_1498]
0x1800ccecd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cced2  nop
0x1800cced3  lea     rcx, [rsp+1528h+var_1478]
0x1800ccedb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccee0  nop
0x1800ccee1  lea     rcx, [rsp+1528h+var_14F8]
0x1800ccee6  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800cceeb  mov     eax, 80070714h
0x1800ccef0  jmp     loc_1800CD01F
0x1800ccef5  mov     eax, dword ptr [rsp+1528h+var_14F8]
0x1800ccef9  jmp     loc_1800CD01F
0x1800ccefe  xor     edx, edx; Val
0x1800ccf00  mov     r8d, 1000h; Size
0x1800ccf06  lea     rcx, [rsp+1528h+var_1018]; void *
0x1800ccf0e  call    memset_0
0x1800ccf13  mov     ebx, 208h
0x1800ccf18  mov     r8d, ebx; Size
0x1800ccf1b  xor     edx, edx; Val
0x1800ccf1d  lea     rcx, [rsp+1528h+Buffer]; void *
0x1800ccf25  call    memset_0
0x1800ccf2a  mov     r8d, ebx; Size
0x1800ccf2d  xor     edx, edx; Val
0x1800ccf2f  lea     rcx, [rsp+1528h+var_1438]; void *
0x1800ccf37  call    memset_0
0x1800ccf3c  xor     edx, edx; hFile
0x1800ccf3e  lea     r8d, [rdx+2]; dwFlags
0x1800ccf42  lea     rcx, aLocationframew_0; "LocationFramework.dll"
0x1800ccf49  call    cs:__imp_LoadLibraryExW
0x1800ccf4f  mov     rbx, rax
0x1800ccf52  test    rax, rax
0x1800ccf55  jnz     short loc_1800CCF61
0x1800ccf57  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800ccf5c  jmp     loc_1800CD01F
0x1800ccf61  mov     r9d, 104h; cchBufferMax
0x1800ccf67  lea     r8, [rsp+1528h+Buffer]; lpBuffer
0x1800ccf6f  lea     edx, [r9-3Ch]; uID
0x1800ccf73  mov     rcx, rbx; hInstance
0x1800ccf76  call    cs:__imp_LoadStringW
0x1800ccf7c  test    eax, eax
0x1800ccf7e  jnz     short loc_1800CCFAE
0x1800ccf80  lea     rax, a0LoadstringIns_2; "0 == LoadString(instRes, IDS_LOC_DEFAUL"...
0x1800ccf87  mov     edx, 0BEh; void *
0x1800ccf8c  lea     r8, aOnecoreuapDriv_81; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1800ccf93  lea     r9, aLocationtoasth; "LocationToastHelper::BuildDefaultLocati"...
0x1800ccf9a  mov     [rsp+1528h+var_1508], rax; char *
0x1800ccf9f  mov     rcx, [rsp+1528h]; this
0x1800ccfa7  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x1800ccfac  jmp     short loc_1800CD01F
0x1800ccfae  mov     r9d, 104h; cchBufferMax
0x1800ccfb4  lea     r8, [rsp+1528h+var_1438]; lpBuffer
0x1800ccfbc  lea     edx, [r9-3Bh]; uID
0x1800ccfc0  mov     rcx, rbx; hInstance
0x1800ccfc3  call    cs:__imp_LoadStringW
0x1800ccfc9  test    eax, eax
0x1800ccfcb  jnz     short loc_1800CCFDB
0x1800ccfcd  lea     rax, a0LoadstringIns_1; "0 == LoadString(instRes, IDS_LOC_DEFAUL"...
0x1800ccfd4  mov     edx, 0BFh
0x1800ccfd9  jmp     short loc_1800CCF8C
0x1800ccfdb  lea     rax, [rsp+1528h+var_1438]
0x1800ccfe3  mov     [rsp+1528h+var_1508], rax
0x1800ccfe8  lea     r9, [rsp+1528h+Buffer]
0x1800ccff0  lea     r8, aToastLaunchMsS_0; "<toast launch=\"ms-settings:privacy-loc"...
0x1800ccff7  mov     edx, 800h; unsigned __int64
0x1800ccffc  lea     rcx, [rsp+1528h+var_1018]; unsigned __int16 *
0x1800cd004  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cd009  test    eax, eax
0x1800cd00b  js      short loc_1800CD01F
0x1800cd00d  lea     rdx, [rsp+1528h+var_1018]
0x1800cd015  mov     rcx, rdi
0x1800cd018  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cd01d  xor     eax, eax
0x1800cd01f  mov     rcx, [rsp+1528h+var_18]
0x1800cd027  xor     rcx, rsp; StackCookie
0x1800cd02a  call    __security_check_cookie
0x1800cd02f  mov     rbx, [rsp+1528h+arg_8]
0x1800cd037  add     rsp, 1520h
0x1800cd03e  pop     rdi
0x1800cd03f  retn
```
