# SetServerConfig(ldap *,ushort const *,_KDS_CONFIGURATION *)

- ea: `0x180007a10`
- end: `0x180007b56`
- name: `?SetServerConfig@@YAJPEAUldap@@PEBGPEAU_KDS_CONFIGURATION@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(LDAP *ld, PWSTR dn, struct _KDS_CONFIGURATION *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001630`
- `0x180006dbc`
- `0x180007a10`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_modify_sW` at `0x180007ad5`
- `WLDAP32!__imp_ldap_modify_sW` at `0x180007ad5`

## string_xrefs

- `0x180007ab4`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`
- `0x180007ae7`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall SetServerConfig(LDAP *ld, PWSTR dn, struct _KDS_CONFIGURATION *a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  ULONG v7; // eax
  int v8; // edi
  __int64 i; // rdi
  LDAPModW *v10; // rcx
  struct berval v12; // [rsp+30h] [rbp-49h] BYREF
  berval v13; // [rsp+40h] [rbp-39h] BYREF
  LDAPModW *mods[2]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v15; // [rsp+60h] [rbp-19h]
  __int128 v16; // [rsp+70h] [rbp-9h]
  __int64 v17; // [rsp+80h] [rbp+7h]
  unsigned __int16 v18[8]; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v19[28]; // [rsp+98h] [rbp+1Fh] BYREF

  *(&v13.bv_len + 1) = 0;
  v17 = 0;
  v13.bv_len = *((_DWORD *)a3 + 12);
  v13.bv_val = (PCHAR)*((_QWORD *)a3 + 5);
  v12.bv_len = *((_DWORD *)a3 + 6);
  v12.bv_val = (PCHAR)*((_QWORD *)a3 + 2);
  *(&v12.bv_len + 1) = 0;
  memset(v19, 0, sizeof(v19));
  *(_OWORD *)mods = 0;
  v15 = 0;
  v16 = 0;
  *(_OWORD *)v18 = 0;
  v5 = GenerateServerConfigAttributes(mods, a3, &v13, &v12, v18);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = ldap_modify_sW(ld, dn, mods);
    v8 = v7;
    if ( v7 )
    {
      SidKeyDebugTraceError(
        v7,
        "ulLdapErr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx",
        0x3CCu);
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      else
        v6 = v8;
    }
    for ( i = 0; i != 7; ++i )
    {
      v10 = mods[i];
      if ( v10 )
      {
        SIDKeyProvFree(v10->mod_vals.modv_strvals);
        SIDKeyProvFree(mods[i]);
      }
    }
  }
  else
  {
    SidKeyDebugTraceError(v5, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", 0x3C1u);
  }
  return v6;
}

```

## disassembly

```asm
0x180007a10  mov     [rsp-8+arg_18], rbx
0x180007a15  push    rbp
0x180007a16  push    rsi
0x180007a17  push    rdi
0x180007a18  lea     rbp, [rsp-47h]
0x180007a1d  sub     rsp, 0C0h
0x180007a24  mov     rax, cs:__security_cookie
0x180007a2b  xor     rax, rsp
0x180007a2e  mov     [rbp+57h+var_18], rax
0x180007a32  xor     eax, eax
0x180007a34  mov     dword ptr [rbp+57h+var_90+4], 0
0x180007a3b  mov     [rbp+57h+var_50], rax
0x180007a3f  lea     r9, [rbp+57h+var_A0]; struct berval *
0x180007a43  mov     eax, [r8+30h]
0x180007a47  xorps   xmm1, xmm1
0x180007a4a  mov     [rbp+57h+var_90.bv_len], eax
0x180007a4d  xorps   xmm0, xmm0
0x180007a50  mov     rax, [r8+28h]
0x180007a54  mov     r10, r8
0x180007a57  mov     [rbp+57h+var_90.bv_val], rax
0x180007a5b  mov     rsi, rdx
0x180007a5e  mov     eax, [r8+18h]
0x180007a62  mov     rdi, rcx
0x180007a65  mov     [rbp+57h+var_A0.bv_len], eax
0x180007a68  lea     rcx, [rbp+57h+mods]; struct ldapmodW **
0x180007a6c  mov     rax, [r8+10h]
0x180007a70  mov     rdx, r10; struct _KDS_CONFIGURATION *
0x180007a73  mov     [rbp+57h+var_A0.bv_val], rax
0x180007a77  lea     r8, [rbp+57h+var_90]; struct berval *
0x180007a7b  lea     rax, [rbp+57h+var_48]
0x180007a7f  mov     dword ptr [rbp+57h+var_A0+4], 0
0x180007a86  movups  xmmword ptr [rbp+57h+var_38], xmm1
0x180007a8a  mov     [rsp+0D0h+var_B0], rax; unsigned __int16 *
0x180007a8f  movups  xmmword ptr [rbp+57h+mods], xmm0
0x180007a93  movups  [rbp+57h+var_70], xmm0
0x180007a97  movups  [rbp+57h+var_60], xmm0
0x180007a9b  movups  xmmword ptr [rbp+57h+var_48], xmm1
0x180007a9f  movups  xmmword ptr [rbp+57h+var_38+0Ch], xmm1
0x180007aa3  call    ?GenerateServerConfigAttributes@@YAJQEAPEAUldapmodW@@PEAU_KDS_CONFIGURATION@@PEAUberval@@2QEAG@Z; GenerateServerConfigAttributes(ldapmodW * * const,_KDS_CONFIGURATION *,berval *,berval *,ushort * const)
0x180007aa8  mov     ebx, eax
0x180007aaa  test    eax, eax
0x180007aac  jns     short loc_180007ACB
0x180007aae  mov     r9d, 3C1h; unsigned int
0x180007ab4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007abb  lea     rdx, aHr; "hr"
0x180007ac2  mov     ecx, eax; unsigned int
0x180007ac4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007ac9  jmp     short loc_180007B35
0x180007acb  lea     r8, [rbp+57h+mods]; mods
0x180007acf  mov     rdx, rsi; dn
0x180007ad2  mov     rcx, rdi; ld
0x180007ad5  call    cs:__imp_ldap_modify_sW
0x180007adb  mov     edi, eax
0x180007add  test    eax, eax
0x180007adf  jz      short loc_180007B0D
0x180007ae1  mov     r9d, 3CCh; unsigned int
0x180007ae7  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180007aee  lea     rdx, aUlldaperr; "ulLdapErr"
0x180007af5  mov     ecx, eax; unsigned int
0x180007af7  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180007afc  test    edi, edi
0x180007afe  jg      short loc_180007B04
0x180007b00  mov     ebx, edi
0x180007b02  jmp     short loc_180007B0D
0x180007b04  movzx   ebx, di
0x180007b07  or      ebx, 80070000h
0x180007b0d  xor     edi, edi
0x180007b0f  mov     rcx, [rbp+rdi*8+57h+mods]
0x180007b14  test    rcx, rcx
0x180007b17  jz      short loc_180007B2C
0x180007b19  mov     rcx, [rcx+10h]; lpMem
0x180007b1d  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180007b22  mov     rcx, [rbp+rdi*8+57h+mods]; lpMem
0x180007b27  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180007b2c  inc     rdi
0x180007b2f  cmp     rdi, 7
0x180007b33  jnz     short loc_180007B0F
0x180007b35  mov     eax, ebx
0x180007b37  mov     rcx, [rbp+57h+var_18]
0x180007b3b  xor     rcx, rsp; StackCookie
0x180007b3e  call    __security_check_cookie
0x180007b43  mov     rbx, [rsp+0D0h+arg_18]
0x180007b4b  add     rsp, 0C0h
0x180007b52  pop     rdi
0x180007b53  pop     rsi
0x180007b54  pop     rbp
0x180007b55  retn
```
