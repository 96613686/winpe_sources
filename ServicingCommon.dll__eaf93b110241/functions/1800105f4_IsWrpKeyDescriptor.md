# IsWrpKeyDescriptor

- ea: `0x1800105f4`
- end: `0x18001074f`
- name: `IsWrpKeyDescriptor`
- size: `347`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010250`

## callees

- `0x1800105f4`
- `0x18001f0bc`
- `0x1800293a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180010727`
- `KERNEL32!LocalFree` at `0x180010727`
- `ntdll!RtlEqualSid` at `0x1800106cc`
- `ntdll!RtlEqualSid` at `0x1800106cc`
- `ADVAPI32!GetAce` at `0x1800106b1`
- `ADVAPI32!GetAce` at `0x1800106b1`
- `ADVAPI32!GetAclInformation` at `0x180010677`
- `ADVAPI32!GetAclInformation` at `0x180010677`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001064a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18001064a`

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
0x1800105f4  push    rbp
0x1800105f6  push    rbx
0x1800105f7  push    rsi
0x1800105f8  push    rdi
0x1800105f9  push    r12
0x1800105fb  push    r14
0x1800105fd  mov     rbp, rsp
0x180010600  sub     rsp, 58h
0x180010604  mov     rax, cs:__security_cookie
0x18001060b  xor     rax, rsp
0x18001060e  mov     [rbp+var_10], rax
0x180010612  xor     eax, eax
0x180010614  xor     ebx, ebx
0x180010616  mov     [rbp+pDacl], rbx
0x18001061a  mov     rdi, rcx
0x18001061d  mov     [rbp+pAclInformation], rax
0x180010621  mov     [rbp+var_18], eax
0x180010624  mov     [rbp+bDaclPresent], eax
0x180010627  mov     [rbp+bDaclDefaulted], eax
0x18001062a  call    InitTrustedSid
0x18001062f  mov     rsi, rax
0x180010632  test    rax, rax
0x180010635  jz      loc_180010733
0x18001063b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18001063f  mov     rcx, rdi; pSecurityDescriptor
0x180010642  lea     r8, [rbp+pDacl]; pDacl
0x180010646  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001064a  call    cs:__imp_GetSecurityDescriptorDacl
0x180010651  nop     dword ptr [rax+rax+00h]
0x180010656  test    eax, eax
0x180010658  jz      loc_180010724
0x18001065e  mov     rcx, [rbp+pDacl]; pAcl
0x180010662  test    rcx, rcx
0x180010665  jz      loc_180010724
0x18001066b  lea     r9d, [rbx+2]; dwAclInformationClass
0x18001066f  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x180010673  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x180010677  call    cs:__imp_GetAclInformation
0x18001067e  nop     dword ptr [rax+rax+00h]
0x180010683  test    eax, eax
0x180010685  jz      loc_180010724
0x18001068b  mov     eax, dword ptr [rbp+pAclInformation]
0x18001068e  test    eax, eax
0x180010690  jz      loc_180010724
0x180010696  xor     r14b, r14b
0x180010699  lea     r12d, [rbx+1]
0x18001069d  xor     edi, edi
0x18001069f  cmp     edi, eax
0x1800106a1  jnb     short loc_18001071D
0x1800106a3  mov     rcx, [rbp+pDacl]; pAcl
0x1800106a7  lea     r8, [rbp+pAce]; pAce
0x1800106ab  mov     edx, edi; dwAceIndex
0x1800106ad  mov     [rbp+pAce], rbx
0x1800106b1  call    cs:__imp_GetAce
0x1800106b8  nop     dword ptr [rax+rax+00h]
0x1800106bd  test    eax, eax
0x1800106bf  jz      short loc_180010715
0x1800106c1  mov     rdx, [rbp+pAce]
0x1800106c5  mov     rcx, rsi; Sid1
0x1800106c8  add     rdx, 8; Sid2
0x1800106cc  call    cs:__imp_RtlEqualSid
0x1800106d3  nop     dword ptr [rax+rax+00h]
0x1800106d8  test    al, al
0x1800106da  jz      short loc_180010704
0x1800106dc  mov     rcx, [rbp+pAce]
0x1800106e0  mov     al, [rcx]
0x1800106e2  test    al, al
0x1800106e4  jnz     short loc_1800106FD
0x1800106e6  cmp     dword ptr [rcx+4], 10000000h
0x1800106ed  jz      short loc_1800106F8
0x1800106ef  cmp     dword ptr [rcx+4], 0F003Fh
0x1800106f6  jnz     short loc_180010715
0x1800106f8  mov     r14b, r12b
0x1800106fb  jmp     short loc_180010715
0x1800106fd  cmp     al, r12b
0x180010700  jnz     short loc_180010715
0x180010702  jmp     short loc_180010724
0x180010704  mov     rax, [rbp+pAce]
0x180010708  cmp     [rax], bl
0x18001070a  jnz     short loc_180010715
0x18001070c  test    dword ptr [rax+4], 500D0006h
0x180010713  jnz     short loc_180010724
0x180010715  mov     eax, dword ptr [rbp+pAclInformation]
0x180010718  add     edi, r12d
0x18001071b  jmp     short loc_18001069F
0x18001071d  test    r14b, r14b
0x180010720  cmovnz  ebx, r12d
0x180010724  mov     rcx, rsi; hMem
0x180010727  call    cs:__imp_LocalFree
0x18001072e  nop     dword ptr [rax+rax+00h]
0x180010733  mov     eax, ebx
0x180010735  mov     rcx, [rbp+var_10]
0x180010739  xor     rcx, rsp; StackCookie
0x18001073c  call    __security_check_cookie
0x180010741  add     rsp, 58h
0x180010745  pop     r14
0x180010747  pop     r12
0x180010749  pop     rdi
0x18001074a  pop     rsi
0x18001074b  pop     rbx
0x18001074c  pop     rbp
0x18001074d  retn
```
