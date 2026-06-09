# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x18002f7d0`
- end: `0x18002f9c8`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `504`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dfd0`

## callees

- `0x180002604`
- `0x18002f3d4`
- `0x18002f63c`
- `0x18002f7d0`
- `0x180031264`
- `0x18003151c`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x18002f8ec`
- `VCRUNTIME140!memcpy` at `0x18002f8ec`
- `VCRUNTIME140!memset` at `0x18002f9a5`
- `VCRUNTIME140!memset` at `0x18002f9a5`
- `ADVAPI32!GetAclInformation` at `0x18002f8a7`
- `ADVAPI32!GetAclInformation` at `0x18002f8a7`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002f82a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002f82a`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002f911`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18002f911`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002f858`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002f858`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f9ab`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18002f9ab`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f9b7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18002f9b7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f920`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f952`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f97c`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f920`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f952`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002f97c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f83f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f8bb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f83f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002f8bb`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(void **this, const struct ATL::CDacl *a2)
{
  void *v4; // rcx
  BOOL v5; // r14d
  void *v6; // rax
  ACL *PACL; // rax
  __int64 v8; // rbp
  ACL *v9; // rdi
  const struct _ACL *v10; // rax
  int v11; // ebx
  int Error; // ebx
  PACL pDacl; // [rsp+20h] [rbp-48h] BYREF
  BOOL bDaclDefaulted; // [rsp+28h] [rbp-40h] BYREF
  BOOL bDaclPresent; // [rsp+2Ch] [rbp-3Ch] BYREF
  _BYTE pAclInformation[4]; // [rsp+30h] [rbp-38h] BYREF
  size_t Size; // [rsp+34h] [rbp-34h]

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
  v5 = 1;
  pDacl = 0;
  if ( v4 )
  {
    if ( !GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v6 = malloc(0x28u);
    this[1] = v6;
    if ( !v6 )
      goto LABEL_24;
    if ( !InitializeSecurityDescriptor(v6, 1u) )
    {
      Error = ATL::AtlHresultFromLastError();
      free(this[1]);
      this[1] = 0;
      ATL::AtlThrowImpl(Error);
    }
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v9 = 0;
    goto LABEL_17;
  }
  PACL = (ACL *)ATL::CAcl::GetPACL(a2);
  if ( !PACL )
    ATL::AtlThrowImpl(-2147467259);
  if ( !GetAclInformation(PACL, pAclInformation, 0xCu, AclSizeInformation) )
    ATL::AtlThrowLastWin32();
  v8 = (unsigned int)Size;
  v9 = (ACL *)malloc((unsigned int)Size);
  if ( !v9 )
LABEL_24:
    ATL::AtlThrowImpl(-2147024882);
  v10 = ATL::CAcl::GetPACL(a2);
  if ( v8 )
  {
    if ( !v10 )
    {
      memset(v9, 0, (unsigned int)v8);
      *_errno() = 22;
      _invalid_parameter_noinfo();
      ATL::AtlThrowImpl(-2147024809);
    }
    memcpy(v9, v10, (unsigned int)v8);
  }
LABEL_17:
  if ( !*((_BYTE *)a2 + 16) && !v9 )
    v5 = 0;
  if ( !SetSecurityDescriptorDacl(this[1], v5, v9, 0) )
  {
    v11 = ATL::AtlHresultFromLastError();
    free(v9);
    ATL::AtlThrowImpl(v11);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x18002f7d0  mov     [rsp+arg_10], rbx
0x18002f7d5  mov     [rsp+arg_18], rbp
0x18002f7da  push    rsi
0x18002f7db  push    rdi
0x18002f7dc  push    r14
0x18002f7de  sub     rsp, 50h
0x18002f7e2  mov     rax, cs:__security_cookie
0x18002f7e9  xor     rax, rsp
0x18002f7ec  mov     [rsp+68h+var_28], rax
0x18002f7f1  cmp     qword ptr [rcx+8], 0
0x18002f7f6  mov     rbx, rdx
0x18002f7f9  mov     rsi, rcx
0x18002f7fc  jz      short loc_18002F803
0x18002f7fe  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x18002f803  mov     rcx, [rsi+8]; pSecurityDescriptor
0x18002f807  mov     r14d, 1
0x18002f80d  mov     [rsp+68h+pDacl], 0
0x18002f816  test    rcx, rcx
0x18002f819  jz      short loc_18002F83A
0x18002f81b  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x18002f820  lea     r8, [rsp+68h+pDacl]; pDacl
0x18002f825  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x18002f82a  call    cs:__imp_GetSecurityDescriptorDacl
0x18002f830  test    eax, eax
0x18002f832  jz      loc_18002F960
0x18002f838  jmp     short loc_18002F866
0x18002f83a  mov     ecx, 28h ; '('; Size
0x18002f83f  call    cs:__imp_malloc
0x18002f845  mov     [rsi+8], rax
0x18002f849  test    rax, rax
0x18002f84c  jz      loc_18002F966
0x18002f852  mov     edx, r14d; dwRevision
0x18002f855  mov     rcx, rax; pSecurityDescriptor
0x18002f858  call    cs:__imp_InitializeSecurityDescriptor
0x18002f85e  test    eax, eax
0x18002f860  jz      loc_18002F971
0x18002f866  cmp     byte ptr [rbx+10h], 0
0x18002f86a  jnz     loc_18002F8F4
0x18002f870  mov     rax, [rbx]
0x18002f873  mov     rcx, rbx
0x18002f876  mov     rax, [rax+8]
0x18002f87a  call    cs:__guard_dispatch_icall_fptr
0x18002f880  test    eax, eax
0x18002f882  jz      short loc_18002F8F4
0x18002f884  mov     rcx, rbx; this
0x18002f887  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18002f88c  test    rax, rax
0x18002f88f  jz      loc_18002F992
0x18002f895  mov     r9d, 2; dwAclInformationClass
0x18002f89b  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x18002f8a0  mov     rcx, rax; pAcl
0x18002f8a3  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18002f8a7  call    cs:__imp_GetAclInformation
0x18002f8ad  test    eax, eax
0x18002f8af  jz      loc_18002F99D
0x18002f8b5  mov     ebp, dword ptr [rsp+68h+Size]
0x18002f8b9  mov     ecx, ebp; Size
0x18002f8bb  call    cs:__imp_malloc
0x18002f8c1  mov     rdi, rax
0x18002f8c4  test    rax, rax
0x18002f8c7  jz      loc_18002F966
0x18002f8cd  mov     rcx, rbx; this
0x18002f8d0  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18002f8d5  test    rbp, rbp
0x18002f8d8  jz      short loc_18002F8F6
0x18002f8da  mov     r8d, ebp; Size
0x18002f8dd  mov     rcx, rdi; void *
0x18002f8e0  test    rax, rax
0x18002f8e3  jz      loc_18002F9A3
0x18002f8e9  mov     rdx, rax; Src
0x18002f8ec  call    cs:__imp_memcpy
0x18002f8f2  jmp     short loc_18002F8F6
0x18002f8f4  xor     edi, edi
0x18002f8f6  cmp     byte ptr [rbx+10h], 0
0x18002f8fa  jnz     short loc_18002F904
0x18002f8fc  test    rdi, rdi
0x18002f8ff  jnz     short loc_18002F904
0x18002f901  xor     r14d, r14d
0x18002f904  mov     rcx, [rsi+8]; pSecurityDescriptor
0x18002f908  xor     r9d, r9d; bDaclDefaulted
0x18002f90b  mov     r8, rdi; pDacl
0x18002f90e  mov     edx, r14d; bDaclPresent
0x18002f911  call    cs:__imp_SetSecurityDescriptorDacl
0x18002f917  test    eax, eax
0x18002f919  jz      short loc_18002F948
0x18002f91b  mov     rcx, [rsp+68h+pDacl]; Block
0x18002f920  call    cs:__imp_free
0x18002f926  mov     rcx, [rsp+68h+var_28]
0x18002f92b  xor     rcx, rsp; StackCookie
0x18002f92e  call    __security_check_cookie
0x18002f933  lea     r11, [rsp+68h+var_18]
0x18002f938  mov     rbx, [r11+30h]
0x18002f93c  mov     rbp, [r11+38h]
0x18002f940  mov     rsp, r11
0x18002f943  pop     r14
0x18002f945  pop     rdi
0x18002f946  pop     rsi
0x18002f947  retn
0x18002f948  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f94d  mov     rcx, rdi; Block
0x18002f950  mov     ebx, eax
0x18002f952  call    cs:__imp_free
0x18002f958  mov     ecx, ebx; int
0x18002f95a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f960  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002f966  mov     ecx, 8007000Eh; int
0x18002f96b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f971  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002f976  mov     rcx, [rsi+8]; Block
0x18002f97a  mov     ebx, eax
0x18002f97c  call    cs:__imp_free
0x18002f982  mov     ecx, ebx; int
0x18002f984  mov     qword ptr [rsi+8], 0
0x18002f98c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f992  mov     ecx, 80004005h; int
0x18002f997  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f99d  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002f9a3  xor     edx, edx; Val
0x18002f9a5  call    cs:__imp_memset
0x18002f9ab  call    cs:__imp__errno
0x18002f9b1  mov     dword ptr [rax], 16h
0x18002f9b7  call    cs:__imp__invalid_parameter_noinfo
0x18002f9bd  mov     ecx, 80070057h; int
0x18002f9c2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
