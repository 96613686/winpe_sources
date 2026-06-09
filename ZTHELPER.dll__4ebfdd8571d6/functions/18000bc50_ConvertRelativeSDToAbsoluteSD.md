# ConvertRelativeSDToAbsoluteSD

- ea: `0x18000bc50`
- end: `0x18000be48`
- name: `ConvertRelativeSDToAbsoluteSD`
- size: `504`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c8a8`

## callees

- `0x1800014b0`
- `0x18000bc50`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb9`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000bcf6`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000bdaf`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000bcf6`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x18000bdaf`

## pseudocode

```c
__int64 __fastcall ConvertRelativeSDToAbsoluteSD(PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor, _QWORD *a2)
{
  PSECURITY_DESCRIPTOR v2; // rbx
  void *v4; // rdi
  struct _ACL *v5; // r14
  struct _ACL *pSacl; // r15
  void *pOwner; // r12
  void *v8; // r13
  DWORD LastError; // ebx
  void *pPrimaryGroup; // rax
  DWORD dwPrimaryGroupSize; // [rsp+70h] [rbp-1h] BYREF
  DWORD dwOwnerSize; // [rsp+74h] [rbp+3h] BYREF
  DWORD dwSaclSize; // [rsp+78h] [rbp+7h] BYREF
  DWORD dwDaclSize; // [rsp+7Ch] [rbp+Bh] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+80h] [rbp+Fh] BYREF

  v2 = pSelfRelativeSecurityDescriptor;
  dwAbsoluteSecurityDescriptorSize = 0;
  v4 = 0;
  dwDaclSize = 0;
  v5 = 0;
  dwSaclSize = 0;
  pSacl = 0;
  dwOwnerSize = 0;
  pOwner = 0;
  dwPrimaryGroupSize = 0;
  v8 = 0;
  if ( a2 && (*a2 = 0, pSelfRelativeSecurityDescriptor) )
  {
    if ( MakeAbsoluteSD(
           pSelfRelativeSecurityDescriptor,
           0,
           &dwAbsoluteSecurityDescriptorSize,
           0,
           &dwDaclSize,
           0,
           &dwSaclSize,
           0,
           &dwOwnerSize,
           0,
           &dwPrimaryGroupSize) )
    {
LABEL_6:
      v4 = (void *)Dns_Allocate(dwAbsoluteSecurityDescriptorSize);
      if ( v4
        && (v5 = (struct _ACL *)Dns_Allocate(dwDaclSize)) != 0
        && (pSacl = (struct _ACL *)Dns_Allocate(dwSaclSize)) != 0
        && (pOwner = (void *)Dns_Allocate(dwOwnerSize)) != 0
        && (pPrimaryGroup = (void *)Dns_Allocate(dwPrimaryGroupSize), (v8 = pPrimaryGroup) != 0) )
      {
        if ( MakeAbsoluteSD(
               v2,
               v4,
               &dwAbsoluteSecurityDescriptorSize,
               v5,
               &dwDaclSize,
               pSacl,
               &dwSaclSize,
               pOwner,
               &dwOwnerSize,
               pPrimaryGroup,
               &dwPrimaryGroupSize) )
        {
          LastError = 0;
          *a2 = v4;
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        LastError = 14;
      }
      goto LABEL_16;
    }
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v2 = pSelfRelativeSecurityDescriptor;
      goto LABEL_6;
    }
  }
  else
  {
    LastError = 87;
  }
LABEL_16:
  Dns_Free(v4);
  Dns_Free(v5);
  Dns_Free(pSacl);
  Dns_Free(pOwner);
  Dns_Free(v8);
  if ( LastError && (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 54, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000bc50  mov     r11, rsp
0x18000bc53  mov     [r11+18h], rbx
0x18000bc57  push    rbp
0x18000bc58  push    rsi
0x18000bc59  push    rdi
0x18000bc5a  push    r12
0x18000bc5c  push    r13
0x18000bc5e  push    r14
0x18000bc60  push    r15
0x18000bc62  lea     rbp, [r11-5Fh]
0x18000bc66  sub     rsp, 90h
0x18000bc6d  mov     rax, cs:__security_cookie
0x18000bc74  xor     rax, rsp
0x18000bc77  mov     [rbp+57h+var_40], rax
0x18000bc7b  mov     rbx, rcx
0x18000bc7e  mov     [rbp+57h+var_60], rcx
0x18000bc82  xor     ecx, ecx
0x18000bc84  mov     rsi, rdx
0x18000bc87  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], ecx
0x18000bc8a  mov     edi, ecx
0x18000bc8c  mov     [rbp+57h+dwDaclSize], ecx
0x18000bc8f  mov     r14d, ecx
0x18000bc92  mov     [rbp+57h+dwSaclSize], ecx
0x18000bc95  mov     r15d, ecx
0x18000bc98  mov     [rbp+57h+dwOwnerSize], ecx
0x18000bc9b  mov     r12d, ecx
0x18000bc9e  mov     [rbp+57h+dwPrimaryGroupSize], ecx
0x18000bca1  mov     r13d, ecx
0x18000bca4  test    rdx, rdx
0x18000bca7  jz      loc_18000BDCC
0x18000bcad  mov     [rdx], rcx
0x18000bcb0  test    rbx, rbx
0x18000bcb3  jz      loc_18000BDCC
0x18000bcb9  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000bcbd  xor     r9d, r9d; pDacl
0x18000bcc0  mov     [r11-78h], rax
0x18000bcc4  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000bcc8  mov     [r11-80h], rcx
0x18000bccc  lea     rax, [rbp+57h+dwOwnerSize]
0x18000bcd0  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000bcd5  xor     edx, edx; pAbsoluteSecurityDescriptor
0x18000bcd7  mov     [rsp+0C0h+pOwner], rcx; pOwner
0x18000bcdc  lea     rax, [rbp+57h+dwSaclSize]
0x18000bce0  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000bce5  lea     rax, [rbp+57h+dwDaclSize]
0x18000bce9  mov     [rsp+0C0h+pSacl], rcx; pSacl
0x18000bcee  mov     rcx, rbx; pSelfRelativeSecurityDescriptor
0x18000bcf1  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000bcf6  call    cs:__imp_MakeAbsoluteSD
0x18000bcfc  test    eax, eax
0x18000bcfe  jnz     short loc_18000BD15
0x18000bd00  call    cs:__imp_GetLastError
0x18000bd06  mov     ebx, eax
0x18000bd08  cmp     eax, 7Ah ; 'z'
0x18000bd0b  jnz     loc_18000BDD1
0x18000bd11  mov     rbx, [rbp+57h+var_60]
0x18000bd15  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]
0x18000bd18  call    Dns_Allocate
0x18000bd1d  mov     rdi, rax
0x18000bd20  test    rax, rax
0x18000bd23  jnz     short loc_18000BD2F
0x18000bd25  mov     ebx, 0Eh
0x18000bd2a  jmp     loc_18000BDD1
0x18000bd2f  mov     ecx, [rbp+57h+dwDaclSize]
0x18000bd32  call    Dns_Allocate
0x18000bd37  mov     r14, rax
0x18000bd3a  test    rax, rax
0x18000bd3d  jz      short loc_18000BD25
0x18000bd3f  mov     ecx, [rbp+57h+dwSaclSize]
0x18000bd42  call    Dns_Allocate
0x18000bd47  mov     r15, rax
0x18000bd4a  test    rax, rax
0x18000bd4d  jz      short loc_18000BD25
0x18000bd4f  mov     ecx, [rbp+57h+dwOwnerSize]
0x18000bd52  call    Dns_Allocate
0x18000bd57  mov     r12, rax
0x18000bd5a  test    rax, rax
0x18000bd5d  jz      short loc_18000BD25
0x18000bd5f  mov     ecx, [rbp+57h+dwPrimaryGroupSize]
0x18000bd62  call    Dns_Allocate
0x18000bd67  mov     r13, rax
0x18000bd6a  test    rax, rax
0x18000bd6d  jz      short loc_18000BD25
0x18000bd6f  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x18000bd73  mov     r9, r14; pDacl
0x18000bd76  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x18000bd7b  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x18000bd7f  mov     [rsp+0C0h+pPrimaryGroup], r13; pPrimaryGroup
0x18000bd84  lea     rax, [rbp+57h+dwOwnerSize]
0x18000bd88  mov     [rsp+0C0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x18000bd8d  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x18000bd90  mov     [rsp+0C0h+pOwner], r12; pOwner
0x18000bd95  lea     rax, [rbp+57h+dwSaclSize]
0x18000bd99  mov     [rsp+0C0h+lpdwSaclSize], rax; lpdwSaclSize
0x18000bd9e  mov     rcx, rbx; pSelfRelativeSecurityDescriptor
0x18000bda1  lea     rax, [rbp+57h+dwDaclSize]
0x18000bda5  mov     [rsp+0C0h+pSacl], r15; pSacl
0x18000bdaa  mov     [rsp+0C0h+lpdwDaclSize], rax; lpdwDaclSize
0x18000bdaf  call    cs:__imp_MakeAbsoluteSD
0x18000bdb5  test    eax, eax
0x18000bdb7  jnz     short loc_18000BDC3
0x18000bdb9  call    cs:__imp_GetLastError
0x18000bdbf  mov     ebx, eax
0x18000bdc1  jmp     short loc_18000BDD1
0x18000bdc3  xor     ebx, ebx
0x18000bdc5  mov     [rsi], rdi
0x18000bdc8  xor     edi, edi
0x18000bdca  jmp     short loc_18000BDD1
0x18000bdcc  mov     ebx, 57h ; 'W'
0x18000bdd1  mov     rcx, rdi; lpMem
0x18000bdd4  call    Dns_Free
0x18000bdd9  mov     rcx, r14; lpMem
0x18000bddc  call    Dns_Free
0x18000bde1  mov     rcx, r15; lpMem
0x18000bde4  call    Dns_Free
0x18000bde9  mov     rcx, r12; lpMem
0x18000bdec  call    Dns_Free
0x18000bdf1  mov     rcx, r13; lpMem
0x18000bdf4  call    Dns_Free
0x18000bdf9  test    ebx, ebx
0x18000bdfb  jz      short loc_18000BE1F
0x18000bdfd  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000be04  jz      short loc_18000BE1F
0x18000be06  mov     edx, 36h ; '6'
0x18000be0b  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000be12  mov     ecx, 40Bh
0x18000be17  mov     r9d, ebx
0x18000be1a  call    WPP_SF_d
0x18000be1f  mov     eax, ebx
0x18000be21  mov     rcx, [rbp+57h+var_40]
0x18000be25  xor     rcx, rsp; StackCookie
0x18000be28  call    __security_check_cookie
0x18000be2d  mov     rbx, [rsp+0C0h+arg_10]
0x18000be35  add     rsp, 90h
0x18000be3c  pop     r15
0x18000be3e  pop     r14
0x18000be40  pop     r13
0x18000be42  pop     r12
0x18000be44  pop     rdi
0x18000be45  pop     rsi
0x18000be46  pop     rbp
0x18000be47  retn
```
