# GetDCInfo(ldap *,ushort const *,ushort * *,int *)

- ea: `0x180002bf0`
- end: `0x18000314f`
- name: `?GetDCInfo@@YAJPEAUldap@@PEBGPEAPEAGPEAH@Z`
- size: `1375`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001630`
- `0x180001fdc`
- `0x180002bf0`
- `0x180003b1c`
- `0x180003e70`
- `0x180003f58`
- `0x18000f1a8`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a694`
- `0x18001a6ac`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x180002f1d`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003000`
- `WLDAP32!__imp_LdapGetLastError` at `0x180002f1d`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003000`
- `WLDAP32!__imp_ldap_first_entry` at `0x180002ecf`
- `WLDAP32!__imp_ldap_first_entry` at `0x180002ecf`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800030db`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800030db`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180002f56`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180003035`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180002f56`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180003035`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180002f0f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180002ff2`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180002f0f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180002ff2`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180002e87`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180002e87`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800030a9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800030b7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800030a9`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800030b7`

## string_xrefs

- `0x180002ce3`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002d43`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002da3`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002e99`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002ee5`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002f29`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002f67`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002fb4`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x18000300c`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GetDCInfo(LDAP *ld, unsigned __int16 *a2, unsigned __int16 **a3, int *a4)
{
  unsigned __int16 *v4; // rdi
  void *v6; // r13
  WCHAR *v7; // rsi
  unsigned __int16 *v8; // r12
  __int64 v9; // r14
  signed int DomainControllerInfo; // eax
  signed int LastError; // ebx
  unsigned __int64 v12; // rsi
  __int64 v13; // rax
  signed int SingleStringAttr; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rdi
  wchar_t *v17; // rax
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  unsigned __int64 v20; // rdi
  void *v21; // rax
  WCHAR *v22; // rsi
  WCHAR *v23; // r9
  ULONG v24; // eax
  int v25; // edi
  LDAPMessage *entry; // rax
  unsigned __int16 *v27; // rdi
  LDAPMessage *v28; // r12
  PWCHAR *valuesW; // rax
  const void **v30; // r15
  const wchar_t **v31; // rsi
  unsigned int v32; // r9d
  unsigned __int64 v33; // r14
  unsigned __int16 *v34; // rax
  PWCHAR *v35; // rax
  int v36; // eax
  int v37; // r8d
  unsigned __int16 **v38; // r9
  bool v39; // zf
  int v40; // eax
  int attrs; // [rsp+20h] [rbp-B9h]
  WCHAR *base; // [rsp+68h] [rbp-71h]
  int v45; // [rsp+70h] [rbp-69h] BYREF
  int v46; // [rsp+74h] [rbp-65h]
  __int64 v47; // [rsp+78h] [rbp-61h] BYREF
  PLDAPMessage res; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int16 *v49; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int64 v50; // [rsp+90h] [rbp-49h] BYREF
  void *lpMem; // [rsp+98h] [rbp-41h]
  unsigned __int16 *v52; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int64 v53; // [rsp+A8h] [rbp-31h] BYREF
  LDAP *lda; // [rsp+B0h] [rbp-29h]
  unsigned __int16 **v55; // [rsp+B8h] [rbp-21h]
  int *v56; // [rsp+C0h] [rbp-19h]
  PWSTR v57[2]; // [rsp+C8h] [rbp-11h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-1h]

  v56 = a4;
  v55 = a3;
  v58 = 0;
  v4 = a2;
  lda = ld;
  v6 = 0;
  v47 = 0;
  lpMem = 0;
  v7 = 0;
  base = 0;
  v8 = a2;
  *(_OWORD *)v57 = 0;
  res = 0;
  v46 = 0;
  v45 = 0;
  v49 = a2;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids, a2);
  v9 = -1;
  if ( v4 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v4[v13] );
    v12 = 2 * v13;
  }
  else
  {
    DomainControllerInfo = GetDomainControllerInfo(1, 0, 0, &v49, &v50, &v52, &v53, &v45);
    LastError = DomainControllerInfo;
    if ( DomainControllerInfo < 0 )
    {
      SidKeyDebugTraceError(
        DomainControllerInfo,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
        0x148u);
      goto LABEL_59;
    }
    v12 = v50;
    v8 = v49;
    v46 = v45;
  }
  SingleStringAttr = GetSingleStringAttr(ld, (PWSTR)L"defaultNamingContext", attrs, (__int64)&v47);
  LastError = SingleStringAttr;
  if ( SingleStringAttr >= 0 )
  {
    v6 = (void *)v47;
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v47 + 2 * v15) );
    v16 = 2 * v15 + 46;
    v17 = (wchar_t *)SIDKeyProvAlloc(v16);
    base = v17;
    if ( !v17 )
    {
      v18 = 358;
LABEL_17:
      LastError = -2147024882;
      v19 = -2147024882;
LABEL_18:
      SidKeyDebugTraceError(v19, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v18);
LABEL_57:
      v4 = a2;
      goto LABEL_58;
    }
    if ( swprintf_s(v17, v16 >> 1, L"%s%s", L"OU=Domain Controllers,", v6) < 0 )
    {
      v18 = 370;
LABEL_21:
      LastError = -2147467259;
      v19 = -2147467259;
      goto LABEL_18;
    }
    v20 = v12 + 26;
    v21 = SIDKeyProvAlloc(v12 + 26);
    lpMem = v21;
    v22 = (WCHAR *)v21;
    if ( !v21 )
    {
      v18 = 379;
      goto LABEL_17;
    }
    if ( swprintf_s((wchar_t *const)v21, v20 >> 1, L"dNSHostName=%s", v8) < 0 )
    {
      v18 = 391;
      goto LABEL_21;
    }
    v58 = 0;
    v57[0] = (PWSTR)L"distinguishedName";
    v23 = v22;
    v7 = base;
    v57[1] = (PWSTR)L"msDS-isRODC";
    v24 = ldap_search_ext_sW(ld, base, 2u, v23, v57, 0, 0, 0, 0, 0, &res);
    v25 = v24;
    if ( v24 )
    {
      SidKeyDebugTraceError(v24, "ulReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x19Fu);
      if ( v25 <= 0 )
      {
        LastError = v25;
LABEL_31:
        v4 = a2;
        goto LABEL_59;
      }
      LastError = (unsigned __int16)v25;
LABEL_30:
      LastError |= 0x80070000;
      goto LABEL_31;
    }
    entry = ldap_first_entry(ld, res);
    v27 = 0;
    v28 = entry;
    if ( !entry )
    {
      SidKeyDebugTraceError(
        0x20u,
        "LDAP_NO_SUCH_OBJECT",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
        0x1A7u);
      LastError = -2147024864;
      goto LABEL_31;
    }
    valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"distinguishedName");
    v30 = (const void **)valuesW;
    if ( !valuesW )
    {
      LastError = LdapGetLastError();
      SidKeyDebugTraceError(
        LastError,
        "ulReturn",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
        0x1B1u);
      if ( LastError <= 0 )
        goto LABEL_31;
      LastError = (unsigned __int16)LastError;
      goto LABEL_30;
    }
    v31 = 0;
    if ( ldap_count_valuesW(valuesW) )
    {
      do
        ++v9;
      while ( *((_WORD *)*v30 + v9) );
      v33 = 2 * v9 + 2;
      v34 = (unsigned __int16 *)SIDKeyProvAlloc(v33);
      v27 = v34;
      if ( !v34 )
      {
        LastError = -2147024882;
        SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x1C3u);
        goto LABEL_53;
      }
      memcpy_0(v34, *v30, v33);
      v35 = ldap_get_valuesW(lda, v28, (const PWSTR)L"msDS-isRODC");
      v31 = (const wchar_t **)v35;
      if ( !v35 )
      {
        LastError = LdapGetLastError();
        SidKeyDebugTraceError(
          LastError,
          "ulReturn",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
          0x1CDu);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_53;
      }
      if ( ldap_count_valuesW(v35) )
      {
        v36 = wcscmp_0(*v31, L"TRUE");
        v38 = v55;
        v39 = v36 == 0;
        v40 = v46;
        if ( v39 )
          v40 = 1;
        *v55 = v27;
        v27 = 0;
        *v56 = v40;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v37, (unsigned int)*v38, v40);
        goto LABEL_53;
      }
      v32 = 469;
    }
    else
    {
      v32 = 441;
    }
    SidKeyDebugTraceError(
      0x10u,
      "LDAP_NO_SUCH_ATTRIBUTE",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
      v32);
    LastError = -2147024880;
LABEL_53:
    ldap_value_freeW((PWCHAR *)v30);
    if ( v31 )
      ldap_value_freeW((PWCHAR *)v31);
    if ( v27 )
      SIDKeyProvFree(v27);
    goto LABEL_57;
  }
  SidKeyDebugTraceError(SingleStringAttr, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x15Bu);
  v6 = (void *)v47;
LABEL_58:
  v7 = base;
LABEL_59:
  if ( res )
    ldap_msgfree(res);
  if ( v7 )
    SIDKeyProvFree(v7);
  if ( lpMem )
    SIDKeyProvFree(lpMem);
  if ( v6 )
    SIDKeyProvFree(v6);
  if ( v4 && v49 != v4 )
    SIDKeyProvFree(v49);
  if ( v52 )
    SIDKeyProvFree(v52);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180002bf0  push    rbp
0x180002bf2  push    rbx
0x180002bf3  push    rsi
0x180002bf4  push    rdi
0x180002bf5  push    r12
0x180002bf7  push    r13
0x180002bf9  push    r14
0x180002bfb  push    r15
0x180002bfd  lea     rbp, [rsp-1Fh]
0x180002c02  sub     rsp, 0F8h
0x180002c09  mov     rax, cs:__security_cookie
0x180002c10  xor     rax, rsp
0x180002c13  mov     [rbp+57h+var_50], rax
0x180002c17  xor     ebx, ebx
0x180002c19  mov     [rbp+57h+var_70], r9
0x180002c1d  xor     eax, eax
0x180002c1f  mov     [rbp+57h+var_78], r8
0x180002c23  xorps   xmm0, xmm0
0x180002c26  mov     [rbp+57h+var_58], rax
0x180002c2a  mov     rdi, rdx
0x180002c2d  mov     [rbp+57h+var_D0], rdx
0x180002c31  mov     r15, rcx
0x180002c34  mov     [rbp+57h+ld], rcx
0x180002c38  mov     r13d, ebx
0x180002c3b  mov     [rbp+57h+var_B8], rbx
0x180002c3f  mov     [rbp+57h+lpMem], rbx
0x180002c43  mov     esi, ebx
0x180002c45  mov     [rbp+57h+base], rbx
0x180002c49  mov     r12, rdx
0x180002c4c  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180002c50  mov     [rbp+57h+var_B0], rbx
0x180002c54  mov     [rbp+57h+var_BC], ebx
0x180002c57  mov     [rbp+57h+var_C0], ebx
0x180002c5a  mov     [rbp+57h+var_A8], rdx
0x180002c5e  mov     [rbp+57h+var_A0], rbx
0x180002c62  mov     [rbp+57h+var_90], rbx
0x180002c66  mov     [rbp+57h+var_88], rbx
0x180002c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c71  lea     rax, WPP_GLOBAL_Control
0x180002c78  cmp     rcx, rax
0x180002c7b  jz      short loc_180002C99
0x180002c7d  test    byte ptr [rcx+1Ch], 4
0x180002c81  jz      short loc_180002C99
0x180002c83  mov     rcx, [rcx+10h]
0x180002c87  lea     edx, [rbx+0Dh]
0x180002c8a  mov     r9, r12
0x180002c8d  lea     r8, WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids
0x180002c94  call    WPP_SF_S
0x180002c99  or      r14, 0FFFFFFFFFFFFFFFFh
0x180002c9d  test    rdi, rdi
0x180002ca0  jnz     short loc_180002D0D
0x180002ca2  lea     rax, [rbp+57h+var_C0]
0x180002ca6  xor     r8d, r8d; unsigned __int16 *
0x180002ca9  mov     [rsp+130h+ClientControls], rax; int *
0x180002cae  lea     r9, [rbp+57h+var_A8]; unsigned __int16 **
0x180002cb2  lea     rax, [rbp+57h+var_88]
0x180002cb6  xor     edx, edx; int
0x180002cb8  mov     [rsp+130h+ServerControls], rax; unsigned __int64 *
0x180002cbd  lea     ecx, [rdi+1]; int
0x180002cc0  lea     rax, [rbp+57h+var_90]
0x180002cc4  mov     qword ptr [rsp+130h+attrsonly], rax; unsigned __int16 **
0x180002cc9  lea     rax, [rbp+57h+var_A0]
0x180002ccd  mov     [rsp+130h+attrs], rax; unsigned __int64 *
0x180002cd2  call    ?GetDomainControllerInfo@@YAJHHPEBGPEAPEAGPEA_K12PEAH@Z; GetDomainControllerInfo(int,int,ushort const *,ushort * *,unsigned __int64 *,ushort * *,unsigned __int64 *,int *)
0x180002cd7  mov     ebx, eax
0x180002cd9  test    eax, eax
0x180002cdb  jns     short loc_180002CFD
0x180002cdd  mov     r9d, 148h; unsigned int
0x180002ce3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002cea  lea     rdx, aHr; "hr"
0x180002cf1  mov     ecx, eax; unsigned int
0x180002cf3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002cf8  jmp     loc_1800030D2
0x180002cfd  mov     eax, [rbp+57h+var_C0]
0x180002d00  mov     rsi, [rbp+57h+var_A0]
0x180002d04  mov     r12, [rbp+57h+var_A8]
0x180002d08  mov     [rbp+57h+var_BC], eax
0x180002d0b  jmp     short loc_180002D1D
0x180002d0d  mov     rax, r14
0x180002d10  inc     rax
0x180002d13  cmp     [rdi+rax*2], bx
0x180002d17  jnz     short loc_180002D10
0x180002d19  lea     rsi, [rax+rax]
0x180002d1d  lea     rax, [rbp+57h+var_B8]
0x180002d21  mov     rcx, r15; ld
0x180002d24  lea     rdx, aDefaultnamingc; "defaultNamingContext"
0x180002d2b  mov     qword ptr [rsp+130h+attrsonly], rax; __int64
0x180002d30  call    GetSingleStringAttr
0x180002d35  xor     ecx, ecx
0x180002d37  mov     ebx, eax
0x180002d39  test    eax, eax
0x180002d3b  jns     short loc_180002D61
0x180002d3d  mov     r9d, 15Bh; unsigned int
0x180002d43  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002d4a  lea     rdx, aHr; "hr"
0x180002d51  mov     ecx, eax; unsigned int
0x180002d53  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002d58  mov     r13, [rbp+57h+var_B8]
0x180002d5c  jmp     loc_1800030CE
0x180002d61  mov     r13, [rbp+57h+var_B8]
0x180002d65  mov     rax, r14
0x180002d68  inc     rax
0x180002d6b  cmp     [r13+rax*2+0], cx
0x180002d71  jnz     short loc_180002D68
0x180002d73  lea     rdi, ds:2Eh[rax*2]
0x180002d7b  mov     rcx, rdi; unsigned __int64
0x180002d7e  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002d83  mov     [rbp+57h+base], rax
0x180002d87  test    rax, rax
0x180002d8a  jnz     short loc_180002DB4
0x180002d8c  mov     r9d, 166h; unsigned int
0x180002d92  mov     ebx, 8007000Eh
0x180002d97  mov     ecx, 8007000Eh; unsigned int
0x180002d9c  lea     rdx, aHr; "hr"
0x180002da3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002daa  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002daf  jmp     loc_1800030CA
0x180002db4  shr     rdi, 1
0x180002db7  lea     r9, aOuDomainContro; "OU=Domain Controllers,"
0x180002dbe  mov     rdx, rdi; BufferCount
0x180002dc1  mov     [rsp+130h+attrs], r13
0x180002dc6  lea     r8, aSS; "%s%s"
0x180002dcd  mov     rcx, rax; Buffer
0x180002dd0  call    swprintf_s
0x180002dd5  test    eax, eax
0x180002dd7  jns     short loc_180002DEB
0x180002dd9  mov     r9d, 172h
0x180002ddf  mov     ebx, 80004005h
0x180002de4  mov     ecx, 80004005h
0x180002de9  jmp     short loc_180002D9C
0x180002deb  lea     rdi, [rsi+1Ah]
0x180002def  mov     rcx, rdi; unsigned __int64
0x180002df2  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002df7  mov     [rbp+57h+lpMem], rax
0x180002dfb  mov     rsi, rax
0x180002dfe  test    rax, rax
0x180002e01  jnz     short loc_180002E0B
0x180002e03  mov     r9d, 17Bh
0x180002e09  jmp     short loc_180002D92
0x180002e0b  shr     rdi, 1
0x180002e0e  lea     r8, aDnshostnameS; "dNSHostName=%s"
0x180002e15  mov     rdx, rdi; BufferCount
0x180002e18  mov     r9, r12
0x180002e1b  mov     rcx, rsi; Buffer
0x180002e1e  call    swprintf_s
0x180002e23  xor     ecx, ecx
0x180002e25  test    eax, eax
0x180002e27  jns     short loc_180002E31
0x180002e29  mov     r9d, 187h
0x180002e2f  jmp     short loc_180002DDF
0x180002e31  lea     rax, attr; "distinguishedName"
0x180002e38  mov     [rbp+57h+var_58], rcx
0x180002e3c  mov     [rbp+57h+var_68], rax
0x180002e40  mov     r9, rsi; filter
0x180002e43  mov     rsi, [rbp+57h+base]
0x180002e47  lea     rax, aMsdsIsrodc; "msDS-isRODC"
0x180002e4e  mov     [rbp+57h+var_68+8], rax
0x180002e52  mov     r8d, 2; scope
0x180002e58  lea     rax, [rbp+57h+var_B0]
0x180002e5c  mov     rdx, rsi; base
0x180002e5f  mov     [rsp+130h+res], rax; res
0x180002e64  lea     rax, [rbp+57h+var_68]
0x180002e68  mov     [rsp+130h+SizeLimit], ecx; SizeLimit
0x180002e6c  mov     [rsp+130h+timeout], rcx; timeout
0x180002e71  mov     [rsp+130h+ClientControls], rcx; ClientControls
0x180002e76  mov     [rsp+130h+ServerControls], rcx; ServerControls
0x180002e7b  mov     [rsp+130h+attrsonly], ecx; attrsonly
0x180002e7f  mov     rcx, r15; ld
0x180002e82  mov     [rsp+130h+attrs], rax; attrs
0x180002e87  call    cs:__imp_ldap_search_ext_sW
0x180002e8d  mov     edi, eax
0x180002e8f  test    eax, eax
0x180002e91  jz      short loc_180002EC8
0x180002e93  mov     r9d, 19Fh; unsigned int
0x180002e99  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002ea0  lea     rdx, aUlreturn; "ulReturn"
0x180002ea7  mov     ecx, eax; unsigned int
0x180002ea9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002eae  test    edi, edi
0x180002eb0  jg      short loc_180002EB6
0x180002eb2  mov     ebx, edi
0x180002eb4  jmp     short loc_180002EBF
0x180002eb6  movzx   ebx, di
0x180002eb9  or      ebx, 80070000h
0x180002ebf  mov     rdi, [rbp+57h+var_D0]
0x180002ec3  jmp     loc_1800030D2
0x180002ec8  mov     rdx, [rbp+57h+var_B0]; res
0x180002ecc  mov     rcx, r15; ld
0x180002ecf  call    cs:__imp_ldap_first_entry
0x180002ed5  xor     edi, edi
0x180002ed7  mov     r12, rax
0x180002eda  test    rax, rax
0x180002edd  jnz     short loc_180002F02
0x180002edf  mov     r9d, 1A7h; unsigned int
0x180002ee5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002eec  lea     rdx, aLdapNoSuchObje; "LDAP_NO_SUCH_OBJECT"
0x180002ef3  lea     ecx, [rax+20h]; unsigned int
0x180002ef6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002efb  mov     ebx, 80070020h
0x180002f00  jmp     short loc_180002EBF
0x180002f02  lea     r8, attr; "distinguishedName"
0x180002f09  mov     rdx, r12; entry
0x180002f0c  mov     rcx, r15; ld
0x180002f0f  call    cs:__imp_ldap_get_valuesW
0x180002f15  mov     r15, rax
0x180002f18  test    rax, rax
0x180002f1b  jnz     short loc_180002F50
0x180002f1d  call    cs:__imp_LdapGetLastError
0x180002f23  mov     r9d, 1B1h; unsigned int
0x180002f29  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002f30  mov     ecx, eax; unsigned int
0x180002f32  lea     rdx, aUlreturn; "ulReturn"
0x180002f39  mov     ebx, eax
0x180002f3b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002f40  test    ebx, ebx
0x180002f42  jle     loc_180002EBF
0x180002f48  movzx   ebx, bx
0x180002f4b  jmp     loc_180002EB9
0x180002f50  mov     rcx, r15; vals
0x180002f53  mov     rsi, rdi
0x180002f56  call    cs:__imp_ldap_count_valuesW
0x180002f5c  cmp     eax, 1
0x180002f5f  jnb     short loc_180002F89
0x180002f61  mov     r9d, 1B9h; unsigned int
0x180002f67  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002f6e  mov     ecx, 10h; unsigned int
0x180002f73  lea     rdx, aLdapNoSuchAttr; "LDAP_NO_SUCH_ATTRIBUTE"
0x180002f7a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002f7f  mov     ebx, 80070010h
0x180002f84  jmp     loc_1800030A6
0x180002f89  mov     rax, [r15]
0x180002f8c  inc     r14
0x180002f8f  cmp     [rax+r14*2], di
0x180002f94  jnz     short loc_180002F8C
0x180002f96  lea     r14, ds:2[r14*2]
0x180002f9e  mov     rcx, r14; unsigned __int64
0x180002fa1  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002fa6  mov     rdi, rax
0x180002fa9  test    rax, rax
0x180002fac  jnz     short loc_180002FD6
0x180002fae  mov     r9d, 1C3h; unsigned int
0x180002fb4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002fbb  lea     rdx, aHr; "hr"
0x180002fc2  mov     ecx, 8007000Eh; unsigned int
0x180002fc7  mov     ebx, 8007000Eh
0x180002fcc  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002fd1  jmp     loc_1800030A6
0x180002fd6  mov     rdx, [r15]; Src
0x180002fd9  mov     r8, r14; Size
0x180002fdc  mov     rcx, rdi; void *
0x180002fdf  call    memcpy_0
0x180002fe4  mov     rcx, [rbp+57h+ld]; ld
0x180002fe8  lea     r8, aMsdsIsrodc; "msDS-isRODC"
0x180002fef  mov     rdx, r12; entry
0x180002ff2  call    cs:__imp_ldap_get_valuesW
0x180002ff8  mov     rsi, rax
0x180002ffb  test    rax, rax
0x180002ffe  jnz     short loc_180003032
0x180003000  call    cs:__imp_LdapGetLastError
0x180003006  mov     r9d, 1CDh; unsigned int
0x18000300c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003013  mov     ecx, eax; unsigned int
0x180003015  lea     rdx, aUlreturn; "ulReturn"
0x18000301c  mov     ebx, eax
0x18000301e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003023  test    ebx, ebx
0x180003025  jle     short loc_1800030A6
0x180003027  movzx   ebx, bx
0x18000302a  or      ebx, 80070000h
0x180003030  jmp     short loc_1800030A6
0x180003032  mov     rcx, rsi; vals
0x180003035  call    cs:__imp_ldap_count_valuesW
0x18000303b  mov     r14d, 1
0x180003041  cmp     eax, r14d
0x180003044  jnb     short loc_180003051
0x180003046  mov     r9d, 1D5h
0x18000304c  jmp     loc_180002F67
0x180003051  mov     rcx, [rsi]; String1
0x180003054  lea     rdx, aTrue; "TRUE"
0x18000305b  call    wcscmp_0
0x180003060  mov     r9, [rbp+57h+var_78]
0x180003064  xor     ecx, ecx
0x180003066  test    eax, eax
0x180003068  mov     eax, [rbp+57h+var_BC]
0x18000306b  cmovz   eax, r14d
0x18000306f  mov     [r9], rdi
0x180003072  mov     edi, ecx
0x180003074  mov     rcx, [rbp+57h+var_70]
0x180003078  mov     [rcx], eax
0x18000307a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003081  lea     rdx, WPP_GLOBAL_Control
0x180003088  cmp     rcx, rdx
0x18000308b  jz      short loc_1800030A6
0x18000308d  test    byte ptr [rcx+1Ch], 4
0x180003091  jz      short loc_1800030A6
0x180003093  mov     r9, [r9]
0x180003096  lea     edx, [rdi+0Eh]
0x180003099  mov     rcx, [rcx+10h]
0x18000309d  mov     dword ptr [rsp+130h+attrs], eax
0x1800030a1  call    WPP_SF_Sd
  ... truncated ...
```
