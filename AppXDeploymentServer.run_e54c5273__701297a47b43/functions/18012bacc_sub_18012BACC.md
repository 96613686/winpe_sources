# sub_18012BACC

- ea: `0x18012bacc`
- end: `0x18012be41`
- name: `sub_18012BACC`
- size: `885`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, PSID pSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18012cea0`

## callees

- `0x180015dd0`
- `0x180055ad4`
- `0x1800bf1ec`
- `0x1800f0cd0`
- `0x18012bacc`
- `0x18012dbf8`
- `0x18012e9dc`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18012bbfd`
- `ntdll!RtlFreeSid` at `0x18012be15`
- `ntdll!RtlFreeSid` at `0x18012bbfd`
- `ntdll!RtlFreeSid` at `0x18012be15`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18012bc2b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18012bc2b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18012bd7b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18012bd7b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18012bc4c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18012bc75`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18012bc4c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18012bc75`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18012bc5c`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18012bc5c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18012bdc8`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18012bdc8`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18012bb38`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18012bb38`

## string_xrefs

- `0x18012bb5a`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bb95`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bbe3`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bcd1`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bd00`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bdf6`: `onecore\admin\appmodel\common\accesshelpers.cpp`
- `0x18012bd9a`: `AddAccessAllowedAceEx %ls %u %p`
- `0x18012bd4d`: `DACL of %ls has duplicated package*SIDs ? %u`
- `0x18012bd2e`: `DACL of %ls missing package*SIDs ? %u`
- `0x18012bbc6`: `PackageSidToPackageCapabilitySid %ls %p`
- `0x18012bde7`: `SetNamedSecurityInfo %ls %u`
- `0x18012bcca`: `DeleteAce %ls %u %u %u 0x%0x`
- `0x18012bb4b`: `GetNamedSecurityInfo %ls`
- `0x18012bb81`: `GetNamedSecurityInfo %ls returned null dacl.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sub_18012BACC(LPWSTR pObjectName, PSID pSid)
{
  const wchar_t *v5; // rdi
  int v6; // ebx
  char v7; // si
  char v8; // r15
  DWORD v9; // ebx
  char *v10; // r12
  int v11; // eax
  PACL *ppDacl; // [rsp+28h] [rbp-38h]
  PACL *ppSacl; // [rsp+30h] [rbp-30h]
  LPVOID pAce; // [rsp+50h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR P; // [rsp+58h] [rbp-8h] BYREF
  void *retaddr; // [rsp+98h] [rbp+38h]
  PSID Sid; // [rsp+B0h] [rbp+50h] BYREF
  PACL pAcl; // [rsp+B8h] [rbp+58h] BYREF

  if ( dword_180565D0C == 5 )
    return 0;
  v5 = (const wchar_t *)sub_18012E9DC(pObjectName);
  P = 0;
  pAcl = 0;
  if ( GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &P) )
  {
    v6 = sub_1800F0CD0(retaddr, 837, "onecore\\admin\\appmodel\\common\\accesshelpers.cpp");
    goto LABEL_36;
  }
  if ( !pAcl )
  {
    v6 = -2147467261;
    sub_18012DBF8(
      retaddr,
      840,
      "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      2147500035LL,
      "GetNamedSecurityInfo %ls returned null dacl.",
      v5);
    goto LABEL_36;
  }
  Sid = 0;
  v6 = sub_180055AD4(pSid, &Sid);
  if ( v6 < 0 )
  {
    sub_18012DBF8(
      retaddr,
      845,
      "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      (unsigned int)v6,
      "PackageSidToPackageCapabilitySid %ls %p",
      v5,
      pSid);
LABEL_9:
    if ( Sid )
      RtlFreeSid(Sid);
    goto LABEL_36;
  }
  v7 = 0;
  v8 = 0;
  pAce = 0;
  v9 = 0;
  while ( v9 < pAcl->AceCount )
  {
    if ( !GetAce(pAcl, v9, &pAce) )
    {
      LODWORD(ppSacl) = pAcl->AceCount;
      LODWORD(ppDacl) = v9;
      v11 = sub_1800BF1EC(
              retaddr,
              854,
              "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
              "GetAce %ls %u %u",
              v5,
              ppDacl,
              ppSacl);
      goto LABEL_23;
    }
    if ( *(_BYTE *)pAce )
    {
LABEL_20:
      ++v9;
    }
    else
    {
      v10 = (char *)pAce + 8;
      if ( !EqualSid((char *)pAce + 8, pSid) )
      {
        if ( EqualSid(v10, Sid) )
          v7 = 1;
        goto LABEL_20;
      }
      if ( !DeleteAce(pAcl, v9) )
      {
        v11 = sub_1800BF1EC(
                retaddr,
                865,
                "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
                "DeleteAce %ls %u %u %u 0x%0x",
                v5,
                v9,
                pAcl->AceCount,
                *(unsigned __int8 *)pAce,
                *((unsigned __int8 *)pAce + 1));
LABEL_23:
        v6 = v11;
        goto LABEL_9;
      }
      v8 = 1;
    }
  }
  if ( v8 )
  {
    if ( v7 )
    {
      LODWORD(ppSacl) = pAcl->AceCount;
      v6 = -2147418113;
      sub_18012DBF8(
        retaddr,
        886,
        "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
        2147549183LL,
        "DACL of %ls has duplicated package*SIDs ? %u",
        v5,
        ppSacl);
      goto LABEL_9;
    }
    if ( !AddAccessAllowedAceEx(pAcl, 2u, 3u, 0x10000000u, Sid) )
    {
      LODWORD(ppDacl) = pAcl->AceCount;
      v11 = sub_1800BF1EC(
              retaddr,
              897,
              "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
              "AddAccessAllowedAceEx %ls %u %p",
              v5,
              ppDacl,
              Sid);
      goto LABEL_23;
    }
    if ( SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, pAcl, 0) )
    {
      v11 = sub_1800F0CD0(retaddr, 908, "onecore\\admin\\appmodel\\common\\accesshelpers.cpp");
      goto LABEL_23;
    }
  }
  else if ( !v7 )
  {
    LODWORD(ppSacl) = pAcl->AceCount;
    v6 = -2147418113;
    sub_18012DBF8(
      retaddr,
      884,
      "onecore\\admin\\appmodel\\common\\accesshelpers.cpp",
      2147549183LL,
      "DACL of %ls missing package*SIDs ? %u",
      v5,
      ppSacl);
    goto LABEL_9;
  }
  if ( Sid )
    RtlFreeSid(Sid);
  v6 = 0;
LABEL_36:
  sub_180015DD0(P);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18012bacc  mov     [rsp-38h+arg_0], rbx
0x18012bad1  push    rbp
0x18012bad2  push    rsi
0x18012bad3  push    rdi
0x18012bad4  push    r12
0x18012bad6  push    r13
0x18012bad8  push    r14
0x18012bada  push    r15
0x18012badc  mov     rbp, rsp
0x18012badf  sub     rsp, 60h
0x18012bae3  mov     r14, rdx
0x18012bae6  mov     r13, rcx
0x18012bae9  cmp     cs:dword_180565D0C, 5
0x18012baf0  jnz     short loc_18012BAF9
0x18012baf2  xor     eax, eax
0x18012baf4  jmp     loc_18012BE29
0x18012baf9  call    sub_18012E9DC
0x18012bafe  mov     rdi, rax
0x18012bb01  xor     r12d, r12d
0x18012bb04  mov     [rbp+P], r12
0x18012bb08  mov     [rbp+pAcl], r12
0x18012bb0c  lea     rax, [rbp+P]
0x18012bb10  mov     [rsp+60h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18012bb15  mov     [rsp+60h+ppSacl], r12; ppSacl
0x18012bb1a  lea     rax, [rbp+pAcl]
0x18012bb1e  mov     [rsp+60h+ppDacl], rax; ppDacl
0x18012bb23  mov     [rsp+60h+ppsidGroup], r12; ppsidGroup
0x18012bb28  xor     r9d, r9d; ppsidOwner
0x18012bb2b  lea     edx, [r12+1]; ObjectType
0x18012bb30  lea     r8d, [r12+4]; SecurityInfo
0x18012bb35  mov     rcx, r13; pObjectName
0x18012bb38  call    cs:GetNamedSecurityInfoW
0x18012bb3e  test    eax, eax
0x18012bb40  jz      short loc_18012BB72
0x18012bb42  mov     rcx, [rbp+38h]
0x18012bb46  mov     [rsp+60h+ppDacl], rdi
0x18012bb4b  lea     rdx, aGetnamedsecuri_0; "GetNamedSecurityInfo %ls"
0x18012bb52  mov     [rsp+60h+ppsidGroup], rdx
0x18012bb57  mov     r9d, eax
0x18012bb5a  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bb61  mov     edx, 345h
0x18012bb66  call    sub_1800F0CD0
0x18012bb6b  mov     ebx, eax
0x18012bb6d  jmp     loc_18012BE1E
0x18012bb72  cmp     [rbp+pAcl], r12
0x18012bb76  jnz     short loc_18012BBAB
0x18012bb78  mov     rcx, [rbp+38h]
0x18012bb7c  mov     [rsp+60h+ppDacl], rdi
0x18012bb81  lea     rax, aGetnamedsecuri_1; "GetNamedSecurityInfo %ls returned null "...
0x18012bb88  mov     [rsp+60h+ppsidGroup], rax
0x18012bb8d  mov     ebx, 80004003h
0x18012bb92  mov     r9d, ebx
0x18012bb95  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bb9c  mov     edx, 348h
0x18012bba1  call    sub_18012DBF8
0x18012bba6  jmp     loc_18012BE1E
0x18012bbab  mov     [rbp+Sid], r12
0x18012bbaf  lea     rdx, [rbp+Sid]; Sid
0x18012bbb3  mov     rcx, r14; pSid
0x18012bbb6  call    sub_180055AD4
0x18012bbbb  mov     ebx, eax
0x18012bbbd  test    eax, eax
0x18012bbbf  jns     short loc_18012BC08
0x18012bbc1  mov     [rsp+60h+ppSacl], r14
0x18012bbc6  lea     rax, aPackagesidtopa; "PackageSidToPackageCapabilitySid %ls %p"
0x18012bbcd  mov     edx, 34Dh
0x18012bbd2  mov     [rsp+60h+ppDacl], rdi
0x18012bbd7  mov     rcx, [rbp+38h]
0x18012bbdb  mov     [rsp+60h+ppsidGroup], rax
0x18012bbe0  mov     r9d, ebx
0x18012bbe3  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bbea  call    sub_18012DBF8
0x18012bbef  nop
0x18012bbf0  mov     rcx, [rbp+Sid]; Sid
0x18012bbf4  test    rcx, rcx
0x18012bbf7  jz      loc_18012BE1E
0x18012bbfd  call    cs:RtlFreeSid
0x18012bc03  jmp     loc_18012BE1E
0x18012bc08  mov     sil, r12b
0x18012bc0b  mov     r15b, r12b
0x18012bc0e  mov     [rbp+pAce], r12
0x18012bc12  mov     ebx, r12d
0x18012bc15  mov     rcx, [rbp+pAcl]; pAcl
0x18012bc19  movzx   eax, word ptr [rcx+4]
0x18012bc1d  cmp     ebx, eax
0x18012bc1f  jnb     loc_18012BD1C
0x18012bc25  lea     r8, [rbp+pAce]; pAce
0x18012bc29  mov     edx, ebx; dwAceIndex
0x18012bc2b  call    cs:GetAce
0x18012bc31  test    eax, eax
0x18012bc33  jz      loc_18012BCE4
0x18012bc39  mov     rax, [rbp+pAce]
0x18012bc3d  cmp     [rax], r12b
0x18012bc40  jnz     short loc_18012BC8E
0x18012bc42  lea     r12, [rax+8]
0x18012bc46  mov     rdx, r14; pSid2
0x18012bc49  mov     rcx, r12; pSid1
0x18012bc4c  call    cs:EqualSid
0x18012bc52  test    eax, eax
0x18012bc54  jz      short loc_18012BC6E
0x18012bc56  mov     edx, ebx; dwAceIndex
0x18012bc58  mov     rcx, [rbp+pAcl]; pAcl
0x18012bc5c  call    cs:DeleteAce
0x18012bc62  xor     r12d, r12d
0x18012bc65  test    eax, eax
0x18012bc67  jz      short loc_18012BC9A
0x18012bc69  mov     r15b, 1
0x18012bc6c  jmp     short loc_18012BC15
0x18012bc6e  mov     rdx, [rbp+Sid]; pSid2
0x18012bc72  mov     rcx, r12; pSid1
0x18012bc75  call    cs:EqualSid
0x18012bc7b  movzx   esi, sil
0x18012bc7f  xor     r12d, r12d
0x18012bc82  test    eax, eax
0x18012bc84  lea     eax, [r12+1]
0x18012bc89  cmovnz  esi, eax
0x18012bc8c  jmp     short loc_18012BC93
0x18012bc8e  mov     eax, 1
0x18012bc93  add     ebx, eax
0x18012bc95  jmp     loc_18012BC15
0x18012bc9a  mov     rax, [rbp+pAce]
0x18012bc9e  movzx   r8d, byte ptr [rax+1]
0x18012bca3  movzx   r9d, byte ptr [rax]
0x18012bca7  mov     rax, [rbp+pAcl]
0x18012bcab  movzx   edx, word ptr [rax+4]
0x18012bcaf  mov     rcx, [rbp+38h]
0x18012bcb3  mov     [rsp+60h+var_20], r8d
0x18012bcb8  mov     dword ptr [rsp+60h+ppSecurityDescriptor], r9d
0x18012bcbd  mov     dword ptr [rsp+60h+ppSacl], edx
0x18012bcc1  mov     dword ptr [rsp+60h+ppDacl], ebx
0x18012bcc5  mov     [rsp+60h+ppsidGroup], rdi
0x18012bcca  lea     r9, aDeleteaceLsUUU; "DeleteAce %ls %u %u %u 0x%0x"
0x18012bcd1  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bcd8  mov     edx, 361h
0x18012bcdd  call    sub_1800BF1EC
0x18012bce2  jmp     short loc_18012BD15
0x18012bce4  mov     rax, [rbp+pAcl]
0x18012bce8  movzx   edx, word ptr [rax+4]
0x18012bcec  mov     dword ptr [rsp+60h+ppSacl], edx
0x18012bcf0  mov     dword ptr [rsp+60h+ppDacl], ebx
0x18012bcf4  lea     r9, aGetaceLsUU; "GetAce %ls %u %u"
0x18012bcfb  mov     edx, 356h
0x18012bd00  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bd07  mov     [rsp+60h+ppsidGroup], rdi
0x18012bd0c  mov     rcx, [rbp+38h]
0x18012bd10  call    sub_1800BF1EC
0x18012bd15  mov     ebx, eax
0x18012bd17  jmp     loc_18012BBF0
0x18012bd1c  test    r15b, r15b
0x18012bd1f  jnz     short loc_18012BD44
0x18012bd21  test    sil, sil
0x18012bd24  jnz     loc_18012BE0C
0x18012bd2a  mov     dword ptr [rsp+60h+ppSacl], eax
0x18012bd2e  lea     rax, aDaclOfLsMissin; "DACL of %ls missing package*SIDs ? %u"
0x18012bd35  mov     ebx, 8000FFFFh
0x18012bd3a  mov     edx, 374h
0x18012bd3f  jmp     loc_18012BBD2
0x18012bd44  test    sil, sil
0x18012bd47  jz      short loc_18012BD63
0x18012bd49  mov     dword ptr [rsp+60h+ppSacl], eax
0x18012bd4d  lea     rax, aDaclOfLsHasDup; "DACL of %ls has duplicated package*SIDs"...
0x18012bd54  mov     ebx, 8000FFFFh
0x18012bd59  mov     edx, 376h
0x18012bd5e  jmp     loc_18012BBD2
0x18012bd63  mov     rax, [rbp+Sid]
0x18012bd67  mov     [rsp+60h+ppsidGroup], rax; pSid
0x18012bd6c  mov     edx, 2; dwAceRevision
0x18012bd71  mov     r9d, 10000000h; AccessMask
0x18012bd77  lea     r8d, [rdx+1]; AceFlags
0x18012bd7b  call    cs:AddAccessAllowedAceEx
0x18012bd81  test    eax, eax
0x18012bd83  mov     rax, [rbp+pAcl]
0x18012bd87  jnz     short loc_18012BDAB
0x18012bd89  mov     r8, [rbp+Sid]
0x18012bd8d  movzx   edx, word ptr [rax+4]
0x18012bd91  mov     [rsp+60h+ppSacl], r8
0x18012bd96  mov     dword ptr [rsp+60h+ppDacl], edx
0x18012bd9a  lea     r9, aAddaccessallow_1; "AddAccessAllowedAceEx %ls %u %p"
0x18012bda1  mov     edx, 381h
0x18012bda6  jmp     loc_18012BD00
0x18012bdab  mov     [rsp+60h+ppSacl], r12; pSacl
0x18012bdb0  mov     [rsp+60h+ppDacl], rax; pDacl
0x18012bdb5  mov     [rsp+60h+ppsidGroup], r12; psidGroup
0x18012bdba  xor     r9d, r9d; psidOwner
0x18012bdbd  lea     edx, [r9+1]; ObjectType
0x18012bdc1  lea     r8d, [r9+4]; SecurityInfo
0x18012bdc5  mov     rcx, r13; pObjectName
0x18012bdc8  call    cs:SetNamedSecurityInfoW
0x18012bdce  test    eax, eax
0x18012bdd0  jz      short loc_18012BE0C
0x18012bdd2  mov     rcx, [rbp+pAcl]
0x18012bdd6  movzx   edx, word ptr [rcx+4]
0x18012bdda  mov     rcx, [rbp+38h]
0x18012bdde  mov     dword ptr [rsp+60h+ppSacl], edx
0x18012bde2  mov     [rsp+60h+ppDacl], rdi
0x18012bde7  lea     rdx, aSetnamedsecuri_0; "SetNamedSecurityInfo %ls %u"
0x18012bdee  mov     [rsp+60h+ppsidGroup], rdx
0x18012bdf3  mov     r9d, eax
0x18012bdf6  lea     r8, aOnecoreAdminAp_129; "onecore\\admin\\appmodel\\common\\acces"...
0x18012bdfd  mov     edx, 38Ch
0x18012be02  call    sub_1800F0CD0
0x18012be07  jmp     loc_18012BD15
0x18012be0c  mov     rcx, [rbp+Sid]; Sid
0x18012be10  test    rcx, rcx
0x18012be13  jz      short loc_18012BE1B
0x18012be15  call    cs:RtlFreeSid
0x18012be1b  mov     ebx, r12d
0x18012be1e  mov     rcx, [rbp+P]; P
0x18012be22  call    sub_180015DD0
0x18012be27  mov     eax, ebx
0x18012be29  mov     rbx, [rsp+60h+arg_0]
0x18012be31  add     rsp, 60h
0x18012be35  pop     r15
0x18012be37  pop     r14
0x18012be39  pop     r13
0x18012be3b  pop     r12
0x18012be3d  pop     rdi
0x18012be3e  pop     rsi
0x18012be3f  pop     rbp
0x18012be40  retn
```
