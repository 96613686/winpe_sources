# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryThumbprintAndStoreNameForSCEPCert(std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,bool,std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo,std::allocator<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>> &)

- ea: `0x180139a0c`
- end: `0x18013a14f`
- name: `?QueryThumbprintAndStoreNameForSCEPCert@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_NAEAV?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@7@@Z`
- size: `1859`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012afd8`

## callees

- `0x180019000`
- `0x1800e4444`
- `0x1800e66dc`
- `0x1800e680c`
- `0x1800e7bac`
- `0x1800e85bc`
- `0x1800e87e8`
- `0x1800ead14`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f3f8c`
- `0x1800f8a0c`
- `0x1800f8aa0`
- `0x1800f9a0c`
- `0x18011129c`
- `0x180126ab4`
- `0x180126ae8`
- `0x180128238`
- `0x180136630`
- `0x180137260`
- `0x18013728c`
- `0x180137840`
- `0x1801386f8`
- `0x180139a0c`
- `0x18013a3c0`
- `0x180191010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180139ddb`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180139ddb`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x180139ded`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x180139ded`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x180139e10`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x180139e10`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180139d2b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180139e1d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180139d2b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180139e1d`
- `OLEAUT32!__imp_VariantInit` at `0x180139aec`
- `OLEAUT32!__imp_VariantInit` at `0x180139aec`
- `OLEAUT32!__imp_VariantClear` at `0x18013a0fe`
- `OLEAUT32!__imp_VariantClear` at `0x18013a0fe`

## string_xrefs

- `0x180139ab6`: `Unexpected locuri for cert thumbprint and store name query. `
- `0x180139be7`: ` ResourceUri: `
- `0x18013a01e`: `Getting node for cert installation for Thumbprint: `
- `0x180139dc4`: ` completed with error 0x`
- `0x180139d9b`: `PFX cert installation for `
- `0x180139cee`: `SCEP cert installation for `
- `0x180139f2f`: `Getting node for PFX cert installation for Thumbprint: `
- `0x180139f60`: `EncryptionStoreUri: `

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryThumbprintAndStoreNameForSCEPCert(
        __int64 a1,
        _QWORD ***a2,
        char a3,
        __int64 a4)
{
  int ConfigManager2; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  _QWORD **v9; // rdi
  _QWORD *i; // rbx
  int TargetCertTypeFromLocURI; // r12d
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v12; // rsi
  __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rax
  __int64 v16; // r14
  int (__fastcall *v17)(__int64, __int64, __int64 *); // rsi
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v22; // rsi
  __int64 v23; // rax
  __int64 bstr; // rax
  __int64 v25; // r14
  int (__fastcall *v26)(__int64, __int64, __int64 *); // rsi
  __int64 v27; // r8
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v31; // rsi
  __int64 v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rsi
  __int64 v36; // rax
  __int64 v37; // rsi
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v38; // rsi
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r14
  int (__fastcall *v42)(__int64, __int64, __int64 *); // rsi
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v48; // rsi
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v54; // rsi
  int v56; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v57; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v58; // [rsp+30h] [rbp-D0h] BYREF
  int v59[2]; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v61[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v62[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v64[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v65[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v66[232]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v67[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v68[16]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v69[8]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v70[232]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v71[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v72[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v73[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v74[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v75[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v76[32]; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  LOBYTE(v56) = a3;
  v57 = 0;
  *(_QWORD *)v59 = 0;
  ConfigManager2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2((LPVOID *)v59);
  v8 = ConfigManager2;
  if ( ConfigManager2 >= 0 )
  {
    v9 = *a2;
    for ( i = *v9; ; i = (_QWORD *)*i )
    {
      if ( i == v9 )
      {
        v8 = 0;
        goto LABEL_32;
      }
      TargetCertTypeFromLocURI = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetTargetCertTypeFromLocURI(
                                   v7,
                                   i + 2);
      if ( !TargetCertTypeFromLocURI )
      {
        v12 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        v13 = std::operator+<unsigned short>(
                v71,
                L"Unexpected locuri for cert thumbprint and store name query. ",
                i + 2);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v12, v13);
        std::wstring::_Tidy_deallocate(v71);
        continue;
      }
      VariantInit(&pvarg);
      v14 = L"/CertThumbPrint";
      if ( TargetCertTypeFromLocURI != 1 )
        v14 = L"/Thumbprint";
      std::operator+<unsigned short>(v75, i + 2, v14);
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
      wil::make_bstr(&v58, v15);
      v16 = *(_QWORD *)v59;
      v17 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v59 + 80LL);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v57);
      if ( v17(v16, v58, &v57) >= 0
        && (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v57 + 104LL))(v57, &pvarg) >= 0
        && pvarg.vt == 8 )
      {
        break;
      }
LABEL_29:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
      std::wstring::_Tidy_deallocate(v75);
      VariantClear(&pvarg);
    }
    std::wstring::wstring(v72, pvarg.llVal);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v68);
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v69, L"Processing Thumbprint: ");
    v19 = std::operator<<<unsigned short>(v18, v72);
    v20 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v19, " ");
    v21 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, " ResourceUri: ");
    std::operator<<<unsigned short>(v21, i + 2);
    v22 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    std::basic_stringbuf<unsigned short>::str(v70, v73);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v22, v73);
    std::wstring::_Tidy_deallocate(v73);
    std::operator+<unsigned short>(v74, i + 2, L"/Status");
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
    bstr = wil::make_bstr(v61, v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v58,
      bstr);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v61);
    v25 = *(_QWORD *)v59;
    v26 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v59 + 80LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v57);
    if ( v26(v25, v58, &v57) < 0
      || (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v57 + 104LL))(v57, &pvarg) < 0 )
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v64);
      v49 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              v65,
              L"Getting node for cert installation for Thumbprint: ");
      v50 = std::operator<<<unsigned short>(v49, v72);
      v51 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v50, " ");
      v52 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v51, "StatusString: ");
      v53 = std::operator<<<unsigned short>(v52, v74);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v53, " failed.");
      v54 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      std::basic_stringbuf<unsigned short>::str(v66, v71);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v54, v71);
      std::wstring::_Tidy_deallocate(v71);
    }
    else if ( TargetCertTypeFromLocURI == 1 )
    {
      if ( pvarg.lVal == 1 )
      {
        ((void (__fastcall *)(__int64, _BYTE *, __int64, int *))std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,unsigned short const (&)[3],bool &>)(
          a4,
          v72,
          v27,
          &v56);
LABEL_28:
        std::wstring::_Tidy_deallocate(v74);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v68);
        std::wstring::_Tidy_deallocate(v72);
        goto LABEL_29;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v64);
      v28 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, L"SCEP cert installation for ");
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v28, v29);
      v30 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
              v65,
              L" is not finished successfully. Status: ");
      std::basic_ostream<unsigned short>::operator<<(v30, pvarg.cyVal.Lo);
      v31 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      std::basic_stringbuf<unsigned short>::str(v66, v73);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v31, v73);
      std::wstring::_Tidy_deallocate(v73);
    }
    else
    {
      if ( !pvarg.lVal )
      {
        std::wstring::wstring(v73, L"MY");
        std::operator+<unsigned short>(v76, i + 2, L"/PFXCertPasswordEncryptionStore");
        v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
        v40 = wil::make_bstr(v62, v39);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &v58,
          v40);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v62);
        v41 = *(_QWORD *)v59;
        v42 = *(int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)v59 + 80LL);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v57);
        if ( v42(v41, v58, &v57) >= 0
          && (*(int (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v57 + 104LL))(v57, &pvarg) >= 0
          && pvarg.vt == 8 )
        {
          std::wstring::assign(v73, pvarg.llVal);
        }
        else
        {
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v64);
          v43 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                  v65,
                  L"Getting node for PFX cert installation for Thumbprint: ");
          v44 = std::operator<<<unsigned short>(v43, v72);
          v45 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v44, " ");
          v46 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v45, "EncryptionStoreUri: ");
          v47 = std::operator<<<unsigned short>(v46, v76);
          std::operator<<<unsigned short,std::char_traits<unsigned short>>(v47, " failed.");
          v48 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
          std::basic_stringbuf<unsigned short>::str(v66, v71);
          Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v48, v71);
          std::wstring::_Tidy_deallocate(v71);
          std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v64);
        }
        v63 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
        ((void (__fastcall *)(__int64, _BYTE *, __int64 *, int *))std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,unsigned short const *,bool &>)(
          a4,
          v72,
          &v63,
          &v56);
        std::wstring::_Tidy_deallocate(v76);
        std::wstring::_Tidy_deallocate(v73);
        goto LABEL_28;
      }
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v64);
      v32 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v65, L"PFX cert installation for ");
      v33 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
      v34 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v32, v33);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v34, L" completed with error 0x");
      v35 = std::basic_ostream<unsigned short>::operator<<(v65, std::hex);
      v36 = std::setw(v67, 8);
      v37 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v35, v36);
      std::basic_ios<unsigned short>::fill(v37 + *(int *)(*(_QWORD *)v37 + 4LL), 48);
      std::basic_ostream<unsigned short>::operator<<(v37, pvarg.cyVal.Lo);
      v38 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      std::basic_stringbuf<unsigned short>::str(v66, v71);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v38, v71);
      std::wstring::_Tidy_deallocate(v71);
    }
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v64);
    goto LABEL_28;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC3,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
    (const char *)(unsigned int)ConfigManager2,
    v56);
LABEL_32:
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(v59);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v57);
  return v8;
}

```

## disassembly

```asm
0x180139a0c  mov     [rsp-8+arg_0], rbx
0x180139a11  push    rbp
0x180139a12  push    rsi
0x180139a13  push    rdi
0x180139a14  push    r12
0x180139a16  push    r13
0x180139a18  push    r14
0x180139a1a  push    r15
0x180139a1c  lea     rbp, [rsp-250h]
0x180139a24  sub     rsp, 350h
0x180139a2b  mov     rax, cs:__security_cookie
0x180139a32  xor     rax, rsp
0x180139a35  mov     [rbp+280h+var_40], rax
0x180139a3c  mov     r13, r9
0x180139a3f  mov     rdi, rdx
0x180139a42  mov     byte ptr [rsp+380h+var_360], r8b; int
0x180139a47  mov     [rsp+380h+var_358], 0
0x180139a50  mov     qword ptr [rsp+380h+var_348], 0
0x180139a59  lea     rcx, [rsp+380h+var_348]; int
0x180139a5e  call    ?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)
0x180139a63  mov     ebx, eax
0x180139a65  test    eax, eax
0x180139a67  jns     short loc_180139A89
0x180139a69  mov     rcx, [rbp+288h]; this
0x180139a70  mov     r9d, eax; char *
0x180139a73  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139a7a  mov     edx, 0C3h; void *
0x180139a7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139a84  jmp     loc_18013A10E
0x180139a89  mov     rdi, [rdi]
0x180139a8c  mov     rbx, [rdi]
0x180139a8f  cmp     rbx, rdi
0x180139a92  jz      loc_18013A10C
0x180139a98  lea     r15, [rbx+10h]
0x180139a9c  mov     rdx, r15
0x180139a9f  call    ?GetTargetCertTypeFromLocURI@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEBA?AW4CertType@12345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::GetTargetCertTypeFromLocURI(std::wstring const &)
0x180139aa4  mov     r12d, eax
0x180139aa7  test    eax, eax
0x180139aa9  jnz     short loc_180139AE7
0x180139aab  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139ab0  mov     rsi, rax
0x180139ab3  mov     r8, r15
0x180139ab6  lea     rdx, aUnexpectedLocu; "Unexpected locuri for cert thumbprint a"...
0x180139abd  lea     rcx, [rbp+280h+var_100]
0x180139ac4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180139ac9  nop
0x180139aca  mov     rdx, rax
0x180139acd  mov     rcx, rsi
0x180139ad0  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x180139ad5  nop
0x180139ad6  lea     rcx, [rbp+280h+var_100]
0x180139add  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139ae2  jmp     loc_18013A104
0x180139ae7  lea     rcx, [rsp+380h+pvarg]; pvarg
0x180139aec  call    cs:__imp_VariantInit
0x180139af2  nop
0x180139af3  lea     rax, aThumbprint; "/Thumbprint"
0x180139afa  lea     r8, aCertthumbprint; "/CertThumbPrint"
0x180139b01  cmp     r12d, 1
0x180139b05  cmovnz  r8, rax
0x180139b09  mov     rdx, r15
0x180139b0c  lea     rcx, [rbp+280h+var_80]
0x180139b13  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180139b18  nop
0x180139b19  lea     rcx, [rbp+280h+var_80]
0x180139b20  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139b25  mov     rdx, rax
0x180139b28  lea     rcx, [rsp+380h+var_350]
0x180139b2d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180139b32  nop
0x180139b33  mov     r14, qword ptr [rsp+380h+var_348]
0x180139b38  mov     rax, [r14]
0x180139b3b  mov     rsi, [rax+50h]
0x180139b3f  lea     rcx, [rsp+380h+var_358]
0x180139b44  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180139b49  lea     r8, [rsp+380h+var_358]
0x180139b4e  mov     rdx, [rsp+380h+var_350]
0x180139b53  mov     rcx, r14
0x180139b56  mov     rax, rsi
0x180139b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139b5e  test    eax, eax
0x180139b60  js      loc_18013A0E1
0x180139b66  mov     rcx, [rsp+380h+var_358]
0x180139b6b  mov     rax, [rcx]
0x180139b6e  lea     rdx, [rsp+380h+pvarg]
0x180139b73  mov     rax, [rax+68h]
0x180139b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139b7c  test    eax, eax
0x180139b7e  js      loc_18013A0E1
0x180139b84  mov     eax, 8
0x180139b89  cmp     word ptr [rsp+380h+pvarg], ax
0x180139b8e  jnz     loc_18013A0E1
0x180139b94  mov     rdx, qword ptr [rsp+380h+pvarg+8]
0x180139b99  lea     rcx, [rbp+280h+var_E0]
0x180139ba0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180139ba5  nop
0x180139ba6  lea     rcx, [rbp+280h+var_200]
0x180139bad  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180139bb2  nop
0x180139bb3  lea     rdx, aProcessingThum; "Processing Thumbprint: "
0x180139bba  lea     rcx, [rbp+280h+var_1F0]
0x180139bc1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139bc6  mov     rcx, rax
0x180139bc9  lea     rdx, [rbp+280h+var_E0]
0x180139bd0  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180139bd5  mov     rcx, rax
0x180139bd8  lea     rdx, asc_1801F14A0; " "
0x180139bdf  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180139be4  mov     rcx, rax
0x180139be7  lea     rdx, aResourceuri; " ResourceUri: "
0x180139bee  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x180139bf3  mov     rcx, rax
0x180139bf6  mov     rdx, r15
0x180139bf9  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180139bfe  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139c03  mov     rsi, rax
0x180139c06  lea     rdx, [rbp+280h+var_C0]
0x180139c0d  lea     rcx, [rbp+280h+var_1E8]
0x180139c14  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180139c19  nop
0x180139c1a  lea     rdx, [rbp+280h+var_C0]
0x180139c21  mov     rcx, rsi
0x180139c24  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x180139c29  nop
0x180139c2a  lea     rcx, [rbp+280h+var_C0]
0x180139c31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139c36  lea     r8, aStatus_1; "/Status"
0x180139c3d  mov     rdx, r15
0x180139c40  lea     rcx, [rbp+280h+var_A0]
0x180139c47  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180139c4c  nop
0x180139c4d  lea     rcx, [rbp+280h+var_A0]
0x180139c54  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139c59  mov     rdx, rax
0x180139c5c  lea     rcx, [rsp+380h+var_328]
0x180139c61  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180139c66  mov     rdx, rax
0x180139c69  lea     rcx, [rsp+380h+var_350]
0x180139c6e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180139c73  lea     rcx, [rsp+380h+var_328]
0x180139c78  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139c7d  mov     r14, qword ptr [rsp+380h+var_348]
0x180139c82  mov     rax, [r14]
0x180139c85  mov     rsi, [rax+50h]
0x180139c89  lea     rcx, [rsp+380h+var_358]
0x180139c8e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180139c93  lea     r8, [rsp+380h+var_358]
0x180139c98  mov     rdx, [rsp+380h+var_350]
0x180139c9d  mov     rcx, r14
0x180139ca0  mov     rax, rsi
0x180139ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139ca8  test    eax, eax
0x180139caa  js      loc_18013A013
0x180139cb0  mov     rcx, [rsp+380h+var_358]
0x180139cb5  mov     rax, [rcx]
0x180139cb8  lea     rdx, [rsp+380h+pvarg]
0x180139cbd  mov     rax, [rax+68h]
0x180139cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139cc6  test    eax, eax
0x180139cc8  js      loc_18013A013
0x180139cce  cmp     r12d, 1
0x180139cd2  jnz     loc_180139D85
0x180139cd8  cmp     dword ptr [rsp+380h+pvarg+8], r12d
0x180139cdd  jz      loc_180139D6C
0x180139ce3  lea     rcx, [rsp+380h+var_310]
0x180139ce8  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180139ced  nop
0x180139cee  lea     rdx, aScepCertInstal; "SCEP cert installation for "
0x180139cf5  lea     rcx, [rbp+280h+var_300]
0x180139cf9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139cfe  mov     rsi, rax
0x180139d01  mov     rcx, r15
0x180139d04  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139d09  mov     rdx, rax
0x180139d0c  mov     rcx, rsi
0x180139d0f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139d14  lea     rdx, aIsNotFinishedS; " is not finished successfully. Status: "
0x180139d1b  lea     rcx, [rbp+280h+var_300]
0x180139d1f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139d24  mov     edx, dword ptr [rsp+380h+pvarg+8]
0x180139d28  mov     rcx, rax
0x180139d2b  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x180139d31  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139d36  mov     rsi, rax
0x180139d39  lea     rdx, [rbp+280h+var_C0]
0x180139d40  lea     rcx, [rbp+280h+var_2F8]
0x180139d44  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180139d49  nop
0x180139d4a  lea     rdx, [rbp+280h+var_C0]
0x180139d51  mov     rcx, rsi
0x180139d54  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x180139d59  nop
0x180139d5a  lea     rcx, [rbp+280h+var_C0]
0x180139d61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139d66  nop
0x180139d67  jmp     loc_18013A0AF
0x180139d6c  lea     r9, [rsp+380h+var_360]
0x180139d71  lea     rdx, [rbp+280h+var_E0]
0x180139d78  mov     rcx, r13
0x180139d7b  call    ??$emplace_back@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY02$$CBGAEA_N@?$list@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@V?$allocator@VCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@QEAAAEAVCertInfo@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY02$$CBGAEA_N@Z; std::list<Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo>::emplace_back<std::wstring &,ushort const (&)[3],bool &>(std::wstring &,ushort const (&)[3],bool &)
0x180139d80  jmp     loc_18013A0BA
0x180139d85  cmp     dword ptr [rsp+380h+pvarg+8], 0
0x180139d8a  jz      loc_180139E5E
0x180139d90  lea     rcx, [rsp+380h+var_310]
0x180139d95  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180139d9a  nop
0x180139d9b  lea     rdx, aPfxCertInstall; "PFX cert installation for "
0x180139da2  lea     rcx, [rbp+280h+var_300]
0x180139da6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139dab  mov     rsi, rax
0x180139dae  mov     rcx, r15
0x180139db1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139db6  mov     rdx, rax
0x180139db9  mov     rcx, rsi
0x180139dbc  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139dc1  mov     rcx, rax
0x180139dc4  lea     rdx, aCompletedWithE; " completed with error 0x"
0x180139dcb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180139dd0  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180139dd7  lea     rcx, [rbp+280h+var_300]
0x180139ddb  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180139de1  mov     rsi, rax
0x180139de4  mov     edx, 8
0x180139de9  lea     rcx, [rbp+280h+var_210]
0x180139ded  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x180139df3  mov     rdx, rax
0x180139df6  mov     rcx, rsi
0x180139df9  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Smanip@_J@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::_Smanip<__int64> const &)
0x180139dfe  mov     rsi, rax
0x180139e01  mov     edx, 30h ; '0'
0x180139e06  mov     rcx, [rax]
0x180139e09  movsxd  rcx, dword ptr [rcx+4]
0x180139e0d  add     rcx, rax
0x180139e10  call    cs:__imp_?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_ios<ushort>::fill(ushort)
0x180139e16  mov     edx, dword ptr [rsp+380h+pvarg+8]
0x180139e1a  mov     rcx, rsi
0x180139e1d  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x180139e23  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139e28  mov     rsi, rax
0x180139e2b  lea     rdx, [rbp+280h+var_100]
0x180139e32  lea     rcx, [rbp+280h+var_2F8]
0x180139e36  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180139e3b  nop
0x180139e3c  lea     rdx, [rbp+280h+var_100]
0x180139e43  mov     rcx, rsi
0x180139e46  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x180139e4b  nop
0x180139e4c  lea     rcx, [rbp+280h+var_100]
0x180139e53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139e58  nop
0x180139e59  jmp     loc_18013A0AF
0x180139e5e  lea     rdx, aMy_0; "MY"
0x180139e65  lea     rcx, [rbp+280h+var_C0]
0x180139e6c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180139e71  nop
0x180139e72  lea     r8, aPfxcertpasswor; "/PFXCertPasswordEncryptionStore"
0x180139e79  mov     rdx, r15
0x180139e7c  lea     rcx, [rbp+280h+var_60]
0x180139e83  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180139e88  nop
0x180139e89  lea     rcx, [rbp+280h+var_60]
0x180139e90  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139e95  mov     rdx, rax
0x180139e98  lea     rcx, [rsp+380h+var_320]
0x180139e9d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180139ea2  mov     rdx, rax
0x180139ea5  lea     rcx, [rsp+380h+var_350]
0x180139eaa  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180139eaf  lea     rcx, [rsp+380h+var_320]
0x180139eb4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139eb9  mov     r14, qword ptr [rsp+380h+var_348]
0x180139ebe  mov     rax, [r14]
0x180139ec1  mov     rsi, [rax+50h]
0x180139ec5  lea     rcx, [rsp+380h+var_358]
0x180139eca  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180139ecf  lea     r8, [rsp+380h+var_358]
0x180139ed4  mov     rdx, [rsp+380h+var_350]
0x180139ed9  mov     rcx, r14
0x180139edc  mov     rax, rsi
0x180139edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139ee4  test    eax, eax
0x180139ee6  js      short loc_180139F24
0x180139ee8  mov     rcx, [rsp+380h+var_358]
0x180139eed  mov     rax, [rcx]
0x180139ef0  lea     rdx, [rsp+380h+pvarg]
0x180139ef5  mov     rax, [rax+68h]
0x180139ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139efe  test    eax, eax
0x180139f00  js      short loc_180139F24
0x180139f02  mov     eax, 8
0x180139f07  cmp     word ptr [rsp+380h+pvarg], ax
0x180139f0c  jnz     short loc_180139F24
0x180139f0e  mov     rdx, qword ptr [rsp+380h+pvarg+8]
0x180139f13  lea     rcx, [rbp+280h+var_C0]
0x180139f1a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180139f1f  jmp     loc_180139FCA
0x180139f24  lea     rcx, [rsp+380h+var_310]
0x180139f29  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180139f2e  nop
0x180139f2f  lea     rdx, aGettingNodeFor; "Getting node for PFX cert installation "...
  ... truncated ...
```
