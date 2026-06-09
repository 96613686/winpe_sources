# PrintJobCleanUpUtil::LaunchStalePrintJobNotification(void)

- ea: `0x18000d424`
- end: `0x18000da5a`
- name: `?LaunchStalePrintJobNotification@PrintJobCleanUpUtil@@YAJXZ`
- size: `1590`
- prototype: `__int64 __fastcall(PrintJobCleanUpUtil *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000eee4`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180007118`
- `0x18000750c`
- `0x180009bf4`
- `0x18000a280`
- `0x18000a2d4`
- `0x18000a300`
- `0x18000a360`
- `0x18000a688`
- `0x18000aa20`
- `0x18000aaec`
- `0x18000ab28`
- `0x18000ab74`
- `0x18000b0b4`
- `0x18000b2a8`
- `0x18000b308`
- `0x18000ba9c`
- `0x18000bd68`
- `0x18000c120`
- `0x18000c344`
- `0x18000ca54`
- `0x18000cc58`
- `0x18000d22c`
- `0x18000d2e8`
- `0x18000d424`
- `0x18000e8e4`
- `0x18000ea58`
- `0x18000f26c`
- `0x18000f334`
- `0x180015a9c`
- `0x180015d18`
- `0x180018010`

## string_xrefs

- `0x18000d48d`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000d551`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000d58f`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000d869`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PrintJobCleanUpUtil::LaunchStalePrintJobNotification(PrintJobCleanUpUtil *this)
{
  int v1; // r15d
  struct _FILETIME *v2; // rax
  unsigned __int64 *v3; // r9
  int v4; // eax
  void (__fastcall ***v6)(_QWORD, __int64 *, int *); // rbx
  void (__fastcall ***v7)(_QWORD, __int64 *, int *); // rdi
  unsigned int v8; // r14d
  int v9; // r12d
  unsigned __int64 i; // rbx
  const unsigned __int16 *const *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rsi
  __int64 NamedItem; // rax
  __int64 v18; // rax
  winrt::Windows::Foundation::IUnknown *v19; // rcx
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  int v23[2]; // [rsp+20h] [rbp-118h] BYREF
  void (__fastcall ***v24)(_QWORD, __int64 *, int *); // [rsp+28h] [rbp-110h] BYREF
  void (__fastcall ***v25)(_QWORD, __int64 *, int *); // [rsp+30h] [rbp-108h] BYREF
  void (__fastcall ***v26)(_QWORD, __int64 *, int *); // [rsp+38h] [rbp-100h] BYREF
  void (__fastcall ***v27)(_QWORD, __int64 *, int *); // [rsp+40h] [rbp-F8h] BYREF
  int v28[2]; // [rsp+48h] [rbp-F0h] BYREF
  _BYTE v29[8]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v30[8]; // [rsp+58h] [rbp-E0h] BYREF
  struct PrintJobCleanUpUtil::StalePrintJobInfo *v31; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE v32[8]; // [rsp+68h] [rbp-D0h] BYREF
  _BYTE v33[8]; // [rsp+70h] [rbp-C8h] BYREF
  _BYTE *v34; // [rsp+78h] [rbp-C0h] BYREF
  int *v35; // [rsp+80h] [rbp-B8h] BYREF
  _BYTE v36[16]; // [rsp+88h] [rbp-B0h] BYREF
  _BYTE v37[32]; // [rsp+98h] [rbp-A0h] BYREF
  _BYTE v38[32]; // [rsp+B8h] [rbp-80h] BYREF
  _BYTE v39[32]; // [rsp+D8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v1 = 0;
  LODWORD(v25) = 0;
  wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(v36);
  v31 = 0;
  v2 = (struct _FILETIME *)wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator&(v36);
  v4 = PrintJobCleanUpUtil::CheckForStalePrintJobs(0, v2, &v31, v3);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)(unsigned int)v4,
      v23[0]);
  if ( !v31 )
  {
    wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(v36);
    return 0;
  }
  GetStalePrintJobNotificationToastContent(v28);
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v27 = 0;
  winrt::param::hstring::hstring((winrt::param::hstring *)v39, L"subgroup");
  winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::GetElementsByTagName(
    v28,
    &v26,
    v39);
  v8 = 0;
  v9 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::Size(&v26);
  while ( v8 != v9 )
  {
    winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::GetAt(
      &v26,
      &v24,
      v8);
    v16 = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(
            &v24,
            v23);
    winrt::param::hstring::hstring((winrt::param::hstring *)v38, L"id");
    NamedItem = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(
                  v16,
                  v29,
                  v38);
    v18 = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(
            NamedItem,
            v30);
    LOBYTE(v16) = winrt::operator==(v18, L"DocumentNames");
    winrt::handle_type<winrt::impl::hstring_traits>::close(v30);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v29);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v23);
    if ( (_BYTE)v16 )
    {
      if ( v6 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
      v6 = v24;
      v25 = v24;
      v19 = (winrt::Windows::Foundation::IUnknown *)&v25;
    }
    else
    {
      v20 = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(
              &v24,
              &v35);
      winrt::param::hstring::hstring((winrt::param::hstring *)v38, L"id");
      v21 = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(
              v20,
              &v34,
              v38);
      v22 = winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(
              v21,
              v33);
      LOBYTE(v20) = winrt::operator==(v22, L"SubmissionDates");
      winrt::handle_type<winrt::impl::hstring_traits>::close(v33);
      winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v34);
      winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v35);
      if ( !(_BYTE)v20 )
        goto LABEL_30;
      if ( v7 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v27);
      v7 = v24;
      v27 = v24;
      v19 = (winrt::Windows::Foundation::IUnknown *)&v27;
    }
    winrt::Windows::Foundation::IUnknown::add_ref(v19);
LABEL_30:
    v1 |= 2u;
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v24);
    ++v8;
  }
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v26);
  *(_QWORD *)v23 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v25, v23) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)0x8000FFFFLL,
      v23[0]);
  *(_QWORD *)v23 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v27, v23) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)0x8000FFFFLL,
      v23[0]);
  for ( i = 0; i < (unsigned __int64)v31; ++i )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v39, L"text");
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::CreateElement(
      v28,
      &v26,
      v39);
    v11 = (const unsigned __int16 *const *)wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](
                                             v36,
                                             i);
    winrt::param::hstring::hstring((winrt::param::hstring *)v37, *v11);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(
      &v26,
      v37);
    winrt::param::hstring::hstring((winrt::param::hstring *)v37, L"body");
    winrt::param::hstring::hstring((winrt::param::hstring *)v38, L"hint-style");
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(
      &v26,
      v38,
      v37);
    *(_QWORD *)v23 = 0;
    if ( v26 )
      (**v26)(v26, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNode>, v23);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(
      &v25,
      v29,
      v23);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v29);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v23);
    winrt::param::hstring::hstring((winrt::param::hstring *)v38, L"text");
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::CreateElement(
      v28,
      &v24,
      v38);
    v12 = wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](
            v36,
            i);
    FileTimeToLocalDateString(v39, *(_QWORD *)(v12 + 8));
    winrt::param::hstring::hstring((winrt::param::hstring *)v37);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(
      &v24,
      v37);
    std::wstring::_Tidy_deallocate(v39);
    winrt::param::hstring::hstring((winrt::param::hstring *)v37, L"body");
    winrt::param::hstring::hstring((winrt::param::hstring *)v39, L"hint-style");
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(
      &v24,
      v39,
      v37);
    *(_QWORD *)v23 = 0;
    if ( v24 )
      (**v24)(v24, winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNode>, v23);
    winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(
      &v27,
      v30,
      v23);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v30);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v23);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v24);
    winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v26);
  }
  v35 = v23;
  *(_QWORD *)v23 = *(_QWORD *)v28;
  winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)v23);
  v34 = v30;
  v13 = winrt::hstring::hstring((winrt::hstring *)v30, L"StalePrintJobNotificationGroup");
  v14 = winrt::hstring::hstring((winrt::hstring *)v29, L"StalePrintJobNotificationTag");
  ToastManager::ToastManager(v32, v14, v13, v23);
  v15 = ToastManager::ShowToast((ToastManager *)v32);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
      (const char *)(unsigned int)v15,
      v23[0]);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v32);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v27);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)&v25);
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation((winrt::Windows::Devices::Enumeration::IDeviceInformation *)v28);
  wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&void PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(v36);
  return 0;
}

```

## disassembly

```asm
0x18000d424  push    rbx
0x18000d426  push    rsi
0x18000d427  push    rdi
0x18000d428  push    r12
0x18000d42a  push    r14
0x18000d42c  push    r15
0x18000d42e  sub     rsp, 108h
0x18000d435  mov     rax, cs:__security_cookie
0x18000d43c  xor     rax, rsp
0x18000d43f  mov     [rsp+138h+var_40], rax
0x18000d447  xor     r15d, r15d
0x18000d44a  mov     dword ptr [rsp+138h+var_108], r15d
0x18000d44f  lea     rcx, [rsp+138h+var_B0]
0x18000d457  call    ??0?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(void)
0x18000d45c  nop
0x18000d45d  mov     [rsp+138h+var_D8], r15
0x18000d462  lea     rcx, [rsp+138h+var_B0]
0x18000d46a  call    ??I?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAPEAPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@XZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator&(void)
0x18000d46f  mov     rdx, rax; bool
0x18000d472  lea     r8, [rsp+138h+var_D8]; struct PrintJobCleanUpUtil::StalePrintJobInfo **
0x18000d477  xor     ecx, ecx; this
0x18000d479  call    ?CheckForStalePrintJobs@PrintJobCleanUpUtil@@YAJ_NPEAPEAUStalePrintJobInfo@1@PEA_K@Z; PrintJobCleanUpUtil::CheckForStalePrintJobs(bool,PrintJobCleanUpUtil::StalePrintJobInfo * *,unsigned __int64 *)
0x18000d47e  mov     rcx, [rsp+138h]; this
0x18000d486  test    eax, eax
0x18000d488  jns     short loc_18000D49E
0x18000d48a  mov     r9d, eax; char *
0x18000d48d  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000d494  mov     edx, 127h; void *
0x18000d499  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d49e  cmp     [rsp+138h+var_D8], 0
0x18000d4a4  jnz     short loc_18000D4BA
0x18000d4a6  lea     rcx, [rsp+138h+var_B0]
0x18000d4ae  call    ??1?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(void)
0x18000d4b3  xor     eax, eax
0x18000d4b5  jmp     loc_18000DA38
0x18000d4ba  lea     rcx, [rsp+138h+var_F0]
0x18000d4bf  call    ?GetStalePrintJobNotificationToastContent@@YA?AUXmlDocument@Dom@Xml@Data@Windows@winrt@@XZ; GetStalePrintJobNotificationToastContent(void)
0x18000d4c4  nop
0x18000d4c5  xor     ebx, ebx
0x18000d4c7  mov     [rsp+138h+var_108], rbx
0x18000d4cc  xor     edi, edi
0x18000d4ce  mov     [rsp+138h+var_F8], rdi
0x18000d4d3  lea     rdx, aSubgroup; "subgroup"
0x18000d4da  lea     rcx, [rsp+138h+var_60]; this
0x18000d4e2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d4e7  lea     r8, [rsp+138h+var_60]
0x18000d4ef  lea     rdx, [rsp+138h+var_100]
0x18000d4f4  lea     rcx, [rsp+138h+var_F0]
0x18000d4f9  call    ?GetElementsByTagName@?$consume_Windows_Data_Xml_Dom_IXmlDocument@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::GetElementsByTagName(winrt::param::hstring const &)
0x18000d4fe  nop
0x18000d4ff  lea     rsi, [rsp+138h+var_100]
0x18000d504  xor     r14d, r14d
0x18000d507  lea     rcx, [rsp+138h+var_100]
0x18000d50c  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@UIXmlNodeList@Dom@Xml@Data@Windows@winrt@@UIXmlNode@23456@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::Size(void)
0x18000d511  mov     r12d, eax
0x18000d514  cmp     r14d, r12d
0x18000d517  jnz     loc_18000D8BB
0x18000d51d  lea     rcx, [rsp+138h+var_100]; this
0x18000d522  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d527  mov     rbx, [rsp+138h]
0x18000d52f  mov     qword ptr [rsp+138h+var_118], 0; int
0x18000d538  lea     rdx, [rsp+138h+var_118]
0x18000d53d  lea     rcx, [rsp+138h+var_108]
0x18000d542  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000d547  test    al, al
0x18000d549  jz      short loc_18000D565
0x18000d54b  mov     r9d, 8000FFFFh; char *
0x18000d551  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000d558  mov     edx, 13Eh; void *
0x18000d55d  mov     rcx, rbx; this
0x18000d560  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d565  mov     rbx, [rsp+138h]
0x18000d56d  mov     qword ptr [rsp+138h+var_118], 0; int
0x18000d576  lea     rdx, [rsp+138h+var_118]
0x18000d57b  lea     rcx, [rsp+138h+var_F8]
0x18000d580  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000d585  test    al, al
0x18000d587  jz      short loc_18000D5A3
0x18000d589  mov     r9d, 8000FFFFh; char *
0x18000d58f  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000d596  mov     edx, 13Fh; void *
0x18000d59b  mov     rcx, rbx; this
0x18000d59e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d5a3  xor     ebx, ebx
0x18000d5a5  cmp     rbx, [rsp+138h+var_D8]
0x18000d5aa  jnb     loc_18000D7E8
0x18000d5b0  lea     rdx, aText; "text"
0x18000d5b7  lea     rcx, [rsp+138h+var_60]; this
0x18000d5bf  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d5c4  lea     r8, [rsp+138h+var_60]
0x18000d5cc  lea     rdx, [rsp+138h+var_100]
0x18000d5d1  lea     rcx, [rsp+138h+var_F0]
0x18000d5d6  call    ?CreateElement@?$consume_Windows_Data_Xml_Dom_IXmlDocument@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::CreateElement(winrt::param::hstring const &)
0x18000d5db  nop
0x18000d5dc  mov     rdx, rbx
0x18000d5df  lea     rcx, [rsp+138h+var_B0]
0x18000d5e7  call    ??A?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAAEAUStalePrintJobInfo@PrintJobCleanUpUtil@@_K@Z; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](unsigned __int64)
0x18000d5ec  mov     rdx, [rax]; unsigned __int16 *
0x18000d5ef  lea     rcx, [rsp+138h+var_A0]; this
0x18000d5f7  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d5fc  lea     rdx, [rsp+138h+var_A0]
0x18000d604  lea     rcx, [rsp+138h+var_100]
0x18000d609  call    ?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(winrt::param::hstring const &)
0x18000d60e  lea     rdx, aBody; "body"
0x18000d615  lea     rcx, [rsp+138h+var_A0]; this
0x18000d61d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d622  lea     rdx, aHintStyle; "hint-style"
0x18000d629  lea     rcx, [rsp+138h+var_80]; this
0x18000d631  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d636  lea     r8, [rsp+138h+var_A0]
0x18000d63e  lea     rdx, [rsp+138h+var_80]
0x18000d646  lea     rcx, [rsp+138h+var_100]
0x18000d64b  call    ?SetAttribute@?$consume_Windows_Data_Xml_Dom_IXmlElement@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000d650  mov     rcx, [rsp+138h+var_100]
0x18000d655  mov     qword ptr [rsp+138h+var_118], 0
0x18000d65e  test    rcx, rcx
0x18000d661  jz      short loc_18000D684
0x18000d663  mov     rax, [rcx]
0x18000d666  lea     r8, [rsp+138h+var_118]
0x18000d66b  lea     rdx, ??$guid_v@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNode>
0x18000d672  mov     rax, [rax]
0x18000d675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d67a  mov     rax, qword ptr [rsp+138h+var_118]
0x18000d67f  mov     qword ptr [rsp+138h+var_118], rax
0x18000d684  lea     r8, [rsp+138h+var_118]
0x18000d689  lea     rdx, [rsp+138h+var_E8]
0x18000d68e  lea     rcx, [rsp+138h+var_108]
0x18000d693  call    ?AppendChild@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUIXmlNode@Dom@Xml@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(winrt::Windows::Data::Xml::Dom::IXmlNode const &)
0x18000d698  lea     rcx, [rsp+138h+var_E8]; this
0x18000d69d  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d6a2  nop
0x18000d6a3  lea     rcx, [rsp+138h+var_118]; this
0x18000d6a8  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d6ad  lea     rdx, aText; "text"
0x18000d6b4  lea     rcx, [rsp+138h+var_80]; this
0x18000d6bc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d6c1  lea     r8, [rsp+138h+var_80]
0x18000d6c9  lea     rdx, [rsp+138h+var_110]
0x18000d6ce  lea     rcx, [rsp+138h+var_F0]
0x18000d6d3  call    ?CreateElement@?$consume_Windows_Data_Xml_Dom_IXmlDocument@UIXmlDocument@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlDocument<winrt::Windows::Data::Xml::Dom::IXmlDocument>::CreateElement(winrt::param::hstring const &)
0x18000d6d8  nop
0x18000d6d9  mov     rdx, rbx
0x18000d6dc  lea     rcx, [rsp+138h+var_B0]
0x18000d6e4  call    ??A?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAAAEAUStalePrintJobInfo@PrintJobCleanUpUtil@@_K@Z; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::operator[](unsigned __int64)
0x18000d6e9  mov     rdx, [rax+8]
0x18000d6ed  lea     rcx, [rsp+138h+var_60]
0x18000d6f5  call    ?FileTimeToLocalDateString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@Z; FileTimeToLocalDateString(_FILETIME)
0x18000d6fa  nop
0x18000d6fb  mov     rdx, rax
0x18000d6fe  lea     rcx, [rsp+138h+var_A0]; this
0x18000d706  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18000d70b  lea     rdx, [rsp+138h+var_A0]
0x18000d713  lea     rcx, [rsp+138h+var_110]
0x18000d718  call    ?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlElement>::InnerText(winrt::param::hstring const &)
0x18000d71d  nop
0x18000d71e  lea     rcx, [rsp+138h+var_60]
0x18000d726  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000d72b  lea     rdx, aBody; "body"
0x18000d732  lea     rcx, [rsp+138h+var_A0]; this
0x18000d73a  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d73f  lea     rdx, aHintStyle; "hint-style"
0x18000d746  lea     rcx, [rsp+138h+var_60]; this
0x18000d74e  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d753  lea     r8, [rsp+138h+var_A0]
0x18000d75b  lea     rdx, [rsp+138h+var_60]
0x18000d763  lea     rcx, [rsp+138h+var_110]
0x18000d768  call    ?SetAttribute@?$consume_Windows_Data_Xml_Dom_IXmlElement@UIXmlElement@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlElement<winrt::Windows::Data::Xml::Dom::IXmlElement>::SetAttribute(winrt::param::hstring const &,winrt::param::hstring const &)
0x18000d76d  mov     rcx, [rsp+138h+var_110]
0x18000d772  mov     qword ptr [rsp+138h+var_118], 0
0x18000d77b  test    rcx, rcx
0x18000d77e  jz      short loc_18000D7A1
0x18000d780  mov     rax, [rcx]
0x18000d783  lea     r8, [rsp+138h+var_118]
0x18000d788  lea     rdx, ??$guid_v@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Xml::Dom::IXmlNode>
0x18000d78f  mov     rax, [rax]
0x18000d792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d797  mov     rax, qword ptr [rsp+138h+var_118]
0x18000d79c  mov     qword ptr [rsp+138h+var_118], rax
0x18000d7a1  lea     r8, [rsp+138h+var_118]
0x18000d7a6  lea     rdx, [rsp+138h+var_E0]
0x18000d7ab  lea     rcx, [rsp+138h+var_F8]
0x18000d7b0  call    ?AppendChild@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUIXmlNode@Dom@Xml@Data@Windows@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::AppendChild(winrt::Windows::Data::Xml::Dom::IXmlNode const &)
0x18000d7b5  lea     rcx, [rsp+138h+var_E0]; this
0x18000d7ba  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d7bf  nop
0x18000d7c0  lea     rcx, [rsp+138h+var_118]; this
0x18000d7c5  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d7ca  nop
0x18000d7cb  lea     rcx, [rsp+138h+var_110]; this
0x18000d7d0  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d7d5  nop
0x18000d7d6  lea     rcx, [rsp+138h+var_100]; this
0x18000d7db  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d7e0  inc     rbx
0x18000d7e3  jmp     loc_18000D5A5
0x18000d7e8  lea     rax, [rsp+138h+var_118]
0x18000d7ed  mov     [rsp+138h+var_B8], rax
0x18000d7f5  mov     rax, qword ptr [rsp+138h+var_F0]
0x18000d7fa  mov     qword ptr [rsp+138h+var_118], rax; int
0x18000d7ff  lea     rcx, [rsp+138h+var_118]; this
0x18000d804  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18000d809  nop
0x18000d80a  lea     rax, [rsp+138h+var_E0]
0x18000d80f  mov     [rsp+138h+var_C0], rax
0x18000d814  lea     rdx, aStaleprintjobn_0; "StalePrintJobNotificationGroup"
0x18000d81b  lea     rcx, [rsp+138h+var_E0]; this
0x18000d820  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18000d825  mov     rbx, rax
0x18000d828  lea     rdx, aStaleprintjobn; "StalePrintJobNotificationTag"
0x18000d82f  lea     rcx, [rsp+138h+var_E8]; this
0x18000d834  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18000d839  nop
0x18000d83a  lea     r9, [rsp+138h+var_118]
0x18000d83f  mov     r8, rbx
0x18000d842  mov     rdx, rax
0x18000d845  lea     rcx, [rsp+138h+var_D0]
0x18000d84a  call    ??0ToastManager@@QEAA@Uhstring@winrt@@0UXmlDocument@Dom@Xml@Data@Windows@2@@Z; ToastManager::ToastManager(winrt::hstring,winrt::hstring,winrt::Windows::Data::Xml::Dom::XmlDocument)
0x18000d84f  nop
0x18000d850  lea     rcx, [rsp+138h+var_D0]; this
0x18000d855  call    ?ShowToast@ToastManager@@QEAAJXZ; ToastManager::ShowToast(void)
0x18000d85a  mov     rcx, [rsp+138h]; this
0x18000d862  test    eax, eax
0x18000d864  jns     short loc_18000D87B
0x18000d866  mov     r9d, eax; char *
0x18000d869  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000d870  mov     edx, 150h; void *
0x18000d875  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d87b  lea     rcx, [rsp+138h+var_D0]; this
0x18000d880  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d885  nop
0x18000d886  lea     rcx, [rsp+138h+var_F8]; this
0x18000d88b  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d890  nop
0x18000d891  lea     rcx, [rsp+138h+var_108]; this
0x18000d896  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d89b  nop
0x18000d89c  lea     rcx, [rsp+138h+var_F0]; this
0x18000d8a1  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d8a6  nop
0x18000d8a7  lea     rcx, [rsp+138h+var_B0]
0x18000d8af  call    ??1?$unique_any_array_ptr@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAUStalePrintJobInfo@PrintJobCleanUpUtil@@@Z$1?FreeStalePrintJobInfo@2@YAX0@Z@details@4@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>::~unique_any_array_ptr<PrintJobCleanUpUtil::StalePrintJobInfo,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(PrintJobCleanUpUtil::StalePrintJobInfo *),&PrintJobCleanUpUtil::FreeStalePrintJobInfo(PrintJobCleanUpUtil::StalePrintJobInfo *)>,unsigned __int64>(void)
0x18000d8b4  xor     eax, eax
0x18000d8b6  jmp     loc_18000DA38
0x18000d8bb  mov     r8d, r14d
0x18000d8be  lea     rdx, [rsp+138h+var_110]
0x18000d8c3  mov     rcx, rsi
0x18000d8c6  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@UIXmlNodeList@Dom@Xml@Data@Windows@winrt@@UIXmlNode@23456@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Data::Xml::Dom::IXmlNodeList,winrt::Windows::Data::Xml::Dom::IXmlNode>::GetAt(uint)
0x18000d8cb  nop
0x18000d8cc  lea     rdx, [rsp+138h+var_118]
0x18000d8d1  lea     rcx, [rsp+138h+var_110]
0x18000d8d6  call    ?Attributes@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(void)
0x18000d8db  mov     rsi, rax
0x18000d8de  lea     rdx, aId; "id"
0x18000d8e5  lea     rcx, [rsp+138h+var_80]; this
0x18000d8ed  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d8f2  lea     r8, [rsp+138h+var_80]
0x18000d8fa  lea     rdx, [rsp+138h+var_E8]
0x18000d8ff  mov     rcx, rsi
0x18000d902  call    ?GetNamedItem@?$consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(winrt::param::hstring const &)
0x18000d907  nop
0x18000d908  lea     rdx, [rsp+138h+var_E0]
0x18000d90d  mov     rcx, rax
0x18000d910  call    ?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(void)
0x18000d915  lea     rdx, aDocumentnames; "DocumentNames"
0x18000d91c  mov     rcx, rax
0x18000d91f  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x18000d924  mov     sil, al
0x18000d927  lea     rcx, [rsp+138h+var_E0]
0x18000d92c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18000d931  nop
0x18000d932  lea     rcx, [rsp+138h+var_E8]; this
0x18000d937  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d93c  nop
0x18000d93d  lea     rcx, [rsp+138h+var_118]; this
0x18000d942  call    ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
0x18000d947  test    sil, sil
0x18000d94a  jz      short loc_18000D96F
0x18000d94c  test    rbx, rbx
0x18000d94f  jz      short loc_18000D95B
0x18000d951  lea     rcx, [rsp+138h+var_108]
0x18000d956  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d95b  mov     rbx, [rsp+138h+var_110]
0x18000d960  mov     [rsp+138h+var_108], rbx
0x18000d965  lea     rcx, [rsp+138h+var_108]
0x18000d96a  jmp     loc_18000DA13
0x18000d96f  lea     rdx, [rsp+138h+var_B8]
0x18000d977  lea     rcx, [rsp+138h+var_110]
0x18000d97c  call    ?Attributes@?$consume_Windows_Data_Xml_Dom_IXmlNode@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNode<winrt::Windows::Data::Xml::Dom::IXmlNode>::Attributes(void)
0x18000d981  mov     rsi, rax
0x18000d984  lea     rdx, aId; "id"
0x18000d98b  lea     rcx, [rsp+138h+var_80]; this
0x18000d993  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18000d998  lea     r8, [rsp+138h+var_80]
0x18000d9a0  lea     rdx, [rsp+138h+var_C0]
0x18000d9a5  mov     rcx, rsi
0x18000d9a8  call    ?GetNamedItem@?$consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap@UIXmlNamedNodeMap@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNamedNodeMap<winrt::Windows::Data::Xml::Dom::IXmlNamedNodeMap>::GetNamedItem(winrt::param::hstring const &)
0x18000d9ad  nop
0x18000d9ae  lea     rdx, [rsp+138h+var_C8]
0x18000d9b3  mov     rcx, rax
0x18000d9b6  call    ?InnerText@?$consume_Windows_Data_Xml_Dom_IXmlNodeSerializer@UIXmlNode@Dom@Xml@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Xml_Dom_IXmlNodeSerializer<winrt::Windows::Data::Xml::Dom::IXmlNode>::InnerText(void)
  ... truncated ...
```
