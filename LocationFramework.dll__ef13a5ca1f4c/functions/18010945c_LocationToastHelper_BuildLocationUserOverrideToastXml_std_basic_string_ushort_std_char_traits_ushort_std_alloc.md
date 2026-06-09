# LocationToastHelper::BuildLocationUserOverrideToastXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18010945c`
- end: `0x1801099ab`
- name: `?BuildLocationUserOverrideToastXml@LocationToastHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1359`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a6d14`

## callees

- `0x18000f040`
- `0x18002085c`
- `0x180020994`
- `0x180020c64`
- `0x180046104`
- `0x18005c458`
- `0x18005f304`
- `0x180060988`
- `0x180061f04`
- `0x180084ac8`
- `0x180086b94`
- `0x18008f490`
- `0x18008f888`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800cd838`
- `0x1800d0160`
- `0x1800eec10`
- `0x180109134`
- `0x1801091e4`
- `0x18010945c`
- `0x180152970`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801098dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180109925`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1801098dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180109925`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801094b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801098ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801094b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801098ae`
- `OLEAUT32!__imp_SysFreeString` at `0x18010960d`
- `OLEAUT32!__imp_SysFreeString` at `0x18010960d`

## string_xrefs

- `0x1801094a9`: `LocationFramework.dll`
- `0x1801098a7`: `LocationFramework.dll`
- `0x180109952`: `<toast launch="ms-settings:privacy-location" activationType="protocol"><visual><binding template="ToastGeneric"><text id="1">%s</text><text id="2">%s</text></binding></visual></toast>`
- `0x180109727`: `<toast launch="ms-settings:privacy-location" activationType="protocol"><visual><binding template="ToastGeneric"><text id="1">{}</text><text id="2">{}</text></binding></visual><actions><action content="{}" activationType="background" arguments="fewerNotificationsButton"/></actions></toast>`
- `0x1801098f7`: `LocationToastHelper::BuildLocationUserOverrideToastXml`
- `0x18010992f`: `0 == LoadString(instRes, IDS_LOC_USER_OVERRIDE_TOAST_BODY_DELETED, body, ARRAYSIZE(body))`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall LocationToastHelper::BuildLocationUserOverrideToastXml(__int64 a1)
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
  int LocationManagerInternal; // edi
  LPVOID v12; // rsi
  __int64 (__fastcall *v13)(LPVOID, BSTR *); // r15
  OLECHAR *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  HMODULE v19; // rax
  wil::details *v20; // rcx
  HINSTANCE v21; // rbx
  const char *v22; // rax
  __int64 v23; // rdx
  const char *v24; // [rsp+28h] [rbp-1560h]
  const wchar_t *v25; // [rsp+30h] [rbp-1558h] BYREF
  __int64 v26; // [rsp+38h] [rbp-1550h]
  HMODULE v27; // [rsp+40h] [rbp-1548h] BYREF
  _BYTE v28[32]; // [rsp+48h] [rbp-1540h] BYREF
  _BYTE v29[32]; // [rsp+68h] [rbp-1520h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-1500h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-14F8h] BYREF
  _BYTE v32[16]; // [rsp+98h] [rbp-14F0h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-14E0h]
  _BYTE v34[16]; // [rsp+B8h] [rbp-14D0h] BYREF
  __int64 v35; // [rsp+C8h] [rbp-14C0h]
  _BYTE v36[16]; // [rsp+D8h] [rbp-14B0h] BYREF
  __int64 v37; // [rsp+E8h] [rbp-14A0h]
  _BYTE v38[32]; // [rsp+F8h] [rbp-1490h] BYREF
  _BYTE v39[40]; // [rsp+118h] [rbp-1470h] BYREF
  WCHAR v40[264]; // [rsp+140h] [rbp-1448h] BYREF
  WCHAR Buffer[264]; // [rsp+350h] [rbp-1238h] BYREF
  unsigned __int16 v42[2048]; // [rsp+560h] [rbp-1028h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+1588h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::GetImpl'::`2'::impl) )
  {
    Library = LoadLibraryExW(L"LocationFramework.dll", 0, 0x802u);
    v4 = Library;
    v27 = Library;
    if ( !Library )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v3);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v27);
      return LastErrorFailHr;
    }
    StringDynamic = LocationToastHelper::LoadStringDynamic(v29, Library, 300);
    v25 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(StringDynamic, StringDynamic);
    v26 = *(_QWORD *)(v8 + 16);
    LSUtility::XmlEscape(v34, &v25);
    std::wstring::_Tidy_deallocate(v29);
    v9 = LocationToastHelper::LoadStringDynamic(v28, v4, 321);
    v25 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9, v9);
    v26 = *(_QWORD *)(v10 + 16);
    LSUtility::XmlEscape(v32, &v25);
    std::wstring::_Tidy_deallocate(v28);
    bstrString = 0;
    ppv = 0;
    LocationManagerInternal = LocationHelper::GetLocationManagerInternal(&ppv);
    if ( LocationManagerInternal < 0 )
      goto LABEL_5;
    v12 = ppv;
    v13 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)ppv + 192LL);
    v14 = bstrString;
    if ( bstrString )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v25);
      SysFreeString(v14);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v25);
    }
    bstrString = 0;
    LocationManagerInternal = v13(v12, &bstrString);
    if ( LocationManagerInternal < 0 )
    {
LABEL_5:
      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&ppv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v34);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v27);
      return (unsigned int)LocationManagerInternal;
    }
    LocationToastHelper::LoadStringDynamic(v38, v4, 320);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v15);
    v17 = wil::str_printf<std::wstring>(v28, v16, bstrString);
    v25 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17, v17);
    v26 = *(_QWORD *)(v18 + 16);
    LSUtility::XmlEscape(v36, &v25);
    std::wstring::_Tidy_deallocate(v28);
    if ( !v35 || !v33 || !v37 )
    {
      std::wstring::_Tidy_deallocate(v36);
      std::wstring::_Tidy_deallocate(v38);
      wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&ppv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
      std::wstring::_Tidy_deallocate(v32);
      std::wstring::_Tidy_deallocate(v34);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v27);
      return 2147944212LL;
    }
    v25 = L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\"><visual><binding template=\"ToastGe"
           "neric\"><text id=\"1\">{}</text><text id=\"2\">{}</text></binding></visual><actions><action content=\"{}\" ac"
           "tivationType=\"background\" arguments=\"fewerNotificationsButton\"/></actions></toast>";
    v26 = 289;
    std::format<std::wstring const &,std::wstring const &,std::wstring const &>(
      (unsigned int)v39,
      (unsigned int)&v25,
      (unsigned int)v34,
      (unsigned int)v36,
      (__int64)v32);
    std::wstring::append(a1, v39);
    std::wstring::_Tidy_deallocate(v39);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v38);
    wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(&ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
    std::wstring::_Tidy_deallocate(v32);
    std::wstring::_Tidy_deallocate(v34);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v27);
    return 0;
  }
  memset_0(v42, 0, sizeof(v42));
  memset_0(Buffer, 0, 0x208u);
  memset_0(v40, 0, 0x208u);
  v19 = LoadLibraryExW(L"LocationFramework.dll", 0, 2u);
  v21 = v19;
  if ( !v19 )
    return wil::details::GetLastErrorFailHr(v20);
  if ( !LoadStringW(v19, 0x12Cu, Buffer, 260) )
  {
    v22 = "0 == LoadString(instRes, IDS_LOC_USER_OVERRIDE_TOAST_TITLE, title, ARRAYSIZE(title))";
    v23 = 272;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v23,
             (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\LocationToastHelper.h",
             "LocationToastHelper::BuildLocationUserOverrideToastXml",
             v22,
             v24);
  }
  if ( !LoadStringW(v21, 0x12Du, v40, 260) )
  {
    v22 = "0 == LoadString(instRes, IDS_LOC_USER_OVERRIDE_TOAST_BODY_DELETED, body, ARRAYSIZE(body))";
    v23 = 273;
    return wil::details::in1diag5::Return_GetLastError(
             retaddr,
             (void *)v23,
             (unsigned int)"onecoreuap\\drivers\\MobilePC\\Location\\Product\\Core\\Framework\\inc\\LocationToastHelper.h",
             "LocationToastHelper::BuildLocationUserOverrideToastXml",
             v22,
             v24);
  }
  result = StringCchPrintfW(
             v42,
             0x800u,
             L"<toast launch=\"ms-settings:privacy-location\" activationType=\"protocol\"><visual><binding template=\"Toas"
              "tGeneric\"><text id=\"1\">%s</text><text id=\"2\">%s</text></binding></visual></toast>",
             Buffer,
             v40);
  if ( (int)result < 0 )
    return result;
  std::wstring::append(a1, v42);
  return 0;
}

```

## disassembly

```asm
0x18010945c  mov     [rsp+arg_8], rbx
0x180109461  mov     [rsp+arg_10], rsi
0x180109466  push    rdi
0x180109467  push    r14
0x180109469  push    r15
0x18010946b  mov     eax, 1570h
0x180109470  call    _alloca_probe
0x180109475  sub     rsp, rax
0x180109478  mov     rax, cs:__security_cookie
0x18010947f  xor     rax, rsp
0x180109482  mov     [rsp+1588h+var_28], rax
0x18010948a  mov     r14, rcx
0x18010948d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast> `wil::Feature<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::GetImpl(void)'::`2'::impl
0x180109494  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Location_Fix_OverrideToast@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Location_Fix_OverrideToast>::__private_IsEnabled(void)
0x180109499  test    al, al
0x18010949b  jz      loc_180109863
0x1801094a1  xor     edx, edx; hFile
0x1801094a3  mov     r8d, 802h; dwFlags
0x1801094a9  lea     rcx, aLocationframew_0; "LocationFramework.dll"
0x1801094b0  call    cs:__imp_LoadLibraryExW
0x1801094b6  mov     rbx, rax
0x1801094b9  mov     [rsp+1588h+var_1548], rax
0x1801094be  test    rax, rax
0x1801094c1  jnz     short loc_1801094DB
0x1801094c3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801094c8  mov     ebx, eax
0x1801094ca  lea     rcx, [rsp+1588h+var_1548]
0x1801094cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801094d4  mov     eax, ebx
0x1801094d6  jmp     loc_180109981
0x1801094db  mov     r8d, 12Ch
0x1801094e1  mov     rdx, rbx
0x1801094e4  lea     rcx, [rsp+1588h+var_1520]
0x1801094e9  call    ?LoadStringDynamic@LocationToastHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@I@Z; LocationToastHelper::LoadStringDynamic(HINSTANCE__ *,uint)
0x1801094ee  mov     rdx, rax
0x1801094f1  mov     rcx, rax
0x1801094f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801094f9  mov     [rsp+1588h+var_1558], rax
0x1801094fe  mov     rax, [rdx+10h]
0x180109502  mov     [rsp+1588h+var_1550], rax
0x180109507  lea     rdx, [rsp+1588h+var_1558]
0x18010950c  lea     rcx, [rsp+1588h+var_14D0]
0x180109514  call    ?XmlEscape@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; LSUtility::XmlEscape(wil::basic_zstring_view<ushort>)
0x180109519  nop
0x18010951a  lea     rcx, [rsp+1588h+var_1520]
0x18010951f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109524  mov     r8d, 141h
0x18010952a  mov     rdx, rbx
0x18010952d  lea     rcx, [rsp+1588h+var_1540]
0x180109532  call    ?LoadStringDynamic@LocationToastHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@I@Z; LocationToastHelper::LoadStringDynamic(HINSTANCE__ *,uint)
0x180109537  mov     rdx, rax
0x18010953a  mov     rcx, rax
0x18010953d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109542  mov     [rsp+1588h+var_1558], rax
0x180109547  mov     rax, [rdx+10h]
0x18010954b  mov     [rsp+1588h+var_1550], rax
0x180109550  lea     rdx, [rsp+1588h+var_1558]
0x180109555  lea     rcx, [rsp+1588h+var_14F0]
0x18010955d  call    ?XmlEscape@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; LSUtility::XmlEscape(wil::basic_zstring_view<ushort>)
0x180109562  nop
0x180109563  lea     rcx, [rsp+1588h+var_1540]
0x180109568  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010956d  mov     [rsp+1588h+bstrString], 0
0x180109579  mov     [rsp+1588h+ppv], 0
0x180109585  lea     rcx, [rsp+1588h+ppv]; ppv
0x18010958d  call    ?GetLocationManagerInternal@LocationHelper@@SAJPEAPEAUILocationManagerInternal@@@Z; LocationHelper::GetLocationManagerInternal(ILocationManagerInternal * *)
0x180109592  mov     edi, eax
0x180109594  test    eax, eax
0x180109596  jns     short loc_1801095E1
0x180109598  lea     rcx, [rsp+1588h+ppv]
0x1801095a0  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x1801095a5  nop
0x1801095a6  lea     rcx, [rsp+1588h+bstrString]
0x1801095ae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801095b3  nop
0x1801095b4  lea     rcx, [rsp+1588h+var_14F0]
0x1801095bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801095c1  nop
0x1801095c2  lea     rcx, [rsp+1588h+var_14D0]
0x1801095ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801095cf  nop
0x1801095d0  lea     rcx, [rsp+1588h+var_1548]
0x1801095d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801095da  mov     eax, edi
0x1801095dc  jmp     loc_180109981
0x1801095e1  mov     rsi, [rsp+1588h+ppv]
0x1801095e9  mov     rax, [rsi]
0x1801095ec  mov     r15, [rax+0C0h]
0x1801095f3  mov     rdi, [rsp+1588h+bstrString]
0x1801095fb  test    rdi, rdi
0x1801095fe  jz      short loc_18010961D
0x180109600  lea     rcx, [rsp+1588h+var_1558]; this
0x180109605  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18010960a  mov     rcx, rdi; bstrString
0x18010960d  call    cs:__imp_SysFreeString
0x180109613  lea     rcx, [rsp+1588h+var_1558]; this
0x180109618  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18010961d  mov     [rsp+1588h+bstrString], 0
0x180109629  lea     rdx, [rsp+1588h+bstrString]
0x180109631  mov     rcx, rsi
0x180109634  mov     rax, r15
0x180109637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010963c  mov     edi, eax
0x18010963e  test    eax, eax
0x180109640  jns     short loc_18010968B
0x180109642  lea     rcx, [rsp+1588h+ppv]
0x18010964a  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x18010964f  nop
0x180109650  lea     rcx, [rsp+1588h+bstrString]
0x180109658  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010965d  nop
0x18010965e  lea     rcx, [rsp+1588h+var_14F0]
0x180109666  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010966b  nop
0x18010966c  lea     rcx, [rsp+1588h+var_14D0]
0x180109674  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109679  nop
0x18010967a  lea     rcx, [rsp+1588h+var_1548]
0x18010967f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180109684  mov     eax, edi
0x180109686  jmp     loc_180109981
0x18010968b  mov     r8d, 140h
0x180109691  mov     rdx, rbx
0x180109694  lea     rcx, [rsp+1588h+var_1490]
0x18010969c  call    ?LoadStringDynamic@LocationToastHelper@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHINSTANCE__@@I@Z; LocationToastHelper::LoadStringDynamic(HINSTANCE__ *,uint)
0x1801096a1  nop
0x1801096a2  lea     rcx, [rsp+1588h+var_1490]
0x1801096aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801096af  mov     rdx, rax
0x1801096b2  mov     r8, [rsp+1588h+bstrString]
0x1801096ba  lea     rcx, [rsp+1588h+var_1540]
0x1801096bf  call    ??$str_printf@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; wil::str_printf<std::wstring>(ushort const *,...)
0x1801096c4  mov     rdx, rax
0x1801096c7  mov     rcx, rax
0x1801096ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801096cf  mov     [rsp+1588h+var_1558], rax
0x1801096d4  mov     rax, [rdx+10h]
0x1801096d8  mov     [rsp+1588h+var_1550], rax
0x1801096dd  lea     rdx, [rsp+1588h+var_1558]
0x1801096e2  lea     rcx, [rsp+1588h+var_14B0]
0x1801096ea  call    ?XmlEscape@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@G@wil@@@Z; LSUtility::XmlEscape(wil::basic_zstring_view<ushort>)
0x1801096ef  nop
0x1801096f0  lea     rcx, [rsp+1588h+var_1540]
0x1801096f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801096fa  cmp     [rsp+1588h+var_14C0], 0
0x180109703  jz      loc_1801097EF
0x180109709  cmp     [rsp+1588h+var_14E0], 0
0x180109712  jz      loc_1801097EF
0x180109718  cmp     [rsp+1588h+var_14A0], 0
0x180109721  jz      loc_1801097EF
0x180109727  lea     rax, aToastLaunchMsS_1; "<toast launch=\"ms-settings:privacy-loc"...
0x18010972e  mov     [rsp+1588h+var_1558], rax
0x180109733  mov     [rsp+1588h+var_1550], 121h
0x18010973c  lea     rax, [rsp+1588h+var_14F0]
0x180109744  mov     [rsp+1588h+var_1568], rax
0x180109749  lea     r9, [rsp+1588h+var_14B0]
0x180109751  lea     r8, [rsp+1588h+var_14D0]
0x180109759  lea     rdx, [rsp+1588h+var_1558]
0x18010975e  lea     rcx, [rsp+1588h+var_1470]
0x180109766  call    ??$format@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@AEBV12@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@U?$basic_format_string@GAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@AEBV12@@0@AEBV10@11@Z; std::format<std::wstring const &,std::wstring const &,std::wstring const &>(std::basic_format_string<ushort,std::wstring const &,std::wstring const &,std::wstring const &>,std::wstring const &,std::wstring const &,std::wstring const &)
0x18010976b  nop
0x18010976c  lea     rdx, [rsp+1588h+var_1470]
0x180109774  mov     rcx, r14
0x180109777  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010977c  nop
0x18010977d  lea     rcx, [rsp+1588h+var_1470]
0x180109785  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010978a  nop
0x18010978b  lea     rcx, [rsp+1588h+var_14B0]
0x180109793  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109798  nop
0x180109799  lea     rcx, [rsp+1588h+var_1490]
0x1801097a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801097a6  nop
0x1801097a7  lea     rcx, [rsp+1588h+ppv]
0x1801097af  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x1801097b4  nop
0x1801097b5  lea     rcx, [rsp+1588h+bstrString]
0x1801097bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801097c2  nop
0x1801097c3  lea     rcx, [rsp+1588h+var_14F0]
0x1801097cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801097d0  nop
0x1801097d1  lea     rcx, [rsp+1588h+var_14D0]
0x1801097d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801097de  nop
0x1801097df  lea     rcx, [rsp+1588h+var_1548]
0x1801097e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801097e9  nop
0x1801097ea  jmp     loc_18010997F
0x1801097ef  lea     rcx, [rsp+1588h+var_14B0]
0x1801097f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801097fc  nop
0x1801097fd  lea     rcx, [rsp+1588h+var_1490]
0x180109805  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010980a  nop
0x18010980b  lea     rcx, [rsp+1588h+ppv]
0x180109813  call    ??1?$com_ptr_t@UIWpnSettingsEndpoint@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>::~com_ptr_t<IWpnSettingsEndpoint,wil::err_exception_policy>(void)
0x180109818  nop
0x180109819  lea     rcx, [rsp+1588h+bstrString]
0x180109821  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180109826  nop
0x180109827  lea     rcx, [rsp+1588h+var_14F0]
0x18010982f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109834  nop
0x180109835  lea     rcx, [rsp+1588h+var_14D0]
0x18010983d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109842  nop
0x180109843  lea     rcx, [rsp+1588h+var_1548]
0x180109848  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18010984d  mov     eax, 80070714h
0x180109852  jmp     loc_180109981
0x180109857  mov     eax, dword ptr [rsp+1588h+bstrString]
0x18010985e  jmp     loc_180109981
0x180109863  xor     edx, edx; Val
0x180109865  mov     r8d, 1000h; Size
0x18010986b  lea     rcx, [rsp+1588h+var_1028]; void *
0x180109873  call    memset_0
0x180109878  mov     ebx, 208h
0x18010987d  mov     r8d, ebx; Size
0x180109880  xor     edx, edx; Val
0x180109882  lea     rcx, [rsp+1588h+Buffer]; void *
0x18010988a  call    memset_0
0x18010988f  mov     r8d, ebx; Size
0x180109892  xor     edx, edx; Val
0x180109894  lea     rcx, [rsp+1588h+var_1448]; void *
0x18010989c  call    memset_0
0x1801098a1  xor     edx, edx; hFile
0x1801098a3  lea     r8d, [rdx+2]; dwFlags
0x1801098a7  lea     rcx, aLocationframew_0; "LocationFramework.dll"
0x1801098ae  call    cs:__imp_LoadLibraryExW
0x1801098b4  mov     rbx, rax
0x1801098b7  test    rax, rax
0x1801098ba  jnz     short loc_1801098C6
0x1801098bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801098c1  jmp     loc_180109981
0x1801098c6  mov     edi, 104h
0x1801098cb  mov     r9d, edi; cchBufferMax
0x1801098ce  lea     r8, [rsp+1588h+Buffer]; lpBuffer
0x1801098d6  lea     edx, [rdi+28h]; uID
0x1801098d9  mov     rcx, rbx; hInstance
0x1801098dc  call    cs:__imp_LoadStringW
0x1801098e2  test    eax, eax
0x1801098e4  jnz     short loc_180109912
0x1801098e6  lea     rax, a0LoadstringIns_0; "0 == LoadString(instRes, IDS_LOC_USER_O"...
0x1801098ed  lea     edx, [rdi+0Ch]; void *
0x1801098f0  lea     r8, aOnecoreuapDriv_81; "onecoreuap\\drivers\\MobilePC\\Location"...
0x1801098f7  lea     r9, aLocationtoasth_0; "LocationToastHelper::BuildLocationUserO"...
0x1801098fe  mov     [rsp+1588h+var_1568], rax; char *
0x180109903  mov     rcx, [rsp+1588h]; this
0x18010990b  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180109910  jmp     short loc_180109981
0x180109912  mov     r9d, edi; cchBufferMax
0x180109915  lea     r8, [rsp+1588h+var_1448]; lpBuffer
0x18010991d  mov     edx, 12Dh; uID
0x180109922  mov     rcx, rbx; hInstance
0x180109925  call    cs:__imp_LoadStringW
0x18010992b  test    eax, eax
0x18010992d  jnz     short loc_18010993D
0x18010992f  lea     rax, a0LoadstringIns; "0 == LoadString(instRes, IDS_LOC_USER_O"...
0x180109936  mov     edx, 111h
0x18010993b  jmp     short loc_1801098F0
0x18010993d  lea     rax, [rsp+1588h+var_1448]
0x180109945  mov     [rsp+1588h+var_1568], rax
0x18010994a  lea     r9, [rsp+1588h+Buffer]
0x180109952  lea     r8, aToastLaunchMsS_0; "<toast launch=\"ms-settings:privacy-loc"...
0x180109959  mov     edx, 800h; unsigned __int64
0x18010995e  lea     rcx, [rsp+1588h+var_1028]; unsigned __int16 *
0x180109966  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010996b  test    eax, eax
0x18010996d  js      short loc_180109981
0x18010996f  lea     rdx, [rsp+1588h+var_1028]
0x180109977  mov     rcx, r14
0x18010997a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010997f  xor     eax, eax
0x180109981  mov     rcx, [rsp+1588h+var_28]
0x180109989  xor     rcx, rsp; StackCookie
0x18010998c  call    __security_check_cookie
0x180109991  lea     r11, [rsp+1588h+var_18]
0x180109999  mov     rbx, [r11+28h]
0x18010999d  mov     rsi, [r11+30h]
0x1801099a1  mov     rsp, r11
0x1801099a4  pop     r15
0x1801099a6  pop     r14
0x1801099a8  pop     rdi
0x1801099a9  retn
```
