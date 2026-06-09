# Windows::Networking::UX::CProvisioningAgentHelper::GetWifiProfileInfo(HSTRING__ *,Windows::Foundation::Collections::IVector<Windows::Networking::UX::IWifiProfileInfo *> * *)

- ea: `0x18002abac`
- end: `0x18002b149`
- name: `?GetWifiProfileInfo@CProvisioningAgentHelper@UX@Networking@Windows@@AEAAJPEAUHSTRING__@@PEAPEAU?$IVector@PEAUIWifiProfileInfo@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `1437`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a740`

## callees

- `0x180003ed0`
- `0x180008e30`
- `0x1800097b4`
- `0x180011a20`
- `0x1800121c8`
- `0x18001c044`
- `0x18001ce64`
- `0x180029f38`
- `0x18002a248`
- `0x18002aa44`
- `0x18002aae4`
- `0x18002abac`
- `0x18002b150`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ac2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ac2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aeaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aefc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aeaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aefc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002afa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b03d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002adb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aeca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002adb8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002aeca`

## string_xrefs

- `0x18002abfe`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002ac47`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002af89`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002afb4`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002afd8`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b006`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b025`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b050`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b074`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b098`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`
- `0x18002b0bc`: `onecoreuap\net\ux\wlanmediamanager\lib\cprovisioningagenthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Networking::UX::CProvisioningAgentHelper::GetWifiProfileInfo(
        __int64 a1,
        HSTRING a2,
        __int64 a3)
{
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int SingleNode; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  int XmlDocument; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  const unsigned __int16 *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int i; // esi
  struct IXMLDOMNodeList *v25; // rdi
  HRESULT (__stdcall *get_item)(IXMLDOMNodeList *, int, IXMLDOMNode **); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, PCNZWCH *); // rbx
  int v35; // eax
  __int64 v36; // rdx
  HRESULT v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, PCNZWCH *); // rbx
  int v45; // eax
  __int64 v46; // rdx
  HRESULT v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rdx
  __int64 v70; // r8
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // rdx
  __int64 v74; // r8
  struct IXMLDOMNodeList *v76; // [rsp+20h] [rbp-59h] BYREF
  HSTRING string; // [rsp+28h] [rbp-51h] BYREF
  struct IXMLDOMNode *v78; // [rsp+30h] [rbp-49h] BYREF
  __int64 v79; // [rsp+38h] [rbp-41h] BYREF
  __int64 v80; // [rsp+40h] [rbp-39h] BYREF
  __int64 v81; // [rsp+48h] [rbp-31h] BYREF
  PCNZWCH sourceString; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v83; // [rsp+58h] [rbp-21h] BYREF
  __int64 v84; // [rsp+60h] [rbp-19h] BYREF
  __int64 v85; // [rsp+68h] [rbp-11h] BYREF
  PCNZWCH v86; // [rsp+70h] [rbp-9h] BYREF
  int v87; // [rsp+78h] [rbp-1h] BYREF
  __int64 v88; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v89[32]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v88 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88, a2, a3);
  v6 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWifiProfileInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IWifiProfileInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IWifiProfileInfo *>>>(
         v5,
         &v88);
  SingleNode = v6;
  if ( v6 >= 0 )
  {
    v78 = 0;
    v76 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78, v7, v8);
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    XmlDocument = CXmlUtil::GetXmlDocument(StringRawBuffer, (struct IXMLDOMDocument **)&v78);
    SingleNode = XmlDocument;
    if ( XmlDocument >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76, v14, v15);
      XmlDocument = CXmlUtil::GetNodes(v78, v21, &v76);
      SingleNode = XmlDocument;
      if ( XmlDocument >= 0 )
      {
        v87 = 0;
        XmlDocument = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v76->lpVtbl->get_length)(v76, &v87);
        SingleNode = XmlDocument;
        if ( XmlDocument >= 0 )
        {
          for ( i = 0; (int)i < v87; ++i )
          {
            v80 = 0;
            v25 = v76;
            get_item = v76->lpVtbl->get_item;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v80,
              v22,
              v23);
            v27 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, __int64 *))get_item)(v25, i, &v80);
            SingleNode = v27;
            if ( v27 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)v27,
                (int)v76);
              goto LABEL_51;
            }
            v79 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v79,
              v28,
              v29);
            v30 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::WifiProfileInfo,Windows::Networking::UX::IWifiProfileInfo,>(&v79);
            SingleNode = v30;
            if ( v30 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC9,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)v30,
                (int)v76);
              goto LABEL_49;
            }
            v81 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v81,
              v31,
              v32);
            std::wstring::wstring(v89, L"*[local-name() = 'name']");
            SingleNode = CXmlUtil::GetSingleNode(v80, v89, &v81);
            std::wstring::_Tidy_deallocate(v89);
            if ( SingleNode < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCB,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)SingleNode,
                (int)v76);
              goto LABEL_47;
            }
            sourceString = 0;
            v33 = v81;
            v34 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v81 + 208LL);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &sourceString,
              0);
            v35 = v34(v33, &sourceString);
            SingleNode = v35;
            if ( v35 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xCE,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)v35,
                (int)v76);
              goto LABEL_45;
            }
            string = 0;
            WindowsDeleteString(0);
            string = 0;
            v36 = -1;
            do
              ++v36;
            while ( sourceString[v36] );
            v37 = WindowsCreateString(sourceString, v36, &string);
            SingleNode = v37;
            if ( v37 < 0 )
            {
              v64 = 209;
LABEL_42:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v64,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)v37,
                (int)v76);
LABEL_43:
              WindowsDeleteString(string);
              string = 0;
LABEL_45:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
LABEL_47:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v81,
                v65,
                v66);
LABEL_49:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v79,
                v67,
                v68);
LABEL_51:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v80,
                v69,
                v70);
              goto LABEL_6;
            }
            v37 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v79 + 64LL))(v79, string);
            SingleNode = v37;
            if ( v37 < 0 )
            {
              v64 = 210;
              goto LABEL_42;
            }
            v84 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v84,
              v38,
              v39);
            std::wstring::wstring(v89, L"*[local-name() = 'Hotspot2']");
            v40 = CXmlUtil::GetSingleNode(v80, v89, &v84);
            std::wstring::_Tidy_deallocate(v89);
            if ( v40 >= 0 )
            {
              v85 = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v85,
                v41,
                v42);
              std::wstring::wstring(v89, L"*[local-name() = 'DomainName']");
              SingleNode = CXmlUtil::GetSingleNode(v84, v89, &v85);
              std::wstring::_Tidy_deallocate(v89);
              if ( SingleNode < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD8,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                  (const char *)(unsigned int)SingleNode,
                  (int)v76);
                goto LABEL_37;
              }
              v86 = 0;
              v43 = v85;
              v44 = *(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v85 + 208LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v86,
                0);
              v45 = v44(v43, &v86);
              SingleNode = v45;
              if ( v45 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xDA,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                  (const char *)(unsigned int)v45,
                  (int)v76);
                goto LABEL_35;
              }
              v83 = 0;
              WindowsDeleteString(0);
              v83 = 0;
              v46 = -1;
              do
                ++v46;
              while ( v86[v46] );
              v47 = WindowsCreateString(v86, v46, &v83);
              SingleNode = v47;
              if ( v47 < 0 )
              {
                v59 = 221;
LABEL_33:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v59,
                  (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                  (const char *)(unsigned int)v47,
                  (int)v76);
                WindowsDeleteString(v83);
                v83 = 0;
LABEL_35:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v86);
LABEL_37:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v85,
                  v60,
                  v61);
LABEL_38:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v84,
                  v62,
                  v63);
                goto LABEL_43;
              }
              v47 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v79 + 72LL))(v79, v83);
              SingleNode = v47;
              if ( v47 < 0 )
              {
                v59 = 222;
                goto LABEL_33;
              }
              WindowsDeleteString(v83);
              v83 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v86);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v85,
                v48,
                v49);
            }
            v50 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 104LL))(v88, v79);
            SingleNode = v50;
            if ( v50 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE1,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
                (const char *)(unsigned int)v50,
                (int)v76);
              goto LABEL_38;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v84,
              v51,
              v52);
            WindowsDeleteString(string);
            string = 0;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v81,
              v53,
              v54);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v79,
              v55,
              v56);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v80,
              v57,
              v58);
          }
          XmlDocument = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v88)(
                          v88,
                          &GUID_d7c8c672_8d7f_5c42_9cc5_c5bb3c886963,
                          a3);
          SingleNode = XmlDocument;
          if ( XmlDocument >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v76,
              v71,
              v72);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v78,
              v73,
              v74);
            SingleNode = 0;
            goto LABEL_55;
          }
          v16 = 228;
        }
        else
        {
          v16 = 194;
        }
      }
      else
      {
        v16 = 191;
      }
    }
    else
    {
      v16 = 187;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
      (const char *)(unsigned int)XmlDocument,
      (int)v76);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76, v17, v18);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v78, v19, v20);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cprovisioningagenthelper.cpp",
      (const char *)(unsigned int)v6,
      (int)v76);
  }
LABEL_55:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v88, v10, v11);
  return (unsigned int)SingleNode;
}

```

## disassembly

```asm
0x18002abac  mov     [rsp-8+arg_0], rbx
0x18002abb1  push    rbp
0x18002abb2  push    rsi
0x18002abb3  push    rdi
0x18002abb4  push    r14
0x18002abb6  push    r15
0x18002abb8  lea     rbp, [rsp-37h]
0x18002abbd  sub     rsp, 0B0h
0x18002abc4  mov     rax, cs:__security_cookie
0x18002abcb  xor     rax, rsp
0x18002abce  mov     [rbp+57h+var_28], rax
0x18002abd2  mov     r14, r8
0x18002abd5  mov     rdi, rdx
0x18002abd8  xor     r15d, r15d
0x18002abdb  mov     [rbp+57h+var_50], r15
0x18002abdf  lea     rcx, [rbp+57h+var_50]
0x18002abe3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002abe8  lea     rdx, [rbp+57h+var_50]
0x18002abec  call    ??$CreateExternalObjectVector@UIWifiProfileInfo@UX@Networking@Windows@@V?$Vector@PEAUIWifiProfileInfo@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWifiProfileInfo@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWifiProfileInfo@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIWifiProfileInfo@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIWifiProfileInfo@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIWifiProfileInfo@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIWifiProfileInfo@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIWifiProfileInfo@UX@Networking@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IWifiProfileInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IWifiProfileInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IWifiProfileInfo *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IWifiProfileInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IWifiProfileInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IWifiProfileInfo *>> * *)
0x18002abf1  mov     ebx, eax
0x18002abf3  test    eax, eax
0x18002abf5  jns     short loc_18002AC14
0x18002abf7  mov     rcx, [rbp+5Fh]; this
0x18002abfb  mov     r9d, eax; char *
0x18002abfe  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002ac05  mov     edx, 0B7h; void *
0x18002ac0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac0f  jmp     loc_18002B11B
0x18002ac14  mov     [rbp+57h+var_A0], r15
0x18002ac18  mov     [rbp+57h+var_B0], r15
0x18002ac1c  lea     rcx, [rbp+57h+var_A0]
0x18002ac20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac25  xor     edx, edx; length
0x18002ac27  mov     rcx, rdi; string
0x18002ac2a  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ac30  lea     rdx, [rbp+57h+var_A0]; struct IXMLDOMDocument **
0x18002ac34  mov     rcx, rax; unsigned __int16 *
0x18002ac37  call    ?GetXmlDocument@CXmlUtil@@SAJPEBGPEAPEAUIXMLDOMDocument@@@Z; CXmlUtil::GetXmlDocument(ushort const *,IXMLDOMDocument * *)
0x18002ac3c  mov     ebx, eax
0x18002ac3e  test    eax, eax
0x18002ac40  jns     short loc_18002AC73
0x18002ac42  mov     edx, 0BBh; void *
0x18002ac47  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002ac4e  mov     r9d, eax; char *
0x18002ac51  mov     rcx, [rbp+5Fh]; this
0x18002ac55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac5a  nop
0x18002ac5b  lea     rcx, [rbp+57h+var_B0]
0x18002ac5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac64  nop
0x18002ac65  lea     rcx, [rbp+57h+var_A0]
0x18002ac69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac6e  jmp     loc_18002B11B
0x18002ac73  lea     rcx, [rbp+57h+var_B0]
0x18002ac77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac7c  lea     r8, [rbp+57h+var_B0]; struct IXMLDOMNodeList **
0x18002ac80  mov     rcx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x18002ac84  call    ?GetNodes@CXmlUtil@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@@Z; CXmlUtil::GetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *)
0x18002ac89  mov     ebx, eax
0x18002ac8b  test    eax, eax
0x18002ac8d  jns     short loc_18002AC96
0x18002ac8f  mov     edx, 0BFh
0x18002ac94  jmp     short loc_18002AC47
0x18002ac96  mov     [rbp+57h+var_58], r15d
0x18002ac9a  mov     rcx, [rbp+57h+var_B0]
0x18002ac9e  mov     rax, [rcx]
0x18002aca1  lea     rdx, [rbp+57h+var_58]
0x18002aca5  mov     rax, [rax+40h]
0x18002aca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acae  mov     ebx, eax
0x18002acb0  test    eax, eax
0x18002acb2  jns     short loc_18002ACBB
0x18002acb4  mov     edx, 0C2h
0x18002acb9  jmp     short loc_18002AC47
0x18002acbb  mov     esi, r15d
0x18002acbe  cmp     esi, [rbp+57h+var_58]
0x18002acc1  jge     loc_18002B0DC
0x18002acc7  mov     [rbp+57h+var_90], r15
0x18002accb  mov     rdi, [rbp+57h+var_B0]
0x18002accf  mov     rax, [rdi]
0x18002acd2  mov     rbx, [rax+38h]
0x18002acd6  lea     rcx, [rbp+57h+var_90]
0x18002acda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002acdf  lea     r8, [rbp+57h+var_90]
0x18002ace3  mov     edx, esi
0x18002ace5  mov     rcx, rdi
0x18002ace8  mov     rax, rbx
0x18002aceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acf0  mov     ebx, eax
0x18002acf2  test    eax, eax
0x18002acf4  js      loc_18002B0B5
0x18002acfa  mov     [rbp+57h+var_98], r15
0x18002acfe  lea     rcx, [rbp+57h+var_98]
0x18002ad02  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ad07  lea     rcx, [rbp+57h+var_98]
0x18002ad0b  call    ??$MakeAndInitialize@VWifiProfileInfo@UX@Networking@Windows@@UIWifiProfileInfo@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIWifiProfileInfo@UX@Networking@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::WifiProfileInfo,Windows::Networking::UX::IWifiProfileInfo,>(Windows::Networking::UX::IWifiProfileInfo * *)
0x18002ad10  mov     ebx, eax
0x18002ad12  test    eax, eax
0x18002ad14  js      loc_18002B091
0x18002ad1a  mov     [rbp+57h+var_88], r15
0x18002ad1e  lea     rcx, [rbp+57h+var_88]
0x18002ad22  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ad27  lea     rdx, aLocalNameName; "*[local-name() = 'name']"
0x18002ad2e  lea     rcx, [rbp+57h+var_48]
0x18002ad32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ad37  nop
0x18002ad38  lea     r8, [rbp+57h+var_88]
0x18002ad3c  lea     rdx, [rbp+57h+var_48]
0x18002ad40  mov     rcx, [rbp+57h+var_90]
0x18002ad44  call    ?GetSingleNode@CXmlUtil@@SAJPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU2@@Z; CXmlUtil::GetSingleNode(IXMLDOMNode *,std::wstring const &,IXMLDOMNode * *)
0x18002ad49  mov     ebx, eax
0x18002ad4b  lea     rcx, [rbp+57h+var_48]
0x18002ad4f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ad54  test    ebx, ebx
0x18002ad56  js      loc_18002B06D
0x18002ad5c  mov     [rbp+57h+sourceString], r15
0x18002ad60  mov     rdi, [rbp+57h+var_88]
0x18002ad64  mov     rax, [rdi]
0x18002ad67  mov     rbx, [rax+0D0h]
0x18002ad6e  xor     edx, edx
0x18002ad70  lea     rcx, [rbp+57h+sourceString]
0x18002ad74  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002ad79  lea     rdx, [rbp+57h+sourceString]
0x18002ad7d  mov     rcx, rdi
0x18002ad80  mov     rax, rbx
0x18002ad83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad88  mov     ebx, eax
0x18002ad8a  test    eax, eax
0x18002ad8c  js      loc_18002B049
0x18002ad92  mov     [rbp+57h+string], r15
0x18002ad96  xor     ecx, ecx; string
0x18002ad98  call    cs:__imp_WindowsDeleteString
0x18002ad9e  mov     [rbp+57h+string], r15
0x18002ada2  mov     rcx, [rbp+57h+sourceString]; sourceString
0x18002ada6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002adaa  inc     rdx; length
0x18002adad  cmp     [rcx+rdx*2], r15w
0x18002adb2  jnz     short loc_18002ADAA
0x18002adb4  lea     r8, [rbp+57h+string]; string
0x18002adb8  call    cs:__imp_WindowsCreateString
0x18002adbe  mov     ebx, eax
0x18002adc0  test    eax, eax
0x18002adc2  js      loc_18002B020
0x18002adc8  mov     rcx, [rbp+57h+var_98]
0x18002adcc  mov     rax, [rcx]
0x18002adcf  mov     rdx, [rbp+57h+string]
0x18002add3  mov     rax, [rax+40h]
0x18002add7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002addc  mov     ebx, eax
0x18002adde  test    eax, eax
0x18002ade0  js      loc_18002B019
0x18002ade6  mov     [rbp+57h+var_70], r15
0x18002adea  lea     rcx, [rbp+57h+var_70]
0x18002adee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002adf3  lea     rdx, aLocalNameHotsp; "*[local-name() = 'Hotspot2']"
0x18002adfa  lea     rcx, [rbp+57h+var_48]
0x18002adfe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ae03  nop
0x18002ae04  lea     r8, [rbp+57h+var_70]
0x18002ae08  lea     rdx, [rbp+57h+var_48]
0x18002ae0c  mov     rcx, [rbp+57h+var_90]
0x18002ae10  call    ?GetSingleNode@CXmlUtil@@SAJPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU2@@Z; CXmlUtil::GetSingleNode(IXMLDOMNode *,std::wstring const &,IXMLDOMNode * *)
0x18002ae15  mov     ebx, eax
0x18002ae17  lea     rcx, [rbp+57h+var_48]
0x18002ae1b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae20  shr     ebx, 1Fh
0x18002ae23  xor     bl, 1
0x18002ae26  jz      loc_18002AF19
0x18002ae2c  mov     [rbp+57h+var_68], r15
0x18002ae30  lea     rcx, [rbp+57h+var_68]
0x18002ae34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ae39  lea     rdx, aLocalNameDomai; "*[local-name() = 'DomainName']"
0x18002ae40  lea     rcx, [rbp+57h+var_48]
0x18002ae44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ae49  nop
0x18002ae4a  lea     r8, [rbp+57h+var_68]
0x18002ae4e  lea     rdx, [rbp+57h+var_48]
0x18002ae52  mov     rcx, [rbp+57h+var_70]
0x18002ae56  call    ?GetSingleNode@CXmlUtil@@SAJPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU2@@Z; CXmlUtil::GetSingleNode(IXMLDOMNode *,std::wstring const &,IXMLDOMNode * *)
0x18002ae5b  mov     ebx, eax
0x18002ae5d  lea     rcx, [rbp+57h+var_48]
0x18002ae61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ae66  test    ebx, ebx
0x18002ae68  js      loc_18002AFD1
0x18002ae6e  mov     [rbp+57h+var_60], r15
0x18002ae72  mov     rdi, [rbp+57h+var_68]
0x18002ae76  mov     rax, [rdi]
0x18002ae79  mov     rbx, [rax+0D0h]
0x18002ae80  xor     edx, edx
0x18002ae82  lea     rcx, [rbp+57h+var_60]
0x18002ae86  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002ae8b  lea     rdx, [rbp+57h+var_60]
0x18002ae8f  mov     rcx, rdi
0x18002ae92  mov     rax, rbx
0x18002ae95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae9a  mov     ebx, eax
0x18002ae9c  test    eax, eax
0x18002ae9e  js      loc_18002AFAD
0x18002aea4  mov     [rbp+57h+var_78], r15
0x18002aea8  xor     ecx, ecx; string
0x18002aeaa  call    cs:__imp_WindowsDeleteString
0x18002aeb0  mov     [rbp+57h+var_78], r15
0x18002aeb4  mov     rcx, [rbp+57h+var_60]; sourceString
0x18002aeb8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002aebc  inc     rdx; length
0x18002aebf  cmp     [rcx+rdx*2], r15w
0x18002aec4  jnz     short loc_18002AEBC
0x18002aec6  lea     r8, [rbp+57h+var_78]; string
0x18002aeca  call    cs:__imp_WindowsCreateString
0x18002aed0  mov     ebx, eax
0x18002aed2  test    eax, eax
0x18002aed4  js      loc_18002AF84
0x18002aeda  mov     rcx, [rbp+57h+var_98]
0x18002aede  mov     rax, [rcx]
0x18002aee1  mov     rdx, [rbp+57h+var_78]
0x18002aee5  mov     rax, [rax+48h]
0x18002aee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeee  mov     ebx, eax
0x18002aef0  test    eax, eax
0x18002aef2  js      loc_18002AF7D
0x18002aef8  mov     rcx, [rbp+57h+var_78]; string
0x18002aefc  call    cs:__imp_WindowsDeleteString
0x18002af02  mov     [rbp+57h+var_78], r15
0x18002af06  lea     rcx, [rbp+57h+var_60]
0x18002af0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002af0f  nop
0x18002af10  lea     rcx, [rbp+57h+var_68]
0x18002af14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002af19  mov     rcx, [rbp+57h+var_50]
0x18002af1d  mov     rax, [rcx]
0x18002af20  mov     rdx, [rbp+57h+var_98]
0x18002af24  mov     rax, [rax+68h]
0x18002af28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af2d  mov     ebx, eax
0x18002af2f  test    eax, eax
0x18002af31  js      loc_18002AFFF
0x18002af37  lea     rcx, [rbp+57h+var_70]
0x18002af3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002af40  nop
0x18002af41  mov     rcx, [rbp+57h+string]; string
0x18002af45  call    cs:__imp_WindowsDeleteString
0x18002af4b  mov     [rbp+57h+string], r15
0x18002af4f  lea     rcx, [rbp+57h+sourceString]
0x18002af53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002af58  nop
0x18002af59  lea     rcx, [rbp+57h+var_88]
0x18002af5d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002af62  nop
0x18002af63  lea     rcx, [rbp+57h+var_98]
0x18002af67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002af6c  nop
0x18002af6d  lea     rcx, [rbp+57h+var_90]
0x18002af71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002af76  inc     esi
0x18002af78  jmp     loc_18002ACBE
0x18002af7d  mov     edx, 0DEh
0x18002af82  jmp     short loc_18002AF89
0x18002af84  mov     edx, 0DDh; void *
0x18002af89  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002af90  mov     r9d, eax; char *
0x18002af93  mov     rcx, [rbp+5Fh]; this
0x18002af97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af9c  nop
0x18002af9d  mov     rcx, [rbp+57h+var_78]; string
0x18002afa1  call    cs:__imp_WindowsDeleteString
0x18002afa7  mov     [rbp+57h+var_78], r15
0x18002afab  jmp     short loc_18002AFC6
0x18002afad  mov     rcx, [rbp+5Fh]; this
0x18002afb1  mov     r9d, eax; char *
0x18002afb4  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002afbb  mov     edx, 0DAh; void *
0x18002afc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afc5  nop
0x18002afc6  lea     rcx, [rbp+57h+var_60]
0x18002afca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002afcf  jmp     short loc_18002AFEA
0x18002afd1  mov     rcx, [rbp+5Fh]; this
0x18002afd5  mov     r9d, ebx; char *
0x18002afd8  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002afdf  mov     edx, 0D8h; void *
0x18002afe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afe9  nop
0x18002afea  lea     rcx, [rbp+57h+var_68]
0x18002afee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aff3  nop
0x18002aff4  lea     rcx, [rbp+57h+var_70]
0x18002aff8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002affd  jmp     short loc_18002B039
0x18002afff  mov     rcx, [rbp+5Fh]; this
0x18002b003  mov     r9d, eax; char *
0x18002b006  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002b00d  mov     edx, 0E1h; void *
0x18002b012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b017  jmp     short loc_18002AFF4
0x18002b019  mov     edx, 0D2h
0x18002b01e  jmp     short loc_18002B025
0x18002b020  mov     edx, 0D1h; void *
0x18002b025  lea     r8, aOnecoreuapNetU_25; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18002b02c  mov     r9d, eax; char *
0x18002b02f  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
