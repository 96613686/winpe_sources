# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x180045490`
- end: `0x180045613`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `387`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800435fc`

## callees

- `0x180006cc8`
- `0x180006d14`
- `0x180007598`
- `0x180010290`
- `0x180042458`
- `0x180042e70`
- `0x180043bec`
- `0x180045490`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `msvcrt!malloc` at `0x18004556d`
- `msvcrt!malloc` at `0x18004556d`
- `msvcrt!free` at `0x1800455dd`
- `msvcrt!free` at `0x1800455f0`
- `msvcrt!free` at `0x1800455dd`
- `msvcrt!free` at `0x1800455f0`
- `msvcrt!memcpy_s` at `0x18004559a`
- `msvcrt!memcpy_s` at `0x18004559a`
- `ADVAPI32!GetAclInformation` at `0x180045555`
- `ADVAPI32!GetAclInformation` at `0x180045555`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800454ee`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1800454ee`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800455c9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800455c9`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(PSECURITY_DESCRIPTOR *this, const struct ATL::CDacl *a2)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  struct _ACL *PACL; // rax
  unsigned int v6; // eax
  rsize_t v7; // rbp
  struct _ACL *v8; // rdi
  const struct _ACL *v9; // rax
  errno_t v10; // eax
  BOOL v11; // edx
  int Error; // ebx
  WINBOOL bDaclDefaulted; // [rsp+20h] [rbp-48h] BYREF
  WINBOOL bDaclPresent; // [rsp+24h] [rbp-44h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-40h] BYREF
  __int64 pAclInformation; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+38h] [rbp-30h]

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
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
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v8 = 0;
  }
  else
  {
    PACL = (struct _ACL *)ATL::CAcl::GetPACL(a2);
    pAclInformation = 0;
    v17 = 0;
    if ( *((_BYTE *)a2 + 16) )
    {
      v6 = 0;
    }
    else
    {
      if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
        ATL::AtlThrowLastWin32();
      v6 = HIDWORD(pAclInformation);
    }
    v7 = v6;
    v8 = (struct _ACL *)malloc(v6);
    if ( !v8 )
      ATL::AtlThrowImpl(-2147024882);
    v9 = ATL::CAcl::GetPACL(a2);
    v10 = memcpy_s(v8, v7, v9, v7);
    ATL::AtlCrtErrorCheck(v10);
  }
  v11 = *((_BYTE *)a2 + 16) || v8;
  if ( !SetSecurityDescriptorDacl(this[1], v11, v8, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v8);
    ATL::AtlThrowImpl(Error);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x180045490  mov     [rsp+arg_10], rbx
0x180045495  push    rbp
0x180045496  push    rsi
0x180045497  push    rdi
0x180045498  sub     rsp, 50h
0x18004549c  mov     rax, cs:__security_cookie
0x1800454a3  xor     rax, rsp
0x1800454a6  mov     [rsp+68h+var_28], rax
0x1800454ab  cmp     qword ptr [rcx+8], 0
0x1800454b0  mov     rbx, rdx
0x1800454b3  mov     rsi, rcx
0x1800454b6  jz      short loc_1800454BD
0x1800454b8  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x1800454bd  mov     rcx, [rsi+8]; pSecurityDescriptor
0x1800454c1  mov     [rsp+68h+pDacl], 0
0x1800454ca  test    rcx, rcx
0x1800454cd  jz      short loc_1800454FE
0x1800454cf  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1800454d4  mov     [rsp+68h+bDaclDefaulted], 0
0x1800454dc  lea     r8, [rsp+68h+pDacl]; pDacl
0x1800454e1  mov     [rsp+68h+bDaclPresent], 0
0x1800454e9  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x1800454ee  call    cs:__imp_GetSecurityDescriptorDacl
0x1800454f4  test    eax, eax
0x1800454f6  jnz     short loc_180045506
0x1800454f8  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1800454fe  mov     rcx, rsi; this
0x180045501  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x180045506  cmp     byte ptr [rbx+10h], 0
0x18004550a  jnz     loc_1800455A9
0x180045510  mov     rax, [rbx]
0x180045513  mov     rcx, rbx
0x180045516  mov     rax, [rax+8]
0x18004551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004551f  test    eax, eax
0x180045521  jz      loc_1800455A9
0x180045527  mov     rcx, rbx; this
0x18004552a  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18004552f  xor     ecx, ecx
0x180045531  mov     [rsp+68h+pAclInformation], rcx
0x180045536  mov     [rsp+68h+var_30], ecx
0x18004553a  cmp     [rbx+10h], cl
0x18004553d  jz      short loc_180045543
0x18004553f  xor     eax, eax
0x180045541  jmp     short loc_180045569
0x180045543  mov     r9d, 2; dwAclInformationClass
0x180045549  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x18004554e  mov     rcx, rax; pAcl
0x180045551  lea     r8d, [r9+0Ah]; nAclInformationLength
0x180045555  call    cs:__imp_GetAclInformation
0x18004555b  test    eax, eax
0x18004555d  jnz     short loc_180045565
0x18004555f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180045565  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x180045569  mov     ecx, eax; Size
0x18004556b  mov     ebp, eax
0x18004556d  call    cs:__imp_malloc
0x180045573  mov     rdi, rax
0x180045576  test    rax, rax
0x180045579  jnz     short loc_180045586
0x18004557b  mov     ecx, 8007000Eh; int
0x180045580  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180045586  mov     rcx, rbx; this
0x180045589  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18004558e  mov     r9, rbp; SourceSize
0x180045591  mov     r8, rax; Source
0x180045594  mov     rdx, rbp; DestinationSize
0x180045597  mov     rcx, rdi; Destination
0x18004559a  call    cs:__imp_memcpy_s
0x1800455a0  mov     ecx, eax; int
0x1800455a2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800455a7  jmp     short loc_1800455AB
0x1800455a9  xor     edi, edi
0x1800455ab  cmp     byte ptr [rbx+10h], 0
0x1800455af  jnz     short loc_1800455BA
0x1800455b1  test    rdi, rdi
0x1800455b4  jnz     short loc_1800455BA
0x1800455b6  xor     edx, edx
0x1800455b8  jmp     short loc_1800455BF
0x1800455ba  mov     edx, 1; bDaclPresent
0x1800455bf  mov     rcx, [rsi+8]; pSecurityDescriptor
0x1800455c3  xor     r9d, r9d; bDaclDefaulted
0x1800455c6  mov     r8, rdi; pDacl
0x1800455c9  call    cs:__imp_SetSecurityDescriptorDacl
0x1800455cf  test    eax, eax
0x1800455d1  jnz     short loc_1800455EB
0x1800455d3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800455d8  mov     rcx, rdi; Block
0x1800455db  mov     ebx, eax
0x1800455dd  call    cs:__imp_free
0x1800455e3  mov     ecx, ebx; int
0x1800455e5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800455eb  mov     rcx, [rsp+68h+pDacl]; Block
0x1800455f0  call    cs:__imp_free
0x1800455f6  mov     rcx, [rsp+68h+var_28]
0x1800455fb  xor     rcx, rsp; StackCookie
0x1800455fe  call    __security_check_cookie
0x180045603  mov     rbx, [rsp+68h+arg_10]
0x18004560b  add     rsp, 50h
0x18004560f  pop     rdi
0x180045610  pop     rsi
0x180045611  pop     rbp
0x180045612  retn
```
