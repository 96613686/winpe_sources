# GetSingleStringAttr

- ea: `0x180003b1c`
- end: `0x180003d75`
- name: `GetSingleStringAttr`
- size: `601`
- prototype: `__int64 __usercall@<rax>(LDAP *ld@<rcx>, PWSTR attr@<rdx>, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002bf0`
- `0x18000398c`

## callees

- `0x180003b1c`
- `0x180003e30`
- `0x180003e70`
- `0x180003ed0`
- `0x180010920`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x180003c41`
- `WLDAP32!__imp_LdapGetLastError` at `0x180003c41`
- `WLDAP32!__imp_ldap_first_entry` at `0x180003bf9`
- `WLDAP32!__imp_ldap_first_entry` at `0x180003bf9`
- `WLDAP32!__imp_ldap_msgfree` at `0x180003d36`
- `WLDAP32!__imp_ldap_msgfree` at `0x180003d36`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180003c59`
- `WLDAP32!__imp_ldap_count_valuesW` at `0x180003c59`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003c33`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180003c33`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180003bb1`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180003bb1`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003d23`
- `WLDAP32!__imp_ldap_value_freeW` at `0x180003d23`

## string_xrefs

- `0x180003bcc`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003c0a`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003c6a`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180003cbb`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GetSingleStringAttr(LDAP *ld, PWSTR attr, __int64 a3, __int64 a4, int a5, _QWORD *a6)
{
  ULONG v8; // eax
  ULONG LastError; // ebx
  unsigned int v10; // r9d
  unsigned int v11; // ecx
  LDAPMessage *entry; // rax
  PWCHAR *valuesW; // rax
  const void **v14; // rdi
  __int64 v15; // rax
  unsigned __int64 v16; // rbp
  void *v17; // rax
  void *v18; // rsi
  __int128 attrs; // [rsp+60h] [rbp-48h] BYREF
  PLDAPMessage res; // [rsp+C8h] [rbp+20h] BYREF

  attrs = 0;
  res = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), attr, a3, attr);
  attrs = (unsigned __int64)attr;
  v8 = ldap_search_ext_sW(ld, 0, 0, (const PWSTR)L"(objectClass=*)", (PZPWSTR)&attrs, 0, 0, 0, 0, 0, &res);
  LastError = v8;
  if ( v8 )
  {
    v10 = 191;
    v11 = v8;
    goto LABEL_6;
  }
  entry = ldap_first_entry(ld, res);
  if ( !entry )
  {
    SidKeyDebugTraceError(
      0x20u,
      "LDAP_NO_SUCH_OBJECT",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
      0xC7u);
    LastError = -2147024864;
    goto LABEL_22;
  }
  valuesW = ldap_get_valuesW(ld, entry, attr);
  v14 = (const void **)valuesW;
  if ( !valuesW )
  {
    LastError = LdapGetLastError();
    v11 = LastError;
    v10 = 208;
LABEL_6:
    SidKeyDebugTraceError(v11, "ulReturn", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v10);
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_22;
  }
  if ( ldap_count_valuesW(valuesW) )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)*v14 + v15) );
    v16 = 2 * v15 + 2;
    v17 = SIDKeyProvAlloc(v16);
    v18 = v17;
    if ( v17 )
    {
      LastError = 0;
      memcpy_0(v17, *v14, v16);
      *a6 = v18;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids, v18);
    }
    else
    {
      LastError = -2147024882;
      SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0xE4u);
    }
  }
  else
  {
    SidKeyDebugTraceError(
      0x10u,
      "LDAP_NO_SUCH_ATTRIBUTE",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
      0xD8u);
    LastError = -2147024880;
  }
  ldap_value_freeW((PWCHAR *)v14);
LABEL_22:
  if ( res )
    ldap_msgfree(res);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180003b1c  mov     rax, rsp
0x180003b1f  mov     [rax+20h], r9
0x180003b23  push    rbx
0x180003b24  push    rbp
0x180003b25  push    rsi
0x180003b26  push    rdi
0x180003b27  push    r12
0x180003b29  push    r14
0x180003b2b  sub     rsp, 78h
0x180003b2f  xorps   xmm0, xmm0
0x180003b32  xor     r14d, r14d
0x180003b35  movups  xmmword ptr [rax-48h], xmm0
0x180003b39  mov     [rax+20h], r14
0x180003b3d  mov     rdi, rdx
0x180003b40  mov     rsi, rcx
0x180003b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b4a  lea     r12, WPP_GLOBAL_Control
0x180003b51  cmp     rcx, r12
0x180003b54  jz      short loc_180003B68
0x180003b56  test    byte ptr [rcx+1Ch], 4
0x180003b5a  jz      short loc_180003B68
0x180003b5c  mov     rcx, [rcx+10h]
0x180003b60  mov     r9, rdx
0x180003b63  call    WPP_SF_SSS
0x180003b68  lea     rax, [rsp+0A8h+arg_18]
0x180003b70  mov     [rsp+0A8h+var_48], rdi
0x180003b75  mov     [rsp+0A8h+res], rax; res
0x180003b7a  lea     r9, filter; "(objectClass=*)"
0x180003b81  mov     [rsp+0A8h+SizeLimit], r14d; SizeLimit
0x180003b86  lea     rax, [rsp+0A8h+var_48]
0x180003b8b  mov     [rsp+0A8h+timeout], r14; timeout
0x180003b90  xor     r8d, r8d; scope
0x180003b93  mov     [rsp+0A8h+ClientControls], r14; ClientControls
0x180003b98  xor     edx, edx; base
0x180003b9a  mov     [rsp+0A8h+ServerControls], r14; ServerControls
0x180003b9f  mov     rcx, rsi; ld
0x180003ba2  mov     [rsp+0A8h+attrsonly], r14d; attrsonly
0x180003ba7  mov     [rsp+0A8h+attrs], rax; attrs
0x180003bac  mov     [rsp+0A8h+var_40], r14
0x180003bb1  call    cs:__imp_ldap_search_ext_sW
0x180003bb7  mov     ebx, eax
0x180003bb9  test    eax, eax
0x180003bbb  jz      short loc_180003BEE
0x180003bbd  mov     r9d, 0BFh; unsigned int
0x180003bc3  mov     ecx, eax; unsigned int
0x180003bc5  lea     rdx, aUlreturn; "ulReturn"
0x180003bcc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003bd3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003bd8  test    ebx, ebx
0x180003bda  jle     loc_180003D29
0x180003be0  movzx   ebx, bx
0x180003be3  or      ebx, 80070000h
0x180003be9  jmp     loc_180003D29
0x180003bee  mov     rdx, [rsp+0A8h+arg_18]; res
0x180003bf6  mov     rcx, rsi; ld
0x180003bf9  call    cs:__imp_ldap_first_entry
0x180003bff  test    rax, rax
0x180003c02  jnz     short loc_180003C2A
0x180003c04  mov     r9d, 0C7h; unsigned int
0x180003c0a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003c11  lea     rdx, aLdapNoSuchObje; "LDAP_NO_SUCH_OBJECT"
0x180003c18  lea     ecx, [rax+20h]; unsigned int
0x180003c1b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003c20  mov     ebx, 80070020h
0x180003c25  jmp     loc_180003D29
0x180003c2a  mov     r8, rdi; attr
0x180003c2d  mov     rdx, rax; entry
0x180003c30  mov     rcx, rsi; ld
0x180003c33  call    cs:__imp_ldap_get_valuesW
0x180003c39  mov     rdi, rax
0x180003c3c  test    rax, rax
0x180003c3f  jnz     short loc_180003C56
0x180003c41  call    cs:__imp_LdapGetLastError
0x180003c47  mov     ebx, eax
0x180003c49  mov     ecx, eax
0x180003c4b  mov     r9d, 0D0h
0x180003c51  jmp     loc_180003BC5
0x180003c56  mov     rcx, rdi; vals
0x180003c59  call    cs:__imp_ldap_count_valuesW
0x180003c5f  cmp     eax, 1
0x180003c62  jnb     short loc_180003C8C
0x180003c64  mov     r9d, 0D8h; unsigned int
0x180003c6a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003c71  lea     rdx, aLdapNoSuchAttr; "LDAP_NO_SUCH_ATTRIBUTE"
0x180003c78  mov     ecx, 10h; unsigned int
0x180003c7d  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003c82  mov     ebx, 80070010h
0x180003c87  jmp     loc_180003D20
0x180003c8c  mov     rcx, [rdi]
0x180003c8f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003c93  inc     rax
0x180003c96  cmp     [rcx+rax*2], r14w
0x180003c9b  jnz     short loc_180003C93
0x180003c9d  lea     rbp, ds:2[rax*2]
0x180003ca5  mov     rcx, rbp; unsigned __int64
0x180003ca8  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180003cad  mov     rsi, rax
0x180003cb0  test    rax, rax
0x180003cb3  jnz     short loc_180003CDA
0x180003cb5  mov     r9d, 0E4h; unsigned int
0x180003cbb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003cc2  lea     rdx, aHr; "hr"
0x180003cc9  mov     ecx, 8007000Eh; unsigned int
0x180003cce  mov     ebx, 8007000Eh
0x180003cd3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180003cd8  jmp     short loc_180003D20
0x180003cda  mov     rdx, [rdi]; Src
0x180003cdd  mov     r8, rbp; Size
0x180003ce0  mov     rcx, rsi; void *
0x180003ce3  mov     ebx, r14d
0x180003ce6  call    memcpy_0
0x180003ceb  mov     rax, [rsp+0A8h+arg_28]
0x180003cf3  mov     [rax], rsi
0x180003cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cfd  cmp     rcx, r12
0x180003d00  jz      short loc_180003D20
0x180003d02  test    byte ptr [rcx+1Ch], 4
0x180003d06  jz      short loc_180003D20
0x180003d08  mov     rcx, [rcx+10h]
0x180003d0c  lea     r8, WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids
0x180003d13  mov     edx, 0Bh
0x180003d18  mov     r9, rsi
0x180003d1b  call    WPP_SF_S
0x180003d20  mov     rcx, rdi; vals
0x180003d23  call    cs:__imp_ldap_value_freeW
0x180003d29  mov     rcx, [rsp+0A8h+arg_18]; res
0x180003d31  test    rcx, rcx
0x180003d34  jz      short loc_180003D3C
0x180003d36  call    cs:__imp_ldap_msgfree
0x180003d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d43  cmp     rcx, r12
0x180003d46  jz      short loc_180003D66
0x180003d48  test    byte ptr [rcx+1Ch], 4
0x180003d4c  jz      short loc_180003D66
0x180003d4e  mov     rcx, [rcx+10h]
0x180003d52  lea     r8, WPP_6c0ca72a727531d2107e7efc67d3e2a5_Traceguids
0x180003d59  mov     edx, 0Ch
0x180003d5e  mov     r9d, ebx
0x180003d61  call    WPP_SF_D
0x180003d66  mov     eax, ebx
0x180003d68  add     rsp, 78h
0x180003d6c  pop     r14
0x180003d6e  pop     r12
0x180003d70  pop     rdi
0x180003d71  pop     rsi
0x180003d72  pop     rbp
0x180003d73  pop     rbx
0x180003d74  retn
```
