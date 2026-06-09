# SetRegistryKeyIntegrityLevel(HKEY__ *,void *)

- ea: `0x18000fea4`
- end: `0x1800101a4`
- name: `?SetRegistryKeyIntegrityLevel@@YAJPEAUHKEY__@@PEAX@Z`
- size: `768`
- prototype: `__int64 __fastcall(HKEY hKey, PSID pSid)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f9d0`
- `0x1800101ac`
- `0x1800478e4`

## callees

- `0x18000fea4`
- `0x1800109d0`
- `0x180031960`
- `0x180031eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010185`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000ff07`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000ff46`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000ff07`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18000ff46`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18001012b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18001012b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000ff65`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18000ff65`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800100b3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x1800100b3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001002c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180010104`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18001002c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180010104`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000ff9d`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000ff9d`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001016e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18001016e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000ffee`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000ffee`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ffac`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ffac`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001009d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001009d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180010011`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180010011`

## pseudocode

```c
__int64 __fastcall SetRegistryKeyIntegrityLevel(HKEY hKey, PSID pSid)
{
  HKEY v3; // rdi
  int KeySecurity; // ebx
  struct _ACL *v5; // r15
  void *v6; // rax
  void *v7; // r12
  struct _ACL *v8; // r14
  int v9; // edi
  DWORD v10; // r13d
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  DWORD i; // esi
  bool v14; // sf
  signed int LastError; // eax
  DWORD cbSecurityDescriptor; // [rsp+30h] [rbp-49h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+34h] [rbp-45h] BYREF
  WINBOOL bSaclPresent; // [rsp+38h] [rbp-41h] BYREF
  PACL pSacl; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-31h] BYREF
  LPVOID pAceList; // [rsp+50h] [rbp-29h] BYREF
  HKEY v23; // [rsp+58h] [rbp-21h]
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  __int64 pAclInformation; // [rsp+88h] [rbp+Fh] BYREF
  int v27; // [rsp+90h] [rbp+17h]

  v23 = hKey;
  v3 = hKey;
  KeySecurity = -2147024809;
  if ( !pSid )
    return (unsigned int)KeySecurity;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  cbSecurityDescriptor = 0;
  v5 = 0;
  KeySecurity = RegGetKeySecurity(hKey, 0x10u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
  {
LABEL_22:
    v14 = KeySecurity < 0;
    if ( KeySecurity <= 0 )
      goto LABEL_23;
    goto LABEL_41;
  }
  v6 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    KeySecurity = RegGetKeySecurity(v3, 0x10u, v6, &cbSecurityDescriptor);
    if ( !KeySecurity )
    {
      if ( GetSecurityDescriptorSacl(v7, &bSaclPresent, &pSacl, &bSaclDefaulted) )
      {
        v8 = pSacl;
        KeySecurity = 8;
        pAceList = 0;
        v9 = 8;
        pAclInformation = 0;
        v27 = 0;
        if ( pSacl && GetAclInformation(pSacl, &pAclInformation, 0xCu, AclSizeInformation) )
          v9 = HIDWORD(pAclInformation);
        v10 = v9 + GetLengthSid(pSid) + 8;
        if ( v10 > 0xFFFF )
          v10 = 0xFFFF;
        v11 = (struct _ACL *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
        v12 = v11;
        if ( !v11 )
          goto LABEL_36;
        if ( InitializeAcl(v11, v10, 2u)
          && AddAccessAllowedAceEx(v12, 2u, 3u, 1u, pSid)
          && (pAce = 0, GetAce(v12, 0, &pAce)) )
        {
          KeySecurity = 0;
          *(_BYTE *)pAce = 17;
          if ( v8 )
          {
            for ( i = 0; i < (unsigned int)pAclInformation; ++i )
            {
              if ( GetAce(v8, i, &pAceList)
                && *(_BYTE *)pAceList != 17
                && !AddAce(v12, 2u, 0xFFFFFFFF, pAceList, *((unsigned __int16 *)pAceList + 1)) )
              {
                goto LABEL_38;
              }
            }
          }
        }
        else
        {
LABEL_38:
          KeySecurity = GetLastError();
        }
        if ( KeySecurity )
LABEL_36:
          operator delete(v12);
        else
          v5 = v12;
        v3 = v23;
      }
      else
      {
        KeySecurity = GetLastError();
      }
    }
    operator delete(v7);
    goto LABEL_22;
  }
  LOWORD(KeySecurity) = 122;
LABEL_41:
  KeySecurity = (unsigned __int16)KeySecurity | 0x80070000;
  v14 = KeySecurity < 0;
LABEL_23:
  if ( !v14 )
  {
    v25 = 0;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      || !SetSecurityDescriptorSacl(pSecurityDescriptor, 1, v5, 0)
      || RegSetKeySecurity(v3, 0x10u, pSecurityDescriptor) )
    {
      LastError = GetLastError();
      KeySecurity = LastError;
      if ( LastError > 0 )
        KeySecurity = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v5 )
      operator delete(v5);
  }
  return (unsigned int)KeySecurity;
}

```

## disassembly

```asm
0x18000fea4  mov     [rsp-8+arg_10], rbx
0x18000fea9  push    rbp
0x18000feaa  push    rsi
0x18000feab  push    rdi
0x18000feac  push    r12
0x18000feae  push    r13
0x18000feb0  push    r14
0x18000feb2  push    r15
0x18000feb4  lea     rbp, [rsp-27h]
0x18000feb9  sub     rsp, 0A0h
0x18000fec0  mov     rax, cs:__security_cookie
0x18000fec7  xor     rax, rsp
0x18000feca  mov     [rbp+57h+var_38], rax
0x18000fece  xor     r13d, r13d
0x18000fed1  mov     [rbp+57h+var_78], rcx
0x18000fed5  mov     rsi, rdx
0x18000fed8  mov     rdi, rcx
0x18000fedb  mov     ebx, 80070057h
0x18000fee0  test    rdx, rdx
0x18000fee3  jz      loc_1800100D2
0x18000fee9  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000feed  mov     [rbp+57h+pSacl], r13
0x18000fef1  xor     r8d, r8d; pSecurityDescriptor
0x18000fef4  mov     [rbp+57h+bSaclPresent], r13d
0x18000fef8  lea     edx, [r13+10h]; SecurityInformation
0x18000fefc  mov     [rbp+57h+bSaclDefaulted], r13d
0x18000ff00  mov     [rbp+57h+cbSecurityDescriptor], r13d
0x18000ff04  mov     r15d, r13d
0x18000ff07  call    cs:__imp_RegGetKeySecurity
0x18000ff0d  mov     ebx, eax
0x18000ff0f  mov     r14d, 80070000h
0x18000ff15  cmp     eax, 7Ah ; 'z'
0x18000ff18  jnz     loc_180010079
0x18000ff1e  mov     ecx, [rbp+57h+cbSecurityDescriptor]; unsigned __int64
0x18000ff21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ff28  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ff2d  mov     r12, rax
0x18000ff30  test    rax, rax
0x18000ff33  jz      loc_180010192
0x18000ff39  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18000ff3d  mov     r8, rax; pSecurityDescriptor
0x18000ff40  lea     edx, [rbx-6Ah]; SecurityInformation
0x18000ff43  mov     rcx, rdi; hKey
0x18000ff46  call    cs:__imp_RegGetKeySecurity
0x18000ff4c  mov     ebx, eax
0x18000ff4e  test    eax, eax
0x18000ff50  jnz     loc_180010071
0x18000ff56  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18000ff5a  mov     rcx, r12; pSecurityDescriptor
0x18000ff5d  lea     r8, [rbp+57h+pSacl]; pSacl
0x18000ff61  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18000ff65  call    cs:__imp_GetSecurityDescriptorSacl
0x18000ff6b  test    eax, eax
0x18000ff6d  jz      loc_180010185
0x18000ff73  mov     r14, [rbp+57h+pSacl]
0x18000ff77  lea     ebx, [r13+8]
0x18000ff7b  mov     [rbp+57h+pAceList], r13
0x18000ff7f  mov     edi, ebx
0x18000ff81  mov     [rbp+57h+pAclInformation], r13
0x18000ff85  mov     [rbp+57h+var_40], r13d
0x18000ff89  test    r14, r14
0x18000ff8c  jz      short loc_18000FFA9
0x18000ff8e  lea     r9d, [r13+2]; dwAclInformationClass
0x18000ff92  mov     rcx, r14; pAcl
0x18000ff95  lea     r8d, [r13+0Ch]; nAclInformationLength
0x18000ff99  lea     rdx, [rbp+57h+pAclInformation]; pAclInformation
0x18000ff9d  call    cs:__imp_GetAclInformation
0x18000ffa3  test    eax, eax
0x18000ffa5  cmovnz  edi, dword ptr [rbp+57h+pAclInformation+4]
0x18000ffa9  mov     rcx, rsi; pSid
0x18000ffac  call    cs:__imp_GetLengthSid
0x18000ffb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ffb9  lea     r13d, [rax+8]
0x18000ffbd  mov     eax, 0FFFFh
0x18000ffc2  add     r13d, edi
0x18000ffc5  cmp     r13d, eax
0x18000ffc8  cmova   r13d, eax
0x18000ffcc  mov     ecx, r13d; unsigned __int64
0x18000ffcf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ffd4  mov     rdi, rax
0x18000ffd7  test    rax, rax
0x18000ffda  jz      loc_180010141
0x18000ffe0  mov     ebx, 2
0x18000ffe5  mov     edx, r13d; nAclLength
0x18000ffe8  mov     r8d, ebx; dwAclRevision
0x18000ffeb  mov     rcx, rax; pAcl
0x18000ffee  call    cs:__imp_InitializeAcl
0x18000fff4  xor     r13d, r13d
0x18000fff7  test    eax, eax
0x18000fff9  jz      loc_180010178
0x18000ffff  lea     r9d, [rbx-1]; AccessMask
0x180010003  mov     [rsp+0D0h+pSid], rsi; pSid
0x180010008  lea     r8d, [rbx+1]; AceFlags
0x18001000c  mov     edx, ebx; dwAceRevision
0x18001000e  mov     rcx, rdi; pAcl
0x180010011  call    cs:__imp_AddAccessAllowedAceEx
0x180010017  test    eax, eax
0x180010019  jz      loc_180010178
0x18001001f  lea     r8, [rbp+57h+pAce]; pAce
0x180010023  mov     [rbp+57h+pAce], r13
0x180010027  xor     edx, edx; dwAceIndex
0x180010029  mov     rcx, rdi; pAcl
0x18001002c  call    cs:__imp_GetAce
0x180010032  test    eax, eax
0x180010034  jz      loc_180010178
0x18001003a  mov     rax, [rbp+57h+pAce]
0x18001003e  mov     ebx, r13d
0x180010041  mov     byte ptr [rax], 11h
0x180010044  test    r14, r14
0x180010047  jz      short loc_180010055
0x180010049  mov     esi, r13d
0x18001004c  cmp     esi, dword ptr [rbp+57h+pAclInformation]
0x18001004f  jb      loc_1800100FB
0x180010055  test    ebx, ebx
0x180010057  mov     rcx, rdi
0x18001005a  cmovnz  rcx, r13
0x18001005e  jnz     loc_180010141
0x180010064  mov     r15, rcx
0x180010067  mov     rdi, [rbp+57h+var_78]
0x18001006b  mov     r14d, 80070000h
0x180010071  mov     rcx, r12; void *
0x180010074  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010079  test    ebx, ebx
0x18001007b  jg      loc_180010197
0x180010081  js      short loc_1800100D2
0x180010083  xor     eax, eax
0x180010085  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180010089  xorps   xmm0, xmm0
0x18001008c  mov     [rbp+57h+var_50], rax
0x180010090  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180010094  lea     esi, [rax+1]
0x180010097  mov     edx, esi; dwRevision
0x180010099  movups  [rbp+57h+var_60], xmm0
0x18001009d  call    cs:__imp_InitializeSecurityDescriptor
0x1800100a3  test    eax, eax
0x1800100a5  jz      short loc_1800100BD
0x1800100a7  xor     r9d, r9d; bSaclDefaulted
0x1800100aa  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800100ae  mov     r8, r15; pSacl
0x1800100b1  mov     edx, esi; bSaclPresent
0x1800100b3  call    cs:__imp_SetSecurityDescriptorSacl
0x1800100b9  test    eax, eax
0x1800100bb  jnz     short loc_18001011F
0x1800100bd  call    cs:__imp_GetLastError
0x1800100c3  mov     ebx, eax
0x1800100c5  test    eax, eax
0x1800100c7  jg      loc_18001014E
0x1800100cd  test    r15, r15
0x1800100d0  jnz     short loc_180010137
0x1800100d2  mov     eax, ebx
0x1800100d4  mov     rcx, [rbp+57h+var_38]
0x1800100d8  xor     rcx, rsp; StackCookie
0x1800100db  call    __security_check_cookie
0x1800100e0  mov     rbx, [rsp+0D0h+arg_10]
0x1800100e8  add     rsp, 0A0h
0x1800100ef  pop     r15
0x1800100f1  pop     r14
0x1800100f3  pop     r13
0x1800100f5  pop     r12
0x1800100f7  pop     rdi
0x1800100f8  pop     rsi
0x1800100f9  pop     rbp
0x1800100fa  retn
0x1800100fb  lea     r8, [rbp+57h+pAceList]; pAce
0x1800100ff  mov     edx, esi; dwAceIndex
0x180010101  mov     rcx, r14; pAcl
0x180010104  call    cs:__imp_GetAce
0x18001010a  test    eax, eax
0x18001010c  jz      short loc_180010118
0x18001010e  mov     r9, [rbp+57h+pAceList]; pAceList
0x180010112  cmp     byte ptr [r9], 11h
0x180010116  jnz     short loc_180010159
0x180010118  inc     esi
0x18001011a  jmp     loc_18001004C
0x18001011f  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180010123  mov     edx, 10h; SecurityInformation
0x180010128  mov     rcx, rdi; hKey
0x18001012b  call    cs:__imp_RegSetKeySecurity
0x180010131  test    eax, eax
0x180010133  jnz     short loc_1800100BD
0x180010135  jmp     short loc_1800100CD
0x180010137  mov     rcx, r15; void *
0x18001013a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001013f  jmp     short loc_1800100D2
0x180010141  mov     rcx, rdi; void *
0x180010144  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010149  jmp     loc_180010067
0x18001014e  movzx   ebx, ax
0x180010151  or      ebx, r14d
0x180010154  jmp     loc_1800100CD
0x180010159  movzx   eax, word ptr [r9+2]
0x18001015e  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x180010162  mov     edx, 2; dwAceRevision
0x180010167  mov     dword ptr [rsp+0D0h+pSid], eax; nAceListLength
0x18001016b  mov     rcx, rdi; pAcl
0x18001016e  call    cs:__imp_AddAce
0x180010174  test    eax, eax
0x180010176  jnz     short loc_180010118
0x180010178  call    cs:__imp_GetLastError
0x18001017e  mov     ebx, eax
0x180010180  jmp     loc_180010055
0x180010185  call    cs:__imp_GetLastError
0x18001018b  mov     ebx, eax
0x18001018d  jmp     loc_180010071
0x180010192  mov     ebx, 7Ah ; 'z'
0x180010197  movzx   ebx, bx
0x18001019a  or      ebx, r14d
0x18001019d  test    ebx, ebx
0x18001019f  jmp     loc_180010081
```
