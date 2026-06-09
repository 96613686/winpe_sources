# ShowFeedbackToastHandler::ShowFeedbackToast(WheFeedbackToastPayload const &)

- ea: `0x18001874c`
- end: `0x180018a65`
- name: `?ShowFeedbackToast@ShowFeedbackToastHandler@@AEAAJAEBUWheFeedbackToastPayload@@@Z`
- size: `793`
- prototype: `ShowFeedbackToast *__fastcall(ShowFeedbackToast *this, const struct WheFeedbackToastPayload *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180018a70`

## callees

- `0x180007f3c`
- `0x18000b524`
- `0x1800100b8`
- `0x180010278`
- `0x18001066c`
- `0x1800106e0`
- `0x180010a0c`
- `0x180010a38`
- `0x180010f20`
- `0x18001161c`
- `0x180012220`
- `0x1800127e0`
- `0x180012b0c`
- `0x18001309c`
- `0x180016e40`
- `0x18001874c`

## string_xrefs

- `0x180018799`: `pcshell\shell\performancetracehandler\dll\showfeedbacktoasthandler.cpp`
- `0x1800187ed`: `pcshell\shell\performancetracehandler\dll\showfeedbacktoasthandler.cpp`
- `0x180018847`: `pcshell\shell\performancetracehandler\dll\showfeedbacktoasthandler.cpp`
- `0x1800188c8`: `\n<toast activationType="background"\n       com:activatorId="{b707f044-51d6-4038-b33b-ef2661b7c5b2}"\n       launch="response=toast_click&amp;id=%ws&amp;trigger=%ws"\n       xmlns:com="http://schemas.microsoft.com/appx/toast/protocol/activation">\n  <visual>\n    <binding template="ToastGeneric">\n      <text>%ws</text>\n    </binding>\n  </visual>\n  <actions>\n    <action content="%ws" activationType="background"\n            arguments="response=yes&amp;id=%ws&amp;trigger=%ws"/>\n    <action `

## pseudocode

```c
ShowFeedbackToast *__fastcall ShowFeedbackToastHandler::ShowFeedbackToast(
        ShowFeedbackToast *this,
        const struct WheFeedbackToastPayload *a2)
{
  int ResourceString; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  ShowFeedbackToast *result; // rax
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-D8h]
  _BYTE v12[8]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v13[8]; // [rsp+68h] [rbp-90h] BYREF
  _QWORD v14[3]; // [rsp+70h] [rbp-88h] BYREF
  _QWORD v15[3]; // [rsp+88h] [rbp-70h] BYREF
  _QWORD v16[3]; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-40h] BYREF
  _BYTE v18[8]; // [rsp+C0h] [rbp-38h] BYREF
  _BYTE v19[48]; // [rsp+C8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  ShowFeedbackToast *v21; // [rsp+100h] [rbp+8h] BYREF
  char v22; // [rsp+110h] [rbp+18h] BYREF
  unsigned __int16 *v23; // [rsp+118h] [rbp+20h] BYREF

  v21 = this;
  memset(v16, 0, sizeof(v16));
  ResourceString = ShowFeedbackToastHandler::LoadResourceString(this, 664, v16);
  v5 = ResourceString;
  if ( ResourceString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\showfeedbacktoasthandler.cpp",
      (const char *)(unsigned int)ResourceString,
      v11);
LABEL_8:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
    return (ShowFeedbackToast *)v5;
  }
  memset(v14, 0, sizeof(v14));
  v6 = ShowFeedbackToastHandler::LoadResourceString(v4, 665, v14);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\showfeedbacktoasthandler.cpp",
      (const char *)(unsigned int)v6,
      v11);
LABEL_7:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
    goto LABEL_8;
  }
  memset(v15, 0, sizeof(v15));
  v8 = ShowFeedbackToastHandler::LoadResourceString(v7, 666, v15);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\showfeedbacktoasthandler.cpp",
      (const char *)(unsigned int)v8,
      v11);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v15);
    goto LABEL_7;
  }
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v23,
    L"\n"
     "<toast activationType=\"background\"\n"
     "       com:activatorId=\"{b707f044-51d6-4038-b33b-ef2661b7c5b2}\"\n"
     "       launch=\"response=toast_click&amp;id=%ws&amp;trigger=%ws\"\n"
     "       xmlns:com=\"http://schemas.microsoft.com/appx/toast/protocol/activation\">\n"
     "  <visual>\n"
     "    <binding template=\"ToastGeneric\">\n"
     "      <text>%ws</text>\n"
     "    </binding>\n"
     "  </visual>\n"
     "  <actions>\n"
     "    <action content=\"%ws\" activationType=\"background\"\n"
     "            arguments=\"response=yes&amp;id=%ws&amp;trigger=%ws\"/>\n"
     "    <action content=\"%ws\" activationType=\"background\"\n"
     "            arguments=\"response=no&amp;id=%ws&amp;trigger=%ws\"/>\n"
     "  </actions>\n"
     "</toast>",
    a2);
  try
  {
    winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((winrt::Windows::Data::Xml::Dom::XmlDocument *)&v22);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, v23);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
      &v22,
      v19);
    winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
      (winrt::Windows::UI::Notifications::ToastNotification *)&v21,
      (const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)&v22);
    v17 = *(_QWORD *)winrt::clock::now(v18) + 18000000000LL;
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
      v12,
      &v17);
    winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(
      &v21,
      v12);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v12);
    winrt::param::hstring::hstring((winrt::param::hstring *)v19, L"Windows.SystemToast.Whesvc.Feedback");
    winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier((const struct winrt::param::hstring *)v13);
    winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
      v13,
      &v21);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v13);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v21);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v15);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xA8,
                     (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\showfeedbacktoasthandler.cpp",
                     v10);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v23);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v15);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
    return (ShowFeedbackToast *)(unsigned int)v21;
  }
  return result;
}

```

## disassembly

```asm
0x18001874c  mov     rax, rsp
0x18001874f  mov     [rax+10h], rbx
0x180018753  mov     [rax+8], rcx
0x180018757  push    rdi
0x180018758  sub     rsp, 0F0h
0x18001875f  mov     rdi, rdx
0x180018762  mov     qword ptr [rax-58h], 0
0x18001876a  mov     qword ptr [rax-50h], 0
0x180018772  mov     qword ptr [rax-48h], 0
0x18001877a  lea     r8, [rax-58h]
0x18001877e  mov     edx, 298h
0x180018783  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180018788  mov     ebx, eax
0x18001878a  test    eax, eax
0x18001878c  jns     short loc_1800187AF
0x18001878e  mov     rcx, [rsp+0F8h]; this
0x180018796  mov     r9d, eax; char *
0x180018799  lea     r8, aPcshellShellPe_1; "pcshell\\shell\\performancetracehandler"...
0x1800187a0  mov     edx, 74h ; 't'; void *
0x1800187a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187aa  jmp     loc_180018872
0x1800187af  mov     [rsp+0F8h+var_88], 0
0x1800187b8  mov     [rsp+0F8h+var_80], 0
0x1800187c1  mov     [rsp+0F8h+var_78], 0
0x1800187cd  lea     r8, [rsp+0F8h+var_88]
0x1800187d2  mov     edx, 299h
0x1800187d7  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800187dc  mov     ebx, eax
0x1800187de  test    eax, eax
0x1800187e0  jns     short loc_180018800
0x1800187e2  mov     rcx, [rsp+0F8h]; this
0x1800187ea  mov     r9d, eax; char *
0x1800187ed  lea     r8, aPcshellShellPe_1; "pcshell\\shell\\performancetracehandler"...
0x1800187f4  mov     edx, 77h ; 'w'; void *
0x1800187f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187fe  jmp     short loc_180018867
0x180018800  mov     [rsp+0F8h+var_70], 0
0x18001880c  mov     [rsp+0F8h+var_68], 0
0x180018818  mov     [rsp+0F8h+var_60], 0
0x180018824  lea     r8, [rsp+0F8h+var_70]
0x18001882c  mov     edx, 29Ah
0x180018831  call    ?LoadResourceString@ShowFeedbackToastHandler@@AEAAJIAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; ShowFeedbackToastHandler::LoadResourceString(uint,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x180018836  mov     ebx, eax
0x180018838  test    eax, eax
0x18001883a  jns     short loc_180018886
0x18001883c  mov     rcx, [rsp+0F8h]; this
0x180018844  mov     r9d, eax; char *
0x180018847  lea     r8, aPcshellShellPe_1; "pcshell\\shell\\performancetracehandler"...
0x18001884e  mov     edx, 7Ah ; 'z'; void *
0x180018853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018858  nop
0x180018859  lea     rcx, [rsp+0F8h+var_70]
0x180018861  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018866  nop
0x180018867  lea     rcx, [rsp+0F8h+var_88]
0x18001886c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018871  nop
0x180018872  lea     rcx, [rsp+0F8h+var_58]
0x18001887a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001887f  mov     eax, ebx
0x180018881  jmp     loc_180018A54
0x180018886  lea     r9, [rdi+80h]
0x18001888d  mov     [rsp+0F8h+var_A8], r9
0x180018892  mov     [rsp+0F8h+var_B0], rdi
0x180018897  mov     rax, [rsp+0F8h+var_70]
0x18001889f  mov     [rsp+0F8h+var_B8], rax
0x1800188a4  mov     [rsp+0F8h+var_C0], r9
0x1800188a9  mov     [rsp+0F8h+var_C8], rdi
0x1800188ae  mov     rax, [rsp+0F8h+var_88]
0x1800188b3  mov     [rsp+0F8h+var_D0], rax
0x1800188b8  mov     rax, [rsp+0F8h+var_58]
0x1800188c0  mov     [rsp+0F8h+var_D8], rax
0x1800188c5  mov     r8, rdi
0x1800188c8  lea     rdx, aToastActivatio; "\n<toast activationType=\"background\""...
0x1800188cf  lea     rcx, [rsp+0F8h+arg_18]
0x1800188d7  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x1800188dc  nop
0x1800188dd  lea     rcx, [rsp+0F8h+arg_10]; this
0x1800188e5  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x1800188ea  nop
0x1800188eb  mov     rdx, [rsp+0F8h+arg_18]; unsigned __int16 *
0x1800188f3  lea     rcx, [rsp+0F8h+var_30]; this
0x1800188fb  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180018900  lea     rdx, [rsp+0F8h+var_30]
0x180018908  lea     rcx, [rsp+0F8h+arg_10]
0x180018910  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180018915  lea     rdx, [rsp+0F8h+arg_10]; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x18001891d  lea     rcx, [rsp+0F8h+arg_0]; this
0x180018925  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x18001892a  nop
0x18001892b  lea     rcx, [rsp+0F8h+var_38]
0x180018933  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180018938  mov     rcx, [rax]
0x18001893b  mov     rax, 430E23400h
0x180018945  add     rcx, rax
0x180018948  mov     [rsp+0F8h+var_40], rcx
0x180018950  lea     rdx, [rsp+0F8h+var_40]
0x180018958  lea     rcx, [rsp+0F8h+var_98]
0x18001895d  call    ??0?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@AEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Z; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180018962  nop
0x180018963  lea     rdx, [rsp+0F8h+var_98]
0x180018968  lea     rcx, [rsp+0F8h+arg_0]
0x180018970  call    ?ExpirationTime@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>> const &)
0x180018975  nop
0x180018976  lea     rcx, [rsp+0F8h+var_98]
0x18001897b  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180018980  lea     rdx, aWindowsSystemt; "Windows.SystemToast.Whesvc.Feedback"
0x180018987  lea     rcx, [rsp+0F8h+var_30]; this
0x18001898f  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180018994  lea     rdx, [rsp+0F8h+var_30]
0x18001899c  lea     rcx, [rsp+0F8h+var_90]; struct winrt::param::hstring *
0x1800189a1  call    ?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)
0x1800189a6  nop
0x1800189a7  lea     rdx, [rsp+0F8h+arg_0]
0x1800189af  lea     rcx, [rsp+0F8h+var_90]
0x1800189b4  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x1800189b9  nop
0x1800189ba  lea     rcx, [rsp+0F8h+var_90]
0x1800189bf  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800189c4  nop
0x1800189c5  lea     rcx, [rsp+0F8h+arg_0]
0x1800189cd  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800189d2  nop
0x1800189d3  lea     rcx, [rsp+0F8h+arg_10]
0x1800189db  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800189e0  nop
0x1800189e1  lea     rcx, [rsp+0F8h+arg_18]
0x1800189e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800189ee  nop
0x1800189ef  lea     rcx, [rsp+0F8h+var_70]
0x1800189f7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800189fc  nop
0x1800189fd  lea     rcx, [rsp+0F8h+var_88]
0x180018a02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018a07  nop
0x180018a08  lea     rcx, [rsp+0F8h+var_58]
0x180018a10  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018a15  xor     eax, eax
0x180018a17  jmp     short loc_180018A54
0x180018a19  lea     rcx, [rsp+0F8h+arg_18]
0x180018a21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018a26  nop
0x180018a27  lea     rcx, [rsp+0F8h+var_70]
0x180018a2f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018a34  nop
0x180018a35  lea     rcx, [rsp+0F8h+var_88]
0x180018a3a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018a3f  nop
0x180018a40  lea     rcx, [rsp+0F8h+var_58]
0x180018a48  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018a4d  mov     eax, dword ptr [rsp+0F8h+arg_0]
0x180018a54  mov     rbx, [rsp+0F8h+arg_8]
0x180018a5c  add     rsp, 0F0h
0x180018a63  pop     rdi
0x180018a64  retn
```
