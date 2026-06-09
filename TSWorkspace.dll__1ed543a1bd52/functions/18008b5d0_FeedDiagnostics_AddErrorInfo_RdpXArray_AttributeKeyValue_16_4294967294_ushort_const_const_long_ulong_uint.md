# FeedDiagnostics::AddErrorInfo(RdpXArray<AttributeKeyValue,16,4294967294> &,ushort const * const,long,ulong,uint)

- ea: `0x18008b5d0`
- end: `0x18008bbf1`
- name: `?AddErrorInfo@FeedDiagnostics@@AEAAJAEAV?$RdpXArray@UAttributeKeyValue@@$0BA@$0PPPPPPPO@@@QEBGJKI@Z`
- size: `1569`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18008c5e8`

## callees

- `0x1800044bf`
- `0x1800058d4`
- `0x18000ece0`
- `0x180010ba4`
- `0x18001a008`
- `0x18001b7e4`
- `0x180027914`
- `0x180032c88`
- `0x18008b050`
- `0x18008b0bc`
- `0x18008b110`
- `0x18008b5d0`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18008bbbd`
- `OLEAUT32!__imp_SysFreeString` at `0x18008bbbd`

## string_xrefs

- `0x18008b6e6`: `TS_WORKSPACE_E_INVALID_FEED_XML`
- `0x18008b6d4`: `TS_CONSENT_UPDATE_E_INVALID_XML`
- `0x18008b6dd`: `TS_DISCOVERY_E_INVALID_XML`
- `0x18008b744`: `StringCchPrintf szErrorCodeSymbolic failed!`
- `0x18008b9c0`: `ErrorCodeSymbolic`
- `0x18008ba47`: `Error during %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FeedDiagnostics::AddErrorInfo(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, int a6)
{
  int v10; // ebx
  const wchar_t *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  int ActivityIdPrefix; // eax
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // eax
  const wchar_t *v23; // rdx
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int128 v42; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v44[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v45[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v46[264]; // [rsp+470h] [rbp+370h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v10 = -2147467259;
  v42 = 0;
  memset_0(v44, 0, 0x20Au);
  memset_0(v46, 0, 0x20Au);
  memset_0(v45, 0, 0x20Au);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"GetTenantResource");
  if ( a4 >= 0 )
    goto LABEL_75;
  switch ( a4 )
  {
    case -2147220988:
      v11 = L"TS_WORKSPACE_E_INVALID_FEED_XML";
      break;
    case -2147220987:
      v11 = L"TS_DISCOVERY_E_INVALID_XML";
      break;
    case -2147220986:
      v11 = L"TS_CONSENT_UPDATE_E_INVALID_XML";
      break;
    case -2147220968:
      v11 = L"TS_WORKSPACE_E_NO_SUPPORTED_AUTH_SCHEME";
      break;
    case -2147220735:
      v11 = L"RADC_E_INVALID_URL_SCHEME";
      break;
    case -2147220734:
      v11 = L"RADC_E_URL_NOT_FOUND";
      break;
    default:
      v11 = L"Unknown Error";
      if ( a4 == -2147220733 )
        v11 = L"RADC_E_UNEXPECTED_SERVER_STATUS";
      break;
  }
  v10 = StringCchPrintfW(v45, 0x105u, L"%s:", v11);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12, v13);
      v15 = 39;
      v16 = "StringCchPrintf szErrorCodeSymbolic failed!";
LABEL_74:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)WPP_5283cbce258e3e6bfb9492d791118421_Traceguids,
        ActivityIdPrefix,
        (__int64)v16,
        v10,
        v42);
      goto LABEL_75;
    }
    goto LABEL_75;
  }
  v10 = StringCchPrintfW(v44, 0x105u, L"0x%x", (unsigned int)a4);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v17, v18);
      v15 = 41;
      v16 = "StringCchPrintf szErrorCodeText failed!";
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  ATL::CComBSTR::operator=(&v42, L"ErrorSource");
  ATL::CComBSTR::operator=((char *)&v42 + 8, L"Client");
  v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
  v10 = MapXResultToHR(v19);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v20, v21);
      v15 = 42;
      v16 = "Adding ErrorSource failed";
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  if ( !*(_QWORD *)(a1 + 48) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v20, v21);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)WPP_5283cbce258e3e6bfb9492d791118421_Traceguids,
        v22,
        (__int64)"m_spRDmiDiagnosticsCore");
    }
    v10 = -2147467261;
    goto LABEL_75;
  }
  if ( a6 == 104 )
  {
    v23 = L"GetTenantList";
  }
  else
  {
    if ( a6 != 105 )
      goto LABEL_43;
    v23 = L"GetTenantResource";
  }
  ATL::CComBSTR::operator=(bstrString, v23);
LABEL_43:
  ATL::CComBSTR::operator=(&v42, L"ErrorOperation");
  ATL::CComBSTR::operator=((char *)&v42 + 8, bstrString);
  v24 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
  v10 = MapXResultToHR(v24);
  if ( v10 >= 0 )
  {
    ATL::CComBSTR::operator=(&v42, L"ErrorCode");
    ATL::CComBSTR::operator=((char *)&v42 + 8, v44);
    v27 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
    v10 = MapXResultToHR(v27);
    if ( v10 >= 0 )
    {
      ATL::CComBSTR::operator=(&v42, L"ErrorCodeSymbolic");
      ATL::CComBSTR::operator=((char *)&v42 + 8, v45);
      v30 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
      v10 = MapXResultToHR(v30);
      if ( v10 >= 0 )
      {
        v10 = StringCchPrintfW(v46, 0x105u, L"Error during %s", a3);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v33, v34);
            v15 = 47;
            v16 = "StringCchPrintf szErrorMsg failed!";
            goto LABEL_74;
          }
          goto LABEL_75;
        }
        ATL::CComBSTR::operator=(&v42, "ErrorMessage");
        ATL::CComBSTR::operator=((char *)&v42 + 8, v46);
        v35 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
        v10 = MapXResultToHR(v35);
        if ( v10 >= 0 )
        {
          ATL::CComBSTR::operator=(&v42, "ErrorInternal");
          ATL::CComBSTR::operator=((char *)&v42 + 8, L"True");
          v38 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 32LL))(a2, &v42);
          v10 = MapXResultToHR(v38);
          if ( v10 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v39, v40);
            v15 = 49;
            v16 = "Adding ErrorInternal failed";
            goto LABEL_74;
          }
          goto LABEL_75;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v36, v37);
        v15 = 48;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v31, v32);
        v15 = 46;
      }
      v16 = "Adding ErrorMessage failed";
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v28, v29);
      v15 = 45;
      v16 = "Adding ErrorCode failed";
      goto LABEL_74;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v25, v26);
    v15 = 44;
    v16 = "Adding ErrorOperation failed";
    goto LABEL_74;
  }
LABEL_75:
  SysFreeString(bstrString[0]);
  AttributeKeyValue::~AttributeKeyValue((AttributeKeyValue *)&v42);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008b5d0  push    rbp
0x18008b5d2  push    rbx
0x18008b5d3  push    rsi
0x18008b5d4  push    rdi
0x18008b5d5  push    r12
0x18008b5d7  push    r14
0x18008b5d9  push    r15
0x18008b5db  lea     rbp, [rsp-590h]
0x18008b5e3  sub     rsp, 690h
0x18008b5ea  mov     [rsp+6C0h+var_678], 0FFFFFFFFFFFFFFFEh
0x18008b5f3  mov     rax, cs:__security_cookie
0x18008b5fa  xor     rax, rsp
0x18008b5fd  mov     [rbp+5C0h+var_40], rax
0x18008b604  mov     edi, r9d
0x18008b607  mov     r15, r8
0x18008b60a  mov     rsi, rdx
0x18008b60d  mov     r14, rcx
0x18008b610  mov     ebx, 80004005h
0x18008b615  xorps   xmm0, xmm0
0x18008b618  movdqu  [rsp+6C0h+var_690], xmm0
0x18008b61e  mov     r12d, 20Ah
0x18008b624  mov     r8d, r12d; Size
0x18008b627  xor     edx, edx; Val
0x18008b629  lea     rcx, [rsp+6C0h+var_670]; void *
0x18008b62e  call    memset_0
0x18008b633  mov     r8d, r12d; Size
0x18008b636  xor     edx, edx; Val
0x18008b638  lea     rcx, [rbp+5C0h+var_250]; void *
0x18008b63f  call    memset_0
0x18008b644  mov     r8d, r12d; Size
0x18008b647  xor     edx, edx; Val
0x18008b649  lea     rcx, [rbp+5C0h+var_460]; void *
0x18008b650  call    memset_0
0x18008b655  lea     rdx, aGettenantresou; "GetTenantResource"
0x18008b65c  lea     rcx, [rsp+6C0h+bstrString]; this
0x18008b661  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18008b666  nop
0x18008b667  test    edi, edi
0x18008b669  jns     loc_18008BBB8
0x18008b66f  cmp     edi, 80040204h
0x18008b675  jz      short loc_18008B6E6
0x18008b677  cmp     edi, 80040205h
0x18008b67d  jz      short loc_18008B6DD
0x18008b67f  cmp     edi, 80040206h
0x18008b685  jz      short loc_18008B6D4
0x18008b687  cmp     edi, 80040218h
0x18008b68d  jz      short loc_18008B6CB
0x18008b68f  cmp     edi, 80040301h
0x18008b695  jz      short loc_18008B6C2
0x18008b697  cmp     edi, 80040302h
0x18008b69d  jz      short loc_18008B6B9
0x18008b69f  lea     r9, aUnknownError_0; "Unknown Error"
0x18008b6a6  lea     rax, aRadcEUnexpecte; "RADC_E_UNEXPECTED_SERVER_STATUS"
0x18008b6ad  cmp     edi, 80040303h
0x18008b6b3  cmovz   r9, rax
0x18008b6b7  jmp     short loc_18008B6ED
0x18008b6b9  lea     r9, aRadcEUrlNotFou; "RADC_E_URL_NOT_FOUND"
0x18008b6c0  jmp     short loc_18008B6ED
0x18008b6c2  lea     r9, aRadcEInvalidUr; "RADC_E_INVALID_URL_SCHEME"
0x18008b6c9  jmp     short loc_18008B6ED
0x18008b6cb  lea     r9, aTsWorkspaceENo; "TS_WORKSPACE_E_NO_SUPPORTED_AUTH_SCHEME"
0x18008b6d2  jmp     short loc_18008B6ED
0x18008b6d4  lea     r9, aTsConsentUpdat; "TS_CONSENT_UPDATE_E_INVALID_XML"
0x18008b6db  jmp     short loc_18008B6ED
0x18008b6dd  lea     r9, aTsDiscoveryEIn; "TS_DISCOVERY_E_INVALID_XML"
0x18008b6e4  jmp     short loc_18008B6ED
0x18008b6e6  lea     r9, aTsWorkspaceEIn; "TS_WORKSPACE_E_INVALID_FEED_XML"
0x18008b6ed  lea     r8, aS_0; "%s:"
0x18008b6f4  mov     r12d, 105h
0x18008b6fa  mov     edx, r12d; unsigned __int64
0x18008b6fd  lea     rcx, [rbp+5C0h+var_460]; unsigned __int16 *
0x18008b704  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b709  mov     ebx, eax
0x18008b70b  test    eax, eax
0x18008b70d  jns     short loc_18008B750
0x18008b70f  lea     rcx, WPP_GLOBAL_Control
0x18008b716  mov     rax, cs:WPP_GLOBAL_Control
0x18008b71d  cmp     rax, rcx
0x18008b720  jz      loc_18008BBB8
0x18008b726  test    byte ptr [rax+1Ch], 8
0x18008b72a  jz      loc_18008BBB8
0x18008b730  cmp     byte ptr [rax+19h], 2
0x18008b734  jb      loc_18008BBB8
0x18008b73a  call    RdpX_GetActivityIdPrefix
0x18008b73f  mov     edx, 27h ; '''
0x18008b744  lea     rcx, aStringcchprint_13; "StringCchPrintf szErrorCodeSymbolic fai"...
0x18008b74b  jmp     loc_18008BB94
0x18008b750  mov     r9d, edi
0x18008b753  lea     r8, a0xX; "0x%x"
0x18008b75a  mov     rdx, r12; unsigned __int64
0x18008b75d  lea     rcx, [rsp+6C0h+var_670]; unsigned __int16 *
0x18008b762  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008b767  mov     ebx, eax
0x18008b769  test    eax, eax
0x18008b76b  jns     short loc_18008B7AE
0x18008b76d  lea     rcx, WPP_GLOBAL_Control
0x18008b774  mov     rax, cs:WPP_GLOBAL_Control
0x18008b77b  cmp     rax, rcx
0x18008b77e  jz      loc_18008BBB8
0x18008b784  test    byte ptr [rax+1Ch], 8
0x18008b788  jz      loc_18008BBB8
0x18008b78e  cmp     byte ptr [rax+19h], 2
0x18008b792  jb      loc_18008BBB8
0x18008b798  call    RdpX_GetActivityIdPrefix
0x18008b79d  mov     edx, 29h ; ')'
0x18008b7a2  lea     rcx, aStringcchprint_1; "StringCchPrintf szErrorCodeText failed!"
0x18008b7a9  jmp     loc_18008BB94
0x18008b7ae  lea     rdx, aErrorsource; "ErrorSource"
0x18008b7b5  lea     rcx, [rsp+6C0h+var_690]
0x18008b7ba  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b7bf  lea     rdx, aClient; "Client"
0x18008b7c6  lea     rcx, [rsp+6C0h+var_690+8]
0x18008b7cb  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b7d0  mov     rax, [rsi]
0x18008b7d3  lea     rdx, [rsp+6C0h+var_690]
0x18008b7d8  mov     rcx, rsi
0x18008b7db  mov     rax, [rax+20h]
0x18008b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b7e4  mov     ecx, eax
0x18008b7e6  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008b7eb  mov     ebx, eax
0x18008b7ed  test    eax, eax
0x18008b7ef  jns     short loc_18008B832
0x18008b7f1  lea     rcx, WPP_GLOBAL_Control
0x18008b7f8  mov     rax, cs:WPP_GLOBAL_Control
0x18008b7ff  cmp     rax, rcx
0x18008b802  jz      loc_18008BBB8
0x18008b808  test    byte ptr [rax+1Ch], 8
0x18008b80c  jz      loc_18008BBB8
0x18008b812  cmp     byte ptr [rax+19h], 2
0x18008b816  jb      loc_18008BBB8
0x18008b81c  call    RdpX_GetActivityIdPrefix
0x18008b821  mov     edx, 2Ah ; '*'
0x18008b826  lea     rcx, aAddingErrorsou; "Adding ErrorSource failed"
0x18008b82d  jmp     loc_18008BB94
0x18008b832  cmp     qword ptr [r14+30h], 0
0x18008b837  jnz     short loc_18008B892
0x18008b839  lea     rcx, WPP_GLOBAL_Control
0x18008b840  mov     rax, cs:WPP_GLOBAL_Control
0x18008b847  cmp     rax, rcx
0x18008b84a  jz      short loc_18008B888
0x18008b84c  test    byte ptr [rax+1Ch], 8
0x18008b850  jz      short loc_18008B888
0x18008b852  cmp     byte ptr [rax+19h], 2
0x18008b856  jb      short loc_18008B888
0x18008b858  call    RdpX_GetActivityIdPrefix
0x18008b85d  mov     edx, 2Bh ; '+'
0x18008b862  lea     rcx, aMSprdmidiagnos; "m_spRDmiDiagnosticsCore"
0x18008b869  mov     [rsp+6C0h+var_6A0], rcx
0x18008b86e  mov     r9d, eax
0x18008b871  lea     r8, WPP_5283cbce258e3e6bfb9492d791118421_Traceguids
0x18008b878  mov     rcx, cs:WPP_GLOBAL_Control
0x18008b87f  mov     rcx, [rcx+10h]
0x18008b883  call    WPP_SF_Ds
0x18008b888  mov     ebx, 80004003h
0x18008b88d  jmp     loc_18008BBB8
0x18008b892  mov     eax, [rbp+5C0h+arg_28]
0x18008b898  sub     eax, 68h ; 'h'
0x18008b89b  jz      short loc_18008B8AB
0x18008b89d  cmp     eax, 1
0x18008b8a0  jnz     short loc_18008B8BC
0x18008b8a2  lea     rdx, aGettenantresou; "GetTenantResource"
0x18008b8a9  jmp     short loc_18008B8B2
0x18008b8ab  lea     rdx, aGettenantlist; "GetTenantList"
0x18008b8b2  lea     rcx, [rsp+6C0h+bstrString]
0x18008b8b7  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b8bc  lea     rdx, aErroroperation; "ErrorOperation"
0x18008b8c3  lea     rcx, [rsp+6C0h+var_690]
0x18008b8c8  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b8cd  lea     rdx, [rsp+6C0h+bstrString]
0x18008b8d2  lea     rcx, [rsp+6C0h+var_690+8]
0x18008b8d7  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18008b8dc  mov     rax, [rsi]
0x18008b8df  lea     rdx, [rsp+6C0h+var_690]
0x18008b8e4  mov     rcx, rsi
0x18008b8e7  mov     rax, [rax+20h]
0x18008b8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b8f0  mov     ecx, eax
0x18008b8f2  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008b8f7  mov     ebx, eax
0x18008b8f9  test    eax, eax
0x18008b8fb  jns     short loc_18008B93E
0x18008b8fd  lea     rcx, WPP_GLOBAL_Control
0x18008b904  mov     rax, cs:WPP_GLOBAL_Control
0x18008b90b  cmp     rax, rcx
0x18008b90e  jz      loc_18008BBB8
0x18008b914  test    byte ptr [rax+1Ch], 8
0x18008b918  jz      loc_18008BBB8
0x18008b91e  cmp     byte ptr [rax+19h], 2
0x18008b922  jb      loc_18008BBB8
0x18008b928  call    RdpX_GetActivityIdPrefix
0x18008b92d  mov     edx, 2Ch ; ','
0x18008b932  lea     rcx, aAddingErrorope; "Adding ErrorOperation failed"
0x18008b939  jmp     loc_18008BB94
0x18008b93e  lea     rdx, aErrorcode; "ErrorCode"
0x18008b945  lea     rcx, [rsp+6C0h+var_690]
0x18008b94a  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b94f  lea     rdx, [rsp+6C0h+var_670]
0x18008b954  lea     rcx, [rsp+6C0h+var_690+8]
0x18008b959  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b95e  mov     rax, [rsi]
0x18008b961  lea     rdx, [rsp+6C0h+var_690]
0x18008b966  mov     rcx, rsi
0x18008b969  mov     rax, [rax+20h]
0x18008b96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b972  mov     ecx, eax
0x18008b974  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008b979  mov     ebx, eax
0x18008b97b  test    eax, eax
0x18008b97d  jns     short loc_18008B9C0
0x18008b97f  lea     rcx, WPP_GLOBAL_Control
0x18008b986  mov     rax, cs:WPP_GLOBAL_Control
0x18008b98d  cmp     rax, rcx
0x18008b990  jz      loc_18008BBB8
0x18008b996  test    byte ptr [rax+1Ch], 8
0x18008b99a  jz      loc_18008BBB8
0x18008b9a0  cmp     byte ptr [rax+19h], 2
0x18008b9a4  jb      loc_18008BBB8
0x18008b9aa  call    RdpX_GetActivityIdPrefix
0x18008b9af  mov     edx, 2Dh ; '-'
0x18008b9b4  lea     rcx, aAddingErrorcod; "Adding ErrorCode failed"
0x18008b9bb  jmp     loc_18008BB94
0x18008b9c0  lea     rdx, aErrorcodesymbo; "ErrorCodeSymbolic"
0x18008b9c7  lea     rcx, [rsp+6C0h+var_690]
0x18008b9cc  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b9d1  lea     rdx, [rbp+5C0h+var_460]
0x18008b9d8  lea     rcx, [rsp+6C0h+var_690+8]
0x18008b9dd  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008b9e2  mov     rax, [rsi]
0x18008b9e5  lea     rdx, [rsp+6C0h+var_690]
0x18008b9ea  mov     rcx, rsi
0x18008b9ed  mov     rax, [rax+20h]
0x18008b9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b9f6  mov     ecx, eax
0x18008b9f8  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008b9fd  mov     ebx, eax
0x18008b9ff  test    eax, eax
0x18008ba01  jns     short loc_18008BA44
0x18008ba03  lea     rcx, WPP_GLOBAL_Control
0x18008ba0a  mov     rax, cs:WPP_GLOBAL_Control
0x18008ba11  cmp     rax, rcx
0x18008ba14  jz      loc_18008BBB8
0x18008ba1a  test    byte ptr [rax+1Ch], 8
0x18008ba1e  jz      loc_18008BBB8
0x18008ba24  cmp     byte ptr [rax+19h], 2
0x18008ba28  jb      loc_18008BBB8
0x18008ba2e  call    RdpX_GetActivityIdPrefix
0x18008ba33  mov     edx, 2Eh ; '.'
0x18008ba38  lea     rcx, aAddingErrormes; "Adding ErrorMessage failed"
0x18008ba3f  jmp     loc_18008BB94
0x18008ba44  mov     r9, r15
0x18008ba47  lea     r8, aErrorDuringS; "Error during %s"
0x18008ba4e  mov     rdx, r12; unsigned __int64
0x18008ba51  lea     rcx, [rbp+5C0h+var_250]; unsigned __int16 *
0x18008ba58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008ba5d  mov     ebx, eax
0x18008ba5f  test    eax, eax
0x18008ba61  jns     short loc_18008BAA4
0x18008ba63  lea     rcx, WPP_GLOBAL_Control
0x18008ba6a  mov     rax, cs:WPP_GLOBAL_Control
0x18008ba71  cmp     rax, rcx
0x18008ba74  jz      loc_18008BBB8
0x18008ba7a  test    byte ptr [rax+1Ch], 8
0x18008ba7e  jz      loc_18008BBB8
0x18008ba84  cmp     byte ptr [rax+19h], 2
0x18008ba88  jb      loc_18008BBB8
0x18008ba8e  call    RdpX_GetActivityIdPrefix
0x18008ba93  mov     edx, 2Fh ; '/'
0x18008ba98  lea     rcx, aStringcchprint_9; "StringCchPrintf szErrorMsg failed!"
0x18008ba9f  jmp     loc_18008BB94
0x18008baa4  lea     rdx, aErrormessage; "ErrorMessage"
0x18008baab  lea     rcx, [rsp+6C0h+var_690]
0x18008bab0  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBD@Z; ATL::CComBSTR::operator=(char const *)
0x18008bab5  lea     rdx, [rbp+5C0h+var_250]
0x18008babc  lea     rcx, [rsp+6C0h+var_690+8]
0x18008bac1  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008bac6  mov     rax, [rsi]
0x18008bac9  lea     rdx, [rsp+6C0h+var_690]
0x18008bace  mov     rcx, rsi
0x18008bad1  mov     rax, [rax+20h]
0x18008bad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bada  mov     ecx, eax
0x18008badc  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x18008bae1  mov     ebx, eax
0x18008bae3  test    eax, eax
0x18008bae5  jns     short loc_18008BB21
0x18008bae7  lea     rcx, WPP_GLOBAL_Control
0x18008baee  mov     rax, cs:WPP_GLOBAL_Control
0x18008baf5  cmp     rax, rcx
0x18008baf8  jz      loc_18008BBB8
0x18008bafe  test    byte ptr [rax+1Ch], 8
0x18008bb02  jz      loc_18008BBB8
0x18008bb08  cmp     byte ptr [rax+19h], 2
0x18008bb0c  jb      loc_18008BBB8
0x18008bb12  call    RdpX_GetActivityIdPrefix
0x18008bb17  mov     edx, 30h ; '0'
0x18008bb1c  jmp     loc_18008BA38
0x18008bb21  lea     rdx, aErrorinternal; "ErrorInternal"
0x18008bb28  lea     rcx, [rsp+6C0h+var_690]
0x18008bb2d  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBD@Z; ATL::CComBSTR::operator=(char const *)
  ... truncated ...
```
