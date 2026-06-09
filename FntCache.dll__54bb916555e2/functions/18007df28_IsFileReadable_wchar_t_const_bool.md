# IsFileReadable(wchar_t const *,bool)

- ea: `0x18007df28`
- end: `0x18007e123`
- name: `?IsFileReadable@@YA_NPEB_W_N@Z`
- size: `507`
- prototype: `bool __fastcall(const wchar_t *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007def0`

## callees

- `0x18007df28`
- `0x18007e12c`
- `0x1800a1558`
- `0x1800aa650`
- `0x1800aa674`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007dff2`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18007dff2`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18007dfc4`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18007dfc4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007df92`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18007df92`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e028`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e052`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e0d2`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e028`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e052`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007e0d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsFileReadable(const wchar_t *a1, unsigned int a2)
{
  int v2; // edi
  struct _SECURITY_DESCRIPTOR *FileSecurityHelper; // rbx
  int v4; // r14d
  int v5; // esi
  DWORD i; // r15d
  char *v7; // r12
  bool v8; // zf
  LPVOID pAce; // [rsp+20h] [rbp-30h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+28h] [rbp-28h] BYREF
  WINBOOL bDaclPresent; // [rsp+2Ch] [rbp-24h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-20h] BYREF
  __int64 pAclInformation; // [rsp+38h] [rbp-18h] BYREF
  int v15; // [rsp+40h] [rbp-10h]

  v2 = byte_18013C30C == 0 ? 0x20000 : 0;
  FileSecurityHelper = GetFileSecurityHelper(a1, a2);
  pAce = FileSecurityHelper;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pDacl = 0;
  if ( !GetSecurityDescriptorDacl(FileSecurityHelper, &bDaclPresent, &pDacl, &bDaclDefaulted) )
LABEL_2:
    OSException::ThrowLastError();
  if ( pDacl )
  {
    pAclInformation = 0;
    v15 = 0;
    if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
      goto LABEL_2;
    v4 = 0;
    v5 = 0;
    for ( i = 0; i < (unsigned int)pAclInformation; ++i )
    {
      pAce = 0;
      if ( GetAce(pDacl, i, &pAce) && (*((_DWORD *)pAce + 1) & 0x20000) != 0 )
      {
        if ( *(_BYTE *)pAce )
        {
          v8 = *(_BYTE *)pAce == 1;
        }
        else
        {
          v7 = (char *)pAce + 8;
          if ( v4 != 0x20000 && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid) )
          {
            v4 |= *((_DWORD *)pAce + 1) & 0x20000;
          }
          else if ( v5 == 0x20000 || !IsWellKnownSid(v7, WinLocalSystemSid) )
          {
            if ( v2 != 0x20000 )
            {
              if ( IsWellKnownSid(v7, WinBuiltinAnyPackageSid) )
                v2 |= *((_DWORD *)pAce + 1) & 0x20000;
            }
          }
          else
          {
            v5 |= *((_DWORD *)pAce + 1) & 0x20000;
          }
          v8 = (v4 & v5 & v2) == 0x20000;
        }
        if ( v8 )
          break;
      }
    }
    operator delete(FileSecurityHelper, 0x28u);
    return (v4 & v5 & v2) == 0x20000;
  }
  else
  {
    operator delete(FileSecurityHelper, 0x28u);
    return 1;
  }
}

```

## disassembly

```asm
0x18007df28  mov     [rsp-28h+arg_8], rbx
0x18007df2d  mov     [rsp-28h+arg_10], rsi
0x18007df32  push    rbp
0x18007df33  push    rdi
0x18007df34  push    r12
0x18007df36  push    r14
0x18007df38  push    r15
0x18007df3a  mov     rbp, rsp
0x18007df3d  sub     rsp, 50h
0x18007df41  mov     rax, cs:__security_cookie
0x18007df48  xor     rax, rsp
0x18007df4b  mov     [rbp+var_8], rax
0x18007df4f  mov     al, cs:byte_18013C30C
0x18007df55  neg     al
0x18007df57  sbb     edi, edi
0x18007df59  not     edi
0x18007df5b  and     edi, 20000h
0x18007df61  call    ?GetFileSecurityHelper@@YAPEAU_SECURITY_DESCRIPTOR@@PEB_WK@Z; GetFileSecurityHelper(wchar_t const *,ulong)
0x18007df66  mov     rbx, rax
0x18007df69  mov     [rbp+pAce], rax
0x18007df6d  mov     [rbp+bDaclPresent], 0
0x18007df74  mov     [rbp+bDaclDefaulted], 0
0x18007df7b  mov     [rbp+pDacl], 0
0x18007df83  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18007df87  lea     r8, [rbp+pDacl]; pDacl
0x18007df8b  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18007df8f  mov     rcx, rax; pSecurityDescriptor
0x18007df92  call    cs:__imp_GetSecurityDescriptorDacl
0x18007df98  test    eax, eax
0x18007df9a  jnz     short loc_18007DFA2
0x18007df9c  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x18007dfa2  mov     rcx, [rbp+pDacl]; pAcl
0x18007dfa6  test    rcx, rcx
0x18007dfa9  jz      loc_18007E109
0x18007dfaf  xor     eax, eax
0x18007dfb1  mov     [rbp+pAclInformation], rax
0x18007dfb5  mov     [rbp+var_10], eax
0x18007dfb8  lea     r9d, [rax+2]; dwAclInformationClass
0x18007dfbc  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18007dfc0  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18007dfc4  call    cs:__imp_GetAclInformation
0x18007dfca  test    eax, eax
0x18007dfcc  jz      short loc_18007DF9C
0x18007dfce  xor     r14d, r14d
0x18007dfd1  xor     esi, esi
0x18007dfd3  xor     r15d, r15d
0x18007dfd6  cmp     dword ptr [rbp+pAclInformation], esi
0x18007dfd9  jbe     loc_18007E086
0x18007dfdf  mov     [rbp+pAce], 0
0x18007dfe7  lea     r8, [rbp+pAce]; pAce
0x18007dfeb  mov     edx, r15d; dwAceIndex
0x18007dfee  mov     rcx, [rbp+pDacl]; pAcl
0x18007dff2  call    cs:__imp_GetAce
0x18007dff8  test    eax, eax
0x18007dffa  jz      short loc_18007E079
0x18007dffc  mov     rax, [rbp+pAce]
0x18007e000  test    dword ptr [rax+4], 20000h
0x18007e007  jz      short loc_18007E079
0x18007e009  mov     cl, [rax]
0x18007e00b  test    cl, cl
0x18007e00d  jnz     loc_18007E11A
0x18007e013  lea     r12, [rax+8]
0x18007e017  cmp     r14d, 20000h
0x18007e01e  jz      short loc_18007E036
0x18007e020  mov     edx, 1Bh; WellKnownSidType
0x18007e025  mov     rcx, r12; pSid
0x18007e028  call    cs:__imp_IsWellKnownSid
0x18007e02e  test    eax, eax
0x18007e030  jnz     loc_18007E0F4
0x18007e036  cmp     esi, 20000h
0x18007e03c  jnz     loc_18007E0CA
0x18007e042  cmp     edi, 20000h
0x18007e048  jz      short loc_18007E06B
0x18007e04a  mov     edx, 54h ; 'T'; WellKnownSidType
0x18007e04f  mov     rcx, r12; pSid
0x18007e052  call    cs:__imp_IsWellKnownSid
0x18007e058  test    eax, eax
0x18007e05a  jz      short loc_18007E06B
0x18007e05c  mov     rax, [rbp+pAce]
0x18007e060  mov     ecx, [rax+4]
0x18007e063  and     ecx, 20000h
0x18007e069  or      edi, ecx
0x18007e06b  mov     eax, edi
0x18007e06d  and     eax, esi
0x18007e06f  and     eax, r14d
0x18007e072  cmp     eax, 20000h
0x18007e077  jz      short loc_18007E086
0x18007e079  inc     r15d
0x18007e07c  cmp     r15d, dword ptr [rbp+pAclInformation]
0x18007e080  jb      loc_18007DFDF
0x18007e086  and     edi, esi
0x18007e088  and     edi, r14d
0x18007e08b  cmp     edi, 20000h
0x18007e091  setz    dil
0x18007e095  mov     edx, 28h ; '('; unsigned __int64
0x18007e09a  mov     rcx, rbx; void *
0x18007e09d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007e0a2  mov     al, dil
0x18007e0a5  mov     rcx, [rbp+var_8]
0x18007e0a9  xor     rcx, rsp; StackCookie
0x18007e0ac  call    __security_check_cookie
0x18007e0b1  lea     r11, [rsp+50h+var_s0]
0x18007e0b6  mov     rbx, [r11+38h]
0x18007e0ba  mov     rsi, [r11+40h]
0x18007e0be  mov     rsp, r11
0x18007e0c1  pop     r15
0x18007e0c3  pop     r14
0x18007e0c5  pop     r12
0x18007e0c7  pop     rdi
0x18007e0c8  pop     rbp
0x18007e0c9  retn
0x18007e0ca  mov     edx, 16h; WellKnownSidType
0x18007e0cf  mov     rcx, r12; pSid
0x18007e0d2  call    cs:__imp_IsWellKnownSid
0x18007e0d8  test    eax, eax
0x18007e0da  jz      loc_18007E042
0x18007e0e0  mov     rax, [rbp+pAce]
0x18007e0e4  mov     ecx, [rax+4]
0x18007e0e7  and     ecx, 20000h
0x18007e0ed  or      esi, ecx
0x18007e0ef  jmp     loc_18007E06B
0x18007e0f4  mov     rax, [rbp+pAce]
0x18007e0f8  mov     ecx, [rax+4]
0x18007e0fb  and     ecx, 20000h
0x18007e101  or      r14d, ecx
0x18007e104  jmp     loc_18007E06B
0x18007e109  mov     edx, 28h ; '('; unsigned __int64
0x18007e10e  mov     rcx, rbx; void *
0x18007e111  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007e116  mov     al, 1
0x18007e118  jmp     short loc_18007E0A5
0x18007e11a  cmp     cl, 1
0x18007e11d  jmp     loc_18007E077
```
