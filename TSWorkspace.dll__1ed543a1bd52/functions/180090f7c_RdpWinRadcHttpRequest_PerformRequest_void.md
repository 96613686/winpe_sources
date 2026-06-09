# RdpWinRadcHttpRequest::PerformRequest(void)

- ea: `0x180090f7c`
- end: `0x180091ac5`
- name: `?PerformRequest@RdpWinRadcHttpRequest@@AEAAJXZ`
- size: `2889`
- prototype: `__int64 __fastcall(RdpWinRadcHttpRequest *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008f830`

## callees

- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x180017fcc`
- `0x18001a008`
- `0x1800487e0`
- `0x180062a08`
- `0x18008fee0`
- `0x1800900a0`
- `0x180090f7c`
- `0x180092380`
- `0x180092eb4`
- `0x18009342c`
- `0x18009361c`
- `0x180093cc4`
- `0x180093e50`
- `0x1800a3010`

## import_xrefs

- `msvcrt!wcscspn` at `0x18009181f`
- `msvcrt!wcscspn` at `0x18009181f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800910ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800910fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18009151e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009158b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800916b3`
- `OLEAUT32!__imp_SysFreeString` at `0x180091a97`
- `OLEAUT32!__imp_SysFreeString` at `0x180091aa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180091aaa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800910ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800910fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18009151e`
- `OLEAUT32!__imp_SysFreeString` at `0x18009158b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800916b3`
- `OLEAUT32!__imp_SysFreeString` at `0x180091a97`
- `OLEAUT32!__imp_SysFreeString` at `0x180091aa1`
- `OLEAUT32!__imp_SysFreeString` at `0x180091aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800911ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800912a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800911ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800912a7`
- `KERNEL32!CompareStringEx` at `0x180091869`
- `KERNEL32!CompareStringEx` at `0x1800918a9`
- `KERNEL32!CompareStringEx` at `0x180091869`
- `KERNEL32!CompareStringEx` at `0x1800918a9`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800911e2`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800911e2`
- `WINHTTP!WinHttpSendRequest` at `0x1800910dc`
- `WINHTTP!WinHttpSendRequest` at `0x1800910dc`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009129d`
- `WINHTTP!WinHttpQueryHeaders` at `0x18009129d`

## string_xrefs

- `0x18009162b`: `SetClaimsTokenIfExists failed`
- `0x18009102c`: `Content-Type: application/xml\n`
- `0x18009101a`: `Content-Type: application/json; charset=utf-16\n`
- `0x180091023`: `Content-Type: application/json\n`
- `0x180091943`: `ReadResponseBody failed`

## pseudocode

```c
__int64 __fastcall RdpWinRadcHttpRequest::PerformRequest(RdpWinRadcHttpRequest *this)
{
  int v1; // r12d
  int v3; // ecx
  wchar_t *v4; // rdi
  unsigned __int16 *v5; // rsi
  int v6; // ecx
  int v7; // ecx
  unsigned int v8; // r14d
  int ActivityIdPrefix; // eax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  DWORD v12; // ebx
  const WCHAR **v13; // rax
  OLECHAR *v14; // rbx
  const WCHAR *v15; // rdx
  int LastError; // ebx
  PVOID *v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rdx
  bool v20; // sf
  __int64 v21; // rbx
  unsigned int v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // eax
  int v25; // eax
  bool ShouldEndEarly; // al
  int v27; // ebx
  __int64 v28; // r14
  unsigned int v29; // eax
  __int64 v30; // r8
  int v31; // ebx
  __int64 v32; // r14
  unsigned int v33; // eax
  __int64 v34; // r8
  PVOID *v35; // rax
  __int64 v36; // rbx
  unsigned int v37; // eax
  unsigned int v38; // eax
  OLECHAR *v39; // rcx
  int v40; // eax
  int v41; // edx
  const char *v42; // rcx
  __int64 v43; // rbx
  unsigned int v44; // eax
  __int64 v45; // r8
  __int64 v46; // rbx
  unsigned int v47; // eax
  __int64 v48; // rbx
  unsigned int v49; // eax
  __int64 v50; // rbx
  unsigned int v51; // eax
  unsigned int v52; // eax
  size_t v53; // rax
  int v54; // ebx
  __int64 v55; // rbx
  int v56; // r8d
  int v57; // r9d
  const wchar_t *v58; // rax
  int v59; // eax
  __int64 v60; // rbx
  unsigned int v61; // eax
  __int64 v62; // r8
  int v63; // eax
  int v64; // eax
  DWORD dwTotalLength[2]; // [rsp+28h] [rbp-58h]
  DWORD dwTotalLengtha[2]; // [rsp+28h] [rbp-58h]
  DWORD dwBufferLength; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-28h] BYREF
  BSTR v70; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v71; // [rsp+68h] [rbp-18h] BYREF
  LPVOID lpOptional; // [rsp+70h] [rbp-10h]
  BSTR v73; // [rsp+78h] [rbp-8h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+40h] BYREF
  DWORD dwOptionalLength; // [rsp+C8h] [rbp+48h]
  BSTR v76; // [rsp+D0h] [rbp+50h] BYREF
  DWORD v77; // [rsp+D8h] [rbp+58h]

  v1 = 0;
  dwBufferLength = 4;
  LODWORD(bstrString) = 0;
  v3 = *((_DWORD *)this + 55);
  v4 = 0;
  String = 0;
  v5 = 0;
  v70 = 0;
  v71 = 0;
  if ( v3 )
  {
    v6 = v3 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 != 1 )
        {
          v8 = -2147418113;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              ActivityIdPrefix,
              (__int64)"Unknown request body content type",
              -2147418113);
          }
          goto LABEL_161;
        }
        v10 = L"Content-Type: application/json; charset=utf-16\r\n";
      }
      else
      {
        v10 = L"Content-Type: application/json\r\n";
      }
    }
    else
    {
      v10 = L"Content-Type: application/xml\r\n";
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v70, v10);
  }
  if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    v8 = 1;
    goto LABEL_161;
  }
  v11 = *((_QWORD *)this + 26);
  v12 = *((_DWORD *)this + 54);
  v77 = v12;
  if ( v11 )
  {
    lpOptional = (LPVOID)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
    dwOptionalLength = v12;
  }
  else
  {
    lpOptional = 0;
    dwOptionalLength = 0;
  }
  v8 = 1;
  if ( *((_QWORD *)this + 26) )
  {
    v13 = (const WCHAR **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v73, (const struct ATL::CComBSTR *)&v70);
    v14 = bstrString;
    v1 = 1;
    LODWORD(v76) = 0;
    v15 = *v13;
  }
  else
  {
    v14 = 0;
    LODWORD(v76) = 2;
    v15 = 0;
  }
  dwOptionalLength = WinHttpSendRequest(
                       *((HINTERNET *)this + 5),
                       v15,
                       0,
                       lpOptional,
                       dwOptionalLength,
                       v77,
                       (DWORD_PTR)this);
  if ( (_DWORD)v76 )
    SysFreeString(v14);
  if ( v1 )
    SysFreeString(v73);
  if ( !dwOptionalLength )
  {
    LastError = GetLastError();
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = RdpX_GetActivityIdPrefix();
      v19 = 97;
LABEL_30:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
        v18,
        LastError);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = *((_QWORD *)this + 2);
    v22 = RdpX_GetActivityIdPrefix();
    WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v22, v21);
  }
  if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
  {
    if ( !WinHttpReceiveResponse(*((HINTERNET *)this + 5), 0) )
    {
      LastError = GetLastError();
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v18 = RdpX_GetActivityIdPrefix();
        v19 = 99;
        goto LABEL_30;
      }
LABEL_31:
      v20 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v20 = LastError < 0;
      }
      if ( !v20 )
      {
        v8 = -2147467259;
        goto LABEL_161;
      }
      goto LABEL_144;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v23 = *((_QWORD *)this + 2);
      v24 = RdpX_GetActivityIdPrefix();
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v24, v23);
    }
    if ( !RdpWinRadcHttpRequest::ShouldEndEarly(this) )
    {
      if ( !WinHttpQueryHeaders(*((HINTERNET *)this + 5), 0x20000013u, 0, &bstrString, &dwBufferLength, 0) )
      {
        LastError = GetLastError();
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpX_GetActivityIdPrefix();
          v19 = 101;
          goto LABEL_30;
        }
        goto LABEL_31;
      }
      LastError = RdpWinRadcHttpRequest::GetHttpHeaderFromResponse(this, 1u, &String);
      if ( LastError < 0 )
      {
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v25 = RdpX_GetActivityIdPrefix();
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v25,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v4 = String;
LABEL_143:
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_144;
        }
        v4 = String;
LABEL_144:
        v8 = LastError;
        if ( LastError == -2147012881 || LastError == -2147012864 )
        {
          if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x10000) != 0 && *((_BYTE *)v17 + 25) >= 4u )
          {
            v60 = *((_QWORD *)this + 2);
            v61 = RdpX_GetActivityIdPrefix();
            WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, v62, v61, v60, v8);
          }
          v8 = -2147220731;
        }
        goto LABEL_161;
      }
      ShouldEndEarly = RdpWinRadcHttpRequest::ShouldEndEarly(this);
      v4 = String;
      if ( ShouldEndEarly )
        goto LABEL_161;
      dwOptionalLength = (unsigned int)bstrString;
      if ( (_DWORD)bstrString != 200 )
      {
        if ( (_DWORD)bstrString == 304 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            *((_QWORD *)this + 2),
            304,
            0);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v50 = *((_QWORD *)this + 2);
            v51 = RdpX_GetActivityIdPrefix();
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              117,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v51,
              v50);
          }
        }
        else
        {
          if ( (_DWORD)bstrString != 401 )
          {
            if ( (_DWORD)bstrString == 404 || (_DWORD)bstrString == 502 || (_DWORD)bstrString == 504 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *))(**((_QWORD **)this + 25) + 32LL))(
                *((_QWORD *)this + 25),
                *((_QWORD *)this + 2),
                (unsigned int)bstrString,
                String);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v31 = (int)bstrString;
                v32 = *((_QWORD *)this + 2);
                v33 = RdpX_GetActivityIdPrefix();
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, v34, v33, v32, v31);
              }
              v8 = -2147220734;
            }
            else
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *))(**((_QWORD **)this + 25) + 32LL))(
                *((_QWORD *)this + 25),
                *((_QWORD *)this + 2),
                (unsigned int)bstrString,
                String);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                v27 = (int)bstrString;
                v28 = *((_QWORD *)this + 2);
                v29 = RdpX_GetActivityIdPrefix();
                WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, v30, v29, v28, v27);
              }
              v8 = -2147220733;
            }
            goto LABEL_161;
          }
          v76 = 0;
          v35 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v36 = *((_QWORD *)this + 2);
            v37 = RdpX_GetActivityIdPrefix();
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v37,
              v36);
            v35 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( !*((_BYTE *)this + 184) )
          {
            if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 8) != 0 && *((_BYTE *)v35 + 25) >= 2u )
            {
              v38 = RdpX_GetActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                110,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v38,
                -2147467263);
            }
            v39 = 0;
            v8 = -2147467263;
            goto LABEL_88;
          }
          LastError = RdpWinRadcHttpRequest::TryFindClaimsAuthChallenge(this, &v76);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_95;
            }
            v40 = RdpX_GetActivityIdPrefix();
            v41 = 111;
            v42 = "TryFindClaimsAuthChallenge failed";
LABEL_94:
            dwTotalLength[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v41,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v40,
              (__int64)v42,
              *(_QWORD *)dwTotalLength);
LABEL_95:
            SysFreeString(v76);
            goto LABEL_143;
          }
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v43 = *((_QWORD *)this + 2);
              v44 = RdpX_GetActivityIdPrefix();
              WPP_SF_DID(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v45, v44, v43, -2147220968);
            }
            v8 = -2147220968;
            goto LABEL_102;
          }
          LastError = RdpWinRadcHttpRequest::SetClaimsTokenIfExists(this);
          if ( LastError < 0 )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_95;
            }
            v40 = RdpX_GetActivityIdPrefix();
            v41 = 113;
            v42 = "SetClaimsTokenIfExists failed";
            goto LABEL_94;
          }
          if ( RdpWinRadcHttpRequest::ShouldEndEarly(this) )
          {
LABEL_102:
            v39 = v76;
LABEL_88:
            SysFreeString(v39);
            goto LABEL_161;
          }
          if ( LastError != 1 )
          {
            v8 = -2147220731;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v48 = *((_QWORD *)this + 2);
              v49 = RdpX_GetActivityIdPrefix();
              WPP_SF_Dq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                115,
                &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
                v49,
                v48);
            }
            goto LABEL_102;
          }
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BSTR))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            *((_QWORD *)this + 2),
            dwOptionalLength,
            v76);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v46 = *((_QWORD *)this + 2);
            v47 = RdpX_GetActivityIdPrefix();
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              114,
              &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v47,
              v46);
          }
          SysFreeString(v76);
        }
LABEL_115:
        v8 = 0;
        goto LABEL_161;
      }
      LastError = RdpWinRadcHttpRequest::GetETagFromHttpResponse(this, &v71);
      if ( LastError == -2147012746 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v52 = RdpX_GetActivityIdPrefix();
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids, v52);
        }
      }
      else if ( LastError < 0 )
      {
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v63 = RdpX_GetActivityIdPrefix();
          dwTotalLength[0] = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            105,
            (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
            v63,
            (__int64)"GetHttpHeaderFromResponse(WINHTTP_QUERY_CONTENT_TYPE) failed",
            *(_QWORD *)dwTotalLength);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        v5 = v71;
        goto LABEL_144;
      }
      v5 = v71;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, wchar_t *, unsigned __int16 *))(**((_QWORD **)this + 25) + 24LL))(
        *((_QWORD *)this + 25),
        *((_QWORD *)this + 2),
        dwOptionalLength,
        v4,
        v71);
      v53 = wcscspn(v4, L";");
      v54 = v53;
      if ( v53 <= 0x7FFFFFFF )
      {
        if ( CompareStringEx(&LocaleName, 1u, v4, v53, L"application/x-msts-webfeed-login", -1, 0, 0, 0) != 2 )
          LOBYTE(v8) = CompareStringEx(
                         &LocaleName,
                         1u,
                         v4,
                         v54,
                         L"application/x-msts-webfeed-discovery-login",
                         -1,
                         0,
                         0,
                         0) == 2;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v55 = *((_QWORD *)this + 2);
          v57 = RdpX_GetActivityIdPrefix();
          v58 = L"is";
          if ( !(_BYTE)v8 )
            v58 = L"is not";
          WPP_SF_DIS(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v56, v57, v55, (__int64)v58);
        }
        LastError = RdpWinRadcHttpRequest::ReadResponseBody((HINTERNET *)this, v8);
        if ( LastError < 0 )
        {
          v17 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v59 = RdpX_GetActivityIdPrefix();
            dwTotalLengtha[0] = LastError;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              108,
              (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
              v59,
              (__int64)"ReadResponseBody failed",
              *(_QWORD *)dwTotalLengtha);
            goto LABEL_143;
          }
          goto LABEL_144;
        }
        goto LABEL_115;
      }
      v8 = -2147024362;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v64 = RdpX_GetActivityIdPrefix();
        dwTotalLength[0] = -2147024362;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          106,
          (unsigned int)&WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids,
          v64,
          (__int64)"SizeTToInt failed",
          *(_QWORD *)dwTotalLength);
      }
    }
  }
LABEL_161:
  SysFreeString(v5);
  SysFreeString(v70);
  SysFreeString(v4);
  return v8;
}

```

## disassembly

```asm
0x180090f7c  push    rbp
0x180090f7e  push    rbx
0x180090f7f  push    rsi
0x180090f80  push    rdi
0x180090f81  push    r12
0x180090f83  push    r14
0x180090f85  push    r15
0x180090f87  mov     rbp, rsp
0x180090f8a  sub     rsp, 80h
0x180090f91  xor     r12d, r12d
0x180090f94  mov     [rbp+dwBufferLength], 4
0x180090f9b  mov     r15, rcx
0x180090f9e  mov     dword ptr [rbp+bstrString], r12d
0x180090fa2  mov     ecx, [rcx+0DCh]
0x180090fa8  mov     edi, r12d
0x180090fab  mov     [rbp+String], r12
0x180090faf  mov     esi, r12d
0x180090fb2  mov     [rbp+var_20], r12
0x180090fb6  mov     [rbp+var_18], r12
0x180090fba  test    ecx, ecx
0x180090fbc  jz      short loc_18009103C
0x180090fbe  sub     ecx, 1
0x180090fc1  jz      short loc_18009102C
0x180090fc3  sub     ecx, 1
0x180090fc6  jz      short loc_180091023
0x180090fc8  cmp     ecx, 1
0x180090fcb  jz      short loc_18009101A
0x180090fcd  mov     r14d, 8000FFFFh
0x180090fd3  mov     rax, cs:WPP_GLOBAL_Control
0x180090fda  lea     r12, WPP_GLOBAL_Control
0x180090fe1  cmp     rax, r12
0x180090fe4  jz      loc_180091A94
0x180090fea  test    byte ptr [rax+1Ch], 8
0x180090fee  jz      loc_180091A94
0x180090ff4  cmp     byte ptr [rax+19h], 2
0x180090ff8  jb      loc_180091A94
0x180090ffe  call    RdpX_GetActivityIdPrefix
0x180091003  lea     edx, [rsi+60h]
0x180091006  mov     [rsp+80h+dwTotalLength], 8000FFFFh
0x18009100e  lea     rcx, aUnknownRequest; "Unknown request body content type"
0x180091015  jmp     loc_180091A75
0x18009101a  lea     rdx, aContentTypeApp; "Content-Type: application/json; charset"...
0x180091021  jmp     short loc_180091033
0x180091023  lea     rdx, aContentTypeApp_1; "Content-Type: application/json\r\n"
0x18009102a  jmp     short loc_180091033
0x18009102c  lea     rdx, aContentTypeApp_0; "Content-Type: application/xml\r\n"
0x180091033  lea     rcx, [rbp+var_20]; this
0x180091037  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009103c  mov     rcx, r15; this
0x18009103f  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x180091044  test    al, al
0x180091046  jz      short loc_180091053
0x180091048  mov     r14d, 1
0x18009104e  jmp     loc_180091A94
0x180091053  mov     rcx, [r15+0D0h]
0x18009105a  mov     ebx, [r15+0D8h]
0x180091061  mov     [rbp+arg_18], ebx
0x180091064  test    rcx, rcx
0x180091067  jz      short loc_18009107E
0x180091069  mov     rax, [rcx]
0x18009106c  mov     rax, [rax+20h]
0x180091070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091075  mov     [rbp+lpOptional], rax
0x180091079  mov     [rbp+arg_8], ebx
0x18009107c  jmp     short loc_180091086
0x18009107e  mov     [rbp+lpOptional], r12
0x180091082  mov     [rbp+arg_8], r12d
0x180091086  mov     r14d, 1
0x18009108c  cmp     [r15+0D0h], r12
0x180091093  jz      short loc_1800910B1
0x180091095  lea     rdx, [rbp+var_20]; struct ATL::CComBSTR *
0x180091099  lea     rcx, [rbp+var_8]; this
0x18009109d  call    ??0CComBSTR@ATL@@QEAA@AEBV01@@Z; ATL::CComBSTR::CComBSTR(ATL::CComBSTR const &)
0x1800910a2  mov     rbx, [rbp+bstrString]
0x1800910a6  mov     r12d, r14d
0x1800910a9  mov     dword ptr [rbp+arg_10], esi
0x1800910ac  mov     rdx, [rax]
0x1800910af  jmp     short loc_1800910BE
0x1800910b1  mov     rbx, r12
0x1800910b4  mov     dword ptr [rbp+arg_10], 2
0x1800910bb  mov     rdx, r12; lpszHeaders
0x1800910be  mov     eax, [rbp+arg_18]
0x1800910c1  xor     r8d, r8d; dwHeadersLength
0x1800910c4  mov     r9, [rbp+lpOptional]; lpOptional
0x1800910c8  mov     rcx, [r15+28h]; hRequest
0x1800910cc  mov     [rsp+80h+dwContext], r15; dwContext
0x1800910d1  mov     [rsp+80h+dwTotalLength], eax; dwTotalLength
0x1800910d5  mov     eax, [rbp+arg_8]
0x1800910d8  mov     [rsp+80h+dwOptionalLength], eax; dwOptionalLength
0x1800910dc  call    cs:__imp_WinHttpSendRequest
0x1800910e2  mov     [rbp+arg_8], eax
0x1800910e5  cmp     dword ptr [rbp+arg_10], esi
0x1800910e8  jz      short loc_1800910F3
0x1800910ea  mov     rcx, rbx; bstrString
0x1800910ed  call    cs:__imp_SysFreeString
0x1800910f3  test    r12d, r12d
0x1800910f6  jz      short loc_180091102
0x1800910f8  mov     rcx, [rbp+var_8]; bstrString
0x1800910fc  call    cs:__imp_SysFreeString
0x180091102  cmp     [rbp+arg_8], esi
0x180091105  jnz     short loc_18009117D
0x180091107  call    cs:__imp_GetLastError
0x18009110d  mov     ebx, eax
0x18009110f  mov     rax, cs:WPP_GLOBAL_Control
0x180091116  lea     r12, WPP_GLOBAL_Control
0x18009111d  cmp     rax, r12
0x180091120  jz      short loc_18009115D
0x180091122  test    byte ptr [rax+1Ch], 8
0x180091126  jz      short loc_18009115D
0x180091128  cmp     byte ptr [rax+19h], 2
0x18009112c  jb      short loc_18009115D
0x18009112e  call    RdpX_GetActivityIdPrefix
0x180091133  mov     edx, 61h ; 'a'
0x180091138  mov     rcx, cs:WPP_GLOBAL_Control
0x18009113f  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180091146  mov     r9d, eax
0x180091149  mov     [rsp+80h+dwOptionalLength], ebx
0x18009114d  mov     rcx, [rcx+10h]
0x180091151  call    WPP_SF_Dd
0x180091156  mov     rax, cs:WPP_GLOBAL_Control
0x18009115d  test    ebx, ebx
0x18009115f  jle     short loc_18009116C
0x180091161  movzx   ebx, bx
0x180091164  or      ebx, 80070000h
0x18009116a  test    ebx, ebx
0x18009116c  js      loc_180091979
0x180091172  mov     r14d, 80004005h
0x180091178  jmp     loc_180091A94
0x18009117d  mov     rax, cs:WPP_GLOBAL_Control
0x180091184  lea     r12, WPP_GLOBAL_Control
0x18009118b  cmp     rax, r12
0x18009118e  jz      short loc_1800911CC
0x180091190  test    dword ptr [rax+1Ch], 10000h
0x180091197  jz      short loc_1800911CC
0x180091199  cmp     byte ptr [rax+19h], 4
0x18009119d  jb      short loc_1800911CC
0x18009119f  mov     rbx, [r15+10h]
0x1800911a3  call    RdpX_GetActivityIdPrefix
0x1800911a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800911af  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x1800911b6  mov     edx, 62h ; 'b'
0x1800911bb  mov     qword ptr [rsp+80h+dwOptionalLength], rbx
0x1800911c0  mov     r9d, eax
0x1800911c3  mov     rcx, [rcx+10h]
0x1800911c7  call    WPP_SF_Dq
0x1800911cc  mov     rcx, r15; this
0x1800911cf  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x1800911d4  test    al, al
0x1800911d6  jnz     loc_180091A94
0x1800911dc  mov     rcx, [r15+28h]; hRequest
0x1800911e0  xor     edx, edx; lpReserved
0x1800911e2  call    cs:__imp_WinHttpReceiveResponse
0x1800911e8  test    eax, eax
0x1800911ea  jnz     short loc_180091227
0x1800911ec  call    cs:__imp_GetLastError
0x1800911f2  mov     ebx, eax
0x1800911f4  mov     rax, cs:WPP_GLOBAL_Control
0x1800911fb  cmp     rax, r12
0x1800911fe  jz      loc_18009115D
0x180091204  test    byte ptr [rax+1Ch], 8
0x180091208  jz      loc_18009115D
0x18009120e  cmp     byte ptr [rax+19h], 2
0x180091212  jb      loc_18009115D
0x180091218  call    RdpX_GetActivityIdPrefix
0x18009121d  mov     edx, 63h ; 'c'
0x180091222  jmp     loc_180091138
0x180091227  mov     rax, cs:WPP_GLOBAL_Control
0x18009122e  cmp     rax, r12
0x180091231  jz      short loc_18009126F
0x180091233  test    dword ptr [rax+1Ch], 10000h
0x18009123a  jz      short loc_18009126F
0x18009123c  cmp     byte ptr [rax+19h], 4
0x180091240  jb      short loc_18009126F
0x180091242  mov     rbx, [r15+10h]
0x180091246  call    RdpX_GetActivityIdPrefix
0x18009124b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091252  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x180091259  mov     edx, 64h ; 'd'
0x18009125e  mov     qword ptr [rsp+80h+dwOptionalLength], rbx
0x180091263  mov     r9d, eax
0x180091266  mov     rcx, [rcx+10h]
0x18009126a  call    WPP_SF_Dq
0x18009126f  mov     rcx, r15; this
0x180091272  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x180091277  test    al, al
0x180091279  jnz     loc_180091A94
0x18009127f  mov     rcx, [r15+28h]; hRequest
0x180091283  lea     rax, [rbp+dwBufferLength]
0x180091287  mov     qword ptr [rsp+80h+dwTotalLength], rsi; lpdwIndex
0x18009128c  lea     r9, [rbp+bstrString]; lpBuffer
0x180091290  xor     r8d, r8d; pwszName
0x180091293  mov     qword ptr [rsp+80h+dwOptionalLength], rax; lpdwBufferLength
0x180091298  mov     edx, 20000013h; dwInfoLevel
0x18009129d  call    cs:__imp_WinHttpQueryHeaders
0x1800912a3  test    eax, eax
0x1800912a5  jnz     short loc_1800912E2
0x1800912a7  call    cs:__imp_GetLastError
0x1800912ad  mov     ebx, eax
0x1800912af  mov     rax, cs:WPP_GLOBAL_Control
0x1800912b6  cmp     rax, r12
0x1800912b9  jz      loc_18009115D
0x1800912bf  test    byte ptr [rax+1Ch], 8
0x1800912c3  jz      loc_18009115D
0x1800912c9  cmp     byte ptr [rax+19h], 2
0x1800912cd  jb      loc_18009115D
0x1800912d3  call    RdpX_GetActivityIdPrefix
0x1800912d8  mov     edx, 65h ; 'e'
0x1800912dd  jmp     loc_180091138
0x1800912e2  lea     r8, [rbp+String]; unsigned __int16 **
0x1800912e6  mov     edx, r14d; unsigned int
0x1800912e9  mov     rcx, r15; this
0x1800912ec  call    ?GetHttpHeaderFromResponse@RdpWinRadcHttpRequest@@AEAAJKPEAPEAG@Z; RdpWinRadcHttpRequest::GetHttpHeaderFromResponse(ulong,ushort * *)
0x1800912f1  mov     ebx, eax
0x1800912f3  test    eax, eax
0x1800912f5  jns     short loc_180091355
0x1800912f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800912fe  cmp     rax, r12
0x180091301  jz      short loc_18009134C
0x180091303  test    byte ptr [rax+1Ch], 8
0x180091307  jz      short loc_18009134C
0x180091309  cmp     byte ptr [rax+19h], 2
0x18009130d  jb      short loc_18009134C
0x18009130f  call    RdpX_GetActivityIdPrefix
0x180091314  lea     rcx, aGethttpheaderf; "GetHttpHeaderFromResponse(WINHTTP_QUERY"...
0x18009131b  mov     [rsp+80h+dwTotalLength], ebx
0x18009131f  mov     qword ptr [rsp+80h+dwOptionalLength], rcx
0x180091324  lea     r8, WPP_4597d29bceaf3c7788eacfece4cd35a8_Traceguids
0x18009132b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091332  mov     edx, 66h ; 'f'
0x180091337  mov     r9d, eax
0x18009133a  mov     rcx, [rcx+10h]
0x18009133e  call    WPP_SF_DsD
0x180091343  mov     rdi, [rbp+String]
0x180091347  jmp     loc_180091972
0x18009134c  mov     rdi, [rbp+String]
0x180091350  jmp     loc_180091979
0x180091355  mov     rcx, r15; this
0x180091358  call    ?ShouldEndEarly@RdpWinRadcHttpRequest@@AEAA_NXZ; RdpWinRadcHttpRequest::ShouldEndEarly(void)
0x18009135d  mov     rdi, [rbp+String]
0x180091361  test    al, al
0x180091363  jnz     loc_180091A94
0x180091369  mov     edx, dword ptr [rbp+bstrString]
0x18009136c  mov     eax, edx
0x18009136e  mov     [rbp+arg_8], edx
0x180091371  sub     eax, 0C8h
0x180091376  jz      loc_180091796
0x18009137c  sub     eax, 68h ; 'h'
0x18009137f  jz      loc_180091720
0x180091385  sub     eax, 61h ; 'a'
0x180091388  jz      loc_18009147D
0x18009138e  sub     eax, 3
0x180091391  jz      short loc_18009140D
0x180091393  sub     eax, 62h ; 'b'
0x180091396  jz      short loc_18009140D
0x180091398  cmp     eax, 2
0x18009139b  jz      short loc_18009140D
0x18009139d  mov     rcx, [r15+0C8h]
0x1800913a4  mov     r8d, edx
0x1800913a7  mov     rdx, [r15+10h]
0x1800913ab  mov     r9, rdi
0x1800913ae  mov     rax, [rcx]
0x1800913b1  mov     rax, [rax+20h]
0x1800913b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800913ba  mov     rax, cs:WPP_GLOBAL_Control
0x1800913c1  cmp     rax, r12
0x1800913c4  jz      short loc_180091402
0x1800913c6  test    dword ptr [rax+1Ch], 10000h
0x1800913cd  jz      short loc_180091402
0x1800913cf  cmp     byte ptr [rax+19h], 3
0x1800913d3  jb      short loc_180091402
0x1800913d5  mov     ebx, dword ptr [rbp+bstrString]
0x1800913d8  mov     r14, [r15+10h]
0x1800913dc  call    RdpX_GetActivityIdPrefix
0x1800913e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800913e8  mov     edx, 76h ; 'v'
0x1800913ed  mov     [rsp+80h+dwTotalLength], ebx
0x1800913f1  mov     r9d, eax
0x1800913f4  mov     qword ptr [rsp+80h+dwOptionalLength], r14
0x1800913f9  mov     rcx, [rcx+10h]
0x1800913fd  call    WPP_SF_DID
0x180091402  mov     r14d, 80040303h
0x180091408  jmp     loc_180091A94
0x18009140d  mov     rcx, [r15+0C8h]
0x180091414  mov     r8d, edx
0x180091417  mov     rdx, [r15+10h]
0x18009141b  mov     r9, rdi
0x18009141e  mov     rax, [rcx]
0x180091421  mov     rax, [rax+20h]
0x180091425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009142a  mov     rax, cs:WPP_GLOBAL_Control
0x180091431  cmp     rax, r12
0x180091434  jz      short loc_180091472
0x180091436  test    dword ptr [rax+1Ch], 10000h
0x18009143d  jz      short loc_180091472
0x18009143f  cmp     byte ptr [rax+19h], 3
0x180091443  jb      short loc_180091472
0x180091445  mov     ebx, dword ptr [rbp+bstrString]
0x180091448  mov     r14, [r15+10h]
0x18009144c  call    RdpX_GetActivityIdPrefix
0x180091451  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
