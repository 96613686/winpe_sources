# WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x180016b6c`
- end: `0x180016e38`
- name: `?LaunchToastNotificationWithFeedbackHubButton@WhesvcUXHandler@@AEAAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@00@Z`
- size: `716`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001642c`

## callees

- `0x180002c00`
- `0x180009508`
- `0x18000b524`
- `0x1800100b8`
- `0x180010278`
- `0x180010424`
- `0x18001066c`
- `0x1800106e0`
- `0x180010a0c`
- `0x180010a38`
- `0x180010f20`
- `0x18001161c`
- `0x180012220`
- `0x1800127e0`
- `0x180012c9c`
- `0x180012d18`
- `0x18001309c`
- `0x1800161f8`
- `0x180016b6c`
- `0x180017c6c`

## string_xrefs

- `0x180016d19`: `<toast scenario="systemDialog" activationType="Protocol" launch="%ws">\n                <visual lang="en-US">\n                <binding template="ToastGeneric">\n                    <text id="1">%ws</text>\n                </binding>\n                </visual>\n                <actions>\n                    <action id="1" activationType="Protocol" arguments="%ws" content="%ws"/>\n                    <action id="2" activationType="Background" arguments="verbNotOk" content="%ws"/>\n               `
- `0x180016c3d`: `<toast scenario="systemDialog">\n                <visual lang="en-US">\n                <binding template="ToastGeneric">\n                    <text id="1">%ws</text>\n                </binding>\n                </visual>\n                <actions>\n                    <action id="1" activationType="Protocol" arguments="%ws" content="%ws"/>\n                    <action id="2" activationType="Background" arguments="verbNotOk" content="%ws"/>\n                </actions>\n            </toast>`

## pseudocode

```c
__int64 __fastcall WhesvcUXHandler::LaunchToastNotificationWithFeedbackHubButton(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  WhesvcUXHandler *v7; // rcx
  void *v8; // rax
  int *v9; // rdx
  _QWORD *v10; // r9
  WhesvcUXHandler *v11; // rcx
  void *v12; // rax
  int *v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // r8
  __int64 v17; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int16 *v18; // [rsp+48h] [rbp-90h] BYREF
  int v19; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v20[8]; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-78h] BYREF
  _BYTE v22[32]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v23[8]; // [rsp+88h] [rbp-50h] BYREF
  _QWORD Src[3]; // [rsp+90h] [rbp-48h] BYREF
  unsigned __int64 v25; // [rsp+A8h] [rbp-30h]

  winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument((winrt::Windows::Data::Xml::Dom::XmlDocument *)&v19);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl'::`2'::impl) )
  {
    std::wstring::wstring(
      Src,
      L"Feedback-Hub://?contextid=1369&amp;feedbackType=2&amp;tabid=2&amp;newFeedback=true&amp;tag=Hotkey");
    v17 = 0;
    if ( (int)WhesvcUXHandler::GetDummyFileToken(v11, (struct winrt::hstring *)&v17) >= 0 )
    {
      v12 = (void *)std::wstring::append(Src, L"&amp;files=");
      if ( v17 )
        v13 = *(int **)(v17 + 16);
      else
        v13 = &dword_18001E1D4;
      std::wstring::append(v12, v13);
    }
    if ( v25 > 7 )
    {
      v14 = (_QWORD *)Src[0];
      v15 = (_QWORD *)Src[0];
    }
    else
    {
      v14 = Src;
      v15 = Src;
    }
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v18,
      L"<toast scenario=\"systemDialog\" activationType=\"Protocol\" launch=\"%ws\">\n"
       "                <visual lang=\"en-US\">\n"
       "                <binding template=\"ToastGeneric\">\n"
       "                    <text id=\"1\">%ws</text>\n"
       "                </binding>\n"
       "                </visual>\n"
       "                <actions>\n"
       "                    <action id=\"1\" activationType=\"Protocol\" arguments=\"%ws\" content=\"%ws\"/>\n"
       "                    <action id=\"2\" activationType=\"Background\" arguments=\"verbNotOk\" content=\"%ws\"/>\n"
       "                </actions>\n"
       "            </toast>",
      v15,
      *a2,
      v14,
      *a3,
      *a4);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, v18);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
      &v19,
      v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
  }
  else
  {
    std::wstring::wstring(
      Src,
      L"Feedback-Hub://?contextid=1369&amp;feedbackType=2&amp;tabid=2&amp;newFeedback=true&amp;tag=Hotkey");
    v17 = 0;
    if ( (int)WhesvcUXHandler::GetDummyFileToken(v7, (struct winrt::hstring *)&v17) >= 0 )
    {
      v8 = (void *)std::wstring::append(Src, L"&amp;files=");
      if ( v17 )
        v9 = *(int **)(v17 + 16);
      else
        v9 = &dword_18001E1D4;
      std::wstring::append(v8, v9);
    }
    v10 = Src;
    if ( v25 > 7 )
      v10 = (_QWORD *)Src[0];
    wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v18,
      L"<toast scenario=\"systemDialog\">\n"
       "                <visual lang=\"en-US\">\n"
       "                <binding template=\"ToastGeneric\">\n"
       "                    <text id=\"1\">%ws</text>\n"
       "                </binding>\n"
       "                </visual>\n"
       "                <actions>\n"
       "                    <action id=\"1\" activationType=\"Protocol\" arguments=\"%ws\" content=\"%ws\"/>\n"
       "                    <action id=\"2\" activationType=\"Background\" arguments=\"verbNotOk\" content=\"%ws\"/>\n"
       "                </actions>\n"
       "            </toast>",
      *a2,
      v10,
      *a3,
      *a4);
    winrt::param::hstring::hstring((winrt::param::hstring *)v22, v18);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(
      &v19,
      v22);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
  }
  std::wstring::_Tidy_deallocate(Src);
  winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(
    (winrt::Windows::UI::Notifications::ToastNotification *)v20,
    (const struct winrt::Windows::Data::Xml::Dom::XmlDocument *)&v19);
  winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"Microsoft.Windows.Explorer");
  winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier((const struct winrt::param::hstring *)v21);
  v17 = *(_QWORD *)winrt::clock::now(v23) + 300000000LL;
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
    &v18,
    &v17);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(
    v20,
    &v18);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v18);
  winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(
    v21,
    v20);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v21);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(v20);
  winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(&v19);
  return 0;
}

```

## disassembly

```asm
0x180016b6c  push    rbx
0x180016b6e  push    rsi
0x180016b6f  push    rdi
0x180016b70  sub     rsp, 0C0h
0x180016b77  mov     rax, cs:__security_cookie
0x180016b7e  xor     rax, rsp
0x180016b81  mov     [rsp+0D8h+var_28], rax
0x180016b89  mov     rsi, r9
0x180016b8c  mov     rdi, r8
0x180016b8f  mov     rbx, rdx
0x180016b92  lea     rcx, [rsp+0D8h+var_88]; this
0x180016b97  call    ??0XmlDocument@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlDocument::XmlDocument(void)
0x180016b9c  nop
0x180016b9d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes2D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes2D>::GetImpl(void)'::`2'::impl
0x180016ba4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::__private_IsEnabled(void)
0x180016ba9  lea     rdx, aFeedbackHubCon; "Feedback-Hub://?contextid=1369&amp;feed"...
0x180016bb0  lea     rcx, [rsp+0D8h+Src]
0x180016bb8  test    al, al
0x180016bba  jnz     loc_180016C89
0x180016bc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016bc5  nop
0x180016bc6  mov     [rsp+0D8h+var_98], 0
0x180016bcf  lea     rdx, [rsp+0D8h+var_98]; struct winrt::hstring *
0x180016bd4  call    ?GetDummyFileToken@WhesvcUXHandler@@AEAAJAEAUhstring@winrt@@@Z; WhesvcUXHandler::GetDummyFileToken(winrt::hstring &)
0x180016bd9  test    eax, eax
0x180016bdb  js      short loc_180016C10
0x180016bdd  lea     rdx, aAmpFiles; "&amp;files="
0x180016be4  lea     rcx, [rsp+0D8h+Src]; Src
0x180016bec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016bf1  mov     rcx, [rsp+0D8h+var_98]
0x180016bf6  test    rcx, rcx
0x180016bf9  jz      short loc_180016C01
0x180016bfb  mov     rdx, [rcx+10h]
0x180016bff  jmp     short loc_180016C08
0x180016c01  lea     rdx, dword_18001E1D4; void *
0x180016c08  mov     rcx, rax; Src
0x180016c0b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016c10  mov     rax, [rsi]
0x180016c13  mov     rcx, [rdi]
0x180016c16  lea     r9, [rsp+0D8h+Src]
0x180016c1e  cmp     [rsp+0D8h+var_30], 7
0x180016c27  cmova   r9, [rsp+0D8h+Src]
0x180016c30  mov     [rsp+0D8h+var_B0], rax
0x180016c35  mov     [rsp+0D8h+var_B8], rcx
0x180016c3a  mov     r8, [rbx]
0x180016c3d  lea     rdx, aToastScenarioS; "<toast scenario=\"systemDialog\">\n    "...
0x180016c44  lea     rcx, [rsp+0D8h+var_90]
0x180016c49  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180016c4e  nop
0x180016c4f  mov     rdx, [rsp+0D8h+var_90]; unsigned __int16 *
0x180016c54  lea     rcx, [rsp+0D8h+var_70]; this
0x180016c59  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180016c5e  lea     rdx, [rsp+0D8h+var_70]
0x180016c63  lea     rcx, [rsp+0D8h+var_88]
0x180016c68  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180016c6d  nop
0x180016c6e  lea     rcx, [rsp+0D8h+var_90]
0x180016c73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016c78  nop
0x180016c79  lea     rcx, [rsp+0D8h+var_98]
0x180016c7e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016c83  nop
0x180016c84  jmp     loc_180016D60
0x180016c89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180016c8e  nop
0x180016c8f  mov     [rsp+0D8h+var_98], 0
0x180016c98  lea     rdx, [rsp+0D8h+var_98]; struct winrt::hstring *
0x180016c9d  call    ?GetDummyFileToken@WhesvcUXHandler@@AEAAJAEAUhstring@winrt@@@Z; WhesvcUXHandler::GetDummyFileToken(winrt::hstring &)
0x180016ca2  test    eax, eax
0x180016ca4  js      short loc_180016CD9
0x180016ca6  lea     rdx, aAmpFiles; "&amp;files="
0x180016cad  lea     rcx, [rsp+0D8h+Src]; Src
0x180016cb5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016cba  mov     rcx, [rsp+0D8h+var_98]
0x180016cbf  test    rcx, rcx
0x180016cc2  jz      short loc_180016CCA
0x180016cc4  mov     rdx, [rcx+10h]
0x180016cc8  jmp     short loc_180016CD1
0x180016cca  lea     rdx, dword_18001E1D4; void *
0x180016cd1  mov     rcx, rax; Src
0x180016cd4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180016cd9  mov     rcx, [rsi]
0x180016cdc  mov     rdx, [rdi]
0x180016cdf  mov     r9, [rbx]
0x180016ce2  cmp     [rsp+0D8h+var_30], 7
0x180016ceb  ja      short loc_180016CFF
0x180016ced  lea     rax, [rsp+0D8h+Src]
0x180016cf5  lea     r8, [rsp+0D8h+Src]
0x180016cfd  jmp     short loc_180016D0A
0x180016cff  mov     rax, [rsp+0D8h+Src]
0x180016d07  mov     r8, rax
0x180016d0a  mov     [rsp+0D8h+var_A8], rcx
0x180016d0f  mov     [rsp+0D8h+var_B0], rdx
0x180016d14  mov     [rsp+0D8h+var_B8], rax
0x180016d19  lea     rdx, aToastScenarioS_2; "<toast scenario=\"systemDialog\" activa"...
0x180016d20  lea     rcx, [rsp+0D8h+var_90]
0x180016d25  call    ??$str_printf@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,...)
0x180016d2a  nop
0x180016d2b  mov     rdx, [rsp+0D8h+var_90]; unsigned __int16 *
0x180016d30  lea     rcx, [rsp+0D8h+var_70]; this
0x180016d35  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180016d3a  lea     rdx, [rsp+0D8h+var_70]
0x180016d3f  lea     rcx, [rsp+0D8h+var_88]
0x180016d44  call    ?LoadXml@?$consume_Windows_Data_Xml_Dom_IXmlDocumentIO@UXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocumentIO<winrt::Windows::Data::Xml::Dom::XmlDocument>::LoadXml(winrt::param::hstring const &)
0x180016d49  nop
0x180016d4a  lea     rcx, [rsp+0D8h+var_90]
0x180016d4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016d54  nop
0x180016d55  lea     rcx, [rsp+0D8h+var_98]
0x180016d5a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016d5f  nop
0x180016d60  lea     rcx, [rsp+0D8h+Src]
0x180016d68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180016d6d  lea     rdx, [rsp+0D8h+var_88]; struct winrt::Windows::Data::Xml::Dom::XmlDocument *
0x180016d72  lea     rcx, [rsp+0D8h+var_80]; this
0x180016d77  call    ??0ToastNotification@Notifications@UI@Windows@winrt@@QEAA@AEBUXmlDocument@Dom@Xml@Data@34@@Z; winrt::Windows::UI::Notifications::ToastNotification::ToastNotification(winrt::Windows::Data::Xml::Dom::XmlDocument const &)
0x180016d7c  nop
0x180016d7d  lea     rdx, aMicrosoftWindo; "Microsoft.Windows.Explorer"
0x180016d84  lea     rcx, [rsp+0D8h+var_70]; this
0x180016d89  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180016d8e  lea     rdx, [rsp+0D8h+var_70]
0x180016d93  lea     rcx, [rsp+0D8h+var_78]; struct winrt::param::hstring *
0x180016d98  call    ?CreateToastNotifier@ToastNotificationManager@Notifications@UI@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::UI::Notifications::ToastNotificationManager::CreateToastNotifier(winrt::param::hstring const &)
0x180016d9d  nop
0x180016d9e  lea     rcx, [rsp+0D8h+var_50]
0x180016da6  call    ?now@clock@winrt@@SA?AV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@XZ; winrt::clock::now(void)
0x180016dab  mov     rcx, [rax]
0x180016dae  add     rcx, 11E1A300h
0x180016db5  mov     [rsp+0D8h+var_98], rcx
0x180016dba  lea     rdx, [rsp+0D8h+var_98]
0x180016dbf  lea     rcx, [rsp+0D8h+var_90]
0x180016dc4  call    ??0?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@AEBV?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Z; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180016dc9  nop
0x180016dca  lea     rdx, [rsp+0D8h+var_90]
0x180016dcf  lea     rcx, [rsp+0D8h+var_80]
0x180016dd4  call    ?ExpirationTime@?$consume_Windows_UI_Notifications_IToastNotification@UIToastNotification@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBU?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotification<winrt::Windows::UI::Notifications::IToastNotification>::ExpirationTime(winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>> const &)
0x180016dd9  nop
0x180016dda  lea     rcx, [rsp+0D8h+var_90]
0x180016ddf  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016de4  lea     rdx, [rsp+0D8h+var_80]
0x180016de9  lea     rcx, [rsp+0D8h+var_78]
0x180016dee  call    ?Show@?$consume_Windows_UI_Notifications_IToastNotifier@UIToastNotifier@Notifications@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUToastNotification@Notifications@UI@Windows@3@@Z; winrt::impl::consume_Windows_UI_Notifications_IToastNotifier<winrt::Windows::UI::Notifications::IToastNotifier>::Show(winrt::Windows::UI::Notifications::ToastNotification const &)
0x180016df3  nop
0x180016df4  lea     rcx, [rsp+0D8h+var_78]
0x180016df9  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016dfe  nop
0x180016dff  lea     rcx, [rsp+0D8h+var_80]
0x180016e04  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016e09  nop
0x180016e0a  lea     rcx, [rsp+0D8h+var_88]
0x180016e0f  call    ??1?$IReference@V?$time_point@Uclock@winrt@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::~IReference<std::chrono::time_point<winrt::clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(void)
0x180016e14  xor     eax, eax
0x180016e16  jmp     short loc_180016E1C
0x180016e18  mov     eax, [rsp+0D8h+var_88]
0x180016e1c  mov     rcx, [rsp+0D8h+var_28]
0x180016e24  xor     rcx, rsp; StackCookie
0x180016e27  call    __security_check_cookie
0x180016e2c  add     rsp, 0C0h
0x180016e33  pop     rdi
0x180016e34  pop     rsi
0x180016e35  pop     rbx
0x180016e36  retn
```
