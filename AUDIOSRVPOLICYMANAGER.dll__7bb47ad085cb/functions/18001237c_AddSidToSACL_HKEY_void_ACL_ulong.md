# AddSidToSACL(HKEY__ *,void *,_ACL * *,ulong *)

- ea: `0x18001237c`
- end: `0x1800125da`
- name: `?AddSidToSACL@@YAKPEAUHKEY__@@PEAXPEAPEAU_ACL@@PEAK@Z`
- size: `606`
- prototype: `unsigned int __fastcall(HKEY hKey, PSID pSid, struct _ACL **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180047ce0`

## callees

- `0x1800109d0`
- `0x18001237c`
- `0x180031960`
- `0x180031eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800125a1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800123f6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001242f`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800123f6`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18001242f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001244e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001244e`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180012512`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001253a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180012512`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001253a`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180012486`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180012486`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180012563`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180012563`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800124d7`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800124d7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012495`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012495`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800124f7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x1800124f7`

## pseudocode

```c
__int64 __fastcall AddSidToSACL(HKEY hKey, PSID pSid, struct _ACL **a3, unsigned int *a4)
{
  DWORD KeySecurity; // ebx
  void *v8; // rax
  void *v9; // r12
  struct _ACL *v10; // r15
  int v11; // edi
  DWORD v12; // r14d
  struct _ACL *v13; // rax
  struct _ACL *v14; // rdi
  DWORD i; // esi
  DWORD cbSecurityDescriptor; // [rsp+30h] [rbp-39h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+34h] [rbp-35h] BYREF
  WINBOOL bSaclPresent; // [rsp+38h] [rbp-31h] BYREF
  PACL pSacl; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pAceList; // [rsp+50h] [rbp-19h] BYREF
  struct _ACL **v23; // [rsp+58h] [rbp-11h]
  __int64 pAclInformation; // [rsp+60h] [rbp-9h] BYREF
  int v25; // [rsp+68h] [rbp-1h]

  v23 = a3;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  cbSecurityDescriptor = 0;
  KeySecurity = 87;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( pSid )
      {
        *a3 = 0;
        *a4 = 0;
        KeySecurity = RegGetKeySecurity(hKey, 0x10u, 0, &cbSecurityDescriptor);
        if ( KeySecurity == 122 )
        {
          v8 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)&std::nothrow);
          v9 = v8;
          if ( v8 )
          {
            KeySecurity = RegGetKeySecurity(hKey, 0x10u, v8, &cbSecurityDescriptor);
            if ( !KeySecurity )
            {
              if ( GetSecurityDescriptorSacl(v9, &bSaclPresent, &pSacl, &bSaclDefaulted) )
              {
                v10 = pSacl;
                KeySecurity = 8;
                pAceList = 0;
                v11 = 8;
                pAclInformation = 0;
                v25 = 0;
                if ( pSacl && GetAclInformation(pSacl, &pAclInformation, 0xCu, AclSizeInformation) )
                  v11 = HIDWORD(pAclInformation);
                v12 = v11 + GetLengthSid(pSid) + 8;
                if ( v12 > 0xFFFF )
                  v12 = 0xFFFF;
                v13 = (struct _ACL *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
                v14 = v13;
                if ( v13 )
                {
                  if ( InitializeAcl(v13, v12, 2u)
                    && AddAccessAllowedAceEx(v14, 2u, 3u, 1u, pSid)
                    && (pAce = 0, GetAce(v14, 0, &pAce)) )
                  {
                    KeySecurity = 0;
                    *(_BYTE *)pAce = 17;
                    if ( v10 )
                    {
                      for ( i = 0; i < (unsigned int)pAclInformation; ++i )
                      {
                        if ( GetAce(v10, i, &pAceList)
                          && *(_BYTE *)pAceList != 17
                          && !AddAce(v14, 2u, 0xFFFFFFFF, pAceList, *((unsigned __int16 *)pAceList + 1)) )
                        {
                          goto LABEL_24;
                        }
                      }
                    }
                  }
                  else
                  {
LABEL_24:
                    KeySecurity = GetLastError();
                  }
                }
                if ( KeySecurity )
                {
                  operator delete(v14);
                }
                else
                {
                  *v23 = v14;
                  *a4 = v12;
                }
              }
              else
              {
                KeySecurity = GetLastError();
              }
            }
            operator delete(v9);
          }
          else
          {
            return 122;
          }
        }
      }
    }
  }
  return KeySecurity;
}

```

## disassembly

```asm
0x18001237c  push    rbp
0x18001237e  push    rbx
0x18001237f  push    rsi
0x180012380  push    rdi
0x180012381  push    r12
0x180012383  push    r13
0x180012385  push    r14
0x180012387  push    r15
0x180012389  lea     rbp, [rsp-1Fh]
0x18001238e  sub     rsp, 88h
0x180012395  mov     rax, cs:__security_cookie
0x18001239c  xor     rax, rsp
0x18001239f  mov     [rbp+57h+var_50], rax
0x1800123a3  xor     r14d, r14d
0x1800123a6  mov     [rbp+57h+var_68], r8
0x1800123aa  mov     [rbp+57h+pSacl], r14
0x1800123ae  mov     r13, r9
0x1800123b1  mov     [rbp+57h+bSaclPresent], r14d
0x1800123b5  mov     rsi, rdx
0x1800123b8  mov     [rbp+57h+bSaclDefaulted], r14d
0x1800123bc  mov     rdi, rcx
0x1800123bf  mov     [rbp+57h+cbSecurityDescriptor], r14d
0x1800123c3  lea     ebx, [r14+57h]
0x1800123c7  test    r8, r8
0x1800123ca  jz      loc_1800125B8
0x1800123d0  test    r9, r9
0x1800123d3  jz      loc_1800125B8
0x1800123d9  test    rdx, rdx
0x1800123dc  jz      loc_1800125B8
0x1800123e2  mov     [r8], r14
0x1800123e5  lea     r15d, [r14+10h]
0x1800123e9  mov     [r9], r14d
0x1800123ec  mov     edx, r15d; SecurityInformation
0x1800123ef  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800123f3  xor     r8d, r8d; pSecurityDescriptor
0x1800123f6  call    cs:__imp_RegGetKeySecurity
0x1800123fc  mov     ebx, eax
0x1800123fe  cmp     eax, 7Ah ; 'z'
0x180012401  jnz     loc_1800125B8
0x180012407  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x18001240a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012411  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012416  mov     r12, rax
0x180012419  test    rax, rax
0x18001241c  jz      loc_1800125B3
0x180012422  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180012426  mov     r8, rax; pSecurityDescriptor
0x180012429  mov     edx, r15d; SecurityInformation
0x18001242c  mov     rcx, rdi; hKey
0x18001242f  call    cs:__imp_RegGetKeySecurity
0x180012435  mov     ebx, eax
0x180012437  test    eax, eax
0x180012439  jnz     loc_1800125A9
0x18001243f  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180012443  mov     rcx, r12; pSecurityDescriptor
0x180012446  lea     r8, [rbp+57h+pSacl]; pSacl
0x18001244a  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18001244e  call    cs:__imp_GetSecurityDescriptorSacl
0x180012454  test    eax, eax
0x180012456  jz      loc_1800125A1
0x18001245c  mov     r15, [rbp+57h+pSacl]
0x180012460  lea     ebx, [r14+8]
0x180012464  mov     [rbp+57h+pAceList], r14
0x180012468  mov     edi, ebx
0x18001246a  mov     [rbp+57h+pAclInformation], r14
0x18001246e  mov     [rbp+57h+var_58], r14d
0x180012472  test    r15, r15
0x180012475  jz      short loc_180012492
0x180012477  lea     r9d, [r14+2]; dwAclInformationClass
0x18001247b  mov     rcx, r15; pAcl
0x18001247e  lea     r8d, [r14+0Ch]; nAclInformationLength
0x180012482  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x180012486  call    cs:__imp_GetAclInformation
0x18001248c  test    eax, eax
0x18001248e  cmovnz  edi, dword ptr [rbp+57h+pAclInformation+4]
0x180012492  mov     rcx, rsi; pSid
0x180012495  call    cs:__imp_GetLengthSid
0x18001249b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800124a2  lea     r14d, [rax+8]
0x1800124a6  mov     eax, 0FFFFh
0x1800124ab  add     r14d, edi
0x1800124ae  cmp     r14d, eax
0x1800124b1  cmova   r14d, eax
0x1800124b5  mov     ecx, r14d; unsigned __int64
0x1800124b8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800124bd  mov     rdi, rax
0x1800124c0  test    rax, rax
0x1800124c3  jz      loc_180012579
0x1800124c9  mov     ebx, 2
0x1800124ce  mov     edx, r14d; nAclLength
0x1800124d1  mov     r8d, ebx; dwAclRevision
0x1800124d4  mov     rcx, rax; pAcl
0x1800124d7  call    cs:__imp_InitializeAcl
0x1800124dd  test    eax, eax
0x1800124df  jz      loc_180012571
0x1800124e5  lea     r9d, [rbx-1]; AccessMask
0x1800124e9  mov     [rsp+0C0h+pSid], rsi; pSid
0x1800124ee  lea     r8d, [rbx+1]; AceFlags
0x1800124f2  mov     edx, ebx; dwAceRevision
0x1800124f4  mov     rcx, rdi; pAcl
0x1800124f7  call    cs:__imp_AddAccessAllowedAceEx
0x1800124fd  test    eax, eax
0x1800124ff  jz      short loc_180012571
0x180012501  lea     r8, [rbp+57h+pAce]; pAce
0x180012505  mov     [rbp+57h+pAce], 0
0x18001250d  xor     edx, edx; dwAceIndex
0x18001250f  mov     rcx, rdi; pAcl
0x180012512  call    cs:__imp_GetAce
0x180012518  test    eax, eax
0x18001251a  jz      short loc_180012571
0x18001251c  mov     rax, [rbp+57h+pAce]
0x180012520  xor     ebx, ebx
0x180012522  mov     byte ptr [rax], 11h
0x180012525  test    r15, r15
0x180012528  jz      short loc_180012579
0x18001252a  xor     esi, esi
0x18001252c  cmp     esi, dword ptr [rbp+57h+pAclInformation]
0x18001252f  jnb     short loc_180012579
0x180012531  lea     r8, [rbp+57h+pAceList]; pAce
0x180012535  mov     edx, esi; dwAceIndex
0x180012537  mov     rcx, r15; pAcl
0x18001253a  call    cs:__imp_GetAce
0x180012540  test    eax, eax
0x180012542  jz      short loc_18001256D
0x180012544  mov     r9, [rbp+57h+pAceList]; pAceList
0x180012548  cmp     byte ptr [r9], 11h
0x18001254c  jz      short loc_18001256D
0x18001254e  movzx   eax, word ptr [r9+2]
0x180012553  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180012557  mov     edx, 2; dwAceRevision
0x18001255c  mov     dword ptr [rsp+0C0h+pSid], eax; nAceListLength
0x180012560  mov     rcx, rdi; pAcl
0x180012563  call    cs:__imp_AddAce
0x180012569  test    eax, eax
0x18001256b  jz      short loc_180012571
0x18001256d  inc     esi
0x18001256f  jmp     short loc_18001252C
0x180012571  call    cs:__imp_GetLastError
0x180012577  mov     ebx, eax
0x180012579  xor     eax, eax
0x18001257b  mov     rcx, rdi
0x18001257e  test    ebx, ebx
0x180012580  cmovnz  r14d, eax
0x180012584  cmovnz  rcx, rax
0x180012588  jz      short loc_180012594
0x18001258a  mov     rcx, rdi; void *
0x18001258d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012592  jmp     short loc_1800125A9
0x180012594  mov     rax, [rbp+57h+var_68]
0x180012598  mov     [rax], rcx
0x18001259b  mov     [r13+0], r14d
0x18001259f  jmp     short loc_1800125A9
0x1800125a1  call    cs:__imp_GetLastError
0x1800125a7  mov     ebx, eax
0x1800125a9  mov     rcx, r12; void *
0x1800125ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800125b1  jmp     short loc_1800125B8
0x1800125b3  mov     ebx, 7Ah ; 'z'
0x1800125b8  mov     eax, ebx
0x1800125ba  mov     rcx, [rbp+57h+var_50]
0x1800125be  xor     rcx, rsp; StackCookie
0x1800125c1  call    __security_check_cookie
0x1800125c6  add     rsp, 88h
0x1800125cd  pop     r15
0x1800125cf  pop     r14
0x1800125d1  pop     r13
0x1800125d3  pop     r12
0x1800125d5  pop     rdi
0x1800125d6  pop     rsi
0x1800125d7  pop     rbx
0x1800125d8  pop     rbp
0x1800125d9  retn
```
