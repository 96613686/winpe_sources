# RdVhd::Uvhd::CDirectoryHelper::AddUserAce(_ACL *,ushort const *,_ACL * *)

- ea: `0x18004c82c`
- end: `0x18004cc67`
- name: `?AddUserAce@CDirectoryHelper@Uvhd@RdVhd@@AEBAJPEAU_ACL@@PEBGPEAPEAU4@@Z`
- size: `1083`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CDirectoryHelper *this, struct _ACL *, const unsigned __int16 *, struct _ACL **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f3d0`

## callees

- `0x18001a280`
- `0x180042ff4`
- `0x1800488e4`
- `0x180048b28`
- `0x18004c82c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c9d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ca5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004caea`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004ca53`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18004ca53`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004caa4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004caa4`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18004cae0`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18004cae0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18004c9c7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18004c9c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004cc41`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004c92f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004c92f`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004cbc4`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18004cbc4`

## string_xrefs

- `0x18004c8e8`: `szSidString`
- `0x18004c89e`: `pOldDacl`
- `0x18004c91a`: `ppNewDacl`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::AddUserAce(
        RdVhd::Uvhd::CDirectoryHelper *this,
        struct _ACL *a2,
        const unsigned __int16 *a3,
        struct _ACL **a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // r9
  signed int v9; // ebx
  signed int LastError; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v11; // rcx
  __int64 v12; // rdx
  signed int v13; // eax
  DWORD i; // esi
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // ebx
  PSID Sid; // [rsp+20h] [rbp-60h] BYREF
  PACL NewAcl; // [rsp+28h] [rbp-58h] BYREF
  LPVOID pAce; // [rsp+30h] [rbp-50h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+38h] [rbp-48h] BYREF
  __int64 pAclInformation; // [rsp+68h] [rbp-18h] BYREF
  int v25; // [rsp+70h] [rbp-10h]

  pAclInformation = 0;
  v25 = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  Sid = 0;
  NewAcl = 0;
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 156;
    v8 = L"pOldDacl";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v6 + 2), v7, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v8);
LABEL_7:
    v9 = -2147024809;
    goto LABEL_86;
  }
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 157;
    v8 = L"szSidString";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 158;
    v8 = L"ppNewDacl";
    goto LABEL_6;
  }
  *a4 = 0;
  v9 = 0;
  if ( ConvertStringSidToSidW(a3, &Sid) )
    goto LABEL_36;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError && (LastError & 0xFFFF0000) == 0 )
  {
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v9 = v9 & 0x8000FFFF | 0x501F0000;
  }
  if ( v9 >= 0 )
  {
LABEL_36:
    if ( GetAclInformation(a2, &pAclInformation, 0xCu, AclSizeInformation) )
      goto LABEL_41;
    v13 = GetLastError();
    v9 = v13;
    if ( v13 && (v13 & 0xFFFF0000) == 0 )
    {
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      v9 = v9 & 0x8000FFFF | 0x50200000;
    }
    if ( v9 >= 0 )
    {
LABEL_41:
      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
      {
        pAce = 0;
        if ( !GetAce(a2, i, &pAce) )
        {
          v15 = GetLastError();
          v9 = v15;
          if ( v15 && (v15 & 0xFFFF0000) == 0 )
          {
            if ( v15 > 0 )
              v9 = (unsigned __int16)v15 | 0x80070000;
            v9 = v9 & 0x8000FFFF | 0x50210000;
          }
          if ( v9 < 0 )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 161;
              goto LABEL_29;
            }
            goto LABEL_86;
          }
        }
        if ( !*(_BYTE *)pAce && EqualSid(Sid, (char *)pAce + 8) )
        {
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids);
          }
          if ( !DeleteAce(a2, i) )
          {
            v16 = GetLastError();
            v9 = v16;
            if ( v16 && (v16 & 0xFFFF0000) == 0 )
            {
              if ( v16 > 0 )
                v9 = (unsigned __int16)v16 | 0x80070000;
              v9 = v9 & 0x8000FFFF | 0x50220000;
            }
            if ( v9 < 0 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v12 = 163;
                goto LABEL_29;
              }
              goto LABEL_86;
            }
          }
          --i;
          LODWORD(pAclInformation) = pAclInformation - 1;
        }
      }
      pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
      pListOfExplicitEntries.grfAccessPermissions = -1;
      pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
      pListOfExplicitEntries.grfInheritance = 3;
      pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
      pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_USER;
      v17 = SetEntriesInAclW(1u, &pListOfExplicitEntries, a2, &NewAcl);
      if ( v17
        && ((v17 & 0xFFFF0000) != 0
          ? (v9 = v17)
          : (v17 > 0 ? (v18 = (unsigned __int16)v17 | 0x80070000) : (v18 = v17), v9 = v18 & 0x8000FFFF | 0x50230000),
            v9 < 0) )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 164;
          goto LABEL_29;
        }
      }
      else
      {
        *a4 = NewAcl;
        NewAcl = 0;
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 160;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 159;
LABEL_29:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, (unsigned int)v9);
    }
  }
LABEL_86:
  if ( Sid )
    LocalFree(Sid);
  if ( NewAcl )
    LocalFree(NewAcl);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004c82c  push    rbp
0x18004c82e  push    rbx
0x18004c82f  push    rsi
0x18004c830  push    rdi
0x18004c831  push    r13
0x18004c833  push    r14
0x18004c835  push    r15
0x18004c837  mov     rbp, rsp
0x18004c83a  sub     rsp, 80h
0x18004c841  mov     rax, cs:__security_cookie
0x18004c848  xor     rax, rsp
0x18004c84b  mov     [rbp+var_8], rax
0x18004c84f  xor     eax, eax
0x18004c851  xorps   xmm0, xmm0
0x18004c854  mov     [rbp+pAclInformation], rax
0x18004c858  mov     r14, r9
0x18004c85b  mov     [rbp+var_10], eax
0x18004c85e  mov     r15, rdx
0x18004c861  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x18004c865  mov     [rbp+Sid], rax
0x18004c869  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x18004c86d  mov     [rbp+NewAcl], rax
0x18004c871  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18004c875  test    rdx, rdx
0x18004c878  jnz     short loc_18004C8BF
0x18004c87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c881  lea     rdi, WPP_GLOBAL_Control
0x18004c888  cmp     rcx, rdi
0x18004c88b  jz      short loc_18004C8B5
0x18004c88d  test    byte ptr [rcx+1Ch], 4
0x18004c891  jz      short loc_18004C8B5
0x18004c893  cmp     byte ptr [rcx+19h], 2
0x18004c897  jb      short loc_18004C8B5
0x18004c899  mov     edx, 9Ch
0x18004c89e  lea     r9, aPolddacl; "pOldDacl"
0x18004c8a5  mov     rcx, [rcx+10h]
0x18004c8a9  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004c8b0  call    WPP_SF_S
0x18004c8b5  mov     ebx, 80070057h
0x18004c8ba  jmp     loc_18004CC29
0x18004c8bf  test    r8, r8
0x18004c8c2  jnz     short loc_18004C8F1
0x18004c8c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8cb  lea     rdi, WPP_GLOBAL_Control
0x18004c8d2  cmp     rcx, rdi
0x18004c8d5  jz      short loc_18004C8B5
0x18004c8d7  test    byte ptr [rcx+1Ch], 4
0x18004c8db  jz      short loc_18004C8B5
0x18004c8dd  cmp     byte ptr [rcx+19h], 2
0x18004c8e1  jb      short loc_18004C8B5
0x18004c8e3  mov     edx, 9Dh
0x18004c8e8  lea     r9, aSzsidstring; "szSidString"
0x18004c8ef  jmp     short loc_18004C8A5
0x18004c8f1  test    r14, r14
0x18004c8f4  jnz     short loc_18004C923
0x18004c8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8fd  lea     rdi, WPP_GLOBAL_Control
0x18004c904  cmp     rcx, rdi
0x18004c907  jz      short loc_18004C8B5
0x18004c909  test    byte ptr [rcx+1Ch], 4
0x18004c90d  jz      short loc_18004C8B5
0x18004c90f  cmp     byte ptr [rcx+19h], 2
0x18004c913  jb      short loc_18004C8B5
0x18004c915  mov     edx, 9Eh
0x18004c91a  lea     r9, aPpnewdacl; "ppNewDacl"
0x18004c921  jmp     short loc_18004C8A5
0x18004c923  lea     rdx, [rbp+Sid]; Sid
0x18004c927  mov     [r9], rax
0x18004c92a  mov     rcx, r8; StringSid
0x18004c92d  xor     ebx, ebx
0x18004c92f  call    cs:__imp_ConvertStringSidToSidW
0x18004c935  mov     edi, 80070000h
0x18004c93a  mov     r13d, 0FFFF0000h
0x18004c940  test    eax, eax
0x18004c942  jnz     short loc_18004C9B6
0x18004c944  call    cs:__imp_GetLastError
0x18004c94a  mov     ebx, eax
0x18004c94c  test    eax, eax
0x18004c94e  jz      short loc_18004C96A
0x18004c950  test    r13d, eax
0x18004c953  jnz     short loc_18004C96A
0x18004c955  test    eax, eax
0x18004c957  jle     short loc_18004C95E
0x18004c959  movzx   ebx, ax
0x18004c95c  or      ebx, edi
0x18004c95e  and     ebx, 0D01FFFFFh
0x18004c964  or      ebx, 501F0000h
0x18004c96a  test    ebx, ebx
0x18004c96c  jns     short loc_18004C9B6
0x18004c96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c975  lea     rdi, WPP_GLOBAL_Control
0x18004c97c  cmp     rcx, rdi
0x18004c97f  jz      loc_18004CC29
0x18004c985  test    byte ptr [rcx+1Ch], 4
0x18004c989  jz      loc_18004CC29
0x18004c98f  cmp     byte ptr [rcx+19h], 2
0x18004c993  jb      loc_18004CC29
0x18004c999  mov     edx, 9Fh
0x18004c99e  mov     rcx, [rcx+10h]
0x18004c9a2  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004c9a9  mov     r9d, ebx
0x18004c9ac  call    WPP_SF_d
0x18004c9b1  jmp     loc_18004CC29
0x18004c9b6  mov     r9d, 2; dwAclInformationClass
0x18004c9bc  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18004c9c0  mov     rcx, r15; pAcl
0x18004c9c3  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18004c9c7  call    cs:__imp_GetAclInformation
0x18004c9cd  test    eax, eax
0x18004c9cf  jnz     short loc_18004CA30
0x18004c9d1  call    cs:__imp_GetLastError
0x18004c9d7  mov     ebx, eax
0x18004c9d9  test    eax, eax
0x18004c9db  jz      short loc_18004C9F7
0x18004c9dd  test    r13d, eax
0x18004c9e0  jnz     short loc_18004C9F7
0x18004c9e2  test    eax, eax
0x18004c9e4  jle     short loc_18004C9EB
0x18004c9e6  movzx   ebx, ax
0x18004c9e9  or      ebx, edi
0x18004c9eb  and     ebx, 0D020FFFFh
0x18004c9f1  or      ebx, 50200000h
0x18004c9f7  test    ebx, ebx
0x18004c9f9  jns     short loc_18004CA30
0x18004c9fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca02  lea     rdi, WPP_GLOBAL_Control
0x18004ca09  cmp     rcx, rdi
0x18004ca0c  jz      loc_18004CC29
0x18004ca12  test    byte ptr [rcx+1Ch], 4
0x18004ca16  jz      loc_18004CC29
0x18004ca1c  cmp     byte ptr [rcx+19h], 2
0x18004ca20  jb      loc_18004CC29
0x18004ca26  mov     edx, 0A0h
0x18004ca2b  jmp     loc_18004C99E
0x18004ca30  xor     esi, esi
0x18004ca32  lea     rdi, WPP_GLOBAL_Control
0x18004ca39  cmp     esi, dword ptr [rbp+pAclInformation]
0x18004ca3c  jnb     loc_18004CB80
0x18004ca42  lea     r8, [rbp+pAce]; pAce
0x18004ca46  mov     [rbp+pAce], 0
0x18004ca4e  mov     edx, esi; dwAceIndex
0x18004ca50  mov     rcx, r15; pAcl
0x18004ca53  call    cs:__imp_GetAce
0x18004ca59  test    eax, eax
0x18004ca5b  jnz     short loc_18004CA8F
0x18004ca5d  call    cs:__imp_GetLastError
0x18004ca63  mov     ebx, eax
0x18004ca65  test    eax, eax
0x18004ca67  jz      short loc_18004CA87
0x18004ca69  test    r13d, eax
0x18004ca6c  jnz     short loc_18004CA87
0x18004ca6e  test    eax, eax
0x18004ca70  jle     short loc_18004CA7B
0x18004ca72  movzx   ebx, ax
0x18004ca75  or      ebx, 80070000h
0x18004ca7b  and     ebx, 0D021FFFFh
0x18004ca81  or      ebx, 50210000h
0x18004ca87  test    ebx, ebx
0x18004ca89  js      loc_18004CB24
0x18004ca8f  mov     rdx, [rbp+pAce]
0x18004ca93  cmp     byte ptr [rdx], 0
0x18004ca96  jnz     loc_18004CB1D
0x18004ca9c  mov     rcx, [rbp+Sid]; pSid1
0x18004caa0  add     rdx, 8; pSid2
0x18004caa4  call    cs:__imp_EqualSid
0x18004caaa  test    eax, eax
0x18004caac  jz      short loc_18004CB1D
0x18004caae  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cab5  cmp     rcx, rdi
0x18004cab8  jz      short loc_18004CADB
0x18004caba  test    byte ptr [rcx+1Ch], 4
0x18004cabe  jz      short loc_18004CADB
0x18004cac0  cmp     byte ptr [rcx+19h], 4
0x18004cac4  jb      short loc_18004CADB
0x18004cac6  mov     rcx, [rcx+10h]
0x18004caca  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004cad1  mov     edx, 0A2h
0x18004cad6  call    WPP_SF_
0x18004cadb  mov     edx, esi; dwAceIndex
0x18004cadd  mov     rcx, r15; pAcl
0x18004cae0  call    cs:__imp_DeleteAce
0x18004cae6  test    eax, eax
0x18004cae8  jnz     short loc_18004CB18
0x18004caea  call    cs:__imp_GetLastError
0x18004caf0  mov     ebx, eax
0x18004caf2  test    eax, eax
0x18004caf4  jz      short loc_18004CB14
0x18004caf6  test    r13d, eax
0x18004caf9  jnz     short loc_18004CB14
0x18004cafb  test    eax, eax
0x18004cafd  jle     short loc_18004CB08
0x18004caff  movzx   ebx, ax
0x18004cb02  or      ebx, 80070000h
0x18004cb08  and     ebx, 0D022FFFFh
0x18004cb0e  or      ebx, 50220000h
0x18004cb14  test    ebx, ebx
0x18004cb16  js      short loc_18004CB52
0x18004cb18  dec     esi
0x18004cb1a  dec     dword ptr [rbp+pAclInformation]
0x18004cb1d  inc     esi
0x18004cb1f  jmp     loc_18004CA39
0x18004cb24  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb2b  cmp     rcx, rdi
0x18004cb2e  jz      loc_18004CC29
0x18004cb34  test    byte ptr [rcx+1Ch], 4
0x18004cb38  jz      loc_18004CC29
0x18004cb3e  cmp     byte ptr [rcx+19h], 2
0x18004cb42  jb      loc_18004CC29
0x18004cb48  mov     edx, 0A1h
0x18004cb4d  jmp     loc_18004C99E
0x18004cb52  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb59  cmp     rcx, rdi
0x18004cb5c  jz      loc_18004CC29
0x18004cb62  test    byte ptr [rcx+1Ch], 4
0x18004cb66  jz      loc_18004CC29
0x18004cb6c  cmp     byte ptr [rcx+19h], 2
0x18004cb70  jb      loc_18004CC29
0x18004cb76  mov     edx, 0A3h
0x18004cb7b  jmp     loc_18004C99E
0x18004cb80  mov     rax, [rbp+Sid]
0x18004cb84  lea     r9, [rbp+NewAcl]; NewAcl
0x18004cb88  mov     r8, r15; OldAcl
0x18004cb8b  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18004cb8f  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x18004cb93  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 0FFFFFFFFh
0x18004cb9a  mov     ecx, 1; cCountOfExplicitEntries
0x18004cb9f  mov     [rbp+pListOfExplicitEntries.grfAccessMode], 1
0x18004cba6  mov     [rbp+pListOfExplicitEntries.grfInheritance], 3
0x18004cbad  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x18004cbb5  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x18004cbbd  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 1
0x18004cbc4  call    cs:__imp_SetEntriesInAclW
0x18004cbca  test    eax, eax
0x18004cbcc  jz      short loc_18004CC1A
0x18004cbce  test    r13d, eax
0x18004cbd1  jnz     short loc_18004CBF2
0x18004cbd3  test    eax, eax
0x18004cbd5  jg      short loc_18004CBDB
0x18004cbd7  mov     ebx, eax
0x18004cbd9  jmp     short loc_18004CBE4
0x18004cbdb  movzx   ebx, ax
0x18004cbde  or      ebx, 80070000h
0x18004cbe4  and     ebx, 0D023FFFFh
0x18004cbea  or      ebx, 50230000h
0x18004cbf0  jmp     short loc_18004CBF4
0x18004cbf2  mov     ebx, eax
0x18004cbf4  test    ebx, ebx
0x18004cbf6  jns     short loc_18004CC1A
0x18004cbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cbff  cmp     rcx, rdi
0x18004cc02  jz      short loc_18004CC29
0x18004cc04  test    byte ptr [rcx+1Ch], 4
0x18004cc08  jz      short loc_18004CC29
0x18004cc0a  cmp     byte ptr [rcx+19h], 2
0x18004cc0e  jb      short loc_18004CC29
0x18004cc10  mov     edx, 0A4h
0x18004cc15  jmp     loc_18004C99E
0x18004cc1a  mov     rax, [rbp+NewAcl]
0x18004cc1e  mov     [r14], rax
0x18004cc21  mov     [rbp+NewAcl], 0
0x18004cc29  mov     rcx, [rbp+Sid]; hMem
0x18004cc2d  test    rcx, rcx
0x18004cc30  jz      short loc_18004CC38
0x18004cc32  call    cs:__imp_LocalFree
0x18004cc38  mov     rcx, [rbp+NewAcl]; hMem
0x18004cc3c  test    rcx, rcx
0x18004cc3f  jz      short loc_18004CC47
0x18004cc41  call    cs:__imp_LocalFree
0x18004cc47  mov     eax, ebx
0x18004cc49  mov     rcx, [rbp+var_8]
0x18004cc4d  xor     rcx, rsp; StackCookie
0x18004cc50  call    __security_check_cookie
0x18004cc55  add     rsp, 80h
0x18004cc5c  pop     r15
0x18004cc5e  pop     r14
0x18004cc60  pop     r13
0x18004cc62  pop     rdi
0x18004cc63  pop     rsi
0x18004cc64  pop     rbx
0x18004cc65  pop     rbp
0x18004cc66  retn
```
