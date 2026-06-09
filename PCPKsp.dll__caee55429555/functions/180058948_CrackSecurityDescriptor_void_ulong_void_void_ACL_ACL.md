# CrackSecurityDescriptor(void *,ulong,void * *,void * *,_ACL * *,_ACL * *)

- ea: `0x180058948`
- end: `0x180058aa9`
- name: `?CrackSecurityDescriptor@@YAJPEAXKPEAPEAX1PEAPEAU_ACL@@2@Z`
- size: `353`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, unsigned int@<edx>, void **@<r8>, void **@<r9>, struct _ACL **, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018e20`

## callees

- `0x180015660`
- `0x1800157c0`
- `0x180058948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800589c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800589c6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180058a1d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180058a1d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180058a4b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180058a4b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800589b6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x1800589b6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800589f9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x1800589f9`

## string_xrefs

- `0x180058967`: `CrackSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CrackSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        char a2,
        void **a3,
        void **a4,
        struct _ACL **a5,
        struct _ACL **a6)
{
  signed int LastError; // eax
  unsigned int v11; // ebx
  struct _ACL **v12; // rcx
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-58h] BYREF
  WINBOOL bSaclPresent; // [rsp+24h] [rbp-54h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+28h] [rbp-50h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+2Ch] [rbp-4Ch] BYREF
  WINBOOL bDaclDefaulted; // [rsp+30h] [rbp-48h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+34h] [rbp-44h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-40h] BYREF
  PACL pSacl; // [rsp+40h] [rbp-38h] BYREF
  PSID pOwner; // [rsp+48h] [rbp-30h] BYREF
  PSID pGroup; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v24[32]; // [rsp+58h] [rbp-20h] BYREF
  int v25; // [rsp+B8h] [rbp+40h] BYREF

  v25 = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v24, L"CrackSecurityDescriptor", &v25);
  pDacl = 0;
  pSacl = 0;
  pOwner = 0;
  pGroup = 0;
  bSaclPresent = 0;
  bDaclPresent = 0;
  bSaclDefaulted = 0;
  bDaclDefaulted = 0;
  bOwnerDefaulted = 0;
  bGroupDefaulted = 0;
  if ( ((a2 & 1) == 0 || GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, &bOwnerDefaulted))
    && ((a2 & 2) == 0 || GetSecurityDescriptorGroup(pSecurityDescriptor, &pGroup, &bGroupDefaulted)) )
  {
    if ( (a2 & 4) != 0 )
    {
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
        goto LABEL_3;
      if ( !bDaclPresent )
        pDacl = 0;
    }
    if ( (a2 & 8) == 0 )
    {
LABEL_16:
      v12 = a5;
      v11 = v25;
      *a3 = pOwner;
      *a4 = pGroup;
      *v12 = pDacl;
      *a6 = pSacl;
      goto LABEL_17;
    }
    if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      if ( !bSaclPresent )
        pSacl = 0;
      goto LABEL_16;
    }
  }
LABEL_3:
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  v25 = v11;
LABEL_17:
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v24);
  return v11;
}

```

## disassembly

```asm
0x180058948  push    rbp
0x18005894a  push    rbx
0x18005894b  push    rsi
0x18005894c  push    rdi
0x18005894d  push    r14
0x18005894f  push    r15
0x180058951  mov     rbp, rsp
0x180058954  sub     rsp, 78h
0x180058958  mov     r14, r8
0x18005895b  mov     ebx, edx
0x18005895d  mov     rdi, rcx
0x180058960  lea     r8, [rbp+arg_8]; int *
0x180058964  xor     r15d, r15d
0x180058967  lea     rdx, aCracksecurityd; "CrackSecurityDescriptor"
0x18005896e  lea     rcx, [rbp+var_20]; this
0x180058972  mov     [rbp+arg_8], r15d
0x180058976  mov     rsi, r9
0x180058979  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x18005897e  mov     [rbp+pDacl], r15
0x180058982  mov     [rbp+pSacl], r15
0x180058986  mov     [rbp+pOwner], r15
0x18005898a  mov     [rbp+pGroup], r15
0x18005898e  mov     [rbp+bSaclPresent], r15d
0x180058992  mov     [rbp+bDaclPresent], r15d
0x180058996  mov     [rbp+bSaclDefaulted], r15d
0x18005899a  mov     [rbp+bDaclDefaulted], r15d
0x18005899e  mov     [rbp+bOwnerDefaulted], r15d
0x1800589a2  mov     [rbp+bGroupDefaulted], r15d
0x1800589a6  test    bl, 1
0x1800589a9  jz      short loc_1800589E9
0x1800589ab  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x1800589af  mov     rcx, rdi; pSecurityDescriptor
0x1800589b2  lea     rdx, [rbp+pOwner]; pOwner
0x1800589b6  call    cs:__imp_GetSecurityDescriptorOwner
0x1800589bd  nop     dword ptr [rax+rax+00h]
0x1800589c2  test    eax, eax
0x1800589c4  jnz     short loc_1800589E9
0x1800589c6  call    cs:__imp_GetLastError
0x1800589cd  nop     dword ptr [rax+rax+00h]
0x1800589d2  mov     ebx, eax
0x1800589d4  test    eax, eax
0x1800589d6  jle     short loc_1800589E1
0x1800589d8  movzx   ebx, ax
0x1800589db  or      ebx, 80070000h
0x1800589e1  mov     [rbp+arg_8], ebx
0x1800589e4  jmp     loc_180058A90
0x1800589e9  test    bl, 2
0x1800589ec  jz      short loc_180058A09
0x1800589ee  lea     r8, [rbp+bGroupDefaulted]; lpbGroupDefaulted
0x1800589f2  mov     rcx, rdi; pSecurityDescriptor
0x1800589f5  lea     rdx, [rbp+pGroup]; pGroup
0x1800589f9  call    cs:__imp_GetSecurityDescriptorGroup
0x180058a00  nop     dword ptr [rax+rax+00h]
0x180058a05  test    eax, eax
0x180058a07  jz      short loc_1800589C6
0x180058a09  test    bl, 4
0x180058a0c  jz      short loc_180058A37
0x180058a0e  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180058a12  mov     rcx, rdi; pSecurityDescriptor
0x180058a15  lea     r8, [rbp+pDacl]; pDacl
0x180058a19  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180058a1d  call    cs:__imp_GetSecurityDescriptorDacl
0x180058a24  nop     dword ptr [rax+rax+00h]
0x180058a29  test    eax, eax
0x180058a2b  jz      short loc_1800589C6
0x180058a2d  cmp     [rbp+bDaclPresent], r15d
0x180058a31  jnz     short loc_180058A37
0x180058a33  mov     [rbp+pDacl], r15
0x180058a37  test    bl, 8
0x180058a3a  jz      short loc_180058A69
0x180058a3c  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180058a40  mov     rcx, rdi; pSecurityDescriptor
0x180058a43  lea     r8, [rbp+pSacl]; pSacl
0x180058a47  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180058a4b  call    cs:__imp_GetSecurityDescriptorSacl
0x180058a52  nop     dword ptr [rax+rax+00h]
0x180058a57  test    eax, eax
0x180058a59  jz      loc_1800589C6
0x180058a5f  cmp     [rbp+bSaclPresent], r15d
0x180058a63  jnz     short loc_180058A69
0x180058a65  mov     [rbp+pSacl], r15
0x180058a69  mov     rax, [rbp+pOwner]
0x180058a6d  mov     rcx, [rbp+arg_20]
0x180058a71  mov     ebx, [rbp+arg_8]
0x180058a74  mov     [r14], rax
0x180058a77  mov     rax, [rbp+pGroup]
0x180058a7b  mov     [rsi], rax
0x180058a7e  mov     rax, [rbp+pDacl]
0x180058a82  mov     [rcx], rax
0x180058a85  mov     rcx, [rbp+arg_28]
0x180058a89  mov     rax, [rbp+pSacl]
0x180058a8d  mov     [rcx], rax
0x180058a90  lea     rcx, [rbp+var_20]; this
0x180058a94  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x180058a99  mov     eax, ebx
0x180058a9b  add     rsp, 78h
0x180058a9f  pop     r15
0x180058aa1  pop     r14
0x180058aa3  pop     rdi
0x180058aa4  pop     rsi
0x180058aa5  pop     rbx
0x180058aa6  pop     rbp
0x180058aa7  retn
```
