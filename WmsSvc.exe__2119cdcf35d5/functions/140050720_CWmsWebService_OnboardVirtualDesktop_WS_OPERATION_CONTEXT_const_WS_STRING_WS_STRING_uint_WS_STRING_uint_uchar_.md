# CWmsWebService::OnboardVirtualDesktop(_WS_OPERATION_CONTEXT const *,_WS_STRING,_WS_STRING,uint *,_WS_STRING *,uint *,uchar * *,_WS_STRING *,_WS_STRING *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x140050720`
- end: `0x140050e9f`
- name: `?OnboardVirtualDesktop@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@U_WS_STRING@@1PEAIPEAU3@2PEAPEAE33PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `1919`
- prototype: `__int64 __usercall@<rax>(const struct _WS_OPERATION_CONTEXT *@<rcx>, struct _WS_STRING *__struct_ptr@<rdx>, struct _WS_STRING *__struct_ptr@<r8>, unsigned int *@<r9>, struct _WS_STRING *, unsigned int *, unsigned __int8 **ptr, struct _WS_STRING *, struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400016b8`
- `0x14004c43c`
- `0x14004d3dc`
- `0x140050720`
- `0x140059ec0`
- `0x14005b418`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064148`
- `0x140064dc0`
- `0x140065070`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140050891`
- `KERNEL32!IsDebuggerPresent` at `0x1400509a3`
- `KERNEL32!IsDebuggerPresent` at `0x140050a55`
- `KERNEL32!IsDebuggerPresent` at `0x140050aff`
- `KERNEL32!IsDebuggerPresent` at `0x140050c46`
- `KERNEL32!IsDebuggerPresent` at `0x140050d18`
- `KERNEL32!IsDebuggerPresent` at `0x140050891`
- `KERNEL32!IsDebuggerPresent` at `0x1400509a3`
- `KERNEL32!IsDebuggerPresent` at `0x140050a55`
- `KERNEL32!IsDebuggerPresent` at `0x140050aff`
- `KERNEL32!IsDebuggerPresent` at `0x140050c46`
- `KERNEL32!IsDebuggerPresent` at `0x140050d18`
- `msvcrt!memcpy_s` at `0x140050d45`
- `msvcrt!memcpy_s` at `0x140050d45`
- `CRYPT32!CertFreeCertificateContext` at `0x140050e54`
- `CRYPT32!CertFreeCertificateContext` at `0x140050e54`
- `ole32!CoCreateInstance` at `0x140050849`
- `ole32!CoCreateInstance` at `0x140050849`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d94`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x140050da7`
- `OLEAUT32!__imp_SysFreeString` at `0x140050dd7`
- `OLEAUT32!__imp_SysFreeString` at `0x140050e0f`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d94`
- `OLEAUT32!__imp_SysFreeString` at `0x140050d9e`
- `OLEAUT32!__imp_SysFreeString` at `0x140050da7`
- `OLEAUT32!__imp_SysFreeString` at `0x140050dd7`
- `OLEAUT32!__imp_SysFreeString` at `0x140050e0f`
- `OLEAUT32!__imp_SysStringLen` at `0x140050db6`
- `OLEAUT32!__imp_SysStringLen` at `0x140050dee`
- `OLEAUT32!__imp_SysStringLen` at `0x140050db6`
- `OLEAUT32!__imp_SysStringLen` at `0x140050dee`
- `OLEAUT32!__imp_VariantInit` at `0x1400507b0`
- `OLEAUT32!__imp_VariantInit` at `0x1400507ba`
- `OLEAUT32!__imp_VariantInit` at `0x1400507c4`
- `OLEAUT32!__imp_VariantInit` at `0x1400507b0`
- `OLEAUT32!__imp_VariantInit` at `0x1400507ba`
- `OLEAUT32!__imp_VariantInit` at `0x1400507c4`
- `OLEAUT32!__imp_VariantClear` at `0x140050d6d`
- `OLEAUT32!__imp_VariantClear` at `0x140050d77`
- `OLEAUT32!__imp_VariantClear` at `0x140050d81`
- `OLEAUT32!__imp_VariantClear` at `0x140050d6d`
- `OLEAUT32!__imp_VariantClear` at `0x140050d77`
- `OLEAUT32!__imp_VariantClear` at `0x140050d81`
- `PROPSYS!VariantToUInt32` at `0x140050abb`
- `PROPSYS!VariantToUInt32` at `0x140050abb`
- `webservices!WsAlloc` at `0x140050cd4`
- `webservices!WsAlloc` at `0x140050cd4`
- `webservices!WsGetOperationContextProperty` at `0x140050c02`
- `webservices!WsGetOperationContextProperty` at `0x140050c02`

## string_xrefs

- `0x14005086e`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050989`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050a3b`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050adc`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050c23`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050cf5`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x140050864`: `CWmsWebService::OnboardVirtualDesktop`
- `0x14005097d`: `CWmsWebService::OnboardVirtualDesktop`
- `0x140050a2f`: `CWmsWebService::OnboardVirtualDesktop`
- `0x140050ad2`: `CWmsWebService::OnboardVirtualDesktop`
- `0x140050c19`: `CWmsWebService::OnboardVirtualDesktop`
- `0x140050ceb`: `CWmsWebService::OnboardVirtualDesktop`
- `0x14005081d`: `CWmsWebService::OnboardVirtualDesktop - bstrVirtualMachineId=%s, bstrRemoteFqdn=%s.\n`
- `0x140050e5d`: `CWmsWebService::OnboardVirtualDesktop - bstrVirtualMachineId=%s, bstrRemoteFqdn=%s returning hr=0x%08X\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::OnboardVirtualDesktop(
        const struct _WS_OPERATION_CONTEXT *a1,
        struct _WS_STRING *a2,
        struct _WS_STRING *a3,
        unsigned int *a4,
        struct _WS_STRING *a5,
        unsigned int *a6,
        unsigned __int8 **ptr,
        struct _WS_STRING *a8,
        struct _WS_STRING *a9,
        const struct _WS_ASYNC_CONTEXT *a10,
        struct _WS_ERROR *error)
{
  unsigned __int16 *v12; // r12
  const CERT_CONTEXT *v13; // r14
  unsigned __int16 *v14; // r13
  struct _WS_ERROR *v17; // r15
  int v18; // ebx
  int v19; // eax
  HRESULT v20; // eax
  __int64 v21; // r9
  __int64 v22; // r8
  bool v23; // zf
  const unsigned __int16 *v24; // rax
  __int64 v25; // r9
  __int64 v26; // r8
  HRESULT v27; // eax
  int CertificateContext; // eax
  HRESULT OperationContextProperty; // eax
  HRESULT v30; // eax
  OLECHAR *v31; // rcx
  __int64 v32; // rax
  OLECHAR *v33; // rcx
  __int64 v34; // rax
  __int64 v36; // [rsp+38h] [rbp-D0h]
  __int64 v37; // [rsp+40h] [rbp-C8h]
  PCCERT_CONTEXT v38; // [rsp+88h] [rbp-80h] BYREF
  SIZE_T size; // [rsp+90h] [rbp-78h] BYREF
  BSTR pbstr; // [rsp+98h] [rbp-70h] BYREF
  BSTR v41; // [rsp+A0h] [rbp-68h] BYREF
  ULONG pulRet; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v43; // [rsp+ACh] [rbp-5Ch] BYREF
  WS_HEAP *value; // [rsp+B0h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-48h] BYREF
  void *Source; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v48; // [rsp+D0h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+D8h] [rbp-30h] BYREF
  BSTR v50; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG v51; // [rsp+E8h] [rbp-20h] BYREF
  void *Block[2]; // [rsp+100h] [rbp-8h] BYREF
  VARIANTARG varIn; // [rsp+110h] [rbp+8h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+20h] BYREF

  ppv = 0;
  v46 = 0;
  bstrString = 0;
  v12 = 0;
  pulRet = 0;
  *(_OWORD *)Block = 0;
  v13 = 0;
  v38 = 0;
  LODWORD(size) = 0;
  v14 = 0;
  Source = 0;
  v43 = 0;
  v50 = 0;
  pbstr = 0;
  v41 = 0;
  v48 = 0;
  value = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&varIn, 0, sizeof(varIn));
  memset(&v51, 0, sizeof(v51));
  VariantInit(&pvarg);
  VariantInit(&varIn);
  VariantInit(&v51);
  v17 = error;
  v18 = CWmsWebService::s_VerifyAdminAccess(a1, error);
  if ( v18 >= 0 )
  {
    v18 = WsStringToBstr(a2, &v46);
    if ( v18 < 0 )
    {
      v12 = v46;
    }
    else
    {
      v19 = WsStringToBstr(a3, &v48);
      v14 = v48;
      v18 = v19;
      v12 = v46;
      if ( v19 < 0 )
        goto LABEL_46;
      DEBUGMSG(L"CWmsWebService::OnboardVirtualDesktop - bstrVirtualMachineId=%s, bstrRemoteFqdn=%s.\n", v46, v48);
      v20 = CoCreateInstance(&CLSID_WmsHypervWmi, 0, 4u, &GUID_75306260_6ac0_4987_8219_e87918401638, &ppv);
      v18 = v20;
      if ( v20 < 0 )
      {
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
          0x16Cu,
          L"CWmsWebService::OnboardVirtualDesktop",
          L"CHRA",
          L"hr",
          v20);
        if ( IsDebuggerPresent() )
        {
          v21 = 364;
LABEL_7:
          LODWORD(v37) = v18;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
            v21,
            L"CWmsWebService::OnboardVirtualDesktop",
            L"CHRA",
            L"hr",
            v37);
LABEL_10:
          v13 = v38;
          v17 = error;
          goto LABEL_46;
        }
        v22 = 364;
        goto LABEL_9;
      }
      v18 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, BSTR *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              v12,
              &bstrString);
      if ( v18 >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(struct ISessionService *, __int64, unsigned __int16 *))(*(_QWORD *)CWmsWebService::s_pISessionService
                                                                                               + 216LL))(
                CWmsWebService::s_pISessionService,
                1,
                v14);
        if ( v18 >= 0 )
        {
          if ( v51.vt != 8 )
          {
            v18 = -2147418113;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
              0x178u,
              L"CWmsWebService::OnboardVirtualDesktop",
              L"CBRAEx",
              L"varRemoteSslThumbprint.vt == VT_BSTR",
              -2147418113);
            v23 = !IsDebuggerPresent();
            v24 = L"varRemoteSslThumbprint.vt == VT_BSTR";
            if ( !v23 )
            {
              v25 = 376;
LABEL_16:
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                v25,
                L"CWmsWebService::OnboardVirtualDesktop",
                L"CBRAEx",
                v24,
                v18);
LABEL_19:
              v13 = v38;
              goto LABEL_46;
            }
            v26 = 376;
            goto LABEL_18;
          }
          if ( !v51.llVal )
          {
            v18 = -2147467261;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
              0x179u,
              L"CWmsWebService::OnboardVirtualDesktop",
              L"CBRAEx",
              L"varRemoteSslThumbprint.bstrVal != 0",
              -2147467261);
            v23 = !IsDebuggerPresent();
            v24 = L"varRemoteSslThumbprint.bstrVal != 0";
            if ( !v23 )
            {
              v25 = 377;
              goto LABEL_16;
            }
            v26 = 377;
LABEL_18:
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
              v26,
              L"CWmsWebService::OnboardVirtualDesktop",
              L"CBRAEx",
              v24,
              v18);
            goto LABEL_19;
          }
          v18 = (*(__int64 (__fastcall **)(struct ISessionService *, __int64, unsigned __int16 *, __int64, VARIANTARG *))(*(_QWORD *)CWmsWebService::s_pISessionService + 216LL))(
                  CWmsWebService::s_pISessionService,
                  1,
                  v14,
                  6,
                  &varIn);
          if ( v18 >= 0 )
          {
            v27 = VariantToUInt32(&varIn, &pulRet);
            v18 = v27;
            if ( v27 < 0 )
            {
              LOGASSERTHR(
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                0x17Fu,
                L"CWmsWebService::OnboardVirtualDesktop",
                L"CHRA",
                L"hr",
                v27);
              if ( IsDebuggerPresent() )
              {
                v21 = 383;
                goto LABEL_7;
              }
              v22 = 383;
LABEL_9:
              LODWORD(v36) = v18;
              DEBUGMSGBOX(
                L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
                L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                v22,
                L"CWmsWebService::OnboardVirtualDesktop",
                L"CHRA",
                L"hr",
                v36);
              goto LABEL_10;
            }
            v18 = ConvertThumbprintStringToBlob(v51.bstrVal, (struct _CRYPTOAPI_BLOB *)Block);
            if ( v18 >= 0 )
            {
              CertificateContext = GetCertificateContext(Block, 0, &v38);
              v13 = v38;
              v18 = CertificateContext;
              if ( CertificateContext >= 0 )
              {
                v18 = (*(__int64 (__fastcall **)(LPVOID, __int64, unsigned __int16 *, unsigned __int16 *, ULONG, LONGLONG, DWORD, BYTE *, unsigned int *, BSTR *, SIZE_T *, void **, BSTR *, BSTR *))(*(_QWORD *)ppv + 160LL))(
                        ppv,
                        2,
                        v12,
                        v14,
                        pulRet,
                        v51.llVal,
                        v38->cbCertEncoded,
                        v38->pbCertEncoded,
                        &v43,
                        &v50,
                        &size,
                        &Source,
                        &pbstr,
                        &v41);
                if ( v18 >= 0 )
                {
                  v18 = VerifySslCertificate(bstrString, (const unsigned __int8 *)Source, size);
                  if ( v18 >= 0 )
                  {
                    OperationContextProperty = WsGetOperationContextProperty(
                                                 a1,
                                                 WS_OPERATION_CONTEXT_PROPERTY_HEAP,
                                                 &value,
                                                 8u,
                                                 error);
                    v18 = OperationContextProperty;
                    if ( OperationContextProperty < 0 )
                    {
                      LOGASSERTHR(
                        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                        0x1A5u,
                        L"CWmsWebService::OnboardVirtualDesktop",
                        L"CHRA",
                        L"hr",
                        OperationContextProperty);
                      if ( IsDebuggerPresent() )
                      {
                        v21 = 421;
                        goto LABEL_7;
                      }
                      v22 = 421;
                      goto LABEL_9;
                    }
                    v18 = StringToWsString(value, pbstr, a8);
                    if ( v18 >= 0 )
                    {
                      v18 = StringToWsString(value, v41, a9);
                      if ( v18 >= 0 )
                      {
                        v18 = StringToWsString(value, v50, a5);
                        if ( v18 >= 0 )
                        {
                          v30 = WsAlloc(value, (unsigned int)size, (void **)ptr, error);
                          v18 = v30;
                          if ( v30 < 0 )
                          {
                            LOGASSERTHR(
                              L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.imultipointserver.cpp",
                              0x1B1u,
                              L"CWmsWebService::OnboardVirtualDesktop",
                              L"CHRA",
                              L"hr",
                              v30);
                            if ( IsDebuggerPresent() )
                            {
                              v21 = 433;
                              goto LABEL_7;
                            }
                            v22 = 433;
                            goto LABEL_9;
                          }
                          memcpy_s(*ptr, (unsigned int)size, Source, (unsigned int)size);
                          *a4 = v43;
                          *a6 = size;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_46:
  VariantClear(&pvarg);
  VariantClear(&varIn);
  VariantClear(&v51);
  SysFreeString(v12);
  SysFreeString(bstrString);
  SysFreeString(v50);
  SysFreeString(v14);
  if ( pbstr )
  {
    LODWORD(v32) = SysStringLen(pbstr);
    v31 = pbstr;
    v32 = (unsigned int)v32;
    if ( (_DWORD)v32 )
    {
      do
      {
        *(_BYTE *)v31 = 0;
        v31 = (OLECHAR *)((char *)v31 + 1);
        --v32;
      }
      while ( v32 );
      v31 = pbstr;
    }
    SysFreeString(v31);
    pbstr = 0;
  }
  if ( v41 )
  {
    LODWORD(v34) = SysStringLen(v41);
    v33 = v41;
    v34 = (unsigned int)v34;
    if ( (_DWORD)v34 )
    {
      do
      {
        *(_BYTE *)v33 = 0;
        v33 = (OLECHAR *)((char *)v33 + 1);
        --v34;
      }
      while ( v34 );
      v33 = v41;
    }
    SysFreeString(v33);
    v41 = 0;
  }
  operator delete(Block[1]);
  operator delete(Source);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v13 )
    CertFreeCertificateContext(v13);
  DEBUGMSG(
    L"CWmsWebService::OnboardVirtualDesktop - bstrVirtualMachineId=%s, bstrRemoteFqdn=%s returning hr=0x%08X\n",
    v12,
    v14,
    (unsigned int)v18);
  if ( v18 < 0 && v17 )
    CWmsWebService::s_CreateWmsFault(v18, v17);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140050720  mov     rax, rsp
0x140050723  mov     [rax+10h], rbx
0x140050727  mov     [rax+20h], r9
0x14005072b  mov     [rax+8], rcx
0x14005072f  push    rbp
0x140050730  push    rsi
0x140050731  push    rdi
0x140050732  push    r12
0x140050734  push    r13
0x140050736  push    r14
0x140050738  push    r15
0x14005073a  lea     rbp, [rax-78h]
0x14005073e  sub     rsp, 140h
0x140050745  xor     eax, eax
0x140050747  xorps   xmm0, xmm0
0x14005074a  mov     rbx, rcx
0x14005074d  mov     [rbp+70h+var_C0], rax
0x140050751  xorps   xmm1, xmm1
0x140050754  mov     [rbp+70h+var_B8], rax
0x140050758  lea     rcx, [rbp+70h+pvarg]; pvarg
0x14005075c  mov     [rbp+70h+bstrString], rax
0x140050760  mov     r12d, eax
0x140050763  mov     [rbp+70h+pulRet], eax
0x140050766  movups  xmmword ptr [rbp+70h+Block], xmm0
0x14005076a  mov     r14d, eax
0x14005076d  mov     [rbp+70h+var_F0], rax
0x140050771  mov     dword ptr [rbp+70h+size], eax
0x140050774  mov     r13d, eax
0x140050777  mov     [rbp+70h+Source], rax
0x14005077b  mov     rdi, r8
0x14005077e  mov     [rbp+70h+var_CC], eax
0x140050781  mov     rsi, rdx
0x140050784  mov     [rbp+70h+var_98], rax
0x140050788  mov     [rbp+70h+pbstr], rax
0x14005078c  mov     [rbp+70h+var_D8], rax
0x140050790  mov     [rbp+70h+var_A8], rax
0x140050794  mov     [rbp+70h+value], rax
0x140050798  movups  xmmword ptr [rbp+70h+pvarg], xmm0
0x14005079c  mov     qword ptr [rbp+70h+pvarg+10h], rax
0x1400507a0  movups  xmmword ptr [rbp+70h+varIn], xmm1
0x1400507a4  mov     qword ptr [rbp+70h+varIn+10h], rax
0x1400507a8  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x1400507ac  mov     qword ptr [rbp+70h+var_90+10h], rax
0x1400507b0  call    cs:__imp_VariantInit
0x1400507b6  lea     rcx, [rbp+70h+varIn]; pvarg
0x1400507ba  call    cs:__imp_VariantInit
0x1400507c0  lea     rcx, [rbp+70h+var_90]; pvarg
0x1400507c4  call    cs:__imp_VariantInit
0x1400507ca  mov     r15, [rbp+70h+error]
0x1400507d1  mov     rcx, rbx; struct _WS_OPERATION_CONTEXT *
0x1400507d4  mov     rdx, r15; struct _WS_ERROR *
0x1400507d7  call    ?s_VerifyAdminAccess@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAU_WS_ERROR@@@Z; CWmsWebService::s_VerifyAdminAccess(_WS_OPERATION_CONTEXT const *,_WS_ERROR *)
0x1400507dc  mov     ebx, eax
0x1400507de  test    eax, eax
0x1400507e0  js      loc_140050D69
0x1400507e6  lea     rdx, [rbp+70h+var_B8]; unsigned __int16 **
0x1400507ea  mov     rcx, rsi; struct _WS_STRING *
0x1400507ed  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x1400507f2  mov     ebx, eax
0x1400507f4  test    eax, eax
0x1400507f6  js      loc_140050D65
0x1400507fc  lea     rdx, [rbp+70h+var_A8]; unsigned __int16 **
0x140050800  mov     rcx, rdi; struct _WS_STRING *
0x140050803  call    ?WsStringToBstr@@YAJPEBU_WS_STRING@@PEAPEAG@Z; WsStringToBstr(_WS_STRING const *,ushort * *)
0x140050808  mov     r13, [rbp+70h+var_A8]
0x14005080c  mov     ebx, eax
0x14005080e  mov     r12, [rbp+70h+var_B8]
0x140050812  test    eax, eax
0x140050814  js      loc_140050D69
0x14005081a  mov     r8, r13
0x14005081d  lea     rcx, aCwmswebservice_124; "CWmsWebService::OnboardVirtualDesktop -"...
0x140050824  mov     rdx, r12
0x140050827  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14005082c  lea     rax, [rbp+70h+var_C0]
0x140050830  xor     edx, edx; pUnkOuter
0x140050832  lea     r9, _GUID_75306260_6ac0_4987_8219_e87918401638; riid
0x140050839  mov     [rsp+170h+ppv], rax; ppv
0x14005083e  lea     r8d, [r14+4]; dwClsContext
0x140050842  lea     rcx, CLSID_WmsHypervWmi; rclsid
0x140050849  call    cs:__imp_CoCreateInstance
0x14005084f  mov     ebx, eax
0x140050851  test    eax, eax
0x140050853  jns     loc_140050900
0x140050859  mov     [rsp+170h+var_148], eax; int
0x14005085d  lea     r15, aChra; "CHRA"
0x140050864  lea     rsi, aCwmswebservice_73; "CWmsWebService::OnboardVirtualDesktop"
0x14005086b  mov     r9, r15; unsigned __int16 *
0x14005086e  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140050875  mov     r8, rsi; unsigned __int16 *
0x140050878  lea     r14, aHr; "hr"
0x14005087f  mov     rcx, rdi; unsigned __int16 *
0x140050882  mov     edx, 16Ch; unsigned int
0x140050887  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x14005088c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140050891  call    cs:__imp_IsDebuggerPresent
0x140050897  test    eax, eax
0x140050899  jz      short loc_1400508CA
0x14005089b  mov     r9d, 16Ch
0x1400508a1  mov     dword ptr [rsp+170h+var_138], ebx
0x1400508a5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400508ac  mov     [rsp+170h+var_140], r14
0x1400508b1  mov     r8, rdi
0x1400508b4  mov     qword ptr [rsp+170h+var_148], r15
0x1400508b9  mov     ecx, 2; unsigned __int8
0x1400508be  mov     [rsp+170h+ppv], rsi
0x1400508c3  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400508c8  jmp     short loc_1400508F0
0x1400508ca  mov     r8d, 16Ch
0x1400508d0  mov     dword ptr [rsp+170h+var_140], ebx
0x1400508d4  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400508db  mov     qword ptr [rsp+170h+var_148], r14
0x1400508e0  mov     r9, rsi
0x1400508e3  mov     rdx, rdi
0x1400508e6  mov     [rsp+170h+ppv], r15
0x1400508eb  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400508f0  mov     r14, [rbp+70h+var_F0]
0x1400508f4  mov     r15, [rbp+70h+error]
0x1400508fb  jmp     loc_140050D69
0x140050900  mov     rcx, [rbp+70h+var_C0]
0x140050904  lea     r8, [rbp+70h+bstrString]
0x140050908  mov     rdx, r12
0x14005090b  mov     rax, [rcx]
0x14005090e  mov     rax, [rax+30h]
0x140050912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050917  mov     ebx, eax
0x140050919  test    eax, eax
0x14005091b  js      loc_140050D69
0x140050921  mov     rcx, cs:?s_pISessionService@CWmsWebService@@0PEAUISessionService@@EA; ISessionService * CWmsWebService::s_pISessionService
0x140050928  lea     rdx, [rbp+70h+var_90]
0x14005092c  mov     r9d, 5
0x140050932  mov     [rsp+170h+ppv], rdx
0x140050937  mov     r8, r13
0x14005093a  mov     rax, [rcx]
0x14005093d  lea     edx, [r9-4]
0x140050941  mov     rax, [rax+0D8h]
0x140050948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005094d  mov     ebx, eax
0x14005094f  test    eax, eax
0x140050951  js      loc_140050D69
0x140050957  mov     edi, 8
0x14005095c  cmp     word ptr [rbp+70h+var_90], di
0x140050960  jz      loc_140050A12
0x140050966  lea     rax, aVarremotesslth_0; "varRemoteSslThumbprint.vt == VT_BSTR"
0x14005096d  mov     ebx, 8000FFFFh
0x140050972  lea     r14, aCbraex; "CBRAEx"
0x140050979  mov     [rsp+170h+var_148], ebx; int
0x14005097d  lea     rsi, aCwmswebservice_73; "CWmsWebService::OnboardVirtualDesktop"
0x140050984  mov     [rsp+170h+ppv], rax; unsigned __int16 *
0x140050989  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140050990  mov     r9, r14; unsigned __int16 *
0x140050993  mov     r8, rsi; unsigned __int16 *
0x140050996  mov     rcx, rdi; unsigned __int16 *
0x140050999  mov     edx, 178h; unsigned int
0x14005099e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400509a3  call    cs:__imp_IsDebuggerPresent
0x1400509a9  test    eax, eax
0x1400509ab  lea     rax, aVarremotesslth_0; "varRemoteSslThumbprint.vt == VT_BSTR"
0x1400509b2  jz      short loc_1400509E3
0x1400509b4  mov     r9d, 178h
0x1400509ba  mov     dword ptr [rsp+170h+var_138], ebx
0x1400509be  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400509c5  mov     [rsp+170h+var_140], rax
0x1400509ca  mov     r8, rdi
0x1400509cd  mov     qword ptr [rsp+170h+var_148], r14
0x1400509d2  mov     ecx, 2; unsigned __int8
0x1400509d7  mov     [rsp+170h+ppv], rsi
0x1400509dc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400509e1  jmp     short loc_140050A09
0x1400509e3  mov     r8d, 178h
0x1400509e9  mov     dword ptr [rsp+170h+var_140], ebx
0x1400509ed  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400509f4  mov     qword ptr [rsp+170h+var_148], rax
0x1400509f9  mov     r9, rsi
0x1400509fc  mov     rdx, rdi
0x1400509ff  mov     [rsp+170h+ppv], r14
0x140050a04  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140050a09  mov     r14, [rbp+70h+var_F0]
0x140050a0d  jmp     loc_140050D69
0x140050a12  cmp     qword ptr [rbp+70h+var_90+8], r14
0x140050a16  jnz     short loc_140050A7C
0x140050a18  lea     rax, aVarremotesslth; "varRemoteSslThumbprint.bstrVal != 0"
0x140050a1f  mov     ebx, 80004003h
0x140050a24  lea     r14, aCbraex; "CBRAEx"
0x140050a2b  mov     [rsp+170h+var_148], ebx; int
0x140050a2f  lea     rsi, aCwmswebservice_73; "CWmsWebService::OnboardVirtualDesktop"
0x140050a36  mov     [rsp+170h+ppv], rax; unsigned __int16 *
0x140050a3b  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140050a42  mov     r9, r14; unsigned __int16 *
0x140050a45  mov     r8, rsi; unsigned __int16 *
0x140050a48  mov     rcx, rdi; unsigned __int16 *
0x140050a4b  mov     edx, 179h; unsigned int
0x140050a50  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140050a55  call    cs:__imp_IsDebuggerPresent
0x140050a5b  test    eax, eax
0x140050a5d  lea     rax, aVarremotesslth; "varRemoteSslThumbprint.bstrVal != 0"
0x140050a64  jz      short loc_140050A71
0x140050a66  mov     r9d, 179h
0x140050a6c  jmp     loc_1400509BA
0x140050a71  mov     r8d, 179h
0x140050a77  jmp     loc_1400509E9
0x140050a7c  mov     rcx, cs:?s_pISessionService@CWmsWebService@@0PEAUISessionService@@EA; ISessionService * CWmsWebService::s_pISessionService
0x140050a83  lea     rdx, [rbp+70h+varIn]
0x140050a87  mov     esi, 6
0x140050a8c  mov     [rsp+170h+ppv], rdx
0x140050a91  mov     r9d, esi
0x140050a94  mov     r8, r13
0x140050a97  mov     rax, [rcx]
0x140050a9a  lea     edx, [rsi-5]
0x140050a9d  mov     rax, [rax+0D8h]
0x140050aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050aa9  mov     ebx, eax
0x140050aab  test    eax, eax
0x140050aad  js      loc_140050D69
0x140050ab3  lea     rdx, [rbp+70h+pulRet]; pulRet
0x140050ab7  lea     rcx, [rbp+70h+varIn]; varIn
0x140050abb  call    cs:__imp_VariantToUInt32
0x140050ac1  mov     ebx, eax
0x140050ac3  test    eax, eax
0x140050ac5  jns     short loc_140050B1F
0x140050ac7  mov     [rsp+170h+var_148], eax; int
0x140050acb  lea     r15, aChra; "CHRA"
0x140050ad2  lea     rsi, aCwmswebservice_73; "CWmsWebService::OnboardVirtualDesktop"
0x140050ad9  mov     r9, r15; unsigned __int16 *
0x140050adc  lea     rdi, aTermsrvWmsSrcD_5; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x140050ae3  mov     r8, rsi; unsigned __int16 *
0x140050ae6  lea     r14, aHr; "hr"
0x140050aed  mov     rcx, rdi; unsigned __int16 *
0x140050af0  mov     edx, 17Fh; unsigned int
0x140050af5  mov     [rsp+170h+ppv], r14; unsigned __int16 *
0x140050afa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140050aff  call    cs:__imp_IsDebuggerPresent
0x140050b05  test    eax, eax
0x140050b07  jz      short loc_140050B14
0x140050b09  mov     r9d, 17Fh
0x140050b0f  jmp     loc_1400508A1
0x140050b14  mov     r8d, 17Fh
0x140050b1a  jmp     loc_1400508D0
0x140050b1f  mov     rcx, qword ptr [rbp+70h+var_90+8]; unsigned __int16 *
0x140050b23  lea     rdx, [rbp+70h+Block]; struct _CRYPTOAPI_BLOB *
0x140050b27  call    ?ConvertThumbprintStringToBlob@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; ConvertThumbprintStringToBlob(ushort const *,_CRYPTOAPI_BLOB *)
0x140050b2c  mov     ebx, eax
0x140050b2e  test    eax, eax
0x140050b30  js      loc_140050D69
0x140050b36  lea     r8, [rbp+70h+var_F0]
0x140050b3a  xor     edx, edx
0x140050b3c  lea     rcx, [rbp+70h+Block]
0x140050b40  call    ?GetCertificateContext@@YAJPEAU_CRYPTOAPI_BLOB@@W4EBehaviorOnCertMissing@@PEAPEBU_CERT_CONTEXT@@@Z; GetCertificateContext(_CRYPTOAPI_BLOB *,EBehaviorOnCertMissing,_CERT_CONTEXT const * *)
0x140050b45  mov     r14, [rbp+70h+var_F0]
0x140050b49  mov     ebx, eax
0x140050b4b  test    eax, eax
0x140050b4d  js      loc_140050D69
0x140050b53  mov     rcx, [rbp+70h+var_C0]
0x140050b57  lea     rdx, [rbp+70h+var_D8]
0x140050b5b  mov     [rsp+68h], rdx
0x140050b60  mov     r9, r13
0x140050b63  lea     rdx, [rbp+70h+pbstr]
0x140050b67  mov     r8, r12
0x140050b6a  mov     [rsp+170h+var_110], rdx
0x140050b6f  lea     rdx, [rbp+70h+Source]
0x140050b73  mov     rax, [rcx]
0x140050b76  mov     [rsp+170h+var_118], rdx
0x140050b7b  lea     rdx, [rbp+70h+size]
0x140050b7f  mov     [rsp+170h+var_120], rdx
0x140050b84  lea     rdx, [rbp+70h+var_98]
0x140050b88  mov     [rsp+170h+var_128], rdx
0x140050b8d  lea     rdx, [rbp+70h+var_CC]
0x140050b91  mov     rax, [rax+0A0h]
0x140050b98  mov     [rsp+170h+var_130], rdx
0x140050b9d  mov     rdx, [r14+8]
0x140050ba1  mov     [rsp+170h+var_138], rdx
0x140050ba6  mov     edx, [r14+10h]
0x140050baa  mov     dword ptr [rsp+170h+var_140], edx
0x140050bae  mov     rdx, qword ptr [rbp+70h+var_90+8]
0x140050bb2  mov     qword ptr [rsp+170h+var_148], rdx
0x140050bb7  mov     edx, [rbp+70h+pulRet]
0x140050bba  mov     dword ptr [rsp+170h+ppv], edx
0x140050bbe  mov     edx, 2
0x140050bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050bc8  mov     ebx, eax
0x140050bca  test    eax, eax
0x140050bcc  js      loc_140050D69
0x140050bd2  mov     r8d, dword ptr [rbp+70h+size]; unsigned int
0x140050bd6  mov     rdx, [rbp+70h+Source]; unsigned __int8 *
0x140050bda  mov     rcx, [rbp+70h+bstrString]; String1
0x140050bde  call    ?VerifySslCertificate@@YAJPEAGPEBEK@Z; VerifySslCertificate(ushort *,uchar const *,ulong)
0x140050be3  mov     ebx, eax
0x140050be5  test    eax, eax
0x140050be7  js      loc_140050D69
0x140050bed  mov     rcx, [rbp+70h+context]; context
0x140050bf4  lea     r8, [rbp+70h+value]; value
0x140050bf8  mov     r9d, edi; valueSize
0x140050bfb  mov     [rsp+170h+ppv], r15; error
0x140050c00  mov     edx, esi; id
0x140050c02  call    cs:__imp_WsGetOperationContextProperty
0x140050c08  mov     ebx, eax
0x140050c0a  test    eax, eax
0x140050c0c  jns     short loc_140050C66
0x140050c0e  mov     [rsp+170h+var_148], eax; int
0x140050c12  lea     r15, aChra; "CHRA"
0x140050c19  lea     rsi, aCwmswebservice_73; "CWmsWebService::OnboardVirtualDesktop"
  ... truncated ...
```
