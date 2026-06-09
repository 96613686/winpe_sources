# QueryADSnapshotBrowserDomainNames(ldap *,_AD_LDAP_BROWSER_STATE *)

- ea: `0x180009ba4`
- end: `0x180009dfe`
- name: `?QueryADSnapshotBrowserDomainNames@@YAJPEAUldap@@PEAU_AD_LDAP_BROWSER_STATE@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(LDAP *ld, struct _AD_LDAP_BROWSER_STATE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009148`

## callees

- `0x180001630`
- `0x180003e08`
- `0x180009ba4`
- `0x180010850`
- `0x18001a450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ce8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180009ce8`
- `WLDAP32!__imp_ldap_first_entry` at `0x180009c95`
- `WLDAP32!__imp_ldap_first_entry` at `0x180009c95`
- `WLDAP32!__imp_ldap_next_entry` at `0x180009d7c`
- `WLDAP32!__imp_ldap_next_entry` at `0x180009d7c`
- `WLDAP32!__imp_ldap_msgfree` at `0x180009dcd`
- `WLDAP32!__imp_ldap_msgfree` at `0x180009dcd`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cba`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cd2`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cfb`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009d2a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009d3e`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cba`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cd2`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009cfb`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009d2a`
- `WLDAP32!__imp_ldap_get_valuesW` at `0x180009d3e`
- `WLDAP32!__imp_ldap_search_sW` at `0x180009c6d`
- `WLDAP32!__imp_ldap_search_sW` at `0x180009c6d`

## string_xrefs

- `0x180009da6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\sidkeyldap.cxx`

## pseudocode

```c
__int64 __fastcall QueryADSnapshotBrowserDomainNames(LDAP *ld, struct _AD_LDAP_BROWSER_STATE *a2)
{
  signed int v4; // eax
  signed int v5; // ebx
  LDAPMessage *entry; // rsi
  PWCHAR *valuesW; // rax
  PWCHAR *v8; // rax
  PWCHAR *v9; // rax
  LDAPMessage *res; // [rsp+40h] [rbp-68h] BYREF
  PWSTR attrs[5]; // [rsp+48h] [rbp-60h] BYREF

  res = 0;
  attrs[0] = (PWSTR)L"nCName";
  attrs[1] = (PWSTR)L"dnsRoot";
  attrs[2] = (PWSTR)L"trustParent";
  attrs[3] = (PWSTR)L"msDS-Behavior-Version";
  attrs[4] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_497df786d6153c614e507117de9dfe52_Traceguids);
  v4 = ldap_search_sW(ld, *((const PWSTR *)a2 + 2), 2u, (const PWSTR)L"(objectClass=crossRef)", attrs, 0, &res);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    entry = ldap_first_entry(ld, res);
    if ( entry )
    {
      do
      {
        if ( ldap_get_valuesW(ld, entry, (const PWSTR)L"msDS-Behavior-Version") )
        {
          valuesW = ldap_get_valuesW(ld, entry, (const PWSTR)L"nCName");
          if ( !valuesW || !*valuesW )
            goto LABEL_8;
          if ( !(unsigned int)_o__wcsicmp(*valuesW, *(_QWORD *)a2) )
          {
            v8 = ldap_get_valuesW(ld, entry, (const PWSTR)L"dnsRoot");
            if ( !v8 || !*v8 )
              goto LABEL_8;
            v5 = SIDKeyCopyString(*v8, (unsigned __int16 **)a2 + 4);
            if ( v5 < 0 )
              goto LABEL_27;
          }
          if ( !ldap_get_valuesW(ld, entry, (const PWSTR)L"trustParent") )
          {
            v9 = ldap_get_valuesW(ld, entry, (const PWSTR)L"dnsRoot");
            if ( !v9 || !*v9 )
              goto LABEL_8;
            v5 = SIDKeyCopyString(*v9, (unsigned __int16 **)a2 + 5);
            if ( v5 < 0 )
              goto LABEL_27;
          }
        }
        if ( *((_QWORD *)a2 + 4) && *((_QWORD *)a2 + 5) )
          break;
        entry = ldap_next_entry(ld, entry);
      }
      while ( entry );
      if ( *((_QWORD *)a2 + 4) && *((_QWORD *)a2 + 5) )
      {
        v5 = 0;
      }
      else
      {
        v5 = -2147023544;
        SidKeyDebugTraceError(72, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\sidkeyldap.cxx", 14);
      }
    }
    else
    {
LABEL_8:
      v5 = -2147418113;
    }
  }
LABEL_27:
  if ( res )
    ldap_msgfree(res);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009ba4  mov     r11, rsp
0x180009ba7  mov     [r11+18h], rbx
0x180009bab  mov     [r11+20h], rbp
0x180009baf  push    rsi
0x180009bb0  push    rdi
0x180009bb1  push    r12
0x180009bb3  push    r13
0x180009bb5  push    r15
0x180009bb7  sub     rsp, 80h
0x180009bbe  mov     rax, cs:__security_cookie
0x180009bc5  xor     rax, rsp
0x180009bc8  mov     [rsp+0A8h+var_38], rax
0x180009bcd  lea     r12, aNcname; "nCName"
0x180009bd4  mov     qword ptr [r11-68h], 0
0x180009bdc  lea     r15, aDnsroot; "dnsRoot"
0x180009be3  mov     [r11-60h], r12
0x180009be7  lea     r13, aTrustparent; "trustParent"
0x180009bee  mov     [r11-58h], r15
0x180009bf2  lea     rax, aMsdsBehaviorVe; "msDS-Behavior-Version"
0x180009bf9  mov     [r11-50h], r13
0x180009bfd  mov     [r11-48h], rax
0x180009c01  mov     rdi, rdx
0x180009c04  mov     rbp, rcx
0x180009c07  mov     qword ptr [r11-40h], 0
0x180009c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c16  lea     rax, WPP_GLOBAL_Control
0x180009c1d  cmp     rcx, rax
0x180009c20  jz      short loc_180009C3D
0x180009c22  test    byte ptr [rcx+1Ch], 4
0x180009c26  jz      short loc_180009C3D
0x180009c28  mov     rcx, [rcx+10h]
0x180009c2c  lea     r8, WPP_497df786d6153c614e507117de9dfe52_Traceguids
0x180009c33  mov     edx, 0Ch
0x180009c38  call    WPP_SF_
0x180009c3d  mov     rdx, [rdi+10h]; base
0x180009c41  lea     rax, [rsp+0A8h+var_68]
0x180009c46  mov     [rsp+0A8h+res], rax; res
0x180009c4b  lea     r9, aObjectclassCro; "(objectClass=crossRef)"
0x180009c52  lea     rax, [rsp+0A8h+var_60]
0x180009c57  mov     [rsp+0A8h+attrsonly], 0; attrsonly
0x180009c5f  mov     r8d, 2; scope
0x180009c65  mov     [rsp+0A8h+attrs], rax; attrs
0x180009c6a  mov     rcx, rbp; ld
0x180009c6d  call    cs:__imp_ldap_search_sW
0x180009c73  mov     ebx, eax
0x180009c75  test    eax, eax
0x180009c77  jz      short loc_180009C8D
0x180009c79  jle     loc_180009DC3
0x180009c7f  movzx   ebx, ax
0x180009c82  or      ebx, 80070000h
0x180009c88  jmp     loc_180009DC3
0x180009c8d  mov     rdx, [rsp+0A8h+var_68]; res
0x180009c92  mov     rcx, rbp; ld
0x180009c95  call    cs:__imp_ldap_first_entry
0x180009c9b  mov     rsi, rax
0x180009c9e  test    rax, rax
0x180009ca1  jnz     short loc_180009CAD
0x180009ca3  mov     ebx, 8000FFFFh
0x180009ca8  jmp     loc_180009DC3
0x180009cad  lea     r8, aMsdsBehaviorVe; "msDS-Behavior-Version"
0x180009cb4  mov     rdx, rsi; entry
0x180009cb7  mov     rcx, rbp; ld
0x180009cba  call    cs:__imp_ldap_get_valuesW
0x180009cc0  test    rax, rax
0x180009cc3  jz      loc_180009D68
0x180009cc9  mov     r8, r12; attr
0x180009ccc  mov     rdx, rsi; entry
0x180009ccf  mov     rcx, rbp; ld
0x180009cd2  call    cs:__imp_ldap_get_valuesW
0x180009cd8  test    rax, rax
0x180009cdb  jz      short loc_180009CA3
0x180009cdd  mov     rcx, [rax]
0x180009ce0  test    rcx, rcx
0x180009ce3  jz      short loc_180009CA3
0x180009ce5  mov     rdx, [rdi]
0x180009ce8  call    cs:__imp__o__wcsicmp
0x180009cee  test    eax, eax
0x180009cf0  jnz     short loc_180009D21
0x180009cf2  mov     r8, r15; attr
0x180009cf5  mov     rdx, rsi; entry
0x180009cf8  mov     rcx, rbp; ld
0x180009cfb  call    cs:__imp_ldap_get_valuesW
0x180009d01  test    rax, rax
0x180009d04  jz      short loc_180009CA3
0x180009d06  mov     rcx, [rax]; unsigned __int16 *
0x180009d09  test    rcx, rcx
0x180009d0c  jz      short loc_180009CA3
0x180009d0e  lea     rdx, [rdi+20h]; unsigned __int16 **
0x180009d12  call    ?SIDKeyCopyString@@YAJPEAGPEAPEAG@Z; SIDKeyCopyString(ushort *,ushort * *)
0x180009d17  mov     ebx, eax
0x180009d19  test    eax, eax
0x180009d1b  js      loc_180009DC3
0x180009d21  mov     r8, r13; attr
0x180009d24  mov     rdx, rsi; entry
0x180009d27  mov     rcx, rbp; ld
0x180009d2a  call    cs:__imp_ldap_get_valuesW
0x180009d30  test    rax, rax
0x180009d33  jnz     short loc_180009D68
0x180009d35  mov     r8, r15; attr
0x180009d38  mov     rdx, rsi; entry
0x180009d3b  mov     rcx, rbp; ld
0x180009d3e  call    cs:__imp_ldap_get_valuesW
0x180009d44  test    rax, rax
0x180009d47  jz      loc_180009CA3
0x180009d4d  mov     rcx, [rax]; unsigned __int16 *
0x180009d50  test    rcx, rcx
0x180009d53  jz      loc_180009CA3
0x180009d59  lea     rdx, [rdi+28h]; unsigned __int16 **
0x180009d5d  call    ?SIDKeyCopyString@@YAJPEAGPEAPEAG@Z; SIDKeyCopyString(ushort *,ushort * *)
0x180009d62  mov     ebx, eax
0x180009d64  test    eax, eax
0x180009d66  js      short loc_180009DC3
0x180009d68  cmp     qword ptr [rdi+20h], 0
0x180009d6d  jz      short loc_180009D76
0x180009d6f  cmp     qword ptr [rdi+28h], 0
0x180009d74  jnz     short loc_180009D8E
0x180009d76  mov     rdx, rsi; entry
0x180009d79  mov     rcx, rbp; ld
0x180009d7c  call    cs:__imp_ldap_next_entry
0x180009d82  mov     rsi, rax
0x180009d85  test    rax, rax
0x180009d88  jnz     loc_180009CAD
0x180009d8e  cmp     qword ptr [rdi+20h], 0
0x180009d93  jz      short loc_180009DA0
0x180009d95  cmp     qword ptr [rdi+28h], 0
0x180009d9a  jz      short loc_180009DA0
0x180009d9c  xor     ebx, ebx
0x180009d9e  jmp     short loc_180009DC3
0x180009da0  mov     r9d, 20Eh; unsigned int
0x180009da6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180009dad  lea     rdx, aHr; "hr"
0x180009db4  mov     ecx, 80070548h; unsigned int
0x180009db9  mov     ebx, 80070548h
0x180009dbe  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180009dc3  mov     rcx, [rsp+0A8h+var_68]; res
0x180009dc8  test    rcx, rcx
0x180009dcb  jz      short loc_180009DD3
0x180009dcd  call    cs:__imp_ldap_msgfree
0x180009dd3  mov     eax, ebx
0x180009dd5  mov     rcx, [rsp+0A8h+var_38]
0x180009dda  xor     rcx, rsp; StackCookie
0x180009ddd  call    __security_check_cookie
0x180009de2  lea     r11, [rsp+0A8h+var_28]
0x180009dea  mov     rbx, [r11+40h]
0x180009dee  mov     rbp, [r11+48h]
0x180009df2  mov     rsp, r11
0x180009df5  pop     r15
0x180009df7  pop     r13
0x180009df9  pop     r12
0x180009dfb  pop     rdi
0x180009dfc  pop     rsi
0x180009dfd  retn
```
