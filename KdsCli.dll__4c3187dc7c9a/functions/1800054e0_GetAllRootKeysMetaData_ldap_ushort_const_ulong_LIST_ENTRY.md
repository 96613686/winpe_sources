# GetAllRootKeysMetaData(ldap *,ushort const *,ulong *,_LIST_ENTRY * *)

- ea: `0x1800054e0`
- end: `0x180005738`
- name: `?GetAllRootKeysMetaData@@YAJPEAUldap@@PEBGPEAKPEAPEAU_LIST_ENTRY@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, unsigned int *, struct _LIST_ENTRY **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008afc`
- `0x180008cf0`

## callees

- `0x180001630`
- `0x180003e08`
- `0x180004568`
- `0x180004f40`
- `0x1800054e0`
- `0x180006564`
- `0x180010920`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x1800055d5`
- `WLDAP32!__imp_LdapGetLastError` at `0x1800055d5`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000564b`
- `WLDAP32!__imp_ldap_first_entry` at `0x18000564b`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800056c5`
- `WLDAP32!__imp_ldap_next_entry` at `0x1800056c5`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800055c7`
- `WLDAP32!__imp_ldap_count_entries` at `0x1800055c7`
- `WLDAP32!__imp_ldap_msgfree` at `0x180005703`
- `WLDAP32!__imp_ldap_msgfree` at `0x180005703`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180005575`
- `WLDAP32!__imp_ldap_search_ext_sW` at `0x180005575`

## string_xrefs

- `0x18000557b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x1800056e5`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180005523`: `msKds-CreateTime`

## pseudocode

```c
__int64 __fastcall GetAllRootKeysMetaData(LDAP *ld, WCHAR *a2, unsigned int *a3, struct _LIST_ENTRY **a4)
{
  int LastError; // ebx
  struct _LIST_ENTRY *v7; // rdi
  signed int v9; // eax
  unsigned int v10; // r9d
  unsigned int v11; // ecx
  ULONG v12; // r15d
  struct _LIST_ENTRY *v13; // rax
  LDAPMessage *entry; // rsi
  int v15; // eax
  PLDAPMessage res; // [rsp+60h] [rbp-29h] BYREF
  struct __ROOT_KEY_METADATA *v18; // [rsp+68h] [rbp-21h] BYREF
  PWSTR attrs[4]; // [rsp+70h] [rbp-19h] BYREF

  LastError = 0;
  res = 0;
  attrs[3] = 0;
  attrs[0] = (PWSTR)L"msKds-UseStartTime";
  attrs[1] = (PWSTR)L"msKds-CreateTime";
  v7 = 0;
  attrs[2] = L"cn";
  v9 = ldap_search_ext_sW(ld, a2, 1u, (const PWSTR)L"(objectClass=msKds-ProvRootKey)", attrs, 0, 0, 0, 0, 0, &res);
  if ( v9 )
  {
    if ( v9 > 0 )
      LastError = (unsigned __int16)v9 | 0x80070000;
    else
      LastError = v9;
    SidKeyDebugTraceError(LastError, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", 0x589u);
  }
  if ( LastError < 0 )
  {
    v10 = 1525;
    v11 = LastError;
LABEL_23:
    SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v10);
    goto LABEL_24;
  }
  v12 = ldap_count_entries(ld, res);
  if ( v12 == -1 )
  {
    LastError = LdapGetLastError();
    SidKeyDebugTraceError(
      LastError,
      "ulLdapError",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
      0x5FFu);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( !a4 )
      goto LABEL_24;
    v13 = (struct _LIST_ENTRY *)SIDKeyProvAlloc(0x10u);
    v7 = v13;
    if ( !v13 )
    {
      LastError = -2147024882;
      v10 = 1550;
      v11 = -2147024882;
      goto LABEL_23;
    }
    v13->Blink = v13;
    v13->Flink = v13;
    entry = ldap_first_entry(ld, res);
    if ( entry )
    {
      while ( 1 )
      {
        v18 = 0;
        v15 = ParseRootKeyMetaData(ld, entry, (UUID **)&v18);
        LastError = v15;
        if ( v15 < 0 )
          break;
        LastError = AddRootMetaDataToSortedList(v18, v7);
        if ( LastError < 0 )
          goto LABEL_24;
        entry = ldap_next_entry(ld, entry);
        if ( !entry )
        {
          *a3 = v12;
          *a4 = v7;
          v7 = 0;
          goto LABEL_24;
        }
      }
      v10 = 1574;
      v11 = v15;
      goto LABEL_23;
    }
    LastError = -2147024864;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids);
  }
LABEL_24:
  if ( res )
    ldap_msgfree(res);
  if ( v7 )
    FreeRootKeyMetaDataList(v7);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800054e0  push    rbp
0x1800054e2  push    rbx
0x1800054e3  push    rsi
0x1800054e4  push    rdi
0x1800054e5  push    r12
0x1800054e7  push    r13
0x1800054e9  push    r14
0x1800054eb  push    r15
0x1800054ed  lea     rbp, [rsp-1Fh]
0x1800054f2  sub     rsp, 0A8h
0x1800054f9  mov     rax, cs:__security_cookie
0x180005500  xor     rax, rsp
0x180005503  mov     [rbp+57h+var_50], rax
0x180005507  xor     ebx, ebx
0x180005509  mov     [rbp+57h+var_80], 0
0x180005511  lea     rax, aMskdsUsestartt; "msKds-UseStartTime"
0x180005518  mov     [rbp+57h+var_58], rbx
0x18000551c  mov     [rbp+57h+var_70], rax
0x180005520  mov     r12, r9
0x180005523  lea     rax, aMskdsCreatetim; "msKds-CreateTime"
0x18000552a  mov     r13, r8
0x18000552d  mov     [rbp+57h+var_68], rax
0x180005531  lea     r9, aObjectclassMsk; "(objectClass=msKds-ProvRootKey)"
0x180005538  lea     rax, aCn; "cn"
0x18000553f  xor     edi, edi
0x180005541  mov     [rbp+57h+var_60], rax
0x180005545  mov     r14, rcx
0x180005548  lea     rax, [rbp+57h+var_80]
0x18000554c  mov     [rsp+0E0h+res], rax; res
0x180005551  lea     rax, [rbp+57h+var_70]
0x180005555  mov     [rsp+0E0h+SizeLimit], ebx; SizeLimit
0x180005559  lea     r8d, [rdi+1]; scope
0x18000555d  mov     [rsp+0E0h+timeout], rbx; timeout
0x180005562  mov     [rsp+0E0h+ClientControls], rbx; ClientControls
0x180005567  mov     [rsp+0E0h+ServerControls], rbx; ServerControls
0x18000556c  mov     [rsp+0E0h+attrsonly], ebx; attrsonly
0x180005570  mov     [rsp+0E0h+attrs], rax; attrs
0x180005575  call    cs:__imp_ldap_search_ext_sW
0x18000557b  lea     rsi, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180005582  test    eax, eax
0x180005584  jz      short loc_1800055AC
0x180005586  jg      short loc_18000558C
0x180005588  mov     ebx, eax
0x18000558a  jmp     short loc_180005595
0x18000558c  movzx   ebx, ax
0x18000558f  or      ebx, 80070000h
0x180005595  mov     r9d, 589h; unsigned int
0x18000559b  lea     rdx, aHr; "hr"
0x1800055a2  mov     r8, rsi; char *
0x1800055a5  mov     ecx, ebx; unsigned int
0x1800055a7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800055ac  test    ebx, ebx
0x1800055ae  jns     short loc_1800055C0
0x1800055b0  mov     r9d, 5F5h
0x1800055b6  mov     r8, rsi
0x1800055b9  mov     ecx, ebx
0x1800055bb  jmp     loc_1800056EE
0x1800055c0  mov     rdx, [rbp+57h+var_80]; res
0x1800055c4  mov     rcx, r14; ld
0x1800055c7  call    cs:__imp_ldap_count_entries
0x1800055cd  mov     r15d, eax
0x1800055d0  cmp     eax, 0FFFFFFFFh
0x1800055d3  jnz     short loc_18000560A
0x1800055d5  call    cs:__imp_LdapGetLastError
0x1800055db  mov     r9d, 5FFh; unsigned int
0x1800055e1  lea     rdx, aUlldaperror; "ulLdapError"
0x1800055e8  mov     ecx, eax; unsigned int
0x1800055ea  mov     r8, rsi; char *
0x1800055ed  mov     ebx, eax
0x1800055ef  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800055f4  test    ebx, ebx
0x1800055f6  jle     loc_1800056FA
0x1800055fc  movzx   ebx, bx
0x1800055ff  or      ebx, 80070000h
0x180005605  jmp     loc_1800056FA
0x18000560a  test    r12, r12
0x18000560d  jz      loc_1800056FA
0x180005613  mov     ecx, 10h; unsigned __int64
0x180005618  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000561d  mov     rdi, rax
0x180005620  test    rax, rax
0x180005623  jnz     short loc_18000563D
0x180005625  mov     ebx, 8007000Eh
0x18000562a  mov     r9d, 60Eh
0x180005630  mov     r8, rsi
0x180005633  mov     ecx, 8007000Eh
0x180005638  jmp     loc_1800056EE
0x18000563d  mov     [rax+8], rdi
0x180005641  mov     rcx, r14; ld
0x180005644  mov     [rax], rdi
0x180005647  mov     rdx, [rbp+57h+var_80]; res
0x18000564b  call    cs:__imp_ldap_first_entry
0x180005651  mov     rsi, rax
0x180005654  test    rax, rax
0x180005657  jnz     short loc_180005690
0x180005659  mov     ebx, 80070020h
0x18000565e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005665  lea     rax, WPP_GLOBAL_Control
0x18000566c  cmp     rcx, rax
0x18000566f  jz      loc_1800056FA
0x180005675  test    byte ptr [rcx+1Ch], 4
0x180005679  jz      short loc_1800056FA
0x18000567b  mov     rcx, [rcx+10h]
0x18000567f  lea     edx, [rsi+20h]
0x180005682  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x180005689  call    WPP_SF_
0x18000568e  jmp     short loc_1800056FA
0x180005690  lea     r8, [rbp+57h+var_78]
0x180005694  mov     [rbp+57h+var_78], 0
0x18000569c  mov     rdx, rsi; entry
0x18000569f  mov     rcx, r14; ld
0x1800056a2  call    ParseRootKeyMetaData
0x1800056a7  mov     ebx, eax
0x1800056a9  test    eax, eax
0x1800056ab  js      short loc_1800056DF
0x1800056ad  mov     rcx, [rbp+57h+var_78]; struct __ROOT_KEY_METADATA *
0x1800056b1  mov     rdx, rdi; struct _LIST_ENTRY *
0x1800056b4  call    ?AddRootMetaDataToSortedList@@YAJPEAU__ROOT_KEY_METADATA@@PEAU_LIST_ENTRY@@@Z; AddRootMetaDataToSortedList(__ROOT_KEY_METADATA *,_LIST_ENTRY *)
0x1800056b9  mov     ebx, eax
0x1800056bb  test    eax, eax
0x1800056bd  js      short loc_1800056FA
0x1800056bf  mov     rdx, rsi; entry
0x1800056c2  mov     rcx, r14; ld
0x1800056c5  call    cs:__imp_ldap_next_entry
0x1800056cb  mov     rsi, rax
0x1800056ce  test    rax, rax
0x1800056d1  jnz     short loc_180005690
0x1800056d3  mov     [r13+0], r15d
0x1800056d7  mov     [r12], rdi
0x1800056db  xor     edi, edi
0x1800056dd  jmp     short loc_1800056FA
0x1800056df  mov     r9d, 626h; unsigned int
0x1800056e5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800056ec  mov     ecx, eax; unsigned int
0x1800056ee  lea     rdx, aHr; "hr"
0x1800056f5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800056fa  mov     rcx, [rbp+57h+var_80]; res
0x1800056fe  test    rcx, rcx
0x180005701  jz      short loc_180005709
0x180005703  call    cs:__imp_ldap_msgfree
0x180005709  test    rdi, rdi
0x18000570c  jz      short loc_180005716
0x18000570e  mov     rcx, rdi; lpMem
0x180005711  call    ?FreeRootKeyMetaDataList@@YAXPEAU_LIST_ENTRY@@@Z; FreeRootKeyMetaDataList(_LIST_ENTRY *)
0x180005716  mov     eax, ebx
0x180005718  mov     rcx, [rbp+57h+var_50]
0x18000571c  xor     rcx, rsp; StackCookie
0x18000571f  call    __security_check_cookie
0x180005724  add     rsp, 0A8h
0x18000572b  pop     r15
0x18000572d  pop     r14
0x18000572f  pop     r13
0x180005731  pop     r12
0x180005733  pop     rdi
0x180005734  pop     rsi
0x180005735  pop     rbx
0x180005736  pop     rbp
0x180005737  retn
```
