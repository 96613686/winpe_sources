# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x1400121e0`
- end: `0x1400123d6`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `502`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011b04`

## callees

- `0x140002e74`
- `0x14000914c`
- `0x14000916c`
- `0x140011de4`
- `0x14001204c`
- `0x1400121e0`
- `0x1400137e0`
- `0x14001473e`
- `0x140014bc0`
- `0x140014c70`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x140012268`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x140012268`
- `ADVAPI32!GetAclInformation` at `0x1400122b7`
- `ADVAPI32!GetAclInformation` at `0x1400122b7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140012320`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x140012320`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14001223a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14001223a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400123b9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1400123b9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400123c5`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1400123c5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x14001224f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400122cb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x14001224f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1400122cb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001232f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012361`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001238b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001232f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012361`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14001238b`

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
      memset_0(v9, 0, (unsigned int)v8);
      *_errno() = 22;
      _invalid_parameter_noinfo();
      ATL::AtlThrowImpl(-2147024809);
    }
    memcpy_0(v9, v10, (unsigned int)v8);
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
0x1400121e0  mov     [rsp+arg_10], rbx
0x1400121e5  mov     [rsp+arg_18], rbp
0x1400121ea  push    rsi
0x1400121eb  push    rdi
0x1400121ec  push    r14
0x1400121ee  sub     rsp, 50h
0x1400121f2  mov     rax, cs:__security_cookie
0x1400121f9  xor     rax, rsp
0x1400121fc  mov     [rsp+68h+var_28], rax
0x140012201  cmp     qword ptr [rcx+8], 0
0x140012206  mov     rbx, rdx
0x140012209  mov     rsi, rcx
0x14001220c  jz      short loc_140012213
0x14001220e  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140012213  mov     rcx, [rsi+8]; pSecurityDescriptor
0x140012217  mov     r14d, 1
0x14001221d  mov     [rsp+68h+pDacl], 0
0x140012226  test    rcx, rcx
0x140012229  jz      short loc_14001224A
0x14001222b  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x140012230  lea     r8, [rsp+68h+pDacl]; pDacl
0x140012235  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x14001223a  call    cs:__imp_GetSecurityDescriptorDacl
0x140012240  test    eax, eax
0x140012242  jz      loc_14001236F
0x140012248  jmp     short loc_140012276
0x14001224a  mov     ecx, 28h ; '('; Size
0x14001224f  call    cs:__imp_malloc
0x140012255  mov     [rsi+8], rax
0x140012259  test    rax, rax
0x14001225c  jz      loc_140012375
0x140012262  mov     edx, r14d; dwRevision
0x140012265  mov     rcx, rax; pSecurityDescriptor
0x140012268  call    cs:__imp_InitializeSecurityDescriptor
0x14001226e  test    eax, eax
0x140012270  jz      loc_140012380
0x140012276  cmp     byte ptr [rbx+10h], 0
0x14001227a  jnz     loc_140012303
0x140012280  mov     rax, [rbx]
0x140012283  mov     rcx, rbx
0x140012286  mov     rax, [rax+8]
0x14001228a  call    cs:__guard_dispatch_icall_fptr
0x140012290  test    eax, eax
0x140012292  jz      short loc_140012303
0x140012294  mov     rcx, rbx; this
0x140012297  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x14001229c  test    rax, rax
0x14001229f  jz      loc_1400123A1
0x1400122a5  mov     r9d, 2; dwAclInformationClass
0x1400122ab  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x1400122b0  mov     rcx, rax; pAcl
0x1400122b3  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1400122b7  call    cs:__imp_GetAclInformation
0x1400122bd  test    eax, eax
0x1400122bf  jz      loc_1400123AC
0x1400122c5  mov     ebp, dword ptr [rsp+68h+Size]
0x1400122c9  mov     ecx, ebp; Size
0x1400122cb  call    cs:__imp_malloc
0x1400122d1  mov     rdi, rax
0x1400122d4  test    rax, rax
0x1400122d7  jz      loc_140012375
0x1400122dd  mov     rcx, rbx; this
0x1400122e0  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x1400122e5  test    rbp, rbp
0x1400122e8  jz      short loc_140012305
0x1400122ea  mov     r8d, ebp; Size
0x1400122ed  mov     rcx, rdi; void *
0x1400122f0  test    rax, rax
0x1400122f3  jz      loc_1400123B2
0x1400122f9  mov     rdx, rax; Src
0x1400122fc  call    memcpy_0
0x140012301  jmp     short loc_140012305
0x140012303  xor     edi, edi
0x140012305  cmp     byte ptr [rbx+10h], 0
0x140012309  jnz     short loc_140012313
0x14001230b  test    rdi, rdi
0x14001230e  jnz     short loc_140012313
0x140012310  xor     r14d, r14d
0x140012313  mov     rcx, [rsi+8]; pSecurityDescriptor
0x140012317  xor     r9d, r9d; bDaclDefaulted
0x14001231a  mov     r8, rdi; pDacl
0x14001231d  mov     edx, r14d; bDaclPresent
0x140012320  call    cs:__imp_SetSecurityDescriptorDacl
0x140012326  test    eax, eax
0x140012328  jz      short loc_140012357
0x14001232a  mov     rcx, [rsp+68h+pDacl]; Block
0x14001232f  call    cs:__imp_free
0x140012335  mov     rcx, [rsp+68h+var_28]
0x14001233a  xor     rcx, rsp; StackCookie
0x14001233d  call    __security_check_cookie
0x140012342  lea     r11, [rsp+68h+var_18]
0x140012347  mov     rbx, [r11+30h]
0x14001234b  mov     rbp, [r11+38h]
0x14001234f  mov     rsp, r11
0x140012352  pop     r14
0x140012354  pop     rdi
0x140012355  pop     rsi
0x140012356  retn
0x140012357  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14001235c  mov     rcx, rdi; Block
0x14001235f  mov     ebx, eax
0x140012361  call    cs:__imp_free
0x140012367  mov     ecx, ebx; int
0x140012369  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001236f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140012375  mov     ecx, 8007000Eh; int
0x14001237a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012380  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140012385  mov     rcx, [rsi+8]; Block
0x140012389  mov     ebx, eax
0x14001238b  call    cs:__imp_free
0x140012391  mov     ecx, ebx; int
0x140012393  mov     qword ptr [rsi+8], 0
0x14001239b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400123a1  mov     ecx, 80004005h; int
0x1400123a6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400123ac  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1400123b2  xor     edx, edx; Val
0x1400123b4  call    memset_0
0x1400123b9  call    cs:__imp__errno
0x1400123bf  mov     dword ptr [rax], 16h
0x1400123c5  call    cs:__imp__invalid_parameter_noinfo
0x1400123cb  mov     ecx, 80070057h; int
0x1400123d0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
