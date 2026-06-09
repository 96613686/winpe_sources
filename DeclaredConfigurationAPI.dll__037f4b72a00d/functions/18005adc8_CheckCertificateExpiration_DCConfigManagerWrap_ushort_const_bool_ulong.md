# CheckCertificateExpiration(DCConfigManagerWrap *,ushort const *,bool,ulong)

- ea: `0x18005adc8`
- end: `0x18005b263`
- name: `?CheckCertificateExpiration@@YAJPEAVDCConfigManagerWrap@@PEBG_NK@Z`
- size: `1179`
- prototype: `__int64 __fastcall(struct DCConfigManagerWrap *this, const unsigned __int16 *, bool, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c05c`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x18001438c`
- `0x180016a54`
- `0x180016f58`
- `0x180018ac0`
- `0x18001924c`
- `0x180019270`
- `0x18001d090`
- `0x18004d158`
- `0x180058678`
- `0x18005adc8`
- `0x180102b9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0cc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005b13c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005b154`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005b13c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005b154`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005b0fa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18005b0fa`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005b10e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18005b10e`
- `CRYPT32!CertCreateCertificateContext` at `0x18005b0b9`
- `CRYPT32!CertCreateCertificateContext` at `0x18005b0b9`
- `OLEAUT32!__imp_VariantInit` at `0x18005ae47`
- `OLEAUT32!__imp_VariantInit` at `0x18005af9c`
- `OLEAUT32!__imp_VariantInit` at `0x18005ae47`
- `OLEAUT32!__imp_VariantInit` at `0x18005af9c`
- `OLEAUT32!__imp_VariantClear` at `0x18005b014`
- `OLEAUT32!__imp_VariantClear` at `0x18005b17a`
- `OLEAUT32!__imp_VariantClear` at `0x18005b19a`
- `OLEAUT32!__imp_VariantClear` at `0x18005b1e0`
- `OLEAUT32!__imp_VariantClear` at `0x18005b200`
- `OLEAUT32!__imp_VariantClear` at `0x18005b22e`
- `OLEAUT32!__imp_VariantClear` at `0x18005b014`
- `OLEAUT32!__imp_VariantClear` at `0x18005b17a`
- `OLEAUT32!__imp_VariantClear` at `0x18005b19a`
- `OLEAUT32!__imp_VariantClear` at `0x18005b1e0`
- `OLEAUT32!__imp_VariantClear` at `0x18005b200`
- `OLEAUT32!__imp_VariantClear` at `0x18005b22e`
- `DMCmnUtils!DecodeBase64W` at `0x18005b097`
- `DMCmnUtils!DecodeBase64W` at `0x18005b097`

## string_xrefs

- `0x18005ae2a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005ae6e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005afce`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005affd`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005b063`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005b1b2`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005b217`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CheckCertificateExpiration(
        struct DCConfigManagerWrap *this,
        const unsigned __int16 *a2,
        char a3,
        unsigned int a4)
{
  __int64 v4; // r12
  int DoesConfigNodeExist; // eax
  unsigned int v9; // edi
  int ConfigNodeValue; // eax
  unsigned int v12; // ebx
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // r14
  int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const unsigned __int16 *v20; // rdx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  PCCERT_CONTEXT CertificateContext; // rsi
  signed int LastError; // eax
  __int64 v26; // rdx
  unsigned __int16 *v27; // [rsp+20h] [rbp-E0h] BYREF
  PCCERT_CONTEXT v28; // [rsp+28h] [rbp-D8h] BYREF
  DWORD cbCertEncoded; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG v31; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *pbCertEncoded; // [rsp+58h] [rbp-A8h] BYREF
  FILETIME FileTime1; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v35[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[32]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v40[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v41[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v42[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v43[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v4 = a4;
  LODWORD(v28) = 0;
  DoesConfigNodeExist = DCConfigManagerWrap::DoesConfigNodeExist(this, a2);
  v9 = DoesConfigNodeExist;
  if ( DoesConfigNodeExist != 1 )
  {
    if ( DoesConfigNodeExist < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34BC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)DoesConfigNodeExist,
        (int)v27);
      return v9;
    }
    VariantInit(&pvarg);
    ConfigNodeValue = DCConfigManagerWrap::GetConfigNodeValue(this, a2, &pvarg);
    v12 = ConfigNodeValue;
    if ( ConfigNodeValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34BF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)ConfigNodeValue,
        (int)v27);
LABEL_42:
      VariantClear(&pvarg);
      return v12;
    }
    if ( pvarg.vt == 8 )
    {
      if ( pvarg.llVal )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(pvarg.llVal + 2 * v13) );
        if ( v13 )
        {
          std::wstring::wstring((__int64)v36, pvarg.llVal);
          v14 = std::wstring::wstring((__int64)v43, (__int64)L"/EncodedCertificate");
          if ( a3 )
          {
            v15 = std::wstring::wstring((__int64)v42, (__int64)L"User/");
            v16 = 1;
          }
          else
          {
            v15 = std::wstring::wstring((__int64)v41, (__int64)L"System/");
            v16 = 2;
          }
          LODWORD(v28) = v16;
          v17 = std::wstring::wstring((__int64)v40, (__int64)L"./Device/Vendor/MSFT/CertificateStore/My/");
          v18 = std::operator+<unsigned short>(v39, v17, v15);
          v19 = std::operator+<unsigned short>(v38, v18, v36);
          std::operator+<unsigned short>(v35, v19, v14);
          std::wstring::_Tidy_deallocate(v38);
          std::wstring::_Tidy_deallocate(v39);
          std::wstring::_Tidy_deallocate(v40);
          if ( (v16 & 2) != 0 )
          {
            LOBYTE(v16) = v16 & 0xFD;
            std::wstring::_Tidy_deallocate(v41);
          }
          if ( (v16 & 1) != 0 )
            std::wstring::_Tidy_deallocate(v42);
          std::wstring::_Tidy_deallocate(v43);
          VariantInit(&v31);
          v20 = (const unsigned __int16 *)v35;
          if ( v35[3] > (unsigned __int16 *)7 )
            v20 = v35[0];
          v21 = DCConfigManagerWrap::GetConfigNodeValue(this, v20, &v31);
          v12 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x34CA,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)(unsigned int)v21,
              (int)v27);
LABEL_41:
            VariantClear(&v31);
            std::wstring::_Tidy_deallocate(v35);
            std::wstring::_Tidy_deallocate(v36);
            goto LABEL_42;
          }
          if ( v31.vt != 8209 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x34CE,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
              (const char *)0x80070002LL,
              (int)v27);
            VariantClear(&v31);
            std::wstring::_Tidy_deallocate(v35);
            std::wstring::_Tidy_deallocate(v36);
            v12 = -2147024894;
            goto LABEL_42;
          }
          v27 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v27,
            0);
          v22 = SafeArrayToBase64Str(v31.parray, &v27);
          v12 = v22;
          if ( v22 >= 0 )
          {
            pbCertEncoded = 0;
            cbCertEncoded = 0;
            v22 = DecodeBase64W(v27, &pbCertEncoded, (int *)&cbCertEncoded);
            v12 = v22;
            if ( v22 >= 0 )
            {
              CertificateContext = CertCreateCertificateContext(1u, pbCertEncoded, cbCertEncoded);
              v28 = CertificateContext;
              if ( CertificateContext )
                goto LABEL_35;
              LastError = GetLastError();
              v12 = LastError;
              if ( LastError > 0 )
                v12 = (unsigned __int16)LastError | 0x80070000;
              if ( (v12 & 0x80000000) == 0 )
              {
LABEL_35:
                SystemTime = 0;
                GetSystemTime(&SystemTime);
                FileTime = 0;
                SystemTimeToFileTime(&SystemTime, &FileTime);
                FileTime1 = (FILETIME)(600000000 * v4 + *(_QWORD *)&FileTime);
                if ( CompareFileTime(&FileTime1, &CertificateContext->pCertInfo->NotAfter) != 1
                  && CompareFileTime(&FileTime, &CertificateContext->pCertInfo->NotBefore) != -1 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v28);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
                  VariantClear(&v31);
                  std::wstring::_Tidy_deallocate(v35);
                  std::wstring::_Tidy_deallocate(v36);
                  VariantClear(&pvarg);
                  return v9;
                }
                v12 = -2146762495;
                v26 = 13552;
              }
              else
              {
                v26 = 13534;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v26,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
                (const char *)v12,
                (int)v27);
              wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v28);
              goto LABEL_40;
            }
            v23 = 13528;
          }
          else
          {
            v23 = 13523;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
            (const char *)(unsigned int)v22,
            (int)v27);
LABEL_40:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
          goto LABEL_41;
        }
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34C3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
      (const char *)0x80070002LL,
      (int)v27);
    VariantClear(&pvarg);
  }
  return 2147942402LL;
}

```

## disassembly

```asm
0x18005adc8  mov     [rsp-8+arg_10], rbx
0x18005adcd  push    rbp
0x18005adce  push    rsi
0x18005adcf  push    rdi
0x18005add0  push    r12
0x18005add2  push    r13
0x18005add4  push    r14
0x18005add6  push    r15
0x18005add8  lea     rbp, [rsp-0A0h]
0x18005ade0  sub     rsp, 1A0h
0x18005ade7  mov     rax, cs:__security_cookie
0x18005adee  xor     rax, rsp
0x18005adf1  mov     [rbp+0D0h+var_40], rax
0x18005adf8  mov     r12d, r9d
0x18005adfb  mov     r14b, r8b
0x18005adfe  mov     rbx, rdx
0x18005ae01  mov     rsi, rcx
0x18005ae04  xor     r13d, r13d
0x18005ae07  mov     dword ptr [rsp+1D0h+var_1A8], r13d
0x18005ae0c  call    ?DoesConfigNodeExist@DCConfigManagerWrap@@QEBAJPEBG@Z; DCConfigManagerWrap::DoesConfigNodeExist(ushort const *)
0x18005ae11  mov     edi, eax
0x18005ae13  cmp     eax, 1
0x18005ae16  jz      loc_18005B234
0x18005ae1c  test    eax, eax
0x18005ae1e  jns     short loc_18005AE42
0x18005ae20  mov     rcx, [rbp+0D8h]; this
0x18005ae27  mov     r9d, eax; char *
0x18005ae2a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005ae31  mov     edx, 34BCh; void *
0x18005ae36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae3b  mov     eax, edi
0x18005ae3d  jmp     loc_18005B239
0x18005ae42  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x18005ae47  call    cs:__imp_VariantInit
0x18005ae4d  nop
0x18005ae4e  lea     r8, [rsp+1D0h+pvarg]; pvarg
0x18005ae53  mov     rdx, rbx; unsigned __int16 *
0x18005ae56  mov     rcx, rsi; this
0x18005ae59  call    ?GetConfigNodeValue@DCConfigManagerWrap@@QEBAJPEBGPEAUtagVARIANT@@@Z; DCConfigManagerWrap::GetConfigNodeValue(ushort const *,tagVARIANT *)
0x18005ae5e  mov     ebx, eax
0x18005ae60  test    eax, eax
0x18005ae62  jns     short loc_18005AE84
0x18005ae64  mov     rcx, [rbp+0D8h]; this
0x18005ae6b  mov     r9d, eax; char *
0x18005ae6e  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005ae75  mov     edx, 34BFh; void *
0x18005ae7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ae7f  jmp     loc_18005B1FB
0x18005ae84  cmp     word ptr [rsp+1D0h+pvarg], 8
0x18005ae8a  jnz     loc_18005B20A
0x18005ae90  mov     rdx, qword ptr [rsp+1D0h+pvarg+8]
0x18005ae95  test    rdx, rdx
0x18005ae98  jz      loc_18005B20A
0x18005ae9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005aea2  inc     rax
0x18005aea5  cmp     [rdx+rax*2], r13w
0x18005aeaa  jnz     short loc_18005AEA2
0x18005aeac  test    rax, rax
0x18005aeaf  jz      loc_18005B20A
0x18005aeb5  lea     rcx, [rbp+0D0h+var_130]
0x18005aeb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005aebe  nop
0x18005aebf  lea     rdx, aEncodedcertifi; "/EncodedCertificate"
0x18005aec6  lea     rcx, [rbp+0D0h+var_60]
0x18005aeca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005aecf  mov     r15, rax
0x18005aed2  test    r14b, r14b
0x18005aed5  jz      short loc_18005AEF1
0x18005aed7  lea     rdx, aUser_1; "User/"
0x18005aede  lea     rcx, [rbp+0D0h+var_80]
0x18005aee2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005aee7  mov     r14, rax
0x18005aeea  mov     ebx, 1
0x18005aeef  jmp     short loc_18005AF09
0x18005aef1  lea     rdx, aSystem; "System/"
0x18005aef8  lea     rcx, [rbp+0D0h+var_A0]
0x18005aefc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005af01  mov     r14, rax
0x18005af04  mov     ebx, 2
0x18005af09  mov     dword ptr [rsp+1D0h+var_1A8], ebx
0x18005af0d  lea     rdx, aDeviceVendorMs_0; "./Device/Vendor/MSFT/CertificateStore/M"...
0x18005af14  lea     rcx, [rbp+0D0h+var_C0]
0x18005af18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005af1d  nop
0x18005af1e  mov     r8, r14
0x18005af21  mov     rdx, rax
0x18005af24  lea     rcx, [rbp+0D0h+var_E0]
0x18005af28  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18005af2d  nop
0x18005af2e  lea     r8, [rbp+0D0h+var_130]
0x18005af32  mov     rdx, rax
0x18005af35  lea     rcx, [rbp+0D0h+var_100]
0x18005af39  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18005af3e  nop
0x18005af3f  mov     r8, r15
0x18005af42  mov     rdx, rax
0x18005af45  lea     rcx, [rbp+0D0h+var_150]
0x18005af49  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18005af4e  nop
0x18005af4f  lea     rcx, [rbp+0D0h+var_100]
0x18005af53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af58  nop
0x18005af59  lea     rcx, [rbp+0D0h+var_E0]
0x18005af5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af62  nop
0x18005af63  lea     rcx, [rbp+0D0h+var_C0]
0x18005af67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af6c  nop
0x18005af6d  test    bl, 2
0x18005af70  jz      short loc_18005AF7F
0x18005af72  and     ebx, 0FFFFFFFDh
0x18005af75  lea     rcx, [rbp+0D0h+var_A0]
0x18005af79  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af7e  nop
0x18005af7f  test    bl, 1
0x18005af82  jz      short loc_18005AF8E
0x18005af84  lea     rcx, [rbp+0D0h+var_80]
0x18005af88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af8d  nop
0x18005af8e  lea     rcx, [rbp+0D0h+var_60]
0x18005af92  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005af97  lea     rcx, [rsp+1D0h+var_190]; pvarg
0x18005af9c  call    cs:__imp_VariantInit
0x18005afa2  nop
0x18005afa3  lea     rdx, [rbp+0D0h+var_150]
0x18005afa7  cmp     [rbp+0D0h+var_138], 7
0x18005afac  cmova   rdx, [rbp+0D0h+var_150]; unsigned __int16 *
0x18005afb1  lea     r8, [rsp+1D0h+var_190]; pvarg
0x18005afb6  mov     rcx, rsi; this
0x18005afb9  call    ?GetConfigNodeValue@DCConfigManagerWrap@@QEBAJPEBGPEAUtagVARIANT@@@Z; DCConfigManagerWrap::GetConfigNodeValue(ushort const *,tagVARIANT *)
0x18005afbe  mov     ebx, eax
0x18005afc0  test    eax, eax
0x18005afc2  jns     short loc_18005AFE4
0x18005afc4  mov     rcx, [rbp+0D8h]; this
0x18005afcb  mov     r9d, eax; char *
0x18005afce  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005afd5  mov     edx, 34CAh; void *
0x18005afda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005afdf  jmp     loc_18005B1DB
0x18005afe4  mov     eax, 2011h
0x18005afe9  cmp     word ptr [rsp+1D0h+var_190], ax
0x18005afee  jz      short loc_18005B038
0x18005aff0  mov     rcx, [rbp+0D8h]; this
0x18005aff7  mov     r9d, 80070002h; char *
0x18005affd  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005b004  mov     edx, 34CEh; void *
0x18005b009  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b00e  nop
0x18005b00f  lea     rcx, [rsp+1D0h+var_190]; pvarg
0x18005b014  call    cs:__imp_VariantClear
0x18005b01a  nop
0x18005b01b  lea     rcx, [rbp+0D0h+var_150]
0x18005b01f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b024  nop
0x18005b025  lea     rcx, [rbp+0D0h+var_130]
0x18005b029  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b02e  mov     ebx, 80070002h
0x18005b033  jmp     loc_18005B1FB
0x18005b038  mov     [rsp+1D0h+var_1B0], r13; int
0x18005b03d  xor     edx, edx
0x18005b03f  lea     rcx, [rsp+1D0h+var_1B0]
0x18005b044  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005b049  lea     rdx, [rsp+1D0h+var_1B0]; unsigned __int16 **
0x18005b04e  mov     rcx, qword ptr [rsp+1D0h+var_190+8]; psa
0x18005b053  call    ?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z; SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)
0x18005b058  mov     ebx, eax
0x18005b05a  test    eax, eax
0x18005b05c  jns     short loc_18005B07E
0x18005b05e  mov     edx, 34D3h; void *
0x18005b063  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005b06a  mov     r9d, eax; char *
0x18005b06d  mov     rcx, [rbp+0D8h]; this
0x18005b074  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b079  jmp     loc_18005B1D0
0x18005b07e  mov     [rsp+1D0h+pbCertEncoded], r13
0x18005b083  mov     [rsp+1D0h+cbCertEncoded], r13d
0x18005b088  lea     r8, [rsp+1D0h+cbCertEncoded]
0x18005b08d  lea     rdx, [rsp+1D0h+pbCertEncoded]
0x18005b092  mov     rcx, [rsp+1D0h+var_1B0]
0x18005b097  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x18005b09d  mov     ebx, eax
0x18005b09f  test    eax, eax
0x18005b0a1  jns     short loc_18005B0AA
0x18005b0a3  mov     edx, 34D8h
0x18005b0a8  jmp     short loc_18005B063
0x18005b0aa  mov     r8d, [rsp+1D0h+cbCertEncoded]; cbCertEncoded
0x18005b0af  mov     rdx, [rsp+1D0h+pbCertEncoded]; pbCertEncoded
0x18005b0b4  mov     ecx, 1; dwCertEncodingType
0x18005b0b9  call    cs:__imp_CertCreateCertificateContext
0x18005b0bf  mov     rsi, rax
0x18005b0c2  mov     [rsp+1D0h+var_1A8], rax
0x18005b0c7  test    rax, rax
0x18005b0ca  jnz     short loc_18005B0EF
0x18005b0cc  call    cs:__imp_GetLastError
0x18005b0d2  mov     ebx, eax
0x18005b0d4  test    eax, eax
0x18005b0d6  jle     short loc_18005B0E1
0x18005b0d8  movzx   ebx, ax
0x18005b0db  or      ebx, 80070000h
0x18005b0e1  test    ebx, ebx
0x18005b0e3  jns     short loc_18005B0EF
0x18005b0e5  mov     edx, 34DEh
0x18005b0ea  jmp     loc_18005B1AF
0x18005b0ef  xorps   xmm0, xmm0
0x18005b0f2  movups  xmmword ptr [rbp+0D0h+SystemTime.wYear], xmm0
0x18005b0f6  lea     rcx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18005b0fa  call    cs:__imp_GetSystemTime
0x18005b100  mov     qword ptr [rsp+1D0h+FileTime.dwLowDateTime], r13
0x18005b105  lea     rdx, [rsp+1D0h+FileTime]; lpFileTime
0x18005b10a  lea     rcx, [rbp+0D0h+SystemTime]; lpSystemTime
0x18005b10e  call    cs:__imp_SystemTimeToFileTime
0x18005b114  mov     rax, qword ptr [rsp+1D0h+FileTime.dwLowDateTime]
0x18005b119  imul    rdx, r12, 23C34600h
0x18005b120  add     rax, rdx
0x18005b123  mov     [rsp+1D0h+FileTime1.dwLowDateTime], eax
0x18005b127  shr     rax, 20h
0x18005b12b  mov     [rsp+1D0h+FileTime1.dwHighDateTime], eax
0x18005b12f  mov     rdx, [rsi+18h]
0x18005b133  add     rdx, 48h ; 'H'; lpFileTime2
0x18005b137  lea     rcx, [rsp+1D0h+FileTime1]; lpFileTime1
0x18005b13c  call    cs:__imp_CompareFileTime
0x18005b142  cmp     eax, 1
0x18005b145  jz      short loc_18005B1A5
0x18005b147  mov     rdx, [rsi+18h]
0x18005b14b  add     rdx, 40h ; '@'; lpFileTime2
0x18005b14f  lea     rcx, [rsp+1D0h+FileTime]; lpFileTime1
0x18005b154  call    cs:__imp_CompareFileTime
0x18005b15a  cmp     eax, 0FFFFFFFFh
0x18005b15d  jz      short loc_18005B1A5
0x18005b15f  lea     rcx, [rsp+1D0h+var_1A8]
0x18005b164  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18005b169  nop
0x18005b16a  lea     rcx, [rsp+1D0h+var_1B0]
0x18005b16f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005b174  nop
0x18005b175  lea     rcx, [rsp+1D0h+var_190]; pvarg
0x18005b17a  call    cs:__imp_VariantClear
0x18005b180  nop
0x18005b181  lea     rcx, [rbp+0D0h+var_150]
0x18005b185  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b18a  nop
0x18005b18b  lea     rcx, [rbp+0D0h+var_130]
0x18005b18f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b194  nop
0x18005b195  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x18005b19a  call    cs:__imp_VariantClear
0x18005b1a0  jmp     loc_18005AE3B
0x18005b1a5  mov     ebx, 800B0101h
0x18005b1aa  mov     edx, 34F0h; void *
0x18005b1af  mov     r9d, ebx; char *
0x18005b1b2  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005b1b9  mov     rcx, [rbp+0D8h]; this
0x18005b1c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b1c5  lea     rcx, [rsp+1D0h+var_1A8]
0x18005b1ca  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18005b1cf  nop
0x18005b1d0  lea     rcx, [rsp+1D0h+var_1B0]
0x18005b1d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18005b1da  nop
0x18005b1db  lea     rcx, [rsp+1D0h+var_190]; pvarg
0x18005b1e0  call    cs:__imp_VariantClear
0x18005b1e6  nop
0x18005b1e7  lea     rcx, [rbp+0D0h+var_150]
0x18005b1eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b1f0  nop
0x18005b1f1  lea     rcx, [rbp+0D0h+var_130]
0x18005b1f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005b1fa  nop
0x18005b1fb  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x18005b200  call    cs:__imp_VariantClear
0x18005b206  mov     eax, ebx
0x18005b208  jmp     short loc_18005B239
0x18005b20a  mov     rcx, [rbp+0D8h]; this
0x18005b211  mov     r9d, 80070002h; char *
0x18005b217  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005b21e  mov     edx, 34C3h; void *
0x18005b223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b228  nop
0x18005b229  lea     rcx, [rsp+1D0h+pvarg]; pvarg
0x18005b22e  call    cs:__imp_VariantClear
0x18005b234  mov     eax, 80070002h
0x18005b239  mov     rcx, [rbp+0D0h+var_40]
0x18005b240  xor     rcx, rsp; StackCookie
0x18005b243  call    __security_check_cookie
0x18005b248  mov     rbx, [rsp+1D0h+arg_10]
0x18005b250  add     rsp, 1A0h
0x18005b257  pop     r15
0x18005b259  pop     r14
0x18005b25b  pop     r13
0x18005b25d  pop     r12
0x18005b25f  pop     rdi
0x18005b260  pop     rsi
0x18005b261  pop     rbp
0x18005b262  retn
```
