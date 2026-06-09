# MsftCertInventoryActivity::ProcessInternalClientQuery(DeclaredConfigurationScopeData *,OrchestratorDCInfo *)

- ea: `0x180121750`
- end: `0x180121bf6`
- name: `?ProcessInternalClientQuery@MsftCertInventoryActivity@@AEAAJPEAUDeclaredConfigurationScopeData@@PEAUOrchestratorDCInfo@@@Z`
- size: `1190`
- prototype: `int(MsftCertInventoryActivity *__hidden this, struct DeclaredConfigurationScopeData *, struct OrchestratorDCInfo *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180121280`

## callees

- `0x1800117dc`
- `0x180014568`
- `0x1800145d8`
- `0x180016f58`
- `0x180018160`
- `0x1800186b8`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d090`
- `0x18001d0b0`
- `0x18004d158`
- `0x180056cf0`
- `0x1800600bc`
- `0x180086c10`
- `0x1800a155c`
- `0x180100ad8`
- `0x180102b9c`
- `0x180121658`
- `0x180121750`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801218aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801218aa`
- `OLEAUT32!__imp_SysAllocString` at `0x180121af4`
- `OLEAUT32!__imp_SysAllocString` at `0x180121af4`
- `OLEAUT32!__imp_VariantInit` at `0x18012198d`
- `OLEAUT32!__imp_VariantInit` at `0x180121ae0`
- `OLEAUT32!__imp_VariantInit` at `0x18012198d`
- `OLEAUT32!__imp_VariantInit` at `0x180121ae0`
- `OLEAUT32!__imp_VariantClear` at `0x18012191d`
- `OLEAUT32!__imp_VariantClear` at `0x180121979`
- `OLEAUT32!__imp_VariantClear` at `0x1801219c8`
- `OLEAUT32!__imp_VariantClear` at `0x180121b25`
- `OLEAUT32!__imp_VariantClear` at `0x180121b93`
- `OLEAUT32!__imp_VariantClear` at `0x180121bb2`
- `OLEAUT32!__imp_VariantClear` at `0x18012191d`
- `OLEAUT32!__imp_VariantClear` at `0x180121979`
- `OLEAUT32!__imp_VariantClear` at `0x1801219c8`
- `OLEAUT32!__imp_VariantClear` at `0x180121b25`
- `OLEAUT32!__imp_VariantClear` at `0x180121b93`
- `OLEAUT32!__imp_VariantClear` at `0x180121bb2`

## string_xrefs

- `0x1801218b8`: `OMADM::TargetedUserSID`
- `0x1801217d0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x18012182b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x18012186f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x180121908`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x1801219b2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x180121a46`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x180121abc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x180121b10`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\engine\activities\src\msftpolicies\msftcertinventoryactivity.cpp`
- `0x180121a96`: `%s@#&lt; URI path=&quot;%s&quot; value=&quot;%s&quot; /@gt;#`
- `0x180121805`: `CSP1\URI1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall MsftCertInventoryActivity::ProcessInternalClientQuery(
        MsftCertInventoryActivity *this,
        const unsigned __int16 **a2,
        struct OrchestratorDCInfo *a3)
{
  char *v5; // rsi
  char *v6; // r8
  const unsigned __int16 *v7; // rdi
  char *v8; // rdx
  int ResultsEnrollmentIdSidStateDocIdVersionKey_4; // ebx
  int v10; // eax
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  int v14; // eax
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  int ConfigNodeValue; // eax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  int v23; // [rsp+20h] [rbp-99h]
  int v24; // [rsp+20h] [rbp-99h]
  __int16 v25; // [rsp+40h] [rbp-79h] BYREF
  __int64 v26; // [rsp+48h] [rbp-71h]
  OLECHAR *psz[2]; // [rsp+50h] [rbp-69h] BYREF
  struct tagVARIANT v28; // [rsp+60h] [rbp-59h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int16 *v30; // [rsp+98h] [rbp-21h] BYREF
  HKEY v31; // [rsp+A0h] [rbp-19h] BYREF
  VARIANTARG v32; // [rsp+A8h] [rbp-11h] BYREF
  VARIANTARG v33; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  MsftCertInventoryActivity *v35; // [rsp+120h] [rbp+67h] BYREF
  unsigned __int16 *v36; // [rsp+130h] [rbp+77h] BYREF
  unsigned __int16 *v37; // [rsp+138h] [rbp+7Fh] BYREF

  v35 = this;
  v31 = 0;
  *(_OWORD *)&pvarg.vt = (unsigned __int64)&v31;
  *((_BYTE *)&pvarg.decVal + 16) = 1;
  v5 = (char *)a3 + 96;
  if ( *((_QWORD *)a3 + 15) <= 7u )
    v6 = (char *)a3 + 96;
  else
    v6 = *(char **)v5;
  v7 = (const unsigned __int16 *)((char *)a3 + 64);
  if ( *((_QWORD *)a3 + 11) <= 7u )
    v8 = (char *)a3 + 64;
  else
    v8 = *(char **)v7;
  ResultsEnrollmentIdSidStateDocIdVersionKey_4 = GetResultsEnrollmentIdSidStateDocIdVersionKey_4(
                                                   a2,
                                                   v8,
                                                   v6,
                                                   &pvarg.decVal.Lo32);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&pvarg);
  if ( ResultsEnrollmentIdSidStateDocIdVersionKey_4 >= 0 )
  {
    v35 = 0;
    *(_QWORD *)&pvarg.vt = &v35;
    pvarg.llVal = 0;
    *((_BYTE *)&pvarg.decVal + 16) = 1;
    ResultsEnrollmentIdSidStateDocIdVersionKey_4 = DCCDNUtil_GetRegistryString(
                                                     v31,
                                                     L"CSP1\\URI1",
                                                     L"value",
                                                     &pvarg.bstrVal);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&pvarg);
    if ( ResultsEnrollmentIdSidStateDocIdVersionKey_4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftcertinventoryactivity.cpp",
        (const char *)(unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4,
        v23);
LABEL_11:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
      goto LABEL_46;
    }
    v36 = 0;
    v25 = 0;
    v26 = 0;
    v10 = DCConfigManagerWrap::Initialize((DCConfigManagerWrap *)&v25);
    ResultsEnrollmentIdSidStateDocIdVersionKey_4 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      v12 = 208;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftcertinventoryactivity.cpp",
        (const char *)v11,
        v23);
LABEL_15:
      DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v25);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
      goto LABEL_11;
    }
    v13 = (_QWORD *)((char *)a3 + 32);
    if ( *((_QWORD *)a3 + 7) > 7u )
      v13 = (_QWORD *)*v13;
    if ( (unsigned int)_o__wcsicmp(v13, L"user") )
    {
      *(_QWORD *)&v28.vt = &v36;
      v28.llVal = 0;
      *((_BYTE *)&v28.decVal + 16) = 1;
      ResultsEnrollmentIdSidStateDocIdVersionKey_4 = DCStringCchPrintfAllStrings(
                                                       &v28.decVal.Lo32,
                                                       L"./Vendor/MSFT/CertificateStore/My/System/%s/EncodedCertificate",
                                                       1,
                                                       v35);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v28);
      if ( ResultsEnrollmentIdSidStateDocIdVersionKey_4 < 0 )
      {
        v11 = (unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4;
        v12 = 226;
        goto LABEL_14;
      }
    }
    else
    {
      wil::make_bstr(&v30, L"OMADM::TargetedUserSID");
      _variant_t::_variant_t((_variant_t *)&pvarg, a2[1]);
      v28 = pvarg;
      v14 = DCConfigManagerWrap::SetSessionVariable((DCConfigManagerWrap *)&v25, v30, &v28);
      ResultsEnrollmentIdSidStateDocIdVersionKey_4 = v14;
      if ( v14 < 0 )
      {
        v15 = (unsigned int)v14;
        v16 = 214;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\"
                        "msftcertinventoryactivity.cpp",
          (const char *)v15,
          v23);
        VariantClear(&pvarg);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
        goto LABEL_15;
      }
      *(_QWORD *)&v28.vt = &v36;
      v28.llVal = 0;
      *((_BYTE *)&v28.decVal + 16) = 1;
      ResultsEnrollmentIdSidStateDocIdVersionKey_4 = DCStringCchPrintfAllStrings(
                                                       &v28.decVal.Lo32,
                                                       L"./Vendor/MSFT/CertificateStore/My/User/%s/EncodedCertificate",
                                                       1,
                                                       v35);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v28);
      if ( ResultsEnrollmentIdSidStateDocIdVersionKey_4 < 0 )
      {
        v15 = (unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4;
        v16 = 219;
        goto LABEL_21;
      }
      VariantClear(&pvarg);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
    }
    VariantInit(&v32);
    ConfigNodeValue = DCConfigManagerWrap::GetConfigNodeValue((DCConfigManagerWrap *)&v25, v36, &v32);
    ResultsEnrollmentIdSidStateDocIdVersionKey_4 = ConfigNodeValue;
    if ( ConfigNodeValue >= 0 )
    {
      v37 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v37,
        0);
      v18 = SafeArrayToBase64Str(v32.parray, &v37);
      ResultsEnrollmentIdSidStateDocIdVersionKey_4 = v18;
      if ( v18 >= 0 )
      {
        psz[0] = 0;
        *(_QWORD *)&v28.vt = psz;
        v28.llVal = 0;
        *((_BYTE *)&v28.decVal + 16) = 1;
        v24 = (int)v36;
        ResultsEnrollmentIdSidStateDocIdVersionKey_4 = DCStringCchPrintfAllStrings(
                                                         &v28.decVal.Lo32,
                                                         L"%s@#&lt; URI path=&quot;%s&quot; value=&quot;%s&quot; /@gt;#",
                                                         3,
                                                         v35);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v28);
        if ( ResultsEnrollmentIdSidStateDocIdVersionKey_4 >= 0 )
        {
          VariantInit(&v33);
          v33.vt = 8;
          v33.llVal = (LONGLONG)SysAllocString(psz[0]);
          if ( v33.llVal )
          {
            if ( *((_QWORD *)v5 + 3) > 7u )
              v5 = *(char **)v5;
            if ( *((_QWORD *)a3 + 11) > 7u )
              v7 = *(const unsigned __int16 **)v7;
            v21 = DeclaredConfigurationStore_WriteResultData(
                    (struct DeclaredConfigurationScopeData *)a2,
                    v7,
                    (const unsigned __int16 *)v5,
                    0,
                    L"CSP1",
                    L"URI1",
                    L"value",
                    &v33);
            ResultsEnrollmentIdSidStateDocIdVersionKey_4 = v21;
            if ( v21 >= 0 )
            {
              VariantClear(&v33);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(psz);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
              VariantClear(&v32);
              DCConfigManagerWrap::~DCConfigManagerWrap((DCConfigManagerWrap *)&v25);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
              std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
              ResultsEnrollmentIdSidStateDocIdVersionKey_4 = 0;
              goto LABEL_46;
            }
            v19 = (unsigned int)v21;
            v20 = 258;
          }
          else
          {
            ResultsEnrollmentIdSidStateDocIdVersionKey_4 = -2147024882;
            v19 = 2147942414LL;
            v20 = 248;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicie"
                          "s\\msftcertinventoryactivity.cpp",
            (const char *)v19,
            v24);
          VariantClear(&v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicie"
                          "s\\msftcertinventoryactivity.cpp",
            (const char *)(unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4,
            v24);
        }
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(psz);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\"
                        "msftcertinventoryactivity.cpp",
          (const char *)(unsigned int)v18,
          v23);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\m"
                      "sftcertinventoryactivity.cpp",
        (const char *)(unsigned int)ConfigNodeValue,
        v23);
    }
    VariantClear(&v32);
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC5,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\engine\\activities\\src\\msftpolicies\\msftc"
                  "ertinventoryactivity.cpp",
    (const char *)(unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4,
    v23);
LABEL_46:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
  return (unsigned int)ResultsEnrollmentIdSidStateDocIdVersionKey_4;
}

```

## disassembly

```asm
0x180121750  mov     [rsp-8+arg_0], rcx
0x180121755  push    rbp
0x180121756  push    rbx
0x180121757  push    rsi
0x180121758  push    rdi
0x180121759  push    r12
0x18012175b  push    r14
0x18012175d  push    r15
0x18012175f  lea     rbp, [rsp-27h]
0x180121764  sub     rsp, 0E0h
0x18012176b  mov     r14, r8
0x18012176e  mov     r15, rdx
0x180121771  xor     r12d, r12d
0x180121774  mov     [rbp+57h+var_70], r12
0x180121778  lea     rax, [rbp+57h+var_70]
0x18012177c  mov     qword ptr [rbp+57h+pvarg], rax
0x180121780  mov     qword ptr [rbp+57h+pvarg+8], r12
0x180121784  mov     byte ptr [rbp+57h+pvarg+10h], 1
0x180121788  lea     rsi, [r8+60h]
0x18012178c  cmp     qword ptr [rsi+18h], 7
0x180121791  jbe     short loc_180121798
0x180121793  mov     r8, [rsi]
0x180121796  jmp     short loc_18012179B
0x180121798  mov     r8, rsi
0x18012179b  lea     rdi, [r14+40h]
0x18012179f  cmp     qword ptr [rdi+18h], 7
0x1801217a4  jbe     short loc_1801217AB
0x1801217a6  mov     rdx, [rdi]
0x1801217a9  jmp     short loc_1801217AE
0x1801217ab  mov     rdx, rdi
0x1801217ae  lea     r9, [rbp+57h+pvarg+8]
0x1801217b2  mov     rcx, r15
0x1801217b5  call    GetResultsEnrollmentIdSidStateDocIdVersionKey_4
0x1801217ba  mov     ebx, eax
0x1801217bc  lea     rcx, [rbp+57h+pvarg]
0x1801217c0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1801217c5  test    ebx, ebx
0x1801217c7  jns     short loc_1801217E6
0x1801217c9  mov     rcx, [rbp+5Fh]; this
0x1801217cd  mov     r9d, ebx; char *
0x1801217d0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801217d7  mov     edx, 0C5h; void *
0x1801217dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801217e1  jmp     loc_180121BD9
0x1801217e6  mov     [rbp+57h+arg_0], r12
0x1801217ea  lea     rax, [rbp+57h+arg_0]
0x1801217ee  mov     qword ptr [rbp+57h+pvarg], rax
0x1801217f2  mov     qword ptr [rbp+57h+pvarg+8], r12
0x1801217f6  mov     byte ptr [rbp+57h+pvarg+10h], 1
0x1801217fa  lea     r9, [rbp+57h+pvarg+8]; unsigned __int16 **
0x1801217fe  lea     r8, aValue_0; "value"
0x180121805  lea     rdx, aCsp1Uri1; "CSP1\\URI1"
0x18012180c  mov     rcx, [rbp+57h+var_70]; HKEY
0x180121810  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180121815  mov     ebx, eax
0x180121817  lea     rcx, [rbp+57h+pvarg]
0x18012181b  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180121820  test    ebx, ebx
0x180121822  jns     short loc_18012184B
0x180121824  mov     rcx, [rbp+5Fh]; this
0x180121828  mov     r9d, ebx; char *
0x18012182b  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180121832  mov     edx, 0C8h; void *
0x180121837  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012183c  nop
0x18012183d  lea     rcx, [rbp+57h+arg_0]
0x180121841  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121846  jmp     loc_180121BD9
0x18012184b  mov     [rbp+57h+arg_10], r12
0x18012184f  mov     [rbp+57h+var_D0], r12w
0x180121854  mov     [rbp+57h+var_C8], r12
0x180121858  lea     rcx, [rbp+57h+var_D0]; this
0x18012185c  call    ?Initialize@DCConfigManagerWrap@@QEAAJXZ; DCConfigManagerWrap::Initialize(void)
0x180121861  mov     ebx, eax
0x180121863  test    eax, eax
0x180121865  jns     short loc_180121895
0x180121867  mov     r9d, eax; char *
0x18012186a  mov     edx, 0D0h; void *
0x18012186f  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180121876  mov     rcx, [rbp+5Fh]; this
0x18012187a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012187f  nop
0x180121880  lea     rcx, [rbp+57h+var_D0]; this
0x180121884  call    ??1DCConfigManagerWrap@@QEAA@XZ; DCConfigManagerWrap::~DCConfigManagerWrap(void)
0x180121889  nop
0x18012188a  lea     rcx, [rbp+57h+arg_10]
0x18012188e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121893  jmp     short loc_18012183D
0x180121895  lea     rcx, [r14+20h]
0x180121899  cmp     qword ptr [rcx+18h], 7
0x18012189e  jbe     short loc_1801218A3
0x1801218a0  mov     rcx, [rcx]
0x1801218a3  lea     rdx, aUser_0; "user"
0x1801218aa  call    cs:__imp__o__wcsicmp
0x1801218b0  test    eax, eax
0x1801218b2  jnz     loc_1801219D3
0x1801218b8  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1801218bf  lea     rcx, [rbp+57h+var_78]
0x1801218c3  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801218c8  nop
0x1801218c9  mov     rdx, [r15+8]; unsigned __int16 *
0x1801218cd  lea     rcx, [rbp+57h+pvarg]; this
0x1801218d1  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x1801218d6  nop
0x1801218d7  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1801218db  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1801218e0  movaps  xmmword ptr [rbp+57h+var_B0], xmm0
0x1801218e4  movsd   qword ptr [rbp+57h+var_B0+10h], xmm1
0x1801218e9  lea     r8, [rbp+57h+var_B0]; struct tagVARIANT
0x1801218ed  mov     rdx, [rbp+57h+var_78]; unsigned __int16 *
0x1801218f1  lea     rcx, [rbp+57h+var_D0]; this
0x1801218f5  call    ?SetSessionVariable@DCConfigManagerWrap@@QEBAJPEAGUtagVARIANT@@@Z; DCConfigManagerWrap::SetSessionVariable(ushort *,tagVARIANT)
0x1801218fa  mov     ebx, eax
0x1801218fc  test    eax, eax
0x1801218fe  jns     short loc_180121932
0x180121900  mov     r9d, eax; char *
0x180121903  mov     edx, 0D6h; void *
0x180121908  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18012190f  mov     rcx, [rbp+5Fh]; this
0x180121913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121918  nop
0x180121919  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18012191d  call    cs:__imp_VariantClear
0x180121923  nop
0x180121924  lea     rcx, [rbp+57h+var_78]
0x180121928  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012192d  jmp     loc_180121880
0x180121932  lea     rax, [rbp+57h+arg_10]
0x180121936  mov     qword ptr [rbp+57h+var_B0], rax
0x18012193a  mov     qword ptr [rbp+57h+var_B0+8], r12
0x18012193e  mov     byte ptr [rbp+57h+var_B0+10h], 1
0x180121942  mov     r9, [rbp+57h+arg_0]
0x180121946  mov     r8d, 1
0x18012194c  lea     rdx, aVendorMsftCert_0; "./Vendor/MSFT/CertificateStore/My/User/"...
0x180121953  lea     rcx, [rbp+57h+var_B0+8]
0x180121957  call    DCStringCchPrintfAllStrings
0x18012195c  mov     ebx, eax
0x18012195e  lea     rcx, [rbp+57h+var_B0]
0x180121962  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180121967  test    ebx, ebx
0x180121969  jns     short loc_180121975
0x18012196b  mov     r9d, ebx
0x18012196e  mov     edx, 0DBh
0x180121973  jmp     short loc_180121908
0x180121975  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180121979  call    cs:__imp_VariantClear
0x18012197f  nop
0x180121980  lea     rcx, [rbp+57h+var_78]
0x180121984  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180121989  lea     rcx, [rbp+57h+var_68]; pvarg
0x18012198d  call    cs:__imp_VariantInit
0x180121993  nop
0x180121994  lea     r8, [rbp+57h+var_68]; pvarg
0x180121998  mov     rdx, [rbp+57h+arg_10]; unsigned __int16 *
0x18012199c  lea     rcx, [rbp+57h+var_D0]; this
0x1801219a0  call    ?GetConfigNodeValue@DCConfigManagerWrap@@QEBAJPEBGPEAUtagVARIANT@@@Z; DCConfigManagerWrap::GetConfigNodeValue(ushort const *,tagVARIANT *)
0x1801219a5  mov     ebx, eax
0x1801219a7  test    eax, eax
0x1801219a9  jns     short loc_180121A1D
0x1801219ab  mov     rcx, [rbp+5Fh]; this
0x1801219af  mov     r9d, eax; char *
0x1801219b2  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1801219b9  mov     edx, 0E6h; void *
0x1801219be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801219c3  nop
0x1801219c4  lea     rcx, [rbp+57h+var_68]; pvarg
0x1801219c8  call    cs:__imp_VariantClear
0x1801219ce  jmp     loc_180121880
0x1801219d3  lea     rax, [rbp+57h+arg_10]
0x1801219d7  mov     qword ptr [rbp+57h+var_B0], rax
0x1801219db  mov     qword ptr [rbp+57h+var_B0+8], r12
0x1801219df  mov     byte ptr [rbp+57h+var_B0+10h], 1
0x1801219e3  mov     r9, [rbp+57h+arg_0]
0x1801219e7  mov     r8d, 1
0x1801219ed  lea     rdx, aVendorMsftCert; "./Vendor/MSFT/CertificateStore/My/Syste"...
0x1801219f4  lea     rcx, [rbp+57h+var_B0+8]
0x1801219f8  call    DCStringCchPrintfAllStrings
0x1801219fd  mov     ebx, eax
0x1801219ff  lea     rcx, [rbp+57h+var_B0]
0x180121a03  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180121a08  test    ebx, ebx
0x180121a0a  jns     loc_180121989
0x180121a10  mov     r9d, ebx
0x180121a13  mov     edx, 0E2h
0x180121a18  jmp     loc_18012186F
0x180121a1d  mov     [rbp+57h+arg_18], r12
0x180121a21  xor     edx, edx
0x180121a23  lea     rcx, [rbp+57h+arg_18]
0x180121a27  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180121a2c  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 **
0x180121a30  mov     rcx, qword ptr [rbp+57h+var_68+8]; psa
0x180121a34  call    ?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z; SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)
0x180121a39  mov     ebx, eax
0x180121a3b  test    eax, eax
0x180121a3d  jns     short loc_180121A66
0x180121a3f  mov     rcx, [rbp+5Fh]; this
0x180121a43  mov     r9d, eax; char *
0x180121a46  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180121a4d  mov     edx, 0E9h; void *
0x180121a52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121a57  nop
0x180121a58  lea     rcx, [rbp+57h+arg_18]
0x180121a5c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180121a61  jmp     loc_1801219C4
0x180121a66  mov     [rbp+57h+psz], r12
0x180121a6a  mov     rax, [rbp+57h+arg_18]
0x180121a6e  mov     rcx, [rbp+57h+arg_10]
0x180121a72  lea     rdx, [rbp+57h+psz]
0x180121a76  mov     qword ptr [rbp+57h+var_B0], rdx
0x180121a7a  mov     qword ptr [rbp+57h+var_B0+8], r12
0x180121a7e  mov     byte ptr [rbp+57h+var_B0+10h], 1
0x180121a82  mov     [rsp+110h+var_E8], rax
0x180121a87  mov     [rsp+110h+var_F0], rcx; int
0x180121a8c  mov     r9, [rbp+57h+arg_0]
0x180121a90  mov     r8d, 3
0x180121a96  lea     rdx, aSLtUriPathQuot; "%s@#&lt; URI path=&quot;%s&quot; value="...
0x180121a9d  lea     rcx, [rbp+57h+var_B0+8]
0x180121aa1  call    DCStringCchPrintfAllStrings
0x180121aa6  mov     ebx, eax
0x180121aa8  lea     rcx, [rbp+57h+var_B0]
0x180121aac  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x180121ab1  test    ebx, ebx
0x180121ab3  jns     short loc_180121ADC
0x180121ab5  mov     rcx, [rbp+5Fh]; this
0x180121ab9  mov     r9d, ebx; char *
0x180121abc  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180121ac3  mov     edx, 0F3h; void *
0x180121ac8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121acd  nop
0x180121ace  lea     rcx, [rbp+57h+psz]
0x180121ad2  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121ad7  jmp     loc_180121A58
0x180121adc  lea     rcx, [rbp+57h+var_50]; pvarg
0x180121ae0  call    cs:__imp_VariantInit
0x180121ae6  nop
0x180121ae7  mov     eax, 8
0x180121aec  mov     word ptr [rbp+57h+var_50], ax
0x180121af0  mov     rcx, [rbp+57h+psz]; psz
0x180121af4  call    cs:__imp_SysAllocString
0x180121afa  mov     qword ptr [rbp+57h+var_50+8], rax
0x180121afe  test    rax, rax
0x180121b01  jnz     short loc_180121B2D
0x180121b03  mov     ebx, 8007000Eh
0x180121b08  mov     r9d, ebx; char *
0x180121b0b  mov     edx, 0F8h; void *
0x180121b10  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x180121b17  mov     rcx, [rbp+5Fh]; this
0x180121b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121b20  nop
0x180121b21  lea     rcx, [rbp+57h+var_50]; pvarg
0x180121b25  call    cs:__imp_VariantClear
0x180121b2b  jmp     short loc_180121ACE
0x180121b2d  cmp     qword ptr [rsi+18h], 7
0x180121b32  jbe     short loc_180121B37
0x180121b34  mov     rsi, [rsi]
0x180121b37  cmp     qword ptr [rdi+18h], 7
0x180121b3c  jbe     short loc_180121B41
0x180121b3e  mov     rdi, [rdi]
0x180121b41  lea     rax, [rbp+57h+var_50]
0x180121b45  mov     [rsp+110h+var_D8], rax; struct tagVARIANT *
0x180121b4a  lea     rax, aValue_0; "value"
0x180121b51  mov     [rsp+110h+lpValueName], rax; lpValueName
0x180121b56  lea     rax, aUri1; "URI1"
0x180121b5d  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x180121b62  lea     rax, aCsp1; "CSP1"
0x180121b69  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x180121b6e  xor     r9d, r9d; unsigned __int16 *
0x180121b71  mov     r8, rsi; unsigned __int16 *
0x180121b74  mov     rdx, rdi; unsigned __int16 *
0x180121b77  mov     rcx, r15; struct DeclaredConfigurationScopeData *
0x180121b7a  call    ?DeclaredConfigurationStore_WriteResultData@@YAJPEAUDeclaredConfigurationScopeData@@PEBG11111PEAUtagVARIANT@@@Z; DeclaredConfigurationStore_WriteResultData(DeclaredConfigurationScopeData *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,tagVARIANT *)
0x180121b7f  mov     ebx, eax
0x180121b81  test    eax, eax
0x180121b83  jns     short loc_180121B8F
0x180121b85  mov     r9d, eax
0x180121b88  mov     edx, 102h
0x180121b8d  jmp     short loc_180121B10
0x180121b8f  lea     rcx, [rbp+57h+var_50]; pvarg
0x180121b93  call    cs:__imp_VariantClear
0x180121b99  nop
0x180121b9a  lea     rcx, [rbp+57h+psz]
0x180121b9e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121ba3  nop
0x180121ba4  lea     rcx, [rbp+57h+arg_18]
0x180121ba8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180121bad  nop
0x180121bae  lea     rcx, [rbp+57h+var_68]; pvarg
0x180121bb2  call    cs:__imp_VariantClear
0x180121bb8  nop
0x180121bb9  lea     rcx, [rbp+57h+var_D0]; this
0x180121bbd  call    ??1DCConfigManagerWrap@@QEAA@XZ; DCConfigManagerWrap::~DCConfigManagerWrap(void)
0x180121bc2  nop
0x180121bc3  lea     rcx, [rbp+57h+arg_10]
0x180121bc7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121bcc  nop
0x180121bcd  lea     rcx, [rbp+57h+arg_0]
0x180121bd1  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180121bd6  mov     ebx, r12d
0x180121bd9  lea     rcx, [rbp+57h+var_70]
0x180121bdd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
  ... truncated ...
```
