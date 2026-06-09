# AddADObject(ldap *,ushort *,_SIDKEY_AD_ATTRIBUTE *,ulong)

- ea: `0x180002888`
- end: `0x180002a0b`
- name: `?AddADObject@@YAJPEAUldap@@PEAGPEAU_SIDKEY_AD_ATTRIBUTE@@K@Z`
- size: `387`
- prototype: `int(struct ldap *, unsigned __int16 *, struct _SIDKEY_AD_ATTRIBUTE *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a00`

## callees

- `0x180002888`
- `0x180002a14`
- `0x180002a5c`
- `0x180002b28`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `WLDAP32!__imp_ldap_add_sW` at `0x1800029ab`
- `WLDAP32!__imp_ldap_add_sW` at `0x1800029ab`

## string_xrefs

- `0x1800028c6`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002924`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x1800029cc`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall AddADObject(struct ldap *a1, unsigned __int16 *a2, struct _SIDKEY_AD_ATTRIBUTE *a3, unsigned int a4)
{
  __int64 v4; // r13
  LDAPModW **v6; // rsi
  struct ldapmodW **v7; // rdi
  int v8; // ebx
  unsigned int v9; // edi
  __int64 v10; // r15
  int v11; // edx
  signed int SingleValueStrAttribute; // eax
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  unsigned int v15; // ecx
  signed int v16; // eax

  v4 = a4;
  v6 = 0;
  v7 = (struct ldapmodW **)SIDKeyProvAlloc(8LL * (a4 + 1));
  if ( !v7 )
  {
    v8 = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x374u);
    v9 = -2147024882;
    goto LABEL_13;
  }
  v8 = 0;
  v10 = 0;
  if ( !(_DWORD)v4 )
  {
LABEL_11:
    v7[v4] = 0;
    v6 = v7;
    goto LABEL_12;
  }
  while ( 1 )
  {
    v11 = *((_DWORD *)a3 + 6 * v10 + 5);
    if ( !v11 )
    {
      SingleValueStrAttribute = GenerateSingleValueStrAttribute(
                                  *((_DWORD *)a3 + 6 * v10 + 4),
                                  *((unsigned __int16 **)a3 + 3 * v10),
                                  *((unsigned __int16 **)a3 + 3 * v10 + 1),
                                  &v7[v10]);
      v8 = SingleValueStrAttribute;
      if ( SingleValueStrAttribute < 0 )
      {
        v13 = 899;
LABEL_7:
        SidKeyDebugTraceError(
          SingleValueStrAttribute,
          "hr",
          "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx",
          v13);
        goto LABEL_16;
      }
      goto LABEL_10;
    }
    if ( v11 != 1 )
      break;
    SingleValueStrAttribute = GenerateSingleValueBervalAttribute(
                                *((_DWORD *)a3 + 6 * v10 + 4),
                                *((unsigned __int16 **)a3 + 3 * v10),
                                *((struct berval **)a3 + 3 * v10 + 1),
                                &v7[v10]);
    v8 = SingleValueStrAttribute;
    if ( SingleValueStrAttribute < 0 )
    {
      v13 = 912;
      goto LABEL_7;
    }
LABEL_10:
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= (unsigned int)v4 )
      goto LABEL_11;
  }
  v8 = -2147024809;
LABEL_16:
  DeleteAttrsList(v7, v10);
  SIDKeyProvFree(v7);
LABEL_12:
  v9 = v8;
  if ( v8 < 0 )
  {
LABEL_13:
    v14 = 955;
    v15 = v8;
    goto LABEL_22;
  }
  v16 = ldap_add_sW(a1, a2, v6);
  if ( v16 )
  {
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    else
      v9 = v16;
    v14 = 968;
    v15 = v9;
LABEL_22:
    SidKeyDebugTraceError(v15, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v14);
  }
  if ( v6 )
  {
    DeleteAttrsList(v6, v4);
    SIDKeyProvFree(v6);
  }
  return v9;
}

```

## disassembly

```asm
0x180002888  mov     [rsp+arg_10], rbx
0x18000288d  mov     [rsp+dn], rdx
0x180002892  mov     [rsp+ld], rcx
0x180002897  push    rsi
0x180002898  push    rdi
0x180002899  push    r12
0x18000289b  push    r13
0x18000289d  push    r15
0x18000289f  sub     rsp, 20h
0x1800028a3  mov     r13d, r9d
0x1800028a6  mov     r12, r8
0x1800028a9  xor     esi, esi
0x1800028ab  lea     ecx, [r13+1]
0x1800028af  shl     rcx, 3; unsigned __int64
0x1800028b3  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x1800028b8  mov     rdi, rax
0x1800028bb  test    rax, rax
0x1800028be  jnz     short loc_1800028EA
0x1800028c0  mov     r9d, 374h; unsigned int
0x1800028c6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800028cd  lea     rdx, aHr; "hr"
0x1800028d4  mov     ecx, 8007000Eh; unsigned int
0x1800028d9  mov     ebx, 8007000Eh
0x1800028de  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800028e3  mov     edi, ebx
0x1800028e5  jmp     loc_180002972
0x1800028ea  xor     ebx, ebx
0x1800028ec  xor     r15d, r15d
0x1800028ef  test    r13d, r13d
0x1800028f2  jz      short loc_180002965
0x1800028f4  lea     rcx, [r15+r15*2]
0x1800028f8  mov     edx, [r12+rcx*8+14h]
0x1800028fd  test    edx, edx
0x1800028ff  jnz     short loc_18000293B
0x180002901  mov     r8, [r12+rcx*8+8]; unsigned __int16 *
0x180002906  lea     r9, [rdi+r15*8]; struct ldapmodW **
0x18000290a  mov     rdx, [r12+rcx*8]; unsigned __int16 *
0x18000290e  mov     ecx, [r12+rcx*8+10h]; unsigned int
0x180002913  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180002918  mov     ebx, eax
0x18000291a  test    eax, eax
0x18000291c  jns     short loc_18000295D
0x18000291e  mov     r9d, 383h; unsigned int
0x180002924  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000292b  mov     ecx, eax; unsigned int
0x18000292d  lea     rdx, aHr; "hr"
0x180002934  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002939  jmp     short loc_180002989
0x18000293b  cmp     edx, 1
0x18000293e  jnz     short loc_180002984
0x180002940  mov     r8, [r12+rcx*8+8]; struct berval *
0x180002945  lea     r9, [rdi+r15*8]; struct ldapmodW **
0x180002949  mov     rdx, [r12+rcx*8]; unsigned __int16 *
0x18000294d  mov     ecx, [r12+rcx*8+10h]; unsigned int
0x180002952  call    ?GenerateSingleValueBervalAttribute@@YAJKPEAGPEAUberval@@PEAPEAUldapmodW@@@Z; GenerateSingleValueBervalAttribute(ulong,ushort *,berval *,ldapmodW * *)
0x180002957  mov     ebx, eax
0x180002959  test    eax, eax
0x18000295b  js      short loc_18000297C
0x18000295d  inc     r15d
0x180002960  cmp     r15d, r13d
0x180002963  jb      short loc_1800028F4
0x180002965  mov     [rdi+r13*8], rsi
0x180002969  mov     rsi, rdi
0x18000296c  mov     edi, ebx
0x18000296e  test    ebx, ebx
0x180002970  jns     short loc_18000299E
0x180002972  mov     r9d, 3BBh
0x180002978  mov     ecx, ebx
0x18000297a  jmp     short loc_1800029CC
0x18000297c  mov     r9d, 390h
0x180002982  jmp     short loc_180002924
0x180002984  mov     ebx, 80070057h
0x180002989  mov     edx, r15d; unsigned int
0x18000298c  mov     rcx, rdi; struct ldapmodW **
0x18000298f  call    ?DeleteAttrsList@@YAXPEAPEAUldapmodW@@K@Z; DeleteAttrsList(ldapmodW * *,ulong)
0x180002994  mov     rcx, rdi; lpMem
0x180002997  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000299c  jmp     short loc_18000296C
0x18000299e  mov     rdx, [rsp+48h+dn]; dn
0x1800029a3  mov     r8, rsi; attrs
0x1800029a6  mov     rcx, [rsp+48h+ld]; ld
0x1800029ab  call    cs:__imp_ldap_add_sW
0x1800029b1  test    eax, eax
0x1800029b3  jz      short loc_1800029DF
0x1800029b5  jg      short loc_1800029BB
0x1800029b7  mov     edi, eax
0x1800029b9  jmp     short loc_1800029C4
0x1800029bb  movzx   edi, ax
0x1800029be  or      edi, 80070000h
0x1800029c4  mov     r9d, 3C8h; unsigned int
0x1800029ca  mov     ecx, edi; unsigned int
0x1800029cc  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800029d3  lea     rdx, aHr; "hr"
0x1800029da  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800029df  test    rsi, rsi
0x1800029e2  jz      short loc_1800029F7
0x1800029e4  mov     edx, r13d; unsigned int
0x1800029e7  mov     rcx, rsi; struct ldapmodW **
0x1800029ea  call    ?DeleteAttrsList@@YAXPEAPEAUldapmodW@@K@Z; DeleteAttrsList(ldapmodW * *,ulong)
0x1800029ef  mov     rcx, rsi; lpMem
0x1800029f2  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x1800029f7  mov     rbx, [rsp+48h+arg_10]
0x1800029fc  mov     eax, edi
0x1800029fe  add     rsp, 20h
0x180002a02  pop     r15
0x180002a04  pop     r13
0x180002a06  pop     r12
0x180002a08  pop     rdi
0x180002a09  pop     rsi
0x180002a0a  retn
```
