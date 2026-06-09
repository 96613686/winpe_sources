# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x1801aa3e0`
- end: `0x1801aa5ae`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `462`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e7c80`

## callees

- `0x180022710`
- `0x18005bf7c`
- `0x18005bfc8`
- `0x1800f6274`
- `0x1800f63e4`
- `0x1801244c0`
- `0x1801a97f0`
- `0x1801a9be8`
- `0x1801aa3e0`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa48b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa568`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa57b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa48b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa568`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801aa57b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801aa45e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801aa505`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801aa45e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801aa505`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801aa476`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801aa476`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1801aa554`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1801aa554`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801aa449`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1801aa449`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801aa4ec`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801aa4ec`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(void **this, const struct ATL::CDacl *a2)
{
  void *v4; // rcx
  BOOL v5; // ebp
  void *v6; // rax
  int Error; // ebx
  struct _ACL *PACL; // rax
  unsigned int v9; // eax
  unsigned int v10; // r14d
  struct _ACL *v11; // rsi
  const struct _ACL *v12; // rax
  errno_t v13; // eax
  int v14; // ebx
  WINBOOL bDaclDefaulted; // [rsp+20h] [rbp-48h] BYREF
  WINBOOL bDaclPresent; // [rsp+24h] [rbp-44h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-40h] BYREF
  __int64 pAclInformation; // [rsp+30h] [rbp-38h] BYREF
  int v19; // [rsp+38h] [rbp-30h]

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
  v5 = 1;
  pDacl = 0;
  if ( v4 )
  {
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    v6 = malloc(0x28u);
    this[1] = v6;
    if ( !v6 )
      goto LABEL_25;
    if ( !InitializeSecurityDescriptor(v6, 1u) )
    {
      Error = ResultFromLastError();
      free(this[1]);
      this[1] = 0;
      ATL::AtlThrowImpl(Error);
    }
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v11 = 0;
    goto LABEL_19;
  }
  PACL = (struct _ACL *)ATL::CAcl::GetPACL(a2);
  pAclInformation = 0;
  v19 = 0;
  if ( *((_BYTE *)a2 + 16) )
  {
    v9 = 0;
  }
  else
  {
    if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
      ATL::AtlThrowLastWin32();
    v9 = HIDWORD(pAclInformation);
  }
  v10 = v9;
  v11 = (struct _ACL *)malloc(v9);
  if ( !v11 )
LABEL_25:
    ATL::AtlThrowImpl(-2147024882);
  v12 = ATL::CAcl::GetPACL(a2);
  v13 = memcpy_s(v11, v10, v12, v10);
  ATL::AtlCrtErrorCheck(v13);
LABEL_19:
  if ( !*((_BYTE *)a2 + 16) && !v11 )
    v5 = 0;
  if ( !SetSecurityDescriptorDacl(this[1], v5, v11, 0) )
  {
    v14 = ResultFromLastError();
    free(v11);
    ATL::AtlThrowImpl(v14);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x1801aa3e0  mov     [rsp+arg_10], rbx
0x1801aa3e5  mov     [rsp+arg_18], rbp
0x1801aa3ea  push    rsi
0x1801aa3eb  push    rdi
0x1801aa3ec  push    r14
0x1801aa3ee  sub     rsp, 50h
0x1801aa3f2  mov     rax, cs:__security_cookie
0x1801aa3f9  xor     rax, rsp
0x1801aa3fc  mov     [rsp+68h+var_28], rax
0x1801aa401  cmp     qword ptr [rcx+8], 0
0x1801aa406  mov     rbx, rdx
0x1801aa409  mov     rdi, rcx
0x1801aa40c  jz      short loc_1801AA413
0x1801aa40e  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x1801aa413  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1801aa417  mov     ebp, 1
0x1801aa41c  mov     [rsp+68h+pDacl], 0
0x1801aa425  test    rcx, rcx
0x1801aa428  jz      short loc_1801AA459
0x1801aa42a  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1801aa42f  mov     [rsp+68h+bDaclDefaulted], 0
0x1801aa437  lea     r8, [rsp+68h+pDacl]; pDacl
0x1801aa43c  mov     [rsp+68h+bDaclPresent], 0
0x1801aa444  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x1801aa449  call    cs:__imp_GetSecurityDescriptorDacl
0x1801aa44f  test    eax, eax
0x1801aa451  jnz     short loc_1801AA4A1
0x1801aa453  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1801aa459  mov     ecx, 28h ; '('; Size
0x1801aa45e  call    cs:__imp_malloc
0x1801aa464  mov     [rdi+8], rax
0x1801aa468  test    rax, rax
0x1801aa46b  jz      loc_1801AA5A3
0x1801aa471  mov     edx, ebp; dwRevision
0x1801aa473  mov     rcx, rax; pSecurityDescriptor
0x1801aa476  call    cs:__imp_InitializeSecurityDescriptor
0x1801aa47c  test    eax, eax
0x1801aa47e  jnz     short loc_1801AA4A1
0x1801aa480  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801aa485  mov     rcx, [rdi+8]; Block
0x1801aa489  mov     ebx, eax
0x1801aa48b  call    cs:__imp_free
0x1801aa491  mov     ecx, ebx; int
0x1801aa493  mov     qword ptr [rdi+8], 0
0x1801aa49b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1801aa4a1  cmp     byte ptr [rbx+10h], 0
0x1801aa4a5  jnz     loc_1801AA539
0x1801aa4ab  mov     rax, [rbx]
0x1801aa4ae  mov     rcx, rbx
0x1801aa4b1  mov     rax, [rax+8]
0x1801aa4b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aa4ba  test    eax, eax
0x1801aa4bc  jz      short loc_1801AA539
0x1801aa4be  mov     rcx, rbx; this
0x1801aa4c1  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1801aa4c6  xor     ecx, ecx
0x1801aa4c8  mov     [rsp+68h+pAclInformation], rcx
0x1801aa4cd  mov     [rsp+68h+var_30], ecx
0x1801aa4d1  cmp     [rbx+10h], cl
0x1801aa4d4  jz      short loc_1801AA4DA
0x1801aa4d6  xor     eax, eax
0x1801aa4d8  jmp     short loc_1801AA500
0x1801aa4da  mov     r9d, 2; dwAclInformationClass
0x1801aa4e0  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x1801aa4e5  mov     rcx, rax; pAcl
0x1801aa4e8  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1801aa4ec  call    cs:__imp_GetAclInformation
0x1801aa4f2  test    eax, eax
0x1801aa4f4  jnz     short loc_1801AA4FC
0x1801aa4f6  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1801aa4fc  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x1801aa500  mov     ecx, eax; Size
0x1801aa502  mov     r14d, eax
0x1801aa505  call    cs:__imp_malloc
0x1801aa50b  mov     rsi, rax
0x1801aa50e  test    rax, rax
0x1801aa511  jz      loc_1801AA5A3
0x1801aa517  mov     rcx, rbx; this
0x1801aa51a  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1801aa51f  mov     r9d, r14d; SourceSize
0x1801aa522  mov     r8, rax; Source
0x1801aa525  mov     edx, r14d; DestinationSize
0x1801aa528  mov     rcx, rsi; Destination
0x1801aa52b  call    memcpy_s
0x1801aa530  mov     ecx, eax; int
0x1801aa532  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1801aa537  jmp     short loc_1801AA53B
0x1801aa539  xor     esi, esi
0x1801aa53b  cmp     byte ptr [rbx+10h], 0
0x1801aa53f  jnz     short loc_1801AA548
0x1801aa541  test    rsi, rsi
0x1801aa544  jnz     short loc_1801AA548
0x1801aa546  xor     ebp, ebp
0x1801aa548  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1801aa54c  xor     r9d, r9d; bDaclDefaulted
0x1801aa54f  mov     r8, rsi; pDacl
0x1801aa552  mov     edx, ebp; bDaclPresent
0x1801aa554  call    cs:__imp_SetSecurityDescriptorDacl
0x1801aa55a  test    eax, eax
0x1801aa55c  jnz     short loc_1801AA576
0x1801aa55e  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1801aa563  mov     rcx, rsi; Block
0x1801aa566  mov     ebx, eax
0x1801aa568  call    cs:__imp_free
0x1801aa56e  mov     ecx, ebx; int
0x1801aa570  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1801aa576  mov     rcx, [rsp+68h+pDacl]; Block
0x1801aa57b  call    cs:__imp_free
0x1801aa581  mov     rcx, [rsp+68h+var_28]
0x1801aa586  xor     rcx, rsp; StackCookie
0x1801aa589  call    __security_check_cookie
0x1801aa58e  lea     r11, [rsp+68h+var_18]
0x1801aa593  mov     rbx, [r11+30h]
0x1801aa597  mov     rbp, [r11+38h]
0x1801aa59b  mov     rsp, r11
0x1801aa59e  pop     r14
0x1801aa5a0  pop     rdi
0x1801aa5a1  pop     rsi
0x1801aa5a2  retn
0x1801aa5a3  mov     ecx, 8007000Eh; int
0x1801aa5a8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
