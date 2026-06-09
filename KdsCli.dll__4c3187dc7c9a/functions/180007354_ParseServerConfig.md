# ParseServerConfig

- ea: `0x180007354`
- end: `0x180007a03`
- name: `ParseServerConfig`
- size: `1711`
- prototype: `__int64 __fastcall(LDAP *ld, LDAPMessage *entry, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000713c`

## callees

- `0x180003e70`
- `0x180006d10`
- `0x180007354`
- `0x180007b60`
- `0x18000fcbc`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a694`
- `0x18001a6ac`

## import_xrefs

- `WLDAP32!__imp_ldap_value_free_len` at `0x1800077d7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800079e3`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800077d7`
- `WLDAP32!__imp_ldap_value_free_len` at `0x1800079e3`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18000742c`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x18000742c`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x1800073c4`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x1800073c4`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000741b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000741b`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800074e4`
- `WLDAP32!__imp_ldap_get_values_lenW` at `0x1800074e4`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800077e9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000797b`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800077e9`
- `WLDAP32!__imp_ldap_memfreeW` at `0x18000797b`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x1800074af`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x1800074af`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800077c1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000796d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800077c1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18000796d`
- `WLDAP32!__imp_ber_free` at `0x18000798d`
- `WLDAP32!__imp_ber_free` at `0x18000798d`

## string_xrefs

- `0x1800075b7`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x180007815`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x18000785e`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall ParseServerConfig(LDAP *ld, LDAPMessage *entry, unsigned int *a3)
{
  unsigned int v4; // edi
  void *v5; // rbx
  void *v6; // r13
  unsigned int v7; // esi
  int v8; // ebp
  LDAPMessage *v9; // r12
  WCHAR *attributeW; // r15
  PWCHAR *valuesW; // rax
  PWCHAR *v12; // r12
  __int64 v13; // rax
  int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  struct berval **values_lenW; // rax
  unsigned int v18; // ebx
  void *v19; // rax
  size_t v20; // r8
  const WCHAR *v21; // rdx
  void *v22; // rcx
  signed int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // ebx
  unsigned int v26; // r9d
  unsigned int v27; // edi
  unsigned int v28; // ebx
  const wchar_t *v29; // rcx
  bool v30; // zf
  unsigned int v31; // ecx
  char *v32; // rbp
  void *v33; // rdx
  const void *v34; // rax
  char *v35; // rsi
  void *v36; // rdx
  void *v38; // [rsp+20h] [rbp-88h]
  size_t Size; // [rsp+28h] [rbp-80h]
  const WCHAR *Src; // [rsp+30h] [rbp-78h]
  size_t v41; // [rsp+38h] [rbp-70h]
  unsigned int v42; // [rsp+40h] [rbp-68h]
  unsigned __int8 **v43; // [rsp+48h] [rbp-60h]
  struct berval **vals; // [rsp+50h] [rbp-58h]
  BerElement *ptr; // [rsp+58h] [rbp-50h] BYREF
  void *lpMem; // [rsp+60h] [rbp-48h]
  void *v47; // [rsp+68h] [rbp-40h]
  unsigned int v50; // [rsp+C8h] [rbp+20h]

  v4 = 0;
  ptr = 0;
  v43 = 0;
  v5 = 0;
  Src = 0;
  v6 = 0;
  Size = 0;
  v7 = 0;
  lpMem = 0;
  v8 = 0;
  v50 = 0;
  v9 = entry;
  v38 = 0;
  v41 = 0;
  v47 = 0;
  v42 = 0;
  attributeW = ldap_first_attributeW(ld, entry, &ptr);
  if ( attributeW )
  {
    while ( 1 )
    {
      if ( !wcscmp_0(attributeW, L"msKds-SecretAgreementParam") || !wcscmp_0(attributeW, L"msKds-KDFParam") )
      {
        v12 = 0;
        values_lenW = ldap_get_values_lenW(ld, entry, attributeW);
        vals = values_lenW;
        if ( !values_lenW )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v16 = 10;
LABEL_13:
            WPP_SF_S(v15[2], v16, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids, attributeW);
          }
LABEL_14:
          v5 = v38;
          goto LABEL_15;
        }
        v43 = (unsigned __int8 **)*values_lenW;
        if ( !*values_lenW )
        {
          v4 = -2147024880;
          SidKeyDebugTraceError(
            0x80070010,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx",
            0xF2u);
          goto LABEL_99;
        }
        v14 = Size;
      }
      else
      {
        vals = 0;
        valuesW = ldap_get_valuesW(ld, v9, attributeW);
        v12 = valuesW;
        if ( !valuesW || !ldap_count_valuesW(valuesW) )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v16 = 11;
            goto LABEL_13;
          }
          goto LABEL_14;
        }
        Src = *v12;
        if ( !*v12 )
          goto LABEL_14;
        v13 = -1;
        do
          ++v13;
        while ( (*v12)[v13] );
        v14 = 2 * v13 + 2;
        Size = 2 * v13 + 2;
      }
      if ( !wcscmp_0(attributeW, L"msKds-KDFAlgorithmID") )
        break;
      if ( !wcscmp_0(attributeW, L"msKds-KDFParam") )
      {
        v23 = ValidateKDFParam(v43[1], *(_DWORD *)v43);
        v4 = 0;
        if ( v23 < 0 )
        {
          SidKeyDebugTraceError(
            v23,
            "hr",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx",
            0x129u);
          a3[18] = 0;
          *((_QWORD *)a3 + 10) = L"msKds-KDFParam";
        }
        if ( !a3[18] && !v8 )
        {
          if ( (Microsoft_Windows_KdsSvcEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(v24, KdsSvcInvalidSrvConfig, attributeW);
          v8 = 1;
        }
        LODWORD(v41) = *(_DWORD *)v43;
        v25 = *(_DWORD *)v43 + v7;
        if ( v25 < v7 )
        {
          v26 = 311;
          goto LABEL_72;
        }
        v38 = SIDKeyProvAlloc(*(unsigned int *)v43);
        if ( !v38 )
        {
          v26 = 321;
LABEL_75:
          v4 = -2147024882;
          v31 = -2147024882;
LABEL_73:
          SidKeyDebugTraceError(v31, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", v26);
          goto LABEL_97;
        }
        v7 = v25;
        v5 = v38;
        memcpy_0(v38, v43[1], *(unsigned int *)v43);
        goto LABEL_65;
      }
      if ( !wcscmp_0(attributeW, L"msKds-SecretAgreementAlgorithmID") )
      {
        HIDWORD(v41) = v14;
        v18 = v7 + v14;
        if ( v18 < v7 )
        {
          v26 = 333;
          goto LABEL_72;
        }
        v19 = SIDKeyProvAlloc(Size);
        v47 = v19;
        if ( !v19 )
        {
          v26 = 341;
          goto LABEL_75;
        }
        goto LABEL_26;
      }
      if ( !wcscmp_0(attributeW, L"msKds-SecretAgreementParam") )
      {
        v42 = *(_DWORD *)v43;
        v27 = *(_DWORD *)v43 + v7;
        if ( v27 < v7 )
        {
          v26 = 353;
          goto LABEL_72;
        }
        v28 = *(_DWORD *)v43;
        v6 = SIDKeyProvAlloc(*(unsigned int *)v43);
        if ( !v6 )
        {
          v26 = 361;
          goto LABEL_75;
        }
        v7 = v27;
        v20 = v28;
        v22 = v6;
        v21 = (const WCHAR *)v43[1];
        goto LABEL_27;
      }
      if ( !wcscmp_0(attributeW, L"msKds-PrivateKeyLength") )
      {
        v4 = ConvertStrToUlong(Src, a3 + 13);
        if ( !a3[13] )
        {
          v29 = L"msKds-PrivateKeyLength";
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      if ( !wcscmp_0(attributeW, L"msKds-PublicKeyLength") )
      {
        v4 = ConvertStrToUlong(Src, a3 + 14);
        if ( !a3[14] )
        {
          v29 = L"msKds-PublicKeyLength";
LABEL_50:
          a3[18] = 0;
          *((_QWORD *)a3 + 10) = v29;
        }
LABEL_51:
        v30 = a3[18] == 0;
LABEL_59:
        if ( v30 && !v8 )
        {
          if ( (Microsoft_Windows_KdsSvcEnableBits & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(v29, KdsSvcInvalidSrvConfig, attributeW);
          v8 = 1;
        }
        goto LABEL_64;
      }
      if ( !wcscmp_0(attributeW, L"msKds-Version") )
      {
        v4 = ConvertStrToUlong(Src, a3);
        if ( *a3 != 1 )
        {
          a3[18] = 0;
          *((_QWORD *)a3 + 10) = L"msKds-Version";
        }
        v30 = a3[18] == 0;
        goto LABEL_59;
      }
LABEL_64:
      v5 = v38;
LABEL_65:
      if ( v12 )
      {
        ldap_value_freeW(v12);
        v12 = 0;
      }
      if ( vals )
      {
        ldap_value_free_len(vals);
        vals = 0;
      }
      ldap_memfreeW(attributeW);
LABEL_15:
      attributeW = ldap_next_attributeW(ld, entry, ptr);
      if ( !attributeW )
        goto LABEL_82;
      v9 = entry;
    }
    v50 = v14;
    v18 = v7 + v14;
    if ( v18 < v7 )
    {
      v26 = 274;
LABEL_72:
      v4 = -2147024362;
      v31 = -2147024362;
      goto LABEL_73;
    }
    v19 = SIDKeyProvAlloc(Size);
    lpMem = v19;
    if ( !v19 )
    {
      v4 = -2147024882;
      goto LABEL_97;
    }
LABEL_26:
    v20 = Size;
    v7 = v18;
    v21 = Src;
    v22 = v19;
LABEL_27:
    v4 = 0;
    memcpy_0(v22, v21, v20);
    goto LABEL_64;
  }
  vals = 0;
  v12 = 0;
LABEL_82:
  v32 = (char *)SIDKeyProvAlloc(v7);
  if ( !v32 )
  {
    v26 = 452;
    goto LABEL_75;
  }
  if ( lpMem )
  {
    v33 = lpMem;
    *((_QWORD *)a3 + 1) = v32;
    memcpy_0(v32, v33, v50);
    v34 = v38;
    v35 = &v32[v50];
    if ( !v38 )
    {
      *((_QWORD *)a3 + 2) = 0;
      a3[6] = 0;
      goto LABEL_90;
    }
  }
  else
  {
    v35 = v32;
    if ( !v5 )
      goto LABEL_90;
    v34 = v38;
  }
  a3[6] = v41;
  *((_QWORD *)a3 + 2) = v35;
  memcpy_0(v35, v34, (unsigned int)v41);
  v35 += (unsigned int)v41;
LABEL_90:
  if ( !v47 )
  {
    if ( !v6 )
      goto LABEL_96;
LABEL_95:
    *((_QWORD *)a3 + 5) = v35;
    memcpy_0(v35, v6, v42);
    a3[12] = v42;
    goto LABEL_96;
  }
  v36 = v47;
  *((_QWORD *)a3 + 4) = v35;
  memcpy_0(v35, v36, HIDWORD(v41));
  if ( v6 )
  {
    v35 += HIDWORD(v41);
    goto LABEL_95;
  }
  *((_QWORD *)a3 + 5) = 0;
  a3[12] = 0;
LABEL_96:
  *((_QWORD *)a3 + 8) = v32;
LABEL_97:
  if ( v12 )
    ldap_value_freeW(v12);
LABEL_99:
  if ( attributeW )
    ldap_memfreeW(attributeW);
  if ( ptr )
    ber_free(ptr, 0);
  if ( v6 )
    SIDKeyProvFree(v6);
  if ( lpMem )
    SIDKeyProvFree(lpMem);
  if ( v38 )
    SIDKeyProvFree(v38);
  if ( v47 )
    SIDKeyProvFree(v47);
  if ( vals )
    ldap_value_free_len(vals);
  return v4;
}

```

## disassembly

```asm
0x180007354  mov     r11, rsp
0x180007357  mov     [r11+18h], rbx
0x18000735b  mov     [r11+10h], rdx
0x18000735f  mov     [r11+8], rcx
0x180007363  push    rbp
0x180007364  push    rsi
0x180007365  push    rdi
0x180007366  push    r12
0x180007368  push    r13
0x18000736a  push    r14
0x18000736c  push    r15
0x18000736e  sub     rsp, 70h
0x180007372  mov     rax, rcx
0x180007375  mov     r14, r8
0x180007378  xor     ecx, ecx
0x18000737a  lea     r8, [r11-50h]; ptr
0x18000737e  mov     edi, ecx
0x180007380  mov     [r11-50h], rcx
0x180007384  mov     [rsp+0A8h+var_60], rcx
0x180007389  mov     ebx, ecx
0x18000738b  mov     [rsp+0A8h+Src], rcx
0x180007390  mov     r13d, ecx
0x180007393  mov     [rsp+0A8h+Size], rcx
0x180007398  mov     esi, ecx
0x18000739a  mov     [rsp+0A8h+lpMem], rcx
0x18000739f  mov     ebp, ecx
0x1800073a1  mov     dword ptr [rsp+0A8h+arg_18], ecx
0x1800073a8  mov     r12, rdx
0x1800073ab  mov     [rsp+0A8h+var_88], rcx
0x1800073b0  mov     dword ptr [rsp+0A8h+var_70], ecx
0x1800073b4  mov     [rsp+0A8h+var_40], rcx
0x1800073b9  mov     dword ptr [rsp+0A8h+var_70+4], ecx
0x1800073bd  mov     dword ptr [rsp+0A8h+var_68], ecx
0x1800073c1  mov     rcx, rax; ld
0x1800073c4  call    cs:__imp_ldap_first_attributeW
0x1800073ca  mov     r15, rax
0x1800073cd  xor     eax, eax
0x1800073cf  test    r15, r15
0x1800073d2  jz      loc_180007882
0x1800073d8  lea     rdx, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x1800073df  mov     rcx, r15; String1
0x1800073e2  call    wcscmp_0
0x1800073e7  xor     ebx, ebx
0x1800073e9  test    eax, eax
0x1800073eb  jz      loc_1800074CE
0x1800073f1  lea     rdx, aMskdsKdfparam; "msKds-KDFParam"
0x1800073f8  mov     rcx, r15; String1
0x1800073fb  call    wcscmp_0
0x180007400  test    eax, eax
0x180007402  jz      loc_1800074CE
0x180007408  mov     rcx, [rsp+0A8h+ld]; ld
0x180007410  mov     r8, r15; attr
0x180007413  mov     rdx, r12; entry
0x180007416  mov     [rsp+0A8h+vals], rbx
0x18000741b  call    cs:__imp_ldap_get_valuesW
0x180007421  mov     r12, rax
0x180007424  test    rax, rax
0x180007427  jz      short loc_180007464
0x180007429  mov     rcx, rax; vals
0x18000742c  call    cs:__imp_ldap_count_valuesW
0x180007432  cmp     eax, 1
0x180007435  jb      short loc_180007464
0x180007437  mov     rcx, [r12]
0x18000743b  mov     [rsp+0A8h+Src], rcx
0x180007440  test    rcx, rcx
0x180007443  jz      short loc_180007495
0x180007445  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007449  inc     rax
0x18000744c  cmp     [rcx+rax*2], bx
0x180007450  jnz     short loc_180007449
0x180007452  lea     rbx, ds:2[rax*2]
0x18000745a  mov     [rsp+0A8h+Size], rbx
0x18000745f  jmp     loc_18000752D
0x180007464  mov     rcx, cs:WPP_GLOBAL_Control
0x18000746b  lea     rax, WPP_GLOBAL_Control
0x180007472  cmp     rcx, rax
0x180007475  jz      short loc_180007495
0x180007477  test    byte ptr [rcx+1Ch], 4
0x18000747b  jz      short loc_180007495
0x18000747d  mov     edx, 0Bh
0x180007482  mov     rcx, [rcx+10h]
0x180007486  lea     r8, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids
0x18000748d  mov     r9, r15
0x180007490  call    WPP_SF_S
0x180007495  mov     rbx, [rsp+0A8h+var_88]
0x18000749a  mov     r8, [rsp+0A8h+ptr]; ptr
0x18000749f  mov     rdx, [rsp+0A8h+entry]; entry
0x1800074a7  mov     rcx, [rsp+0A8h+ld]; ld
0x1800074af  call    cs:__imp_ldap_next_attributeW
0x1800074b5  mov     r15, rax
0x1800074b8  test    rax, rax
0x1800074bb  jz      loc_18000788A
0x1800074c1  mov     r12, [rsp+0A8h+entry]
0x1800074c9  jmp     loc_1800073D8
0x1800074ce  mov     rdx, [rsp+0A8h+entry]; Message
0x1800074d6  mov     r8, r15; attr
0x1800074d9  mov     rcx, [rsp+0A8h+ld]; ExternalHandle
0x1800074e1  mov     r12, rbx
0x1800074e4  call    cs:__imp_ldap_get_values_lenW
0x1800074ea  mov     [rsp+0A8h+vals], rax
0x1800074ef  test    rax, rax
0x1800074f2  jnz     short loc_180007517
0x1800074f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074fb  lea     rax, WPP_GLOBAL_Control
0x180007502  cmp     rcx, rax
0x180007505  jz      short loc_180007495
0x180007507  test    byte ptr [rcx+1Ch], 4
0x18000750b  jz      short loc_180007495
0x18000750d  mov     edx, 0Ah
0x180007512  jmp     loc_180007482
0x180007517  mov     rax, [rax]
0x18000751a  mov     [rsp+0A8h+var_60], rax
0x18000751f  test    rax, rax
0x180007522  jz      loc_180007858
0x180007528  mov     rbx, [rsp+0A8h+Size]
0x18000752d  lea     rdx, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x180007534  mov     rcx, r15; String1
0x180007537  call    wcscmp_0
0x18000753c  test    eax, eax
0x18000753e  jnz     short loc_180007584
0x180007540  mov     dword ptr [rsp+0A8h+arg_18], ebx
0x180007547  add     ebx, esi
0x180007549  cmp     ebx, esi
0x18000754b  jb      loc_1800077FE
0x180007551  mov     rcx, [rsp+0A8h+Size]; unsigned __int64
0x180007556  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000755b  mov     [rsp+0A8h+lpMem], rax
0x180007560  test    rax, rax
0x180007563  jz      loc_1800077F4
0x180007569  mov     r8, [rsp+0A8h+Size]; Size
0x18000756e  mov     esi, ebx
0x180007570  mov     rdx, [rsp+0A8h+Src]; Src
0x180007575  mov     rcx, rax; void *
0x180007578  xor     edi, edi
0x18000757a  call    memcpy_0
0x18000757f  jmp     loc_1800077B4
0x180007584  lea     rdx, aMskdsKdfparam; "msKds-KDFParam"
0x18000758b  mov     rcx, r15; String1
0x18000758e  call    wcscmp_0
0x180007593  test    eax, eax
0x180007595  jnz     loc_180007648
0x18000759b  mov     rbx, [rsp+0A8h+var_60]
0x1800075a0  mov     edx, [rbx]; unsigned int
0x1800075a2  mov     rcx, [rbx+8]; unsigned __int8 *
0x1800075a6  call    ?ValidateKDFParam@@YAJPEAEK@Z; ValidateKDFParam(uchar *,ulong)
0x1800075ab  xor     edi, edi
0x1800075ad  test    eax, eax
0x1800075af  jns     short loc_1800075DB
0x1800075b1  mov     r9d, 129h; unsigned int
0x1800075b7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800075be  lea     rdx, aHr; "hr"
0x1800075c5  mov     ecx, eax; unsigned int
0x1800075c7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800075cc  lea     rax, aMskdsKdfparam; "msKds-KDFParam"
0x1800075d3  mov     [r14+48h], edi
0x1800075d7  mov     [r14+50h], rax
0x1800075db  cmp     [r14+48h], edi
0x1800075df  jnz     short loc_180007602
0x1800075e1  test    ebp, ebp
0x1800075e3  jnz     short loc_180007602
0x1800075e5  test    cs:Microsoft_Windows_KdsSvcEnableBits, 4
0x1800075ec  jz      short loc_1800075FD
0x1800075ee  mov     r8, r15
0x1800075f1  lea     rdx, KdsSvcInvalidSrvConfig
0x1800075f8  call    McTemplateU0z_EventWriteTransfer
0x1800075fd  mov     ebp, 1
0x180007602  mov     eax, [rbx]
0x180007604  mov     dword ptr [rsp+0A8h+var_70], eax
0x180007608  lea     ebx, [rax+rsi]
0x18000760b  cmp     ebx, esi
0x18000760d  jb      loc_180007838
0x180007613  mov     ecx, eax; unsigned __int64
0x180007615  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000761a  mov     [rsp+0A8h+var_88], rax
0x18000761f  test    rax, rax
0x180007622  jz      loc_180007826
0x180007628  mov     rax, [rsp+0A8h+var_60]
0x18000762d  mov     esi, ebx
0x18000762f  mov     rbx, [rsp+0A8h+var_88]
0x180007634  mov     rcx, rbx; void *
0x180007637  mov     r8d, [rax]; Size
0x18000763a  mov     rdx, [rax+8]; Src
0x18000763e  call    memcpy_0
0x180007643  jmp     loc_1800077B9
0x180007648  lea     rdx, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x18000764f  mov     rcx, r15; String1
0x180007652  call    wcscmp_0
0x180007657  test    eax, eax
0x180007659  jnz     short loc_18000768C
0x18000765b  mov     dword ptr [rsp+0A8h+var_70+4], ebx
0x18000765f  add     ebx, esi
0x180007661  cmp     ebx, esi
0x180007663  jb      loc_180007840
0x180007669  mov     rcx, [rsp+0A8h+Size]; unsigned __int64
0x18000766e  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180007673  mov     [rsp+0A8h+var_40], rax
0x180007678  test    rax, rax
0x18000767b  jnz     loc_180007569
0x180007681  mov     r9d, 155h
0x180007687  jmp     loc_18000782C
0x18000768c  lea     rdx, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x180007693  mov     rcx, r15; String1
0x180007696  call    wcscmp_0
0x18000769b  xor     ebx, ebx
0x18000769d  test    eax, eax
0x18000769f  jnz     short loc_1800076E2
0x1800076a1  mov     rax, [rsp+0A8h+var_60]
0x1800076a6  mov     eax, [rax]
0x1800076a8  mov     dword ptr [rsp+0A8h+var_68], eax
0x1800076ac  lea     edi, [rax+rsi]
0x1800076af  cmp     edi, esi
0x1800076b1  jb      loc_180007850
0x1800076b7  mov     ecx, eax; unsigned __int64
0x1800076b9  mov     ebx, eax
0x1800076bb  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800076c0  mov     r13, rax
0x1800076c3  test    rax, rax
0x1800076c6  jz      loc_180007848
0x1800076cc  mov     rax, [rsp+0A8h+var_60]
0x1800076d1  mov     esi, edi
0x1800076d3  mov     r8d, ebx
0x1800076d6  mov     rcx, r13
0x1800076d9  mov     rdx, [rax+8]
0x1800076dd  jmp     loc_180007578
0x1800076e2  lea     rdx, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x1800076e9  mov     rcx, r15; String1
0x1800076ec  call    wcscmp_0
0x1800076f1  test    eax, eax
0x1800076f3  jnz     short loc_180007722
0x1800076f5  mov     rcx, [rsp+0A8h+Src]; SourceString
0x1800076fa  lea     rdx, [r14+34h]; unsigned int *
0x1800076fe  call    ?ConvertStrToUlong@@YAJPEAGPEAK@Z; ConvertStrToUlong(ushort *,ulong *)
0x180007703  mov     edi, eax
0x180007705  xor     eax, eax
0x180007707  cmp     [r14+34h], eax
0x18000770b  jnz     short loc_18000771C
0x18000770d  lea     rcx, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x180007714  mov     [r14+48h], eax
0x180007718  mov     [r14+50h], rcx
0x18000771c  cmp     [r14+48h], eax
0x180007720  jmp     short loc_180007791
0x180007722  lea     rdx, aMskdsPublickey; "msKds-PublicKeyLength"
0x180007729  mov     rcx, r15; String1
0x18000772c  call    wcscmp_0
0x180007731  test    eax, eax
0x180007733  jnz     short loc_180007756
0x180007735  mov     rcx, [rsp+0A8h+Src]; SourceString
0x18000773a  lea     rdx, [r14+38h]; unsigned int *
0x18000773e  call    ?ConvertStrToUlong@@YAJPEAGPEAK@Z; ConvertStrToUlong(ushort *,ulong *)
0x180007743  mov     edi, eax
0x180007745  xor     eax, eax
0x180007747  cmp     [r14+38h], eax
0x18000774b  jnz     short loc_18000771C
0x18000774d  lea     rcx, aMskdsPublickey; "msKds-PublicKeyLength"
0x180007754  jmp     short loc_180007714
0x180007756  lea     rdx, aMskdsVersion; "msKds-Version"
0x18000775d  mov     rcx, r15; String1
0x180007760  call    wcscmp_0
0x180007765  test    eax, eax
0x180007767  jnz     short loc_1800077B4
0x180007769  mov     rcx, [rsp+0A8h+Src]; SourceString
0x18000776e  mov     rdx, r14; unsigned int *
0x180007771  call    ?ConvertStrToUlong@@YAJPEAGPEAK@Z; ConvertStrToUlong(ushort *,ulong *)
0x180007776  cmp     dword ptr [r14], 1
0x18000777a  mov     edi, eax
0x18000777c  jz      short loc_18000778D
0x18000777e  lea     rax, aMskdsVersion; "msKds-Version"
0x180007785  mov     [r14+48h], ebx
0x180007789  mov     [r14+50h], rax
0x18000778d  cmp     [r14+48h], ebx
0x180007791  jnz     short loc_1800077B4
0x180007793  test    ebp, ebp
0x180007795  jnz     short loc_1800077B4
0x180007797  test    cs:Microsoft_Windows_KdsSvcEnableBits, 4
0x18000779e  jz      short loc_1800077AF
0x1800077a0  mov     r8, r15
0x1800077a3  lea     rdx, KdsSvcInvalidSrvConfig
0x1800077aa  call    McTemplateU0z_EventWriteTransfer
0x1800077af  mov     ebp, 1
0x1800077b4  mov     rbx, [rsp+0A8h+var_88]
0x1800077b9  test    r12, r12
0x1800077bc  jz      short loc_1800077CA
0x1800077be  mov     rcx, r12; vals
0x1800077c1  call    cs:__imp_ldap_value_freeW
0x1800077c7  xor     r12d, r12d
0x1800077ca  mov     rax, [rsp+0A8h+vals]
0x1800077cf  test    rax, rax
0x1800077d2  jz      short loc_1800077E6
0x1800077d4  mov     rcx, rax; vals
0x1800077d7  call    cs:__imp_ldap_value_free_len
0x1800077dd  mov     [rsp+0A8h+vals], 0
0x1800077e6  mov     rcx, r15; Block
0x1800077e9  call    cs:__imp_ldap_memfreeW
0x1800077ef  jmp     loc_18000749A
0x1800077f4  mov     edi, 8007000Eh
0x1800077f9  jmp     loc_180007963
0x1800077fe  mov     r9d, 112h; unsigned int
0x180007804  mov     edi, 80070216h
0x180007809  mov     ecx, 80070216h; unsigned int
0x18000780e  lea     rdx, aHr; "hr"
  ... truncated ...
```
