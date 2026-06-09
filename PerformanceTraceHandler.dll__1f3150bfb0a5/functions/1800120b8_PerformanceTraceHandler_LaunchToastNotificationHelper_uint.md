# PerformanceTraceHandler::LaunchToastNotificationHelper(uint)

- ea: `0x1800120b8`
- end: `0x1800121f2`
- name: `?LaunchToastNotificationHelper@PerformanceTraceHandler@@AEAAXI@Z`
- size: `314`
- prototype: `void __fastcall(PerformanceTraceHandler *this, unsigned int)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012018`
- `0x180012068`
- `0x1800121f8`

## callees

- `0x18000b524`
- `0x1800100b8`
- `0x18001066c`
- `0x1800106e0`
- `0x180010a0c`
- `0x180010a38`
- `0x180010f20`
- `0x180011660`
- `0x1800120b8`
- `0x180012220`
- `0x1800127e0`
- `0x180012b0c`
- `0x180012b48`
- `0x180012c40`

## string_xrefs

- `0x180012137`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x18001214c`: `<toast scenario="systemDialog">\n            <visual>\n            <binding template="ToastGeneric">\n                <text id="1">%ws</text>\n            </binding>\n            </visual>\n            <actions>\n                <action id="1" activationType="Background" arguments="verbNotOk" content="Dismiss"/>\n            </actions>\n        </toast>`

## pseudocode

```c
void __fastcall PerformanceTraceHandler::LaunchToastNotificationHelper(PerformanceTraceHandler *this, unsigned int a2)
{
  __int64 v3; // rsi
  int v4; // edi
  unsigned __int16 v5; // r8
  int v6; // [rsp+20h] [rbp-50h]
  unsigned __int16 *v7; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v8[3]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  PerformanceTraceHandler *v11; // [rsp+90h] [rbp+20h] BYREF
  char v12; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v13; // [rsp+A8h] [rbp+38h] BYREF

  v11 = this;
  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((winrt::Windows::Data::Xml::Dom::XmlDocument *)&v12);
  v3 = 0;
  memset(v8, 0, sizeof(v8));
  v4 = -2147467259;
  v13 = 0;
  LOWORD(v11) = 0;
  if ( Windows::Internal::ResourceString::FindAndSize(
         (HINSTANCE)0x180000000LL,
         a2,
         v5,
         (const unsigned __int16 **)&v13,
         (unsigned __int16 *)&v11) )
  {
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           v8,
           v13,
           (unsigned __int16)v11);
    v3 = v8[0];
  }
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x14E,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v4,
      v6);
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v7,
    L"<toast scenario=\"systemDialog\">\n"
     "            <visual>\n"
     "            <binding template=\"ToastGeneric\">\n"
     "                <text id=\"1\">%ws</text>\n"
     "            </binding>\n"
     "            </visual>\n"
     "            <actions>\n"
     "                <action id=\"1\" activationType=\"Background\" arguments=\"verbNotOk\" content=\"Dismiss\"/>\n"
     "            </actions>\n"
     "        </toast>",
    v3);
  winrt::param::hstring::hstring((winrt::param::hstring *)v9, v7);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
    &v12,
    v9);
  winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
    (winrt::Windows::UI::Notifications::ToastNotification *)&v13,
    (const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)&v12);
  winrt::param::hstring::hstring((winrt::param::hstring *)v9, L"Microsoft.Windows.Explorer");
  winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier((const struct winrt::param::hstring *)&v11);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
    &v11,
    &v13);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v11);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v13);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v7);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v8);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v12);
}

```

## disassembly

```asm
0x1800120b8  mov     [rsp-18h+arg_8], rbx
0x1800120bd  mov     [rsp-18h+arg_0], rcx
0x1800120c2  push    rbp
0x1800120c3  push    rsi
0x1800120c4  push    rdi
0x1800120c5  mov     rbp, rsp
0x1800120c8  sub     rsp, 70h
0x1800120cc  mov     ebx, edx
0x1800120ce  lea     rcx, [rbp+arg_10]; this
0x1800120d2  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x1800120d7  nop
0x1800120d8  xor     esi, esi
0x1800120da  mov     [rbp+var_38], rsi
0x1800120de  mov     [rbp+var_30], rsi
0x1800120e2  mov     [rbp+var_28], rsi
0x1800120e6  mov     edi, 80004005h
0x1800120eb  mov     [rbp+arg_18], rsi
0x1800120ef  xor     eax, eax
0x1800120f1  mov     word ptr [rbp+arg_0], ax
0x1800120f5  lea     rax, [rbp+arg_0]
0x1800120f9  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800120fe  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x180012102  mov     edx, ebx; unsigned int
0x180012104  lea     rcx, cs:180000000h; hModule
0x18001210b  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180012110  test    al, al
0x180012112  jz      short loc_18001212C
0x180012114  movzx   r8d, word ptr [rbp+arg_0]
0x180012119  mov     rdx, [rbp+arg_18]
0x18001211d  lea     rcx, [rbp+var_38]
0x180012121  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180012126  mov     edi, eax
0x180012128  mov     rsi, [rbp+var_38]
0x18001212c  mov     rcx, [rbp+18h]; this
0x180012130  test    edi, edi
0x180012132  jns     short loc_180012149
0x180012134  mov     r9d, edi; char *
0x180012137  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001213e  mov     edx, 14Eh; void *
0x180012143  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012149  mov     r8, rsi
0x18001214c  lea     rdx, aToastScenarioS_3; "<toast scenario=\"systemDialog\">\n    "...
0x180012153  lea     rcx, [rbp+var_40]
0x180012157  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x18001215c  nop
0x18001215d  mov     rdx, [rbp+var_40]; unsigned __int16 *
0x180012161  lea     rcx, [rbp+var_20]; this
0x180012165  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18001216a  lea     rdx, [rbp+var_20]
0x18001216e  lea     rcx, [rbp+arg_10]
0x180012172  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180012177  lea     rdx, [rbp+arg_10]; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x18001217b  lea     rcx, [rbp+arg_18]; this
0x18001217f  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x180012184  nop
0x180012185  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Explorer"
0x18001218c  lea     rcx, [rbp+var_20]; this
0x180012190  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012195  lea     rdx, [rbp+var_20]
0x180012199  lea     rcx, [rbp+arg_0]; struct winrt::param::hstring *
0x18001219d  call    ?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)
0x1800121a2  nop
0x1800121a3  lea     rdx, [rbp+arg_18]
0x1800121a7  lea     rcx, [rbp+arg_0]
0x1800121ab  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x1800121b0  nop
0x1800121b1  lea     rcx, [rbp+arg_0]
0x1800121b5  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800121ba  nop
0x1800121bb  lea     rcx, [rbp+arg_18]
0x1800121bf  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800121c4  nop
0x1800121c5  lea     rcx, [rbp+var_40]
0x1800121c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800121ce  nop
0x1800121cf  lea     rcx, [rbp+var_38]
0x1800121d3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800121d8  nop
0x1800121d9  lea     rcx, [rbp+arg_10]
0x1800121dd  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x1800121e2  mov     rbx, [rsp+70h+arg_8]
0x1800121ea  add     rsp, 70h
0x1800121ee  pop     rdi
0x1800121ef  pop     rsi
0x1800121f0  pop     rbp
0x1800121f1  retn
```
