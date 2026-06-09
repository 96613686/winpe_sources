# ParseRootKey

- ea: `0x180005a24`
- end: `0x18000655b`
- name: `ParseRootKey`
- size: `2871`
- prototype: `__int64 __fastcall(LDAP *ld, LDAPMessage *entry)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005330`
- `0x180005740`

## callees

- `0x180001630`
- `0x180003e08`
- `0x180003e30`
- `0x180003e70`
- `0x180005a24`
- `0x180006cb8`
- `0x180007b60`
- `0x18000fcbc`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a694`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180005d0d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180005d90`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180005d0d`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180005d90`
- `WLDAP32!__imp_LdapGetLastError` at `0x180006351`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800063ea`
- `WLDAP32!__imp_LdapGetLastError` at `0x180006351`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800063ea`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800062ed`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800064d8`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800062ed`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800064d8`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180005b03`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180005b03`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180005b76`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180005b76`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180005bcf`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x180005bcf`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800062bf`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800064ca`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800062bf`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800064ca`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x180006307`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x180006307`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800062d5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800064bc`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800062d5`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800064bc`
- `WLDAP32!__imp_ber_free` at `0x1800064f1`
- `WLDAP32!__imp_ber_free` at `0x1800064f1`
- `RPCRT4!UuidFromStringW` at `0x180005fb5`
- `RPCRT4!UuidFromStringW` at `0x180005fb5`

## string_xrefs

- `0x180005ab2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180005b1b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180005cf7`: `msKds-CreateTime`
- `0x180005d27`: `msKds-CreateTime`

## pseudocode

```c
__int64 __fastcall ParseRootKey(LDAP *ld, LDAPMessage *entry, _QWORD *a3)
{
  wchar_t *v3; // rbp
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  signed int LastError; // ebx
  void *v10; // r13
  _DWORD *v11; // rsi
  __int64 v12; // r8
  PWCHAR attributeW; // r15
  __int64 v14; // rcx
  PWCHAR *valuesW; // rax
  __int64 v16; // rax
  struct berval **values_lenW; // rax
  void *v18; // rax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  signed int v21; // eax
  void *v22; // rax
  void *v23; // rcx
  size_t v24; // r8
  unsigned __int8 *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned __int8 *v29; // rax
  void *v30; // rax
  void *v31; // rax
  int v32; // eax
  __int64 v33; // rax
  unsigned __int64 v34; // rbp
  wchar_t *v35; // rax
  unsigned int v36; // r9d
  unsigned int v37; // ecx
  struct berval **v38; // r12
  int v39; // edx
  const wchar_t *v40; // rax
  __int64 v41; // rcx
  int v43; // [rsp+30h] [rbp-B8h]
  struct berval **v44; // [rsp+38h] [rbp-B0h]
  PWCHAR *vals; // [rsp+40h] [rbp-A8h]
  wchar_t *v46; // [rsp+48h] [rbp-A0h]
  size_t Size; // [rsp+50h] [rbp-98h]
  unsigned __int8 **v48; // [rsp+58h] [rbp-90h]
  BerElement *ptr; // [rsp+70h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+78h] [rbp-70h] BYREF
  _DWORD *v53; // [rsp+88h] [rbp-60h]
  __int64 v54; // [rsp+90h] [rbp-58h]
  const wchar_t *v55; // [rsp+98h] [rbp-50h]
  int v56; // [rsp+A0h] [rbp-48h]
  int v57; // [rsp+A4h] [rbp-44h]

  ptr = 0;
  v3 = 0;
  v46 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids);
  v7 = SIDKeyProvAlloc(0xE0u);
  v8 = v7;
  if ( !v7 )
  {
    LastError = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x2C9u);
    *a3 = 0;
    goto LABEL_138;
  }
  v43 = 0;
  LastError = 0;
  v48 = 0;
  v10 = 0;
  Size = 0;
  v11 = v7 + 28;
  v7[28] = 1;
  v7[24] = 1;
  attributeW = ldap_first_attributeW(ld, entry, &ptr);
  v14 = -1;
  if ( !attributeW )
  {
    v38 = 0;
    v39 = 0;
    goto LABEL_124;
  }
  while ( !wcscmp_0(attributeW, L"msKds-SecretAgreementParam")
       || !wcscmp_0(attributeW, L"msKds-RootKeyData")
       || !wcscmp_0(attributeW, L"msKds-KDFParam") )
  {
    vals = 0;
    values_lenW = ldap_get_values_lenW(ld, entry, attributeW);
    v44 = values_lenW;
    if ( !values_lenW )
    {
      LastError = LdapGetLastError();
      SidKeyDebugTraceError(
        LastError,
        "ulReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
        0x2E0u);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_106;
    }
    v48 = (unsigned __int8 **)*values_lenW;
    if ( !*values_lenW )
    {
      v36 = 744;
      goto LABEL_104;
    }
LABEL_17:
    if ( !wcscmp_0(attributeW, L"msKds-KDFAlgorithmID") )
    {
      v18 = SIDKeyProvAlloc(Size);
      *((_QWORD *)v8 + 4) = v18;
      if ( !v18 )
      {
        v36 = 779;
        goto LABEL_111;
      }
      memcpy_0(v18, v10, Size);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v20 = 11;
LABEL_90:
        WPP_SF_S(v19[2], v20, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
      }
    }
    else if ( !wcscmp_0(attributeW, L"msKds-KDFParam") )
    {
      v21 = ValidateKDFParam(v48[1], *(_DWORD *)v48);
      LastError = v21;
      if ( v21 >= 0 )
      {
        v22 = SIDKeyProvAlloc(*(unsigned int *)v48);
        *((_QWORD *)v8 + 5) = v22;
        v23 = v22;
        if ( !v22 )
        {
          v36 = 797;
          goto LABEL_111;
        }
        v8[12] = *(_DWORD *)v48;
        v24 = *(unsigned int *)v48;
        v25 = v48[1];
LABEL_75:
        memcpy_0(v23, v25, v24);
        goto LABEL_91;
      }
      SidKeyDebugTraceError(v21, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x326u);
      if ( LastError != -2146893819 )
        goto LABEL_106;
      LastError = 0;
      *v11 = 0;
      v8[24] = 0;
      *((_QWORD *)v8 + 18) = L"msKds-KDFParam";
      *((_QWORD *)v8 + 13) = L"msKds-KDFParam";
    }
    else if ( !wcscmp_0(attributeW, L"msKds-CreateTime") )
    {
      v26 = _wtoi64((const wchar_t *)v10);
      *((_QWORD *)v8 + 16) = v26;
      if ( !v26 )
      {
        *v11 = 0;
        *((_QWORD *)v8 + 18) = L"msKds-CreateTime";
        SidKeyDebugTraceError(
          0x80090003,
          "NTE_BAD_KEY",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x33Cu);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 12;
          goto LABEL_90;
        }
      }
    }
    else if ( !wcscmp_0(attributeW, L"msKds-UseStartTime") )
    {
      v27 = _wtoi64((const wchar_t *)v10);
      *((_QWORD *)v8 + 17) = v27;
      if ( !v27 )
      {
        *v11 = 0;
        *((_QWORD *)v8 + 18) = L"msKds-UseStartTime";
        SidKeyDebugTraceError(
          0x80090003,
          "NTE_BAD_KEY",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x347u);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 13;
          goto LABEL_90;
        }
      }
    }
    else if ( !wcscmp_0(attributeW, L"msKds-Version") )
    {
      LastError = ConvertStrToUlong((PCWSTR)v10, v8);
      v28 = *v8;
      v8[6] = *v8;
      if ( LastError >= 0 )
      {
        if ( v28 != 1 )
        {
          *v11 = 0;
          v8[24] = 0;
          *((_QWORD *)v8 + 18) = L"msKds-Version";
          *((_QWORD *)v8 + 13) = L"msKds-Version";
          SidKeyDebugTraceError(
            0x80090003,
            "NTE_BAD_KEY",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
            0x360u);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 15;
            goto LABEL_90;
          }
        }
      }
      else
      {
        *v11 = 0;
        v8[24] = 0;
        *((_QWORD *)v8 + 18) = L"msKds-Version";
        *((_QWORD *)v8 + 13) = L"msKds-Version";
        SidKeyDebugTraceError(
          0x80090003,
          "NTE_BAD_KEY",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x357u);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 14;
          goto LABEL_90;
        }
      }
    }
    else
    {
      if ( !wcscmp_0(attributeW, L"msKds-DomainID") )
      {
        *((_QWORD *)v8 + 15) = SIDKeyProvAlloc(Size);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
        v23 = (void *)*((_QWORD *)v8 + 15);
        if ( !v23 )
        {
          v36 = 875;
          goto LABEL_111;
        }
        v24 = Size;
        v25 = (unsigned __int8 *)v10;
        goto LABEL_75;
      }
      if ( *attributeW == 99 && attributeW[1] == 110 && !attributeW[2] )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
        if ( UuidFromStringW((RPC_WSTR)v10, (UUID *)(v8 + 1)) )
        {
          *v11 = 0;
          *((_QWORD *)v8 + 18) = L"cn";
          SidKeyDebugTraceError(
            0x80090003,
            "NTE_BAD_KEY",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
            0x37Bu);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 18;
            goto LABEL_90;
          }
        }
      }
      else if ( !wcscmp_0(attributeW, L"msKds-RootKeyData") )
      {
        if ( *(_DWORD *)v48 == 64 )
        {
          v8[38] = 64;
          v29 = v48[1];
          *((_OWORD *)v8 + 10) = *(_OWORD *)v29;
          *((_OWORD *)v8 + 11) = *((_OWORD *)v29 + 1);
          *((_OWORD *)v8 + 12) = *((_OWORD *)v29 + 2);
          *((_OWORD *)v8 + 13) = *((_OWORD *)v29 + 3);
        }
        else
        {
          *v11 = 0;
          *((_QWORD *)v8 + 18) = L"msKds-RootKeyData";
          SidKeyDebugTraceError(
            0x80090003,
            "NTE_BAD_KEY",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
            0x385u);
        }
      }
      else if ( !wcscmp_0(attributeW, L"msKds-SecretAgreementAlgorithmID") )
      {
        v30 = SIDKeyProvAlloc(Size);
        *((_QWORD *)v8 + 7) = v30;
        if ( !v30 )
        {
          v36 = 916;
          goto LABEL_111;
        }
        memcpy_0(v30, v10, Size);
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v20 = 19;
          goto LABEL_90;
        }
      }
      else
      {
        if ( !wcscmp_0(attributeW, L"msKds-SecretAgreementParam") )
        {
          v31 = SIDKeyProvAlloc(*(unsigned int *)v48);
          *((_QWORD *)v8 + 8) = v31;
          v23 = v31;
          if ( !v31 )
          {
            v36 = 928;
            goto LABEL_111;
          }
          v8[18] = *(_DWORD *)v48;
          v24 = *(unsigned int *)v48;
          v25 = v48[1];
          goto LABEL_75;
        }
        if ( !wcscmp_0(attributeW, L"msKds-PrivateKeyLength") )
        {
          v32 = ConvertStrToUlong((PCWSTR)v10, v8 + 19);
          LastError = v32;
          if ( v32 < 0 )
          {
            v36 = 939;
LABEL_117:
            v37 = v32;
            goto LABEL_105;
          }
          if ( !v8[19] )
          {
            *v11 = 0;
            v8[24] = 0;
            *((_QWORD *)v8 + 18) = L"msKds-PrivateKeyLength";
            *((_QWORD *)v8 + 13) = L"msKds-PrivateKeyLength";
            SidKeyDebugTraceError(
              0x80090003,
              "NTE_BAD_KEY",
              "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
              0x3B4u);
          }
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v20 = 20;
            goto LABEL_90;
          }
        }
        else if ( !wcscmp_0(attributeW, L"msKds-PublicKeyLength") )
        {
          v32 = ConvertStrToUlong((PCWSTR)v10, v8 + 20);
          LastError = v32;
          if ( v32 < 0 )
          {
            v36 = 957;
            goto LABEL_117;
          }
          if ( !v8[20] )
          {
            *v11 = 0;
            v8[24] = 0;
            *((_QWORD *)v8 + 18) = L"msKds-PublicKeyLength";
            *((_QWORD *)v8 + 13) = L"msKds-PublicKeyLength";
            SidKeyDebugTraceError(
              0x80090003,
              "NTE_BAD_KEY",
              "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
              0x3C6u);
          }
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v20 = 21;
            goto LABEL_90;
          }
        }
      }
    }
LABEL_91:
    if ( !*v11 && !v43 )
    {
      v33 = -1;
      do
        ++v33;
      while ( attributeW[v33] );
      v34 = 2 * v33 + 2;
      v35 = (wchar_t *)SIDKeyProvAlloc(v34);
      v46 = v35;
      if ( !v35 )
      {
        v36 = 979;
LABEL_111:
        LastError = -2147024882;
        v37 = -2147024882;
LABEL_105:
        SidKeyDebugTraceError(v37, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v36);
LABEL_106:
        v10 = vals;
        goto LABEL_107;
      }
      memcpy_0(v35, attributeW, v34);
      v43 = 1;
    }
    ldap_memfreeW(attributeW);
    if ( vals )
    {
      ldap_value_freeW(vals);
      vals = 0;
    }
    if ( v44 )
    {
      ldap_value_free_len(v44);
      v44 = 0;
    }
    attributeW = ldap_next_attributeW(ld, entry, ptr);
    if ( !attributeW )
      goto LABEL_106;
  }
  v44 = 0;
  valuesW = ldap_get_valuesW(ld, entry, attributeW);
  vals = valuesW;
  v10 = valuesW;
  if ( valuesW )
  {
    v10 = *valuesW;
    if ( !*valuesW )
    {
      v36 = 766;
LABEL_104:
      LastError = -2147024880;
      v37 = -2147024880;
      goto LABEL_105;
    }
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v10 + v16) );
    Size = 2 * v16 + 2;
    goto LABEL_17;
  }
  LastError = LdapGetLastError();
  SidKeyDebugTraceError(
    LastError,
    "ulReturn",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
    0x2F4u);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_107:
  v3 = v46;
  v14 = -1;
  v38 = v44;
  v39 = v43;
LABEL_124:
  *a3 = v8;
  if ( !*v11 && v39 == 1 && (Microsoft_Windows_KdsSvcEnableBits & 4) != 0 )
  {
    v54 = 16;
    v53 = v8 + 1;
    if ( v3 )
    {
      do
        ++v14;
      while ( v3[v14] );
      v40 = v3;
      v41 = (unsigned int)(2 * v14 + 2);
    }
    else
    {
      v40 = L"NULL";
      v41 = 10;
    }
    v55 = v40;
    v56 = v41;
    v57 = 0;
    McGenEventWrite_EventWriteTransfer(v41, (const EVENT_DESCRIPTOR *)KdsSvcInvalidMRK, v12, 3u, &v52);
  }
  if ( v10 )
    ldap_value_freeW((PWCHAR *)v10);
  if ( attributeW )
    ldap_memfreeW(attributeW);
  if ( v38 )
    ldap_value_free_len(v38);
LABEL_138:
  if ( ptr )
    ber_free(ptr, 0);
  if ( v3 )
    SIDKeyProvFree(v3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids,
      (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180005a24  mov     [rsp+arg_18], rbx
0x180005a29  push    rbp
0x180005a2a  push    rsi
0x180005a2b  push    rdi
0x180005a2c  push    r12
0x180005a2e  push    r13
0x180005a30  push    r14
0x180005a32  push    r15
0x180005a34  sub     rsp, 0B0h
0x180005a3b  mov     rax, cs:__security_cookie
0x180005a42  xor     rax, rsp
0x180005a45  mov     [rsp+0E8h+var_40], rax
0x180005a4d  xor     esi, esi
0x180005a4f  mov     [rsp+0E8h+entry], rdx
0x180005a54  mov     [rsp+0E8h+ptr], rsi
0x180005a59  mov     ebp, esi
0x180005a5b  mov     [rsp+0E8h+var_A0], rsi
0x180005a60  mov     r14, r8
0x180005a63  mov     r12, rdx
0x180005a66  mov     [rsp+0E8h+ld], rcx
0x180005a6b  mov     r15, rcx
0x180005a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a75  lea     r13, WPP_GLOBAL_Control
0x180005a7c  cmp     rcx, r13
0x180005a7f  jz      short loc_180005A9A
0x180005a81  test    byte ptr [rcx+1Ch], 4
0x180005a85  jz      short loc_180005A9A
0x180005a87  mov     rcx, [rcx+10h]
0x180005a8b  lea     edx, [rsi+0Ah]
0x180005a8e  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x180005a95  call    WPP_SF_
0x180005a9a  mov     ecx, 0E0h; unsigned __int64
0x180005a9f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180005aa4  mov     rdi, rax
0x180005aa7  test    rax, rax
0x180005aaa  jnz     short loc_180005AD7
0x180005aac  mov     r9d, 2C9h; unsigned int
0x180005ab2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005ab9  lea     rdx, aHr; "hr"
0x180005ac0  mov     ecx, 8007000Eh; unsigned int
0x180005ac5  mov     ebx, 8007000Eh
0x180005aca  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005acf  mov     [r14], rdi
0x180005ad2  jmp     loc_1800064E5
0x180005ad7  mov     [rsp+0E8h+var_B8], esi
0x180005adb  lea     r8, [rsp+0E8h+ptr]; ptr
0x180005ae0  mov     ebx, esi
0x180005ae2  mov     [rsp+0E8h+var_90], rsi
0x180005ae7  mov     r13, rsi
0x180005aea  mov     [rsp+0E8h+Size], rsi
0x180005aef  lea     rsi, [rax+70h]
0x180005af3  mov     rdx, r12; entry
0x180005af6  mov     eax, 1
0x180005afb  mov     rcx, r15; ld
0x180005afe  mov     [rsi], eax
0x180005b00  mov     [rdi+60h], eax
0x180005b03  call    cs:__imp_ldap_first_attributeW
0x180005b09  mov     r15, rax
0x180005b0c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180005b10  xor     eax, eax
0x180005b12  test    r15, r15
0x180005b15  jz      loc_18000641F
0x180005b1b  lea     r12, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005b22  lea     rdx, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x180005b29  mov     rcx, r15; String1
0x180005b2c  lea     rbp, aHr; "hr"
0x180005b33  call    wcscmp_0
0x180005b38  test    eax, eax
0x180005b3a  jz      short loc_180005BB9
0x180005b3c  lea     rdx, aMskdsRootkeyda; "msKds-RootKeyData"
0x180005b43  mov     rcx, r15; String1
0x180005b46  call    wcscmp_0
0x180005b4b  test    eax, eax
0x180005b4d  jz      short loc_180005BB9
0x180005b4f  lea     rdx, aMskdsKdfparam; "msKds-KDFParam"
0x180005b56  mov     rcx, r15; String1
0x180005b59  call    wcscmp_0
0x180005b5e  xor     ecx, ecx
0x180005b60  test    eax, eax
0x180005b62  jz      short loc_180005BB9
0x180005b64  mov     rdx, [rsp+0E8h+entry]; entry
0x180005b69  mov     r8, r15; attr
0x180005b6c  mov     [rsp+0E8h+var_B0], rcx
0x180005b71  mov     rcx, [rsp+0E8h+ld]; ld
0x180005b76  call    cs:__imp_ldap_get_valuesW
0x180005b7c  xor     ecx, ecx
0x180005b7e  mov     [rsp+0E8h+vals], rax
0x180005b83  mov     r13, rax
0x180005b86  test    rax, rax
0x180005b89  jz      loc_180006351
0x180005b8f  mov     r13, [rax]
0x180005b92  test    r13, r13
0x180005b95  jz      loc_18000631A
0x180005b9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005b9f  inc     rax
0x180005ba2  cmp     [r13+rax*2+0], cx
0x180005ba8  jnz     short loc_180005B9F
0x180005baa  lea     rax, ds:2[rax*2]
0x180005bb2  mov     [rsp+0E8h+Size], rax
0x180005bb7  jmp     short loc_180005BF4
0x180005bb9  mov     rdx, [rsp+0E8h+entry]; Message
0x180005bbe  mov     r8, r15; attr
0x180005bc1  mov     rcx, [rsp+0E8h+ld]; ExternalHandle
0x180005bc6  mov     [rsp+0E8h+vals], 0
0x180005bcf  call    cs:__imp_ldap_get_values_lenW
0x180005bd5  mov     [rsp+0E8h+var_B0], rax
0x180005bda  test    rax, rax
0x180005bdd  jz      loc_1800063EA
0x180005be3  mov     rax, [rax]
0x180005be6  mov     [rsp+0E8h+var_90], rax
0x180005beb  test    rax, rax
0x180005bee  jz      loc_1800063DF
0x180005bf4  lea     rdx, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x180005bfb  mov     rcx, r15; String1
0x180005bfe  call    wcscmp_0
0x180005c03  test    eax, eax
0x180005c05  jnz     short loc_180005C59
0x180005c07  mov     rcx, [rsp+0E8h+Size]; unsigned __int64
0x180005c0c  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180005c11  mov     [rdi+20h], rax
0x180005c15  test    rax, rax
0x180005c18  jz      loc_18000637F
0x180005c1e  mov     r8, [rsp+0E8h+Size]; Size
0x180005c23  mov     rdx, r13; Src
0x180005c26  mov     rcx, rax; void *
0x180005c29  call    memcpy_0
0x180005c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c35  lea     rbp, WPP_GLOBAL_Control
0x180005c3c  cmp     rcx, rbp
0x180005c3f  jz      loc_18000626C
0x180005c45  test    byte ptr [rcx+1Ch], 4
0x180005c49  jz      loc_18000626C
0x180005c4f  mov     edx, 0Bh
0x180005c54  jmp     loc_180006259
0x180005c59  lea     rdx, aMskdsKdfparam; "msKds-KDFParam"
0x180005c60  mov     rcx, r15; String1
0x180005c63  call    wcscmp_0
0x180005c68  test    eax, eax
0x180005c6a  jnz     loc_180005CF7
0x180005c70  mov     rax, [rsp+0E8h+var_90]
0x180005c75  mov     edx, [rax]; unsigned int
0x180005c77  mov     rcx, [rax+8]; unsigned __int8 *
0x180005c7b  call    ?ValidateKDFParam@@YAJPEAEK@Z; ValidateKDFParam(uchar *,ulong)
0x180005c80  mov     ebx, eax
0x180005c82  test    eax, eax
0x180005c84  js      short loc_180005CBA
0x180005c86  mov     rax, [rsp+0E8h+var_90]
0x180005c8b  mov     ecx, [rax]; unsigned __int64
0x180005c8d  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180005c92  mov     [rdi+28h], rax
0x180005c96  mov     rcx, rax
0x180005c99  test    rax, rax
0x180005c9c  jz      loc_180006394
0x180005ca2  mov     rbp, [rsp+0E8h+var_90]
0x180005ca7  mov     eax, [rbp+0]
0x180005caa  mov     [rdi+30h], eax
0x180005cad  mov     r8d, [rbp+0]
0x180005cb1  mov     rdx, [rbp+8]
0x180005cb5  jmp     loc_180006145
0x180005cba  mov     r9d, 326h; unsigned int
0x180005cc0  mov     r8, r12; char *
0x180005cc3  mov     rdx, rbp; char *
0x180005cc6  mov     ecx, ebx; unsigned int
0x180005cc8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005ccd  cmp     ebx, 80090005h
0x180005cd3  jnz     loc_180006335
0x180005cd9  xor     ebx, ebx
0x180005cdb  lea     rax, aMskdsKdfparam; "msKds-KDFParam"
0x180005ce2  mov     [rsi], ebx
0x180005ce4  mov     [rdi+60h], ebx
0x180005ce7  mov     [rdi+90h], rax
0x180005cee  mov     [rdi+68h], rax
0x180005cf2  jmp     loc_18000626C
0x180005cf7  lea     rdx, aMskdsCreatetim; "msKds-CreateTime"
0x180005cfe  mov     rcx, r15; String1
0x180005d01  call    wcscmp_0
0x180005d06  test    eax, eax
0x180005d08  jnz     short loc_180005D7A
0x180005d0a  mov     rcx, r13; String
0x180005d0d  call    cs:__imp__wtoi64
0x180005d13  xor     ecx, ecx
0x180005d15  mov     [rdi+80h], rax
0x180005d1c  test    rax, rax
0x180005d1f  jnz     loc_18000626C
0x180005d25  mov     [rsi], ecx
0x180005d27  lea     rax, aMskdsCreatetim; "msKds-CreateTime"
0x180005d2e  mov     ecx, 80090003h; unsigned int
0x180005d33  mov     [rdi+90h], rax
0x180005d3a  mov     r9d, 33Ch; unsigned int
0x180005d40  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180005d47  mov     r8, r12; char *
0x180005d4a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d56  lea     rax, WPP_GLOBAL_Control
0x180005d5d  cmp     rcx, rax
0x180005d60  jz      loc_18000626C
0x180005d66  test    byte ptr [rcx+1Ch], 1
0x180005d6a  jz      loc_18000626C
0x180005d70  mov     edx, 0Ch
0x180005d75  jmp     loc_180006259
0x180005d7a  lea     rdx, aMskdsUsestartt; "msKds-UseStartTime"
0x180005d81  mov     rcx, r15; String1
0x180005d84  call    wcscmp_0
0x180005d89  test    eax, eax
0x180005d8b  jnz     short loc_180005DFD
0x180005d8d  mov     rcx, r13; String
0x180005d90  call    cs:__imp__wtoi64
0x180005d96  xor     ecx, ecx
0x180005d98  mov     [rdi+88h], rax
0x180005d9f  test    rax, rax
0x180005da2  jnz     loc_18000626C
0x180005da8  mov     [rsi], ecx
0x180005daa  lea     rax, aMskdsUsestartt; "msKds-UseStartTime"
0x180005db1  mov     ecx, 80090003h; unsigned int
0x180005db6  mov     [rdi+90h], rax
0x180005dbd  mov     r9d, 347h; unsigned int
0x180005dc3  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180005dca  mov     r8, r12; char *
0x180005dcd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dd9  lea     rax, WPP_GLOBAL_Control
0x180005de0  cmp     rcx, rax
0x180005de3  jz      loc_18000626C
0x180005de9  test    byte ptr [rcx+1Ch], 1
0x180005ded  jz      loc_18000626C
0x180005df3  mov     edx, 0Dh
0x180005df8  jmp     loc_180006259
0x180005dfd  lea     rdx, aMskdsVersion; "msKds-Version"
0x180005e04  mov     rcx, r15; String1
0x180005e07  call    wcscmp_0
0x180005e0c  test    eax, eax
0x180005e0e  jnz     loc_180005EED
0x180005e14  mov     rdx, rdi; unsigned int *
0x180005e17  mov     rcx, r13; SourceString
0x180005e1a  call    ?ConvertStrToUlong@@YAJPEAGPEAK@Z; ConvertStrToUlong(ushort *,ulong *)
0x180005e1f  mov     ebx, eax
0x180005e21  xor     ecx, ecx
0x180005e23  mov     eax, [rdi]
0x180005e25  mov     [rdi+18h], eax
0x180005e28  test    ebx, ebx
0x180005e2a  jns     short loc_180005E88
0x180005e2c  mov     [rsi], ecx
0x180005e2e  lea     rbp, aMskdsVersion; "msKds-Version"
0x180005e35  mov     [rdi+60h], ecx
0x180005e38  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180005e3f  mov     ecx, 80090003h; unsigned int
0x180005e44  mov     [rdi+90h], rbp
0x180005e4b  mov     r9d, 357h; unsigned int
0x180005e51  mov     [rdi+68h], rbp
0x180005e55  mov     r8, r12; char *
0x180005e58  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e64  lea     rax, WPP_GLOBAL_Control
0x180005e6b  cmp     rcx, rax
0x180005e6e  jz      loc_18000626C
0x180005e74  test    byte ptr [rcx+1Ch], 1
0x180005e78  jz      loc_18000626C
0x180005e7e  mov     edx, 0Eh
0x180005e83  jmp     loc_180006259
0x180005e88  cmp     eax, 1
0x180005e8b  jz      loc_18000626C
0x180005e91  lea     rax, aMskdsVersion; "msKds-Version"
0x180005e98  mov     [rsi], ecx
0x180005e9a  mov     [rdi+60h], ecx
0x180005e9d  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180005ea4  mov     ecx, 80090003h; unsigned int
0x180005ea9  mov     [rdi+90h], rax
0x180005eb0  mov     r9d, 360h; unsigned int
0x180005eb6  mov     [rdi+68h], rax
0x180005eba  mov     r8, r12; char *
0x180005ebd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180005ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ec9  lea     rax, WPP_GLOBAL_Control
0x180005ed0  cmp     rcx, rax
0x180005ed3  jz      loc_18000626C
0x180005ed9  test    byte ptr [rcx+1Ch], 1
0x180005edd  jz      loc_18000626C
0x180005ee3  mov     edx, 0Fh
0x180005ee8  jmp     loc_180006259
0x180005eed  lea     rdx, aMskdsDomainid; "msKds-DomainID"
0x180005ef4  mov     rcx, r15; String1
0x180005ef7  call    wcscmp_0
0x180005efc  xor     ecx, ecx
0x180005efe  test    eax, eax
0x180005f00  jnz     short loc_180005F5B
0x180005f02  mov     rcx, [rsp+0E8h+Size]; unsigned __int64
0x180005f07  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180005f0c  mov     [rdi+78h], rax
0x180005f10  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f17  lea     rax, WPP_GLOBAL_Control
0x180005f1e  cmp     rcx, rax
0x180005f21  jz      short loc_180005F41
0x180005f23  test    byte ptr [rcx+1Ch], 4
0x180005f27  jz      short loc_180005F41
0x180005f29  mov     rcx, [rcx+10h]
0x180005f2d  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x180005f34  mov     edx, 10h
0x180005f39  mov     r9, r13
0x180005f3c  call    WPP_SF_S
0x180005f41  mov     rcx, [rdi+78h]
  ... truncated ...
```
