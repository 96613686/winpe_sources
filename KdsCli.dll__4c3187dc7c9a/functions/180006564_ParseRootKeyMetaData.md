# ParseRootKeyMetaData

- ea: `0x180006564`
- end: `0x180006900`
- name: `ParseRootKeyMetaData`
- size: `924`
- prototype: `__int64 __fastcall(LDAP *ld, LDAPMessage *entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800054e0`

## callees

- `0x180003e08`
- `0x180003e30`
- `0x180003e70`
- `0x180006564`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a694`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18000664a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800066d6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18000664a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800066d6`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800068a3`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800068a3`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180006602`
- `WLDAP32!__imp_ldap_first_attributeW` at `0x180006602`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006616`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180006616`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800067ee`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800068f5`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800067ee`
- `WLDAP32!__imp_ldap_memfreeW` at `0x1800068f5`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18000680d`
- `WLDAP32!__imp_ldap_next_attributeW` at `0x18000680d`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800067f7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800068e3`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800067f7`
- `WLDAP32!__imp_ldap_value_freeW` at `0x1800068e3`
- `WLDAP32!__imp_ber_free` at `0x18000683a`
- `WLDAP32!__imp_ber_free` at `0x18000683a`
- `RPCRT4!UuidFromStringW` at `0x18000678d`
- `RPCRT4!UuidFromStringW` at `0x18000678d`

## string_xrefs

- `0x1800065d2`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180006663`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x1800066ef`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x18000679d`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180006884`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x1800068af`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180006634`: `msKds-CreateTime`

## pseudocode

```c
__int64 __fastcall ParseRootKeyMetaData(LDAP *ld, LDAPMessage *entry, UUID **a3)
{
  LDAP *v4; // rsi
  UUID *v5; // r14
  ULONG LastError; // ebx
  WCHAR *i; // rax
  PWCHAR *valuesW; // rax
  PWCHAR *v9; // r12
  wchar_t *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  WCHAR *v15; // rdi
  BerElement *ptr; // [rsp+68h] [rbp+20h] BYREF

  ptr = 0;
  v4 = ld;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids);
  v5 = (UUID *)SIDKeyProvAlloc(0x20u);
  if ( !v5 )
  {
    LastError = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x42Du);
    goto LABEL_33;
  }
  LastError = 0;
  for ( i = ldap_first_attributeW(v4, entry, &ptr); ; i = ldap_next_attributeW(ld, entry, ptr) )
  {
    v15 = i;
    if ( !i )
    {
      *a3 = v5;
      goto LABEL_33;
    }
    valuesW = ldap_get_valuesW(v4, entry, i);
    v9 = valuesW;
    if ( !valuesW )
      break;
    v10 = *valuesW;
    if ( !*valuesW )
    {
      LastError = -2147024880;
      SidKeyDebugTraceError(
        0x80070010,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
        0x446u);
      goto LABEL_42;
    }
    if ( !wcscmp_0(v15, L"msKds-CreateTime") )
    {
      v11 = _wtoi64(v10);
      *(_QWORD *)&v5[1].Data1 = v11;
      if ( !v11 )
      {
        LastError = -2146893821;
        SidKeyDebugTraceError(
          0x80090003,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x451u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
        goto LABEL_42;
      }
    }
    else if ( !wcscmp_0(v15, L"msKds-UseStartTime") )
    {
      v12 = _wtoi64(v10);
      *(_QWORD *)v5[1].Data4 = v12;
      if ( !v12 )
      {
        LastError = -2146893821;
        SidKeyDebugTraceError(
          0x80090003,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x45Cu);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 25;
LABEL_29:
          WPP_SF_S(v13[2], v14, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
        }
      }
    }
    else if ( *v15 == 99 && v15[1] == 110 && !v15[2] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, v10);
      if ( UuidFromStringW(v10, v5) )
      {
        LastError = -2146893821;
        SidKeyDebugTraceError(
          0x80090003,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
          0x46Au);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 27;
          goto LABEL_29;
        }
      }
    }
    ldap_memfreeW(v15);
    ldap_value_freeW(v9);
    v4 = ld;
  }
  LastError = LdapGetLastError();
  SidKeyDebugTraceError(
    LastError,
    "ulReturn",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
    0x43Cu);
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_42:
  SIDKeyProvFree(v5);
  if ( v9 )
    ldap_value_freeW(v9);
  if ( v15 )
    ldap_memfreeW(v15);
LABEL_33:
  if ( ptr )
    ber_free(ptr, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180006564  mov     rax, rsp
0x180006567  mov     [rax+10h], rbx
0x18000656b  mov     [rax+18h], r8
0x18000656f  mov     [rax+8], rcx
0x180006573  push    rsi
0x180006574  push    rdi
0x180006575  push    r12
0x180006577  push    r13
0x180006579  push    r14
0x18000657b  sub     rsp, 20h
0x18000657f  xor     r12d, r12d
0x180006582  mov     r13, rdx
0x180006585  mov     [rax+20h], r12
0x180006589  mov     rsi, rcx
0x18000658c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006593  lea     rdi, WPP_GLOBAL_Control
0x18000659a  cmp     rcx, rdi
0x18000659d  jz      short loc_1800065BA
0x18000659f  test    byte ptr [rcx+1Ch], 4
0x1800065a3  jz      short loc_1800065BA
0x1800065a5  mov     rcx, [rcx+10h]
0x1800065a9  lea     edx, [r12+17h]
0x1800065ae  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x1800065b5  call    WPP_SF_
0x1800065ba  mov     ecx, 20h ; ' '; unsigned __int64
0x1800065bf  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800065c4  mov     r14, rax
0x1800065c7  test    rax, rax
0x1800065ca  jnz     short loc_1800065F4
0x1800065cc  mov     r9d, 42Dh; unsigned int
0x1800065d2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800065d9  lea     rdx, aHr; "hr"
0x1800065e0  mov     ecx, 8007000Eh; unsigned int
0x1800065e5  mov     ebx, 8007000Eh
0x1800065ea  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800065ef  jmp     loc_18000682E
0x1800065f4  lea     r8, [rsp+48h+ptr]; ptr
0x1800065f9  mov     rdx, r13; entry
0x1800065fc  mov     rcx, rsi; ld
0x1800065ff  mov     ebx, r12d
0x180006602  call    cs:__imp_ldap_first_attributeW
0x180006608  jmp     loc_180006813
0x18000660d  mov     r8, rdi; attr
0x180006610  mov     rdx, r13; entry
0x180006613  mov     rcx, rsi; ld
0x180006616  call    cs:__imp_ldap_get_valuesW
0x18000661c  mov     r12, rax
0x18000661f  test    rax, rax
0x180006622  jz      loc_1800068A3
0x180006628  mov     rsi, [rax]
0x18000662b  test    rsi, rsi
0x18000662e  jz      loc_18000687E
0x180006634  lea     rdx, aMskdsCreatetim; "msKds-CreateTime"
0x18000663b  mov     rcx, rdi; String1
0x18000663e  call    wcscmp_0
0x180006643  test    eax, eax
0x180006645  jnz     short loc_1800066BE
0x180006647  mov     rcx, rsi; String
0x18000664a  call    cs:__imp__wtoi64
0x180006650  mov     [r14+10h], rax
0x180006654  test    rax, rax
0x180006657  jnz     loc_1800067EB
0x18000665d  mov     r9d, 451h; unsigned int
0x180006663  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000666a  lea     rdx, aHr; "hr"
0x180006671  mov     ecx, 80090003h; unsigned int
0x180006676  mov     ebx, 80090003h
0x18000667b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180006680  mov     rcx, cs:WPP_GLOBAL_Control
0x180006687  lea     rax, WPP_GLOBAL_Control
0x18000668e  cmp     rcx, rax
0x180006691  jz      loc_1800068D3
0x180006697  test    byte ptr [rcx+1Ch], 1
0x18000669b  jz      loc_1800068D3
0x1800066a1  mov     rcx, [rcx+10h]
0x1800066a5  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x1800066ac  mov     edx, 18h
0x1800066b1  mov     r9, rsi
0x1800066b4  call    WPP_SF_S
0x1800066b9  jmp     loc_1800068D3
0x1800066be  lea     rdx, aMskdsUsestartt; "msKds-UseStartTime"
0x1800066c5  mov     rcx, rdi; String1
0x1800066c8  call    wcscmp_0
0x1800066cd  xor     ecx, ecx
0x1800066cf  test    eax, eax
0x1800066d1  jnz     short loc_180006737
0x1800066d3  mov     rcx, rsi; String
0x1800066d6  call    cs:__imp__wtoi64
0x1800066dc  mov     [r14+18h], rax
0x1800066e0  test    rax, rax
0x1800066e3  jnz     loc_1800067EB
0x1800066e9  mov     r9d, 45Ch; unsigned int
0x1800066ef  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800066f6  lea     rdx, aHr; "hr"
0x1800066fd  mov     ecx, 80090003h; unsigned int
0x180006702  mov     ebx, 80090003h
0x180006707  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000670c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006713  lea     rax, WPP_GLOBAL_Control
0x18000671a  cmp     rcx, rax
0x18000671d  jz      loc_1800067EB
0x180006723  test    byte ptr [rcx+1Ch], 1
0x180006727  jz      loc_1800067EB
0x18000672d  mov     edx, 19h
0x180006732  jmp     loc_1800067D8
0x180006737  cmp     word ptr [rdi], 63h ; 'c'
0x18000673b  jnz     loc_1800067EB
0x180006741  cmp     word ptr [rdi+2], 6Eh ; 'n'
0x180006746  jnz     loc_1800067EB
0x18000674c  cmp     [rdi+4], cx
0x180006750  jnz     loc_1800067EB
0x180006756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000675d  lea     rax, WPP_GLOBAL_Control
0x180006764  cmp     rcx, rax
0x180006767  jz      short loc_180006787
0x180006769  test    byte ptr [rcx+1Ch], 4
0x18000676d  jz      short loc_180006787
0x18000676f  mov     rcx, [rcx+10h]
0x180006773  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x18000677a  mov     edx, 1Ah
0x18000677f  mov     r9, rsi
0x180006782  call    WPP_SF_S
0x180006787  mov     rdx, r14; Uuid
0x18000678a  mov     rcx, rsi; StringUuid
0x18000678d  call    cs:__imp_UuidFromStringW
0x180006793  test    eax, eax
0x180006795  jz      short loc_1800067EB
0x180006797  mov     r9d, 46Ah; unsigned int
0x18000679d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800067a4  lea     rdx, aHr; "hr"
0x1800067ab  mov     ecx, 80090003h; unsigned int
0x1800067b0  mov     ebx, 80090003h
0x1800067b5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800067ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067c1  lea     rax, WPP_GLOBAL_Control
0x1800067c8  cmp     rcx, rax
0x1800067cb  jz      short loc_1800067EB
0x1800067cd  test    byte ptr [rcx+1Ch], 1
0x1800067d1  jz      short loc_1800067EB
0x1800067d3  mov     edx, 1Bh
0x1800067d8  mov     rcx, [rcx+10h]
0x1800067dc  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x1800067e3  mov     r9, rsi
0x1800067e6  call    WPP_SF_S
0x1800067eb  mov     rcx, rdi; Block
0x1800067ee  call    cs:__imp_ldap_memfreeW
0x1800067f4  mov     rcx, r12; vals
0x1800067f7  call    cs:__imp_ldap_value_freeW
0x1800067fd  mov     rsi, [rsp+48h+ld]
0x180006802  mov     rdx, r13; entry
0x180006805  mov     r8, [rsp+48h+ptr]; ptr
0x18000680a  mov     rcx, rsi; ld
0x18000680d  call    cs:__imp_ldap_next_attributeW
0x180006813  mov     rdi, rax
0x180006816  test    rax, rax
0x180006819  jnz     loc_18000660D
0x18000681f  mov     rax, [rsp+48h+arg_10]
0x180006824  mov     [rax], r14
0x180006827  lea     rdi, WPP_GLOBAL_Control
0x18000682e  mov     rcx, [rsp+48h+ptr]
0x180006833  test    rcx, rcx
0x180006836  jz      short loc_180006840
0x180006838  xor     edx, edx
0x18000683a  call    cs:__imp_ber_free
0x180006840  mov     rcx, cs:WPP_GLOBAL_Control
0x180006847  cmp     rcx, rdi
0x18000684a  jz      short loc_18000686A
0x18000684c  test    byte ptr [rcx+1Ch], 4
0x180006850  jz      short loc_18000686A
0x180006852  mov     rcx, [rcx+10h]
0x180006856  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x18000685d  mov     edx, 1Ch
0x180006862  mov     r9d, ebx
0x180006865  call    WPP_SF_D
0x18000686a  mov     eax, ebx
0x18000686c  mov     rbx, [rsp+48h+arg_8]
0x180006871  add     rsp, 20h
0x180006875  pop     r14
0x180006877  pop     r13
0x180006879  pop     r12
0x18000687b  pop     rdi
0x18000687c  pop     rsi
0x18000687d  retn
0x18000687e  mov     r9d, 446h; unsigned int
0x180006884  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000688b  lea     rdx, aHr; "hr"
0x180006892  mov     ecx, 80070010h; unsigned int
0x180006897  mov     ebx, 80070010h
0x18000689c  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800068a1  jmp     short loc_1800068D3
0x1800068a3  call    cs:__imp_LdapGetLastError
0x1800068a9  mov     r9d, 43Ch; unsigned int
0x1800068af  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800068b6  mov     ecx, eax; unsigned int
0x1800068b8  lea     rdx, aUlreturn; "ulReturn"
0x1800068bf  mov     ebx, eax
0x1800068c1  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800068c6  test    ebx, ebx
0x1800068c8  jle     short loc_1800068D3
0x1800068ca  movzx   ebx, bx
0x1800068cd  or      ebx, 80070000h
0x1800068d3  mov     rcx, r14; lpMem
0x1800068d6  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800068db  test    r12, r12
0x1800068de  jz      short loc_1800068E9
0x1800068e0  mov     rcx, r12; vals
0x1800068e3  call    cs:__imp_ldap_value_freeW
0x1800068e9  test    rdi, rdi
0x1800068ec  jz      loc_180006827
0x1800068f2  mov     rcx, rdi; Block
0x1800068f5  call    cs:__imp_ldap_memfreeW
0x1800068fb  jmp     loc_180006827
```
