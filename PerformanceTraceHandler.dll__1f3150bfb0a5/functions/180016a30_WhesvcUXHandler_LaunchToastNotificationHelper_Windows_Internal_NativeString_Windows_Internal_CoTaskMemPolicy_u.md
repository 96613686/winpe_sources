# WhesvcUXHandler::LaunchToastNotificationHelper(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x180016a30`
- end: `0x180016b64`
- name: `?LaunchToastNotificationHelper@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@0@Z`
- size: `308`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800166a0`
- `0x180016868`

## callees

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
- `0x18001309c`
- `0x180016a30`

## string_xrefs

- `0x180016a56`: `<toast scenario="systemDialog">\n            <visual lang="en-US">\n            <binding template="ToastGeneric">\n                <text id="1">%ws</text>\n            </binding>\n            </visual>\n            <actions>\n                <action id="1" activationType="Background" arguments="verbNotOk" content="%ws"/>\n            </actions>\n        </toast>`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::LaunchToastNotificationHelper(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  const char *v5; // r9
  __int64 result; // rax
  __int64 v7; // [rsp+20h] [rbp-58h] BYREF
  __int64 v8; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int16 *v9; // [rsp+30h] [rbp-48h] BYREF
  __int64 v10; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v11[8]; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v12[48]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF
  __int64 v15; // [rsp+98h] [rbp+20h] BYREF

  v14 = a1;
  try
  {
    winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((winrt::Windows::Data::Xml::Dom::XmlDocument *)&v15);
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v9,
      (__int64)L"<toast scenario=\"systemDialog\">\n"
                "            <visual lang=\"en-US\">\n"
                "            <binding template=\"ToastGeneric\">\n"
                "                <text id=\"1\">%ws</text>\n"
                "            </binding>\n"
                "            </visual>\n"
                "            <actions>\n"
                "                <action id=\"1\" activationType=\"Background\" arguments=\"verbNotOk\" content=\"%ws\"/>"
                "\n"
                "            </actions>\n"
                "        </toast>",
      *a2,
      *a3);
    winrt::param::hstring::hstring((winrt::param::hstring *)v12, v9);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
      &v15,
      v12);
    winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
      (winrt::Windows::UI::Notifications::ToastNotification *)&v14,
      (const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)&v15);
    v10 = *(_QWORD *)winrt::clock::now(v11) + 300000000LL;
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
      &v7,
      &v10);
    winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(
      &v14,
      &v7);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v7);
    winrt::param::hstring::hstring((winrt::param::hstring *)v12, L"Microsoft.Windows.Explorer");
    winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(
      (const struct winrt::param::hstring *)&v8,
      (__int64)v12);
    winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
      &v8,
      &v14);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v8);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v14);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v9);
    winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v15);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v14) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x114,
                     (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\whesvcuxhandler.cpp",
                     v5);
    return (unsigned int)v14;
  }
  return result;
}

```

## disassembly

```asm
0x180016a30  mov     rax, rsp
0x180016a33  mov     [rax+10h], rbx
0x180016a37  mov     [rax+8], rcx
0x180016a3b  push    rdi
0x180016a3c  sub     rsp, 70h
0x180016a40  mov     rbx, r8
0x180016a43  mov     rdi, rdx
0x180016a46  lea     rcx, [rax+20h]; this
0x180016a4a  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x180016a4f  nop
0x180016a50  mov     r9, [rbx]
0x180016a53  mov     r8, [rdi]
0x180016a56  lea     rdx, aToastScenarioS_0; "<toast scenario=\"systemDialog\">\n    "...
0x180016a5d  lea     rcx, [rsp+78h+var_48]
0x180016a62  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180016a67  nop
0x180016a68  mov     rdx, [rsp+78h+var_48]; unsigned __int16 *
0x180016a6d  lea     rcx, [rsp+78h+var_30]; this
0x180016a72  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180016a77  lea     rdx, [rsp+78h+var_30]
0x180016a7c  lea     rcx, [rsp+78h+arg_18]
0x180016a84  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180016a89  lea     rdx, [rsp+78h+arg_18]; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x180016a91  lea     rcx, [rsp+78h+arg_0]; this
0x180016a99  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x180016a9e  nop
0x180016a9f  lea     rcx, [rsp+78h+var_38]
0x180016aa4  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180016aa9  mov     rcx, [rax]
0x180016aac  add     rcx, 11E1A300h
0x180016ab3  mov     [rsp+78h+var_40], rcx
0x180016ab8  lea     rdx, [rsp+78h+var_40]
0x180016abd  lea     rcx, [rsp+78h+var_58]
0x180016ac2  call    ??0?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@AEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Z; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180016ac7  nop
0x180016ac8  lea     rdx, [rsp+78h+var_58]
0x180016acd  lea     rcx, [rsp+78h+arg_0]
0x180016ad5  call    ?ExpirationTime@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>> const &)
0x180016ada  nop
0x180016adb  lea     rcx, [rsp+78h+var_58]
0x180016ae0  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016ae5  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Explorer"
0x180016aec  lea     rcx, [rsp+78h+var_30]; this
0x180016af1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180016af6  lea     rdx, [rsp+78h+var_30]
0x180016afb  lea     rcx, [rsp+78h+var_50]; struct winrt::param::hstring *
0x180016b00  call    ?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)
0x180016b05  nop
0x180016b06  lea     rdx, [rsp+78h+arg_0]
0x180016b0e  lea     rcx, [rsp+78h+var_50]
0x180016b13  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x180016b18  nop
0x180016b19  lea     rcx, [rsp+78h+var_50]
0x180016b1e  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016b23  nop
0x180016b24  lea     rcx, [rsp+78h+arg_0]
0x180016b2c  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016b31  nop
0x180016b32  lea     rcx, [rsp+78h+var_48]
0x180016b37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016b3c  nop
0x180016b3d  lea     rcx, [rsp+78h+arg_18]
0x180016b45  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016b4a  xor     eax, eax
0x180016b4c  jmp     short loc_180016B55
0x180016b4e  mov     eax, dword ptr [rsp+78h+arg_0]
0x180016b55  mov     rbx, [rsp+78h+arg_8]
0x180016b5d  add     rsp, 70h
0x180016b61  pop     rdi
0x180016b62  retn
```
