# TraceW8ReturnCode(ushort *,uint)

- ea: `0x1800bbdb8`
- end: `0x1800be3b4`
- name: `?TraceW8ReturnCode@@YAJPEAGI@Z`
- size: `9724`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a5b20`

## callees

- `0x1800123f0`
- `0x18004ce90`
- `0x18009c84c`
- `0x1800bbdb8`
- `0x1800be3bc`

## string_xrefs

- `0x1800bd242`: `TPM_RC_PARAMSIZE`
- `0x1800bd1f0`: `TPM_RC_COMMAND_CODE`

## pseudocode

```c
__int64 __fastcall TraceW8ReturnCode(unsigned __int16 *a1, unsigned int a2)
{
  int Buffer; // ebx
  int v5; // eax
  int v6; // ecx
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  unsigned int v57; // ecx
  unsigned int v58; // ecx
  unsigned int v59; // ecx
  unsigned int v60; // ecx
  int v61; // eax
  unsigned __int16 *v62; // rdi
  __int64 v64; // [rsp+30h] [rbp-30h]
  __int64 v65; // [rsp+30h] [rbp-30h]
  __int64 v66; // [rsp+30h] [rbp-30h]
  __int64 v67; // [rsp+38h] [rbp-28h]
  __int64 v68; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v69; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v70; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int64 v71; // [rsp+A0h] [rbp+40h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+A8h] [rbp+48h] BYREF

  v69 = 0;
  pszDest = 0;
  v70 = 0;
  v71 = 0;
  if ( !a2 )
  {
    while ( 1 )
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        break;
      if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"%sReturnCode = TPM_RC_SUCCESS\r\n", a1) != -2147024774 )
        goto LABEL_483;
    }
LABEL_484:
    v62 = v69;
    goto LABEL_485;
  }
  if ( a2 == 30 )
  {
    while ( 1 )
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        goto LABEL_484;
      LODWORD(v67) = 30;
      if ( (unsigned int)StringCchPrintfExW(
                           pszDest,
                           v71,
                           &pszDest,
                           &v71,
                           0,
                           L"%sReturnCode = TPM_RC_BAD_TAG (0x%08x)\r\n",
                           a1,
                           v67) != -2147024774 )
        goto LABEL_483;
    }
  }
  if ( (a2 & 0x80u) != 0 )
  {
    if ( (a2 & 0x40) != 0 )
    {
      while ( 1 )
      {
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        if ( Buffer < 0 )
          goto LABEL_484;
        LODWORD(v67) = (a2 >> 8) & 0xF;
        if ( (unsigned int)StringCchPrintfExW(
                             pszDest,
                             v71,
                             &pszDest,
                             &v71,
                             0,
                             L"%sReturnCode = PARAMETER-%d: ",
                             a1,
                             v67) != -2147024774 )
          goto LABEL_324;
      }
    }
    if ( (a2 & 0x800) != 0 )
    {
      while ( 1 )
      {
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        if ( Buffer < 0 )
          goto LABEL_484;
        LODWORD(v67) = (a2 >> 8) & 7;
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"%sReturnCode = SESSION-%d: ", a1, v67) != -2147024774 )
          goto LABEL_324;
      }
    }
    do
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        goto LABEL_484;
      LODWORD(v67) = (a2 >> 8) & 7;
      v36 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"%sReturnCode = HANDLE-%d: ", a1, v67);
    }
    while ( v36 == -2147024774 );
LABEL_324:
    v37 = a2 & 0xBF;
    if ( v37 > 0x92 )
    {
      if ( v37 > 0x9D )
      {
        v56 = v37 - 159;
        if ( !v56 )
        {
          while ( 1 )
          {
            v61 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_INTEGRITY");
            if ( v61 != -2147024774 )
              break;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
            if ( Buffer < 0 )
              goto LABEL_484;
          }
LABEL_482:
          while ( 1 )
          {
            LODWORD(v66) = a2;
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L" (0x%08x)\r\n", v66) != -2147024774 )
              goto LABEL_483;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
            if ( Buffer < 0 )
              goto LABEL_484;
          }
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_TICKET") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v58 = v57 - 1;
        if ( !v58 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_RESERVED_BITS") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v59 = v58 - 1;
        if ( !v59 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_BAD_AUTH") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v60 = v59 - 1;
        if ( !v60 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_EXPIRED") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        if ( v60 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_POLICY_CC") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
      }
      else
      {
        if ( v37 == 157 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_POLICY_FAIL") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v50 = v37 - 149;
        if ( !v50 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SIZE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v51 = v50 - 1;
        if ( !v51 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SYMMETRIC") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v52 = v51 - 1;
        if ( !v52 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_TAG") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v53 = v52 - 1;
        if ( !v53 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SELECTOR") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v54 = v53 - 2;
        if ( !v54 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_INSUFFICIENT") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v55 = v54 - 1;
        if ( !v55 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SIGNATURE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        if ( v55 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_KEY") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
      }
    }
    else
    {
      if ( v37 == 146 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SCHEME") != -2147024774 )
            goto LABEL_482;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      if ( v37 > 0x89 )
      {
        v44 = v37 - 138;
        if ( !v44 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_TYPE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v45 = v44 - 1;
        if ( !v45 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_HANDLE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v46 = v45 - 1;
        if ( !v46 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_KDF") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v47 = v46 - 1;
        if ( !v47 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_RANGE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v48 = v47 - 1;
        if ( !v48 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_AUTH_FAIL") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v49 = v48 - 1;
        if ( !v49 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NONCE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        if ( v49 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PP") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
      }
      else
      {
        if ( v37 == 137 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_MODE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v38 = v37 - 129;
        if ( !v38 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_ASYMMETRIC") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v39 = v38 - 1;
        if ( !v39 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_ATTRIBUTES") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v40 = v39 - 1;
        if ( !v40 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_HASH") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v41 = v40 - 1;
        if ( !v41 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_VALUE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v42 = v41 - 1;
        if ( !v42 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_HIERARCHY") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        v43 = v42 - 2;
        if ( !v43 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_KEY_SIZE") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
        if ( v43 == 1 )
        {
          do
          {
            if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_MGF") != -2147024774 )
              goto LABEL_482;
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
          }
          while ( Buffer >= 0 );
          goto LABEL_484;
        }
      }
    }
    do
    {
      LODWORD(v66) = a2 & 0x3F;
      if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"UNKNOWN_FMT1(0x%03x)", v66) != -2147024774 )
        goto LABEL_482;
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
    }
    while ( Buffer >= 0 );
    goto LABEL_484;
  }
  if ( (a2 & 0x400) != 0 )
  {
    while ( 1 )
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        goto LABEL_484;
      LODWORD(v68) = a2;
      LODWORD(v67) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(
                           pszDest,
                           v71,
                           &pszDest,
                           &v71,
                           0,
                           L"%sReturnCode = VENDORSPECIFIC(0x%03x) (0x%08x)\r\n",
                           a1,
                           v67,
                           v68) != -2147024774 )
        goto LABEL_483;
    }
  }
  if ( (a2 & 0x800) != 0 )
  {
    while ( 1 )
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        goto LABEL_484;
      v5 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"%sReturnCode = WARNING: ", a1);
      v6 = v5;
      if ( v5 != -2147024774 )
      {
        if ( v5 )
          v6 = -2147023537;
        switch ( a2 & 0xFFF )
        {
          case 0x901u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_CONTEXT_GAP");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x902u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_OBJECT_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x903u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SESSION_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x904u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_MEMORY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x905u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SESSION_HANDLES");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x906u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_OBJECT_HANDLES");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x907u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_LOCALITY");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x908u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_YIELDED");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x909u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_CANCELLED");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x90Au:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_TESTING");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x910u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H0");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x911u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H1");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x912u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H2");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x913u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H3");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x914u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H4");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x915u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H5");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x916u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_H6");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x918u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S0");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x919u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S1");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Au:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S2");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Bu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S3");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Cu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S4");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Du:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S5");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Eu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S6");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x91Fu:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REFERENCE_S7");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x920u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_RATE");
              v6 = v7;
              if ( v7 != -2147024774 )
                goto LABEL_23;
            }
          case 0x921u:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              v7 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_LOCKOUT");
              v6 = v7;
              if ( v7 != -2147024774 )
              {
LABEL_23:
                if ( v7 )
                  v6 = -2147023537;
                goto LABEL_134;
              }
            }
          default:
            break;
        }
        while ( 1 )
        {
          if ( v6 == -2147024774 )
          {
            Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
            if ( Buffer < 0 )
              goto LABEL_484;
          }
          LODWORD(v64) = a2 & 0x7F;
          v8 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"UNKNOWN(0x%03x)", v64);
          v6 = v8;
          if ( v8 != -2147024774 )
          {
            if ( v8 )
              v6 = -2147023537;
LABEL_134:
            while ( 1 )
            {
              if ( v6 == -2147024774 )
              {
                Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
                if ( Buffer < 0 )
                  goto LABEL_484;
              }
              LODWORD(v64) = a2;
              v6 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L" (0x%08x)\r\n", v64);
              if ( v6 != -2147024774 )
                goto LABEL_483;
            }
          }
        }
      }
    }
  }
  if ( (a2 & 0x100) == 0 )
  {
    while ( 1 )
    {
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      if ( Buffer < 0 )
        goto LABEL_484;
      LODWORD(v68) = a2;
      LODWORD(v67) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(
                           pszDest,
                           v71,
                           &pszDest,
                           &v71,
                           0,
                           L"%sReturnCode = LEGACY(0x%03x) (0x%08x)\r\n",
                           a1,
                           v67,
                           v68) != -2147024774 )
        goto LABEL_483;
    }
  }
  do
  {
    Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
    if ( Buffer < 0 )
      goto LABEL_484;
  }
  while ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"%sReturnCode = ERROR: ", a1) == -2147024774 );
  v9 = a2 & 0x1FF;
  if ( v9 <= 0x12F )
  {
    if ( v9 == 303 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_AUTH_UNAVAILABLE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    if ( v9 > 0x124 )
    {
      v17 = v9 - 293;
      if ( !v17 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_AUTH_MISSING") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_POLICY") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PCR") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PCR_CHANGED") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v21 = v20 - 4;
      if ( !v21 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_ECC_POINT") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_UPGRADE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      if ( v22 == 1 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_TOO_MANY_CONTEXTS") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
    }
    else
    {
      if ( v9 == 292 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_AUTH_TYPE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v10 = v9 - 256;
      if ( !v10 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_INITIALIZE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_FAILURE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v12 = v11 - 2;
      if ( !v12 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_SEQUENCE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v13 = v12 - 8;
      if ( !v13 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PRIVATE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v14 = v13 - 14;
      if ( !v14 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_HMAC") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v15 = v14 - 7;
      if ( !v15 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_DISABLED") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_EXCLUSIVE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
      if ( v16 == 2 )
      {
        do
        {
          if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_ECC_CURVE") != -2147024774 )
            goto LABEL_312;
          Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
        }
        while ( Buffer >= 0 );
        goto LABEL_484;
      }
    }
    goto LABEL_281;
  }
  if ( v9 <= 0x149 )
  {
    if ( v9 == 329 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_AUTHORIZATION") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v23 = v9 - 304;
    if ( !v23 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_REBOOT") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v24 = v23 - 18;
    if ( !v24 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PARAMSIZE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v25 = v24 - 1;
    if ( !v25 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_COMMAND_CODE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v26 = v25 - 1;
    if ( !v26 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_AUTHSIZE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v27 = v26 - 2;
    if ( !v27 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_RANGE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_SIZE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    if ( v28 == 1 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_LOCKED") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    goto LABEL_281;
  }
  v29 = v9 - 330;
  if ( v29 )
  {
    v30 = v29 - 1;
    if ( !v30 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_SPACE") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_DEFINED") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v32 = v31 - 4;
    if ( !v32 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_BAD_CONTEXT") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_CPHASH") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_PARENT") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    if ( v34 == 1 )
    {
      do
      {
        if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NEEDS_TEST") != -2147024774 )
          goto LABEL_312;
        Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
      }
      while ( Buffer >= 0 );
      goto LABEL_484;
    }
    do
    {
LABEL_281:
      LODWORD(v65) = a2 & 0x7F;
      if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"UNKNOWN(0x%03x)", v65) != -2147024774 )
        goto LABEL_312;
      Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
    }
    while ( Buffer >= 0 );
    goto LABEL_484;
  }
  while ( 1 )
  {
    v35 = StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L"TPM_RC_NV_UNINITIALIZED");
    if ( v35 != -2147024774 )
      break;
    Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
    if ( Buffer < 0 )
      goto LABEL_484;
  }
LABEL_312:
  while ( 1 )
  {
    LODWORD(v65) = a2;
    if ( (unsigned int)StringCchPrintfExW(pszDest, v71, &pszDest, &v71, 0, L" (0x%08x)\r\n", v65) != -2147024774 )
      break;
    Buffer = TracepGetBuffer(&v69, &pszDest, &v70, &v71);
    if ( Buffer < 0 )
      goto LABEL_484;
  }
LABEL_483:
  v62 = v69;
  Buffer = PlatformFlushTrace(v69, v70 - v71);
LABEL_485:
  PlatformFreeMemory(v62);
  return (unsigned int)Buffer;
}

```

## disassembly

```asm
0x1800bbdb8  mov     [rsp-28h+arg_0], rbx
0x1800bbdbd  mov     [rsp-28h+arg_8], rsi
0x1800bbdc2  push    rbp
0x1800bbdc3  push    rdi
0x1800bbdc4  push    r12
0x1800bbdc6  push    r14
0x1800bbdc8  push    r15
0x1800bbdca  mov     rbp, rsp
0x1800bbdcd  sub     rsp, 60h
0x1800bbdd1  xor     r12d, r12d
0x1800bbdd4  mov     r15d, edx
0x1800bbdd7  mov     [rbp+var_10], r12
0x1800bbddb  mov     r14, rcx
0x1800bbdde  mov     [rbp+pszDest], r12
0x1800bbde2  mov     edi, 8007007Ah
0x1800bbde7  mov     [rbp+var_8], r12
0x1800bbdeb  mov     [rbp+arg_10], r12
0x1800bbdef  test    edx, edx
0x1800bbdf1  jnz     short loc_1800BBE46
0x1800bbdf3  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbdf7  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bbdfb  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bbdff  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bbe03  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bbe08  mov     ebx, eax
0x1800bbe0a  test    eax, eax
0x1800bbe0c  js      loc_1800BE305
0x1800bbe12  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bbe16  lea     rax, aSreturncodeTpm; "%sReturnCode = TPM_RC_SUCCESS\r\n"
0x1800bbe1d  mov     rcx, [rbp+pszDest]; pszDest
0x1800bbe21  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbe25  mov     [rsp+60h+var_30], r14
0x1800bbe2a  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bbe2e  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bbe33  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bbe38  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bbe3d  cmp     eax, edi
0x1800bbe3f  jz      short loc_1800BBDF3
0x1800bbe41  jmp     loc_1800BE2ED
0x1800bbe46  cmp     r15d, 1Eh
0x1800bbe4a  jnz     short loc_1800BBEA7
0x1800bbe4c  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbe50  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bbe54  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bbe58  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bbe5c  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bbe61  mov     ebx, eax
0x1800bbe63  test    eax, eax
0x1800bbe65  js      loc_1800BE305
0x1800bbe6b  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bbe6f  lea     rax, aSreturncodeTpm_0; "%sReturnCode = TPM_RC_BAD_TAG (0x%08x)"...
0x1800bbe76  mov     rcx, [rbp+pszDest]; pszDest
0x1800bbe7a  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbe7e  mov     dword ptr [rsp+60h+var_28], 1Eh
0x1800bbe86  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bbe8a  mov     [rsp+60h+var_30], r14
0x1800bbe8f  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bbe94  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bbe99  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bbe9e  cmp     eax, edi
0x1800bbea0  jz      short loc_1800BBE4C
0x1800bbea2  jmp     loc_1800BE2ED
0x1800bbea7  test    r15b, r15b
0x1800bbeaa  js      loc_1800BD640
0x1800bbeb0  bt      r15d, 0Ah
0x1800bbeb5  jnb     short loc_1800BBF19
0x1800bbeb7  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbebb  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bbebf  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bbec3  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bbec7  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bbecc  mov     ebx, eax
0x1800bbece  test    eax, eax
0x1800bbed0  js      loc_1800BE305
0x1800bbed6  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bbeda  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbede  mov     rcx, [rbp+pszDest]; pszDest
0x1800bbee2  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bbee6  mov     [rsp+60h+var_20], r15d
0x1800bbeeb  mov     eax, r15d
0x1800bbeee  and     eax, 7Fh
0x1800bbef1  mov     dword ptr [rsp+60h+var_28], eax
0x1800bbef5  lea     rax, aSreturncodeVen; "%sReturnCode = VENDORSPECIFIC(0x%03x) ("...
0x1800bbefc  mov     [rsp+60h+var_30], r14
0x1800bbf01  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bbf06  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bbf0b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bbf10  cmp     eax, edi
0x1800bbf12  jz      short loc_1800BBEB7
0x1800bbf14  jmp     loc_1800BE2ED
0x1800bbf19  bt      r15d, 0Bh
0x1800bbf1e  jnb     loc_1800BC945
0x1800bbf24  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbf28  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bbf2c  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bbf30  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bbf34  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bbf39  mov     ebx, eax
0x1800bbf3b  test    eax, eax
0x1800bbf3d  js      loc_1800BE305
0x1800bbf43  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bbf47  lea     rax, aSreturncodeWar; "%sReturnCode = WARNING: "
0x1800bbf4e  mov     rcx, [rbp+pszDest]; pszDest
0x1800bbf52  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbf56  mov     [rsp+60h+var_30], r14
0x1800bbf5b  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bbf5f  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bbf64  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bbf69  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bbf6e  mov     ecx, eax
0x1800bbf70  cmp     eax, edi
0x1800bbf72  jz      short loc_1800BBF24
0x1800bbf74  test    eax, eax
0x1800bbf76  mov     esi, 8007054Fh
0x1800bbf7b  mov     eax, r15d
0x1800bbf7e  cmovnz  ecx, esi
0x1800bbf81  and     eax, 0FFFh
0x1800bbf86  add     eax, 0FFFFF6FFh; switch 33 cases
0x1800bbf8b  cmp     eax, 20h
0x1800bbf8e  ja      def_1800BBFA5; jumptable 00000001800BBFA5 default case, cases 2315-2319,2327
0x1800bbf94  lea     rdx, __ImageBase
0x1800bbf9b  mov     eax, ds:(jpt_1800BBFA5 - 180000000h)[rdx+rax*4]
0x1800bbfa2  add     rax, rdx
0x1800bbfa5  jmp     rax; switch jump
0x1800bbfab  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2305
0x1800bbfad  jnz     short loc_1800BBFCE
0x1800bbfaf  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbfb3  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bbfb7  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bbfbb  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bbfbf  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bbfc4  mov     ebx, eax
0x1800bbfc6  test    eax, eax
0x1800bbfc8  js      loc_1800BE305
0x1800bbfce  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bbfd2  lea     rax, aTpmRcContextGa; "TPM_RC_CONTEXT_GAP"
0x1800bbfd9  mov     rcx, [rbp+pszDest]; pszDest
0x1800bbfdd  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bbfe1  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bbfe6  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bbfea  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bbfef  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bbff4  mov     ecx, eax
0x1800bbff6  cmp     eax, edi
0x1800bbff8  jz      short loc_1800BBFAB; jumptable 00000001800BBFA5 case 2305
0x1800bbffa  test    eax, eax
0x1800bbffc  jz      loc_1800BC8EC
0x1800bc002  mov     ecx, esi
0x1800bc004  jmp     loc_1800BC8EC
0x1800bc009  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2306
0x1800bc00b  jnz     short loc_1800BC02C
0x1800bc00d  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc011  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc015  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc019  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc01d  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc022  mov     ebx, eax
0x1800bc024  test    eax, eax
0x1800bc026  js      loc_1800BE305
0x1800bc02c  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc030  lea     rax, aTpmRcObjectMem; "TPM_RC_OBJECT_MEMORY"
0x1800bc037  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc03b  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc03f  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc044  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc048  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc04d  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc052  mov     ecx, eax
0x1800bc054  cmp     eax, edi
0x1800bc056  jz      short loc_1800BC009; jumptable 00000001800BBFA5 case 2306
0x1800bc058  jmp     short loc_1800BBFFA
0x1800bc05a  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2307
0x1800bc05c  jnz     short loc_1800BC07D
0x1800bc05e  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc062  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc066  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc06a  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc06e  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc073  mov     ebx, eax
0x1800bc075  test    eax, eax
0x1800bc077  js      loc_1800BE305
0x1800bc07d  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc081  lea     rax, aTpmRcSessionMe; "TPM_RC_SESSION_MEMORY"
0x1800bc088  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc08c  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc090  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc095  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc099  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc09e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc0a3  mov     ecx, eax
0x1800bc0a5  cmp     eax, edi
0x1800bc0a7  jz      short loc_1800BC05A; jumptable 00000001800BBFA5 case 2307
0x1800bc0a9  jmp     loc_1800BBFFA
0x1800bc0ae  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2308
0x1800bc0b0  jnz     short loc_1800BC0D1
0x1800bc0b2  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc0b6  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc0ba  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc0be  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc0c2  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc0c7  mov     ebx, eax
0x1800bc0c9  test    eax, eax
0x1800bc0cb  js      loc_1800BE305
0x1800bc0d1  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc0d5  lea     rax, aTpmRcMemory; "TPM_RC_MEMORY"
0x1800bc0dc  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc0e0  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc0e4  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc0e9  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc0ed  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc0f2  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc0f7  mov     ecx, eax
0x1800bc0f9  cmp     eax, edi
0x1800bc0fb  jz      short loc_1800BC0AE; jumptable 00000001800BBFA5 case 2308
0x1800bc0fd  jmp     loc_1800BBFFA
0x1800bc102  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2309
0x1800bc104  jnz     short loc_1800BC125
0x1800bc106  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc10a  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc10e  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc112  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc116  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc11b  mov     ebx, eax
0x1800bc11d  test    eax, eax
0x1800bc11f  js      loc_1800BE305
0x1800bc125  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc129  lea     rax, aTpmRcSessionHa; "TPM_RC_SESSION_HANDLES"
0x1800bc130  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc134  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc138  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc13d  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc141  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc146  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc14b  mov     ecx, eax
0x1800bc14d  cmp     eax, edi
0x1800bc14f  jz      short loc_1800BC102; jumptable 00000001800BBFA5 case 2309
0x1800bc151  jmp     loc_1800BBFFA
0x1800bc156  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2310
0x1800bc158  jnz     short loc_1800BC179
0x1800bc15a  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc15e  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc162  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc166  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc16a  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc16f  mov     ebx, eax
0x1800bc171  test    eax, eax
0x1800bc173  js      loc_1800BE305
0x1800bc179  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc17d  lea     rax, aTpmRcObjectHan; "TPM_RC_OBJECT_HANDLES"
0x1800bc184  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc188  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc18c  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc191  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc195  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc19a  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc19f  mov     ecx, eax
0x1800bc1a1  cmp     eax, edi
0x1800bc1a3  jz      short loc_1800BC156; jumptable 00000001800BBFA5 case 2310
0x1800bc1a5  jmp     loc_1800BBFFA
0x1800bc1aa  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2311
0x1800bc1ac  jnz     short loc_1800BC1CD
0x1800bc1ae  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc1b2  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc1b6  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc1ba  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc1be  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc1c3  mov     ebx, eax
0x1800bc1c5  test    eax, eax
0x1800bc1c7  js      loc_1800BE305
0x1800bc1cd  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc1d1  lea     rax, aTpmRcLocality; "TPM_RC_LOCALITY"
0x1800bc1d8  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc1dc  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc1e0  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc1e5  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc1e9  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc1ee  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc1f3  mov     ecx, eax
0x1800bc1f5  cmp     eax, edi
0x1800bc1f7  jz      short loc_1800BC1AA; jumptable 00000001800BBFA5 case 2311
0x1800bc1f9  jmp     loc_1800BBFFA
0x1800bc1fe  cmp     ecx, edi; jumptable 00000001800BBFA5 case 2312
0x1800bc200  jnz     short loc_1800BC221
0x1800bc202  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc206  lea     r8, [rbp+var_8]; unsigned __int64 *
0x1800bc20a  lea     rdx, [rbp+pszDest]; unsigned __int16 **
0x1800bc20e  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x1800bc212  call    ?TracepGetBuffer@@YAJPEAPEAG0PEA_K1@Z; TracepGetBuffer(ushort * *,ushort * *,unsigned __int64 *,unsigned __int64 *)
0x1800bc217  mov     ebx, eax
0x1800bc219  test    eax, eax
0x1800bc21b  js      loc_1800BE305
0x1800bc221  mov     rdx, [rbp+arg_10]; unsigned __int64
0x1800bc225  lea     rax, aTpmRcYielded; "TPM_RC_YIELDED"
0x1800bc22c  mov     rcx, [rbp+pszDest]; pszDest
0x1800bc230  lea     r9, [rbp+arg_10]; unsigned __int64 *
0x1800bc234  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800bc239  lea     r8, [rbp+pszDest]; unsigned __int16 **
0x1800bc23d  mov     qword ptr [rsp+60h+var_40], r12; unsigned int
0x1800bc242  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800bc247  mov     ecx, eax
  ... truncated ...
```
