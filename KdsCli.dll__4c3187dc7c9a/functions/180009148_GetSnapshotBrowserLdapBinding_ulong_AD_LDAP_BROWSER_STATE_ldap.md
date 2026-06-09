# GetSnapshotBrowserLdapBinding(ulong,_AD_LDAP_BROWSER_STATE * *,ldap * *)

- ea: `0x180009148`
- end: `0x1800093ff`
- name: `?GetSnapshotBrowserLdapBinding@@YAJKPEAPEAU_AD_LDAP_BROWSER_STATE@@PEAPEAUldap@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(ULONG PortNumber, struct _AD_LDAP_BROWSER_STATE **, struct ldap **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008eb4`

## callees

- `0x180003e30`
- `0x180008528`
- `0x180009148`
- `0x180009ba4`
- `0x180009e04`
- `0x18000a384`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x1800093df`
- `WLDAP32!__imp_ldap_unbind` at `0x1800093df`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800091e5`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800091fc`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180009213`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180009228`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800091e5`
- `WLDAP32!__imp_ldap_set_optionW` at `0x1800091fc`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180009213`
- `WLDAP32!__imp_ldap_set_optionW` at `0x180009228`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800091b6`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800091b6`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180009242`
- `WLDAP32!__imp_ldap_bind_sW` at `0x180009242`
- `WLDAP32!__imp_ldap_initW` at `0x1800091a8`
- `WLDAP32!__imp_ldap_initW` at `0x1800091a8`

## string_xrefs

- `0x180009291`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x1800092e5`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`
- `0x180009328`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall GetSnapshotBrowserLdapBinding(
        ULONG PortNumber,
        struct _AD_LDAP_BROWSER_STATE **a2,
        struct ldap **a3)
{
  struct _AD_LDAP_BROWSER_STATE *v3; // rsi
  LDAP *v7; // rax
  LDAP *v8; // rdi
  signed int LastError; // eax
  int v10; // ebx
  bool v11; // cc
  ULONG v12; // eax
  __int64 v13; // r8
  unsigned int v14; // r9d
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // r9d
  int ADSnapshotBrowserDomainNames; // eax
  struct _AD_LDAP_BROWSER_STATE *v20; // [rsp+68h] [rbp+10h] BYREF

  v3 = 0;
  v20 = 0;
  *a2 = 0;
  *a3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, PortNumber, PortNumber);
  v7 = ldap_initW((const PWSTR)L"localhost", PortNumber);
  v8 = v7;
  if ( !v7 )
  {
    LastError = LdapGetLastError();
    v10 = LastError;
    v11 = LastError <= 0;
    goto LABEL_6;
  }
  LastError = ldap_set_optionW(v7, 149, (const void *)1);
  v10 = LastError;
  v11 = LastError <= 0;
  if ( LastError )
    goto LABEL_6;
  LastError = ldap_set_optionW(v8, 150, (const void *)1);
  v10 = LastError;
  v11 = LastError <= 0;
  if ( LastError
    || (LastError = ldap_set_optionW(v8, 152, (const void *)1), v10 = LastError, v11 = LastError <= 0, LastError)
    || (LastError = ldap_set_optionW(v8, 8, 0), v10 = LastError, v11 = LastError <= 0, LastError) )
  {
LABEL_6:
    if ( !v11 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_40;
  }
  v12 = ldap_bind_sW(v8, 0, 0, 0x486u);
  v10 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v13, v12, v12);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v14 = 625;
LABEL_19:
    v15 = v10;
LABEL_20:
    SidKeyDebugTraceError(v15, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v14);
    goto LABEL_40;
  }
  v16 = QueryADSnapshotBrowserState(v8, &v20);
  v10 = v16;
  if ( v16 >= 0 )
  {
    v3 = v20;
    if ( *((_DWORD *)v20 + 6) >= 7u )
    {
      if ( *((_DWORD *)v20 + 7) >= 7u )
      {
        ADSnapshotBrowserDomainNames = QueryADSnapshotBrowserDomainNames(v8, v20);
        v10 = ADSnapshotBrowserDomainNames;
        if ( ADSnapshotBrowserDomainNames >= 0 )
        {
          *a2 = v3;
          v3 = 0;
          *a3 = v8;
          v8 = 0;
          v10 = 0;
          goto LABEL_40;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_497df786d6153c614e507117de9dfe52_Traceguids,
            (unsigned int)ADSnapshotBrowserDomainNames);
        v14 = 656;
        goto LABEL_19;
      }
      v17 = 172;
    }
    else
    {
      v17 = 165;
    }
    SidKeyDebugTraceError(0x80070548, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", v17);
    v10 = -2147023544;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_497df786d6153c614e507117de9dfe52_Traceguids, 2147943752LL);
    v14 = 646;
    v15 = -2147023544;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_497df786d6153c614e507117de9dfe52_Traceguids,
      (unsigned int)v16);
  SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 0x27Bu);
  v3 = v20;
LABEL_40:
  FreeLdapBrowserState(v3);
  if ( v8 )
    ldap_unbind(v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180009148  mov     rax, rsp
0x18000914b  mov     [rax+8], rbx
0x18000914f  mov     [rax+18h], rsi
0x180009153  push    rdi
0x180009154  push    r12
0x180009156  push    r13
0x180009158  push    r14
0x18000915a  push    r15
0x18000915c  sub     rsp, 30h
0x180009160  xor     esi, esi
0x180009162  mov     r14, r8
0x180009165  mov     [rax+10h], rsi
0x180009169  mov     r15, rdx
0x18000916c  mov     [rdx], rsi
0x18000916f  mov     ebx, ecx
0x180009171  mov     [r8], rsi
0x180009174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000917b  lea     r13, WPP_GLOBAL_Control
0x180009182  cmp     rcx, r13
0x180009185  jz      short loc_18000919F
0x180009187  test    byte ptr [rcx+1Ch], 4
0x18000918b  jz      short loc_18000919F
0x18000918d  mov     rcx, [rcx+10h]
0x180009191  lea     edx, [rsi+0Dh]
0x180009194  mov     r9d, ebx
0x180009197  mov     [rax-38h], ebx
0x18000919a  call    WPP_SF_Dd
0x18000919f  mov     edx, ebx; PortNumber
0x1800091a1  lea     rcx, HostName; "localhost"
0x1800091a8  call    cs:__imp_ldap_initW
0x1800091ae  mov     rdi, rax
0x1800091b1  test    rax, rax
0x1800091b4  jnz     short loc_1800091D4
0x1800091b6  call    cs:__imp_LdapGetLastError
0x1800091bc  mov     ebx, eax
0x1800091be  test    eax, eax
0x1800091c0  jle     loc_1800093CF
0x1800091c6  movzx   ebx, ax
0x1800091c9  or      ebx, 80070000h
0x1800091cf  jmp     loc_1800093CF
0x1800091d4  mov     r12d, 1
0x1800091da  mov     edx, 95h; option
0x1800091df  mov     r8d, r12d; invalue
0x1800091e2  mov     rcx, rdi; ld
0x1800091e5  call    cs:__imp_ldap_set_optionW
0x1800091eb  mov     ebx, eax
0x1800091ed  test    eax, eax
0x1800091ef  jnz     short loc_1800091C0
0x1800091f1  mov     r8d, r12d; invalue
0x1800091f4  mov     edx, 96h; option
0x1800091f9  mov     rcx, rdi; ld
0x1800091fc  call    cs:__imp_ldap_set_optionW
0x180009202  mov     ebx, eax
0x180009204  test    eax, eax
0x180009206  jnz     short loc_1800091C0
0x180009208  mov     r8d, r12d; invalue
0x18000920b  mov     edx, 98h; option
0x180009210  mov     rcx, rdi; ld
0x180009213  call    cs:__imp_ldap_set_optionW
0x180009219  mov     ebx, eax
0x18000921b  test    eax, eax
0x18000921d  jnz     short loc_1800091C0
0x18000921f  xor     r8d, r8d; invalue
0x180009222  lea     edx, [rax+8]; option
0x180009225  mov     rcx, rdi; ld
0x180009228  call    cs:__imp_ldap_set_optionW
0x18000922e  mov     ebx, eax
0x180009230  test    eax, eax
0x180009232  jnz     short loc_1800091C0
0x180009234  mov     r9d, 486h; method
0x18000923a  xor     r8d, r8d; cred
0x18000923d  xor     edx, edx; dn
0x18000923f  mov     rcx, rdi; ld
0x180009242  call    cs:__imp_ldap_bind_sW
0x180009248  mov     ebx, eax
0x18000924a  test    eax, eax
0x18000924c  jz      short loc_1800092A2
0x18000924e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009255  cmp     rcx, r13
0x180009258  jz      short loc_180009275
0x18000925a  test    [rcx+1Ch], r12b
0x18000925e  jz      short loc_180009275
0x180009260  mov     rcx, [rcx+10h]
0x180009264  lea     edx, [r12+0Dh]
0x180009269  mov     r9d, eax
0x18000926c  mov     [rsp+58h+var_38], eax
0x180009270  call    WPP_SF_Dd
0x180009275  test    ebx, ebx
0x180009277  jle     short loc_180009282
0x180009279  movzx   ebx, bx
0x18000927c  or      ebx, 80070000h
0x180009282  mov     r9d, 271h; unsigned int
0x180009288  mov     ecx, ebx; unsigned int
0x18000928a  lea     rdx, aHr; "hr"
0x180009291  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009298  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000929d  jmp     loc_1800093CF
0x1800092a2  lea     rdx, [rsp+58h+arg_8]; struct _AD_LDAP_BROWSER_STATE **
0x1800092a7  mov     rcx, rdi; ld
0x1800092aa  call    ?QueryADSnapshotBrowserState@@YAJPEAUldap@@PEAPEAU_AD_LDAP_BROWSER_STATE@@@Z; QueryADSnapshotBrowserState(ldap *,_AD_LDAP_BROWSER_STATE * *)
0x1800092af  mov     ebx, eax
0x1800092b1  test    eax, eax
0x1800092b3  jns     short loc_180009304
0x1800092b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092bc  cmp     rcx, r13
0x1800092bf  jz      short loc_1800092DF
0x1800092c1  test    [rcx+1Ch], r12b
0x1800092c5  jz      short loc_1800092DF
0x1800092c7  mov     rcx, [rcx+10h]
0x1800092cb  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800092d2  mov     edx, 0Fh
0x1800092d7  mov     r9d, eax
0x1800092da  call    WPP_SF_D
0x1800092df  mov     r9d, 27Bh; unsigned int
0x1800092e5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800092ec  lea     rdx, aHr; "hr"
0x1800092f3  mov     ecx, ebx; unsigned int
0x1800092f5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800092fa  mov     rsi, [rsp+58h+arg_8]
0x1800092ff  jmp     loc_1800093CF
0x180009304  mov     rsi, [rsp+58h+arg_8]
0x180009309  cmp     dword ptr [rsi+18h], 7
0x18000930d  jnb     short loc_180009317
0x18000930f  mov     r9d, 0A5h
0x180009315  jmp     short loc_180009323
0x180009317  cmp     dword ptr [rsi+1Ch], 7
0x18000931b  jnb     short loc_18000937D
0x18000931d  mov     r9d, 0ACh; unsigned int
0x180009323  mov     ecx, 80070548h; unsigned int
0x180009328  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000932f  lea     rdx, aHr; "hr"
0x180009336  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000933b  mov     ebx, 80070548h
0x180009340  mov     rcx, cs:WPP_GLOBAL_Control
0x180009347  cmp     rcx, r13
0x18000934a  jz      short loc_18000936D
0x18000934c  test    [rcx+1Ch], r12b
0x180009350  jz      short loc_18000936D
0x180009352  mov     rcx, [rcx+10h]
0x180009356  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x18000935d  mov     edx, 10h
0x180009362  mov     r9d, 80070548h
0x180009368  call    WPP_SF_D
0x18000936d  mov     r9d, 286h
0x180009373  mov     ecx, 80070548h
0x180009378  jmp     loc_18000928A
0x18000937d  mov     rdx, rsi; struct _AD_LDAP_BROWSER_STATE *
0x180009380  mov     rcx, rdi; ld
0x180009383  call    ?QueryADSnapshotBrowserDomainNames@@YAJPEAUldap@@PEAU_AD_LDAP_BROWSER_STATE@@@Z; QueryADSnapshotBrowserDomainNames(ldap *,_AD_LDAP_BROWSER_STATE *)
0x180009388  mov     ebx, eax
0x18000938a  test    eax, eax
0x18000938c  jns     short loc_1800093C3
0x18000938e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009395  cmp     rcx, r13
0x180009398  jz      short loc_1800093B8
0x18000939a  test    [rcx+1Ch], r12b
0x18000939e  jz      short loc_1800093B8
0x1800093a0  mov     rcx, [rcx+10h]
0x1800093a4  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x1800093ab  mov     edx, 11h
0x1800093b0  mov     r9d, eax
0x1800093b3  call    WPP_SF_D
0x1800093b8  mov     r9d, 290h
0x1800093be  jmp     loc_180009288
0x1800093c3  mov     [r15], rsi
0x1800093c6  xor     esi, esi
0x1800093c8  mov     [r14], rdi
0x1800093cb  xor     edi, edi
0x1800093cd  xor     ebx, ebx
0x1800093cf  mov     rcx, rsi; struct _AD_LDAP_BROWSER_STATE *
0x1800093d2  call    ?FreeLdapBrowserState@@YAXPEAU_AD_LDAP_BROWSER_STATE@@@Z; FreeLdapBrowserState(_AD_LDAP_BROWSER_STATE *)
0x1800093d7  test    rdi, rdi
0x1800093da  jz      short loc_1800093E5
0x1800093dc  mov     rcx, rdi; ld
0x1800093df  call    cs:__imp_ldap_unbind
0x1800093e5  mov     rsi, [rsp+58h+arg_10]
0x1800093ea  mov     eax, ebx
0x1800093ec  mov     rbx, [rsp+58h+arg_0]
0x1800093f1  add     rsp, 30h
0x1800093f5  pop     r15
0x1800093f7  pop     r14
0x1800093f9  pop     r13
0x1800093fb  pop     r12
0x1800093fd  pop     rdi
0x1800093fe  retn
```
