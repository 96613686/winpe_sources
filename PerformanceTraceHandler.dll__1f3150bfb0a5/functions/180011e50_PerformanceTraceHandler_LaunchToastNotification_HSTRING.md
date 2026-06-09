# PerformanceTraceHandler::LaunchToastNotification(HSTRING__ *)

- ea: `0x180011e50`
- end: `0x180012012`
- name: `?LaunchToastNotification@PerformanceTraceHandler@@AEAAJPEAUHSTRING__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *this, HSTRING)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001124c`

## callees

- `0x180002c00`
- `0x18000b524`
- `0x1800100b8`
- `0x180010278`
- `0x180010424`
- `0x18001066c`
- `0x1800106e0`
- `0x180010a0c`
- `0x180010a38`
- `0x180010a90`
- `0x180010ca4`
- `0x180010f20`
- `0x18001161c`
- `0x180011e50`
- `0x180012220`
- `0x1800127e0`
- `0x180012c9c`
- `0x180012d18`
- `0x18001309c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011eb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011eb0`

## string_xrefs

- `0x180011ed5`: `<toast scenario="systemDialog">\n            <visual>\n            <binding template="ToastGeneric">\n                <text id="1">A trace has been successfully saved to %%LOCALAPPDATA%%\Traces.</text>\n            </binding>\n            </visual>\n            <actions>\n                <action id="1" activationType="Protocol" arguments="%ws" content="Launch Feedback Hub"/>\n                <action id="2" activationType="Background" arguments="verbNotOk" content="Dismiss"/>\n            </actio`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::LaunchToastNotification(PerformanceTraceHandler *this, HSTRING a2)
{
  void *v4; // rbx
  WCHAR *StringRawBuffer; // rax
  _QWORD *v6; // r8
  int v8; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-80h] BYREF
  __int64 v10; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-70h] BYREF
  _BYTE v12[8]; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 *v13; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v14[8]; // [rsp+50h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-50h] BYREF
  _QWORD Src[4]; // [rsp+78h] [rbp-30h] BYREF

  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((winrt::Windows::Data::Xml::Dom::XmlDocument *)v9);
  std::wstring::wstring(Src, L"Feedback-Hub://?tabID=2&amp;newFeedback=True&amp;feedbackType=2&amp;ContextId=67");
  v4 = (void *)std::wstring::append(Src, L"&amp;files=");
  StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(a2, 0);
  std::wstring::append(v4, StringRawBuffer);
  v6 = Src;
  if ( Src[3] > 7u )
    v6 = (_QWORD *)Src[0];
  wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v13,
    L"<toast scenario=\"systemDialog\">\n"
     "            <visual>\n"
     "            <binding template=\"ToastGeneric\">\n"
     "                <text id=\"1\">A trace has been successfully saved to %%LOCALAPPDATA%%\\Traces.</text>\n"
     "            </binding>\n"
     "            </visual>\n"
     "            <actions>\n"
     "                <action id=\"1\" activationType=\"Protocol\" arguments=\"%ws\" content=\"Launch Feedback Hub\"/>\n"
     "                <action id=\"2\" activationType=\"Background\" arguments=\"verbNotOk\" content=\"Dismiss\"/>\n"
     "            </actions>\n"
     "        </toast>",
    v6);
  winrt::param::hstring::hstring((winrt::param::hstring *)v15, v13);
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
    v9,
    v15);
  winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
    (winrt::Windows::UI::Notifications::ToastNotification *)&v8,
    (const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)v9);
  winrt::param::hstring::hstring((winrt::param::hstring *)v15, L"Microsoft.Windows.Explorer");
  winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier((const struct winrt::param::hstring *)v12);
  v10 = *(_QWORD *)winrt::clock::now(v14) + 300000000LL;
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
    v11,
    &v10);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(
    &v8,
    v11);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v11);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
    v12,
    &v8);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                          (char *)this + 192,
                          &v10)
           + 283LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(&v10);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v12);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v13);
  std::wstring::_Tidy_deallocate(Src);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v9);
  return 0;
}

```

## disassembly

```asm
0x180011e50  mov     [rsp+arg_10], rbx
0x180011e55  mov     [rsp+arg_18], rsi
0x180011e5a  push    rdi
0x180011e5b  sub     rsp, 0A0h
0x180011e62  mov     rax, cs:__security_cookie
0x180011e69  xor     rax, rsp
0x180011e6c  mov     [rsp+0A8h+var_10], rax
0x180011e74  mov     rdi, rdx
0x180011e77  mov     rsi, rcx
0x180011e7a  lea     rcx, [rsp+0A8h+var_80]; this
0x180011e7f  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x180011e84  nop
0x180011e85  lea     rdx, aFeedbackHubTab; "Feedback-Hub://?tabID=2&amp;newFeedback"...
0x180011e8c  lea     rcx, [rsp+0A8h+Src]
0x180011e91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011e96  nop
0x180011e97  lea     rdx, aAmpFiles; "&amp;files="
0x180011e9e  lea     rcx, [rsp+0A8h+Src]; Src
0x180011ea3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011ea8  mov     rbx, rax
0x180011eab  xor     edx, edx; length
0x180011ead  mov     rcx, rdi; string
0x180011eb0  call    cs:__imp_WindowsGetStringRawBuffer
0x180011eb6  mov     rdx, rax; void *
0x180011eb9  mov     rcx, rbx; Src
0x180011ebc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180011ec1  lea     r8, [rsp+0A8h+Src]
0x180011ec6  cmp     [rsp+0A8h+var_18], 7
0x180011ecf  cmova   r8, [rsp+0A8h+Src]
0x180011ed5  lea     rdx, aToastScenarioS_1; "<toast scenario=\"systemDialog\">\n    "...
0x180011edc  lea     rcx, [rsp+0A8h+var_60]
0x180011ee1  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180011ee6  nop
0x180011ee7  mov     rdx, [rsp+0A8h+var_60]; unsigned __int16 *
0x180011eec  lea     rcx, [rsp+0A8h+var_50]; this
0x180011ef1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180011ef6  lea     rdx, [rsp+0A8h+var_50]
0x180011efb  lea     rcx, [rsp+0A8h+var_80]
0x180011f00  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180011f05  lea     rdx, [rsp+0A8h+var_80]; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x180011f0a  lea     rcx, [rsp+0A8h+var_88]; this
0x180011f0f  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x180011f14  nop
0x180011f15  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Explorer"
0x180011f1c  lea     rcx, [rsp+0A8h+var_50]; this
0x180011f21  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180011f26  lea     rdx, [rsp+0A8h+var_50]
0x180011f2b  lea     rcx, [rsp+0A8h+var_68]; struct winrt::param::hstring *
0x180011f30  call    ?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)
0x180011f35  nop
0x180011f36  lea     rcx, [rsp+0A8h+var_58]
0x180011f3b  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180011f40  mov     rcx, [rax]
0x180011f43  add     rcx, 11E1A300h
0x180011f4a  mov     [rsp+0A8h+var_78], rcx
0x180011f4f  lea     rdx, [rsp+0A8h+var_78]
0x180011f54  lea     rcx, [rsp+0A8h+var_70]
0x180011f59  call    ??0?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@AEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Z; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180011f5e  nop
0x180011f5f  lea     rdx, [rsp+0A8h+var_70]
0x180011f64  lea     rcx, [rsp+0A8h+var_88]
0x180011f69  call    ?ExpirationTime@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>> const &)
0x180011f6e  nop
0x180011f6f  lea     rcx, [rsp+0A8h+var_70]
0x180011f74  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180011f79  lea     rdx, [rsp+0A8h+var_88]
0x180011f7e  lea     rcx, [rsp+0A8h+var_68]
0x180011f83  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x180011f88  lea     rcx, [rsi+0C0h]
0x180011f8f  lea     rdx, [rsp+0A8h+var_78]
0x180011f94  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011f99  mov     rcx, [rax]
0x180011f9c  mov     byte ptr [rcx+11Bh], 1
0x180011fa3  lea     rcx, [rsp+0A8h+var_78]
0x180011fa8  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180011fad  nop
0x180011fae  lea     rcx, [rsp+0A8h+var_68]
0x180011fb3  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180011fb8  nop
0x180011fb9  lea     rcx, [rsp+0A8h+var_88]
0x180011fbe  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180011fc3  nop
0x180011fc4  lea     rcx, [rsp+0A8h+var_60]
0x180011fc9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011fce  nop
0x180011fcf  lea     rcx, [rsp+0A8h+Src]
0x180011fd4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011fd9  nop
0x180011fda  lea     rcx, [rsp+0A8h+var_80]
0x180011fdf  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180011fe4  xor     eax, eax
0x180011fe6  jmp     short loc_180011FEC
0x180011fe8  mov     eax, [rsp+0A8h+var_88]
0x180011fec  mov     rcx, [rsp+0A8h+var_10]
0x180011ff4  xor     rcx, rsp; StackCookie
0x180011ff7  call    __security_check_cookie
0x180011ffc  lea     r11, [rsp+0A8h+var_8]
0x180012004  mov     rbx, [r11+20h]
0x180012008  mov     rsi, [r11+28h]
0x18001200c  mov     rsp, r11
0x18001200f  pop     rdi
0x180012010  retn
```
