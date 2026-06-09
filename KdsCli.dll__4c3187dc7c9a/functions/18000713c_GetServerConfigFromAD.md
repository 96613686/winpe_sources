# GetServerConfigFromAD

- ea: `0x18000713c`
- end: `0x18000734c`
- name: `GetServerConfigFromAD`
- size: `528`
- prototype: `__int64 __fastcall(LDAP *ld, PWSTR base, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007060`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180003e08`
- `0x180003e30`
- `0x18000713c`
- `0x180007354`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_first_entry` at `0x18000728a`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000728a`
- `WLDAP32!__imp_ldap_msgfree` at `0x180007300`
- `WLDAP32!__imp_ldap_msgfree` at `0x180007300`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000724d`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x18000724d`

## string_xrefs

- `0x18000725f`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x1800072d8`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x1800071be`: `(&(objectClass=msKds-ProvServerConfiguration)(cn=Group Key Distribution Service Server Configuration))`

## pseudocode

```c
__int64 __fastcall GetServerConfigFromAD(LDAP *ld, PWSTR base, unsigned int *a3)
{
  ULONG v6; // eax
  unsigned int v7; // ebx
  LDAPMessage *entry; // rax
  _QWORD *v9; // rcx
  signed int v10; // eax
  PLDAPMessage res; // [rsp+60h] [rbp-29h] BYREF
  PWSTR attrs[8]; // [rsp+70h] [rbp-19h] BYREF

  res = 0;
  memset_0(attrs, 0, sizeof(attrs));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids);
  attrs[7] = 0;
  attrs[0] = (PWSTR)L"msKds-KDFAlgorithmID";
  attrs[1] = (PWSTR)L"msKds-KDFParam";
  attrs[2] = (PWSTR)L"msKds-SecretAgreementAlgorithmID";
  attrs[3] = (PWSTR)L"msKds-SecretAgreementParam";
  attrs[4] = (PWSTR)L"msKds-PublicKeyLength";
  attrs[5] = (PWSTR)L"msKds-PrivateKeyLength";
  attrs[6] = (PWSTR)L"msKds-Version";
  v6 = ldap_search_ext_sW(
         ld,
         base,
         0,
         (const PWSTR)L"(&(objectClass=msKds-ProvServerConfiguration)(cn=Group Key Distribution Service Server Configuration))",
         attrs,
         0,
         0,
         0,
         0,
         1u,
         &res);
  v7 = v6;
  if ( v6 )
  {
    SidKeyDebugTraceError(v6, "ulReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", 0x246u);
    if ( (int)v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_13;
  }
  entry = ldap_first_entry(ld, res);
  if ( entry )
  {
    v10 = ParseServerConfig(ld, entry, a3);
    v7 = v10;
    if ( v10 < 0 )
      SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", 0x257u);
    goto LABEL_13;
  }
  v7 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids);
LABEL_13:
    v9 = WPP_GLOBAL_Control;
  }
  if ( res )
  {
    ldap_msgfree(res);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
    WPP_SF_D(v9[2], 14, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000713c  push    rbp
0x18000713e  push    rbx
0x18000713f  push    rsi
0x180007140  push    rdi
0x180007141  push    r13
0x180007143  lea     rbp, [rsp-37h]
0x180007148  sub     rsp, 0C0h
0x18000714f  mov     rax, cs:__security_cookie
0x180007156  xor     rax, rsp
0x180007159  mov     [rbp+57h+var_30], rax
0x18000715d  mov     rbx, rdx
0x180007160  mov     [rbp+57h+var_80], 0
0x180007168  xor     edx, edx; Val
0x18000716a  mov     rsi, r8
0x18000716d  mov     rdi, rcx
0x180007170  lea     rcx, [rbp+57h+var_70]; void *
0x180007174  lea     r8d, [rdx+40h]; Size
0x180007178  call    memset_0
0x18000717d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007184  lea     r13, WPP_GLOBAL_Control
0x18000718b  cmp     rcx, r13
0x18000718e  jz      short loc_1800071AB
0x180007190  test    byte ptr [rcx+1Ch], 4
0x180007194  jz      short loc_1800071AB
0x180007196  mov     rcx, [rcx+10h]
0x18000719a  lea     r8, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids
0x1800071a1  mov     edx, 0Ch
0x1800071a6  call    WPP_SF_
0x1800071ab  lea     rax, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x1800071b2  mov     [rbp+57h+var_38], 0
0x1800071ba  mov     [rbp+57h+var_70], rax
0x1800071be  lea     r9, aObjectclassMsk_0; "(&(objectClass=msKds-ProvServerConfigur"...
0x1800071c5  lea     rax, aMskdsKdfparam; "msKds-KDFParam"
0x1800071cc  xor     r8d, r8d; scope
0x1800071cf  mov     [rbp+57h+var_68], rax
0x1800071d3  mov     rdx, rbx; base
0x1800071d6  lea     rax, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x1800071dd  mov     rcx, rdi; ld
0x1800071e0  mov     [rbp+57h+var_60], rax
0x1800071e4  lea     rax, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x1800071eb  mov     [rbp+57h+var_58], rax
0x1800071ef  lea     rax, aMskdsPublickey; "msKds-PublicKeyLength"
0x1800071f6  mov     [rbp+57h+var_50], rax
0x1800071fa  lea     rax, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x180007201  mov     [rbp+57h+var_48], rax
0x180007205  lea     rax, aMskdsVersion; "msKds-Version"
0x18000720c  mov     [rbp+57h+var_40], rax
0x180007210  lea     rax, [rbp+57h+var_80]
0x180007214  mov     [rsp+0E0h+res], rax; res
0x180007219  lea     rax, [rbp+57h+var_70]
0x18000721d  mov     [rsp+0E0h+SizeLimit], 1; SizeLimit
0x180007225  mov     [rsp+0E0h+timeout], 0; timeout
0x18000722e  mov     [rsp+0E0h+ClientControls], 0; ClientControls
0x180007237  mov     [rsp+0E0h+ServerControls], 0; ServerControls
0x180007240  mov     [rsp+0E0h+attrsonly], 0; attrsonly
0x180007248  mov     [rsp+0E0h+attrs], rax; attrs
0x18000724d  call    cs:__imp_ldap_search_ext_sW
0x180007253  mov     ebx, eax
0x180007255  test    eax, eax
0x180007257  jz      short loc_180007283
0x180007259  mov     r9d, 246h; unsigned int
0x18000725f  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007266  lea     rdx, aUlreturn; "ulReturn"
0x18000726d  mov     ecx, eax; unsigned int
0x18000726f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007274  test    ebx, ebx
0x180007276  jle     short loc_1800072ED
0x180007278  movzx   ebx, bx
0x18000727b  or      ebx, 80070000h
0x180007281  jmp     short loc_1800072ED
0x180007283  mov     rdx, [rbp+57h+var_80]; res
0x180007287  mov     rcx, rdi; ld
0x18000728a  call    cs:__imp_ldap_first_entry
0x180007290  test    rax, rax
0x180007293  jnz     short loc_1800072BE
0x180007295  xor     ebx, ebx
0x180007297  mov     rcx, cs:WPP_GLOBAL_Control
0x18000729e  cmp     rcx, r13
0x1800072a1  jz      short loc_1800072F4
0x1800072a3  test    byte ptr [rcx+1Ch], 4
0x1800072a7  jz      short loc_1800072F4
0x1800072a9  mov     rcx, [rcx+10h]
0x1800072ad  lea     edx, [rax+0Dh]
0x1800072b0  lea     r8, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids
0x1800072b7  call    WPP_SF_
0x1800072bc  jmp     short loc_1800072ED
0x1800072be  mov     r8, rsi; unsigned int *
0x1800072c1  mov     rdx, rax; entry
0x1800072c4  mov     rcx, rdi; ld
0x1800072c7  call    ParseServerConfig
0x1800072cc  mov     ebx, eax
0x1800072ce  test    eax, eax
0x1800072d0  jns     short loc_1800072ED
0x1800072d2  mov     r9d, 257h; unsigned int
0x1800072d8  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800072df  lea     rdx, aHr; "hr"
0x1800072e6  mov     ecx, eax; unsigned int
0x1800072e8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800072ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072f4  mov     rax, [rbp+57h+var_80]
0x1800072f8  test    rax, rax
0x1800072fb  jz      short loc_18000730D
0x1800072fd  mov     rcx, rax; res
0x180007300  call    cs:__imp_ldap_msgfree
0x180007306  mov     rcx, cs:WPP_GLOBAL_Control
0x18000730d  cmp     rcx, r13
0x180007310  jz      short loc_180007330
0x180007312  test    byte ptr [rcx+1Ch], 4
0x180007316  jz      short loc_180007330
0x180007318  mov     rcx, [rcx+10h]
0x18000731c  lea     r8, WPP_d62c2fbab676338d1e19cb4175520a6f_Traceguids
0x180007323  mov     edx, 0Eh
0x180007328  mov     r9d, ebx
0x18000732b  call    WPP_SF_D
0x180007330  mov     eax, ebx
0x180007332  mov     rcx, [rbp+57h+var_30]
0x180007336  xor     rcx, rsp; StackCookie
0x180007339  call    __security_check_cookie
0x18000733e  add     rsp, 0C0h
0x180007345  pop     r13
0x180007347  pop     rdi
0x180007348  pop     rsi
0x180007349  pop     rbx
0x18000734a  pop     rbp
0x18000734b  retn
```
