# GetDCInfoForLocalDC(ldap *,ushort * *,int *)

- ea: `0x180003160`
- end: `0x18000359a`
- name: `?GetDCInfoForLocalDC@@YAJPEAUldap@@PEAPEAGPEAH@Z`
- size: `1082`
- prototype: `__int64 __fastcall(LDAP *ld, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001630`
- `0x180003160`
- `0x180003d7c`
- `0x180003f58`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a694`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003224`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180003224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003249`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003249`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003568`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003264`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180003264`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800031f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800031f1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000320a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000320a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180003254`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180003254`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003380`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003469`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003380`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003469`
- `WLDAP32!__imp_ldap_first_entry` at `0x180003335`
- `WLDAP32!__imp_ldap_first_entry` at `0x180003335`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000355f`
- `WLDAP32!__imp_ldap_msgfree` at `0x18000355f`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800033b6`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800034a5`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800033b6`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x1800034a5`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003372`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003458`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003372`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003458`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800032ee`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x1800032ee`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003535`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003543`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003535`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003543`

## string_xrefs

- `0x180003300`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003349`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x18000338c`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x1800033c3`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x18000341b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003475`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x1800034b6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x18000327b`: `<sid=%s>`

## pseudocode

```c
__int64 __fastcall GetDCInfoForLocalDC(LDAP *ld, unsigned __int16 **a2, int *a3)
{
  const wchar_t **v3; // rsi
  LPWSTR v5; // r12
  NTSTATUS v6; // ebx
  signed int LastError; // ebx
  ULONG v8; // eax
  int v9; // edi
  LDAPMessage *entry; // rax
  LDAPMessage *v11; // r15
  PWCHAR *valuesW; // rax
  const void **v13; // r14
  unsigned __int16 *v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // r12
  unsigned __int16 *v17; // rax
  PWCHAR *v18; // rax
  int v19; // eax
  unsigned __int16 **v20; // r9
  char v21; // zf
  int *v22; // rax
  LPWSTR v24; // [rsp+60h] [rbp-A0h]
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  PVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-88h] BYREF
  PLDAPMessage res; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 **v29; // [rsp+88h] [rbp-78h]
  int *v30; // [rsp+90h] [rbp-70h]
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  PWSTR attrs[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v33; // [rsp+D8h] [rbp-28h]
  WCHAR base[104]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = 0;
  v30 = a3;
  *a2 = 0;
  v29 = a2;
  *a3 = 0;
  res = 0;
  v33 = 0;
  *(_OWORD *)attrs = 0;
  StringSid = 0;
  v5 = 0;
  PolicyHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  Buffer = 0;
  v24 = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  v6 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v6 >= 0 )
  {
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyMachineAccountInformation, &Buffer);
    if ( v6 >= 0 )
    {
      if ( ConvertSidToStringSidW(*((PSID *)Buffer + 1), &StringSid) )
      {
        v5 = StringSid;
        v24 = StringSid;
        StringSid = 0;
      }
      else
      {
        v6 = -1073741801;
      }
    }
  }
  LocalFree(StringSid);
  LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v6 < 0 )
  {
    LastError = -2147024882;
    goto LABEL_40;
  }
  LastError = StringCchPrintfW(base, 0x64u, L"<sid=%s>", v5);
  if ( LastError >= 0 )
  {
    v33 = 0;
    attrs[1] = (PWSTR)L"msDS-isRODC";
    attrs[0] = (PWSTR)L"distinguishedName";
    v8 = ldap_search_ext_sW(ld, base, 0, (const PWSTR)L"(objectClass=*)", attrs, 0, 0, 0, 0, 0, &res);
    v9 = v8;
    if ( v8 )
    {
      SidKeyDebugTraceError(v8, "ulReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x29Au);
      if ( v9 <= 0 )
      {
        LastError = v9;
        goto LABEL_40;
      }
      LastError = (unsigned __int16)v9;
      goto LABEL_15;
    }
    entry = ldap_first_entry(ld, res);
    v11 = entry;
    if ( entry )
    {
      valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"distinguishedName");
      v13 = (const void **)valuesW;
      if ( valuesW )
      {
        if ( ldap_count_valuesW(valuesW) )
        {
          v15 = -1;
          do
            ++v15;
          while ( *((_WORD *)*v13 + v15) );
          v16 = 2 * v15 + 2;
          v17 = (unsigned __int16 *)SIDKeyProvAlloc(v16);
          v14 = v17;
          if ( v17 )
          {
            memcpy_0(v17, *v13, v16);
            v18 = ldap_get_valuesW(ld, v11, (const PWSTR)L"msDS-isRODC");
            v3 = (const wchar_t **)v18;
            if ( v18 )
            {
              if ( ldap_count_valuesW(v18) )
              {
                v19 = wcscmp_0(*v3, L"TRUE");
                v20 = v29;
                v21 = v19 == 0;
                v22 = v30;
                *v29 = v14;
                v14 = 0;
                *v22 = v21;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
                {
                  WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v21, (unsigned int)*v20, v21);
                }
              }
              else
              {
                SidKeyDebugTraceError(
                  0x10u,
                  "LDAP_NO_SUCH_ATTRIBUTE",
                  "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
                  0x2D0u);
                LastError = -2147024880;
              }
            }
            else
            {
              LastError = LdapGetLastError();
              SidKeyDebugTraceError(
                LastError,
                "ulReturn",
                "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
                0x2C8u);
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
          }
          else
          {
            LastError = -2147024882;
            SidKeyDebugTraceError(
              0x8007000E,
              "hr",
              "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
              0x2BEu);
          }
          v5 = v24;
        }
        else
        {
          v14 = 0;
          SidKeyDebugTraceError(
            0x10u,
            "LDAP_NO_SUCH_ATTRIBUTE",
            "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
            0x2B4u);
          LastError = -2147024880;
        }
        ldap_value_freeW((PWCHAR *)v13);
        if ( v3 )
          ldap_value_freeW((PWCHAR *)v3);
        if ( v14 )
          SIDKeyProvFree(v14);
      }
      else
      {
        LastError = LdapGetLastError();
        SidKeyDebugTraceError(
          LastError,
          "ulReturn",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
          0x2ACu);
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError;
LABEL_15:
          LastError |= 0x80070000;
        }
      }
    }
    else
    {
      SidKeyDebugTraceError(
        0x20u,
        "LDAP_NO_SUCH_OBJECT",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
        0x2A2u);
      LastError = -2147024864;
    }
  }
LABEL_40:
  if ( res )
    ldap_msgfree(res);
  LocalFree(v5);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180003160  mov     [rsp-8+arg_18], rbx
0x180003165  push    rbp
0x180003166  push    rsi
0x180003167  push    rdi
0x180003168  push    r12
0x18000316a  push    r13
0x18000316c  push    r14
0x18000316e  push    r15
0x180003170  lea     rbp, [rsp-0C0h]
0x180003178  sub     rsp, 1C0h
0x18000317f  mov     rax, cs:__security_cookie
0x180003186  xor     rax, rsp
0x180003189  mov     [rbp+0F0h+var_40], rax
0x180003190  xor     esi, esi
0x180003192  mov     [rbp+0F0h+var_160], r8
0x180003196  mov     [rdx], rsi
0x180003199  lea     r9, [rsp+1F0h+PolicyHandle]; PolicyHandle
0x18000319e  xorps   xmm0, xmm0
0x1800031a1  mov     [rbp+0F0h+var_168], rdx
0x1800031a5  mov     r13, rcx
0x1800031a8  mov     [r8], esi
0x1800031ab  xor     ecx, ecx; SystemName
0x1800031ad  mov     [rbp+0F0h+var_170], rsi
0x1800031b1  lea     rdx, [rbp+0F0h+ObjectAttributes]; ObjectAttributes
0x1800031b5  mov     [rbp+0F0h+var_118], rcx
0x1800031b9  movups  xmmword ptr [rbp+0F0h+var_128], xmm0
0x1800031bd  mov     [rsp+1F0h+StringSid], rsi
0x1800031c2  mov     r12d, esi
0x1800031c5  lea     r8d, [rcx+1]; DesiredAccess
0x1800031c9  mov     [rsp+1F0h+PolicyHandle], rsi
0x1800031ce  mov     qword ptr [rbp+0F0h+ObjectAttributes.Length], 30h ; '0'
0x1800031d6  mov     qword ptr [rbp+0F0h+ObjectAttributes.Attributes], rsi
0x1800031da  mov     [rsp+1F0h+Buffer], rsi
0x1800031df  mov     [rsp+1F0h+var_190], rsi
0x1800031e4  mov     [rbp+0F0h+ObjectAttributes.RootDirectory], rsi
0x1800031e8  mov     [rbp+0F0h+ObjectAttributes.ObjectName], rsi
0x1800031ec  movdqu  xmmword ptr [rbp+0F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800031f1  call    cs:__imp_LsaOpenPolicy
0x1800031f7  mov     ebx, eax
0x1800031f9  test    eax, eax
0x1800031fb  js      short loc_180003244
0x1800031fd  mov     rcx, [rsp+1F0h+PolicyHandle]; PolicyHandle
0x180003202  lea     r8, [rsp+1F0h+Buffer]; Buffer
0x180003207  lea     edx, [rsi+0Fh]; InformationClass
0x18000320a  call    cs:__imp_LsaQueryInformationPolicy
0x180003210  mov     ebx, eax
0x180003212  test    eax, eax
0x180003214  js      short loc_180003244
0x180003216  mov     rcx, [rsp+1F0h+Buffer]
0x18000321b  lea     rdx, [rsp+1F0h+StringSid]; StringSid
0x180003220  mov     rcx, [rcx+8]; Sid
0x180003224  call    cs:__imp_ConvertSidToStringSidW
0x18000322a  test    eax, eax
0x18000322c  jnz     short loc_180003235
0x18000322e  mov     ebx, 0C0000017h
0x180003233  jmp     short loc_180003244
0x180003235  mov     r12, [rsp+1F0h+StringSid]
0x18000323a  mov     [rsp+1F0h+var_190], r12
0x18000323f  mov     [rsp+1F0h+StringSid], rsi
0x180003244  mov     rcx, [rsp+1F0h+StringSid]; hMem
0x180003249  call    cs:__imp_LocalFree
0x18000324f  mov     rcx, [rsp+1F0h+Buffer]; Buffer
0x180003254  call    cs:__imp_LsaFreeMemory
0x18000325a  mov     rcx, [rsp+1F0h+PolicyHandle]; ObjectHandle
0x18000325f  test    rcx, rcx
0x180003262  jz      short loc_18000326A
0x180003264  call    cs:__imp_LsaClose
0x18000326a  test    ebx, ebx
0x18000326c  jns     short loc_180003278
0x18000326e  mov     ebx, 8007000Eh
0x180003273  jmp     loc_180003556
0x180003278  mov     r9, r12
0x18000327b  lea     r8, aSidS; "<sid=%s>"
0x180003282  mov     edx, 64h ; 'd'; unsigned __int64
0x180003287  lea     rcx, [rbp+0F0h+base]; unsigned __int16 *
0x18000328b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003290  mov     ebx, eax
0x180003292  test    eax, eax
0x180003294  js      loc_180003556
0x18000329a  lea     rax, aMsdsIsrodc; "msDS-isRODC"
0x1800032a1  mov     [rbp+0F0h+var_118], rsi
0x1800032a5  mov     [rbp+0F0h+var_128+8], rax
0x1800032a9  lea     r14, attr; "distinguishedName"
0x1800032b0  lea     rax, [rbp+0F0h+var_170]
0x1800032b4  mov     [rbp+0F0h+var_128], r14
0x1800032b8  mov     [rsp+1F0h+res], rax; res
0x1800032bd  lea     r9, filter; "(objectClass=*)"
0x1800032c4  mov     [rsp+1F0h+SizeLimit], esi; SizeLimit
0x1800032c8  lea     rax, [rbp+0F0h+var_128]
0x1800032cc  mov     [rsp+1F0h+timeout], rsi; timeout
0x1800032d1  lea     rdx, [rbp+0F0h+base]; base
0x1800032d5  mov     [rsp+1F0h+ClientControls], rsi; ClientControls
0x1800032da  xor     r8d, r8d; scope
0x1800032dd  mov     [rsp+1F0h+ServerControls], rsi; ServerControls
0x1800032e2  mov     rcx, r13; ld
0x1800032e5  mov     [rsp+1F0h+attrsonly], esi; attrsonly
0x1800032e9  mov     [rsp+1F0h+attrs], rax; attrs
0x1800032ee  call    cs:__imp_ldap_search_ext_sW
0x1800032f4  mov     edi, eax
0x1800032f6  test    eax, eax
0x1800032f8  jz      short loc_18000332E
0x1800032fa  mov     r9d, 29Ah; unsigned int
0x180003300  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003307  lea     rdx, aUlreturn; "ulReturn"
0x18000330e  mov     ecx, eax; unsigned int
0x180003310  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003315  test    edi, edi
0x180003317  jg      short loc_180003320
0x180003319  mov     ebx, edi
0x18000331b  jmp     loc_180003556
0x180003320  movzx   ebx, di
0x180003323  or      ebx, 80070000h
0x180003329  jmp     loc_180003556
0x18000332e  mov     rdx, [rbp+0F0h+var_170]; res
0x180003332  mov     rcx, r13; ld
0x180003335  call    cs:__imp_ldap_first_entry
0x18000333b  mov     r15, rax
0x18000333e  test    rax, rax
0x180003341  jnz     short loc_180003369
0x180003343  mov     r9d, 2A2h; unsigned int
0x180003349  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003350  lea     rdx, aLdapNoSuchObje; "LDAP_NO_SUCH_OBJECT"
0x180003357  lea     ecx, [rax+20h]; unsigned int
0x18000335a  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000335f  mov     ebx, 80070020h
0x180003364  jmp     loc_180003556
0x180003369  mov     r8, r14; attr
0x18000336c  mov     rdx, r15; entry
0x18000336f  mov     rcx, r13; ld
0x180003372  call    cs:__imp_ldap_get_valuesW
0x180003378  mov     r14, rax
0x18000337b  test    rax, rax
0x18000337e  jnz     short loc_1800033B3
0x180003380  call    cs:__imp_LdapGetLastError
0x180003386  mov     r9d, 2ACh; unsigned int
0x18000338c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003393  mov     ecx, eax; unsigned int
0x180003395  lea     rdx, aUlreturn; "ulReturn"
0x18000339c  mov     ebx, eax
0x18000339e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800033a3  test    ebx, ebx
0x1800033a5  jle     loc_180003556
0x1800033ab  movzx   ebx, bx
0x1800033ae  jmp     loc_180003323
0x1800033b3  mov     rcx, r14; vals
0x1800033b6  call    cs:__imp_ldap_count_valuesW
0x1800033bc  cmp     eax, 1
0x1800033bf  jnb     short loc_1800033EB
0x1800033c1  xor     edx, edx
0x1800033c3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800033ca  mov     edi, edx
0x1800033cc  mov     r9d, 2B4h; unsigned int
0x1800033d2  lea     rdx, aLdapNoSuchAttr; "LDAP_NO_SUCH_ATTRIBUTE"
0x1800033d9  lea     ecx, [rdi+10h]; unsigned int
0x1800033dc  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800033e1  mov     ebx, 80070010h
0x1800033e6  jmp     loc_180003532
0x1800033eb  mov     rcx, [r14]
0x1800033ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033f2  xor     edx, edx
0x1800033f4  inc     rax
0x1800033f7  cmp     [rcx+rax*2], dx
0x1800033fb  jnz     short loc_1800033F4
0x1800033fd  lea     r12, ds:2[rax*2]
0x180003405  mov     rcx, r12; unsigned __int64
0x180003408  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000340d  mov     rdi, rax
0x180003410  test    rax, rax
0x180003413  jnz     short loc_18000343D
0x180003415  mov     r9d, 2BEh; unsigned int
0x18000341b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003422  lea     rdx, aHr; "hr"
0x180003429  mov     ecx, 8007000Eh; unsigned int
0x18000342e  mov     ebx, 8007000Eh
0x180003433  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003438  jmp     loc_18000352D
0x18000343d  mov     rdx, [r14]; Src
0x180003440  mov     r8, r12; Size
0x180003443  mov     rcx, rdi; void *
0x180003446  call    memcpy_0
0x18000344b  lea     r8, aMsdsIsrodc; "msDS-isRODC"
0x180003452  mov     rdx, r15; entry
0x180003455  mov     rcx, r13; ld
0x180003458  call    cs:__imp_ldap_get_valuesW
0x18000345e  xor     r12d, r12d
0x180003461  mov     rsi, rax
0x180003464  test    rax, rax
0x180003467  jnz     short loc_1800034A2
0x180003469  call    cs:__imp_LdapGetLastError
0x18000346f  mov     r9d, 2C8h; unsigned int
0x180003475  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000347c  mov     ecx, eax; unsigned int
0x18000347e  lea     rdx, aUlreturn; "ulReturn"
0x180003485  mov     ebx, eax
0x180003487  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000348c  test    ebx, ebx
0x18000348e  jle     loc_18000352D
0x180003494  movzx   ebx, bx
0x180003497  or      ebx, 80070000h
0x18000349d  jmp     loc_18000352D
0x1800034a2  mov     rcx, rsi; vals
0x1800034a5  call    cs:__imp_ldap_count_valuesW
0x1800034ab  cmp     eax, 1
0x1800034ae  jnb     short loc_1800034D5
0x1800034b0  mov     r9d, 2D0h; unsigned int
0x1800034b6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800034bd  lea     rdx, aLdapNoSuchAttr; "LDAP_NO_SUCH_ATTRIBUTE"
0x1800034c4  mov     ecx, 10h; unsigned int
0x1800034c9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800034ce  mov     ebx, 80070010h
0x1800034d3  jmp     short loc_18000352D
0x1800034d5  mov     rcx, [rsi]; String1
0x1800034d8  lea     rdx, aTrue; "TRUE"
0x1800034df  call    wcscmp_0
0x1800034e4  mov     r9, [rbp+0F0h+var_168]
0x1800034e8  test    eax, eax
0x1800034ea  mov     rax, [rbp+0F0h+var_160]
0x1800034ee  mov     r8d, r12d
0x1800034f1  setz    r8b
0x1800034f5  mov     [r9], rdi
0x1800034f8  mov     rdi, r12
0x1800034fb  mov     [rax], r8d
0x1800034fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003505  lea     rax, WPP_GLOBAL_Control
0x18000350c  cmp     rcx, rax
0x18000350f  jz      short loc_18000352D
0x180003511  test    byte ptr [rcx+1Ch], 4
0x180003515  jz      short loc_18000352D
0x180003517  mov     r9, [r9]
0x18000351a  mov     edx, 0Fh
0x18000351f  mov     rcx, [rcx+10h]
0x180003523  mov     dword ptr [rsp+1F0h+attrs], r8d
0x180003528  call    WPP_SF_Sd
0x18000352d  mov     r12, [rsp+1F0h+var_190]
0x180003532  mov     rcx, r14; vals
0x180003535  call    cs:__imp_ldap_value_freeW
0x18000353b  test    rsi, rsi
0x18000353e  jz      short loc_180003549
0x180003540  mov     rcx, rsi; vals
0x180003543  call    cs:__imp_ldap_value_freeW
0x180003549  test    rdi, rdi
0x18000354c  jz      short loc_180003556
0x18000354e  mov     rcx, rdi; lpMem
0x180003551  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180003556  mov     rcx, [rbp+0F0h+var_170]; res
0x18000355a  test    rcx, rcx
0x18000355d  jz      short loc_180003565
0x18000355f  call    cs:__imp_ldap_msgfree
0x180003565  mov     rcx, r12; hMem
0x180003568  call    cs:__imp_LocalFree
0x18000356e  mov     eax, ebx
0x180003570  mov     rcx, [rbp+0F0h+var_40]
0x180003577  xor     rcx, rsp; StackCookie
0x18000357a  call    __security_check_cookie
0x18000357f  mov     rbx, [rsp+1F0h+arg_18]
0x180003587  add     rsp, 1C0h
0x18000358e  pop     r15
0x180003590  pop     r14
0x180003592  pop     r13
0x180003594  pop     r12
0x180003596  pop     rdi
0x180003597  pop     rsi
0x180003598  pop     rbp
0x180003599  retn
```
