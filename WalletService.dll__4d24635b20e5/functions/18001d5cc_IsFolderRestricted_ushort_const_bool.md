# IsFolderRestricted(ushort const *,bool &)

- ea: `0x18001d5cc`
- end: `0x18001d808`
- name: `?IsFolderRestricted@@YAJPEBGAEA_N@Z`
- size: `572`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d50c`

## callees

- `0x180002e48`
- `0x18001c658`
- `0x18001d5cc`
- `0x180043090`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d793`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d793`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d7cf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d7d9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d7cf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d7d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7a2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d769`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d77b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d769`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d77b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001d74f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001d74f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18001d728`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18001d728`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001d6f5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001d6f5`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d65f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d6a6`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d65f`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18001d6a6`

## pseudocode

```c
__int64 __fastcall IsFolderRestricted(LPCWSTR lpFileName, bool *a2)
{
  bool v3; // zf
  unsigned int v5; // edi
  signed int v6; // eax
  void *v7; // rbx
  signed int LastError; // eax
  char v9; // r14
  DWORD i; // esi
  char *v11; // r15
  signed int v12; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-50h] BYREF
  WINBOOL bDaclPresent; // [rsp+34h] [rbp-4Ch] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-48h] BYREF
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  PSID v18; // [rsp+48h] [rbp-38h] BYREF
  PSID pSid1; // [rsp+50h] [rbp-30h] BYREF
  LPVOID pAce; // [rsp+58h] [rbp-28h] BYREF
  DWORD pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  __int64 v22; // [rsp+64h] [rbp-1Ch]

  v3 = g_fUnitTestContext == 0;
  v5 = 0;
  pSid1 = 0;
  v18 = 0;
  *a2 = 0;
  if ( v3 )
  {
    v6 = CreateLocalWellKnownSid(WinLocalSystemSid, &pSid1);
    if ( v6 < 0 || (v6 = CreateLocalWellKnownSid(WinBuiltinAdministratorsSid, &v18), v6 < 0) )
    {
      v5 = v6;
      goto LABEL_31;
    }
    nLengthNeeded = 0;
    if ( GetFileSecurityW(lpFileName, 4u, 0, 0, &nLengthNeeded) )
    {
      v5 = -2147418113;
      goto LABEL_31;
    }
    if ( GetLastError() == 122 )
    {
      v7 = operator new[](nLengthNeeded);
      if ( !v7 )
      {
        v5 = -2147024882;
        goto LABEL_31;
      }
      if ( GetFileSecurityW(lpFileName, 4u, v7, nLengthNeeded, &nLengthNeeded) )
      {
        pDacl = 0;
        bDaclDefaulted = 0;
        bDaclPresent = 0;
        if ( GetSecurityDescriptorDacl(v7, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        {
          pAclInformation = 0;
          v22 = 8;
          if ( !bDaclPresent || !pDacl )
          {
LABEL_23:
            operator delete(v7);
            goto LABEL_31;
          }
          if ( GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
          {
            pAce = 0;
            v9 = 1;
            for ( i = 0; i < pAclInformation; ++i )
            {
              if ( !GetAce(pDacl, i, &pAce) )
                goto LABEL_8;
              v11 = (char *)pAce;
              if ( !EqualSid(pSid1, (char *)pAce + 8) )
                v9 = EqualSid(v18, v11 + 8) ? v9 : 0;
            }
            *a2 = v9;
            goto LABEL_23;
          }
        }
      }
LABEL_8:
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v5 = -2143748092;
      }
      goto LABEL_23;
    }
    v12 = GetLastError();
    v5 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v5 = -2143748092;
    }
  }
LABEL_31:
  operator delete[](v18);
  operator delete[](pSid1);
  return v5;
}

```

## disassembly

```asm
0x18001d5cc  mov     [rsp-38h+arg_10], rbx
0x18001d5d1  push    rbp
0x18001d5d2  push    rsi
0x18001d5d3  push    rdi
0x18001d5d4  push    r12
0x18001d5d6  push    r13
0x18001d5d8  push    r14
0x18001d5da  push    r15
0x18001d5dc  mov     rbp, rsp
0x18001d5df  sub     rsp, 80h
0x18001d5e6  mov     rax, cs:__security_cookie
0x18001d5ed  xor     rax, rsp
0x18001d5f0  mov     [rbp+var_10], rax
0x18001d5f4  xor     r13d, r13d
0x18001d5f7  mov     r12, rdx
0x18001d5fa  cmp     cs:?g_fUnitTestContext@@3HA, r13d; int g_fUnitTestContext
0x18001d601  mov     rsi, rcx
0x18001d604  mov     edi, r13d
0x18001d607  mov     [rbp+pSid1], r13
0x18001d60b  mov     [rbp+var_38], r13
0x18001d60f  mov     [rdx], r13b
0x18001d612  jnz     loc_18001D7CB
0x18001d618  lea     rdx, [rbp+pSid1]
0x18001d61c  lea     ecx, [r13+16h]; WellKnownSidType
0x18001d620  call    ?CreateLocalWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z; CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE,std::unique_ptr<uchar [0]> &)
0x18001d625  test    eax, eax
0x18001d627  js      loc_18001D7C9
0x18001d62d  lea     rdx, [rbp+var_38]
0x18001d631  lea     ecx, [r13+1Ah]; WellKnownSidType
0x18001d635  call    ?CreateLocalWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z; CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE,std::unique_ptr<uchar [0]> &)
0x18001d63a  test    eax, eax
0x18001d63c  js      loc_18001D7C9
0x18001d642  lea     rax, [rbp+nLengthNeeded]
0x18001d646  mov     [rbp+nLengthNeeded], r13d
0x18001d64a  lea     r14d, [r13+4]
0x18001d64e  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001d653  mov     edx, r14d; RequestedInformation
0x18001d656  xor     r9d, r9d; nLength
0x18001d659  xor     r8d, r8d; pSecurityDescriptor
0x18001d65c  mov     rcx, rsi; lpFileName
0x18001d65f  call    cs:__imp_GetFileSecurityW
0x18001d665  test    eax, eax
0x18001d667  jnz     loc_18001D7C2
0x18001d66d  call    cs:__imp_GetLastError
0x18001d673  cmp     eax, 7Ah ; 'z'
0x18001d676  jnz     loc_18001D7A2
0x18001d67c  mov     ecx, [rbp+nLengthNeeded]; unsigned __int64
0x18001d67f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d684  mov     rbx, rax
0x18001d687  test    rax, rax
0x18001d68a  jz      loc_18001D79B
0x18001d690  mov     r9d, [rbp+nLengthNeeded]; nLength
0x18001d694  lea     rax, [rbp+nLengthNeeded]
0x18001d698  mov     r8, rbx; pSecurityDescriptor
0x18001d69b  mov     [rsp+80h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18001d6a0  mov     edx, r14d; RequestedInformation
0x18001d6a3  mov     rcx, rsi; lpFileName
0x18001d6a6  call    cs:__imp_GetFileSecurityW
0x18001d6ac  test    eax, eax
0x18001d6ae  jnz     short loc_18001D6DA
0x18001d6b0  call    cs:__imp_GetLastError
0x18001d6b6  mov     edi, eax
0x18001d6b8  test    eax, eax
0x18001d6ba  jz      short loc_18001D6D0
0x18001d6bc  jle     loc_18001D790
0x18001d6c2  movzx   edi, ax
0x18001d6c5  or      edi, 80070000h
0x18001d6cb  jmp     loc_18001D790
0x18001d6d0  mov     edi, 80390004h
0x18001d6d5  jmp     loc_18001D790
0x18001d6da  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18001d6de  mov     [rbp+pDacl], r13
0x18001d6e2  lea     r8, [rbp+pDacl]; pDacl
0x18001d6e6  mov     [rbp+bDaclDefaulted], r13d
0x18001d6ea  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001d6ee  mov     [rbp+bDaclPresent], r13d
0x18001d6f2  mov     rcx, rbx; pSecurityDescriptor
0x18001d6f5  call    cs:__imp_GetSecurityDescriptorDacl
0x18001d6fb  test    eax, eax
0x18001d6fd  jz      short loc_18001D6B0
0x18001d6ff  mov     [rbp+pAclInformation], r13d
0x18001d703  mov     [rbp+var_1C], 8
0x18001d70b  cmp     [rbp+bDaclPresent], r13d
0x18001d70f  jz      short loc_18001D790
0x18001d711  mov     rcx, [rbp+pDacl]; pAcl
0x18001d715  test    rcx, rcx
0x18001d718  jz      short loc_18001D790
0x18001d71a  mov     r9d, 2; dwAclInformationClass
0x18001d720  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18001d724  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18001d728  call    cs:__imp_GetAclInformation
0x18001d72e  test    eax, eax
0x18001d730  jz      loc_18001D6B0
0x18001d736  mov     [rbp+pAce], r13
0x18001d73a  mov     r14b, 1
0x18001d73d  mov     esi, r13d
0x18001d740  cmp     esi, [rbp+pAclInformation]
0x18001d743  jnb     short loc_18001D78C
0x18001d745  mov     rcx, [rbp+pDacl]; pAcl
0x18001d749  lea     r8, [rbp+pAce]; pAce
0x18001d74d  mov     edx, esi; dwAceIndex
0x18001d74f  call    cs:__imp_GetAce
0x18001d755  test    eax, eax
0x18001d757  jz      loc_18001D6B0
0x18001d75d  mov     r15, [rbp+pAce]
0x18001d761  mov     rcx, [rbp+pSid1]; pSid1
0x18001d765  lea     rdx, [r15+8]; pSid2
0x18001d769  call    cs:__imp_EqualSid
0x18001d76f  test    eax, eax
0x18001d771  jnz     short loc_18001D788
0x18001d773  mov     rcx, [rbp+var_38]; pSid1
0x18001d777  lea     rdx, [r15+8]; pSid2
0x18001d77b  call    cs:__imp_EqualSid
0x18001d781  neg     eax
0x18001d783  sbb     cl, cl
0x18001d785  and     r14b, cl
0x18001d788  inc     esi
0x18001d78a  jmp     short loc_18001D740
0x18001d78c  mov     [r12], r14b
0x18001d790  mov     rcx, rbx
0x18001d793  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d799  jmp     short loc_18001D7CB
0x18001d79b  mov     edi, 8007000Eh
0x18001d7a0  jmp     short loc_18001D7CB
0x18001d7a2  call    cs:__imp_GetLastError
0x18001d7a8  mov     edi, eax
0x18001d7aa  test    eax, eax
0x18001d7ac  jz      short loc_18001D7BB
0x18001d7ae  jle     short loc_18001D7CB
0x18001d7b0  movzx   edi, ax
0x18001d7b3  or      edi, 80070000h
0x18001d7b9  jmp     short loc_18001D7CB
0x18001d7bb  mov     edi, 80390004h
0x18001d7c0  jmp     short loc_18001D7CB
0x18001d7c2  mov     edi, 8000FFFFh
0x18001d7c7  jmp     short loc_18001D7CB
0x18001d7c9  mov     edi, eax
0x18001d7cb  mov     rcx, [rbp+var_38]
0x18001d7cf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d7d5  mov     rcx, [rbp+pSid1]
0x18001d7d9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d7df  mov     eax, edi
0x18001d7e1  mov     rcx, [rbp+var_10]
0x18001d7e5  xor     rcx, rsp; StackCookie
0x18001d7e8  call    __security_check_cookie
0x18001d7ed  mov     rbx, [rsp+80h+arg_10]
0x18001d7f5  add     rsp, 80h
0x18001d7fc  pop     r15
0x18001d7fe  pop     r14
0x18001d800  pop     r13
0x18001d802  pop     r12
0x18001d804  pop     rdi
0x18001d805  pop     rsi
0x18001d806  pop     rbp
0x18001d807  retn
```
