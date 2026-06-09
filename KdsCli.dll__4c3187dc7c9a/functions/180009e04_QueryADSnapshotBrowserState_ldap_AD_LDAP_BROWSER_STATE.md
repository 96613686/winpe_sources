# QueryADSnapshotBrowserState(ldap *,_AD_LDAP_BROWSER_STATE * *)

- ea: `0x180009e04`
- end: `0x18000a14c`
- name: `?QueryADSnapshotBrowserState@@YAJPEAUldap@@PEAPEAU_AD_LDAP_BROWSER_STATE@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(LDAP *ld, struct _AD_LDAP_BROWSER_STATE **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009148`

## callees

- `0x180001630`
- `0x180003d7c`
- `0x180003e08`
- `0x180008528`
- `0x180009e04`
- `0x180010850`
- `0x180010920`
- `0x18001a450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009f66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009f66`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000a0b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000a0ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000a0b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18000a0ea`
- `WLDAP32!__imp_ldap_first_entry` at `0x180009efb`
- `WLDAP32!__imp_ldap_first_entry` at `0x180009efb`
- `WLDAP32!__imp_ldap_msgfree` at `0x180009fde`
- `WLDAP32!__imp_ldap_msgfree` at `0x180009fde`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180009f49`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180009f49`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009f38`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a01b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a055`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a08f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a0ca`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009f38`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a01b`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a055`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a08f`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x18000a0ca`
- `WLDAP32!__imp_ldap_search_sW` at `0x180009ecf`
- `WLDAP32!__imp_ldap_search_sW` at `0x180009ecf`

## string_xrefs

- `0x180009e2f`: `configurationNamingContext`
- `0x18000a00e`: `configurationNamingContext`
- `0x180009fb9`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall QueryADSnapshotBrowserState(LDAP *ld, struct _AD_LDAP_BROWSER_STATE **a2)
{
  char *v4; // rdi
  signed int v5; // eax
  signed int v6; // ebx
  unsigned int v7; // r9d
  unsigned int v8; // ecx
  LDAPMessage *entry; // rsi
  PWCHAR *valuesW; // rax
  PWCHAR *v11; // r14
  ULONG v12; // r15d
  int v13; // ebx
  PWCHAR *v15; // rax
  _QWORD *v16; // r14
  PWCHAR *v17; // rax
  const wchar_t **v18; // rax
  const wchar_t **v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // rax
  LDAPMessage *res; // [rsp+40h] [rbp-78h] BYREF
  PWSTR attrs[6]; // [rsp+48h] [rbp-70h] BYREF

  attrs[1] = (PWSTR)L"configurationNamingContext";
  res = 0;
  attrs[2] = (PWSTR)L"defaultNamingContext";
  *a2 = 0;
  attrs[3] = (PWSTR)L"domainControllerFunctionality";
  attrs[0] = (PWSTR)L"supportedCapabilities";
  attrs[4] = (PWSTR)L"domainFunctionality";
  v4 = 0;
  attrs[5] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
  v5 = ldap_search_sW(ld, 0, 0, (const PWSTR)L"(objectClass=*)", attrs, 0, &res);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v7 = 223;
    v8 = v6;
LABEL_20:
    SidKeyDebugTraceError(v8, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v7);
    goto LABEL_21;
  }
  entry = ldap_first_entry(ld, res);
  if ( !entry )
  {
LABEL_9:
    v6 = -2147418113;
    goto LABEL_21;
  }
  v4 = (char *)SIDKeyProvAlloc(0x30u);
  if ( !v4 )
  {
LABEL_11:
    v6 = -2147024882;
    goto LABEL_21;
  }
  valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"supportedCapabilities");
  v11 = valuesW;
  if ( !valuesW )
    goto LABEL_9;
  v12 = ldap_count_valuesW(valuesW);
  v13 = 0;
  if ( !v12 )
  {
LABEL_16:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
    v6 = -2147023544;
    v7 = 269;
    v8 = -2147023544;
    goto LABEL_20;
  }
  while ( (unsigned int)_o__wcsicmp(v11[v13], L"1.2.840.113556.1.4.2237") )
  {
    if ( ++v13 >= v12 )
      goto LABEL_16;
  }
  v15 = ldap_get_valuesW(ld, entry, (const PWSTR)L"configurationNamingContext");
  if ( !v15 || !*v15 )
    goto LABEL_9;
  v16 = v4 + 8;
  v6 = SIDKeyCopyString(*v15, (unsigned __int16 **)v4 + 1);
  if ( v6 >= 0 )
  {
    v17 = ldap_get_valuesW(ld, entry, (const PWSTR)L"defaultNamingContext");
    if ( !v17 || !*v17 )
      goto LABEL_9;
    v6 = SIDKeyCopyString(*v17, (unsigned __int16 **)v4);
    if ( v6 >= 0 )
    {
      v18 = (const wchar_t **)ldap_get_valuesW(ld, entry, (const PWSTR)L"domainControllerFunctionality");
      if ( !v18 )
        goto LABEL_9;
      if ( !*v18 )
        goto LABEL_9;
      *((_DWORD *)v4 + 6) = wcstoul(*v18, 0, 10);
      v19 = (const wchar_t **)ldap_get_valuesW(ld, entry, (const PWSTR)L"domainFunctionality");
      if ( !v19 || !*v19 )
        goto LABEL_9;
      v20 = wcstoul(*v19, 0, 10);
      v21 = *v16;
      *((_DWORD *)v4 + 7) = v20;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      v23 = v22 + 16;
      v24 = (unsigned __int16 *)SIDKeyProvAlloc(2 * (v22 + 16));
      *((_QWORD *)v4 + 2) = v24;
      if ( !v24 )
        goto LABEL_11;
      v6 = StringCchPrintfW(v24, v23, L"CN=Partitions,%s", *v16);
      if ( v6 >= 0 )
      {
        *a2 = (struct _AD_LDAP_BROWSER_STATE *)v4;
        v6 = 0;
        v4 = 0;
      }
    }
  }
LABEL_21:
  FreeLdapBrowserState((struct _AD_LDAP_BROWSER_STATE *)v4);
  if ( res )
    ldap_msgfree(res);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009e04  mov     r11, rsp
0x180009e07  mov     [r11+18h], rbx
0x180009e0b  push    rbp
0x180009e0c  push    rsi
0x180009e0d  push    rdi
0x180009e0e  push    r12
0x180009e10  push    r13
0x180009e12  push    r14
0x180009e14  push    r15
0x180009e16  sub     rsp, 80h
0x180009e1d  mov     rax, cs:__security_cookie
0x180009e24  xor     rax, rsp
0x180009e27  mov     [rsp+0B8h+var_40], rax
0x180009e2c  xor     r13d, r13d
0x180009e2f  lea     rax, aConfigurationn; "configurationNamingContext"
0x180009e36  mov     [r11-68h], rax
0x180009e3a  lea     r14, aSupportedcapab; "supportedCapabilities"
0x180009e41  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x180009e48  mov     [r11-78h], r13
0x180009e4c  mov     [r11-60h], rax
0x180009e50  mov     r12, rdx
0x180009e53  lea     rax, aDomaincontroll; "domainControllerFunctionality"
0x180009e5a  mov     [rdx], r13
0x180009e5d  mov     [r11-58h], rax
0x180009e61  mov     rbp, rcx
0x180009e64  lea     rax, aDomainfunction; "domainFunctionality"
0x180009e6b  mov     [r11-70h], r14
0x180009e6f  mov     [r11-50h], rax
0x180009e73  mov     edi, r13d
0x180009e76  mov     [r11-48h], r13
0x180009e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e81  lea     rax, WPP_GLOBAL_Control
0x180009e88  cmp     rcx, rax
0x180009e8b  jz      short loc_180009EA7
0x180009e8d  test    byte ptr [rcx+1Ch], 4
0x180009e91  jz      short loc_180009EA7
0x180009e93  mov     rcx, [rcx+10h]
0x180009e97  lea     edx, [r13+0Ah]
0x180009e9b  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x180009ea2  call    WPP_SF_
0x180009ea7  lea     rax, [rsp+0B8h+var_78]
0x180009eac  xor     r8d, r8d; scope
0x180009eaf  mov     [rsp+0B8h+res], rax; res
0x180009eb4  lea     r9, filter; "(objectClass=*)"
0x180009ebb  lea     rax, [rsp+0B8h+var_70]
0x180009ec0  mov     [rsp+0B8h+attrsonly], r13d; attrsonly
0x180009ec5  xor     edx, edx; base
0x180009ec7  mov     [rsp+0B8h+attrs], rax; attrs
0x180009ecc  mov     rcx, rbp; ld
0x180009ecf  call    cs:__imp_ldap_search_sW
0x180009ed5  mov     ebx, eax
0x180009ed7  test    eax, eax
0x180009ed9  jz      short loc_180009EF3
0x180009edb  jle     short loc_180009EE6
0x180009edd  movzx   ebx, ax
0x180009ee0  or      ebx, 80070000h
0x180009ee6  mov     r9d, 0DFh
0x180009eec  mov     ecx, ebx
0x180009eee  jmp     loc_180009FB9
0x180009ef3  mov     rdx, [rsp+0B8h+var_78]; res
0x180009ef8  mov     rcx, rbp; ld
0x180009efb  call    cs:__imp_ldap_first_entry
0x180009f01  mov     rsi, rax
0x180009f04  test    rax, rax
0x180009f07  jnz     short loc_180009F13
0x180009f09  mov     ebx, 8000FFFFh
0x180009f0e  jmp     loc_180009FCC
0x180009f13  mov     ecx, 30h ; '0'; unsigned __int64
0x180009f18  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180009f1d  mov     rdi, rax
0x180009f20  test    rax, rax
0x180009f23  jnz     short loc_180009F2F
0x180009f25  mov     ebx, 8007000Eh
0x180009f2a  jmp     loc_180009FCC
0x180009f2f  mov     r8, r14; attr
0x180009f32  mov     rdx, rsi; entry
0x180009f35  mov     rcx, rbp; ld
0x180009f38  call    cs:__imp_ldap_get_valuesW
0x180009f3e  mov     r14, rax
0x180009f41  test    rax, rax
0x180009f44  jz      short loc_180009F09
0x180009f46  mov     rcx, rax; vals
0x180009f49  call    cs:__imp_ldap_count_valuesW
0x180009f4f  mov     r15d, eax
0x180009f52  mov     ebx, r13d
0x180009f55  test    eax, eax
0x180009f57  jz      short loc_180009F7B
0x180009f59  mov     ecx, ebx
0x180009f5b  lea     rdx, a12840113556142; "1.2.840.113556.1.4.2237"
0x180009f62  mov     rcx, [r14+rcx*8]
0x180009f66  call    cs:__imp__o__wcsicmp
0x180009f6c  test    eax, eax
0x180009f6e  jz      loc_18000A00E
0x180009f74  inc     ebx
0x180009f76  cmp     ebx, r15d
0x180009f79  jb      short loc_180009F59
0x180009f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f82  lea     rax, WPP_GLOBAL_Control
0x180009f89  cmp     rcx, rax
0x180009f8c  jz      short loc_180009FA9
0x180009f8e  test    byte ptr [rcx+1Ch], 1
0x180009f92  jz      short loc_180009FA9
0x180009f94  mov     rcx, [rcx+10h]
0x180009f98  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x180009f9f  mov     edx, 0Bh
0x180009fa4  call    WPP_SF_
0x180009fa9  mov     ebx, 80070548h
0x180009fae  mov     r9d, 10Dh; unsigned int
0x180009fb4  mov     ecx, 80070548h; unsigned int
0x180009fb9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009fc0  lea     rdx, aHr; "hr"
0x180009fc7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009fcc  mov     rcx, rdi; struct _AD_LDAP_BROWSER_STATE *
0x180009fcf  call    ?FreeLdapBrowserState@@YAXPEAU_AD_LDAP_BROWSER_STATE@@@Z; FreeLdapBrowserState(_AD_LDAP_BROWSER_STATE *)
0x180009fd4  mov     rcx, [rsp+0B8h+var_78]; res
0x180009fd9  test    rcx, rcx
0x180009fdc  jz      short loc_180009FE4
0x180009fde  call    cs:__imp_ldap_msgfree
0x180009fe4  mov     eax, ebx
0x180009fe6  mov     rcx, [rsp+0B8h+var_40]
0x180009feb  xor     rcx, rsp; StackCookie
0x180009fee  call    __security_check_cookie
0x180009ff3  mov     rbx, [rsp+0B8h+arg_10]
0x180009ffb  add     rsp, 80h
0x18000a002  pop     r15
0x18000a004  pop     r14
0x18000a006  pop     r13
0x18000a008  pop     r12
0x18000a00a  pop     rdi
0x18000a00b  pop     rsi
0x18000a00c  pop     rbp
0x18000a00d  retn
0x18000a00e  lea     r8, aConfigurationn; "configurationNamingContext"
0x18000a015  mov     rdx, rsi; entry
0x18000a018  mov     rcx, rbp; ld
0x18000a01b  call    cs:__imp_ldap_get_valuesW
0x18000a021  test    rax, rax
0x18000a024  jz      loc_180009F09
0x18000a02a  mov     rcx, [rax]; unsigned __int16 *
0x18000a02d  test    rcx, rcx
0x18000a030  jz      loc_180009F09
0x18000a036  lea     r14, [rdi+8]
0x18000a03a  mov     rdx, r14; unsigned __int16 **
0x18000a03d  call    ?SIDKeyCopyString@@YAJPEAGPEAPEAG@Z; SIDKeyCopyString(ushort *,ushort * *)
0x18000a042  mov     ebx, eax
0x18000a044  test    eax, eax
0x18000a046  js      short loc_180009FCC
0x18000a048  lea     r8, aDefaultnamingc; "defaultNamingContext"
0x18000a04f  mov     rdx, rsi; entry
0x18000a052  mov     rcx, rbp; ld
0x18000a055  call    cs:__imp_ldap_get_valuesW
0x18000a05b  test    rax, rax
0x18000a05e  jz      loc_180009F09
0x18000a064  mov     rcx, [rax]; unsigned __int16 *
0x18000a067  test    rcx, rcx
0x18000a06a  jz      loc_180009F09
0x18000a070  mov     rdx, rdi; unsigned __int16 **
0x18000a073  call    ?SIDKeyCopyString@@YAJPEAGPEAPEAG@Z; SIDKeyCopyString(ushort *,ushort * *)
0x18000a078  mov     ebx, eax
0x18000a07a  test    eax, eax
0x18000a07c  js      loc_180009FCC
0x18000a082  lea     r8, aDomaincontroll; "domainControllerFunctionality"
0x18000a089  mov     rdx, rsi; entry
0x18000a08c  mov     rcx, rbp; ld
0x18000a08f  call    cs:__imp_ldap_get_valuesW
0x18000a095  test    rax, rax
0x18000a098  jz      loc_180009F09
0x18000a09e  mov     rcx, [rax]; String
0x18000a0a1  test    rcx, rcx
0x18000a0a4  jz      loc_180009F09
0x18000a0aa  mov     ebx, 0Ah
0x18000a0af  xor     edx, edx; EndPtr
0x18000a0b1  mov     r8d, ebx; Radix
0x18000a0b4  call    cs:__imp_wcstoul
0x18000a0ba  lea     r8, aDomainfunction; "domainFunctionality"
0x18000a0c1  mov     rdx, rsi; entry
0x18000a0c4  mov     rcx, rbp; ld
0x18000a0c7  mov     [rdi+18h], eax
0x18000a0ca  call    cs:__imp_ldap_get_valuesW
0x18000a0d0  test    rax, rax
0x18000a0d3  jz      loc_180009F09
0x18000a0d9  mov     rcx, [rax]; String
0x18000a0dc  test    rcx, rcx
0x18000a0df  jz      loc_180009F09
0x18000a0e5  mov     r8d, ebx; Radix
0x18000a0e8  xor     edx, edx; EndPtr
0x18000a0ea  call    cs:__imp_wcstoul
0x18000a0f0  mov     rcx, [r14]
0x18000a0f3  mov     [rdi+1Ch], eax
0x18000a0f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a0fa  inc     rax
0x18000a0fd  cmp     [rcx+rax*2], r13w
0x18000a102  jnz     short loc_18000A0FA
0x18000a104  lea     rbx, [rax+10h]
0x18000a108  lea     rcx, [rbx+rbx]; unsigned __int64
0x18000a10c  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000a111  mov     [rdi+10h], rax
0x18000a115  test    rax, rax
0x18000a118  jz      loc_180009F25
0x18000a11e  mov     r9, [r14]
0x18000a121  lea     r8, aCnPartitionsS; "CN=Partitions,%s"
0x18000a128  mov     rdx, rbx; unsigned __int64
0x18000a12b  mov     rcx, rax; unsigned __int16 *
0x18000a12e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a133  mov     ebx, eax
0x18000a135  test    eax, eax
0x18000a137  js      loc_180009FCC
0x18000a13d  mov     [r12], rdi
0x18000a141  mov     ebx, r13d
0x18000a144  mov     rdi, r13
0x18000a147  jmp     loc_180009FCC
```
