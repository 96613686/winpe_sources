# CloudPrint::CloudPrintHelper::GetWebTokenRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest>>,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>>)

- ea: `0x180017b98`
- end: `0x180018662`
- name: `?GetWebTokenRequest@CloudPrintHelper@CloudPrint@@KAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@V?$ComPtrRef@V?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@678@V?$ComPtrRef@V?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@@678@@Z`
- size: `2762`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180013a2c`

## callees

- `0x180003a60`
- `0x180006b70`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e5e8`
- `0x18000f7a4`
- `0x18000f8b4`
- `0x180010678`
- `0x1800107b8`
- `0x1800115c0`
- `0x180012700`
- `0x1800133a0`
- `0x1800179e8`
- `0x180017b98`
- `0x18001bfe4`
- `0x18001c0a8`
- `0x18001df80`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018060`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001815c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018014`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018090`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001815c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017c1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800182b1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017c1a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800182b1`

## string_xrefs

- `0x180018286`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`
- `0x180017bf1`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`
- `0x180017bce`: `GetWebTokenRequest`
- `0x180018219`: `CloudPrint::CloudPrintHelper::GetWebTokenRequest`
- `0x180018232`: `CloudPrint::CloudPrintHelper::GetWebTokenRequest`
- `0x180018583`: `CloudPrint::CloudPrintHelper::GetWebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CloudPrint::CloudPrintHelper::GetWebTokenRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 (__fastcall ****a4)(_QWORD, GUID *, __int64 *),
        __int64 *a5,
        __int64 *a6)
{
  __int64 v8; // rdi
  int ActivationFactory; // eax
  int AllAccounts; // edi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // r14
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v13; // rdi
  __int64 v14; // rax
  int v15; // eax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rsi
  DWORD v17; // edx
  int v18; // r8d
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rbx
  DWORD v27; // edx
  int v28; // r8d
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, __int64 *); // rbx
  int v34; // eax
  __int64 v35; // rdx
  unsigned int i; // esi
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD, _QWORD); // rbx
  int v39; // eax
  __int64 (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v41)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, __int64 *); // rbx
  int v44; // eax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, HSTRING *); // rbx
  int v47; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v49; // rax
  __int64 (__fastcall ***v50)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 v51; // rdx
  __int64 v52; // rbx
  int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // r14
  __int64 (__fastcall *v56)(__int64, __int64, __int64, __int64); // rsi
  __int64 v57; // rdi
  __int64 v58; // rdi
  __int64 (__fastcall *v59)(__int64, __int64 *); // rbx
  int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rsi
  __int64 (__fastcall *v63)(__int64, __int64, __int64, char *); // rdi
  __int64 v64; // rbx
  __int64 v65; // rsi
  __int64 (__fastcall *v66)(__int64, __int64, __int64, char *); // rdi
  __int64 v67; // rbx
  __int64 v68; // r10
  __int64 v69; // rsi
  __int64 (__fastcall *v70)(__int64, __int64, __int64, char *); // rdi
  __int64 v71; // rbx
  __int64 v72; // rax
  __int64 v73; // rsi
  __int64 (__fastcall *v74)(__int64, __int64, __int64, char *); // rdi
  __int64 v75; // rbx
  int v77; // [rsp+20h] [rbp-E0h]
  char v78[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v79)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v80; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v82; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v83)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v84; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v85; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v86; // [rsp+70h] [rbp-90h] BYREF
  __int64 v87; // [rsp+78h] [rbp-88h] BYREF
  __int64 v88; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v89)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h] BYREF
  unsigned int v90; // [rsp+90h] [rbp-70h] BYREF
  HSTRING string; // [rsp+98h] [rbp-68h] BYREF
  __int64 v92; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v93; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v94[80]; // [rsp+B0h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp+0h] BYREF
  __int64 v96; // [rsp+118h] [rbp+18h]
  HSTRING_HEADER v97; // [rsp+120h] [rbp+20h] BYREF
  __int64 v98; // [rsp+138h] [rbp+38h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  CloudPrintHelperTelemetry::WatchCurrentThread(v94, "GetWebTokenRequest");
  v96 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
    0x46u,
    0x45u);
  v8 = v96;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_6aca7c92_a581_4479_9c10_752eff44fd34, a4);
  AllAccounts = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v79 = 0;
    v11 = *a4;
    v12 = (**a4)[12];
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    v13 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v97, &off_18003F0B0) + 24);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18003F0A8);
    v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))v12)(
            v11,
            *(_QWORD *)(v14 + 24),
            v13,
            &v79);
    AllAccounts = v15;
    if ( v15 < 0 )
    {
      if ( v15 != -2147023584 && v15 != -805306273 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x840,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v15,
          v77);
      goto LABEL_7;
    }
    v80 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
    v16 = v79;
    AllAccounts = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(
                    v79,
                    v17,
                    v18);
    if ( AllAccounts >= 0 )
      AllAccounts = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v16)[8])(
                      v16,
                      &v80);
    if ( AllAccounts < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x843,
        (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
        (const char *)(unsigned int)AllAccounts,
        v77);
LABEL_12:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
LABEL_7:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      goto LABEL_81;
    }
    if ( (unsigned __int8)std::operator!=<unsigned short>(a3, L"organizations") )
    {
      v82 = 0;
      v19 = *a4;
      v20 = ***a4;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
      v21 = v20(v19, &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf, &v82);
      AllAccounts = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x84C,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v21,
          v77);
LABEL_16:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
        goto LABEL_12;
      }
      v83 = 0;
      v22 = v82;
      v23 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v82 + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      v85 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v97, &v85);
      v25 = v23(v22, v80, *(_QWORD *)(v24 + 24), &v83);
      AllAccounts = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x852,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v25,
          v77);
LABEL_19:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
        goto LABEL_16;
      }
      v81 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      v26 = v83;
      AllAccounts = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(
                      v83,
                      v27,
                      v28);
      if ( AllAccounts >= 0 )
        AllAccounts = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v26)[8])(
                        v26,
                        &v81);
      if ( AllAccounts < 0 )
      {
        v29 = (unsigned int)AllAccounts;
        v30 = 2133;
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)v29,
          v77);
LABEL_25:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
        goto LABEL_19;
      }
      v90 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v81 + 56LL))(v81, &v90);
      AllAccounts = v31;
      if ( v31 < 0 )
      {
        v29 = (unsigned int)v31;
        v30 = 2136;
        goto LABEL_24;
      }
      if ( !v90 )
      {
        v87 = 0;
        v32 = v81;
        v33 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
        v34 = v33(v32, &v87);
        AllAccounts = v34;
        if ( v34 >= 0 )
        {
          v86 = 0;
          v34 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v87 + 56LL))(v87, &v86);
          AllAccounts = v34;
          if ( v34 >= 0 )
          {
            for ( i = 0; ; ++i )
            {
              if ( i >= v86 )
                goto LABEL_48;
              v89 = 0;
              v92 = 0;
              v37 = v87;
              v38 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v87 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
              v39 = v38(v37, i, &v89);
              AllAccounts = v39;
              if ( v39 < 0 )
                break;
              v40 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v89;
              v41 = **v89;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
              v39 = v41(v40, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v92);
              AllAccounts = v39;
              if ( v39 < 0 )
              {
                v51 = 2150;
                goto LABEL_54;
              }
              v85 = 0;
              v42 = v92;
              v43 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v92 + 56LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
              v44 = v43(v42, &v85);
              AllAccounts = v44;
              if ( v44 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x869,
                  (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                  (const char *)(unsigned int)v44,
                  v77);
                goto LABEL_51;
              }
              string = 0;
              v45 = v85;
              v46 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v85 + 48LL);
              WindowsDeleteString(0);
              string = 0;
              v96 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Authority", 0xAu, 9u);
              v47 = v46(v45, v96, &string);
              AllAccounts = v47;
              if ( v47 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x86C,
                  (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
                  (const char *)(unsigned int)v47,
                  v77);
                WindowsDeleteString(string);
                string = 0;
LABEL_51:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
                goto LABEL_55;
              }
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              std::_WChar_traits<unsigned short>::length(StringRawBuffer);
              v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v49) )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a6);
                v50 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v89;
                if ( (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a6 != v89 )
                {
                  if ( v89 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v89)[1])(v89);
                  v93 = *a6;
                  *a6 = (__int64)v50;
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v93);
                }
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
LABEL_48:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
                goto LABEL_60;
              }
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
            }
            v51 = 2149;
LABEL_54:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v51,
              (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
              (const char *)(unsigned int)v39,
              v77);
LABEL_55:
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v92);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v89);
            goto LABEL_32;
          }
          v35 = 2143;
        }
        else
        {
          v35 = 2140;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v34,
          v77);
LABEL_32:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v87);
        goto LABEL_25;
      }
      v86 = 0;
      std::wstring::wstring((__int64)&hstringHeader);
      v85 = 0;
      if ( (int)CloudPrint::CloudPrintHelper::GetWebProviderError(&v85, &v81, &v86, (__int64)&hstringHeader) < 0 )
      {
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetWebTokenRequest",
          L"Failed to get the list of WAM web accounts. status %d",
          v90);
      }
      else
      {
        v77 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        CloudPrintHelperTelemetry::WriteDbgTraceInfo(
          "CloudPrint::CloudPrintHelper::GetWebTokenRequest",
          L"Failed to get the list of WAM web accounts. status=%d, errorCode=%#x, errorMsg=%s",
          v90,
          v86);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
      std::wstring::_Tidy_deallocate((__int64)&hstringHeader);
LABEL_60:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    }
    v88 = 0;
    v96 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
      0x39u,
      0x38u);
    v52 = v96;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    v53 = RoGetActivationFactory(v52, &GUID_6cf2141c_0ff0_4c67_b84f_99ddbe4a72c9, &v88);
    AllAccounts = v53;
    if ( v53 >= 0 )
    {
      v55 = v88;
      v56 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v88 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a5);
      v93 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      v57 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v97, &v93) + 24);
      v96 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &dword_18002DF04, 1u, 0);
      v77 = (int)a5;
      v53 = v56(v55, v80, v96, v57);
      AllAccounts = v53;
      if ( v53 >= 0 )
      {
        v84 = 0;
        v58 = *a5;
        v59 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a5 + 80LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
        v60 = v59(v58, &v84);
        AllAccounts = v60;
        if ( v60 >= 0 )
        {
          v78[0] = 0;
          v62 = v84;
          v63 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v84 + 80LL);
          v93 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
          v64 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v97, &v93) + 24);
          v96 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"resource", 9u, 8u);
          v60 = v63(v62, v96, v64, v78);
          AllAccounts = v60;
          if ( v60 >= 0 )
          {
            v65 = v84;
            v66 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v84 + 80LL);
            v93 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            v67 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v97, &v93) + 24);
            v96 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"authority", 0xAu, 9u);
            v60 = v66(v65, v96, v67, v78);
            AllAccounts = v60;
            if ( v60 >= 0 )
            {
              std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
              std::_WChar_traits<unsigned short>::length(L"organizations");
              if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v68) )
                goto LABEL_84;
              v69 = v84;
              v70 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v84 + 80LL);
              v96 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"home", 5u, 4u);
              v71 = v96;
              v98 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v97, L"discover", 9u, 8u);
              v60 = v70(v69, v98, v71, v78);
              AllAccounts = v60;
              if ( v60 < 0 )
              {
                v61 = 2207;
              }
              else
              {
LABEL_84:
                if ( std::wstring::find(a3, L"adfs", 0) == -1 )
                  goto LABEL_80;
                v72 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
                CloudPrintHelperTelemetry::WriteDbgTraceInfo(
                  "CloudPrint::CloudPrintHelper::GetWebTokenRequest",
                  L"ADFS detected for OAuthAuthority %s. Setting validateAuthority to False.",
                  v72);
                v73 = v84;
                v74 = *(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)v84 + 80LL);
                v98 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v97, L"False", 6u, 5u);
                v75 = v98;
                v96 = 0;
                Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                  &hstringHeader,
                  L"validateAuthority",
                  0x12u,
                  0x11u);
                v60 = v74(v73, v96, v75, v78);
                AllAccounts = v60;
                if ( v60 >= 0 )
                {
LABEL_80:
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v80);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
                  AllAccounts = 0;
                  goto LABEL_81;
                }
                v61 = 2215;
              }
            }
            else
            {
              v61 = 2202;
            }
          }
          else
          {
            v61 = 2198;
          }
        }
        else
        {
          v61 = 2194;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v61,
          (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
          (const char *)(unsigned int)v60,
          (int)a5);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
        goto LABEL_64;
      }
      v54 = 2191;
    }
    else
    {
      v54 = 2185;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v54,
      (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
      (const char *)(unsigned int)v53,
      v77);
LABEL_64:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v88);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x836,
    (unsigned int)"onecoreuap\\printscan\\print\\shared\\cloudprinthelper\\lib\\cloudprinthelper.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v77);
LABEL_81:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v94);
  return (unsigned int)AllAccounts;
}

```

## disassembly

```asm
0x180017b98  mov     [rsp-8+arg_18], rbx
0x180017b9d  push    rbp
0x180017b9e  push    rsi
0x180017b9f  push    rdi
0x180017ba0  push    r12
0x180017ba2  push    r13
0x180017ba4  push    r14
0x180017ba6  push    r15
0x180017ba8  lea     rbp, [rsp-50h]
0x180017bad  sub     rsp, 150h
0x180017bb4  mov     rax, cs:__security_cookie
0x180017bbb  xor     rax, rsp
0x180017bbe  mov     [rbp+80h+var_40], rax
0x180017bc2  mov     rbx, r9
0x180017bc5  mov     r15, r8
0x180017bc8  mov     r12, rdx
0x180017bcb  mov     r13, rcx
0x180017bce  lea     rdx, aGetwebtokenreq; "GetWebTokenRequest"
0x180017bd5  lea     rcx, [rbp+80h+var_D0]
0x180017bd9  call    ?WatchCurrentThread@CloudPrintHelperTelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CloudPrintHelperTelemetry::WatchCurrentThread(char const *)
0x180017bde  nop
0x180017bdf  mov     [rbp+80h+var_68], 0
0x180017be7  mov     r9d, 45h ; 'E'; unsigned int
0x180017bed  lea     r8d, [r9+1]; unsigned int
0x180017bf1  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180017bf8  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180017bfc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017c01  mov     rdi, [rbp+80h+var_68]
0x180017c05  mov     rcx, rbx
0x180017c08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c0d  mov     r8, rbx
0x180017c10  lea     rdx, _GUID_6aca7c92_a581_4479_9c10_752eff44fd34
0x180017c17  mov     rcx, rdi
0x180017c1a  call    cs:__imp_RoGetActivationFactory
0x180017c20  mov     edi, eax
0x180017c22  test    eax, eax
0x180017c24  jns     short loc_180017C46
0x180017c26  mov     rcx, [rbp+88h]; this
0x180017c2d  mov     r9d, eax; char *
0x180017c30  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017c37  mov     edx, 836h; void *
0x180017c3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c41  jmp     loc_180018630
0x180017c46  mov     [rsp+180h+var_148], 0
0x180017c4f  mov     r14, [rbx]
0x180017c52  mov     rax, [r14]
0x180017c55  mov     rsi, [rax+60h]
0x180017c59  lea     rcx, [rsp+180h+var_148]
0x180017c5e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c63  lea     rdx, off_18003F0B0; "organizations"
0x180017c6a  lea     rcx, [rbp+80h+var_60]
0x180017c6e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017c73  nop
0x180017c74  mov     rdi, [rax+18h]
0x180017c78  lea     rdx, off_18003F0A8; "https://login.microsoft.com"
0x180017c7f  lea     rcx, [rbp+80h+hstringHeader]
0x180017c83  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017c88  nop
0x180017c89  lea     r9, [rsp+180h+var_148]
0x180017c8e  mov     r8, rdi
0x180017c91  mov     rdx, [rax+18h]
0x180017c95  mov     rcx, r14
0x180017c98  mov     rax, rsi
0x180017c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ca0  mov     edi, eax
0x180017ca2  xor     r14d, r14d
0x180017ca5  test    eax, eax
0x180017ca7  jns     short loc_180017CE2
0x180017ca9  cmp     eax, 80070520h
0x180017cae  jz      short loc_180017CD3
0x180017cb0  cmp     eax, 0D000005Fh
0x180017cb5  jz      short loc_180017CD3
0x180017cb7  mov     rcx, [rbp+88h]; this
0x180017cbe  mov     r9d, eax; char *
0x180017cc1  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017cc8  mov     edx, 840h; void *
0x180017ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cd2  nop
0x180017cd3  lea     rcx, [rsp+180h+var_148]
0x180017cd8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017cdd  jmp     loc_180018630
0x180017ce2  mov     [rsp+180h+var_140], r14
0x180017ce7  lea     rcx, [rsp+180h+var_140]
0x180017cec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017cf1  mov     rsi, [rsp+180h+var_148]
0x180017cf6  mov     rcx, rsi
0x180017cf9  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVWebAccountProvider@Credentials@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Credentials::WebAccountProvider *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180017cfe  mov     edi, eax
0x180017d00  test    eax, eax
0x180017d02  js      short loc_180017D1A
0x180017d04  mov     rax, [rsi]
0x180017d07  lea     rdx, [rsp+180h+var_140]
0x180017d0c  mov     rcx, rsi
0x180017d0f  mov     rax, [rax+40h]
0x180017d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d18  mov     edi, eax
0x180017d1a  test    edi, edi
0x180017d1c  jns     short loc_180017D46
0x180017d1e  mov     rcx, [rbp+88h]; this
0x180017d25  mov     r9d, edi; char *
0x180017d28  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017d2f  mov     edx, 843h; void *
0x180017d34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d39  nop
0x180017d3a  lea     rcx, [rsp+180h+var_140]
0x180017d3f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017d44  jmp     short loc_180017CD3
0x180017d46  lea     rdx, aOrganizations; "organizations"
0x180017d4d  mov     rcx, r15
0x180017d50  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG@Z; std::operator!=<ushort>(std::wstring const &,ushort const * const)
0x180017d55  test    al, al
0x180017d57  jz      loc_180018274
0x180017d5d  mov     [rsp+180h+var_130], r14
0x180017d62  mov     rdi, [rbx]
0x180017d65  mov     rax, [rdi]
0x180017d68  mov     rbx, [rax]
0x180017d6b  lea     rcx, [rsp+180h+var_130]
0x180017d70  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017d75  lea     r8, [rsp+180h+var_130]
0x180017d7a  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x180017d81  mov     rcx, rdi
0x180017d84  mov     rax, rbx
0x180017d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d8c  mov     edi, eax
0x180017d8e  test    eax, eax
0x180017d90  jns     short loc_180017DBA
0x180017d92  mov     rcx, [rbp+88h]; this
0x180017d99  mov     r9d, eax; char *
0x180017d9c  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017da3  mov     edx, 84Ch; void *
0x180017da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017dad  nop
0x180017dae  lea     rcx, [rsp+180h+var_130]
0x180017db3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017db8  jmp     short loc_180017D3A
0x180017dba  mov     [rsp+180h+var_128], r14
0x180017dbf  mov     rdi, [rsp+180h+var_130]
0x180017dc4  mov     rax, [rdi]
0x180017dc7  mov     rbx, [rax+38h]
0x180017dcb  lea     rcx, [rsp+180h+var_128]
0x180017dd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017dd5  mov     rcx, r12
0x180017dd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017ddd  mov     [rsp+180h+var_118], rax
0x180017de2  lea     rdx, [rsp+180h+var_118]
0x180017de7  lea     rcx, [rbp+80h+var_60]
0x180017deb  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017df0  nop
0x180017df1  lea     r9, [rsp+180h+var_128]
0x180017df6  mov     r8, [rax+18h]
0x180017dfa  mov     rdx, [rsp+180h+var_140]
0x180017dff  mov     rcx, rdi
0x180017e02  mov     rax, rbx
0x180017e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e0a  mov     edi, eax
0x180017e0c  test    eax, eax
0x180017e0e  jns     short loc_180017E3B
0x180017e10  mov     rcx, [rbp+88h]; this
0x180017e17  mov     r9d, eax; char *
0x180017e1a  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017e21  mov     edx, 852h; void *
0x180017e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e2b  nop
0x180017e2c  lea     rcx, [rsp+180h+var_128]
0x180017e31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e36  jmp     loc_180017DAE
0x180017e3b  mov     [rsp+180h+var_138], r14
0x180017e40  lea     rcx, [rsp+180h+var_138]
0x180017e45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e4a  mov     rbx, [rsp+180h+var_128]
0x180017e4f  mov     rcx, rbx
0x180017e52  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180017e57  mov     edi, eax
0x180017e59  test    eax, eax
0x180017e5b  js      short loc_180017E73
0x180017e5d  mov     rax, [rbx]
0x180017e60  lea     rdx, [rsp+180h+var_138]
0x180017e65  mov     rcx, rbx
0x180017e68  mov     rax, [rax+40h]
0x180017e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e71  mov     edi, eax
0x180017e73  test    edi, edi
0x180017e75  jns     short loc_180017E9F
0x180017e77  mov     r9d, edi; char *
0x180017e7a  mov     edx, 855h; void *
0x180017e7f  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017e86  mov     rcx, [rbp+88h]; this
0x180017e8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e92  nop
0x180017e93  lea     rcx, [rsp+180h+var_138]
0x180017e98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e9d  jmp     short loc_180017E2C
0x180017e9f  mov     [rbp+80h+var_F0], r14d
0x180017ea3  mov     rcx, [rsp+180h+var_138]
0x180017ea8  mov     rax, [rcx]
0x180017eab  lea     rdx, [rbp+80h+var_F0]
0x180017eaf  mov     rax, [rax+38h]
0x180017eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017eb8  mov     edi, eax
0x180017eba  test    eax, eax
0x180017ebc  jns     short loc_180017EC8
0x180017ebe  mov     r9d, eax
0x180017ec1  mov     edx, 858h
0x180017ec6  jmp     short loc_180017E7F
0x180017ec8  cmp     [rbp+80h+var_F0], r14d
0x180017ecc  jnz     loc_1800181CB
0x180017ed2  mov     [rsp+180h+var_108], r14
0x180017ed7  mov     rdi, [rsp+180h+var_138]
0x180017edc  mov     rax, [rdi]
0x180017edf  mov     rbx, [rax+30h]
0x180017ee3  lea     rcx, [rsp+180h+var_108]
0x180017ee8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017eed  lea     rdx, [rsp+180h+var_108]
0x180017ef2  mov     rcx, rdi
0x180017ef5  mov     rax, rbx
0x180017ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017efd  mov     edi, eax
0x180017eff  test    eax, eax
0x180017f01  jns     short loc_180017F2E
0x180017f03  mov     edx, 85Ch; void *
0x180017f08  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\shared\\c"...
0x180017f0f  mov     r9d, eax; char *
0x180017f12  mov     rcx, [rbp+88h]; this
0x180017f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f1e  nop
0x180017f1f  lea     rcx, [rsp+180h+var_108]
0x180017f24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017f29  jmp     loc_180017E93
0x180017f2e  mov     [rsp+180h+var_110], r14d
0x180017f33  mov     rcx, [rsp+180h+var_108]
0x180017f38  mov     rax, [rcx]
0x180017f3b  lea     rdx, [rsp+180h+var_110]
0x180017f40  mov     rax, [rax+38h]
0x180017f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f49  mov     edi, eax
0x180017f4b  test    eax, eax
0x180017f4d  jns     short loc_180017F56
0x180017f4f  mov     edx, 85Fh
0x180017f54  jmp     short loc_180017F08
0x180017f56  mov     esi, r14d
0x180017f59  cmp     esi, [rsp+180h+var_110]
0x180017f5d  jnb     loc_18001812D
0x180017f63  mov     [rbp+80h+var_F8], r14
0x180017f67  mov     [rbp+80h+var_E0], r14
0x180017f6b  mov     rdi, [rsp+180h+var_108]
0x180017f70  mov     rax, [rdi]
0x180017f73  mov     rbx, [rax+30h]
0x180017f77  lea     rcx, [rbp+80h+var_F8]
0x180017f7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017f80  lea     r8, [rbp+80h+var_F8]
0x180017f84  mov     edx, esi
0x180017f86  mov     rcx, rdi
0x180017f89  mov     rax, rbx
0x180017f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f91  mov     edi, eax
0x180017f93  test    eax, eax
0x180017f95  js      loc_180018197
0x180017f9b  mov     rbx, [rbp+80h+var_F8]
0x180017f9f  mov     rax, [rbx]
0x180017fa2  mov     rdi, [rax]
0x180017fa5  lea     rcx, [rbp+80h+var_E0]
0x180017fa9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017fae  lea     r8, [rbp+80h+var_E0]
0x180017fb2  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x180017fb9  mov     rcx, rbx
0x180017fbc  mov     rax, rdi
0x180017fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fc4  mov     edi, eax
0x180017fc6  test    eax, eax
0x180017fc8  js      loc_180018190
0x180017fce  mov     [rsp+180h+var_118], r14
0x180017fd3  mov     rdi, [rbp+80h+var_E0]
0x180017fd7  mov     rax, [rdi]
0x180017fda  mov     rbx, [rax+38h]
0x180017fde  lea     rcx, [rsp+180h+var_118]
0x180017fe3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017fe8  lea     rdx, [rsp+180h+var_118]
0x180017fed  mov     rcx, rdi
0x180017ff0  mov     rax, rbx
0x180017ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff8  mov     edi, eax
0x180017ffa  test    eax, eax
0x180017ffc  js      loc_180018168
0x180018002  mov     [rbp+80h+string], r14
0x180018006  mov     rdi, [rsp+180h+var_118]
0x18001800b  mov     rax, [rdi]
0x18001800e  mov     rbx, [rax+30h]
0x180018012  xor     ecx, ecx; string
0x180018014  call    cs:__imp_WindowsDeleteString
0x18001801a  mov     [rbp+80h+string], r14
0x18001801e  mov     [rbp+80h+var_68], r14
0x180018022  mov     r9d, 9; unsigned int
0x180018028  lea     r8d, [r9+1]; unsigned int
0x18001802c  lea     rdx, sourceString; "Authority"
0x180018033  lea     rcx, [rbp+80h+hstringHeader]; hstringHeader
0x180018037  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001803c  nop
0x18001803d  lea     r8, [rbp+80h+string]
0x180018041  mov     rdx, [rbp+80h+var_68]
0x180018045  mov     rcx, rdi
  ... truncated ...
```
