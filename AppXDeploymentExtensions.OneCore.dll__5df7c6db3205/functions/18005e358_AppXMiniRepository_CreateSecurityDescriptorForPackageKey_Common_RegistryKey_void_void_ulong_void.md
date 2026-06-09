# AppXMiniRepository::CreateSecurityDescriptorForPackageKey(Common::RegistryKey &,void *,void *,ulong *,void * *)

- ea: `0x18005e358`
- end: `0x18005e5e5`
- name: `?CreateSecurityDescriptorForPackageKey@AppXMiniRepository@@CAJAEAVRegistryKey@Common@@PEAX1PEAKPEAPEAX@Z`
- size: `653`
- prototype: `static int(struct Common::RegistryKey *, void *, void *, unsigned int *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005dfb8`
- `0x18005e090`

## callees

- `0x18005e358`
- `0x1800ce12c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f073c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005e3c7`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005e42d`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005e3c7`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18005e42d`
- `ntdll!RtlLengthSid` at `0x18005e476`
- `ntdll!RtlLengthSid` at `0x18005e476`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e5dd`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18005e5dd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18005e4be`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18005e4be`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e4d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18005e4d8`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e465`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18005e465`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005e49a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18005e49a`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x18005e512`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x18005e512`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18005e528`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x18005e528`

## pseudocode

```c
LSTATUS __fastcall AppXMiniRepository::CreateSecurityDescriptorForPackageKey(
        HKEY *a1,
        void *a2,
        void *a3,
        unsigned int *a4,
        void **a5)
{
  HKEY v8; // rcx
  LSTATUS result; // eax
  void *v10; // rax
  void *v11; // rsi
  LSTATUS KeySecurity; // eax
  unsigned int HResultFromLastError; // r14d
  void *v14; // rax
  void *v15; // rbx
  Common *v16; // rcx
  struct _ACL *v17; // rdi
  Common *v18; // rcx
  DWORD cbSecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+48h] [rbp-28h] BYREF
  void **v21; // [rsp+50h] [rbp-20h]
  struct _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp-18h] BYREF

  v21 = a5;
  cbSecurityDescriptor = 0;
  NewDescriptor = 0;
  GenericMapping.GenericRead = 131097;
  GenericMapping.GenericWrite = 131078;
  v8 = *a1;
  GenericMapping.GenericExecute = 131097;
  GenericMapping.GenericAll = 983103;
  result = RegGetKeySecurity(v8, 7u, 0, &cbSecurityDescriptor);
  if ( result == 122 )
  {
    v10 = operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( !v10 )
    {
      operator delete(0, 0x28u);
      return -2147024882;
    }
    KeySecurity = RegGetKeySecurity(*a1, 7u, v10, &cbSecurityDescriptor);
    HResultFromLastError = KeySecurity;
    if ( KeySecurity )
    {
      if ( KeySecurity > 0 )
        HResultFromLastError = (unsigned __int16)KeySecurity | 0x80070000;
      goto LABEL_15;
    }
    v14 = operator new[](0x28u, (const struct std::nothrow_t *)std::nothrow);
    v15 = v14;
    if ( !v14 )
    {
      operator delete(0, 0x28u);
      HResultFromLastError = -2147024882;
      goto LABEL_15;
    }
    if ( InitializeSecurityDescriptor(v14, 1u) )
    {
      cbSecurityDescriptor = (RtlLengthSid(a2) + 23) & 0xFFFFFFFC;
      v17 = (struct _ACL *)operator new[](cbSecurityDescriptor, (const struct std::nothrow_t *)std::nothrow);
      if ( InitializeAcl(v17, cbSecurityDescriptor, 2u)
        && AddAccessAllowedAceEx(v17, 2u, 3u, 0x20019u, a2)
        && SetSecurityDescriptorDacl(v15, 1, v17, 0)
        && CreatePrivateObjectSecurityEx(v11, v15, &NewDescriptor, 0, 1, 0x71u, 0, &GenericMapping) )
      {
        if ( SetSecurityDescriptorControl(NewDescriptor, 0x100u, 0x100u) )
        {
          *v21 = NewDescriptor;
          *a4 = 4;
          operator delete(v17, 8u);
          operator delete(v15, 0x28u);
          HResultFromLastError = 0;
LABEL_15:
          operator delete(v11, 0x28u);
          return HResultFromLastError;
        }
        DestroyPrivateObjectSecurity(&NewDescriptor);
      }
      HResultFromLastError = Common::GetHResultFromLastError(v18);
      operator delete(v17, 8u);
    }
    else
    {
      HResultFromLastError = Common::GetHResultFromLastError(v16);
    }
    operator delete(v15, 0x28u);
    goto LABEL_15;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18005e358  mov     [rsp-38h+arg_10], rbx
0x18005e35d  push    rbp
0x18005e35e  push    rsi
0x18005e35f  push    rdi
0x18005e360  push    r12
0x18005e362  push    r13
0x18005e364  push    r14
0x18005e366  push    r15
0x18005e368  mov     rbp, rsp
0x18005e36b  sub     rsp, 70h
0x18005e36f  mov     rax, cs:__security_cookie
0x18005e376  xor     rax, rsp
0x18005e379  mov     [rbp+var_8], rax
0x18005e37d  mov     rax, [rbp+arg_20]
0x18005e381  xor     r8d, r8d; pSecurityDescriptor
0x18005e384  mov     [rbp+var_20], rax
0x18005e388  mov     r13, r9
0x18005e38b  mov     eax, 20019h
0x18005e390  mov     [rbp+cbSecurityDescriptor], 0
0x18005e397  mov     r12, rdx
0x18005e39a  mov     [rbp+NewDescriptor], 0
0x18005e3a2  lea     r14d, [r8+7]
0x18005e3a6  mov     [rbp+var_18.GenericRead], eax
0x18005e3a9  mov     rbx, rcx
0x18005e3ac  mov     [rbp+var_18.GenericWrite], 20006h
0x18005e3b3  mov     rcx, [rcx]; hKey
0x18005e3b6  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18005e3ba  mov     edx, r14d; SecurityInformation
0x18005e3bd  mov     [rbp+var_18.GenericExecute], eax
0x18005e3c0  mov     [rbp+var_18.GenericAll], 0F003Fh
0x18005e3c7  call    cs:__imp_RegGetKeySecurity
0x18005e3cd  cmp     eax, 7Ah ; 'z'
0x18005e3d0  jz      short loc_18005E402
0x18005e3d2  test    eax, eax
0x18005e3d4  jle     short loc_18005E3DE
0x18005e3d6  movzx   eax, ax
0x18005e3d9  or      eax, 80070000h
0x18005e3de  mov     rcx, [rbp+var_8]
0x18005e3e2  xor     rcx, rsp; StackCookie
0x18005e3e5  call    __security_check_cookie
0x18005e3ea  mov     rbx, [rsp+70h+arg_10]
0x18005e3f2  add     rsp, 70h
0x18005e3f6  pop     r15
0x18005e3f8  pop     r14
0x18005e3fa  pop     r13
0x18005e3fc  pop     r12
0x18005e3fe  pop     rdi
0x18005e3ff  pop     rsi
0x18005e400  pop     rbp
0x18005e401  retn
0x18005e402  mov     ecx, [rbp+cbSecurityDescriptor]; unsigned __int64
0x18005e405  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18005e40c  mov     rdx, rdi; struct std::nothrow_t *
0x18005e40f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005e414  mov     rsi, rax
0x18005e417  test    rax, rax
0x18005e41a  jz      loc_18005E598
0x18005e420  mov     rcx, [rbx]; hKey
0x18005e423  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18005e427  mov     r8, rax; pSecurityDescriptor
0x18005e42a  mov     edx, r14d; SecurityInformation
0x18005e42d  call    cs:__imp_RegGetKeySecurity
0x18005e433  mov     r14d, eax
0x18005e436  mov     r15d, 28h ; '('
0x18005e43c  test    eax, eax
0x18005e43e  jnz     loc_18005E5AE
0x18005e444  mov     rdx, rdi; struct std::nothrow_t *
0x18005e447  mov     ecx, r15d; unsigned __int64
0x18005e44a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005e44f  mov     rbx, rax
0x18005e452  test    rax, rax
0x18005e455  jz      loc_18005E5BD
0x18005e45b  lea     r14d, [r15-27h]
0x18005e45f  mov     rcx, rax; pSecurityDescriptor
0x18005e462  mov     edx, r14d; dwRevision
0x18005e465  call    cs:__imp_InitializeSecurityDescriptor
0x18005e46b  test    eax, eax
0x18005e46d  jz      loc_18005E5CF
0x18005e473  mov     rcx, r12; Sid
0x18005e476  call    cs:__imp_RtlLengthSid
0x18005e47c  mov     rdx, rdi; struct std::nothrow_t *
0x18005e47f  lea     ecx, [rax+17h]
0x18005e482  and     ecx, 0FFFFFFFCh; unsigned __int64
0x18005e485  mov     [rbp+cbSecurityDescriptor], ecx
0x18005e488  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005e48d  mov     edx, [rbp+cbSecurityDescriptor]; nAclLength
0x18005e490  lea     r8d, [r15-26h]; dwAclRevision
0x18005e494  mov     rcx, rax; pAcl
0x18005e497  mov     rdi, rax
0x18005e49a  call    cs:__imp_InitializeAcl
0x18005e4a0  test    eax, eax
0x18005e4a2  jz      loc_18005E576
0x18005e4a8  lea     edx, [r15-26h]; dwAceRevision
0x18005e4ac  mov     [rsp+70h+pSid], r12; pSid
0x18005e4b1  mov     r9d, 20019h; AccessMask
0x18005e4b7  lea     r8d, [r15-25h]; AceFlags
0x18005e4bb  mov     rcx, rdi; pAcl
0x18005e4be  call    cs:__imp_AddAccessAllowedAceEx
0x18005e4c4  test    eax, eax
0x18005e4c6  jz      loc_18005E576
0x18005e4cc  xor     r9d, r9d; bDaclDefaulted
0x18005e4cf  mov     r8, rdi; pDacl
0x18005e4d2  mov     edx, r14d; bDaclPresent
0x18005e4d5  mov     rcx, rbx; pSecurityDescriptor
0x18005e4d8  call    cs:__imp_SetSecurityDescriptorDacl
0x18005e4de  test    eax, eax
0x18005e4e0  jz      loc_18005E576
0x18005e4e6  lea     rax, [rbp+var_18]
0x18005e4ea  xor     r9d, r9d; ObjectType
0x18005e4ed  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x18005e4f2  lea     r8, [rbp+NewDescriptor]; NewDescriptor
0x18005e4f6  mov     [rsp+70h+Token], 0; Token
0x18005e4ff  mov     rdx, rbx; CreatorDescriptor
0x18005e502  mov     [rsp+70h+AutoInheritFlags], 71h ; 'q'; AutoInheritFlags
0x18005e50a  mov     rcx, rsi; ParentDescriptor
0x18005e50d  mov     dword ptr [rsp+70h+pSid], r14d; IsContainerObject
0x18005e512  call    cs:__imp_CreatePrivateObjectSecurityEx
0x18005e518  test    eax, eax
0x18005e51a  jz      short loc_18005E576
0x18005e51c  mov     rcx, [rbp+NewDescriptor]; pSecurityDescriptor
0x18005e520  mov     edx, 100h; ControlBitsOfInterest
0x18005e525  mov     r8d, edx; ControlBitsToSet
0x18005e528  call    cs:__imp_SetSecurityDescriptorControl
0x18005e52e  test    eax, eax
0x18005e530  jz      loc_18005E5D9
0x18005e536  mov     rcx, [rbp+var_20]
0x18005e53a  lea     edx, [r15-20h]; unsigned __int64
0x18005e53e  mov     rax, [rbp+NewDescriptor]
0x18005e542  mov     [rcx], rax
0x18005e545  mov     rcx, rdi; void *
0x18005e548  mov     dword ptr [r13+0], 4
0x18005e550  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e555  mov     edx, r15d; unsigned __int64
0x18005e558  mov     rcx, rbx; void *
0x18005e55b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e560  xor     r14d, r14d
0x18005e563  mov     rdx, r15; unsigned __int64
0x18005e566  mov     rcx, rsi; void *
0x18005e569  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e56e  mov     eax, r14d
0x18005e571  jmp     loc_18005E3DE
0x18005e576  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x18005e57b  mov     edx, 8; unsigned __int64
0x18005e580  mov     rcx, rdi; void *
0x18005e583  mov     r14d, eax
0x18005e586  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e58b  mov     rdx, r15; unsigned __int64
0x18005e58e  mov     rcx, rbx; void *
0x18005e591  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e596  jmp     short loc_18005E563
0x18005e598  mov     edx, 28h ; '('; unsigned __int64
0x18005e59d  xor     ecx, ecx; void *
0x18005e59f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e5a4  mov     eax, 8007000Eh
0x18005e5a9  jmp     loc_18005E3DE
0x18005e5ae  jle     short loc_18005E563
0x18005e5b0  movzx   r14d, ax
0x18005e5b4  or      r14d, 80070000h
0x18005e5bb  jmp     short loc_18005E563
0x18005e5bd  mov     rdx, r15; unsigned __int64
0x18005e5c0  xor     ecx, ecx; void *
0x18005e5c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005e5c7  mov     r14d, 8007000Eh
0x18005e5cd  jmp     short loc_18005E563
0x18005e5cf  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x18005e5d4  mov     r14d, eax
0x18005e5d7  jmp     short loc_18005E58B
0x18005e5d9  lea     rcx, [rbp+NewDescriptor]; ObjectDescriptor
0x18005e5dd  call    cs:__imp_DestroyPrivateObjectSecurity
0x18005e5e3  jmp     short loc_18005E576
```
