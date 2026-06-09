# IsWrpKeyDescriptor

- ea: `0x18001abd8`
- end: `0x18001ad33`
- name: `IsWrpKeyDescriptor`
- size: `347`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a450`

## callees

- `0x18001abd8`
- `0x18002125c`
- `0x18002d2b0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001ad0b`
- `KERNEL32!LocalFree` at `0x18001ad0b`
- `ntdll!RtlEqualSid` at `0x18001acb0`
- `ntdll!RtlEqualSid` at `0x18001acb0`
- `ADVAPI32!GetAce` at `0x18001ac95`
- `ADVAPI32!GetAce` at `0x18001ac95`
- `ADVAPI32!GetAclInformation` at `0x18001ac5b`
- `ADVAPI32!GetAclInformation` at `0x18001ac5b`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001ac2e`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001ac2e`

## pseudocode

```c
__int64 __fastcall IsWrpKeyDescriptor(PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned int v1; // ebx
  void *inited; // rsi
  DWORD v4; // eax
  char v5; // r14
  DWORD i; // edi
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+28h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+2Ch] [rbp-2Ch] BYREF
  PACL pDacl; // [rsp+30h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v1 = 0;
  pDacl = 0;
  pAclInformation = 0;
  v13 = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  inited = (void *)InitTrustedSid();
  if ( inited )
  {
    if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( pDacl )
      {
        if ( GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
        {
          v4 = pAclInformation;
          if ( (_DWORD)pAclInformation )
          {
            v5 = 0;
            for ( i = 0; i < v4; ++i )
            {
              pAce = 0;
              if ( GetAce(pDacl, i, &pAce) )
              {
                if ( RtlEqualSid(inited, (char *)pAce + 8) )
                {
                  if ( *(_BYTE *)pAce )
                  {
                    if ( *(_BYTE *)pAce == 1 )
                      goto LABEL_21;
                  }
                  else if ( *((_DWORD *)pAce + 1) == 0x10000000 || *((_DWORD *)pAce + 1) == 983103 )
                  {
                    v5 = 1;
                  }
                }
                else if ( !*(_BYTE *)pAce && (*((_DWORD *)pAce + 1) & 0x500D0006) != 0 )
                {
                  goto LABEL_21;
                }
              }
              v4 = pAclInformation;
            }
            if ( v5 )
              v1 = 1;
          }
        }
      }
    }
LABEL_21:
    LocalFree(inited);
  }
  return v1;
}

```

## disassembly

```asm
0x18001abd8  push    rbp
0x18001abda  push    rbx
0x18001abdb  push    rsi
0x18001abdc  push    rdi
0x18001abdd  push    r12
0x18001abdf  push    r14
0x18001abe1  mov     rbp, rsp
0x18001abe4  sub     rsp, 58h
0x18001abe8  mov     rax, cs:__security_cookie
0x18001abef  xor     rax, rsp
0x18001abf2  mov     [rbp+var_10], rax
0x18001abf6  xor     eax, eax
0x18001abf8  xor     ebx, ebx
0x18001abfa  mov     [rbp+pDacl], rbx
0x18001abfe  mov     rdi, rcx
0x18001ac01  mov     [rbp+pAclInformation], rax
0x18001ac05  mov     [rbp+var_18], eax
0x18001ac08  mov     [rbp+bDaclPresent], eax
0x18001ac0b  mov     [rbp+bDaclDefaulted], eax
0x18001ac0e  call    InitTrustedSid
0x18001ac13  mov     rsi, rax
0x18001ac16  test    rax, rax
0x18001ac19  jz      loc_18001AD17
0x18001ac1f  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18001ac23  mov     rcx, rdi; pSecurityDescriptor
0x18001ac26  lea     r8, [rbp+pDacl]; pDacl
0x18001ac2a  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001ac2e  call    cs:__imp_GetSecurityDescriptorDacl
0x18001ac35  nop     dword ptr [rax+rax+00h]
0x18001ac3a  test    eax, eax
0x18001ac3c  jz      loc_18001AD08
0x18001ac42  mov     rcx, [rbp+pDacl]; pAcl
0x18001ac46  test    rcx, rcx
0x18001ac49  jz      loc_18001AD08
0x18001ac4f  lea     r9d, [rbx+2]; dwAclInformationClass
0x18001ac53  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x18001ac57  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18001ac5b  call    cs:__imp_GetAclInformation
0x18001ac62  nop     dword ptr [rax+rax+00h]
0x18001ac67  test    eax, eax
0x18001ac69  jz      loc_18001AD08
0x18001ac6f  mov     eax, dword ptr [rbp+pAclInformation]
0x18001ac72  test    eax, eax
0x18001ac74  jz      loc_18001AD08
0x18001ac7a  xor     r14b, r14b
0x18001ac7d  lea     r12d, [rbx+1]
0x18001ac81  xor     edi, edi
0x18001ac83  cmp     edi, eax
0x18001ac85  jnb     short loc_18001AD01
0x18001ac87  mov     rcx, [rbp+pDacl]; pAcl
0x18001ac8b  lea     r8, [rbp+pAce]; pAce
0x18001ac8f  mov     edx, edi; dwAceIndex
0x18001ac91  mov     [rbp+pAce], rbx
0x18001ac95  call    cs:__imp_GetAce
0x18001ac9c  nop     dword ptr [rax+rax+00h]
0x18001aca1  test    eax, eax
0x18001aca3  jz      short loc_18001ACF9
0x18001aca5  mov     rdx, [rbp+pAce]
0x18001aca9  mov     rcx, rsi; Sid1
0x18001acac  add     rdx, 8; Sid2
0x18001acb0  call    cs:__imp_RtlEqualSid
0x18001acb7  nop     dword ptr [rax+rax+00h]
0x18001acbc  test    al, al
0x18001acbe  jz      short loc_18001ACE8
0x18001acc0  mov     rcx, [rbp+pAce]
0x18001acc4  mov     al, [rcx]
0x18001acc6  test    al, al
0x18001acc8  jnz     short loc_18001ACE1
0x18001acca  cmp     dword ptr [rcx+4], 10000000h
0x18001acd1  jz      short loc_18001ACDC
0x18001acd3  cmp     dword ptr [rcx+4], 0F003Fh
0x18001acda  jnz     short loc_18001ACF9
0x18001acdc  mov     r14b, r12b
0x18001acdf  jmp     short loc_18001ACF9
0x18001ace1  cmp     al, r12b
0x18001ace4  jnz     short loc_18001ACF9
0x18001ace6  jmp     short loc_18001AD08
0x18001ace8  mov     rax, [rbp+pAce]
0x18001acec  cmp     [rax], bl
0x18001acee  jnz     short loc_18001ACF9
0x18001acf0  test    dword ptr [rax+4], 500D0006h
0x18001acf7  jnz     short loc_18001AD08
0x18001acf9  mov     eax, dword ptr [rbp+pAclInformation]
0x18001acfc  add     edi, r12d
0x18001acff  jmp     short loc_18001AC83
0x18001ad01  test    r14b, r14b
0x18001ad04  cmovnz  ebx, r12d
0x18001ad08  mov     rcx, rsi; hMem
0x18001ad0b  call    cs:__imp_LocalFree
0x18001ad12  nop     dword ptr [rax+rax+00h]
0x18001ad17  mov     eax, ebx
0x18001ad19  mov     rcx, [rbp+var_10]
0x18001ad1d  xor     rcx, rsp; StackCookie
0x18001ad20  call    __security_check_cookie
0x18001ad25  add     rsp, 58h
0x18001ad29  pop     r14
0x18001ad2b  pop     r12
0x18001ad2d  pop     rdi
0x18001ad2e  pop     rsi
0x18001ad2f  pop     rbx
0x18001ad30  pop     rbp
0x18001ad31  retn
```
