# GetAllRootKeys(ldap *,ushort const *,ulong *,_ROOT_KEY_HEADER * *)

- ea: `0x180005330`
- end: `0x1800054d8`
- name: `?GetAllRootKeys@@YAJPEAUldap@@PEBGPEAKPEAPEAU_ROOT_KEY_HEADER@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(LDAP *ld, const unsigned __int16 *, unsigned int *, struct _ROOT_KEY_HEADER **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003e08`
- `0x180005330`
- `0x180005a24`
- `0x180006908`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_LdapGetLastError` at `0x18000539e`
- `WLDAP32!__imp_LdapGetLastError` at `0x18000539e`
- `WLDAP32!__imp_ldap_first_entry` at `0x180005406`
- `WLDAP32!__imp_ldap_first_entry` at `0x180005406`
- `WLDAP32!__imp_ldap_next_entry` at `0x18000547b`
- `WLDAP32!__imp_ldap_next_entry` at `0x18000547b`
- `WLDAP32!__imp_ldap_count_entries` at `0x180005391`
- `WLDAP32!__imp_ldap_count_entries` at `0x180005391`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800054b9`
- `WLDAP32!__imp_ldap_msgfree` at `0x1800054b9`

## string_xrefs

- `0x1800053aa`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`
- `0x180005495`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsrootkey.cxx`

## pseudocode

```c
__int64 __fastcall GetAllRootKeys(LDAP *ld, WCHAR *a2, unsigned int *a3, struct _ROOT_KEY_HEADER **a4)
{
  int v7; // eax
  signed int LastError; // ebx
  ULONG v9; // edi
  unsigned int v10; // r9d
  unsigned int v11; // ecx
  LDAPMessage *entry; // rsi
  __int64 v13; // rbp
  LDAPMessage *v14; // rcx
  struct _ROOT_KEY_HEADER *v16; // [rsp+30h] [rbp-38h] BYREF
  LDAPMessage *res; // [rsp+80h] [rbp+18h] BYREF

  res = 0;
  v7 = QueryRootKeyObjects(ld, a2, 0, 0, 0, &res);
  LastError = v7;
  if ( v7 < 0 )
  {
    v9 = 0;
    v10 = 1318;
LABEL_19:
    v11 = v7;
    goto LABEL_20;
  }
  v9 = ldap_count_entries(ld, res);
  if ( v9 == -1 )
  {
    LastError = LdapGetLastError();
    SidKeyDebugTraceError(
      LastError,
      "ulLdapError",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx",
      0x530u);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( !a4 )
      goto LABEL_21;
    if ( *a3 < v9 )
    {
      LastError = -2146893784;
      v10 = 1342;
      v11 = -2146893784;
LABEL_20:
      SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsrootkey.cxx", v10);
      goto LABEL_21;
    }
    entry = ldap_first_entry(ld, res);
    if ( entry )
    {
      v13 = 0;
      while ( (unsigned int)v13 < v9 )
      {
        v16 = 0;
        v7 = ParseRootKey(ld, entry, &v16);
        LastError = v7;
        if ( v7 < 0 )
        {
          v10 = 1364;
          goto LABEL_19;
        }
        a4[v13] = v16;
        v13 = (unsigned int)(v13 + 1);
        entry = ldap_next_entry(ld, entry);
        if ( !entry )
          break;
      }
    }
    else
    {
      LastError = -2147024864;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids);
    }
  }
LABEL_21:
  v14 = res;
  *a3 = v9;
  if ( v14 )
    ldap_msgfree(v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180005330  mov     r11, rsp
0x180005333  mov     [r11+8], rbx
0x180005337  mov     [r11+10h], rbp
0x18000533b  push    rsi
0x18000533c  push    rdi
0x18000533d  push    r12
0x18000533f  push    r14
0x180005341  push    r15
0x180005343  sub     rsp, 40h
0x180005347  lea     rax, [r11+18h]
0x18000534b  mov     qword ptr [r11+18h], 0
0x180005353  mov     r15, r9
0x180005356  mov     [r11-40h], rax
0x18000535a  mov     r12, r8
0x18000535d  mov     qword ptr [r11-48h], 0
0x180005365  xor     r9d, r9d
0x180005368  xor     r8d, r8d
0x18000536b  mov     r14, rcx
0x18000536e  call    QueryRootKeyObjects
0x180005373  mov     ebx, eax
0x180005375  test    eax, eax
0x180005377  jns     short loc_180005386
0x180005379  xor     edi, edi
0x18000537b  mov     r9d, 526h
0x180005381  jmp     loc_180005493
0x180005386  mov     rdx, [rsp+68h+res]; res
0x18000538e  mov     rcx, r14; ld
0x180005391  call    cs:__imp_ldap_count_entries
0x180005397  mov     edi, eax
0x180005399  cmp     eax, 0FFFFFFFFh
0x18000539c  jnz     short loc_1800053D7
0x18000539e  call    cs:__imp_LdapGetLastError
0x1800053a4  mov     r9d, 530h; unsigned int
0x1800053aa  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800053b1  mov     ecx, eax; unsigned int
0x1800053b3  lea     rdx, aUlldaperror; "ulLdapError"
0x1800053ba  mov     ebx, eax
0x1800053bc  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800053c1  test    ebx, ebx
0x1800053c3  jle     loc_1800054A8
0x1800053c9  movzx   ebx, bx
0x1800053cc  or      ebx, 80070000h
0x1800053d2  jmp     loc_1800054A8
0x1800053d7  test    r15, r15
0x1800053da  jz      loc_1800054A8
0x1800053e0  cmp     [r12], edi
0x1800053e4  jnb     short loc_1800053FB
0x1800053e6  mov     ebx, 80090028h
0x1800053eb  mov     r9d, 53Eh
0x1800053f1  mov     ecx, 80090028h
0x1800053f6  jmp     loc_180005495
0x1800053fb  mov     rdx, [rsp+68h+res]; res
0x180005403  mov     rcx, r14; ld
0x180005406  call    cs:__imp_ldap_first_entry
0x18000540c  mov     rsi, rax
0x18000540f  test    rax, rax
0x180005412  jnz     short loc_180005447
0x180005414  mov     ebx, 80070020h
0x180005419  mov     rcx, cs:WPP_GLOBAL_Control
0x180005420  lea     rax, WPP_GLOBAL_Control
0x180005427  cmp     rcx, rax
0x18000542a  jz      short loc_1800054A8
0x18000542c  test    byte ptr [rcx+1Ch], 4
0x180005430  jz      short loc_1800054A8
0x180005432  mov     rcx, [rcx+10h]
0x180005436  lea     edx, [rsi+1Fh]
0x180005439  lea     r8, WPP_708c196e39bc38fc646e8899e13b9dd4_Traceguids
0x180005440  call    WPP_SF_
0x180005445  jmp     short loc_1800054A8
0x180005447  xor     ebp, ebp
0x180005449  cmp     ebp, edi
0x18000544b  jnb     short loc_1800054A8
0x18000544d  lea     r8, [rsp+68h+var_38]
0x180005452  mov     [rsp+68h+var_38], 0
0x18000545b  mov     rdx, rsi; entry
0x18000545e  mov     rcx, r14; ld
0x180005461  call    ParseRootKey
0x180005466  mov     ebx, eax
0x180005468  test    eax, eax
0x18000546a  js      short loc_18000548D
0x18000546c  mov     rax, [rsp+68h+var_38]
0x180005471  mov     rdx, rsi; entry
0x180005474  mov     rcx, r14; ld
0x180005477  mov     [r15+rbp*8], rax
0x18000547b  call    cs:__imp_ldap_next_entry
0x180005481  inc     ebp
0x180005483  mov     rsi, rax
0x180005486  test    rax, rax
0x180005489  jnz     short loc_180005449
0x18000548b  jmp     short loc_1800054A8
0x18000548d  mov     r9d, 554h; unsigned int
0x180005493  mov     ecx, eax; unsigned int
0x180005495  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000549c  lea     rdx, aHr; "hr"
0x1800054a3  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800054a8  mov     rcx, [rsp+68h+res]; res
0x1800054b0  mov     [r12], edi
0x1800054b4  test    rcx, rcx
0x1800054b7  jz      short loc_1800054BF
0x1800054b9  call    cs:__imp_ldap_msgfree
0x1800054bf  mov     rbp, [rsp+68h+arg_8]
0x1800054c4  mov     eax, ebx
0x1800054c6  mov     rbx, [rsp+68h+arg_0]
0x1800054cb  add     rsp, 40h
0x1800054cf  pop     r15
0x1800054d1  pop     r14
0x1800054d3  pop     r12
0x1800054d5  pop     rdi
0x1800054d6  pop     rsi
0x1800054d7  retn
```
