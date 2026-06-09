# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x1800187c0`
- end: `0x180018932`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `370`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001733c`
- `0x18009b528`

## callees

- `0x1800187c0`
- `0x180018938`
- `0x180018ba8`
- `0x180018c18`
- `0x180018d78`
- `0x18001e46c`
- `0x18001e838`
- `0x18009e0f8`
- `0x18009e2e4`
- `0x1800a98c0`
- `0x1800aa46a`
- `0x1800aa594`
- `0x1800aa5ac`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800188d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018906`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800188d8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180018906`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018855`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180018855`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018886`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180018886`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800188c9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800188c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180018822`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180018822`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(PSECURITY_DESCRIPTOR *this, const struct ATL::CDacl *a2)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  size_t Length; // rbp
  struct _ACL *v6; // rdi
  const struct _ACL *PACL; // rax
  __int64 v8; // rcx
  int v9; // ebp
  BOOL v10; // edx
  int LastErrorAsHResult; // ebx
  PACL pDacl; // [rsp+20h] [rbp-38h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+28h] [rbp-30h] BYREF
  WINBOOL bDaclPresent; // [rsp+2Ch] [rbp-2Ch] BYREF

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
  if ( !*((_BYTE *)a2 + 16) && (*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    Length = ATL::CAcl::GetLength(a2);
    v6 = (struct _ACL *)malloc(Length);
    if ( !v6 )
      ATL::AtlThrowImpl(-2147024882);
    PACL = ATL::CAcl::GetPACL(a2);
    if ( Length )
    {
      if ( !PACL )
      {
        memset_0(v6, 0, (unsigned int)Length);
        v9 = 22;
        *(_DWORD *)_o__errno(v8) = 22;
        invalid_parameter_noinfo();
LABEL_14:
        ATL::AtlCrtErrorCheck(v9);
        goto LABEL_15;
      }
      memcpy_0(v6, PACL, (unsigned int)Length);
    }
    v9 = 0;
    goto LABEL_14;
  }
  v6 = 0;
LABEL_15:
  v10 = *((_BYTE *)a2 + 16) || v6;
  if ( !SetSecurityDescriptorDacl(this[1], v10, v6, 0) )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    free(v6);
    ATL::AtlThrowImpl(LastErrorAsHResult);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x1800187c0  mov     [rsp+arg_10], rbx
0x1800187c5  push    rbp
0x1800187c6  push    rsi
0x1800187c7  push    rdi
0x1800187c8  sub     rsp, 40h
0x1800187cc  mov     rax, cs:__security_cookie
0x1800187d3  xor     rax, rsp
0x1800187d6  mov     [rsp+58h+var_28], rax
0x1800187db  cmp     qword ptr [rcx+8], 0
0x1800187e0  mov     rbx, rdx
0x1800187e3  mov     rsi, rcx
0x1800187e6  jz      short loc_1800187ED
0x1800187e8  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x1800187ed  mov     rcx, [rsi+8]; pSecurityDescriptor
0x1800187f1  mov     [rsp+58h+pDacl], 0
0x1800187fa  test    rcx, rcx
0x1800187fd  jz      loc_180018925
0x180018803  lea     r9, [rsp+58h+bDaclDefaulted]; lpbDaclDefaulted
0x180018808  mov     [rsp+58h+bDaclDefaulted], 0
0x180018810  lea     r8, [rsp+58h+pDacl]; pDacl
0x180018815  mov     [rsp+58h+bDaclPresent], 0
0x18001881d  lea     rdx, [rsp+58h+bDaclPresent]; lpbDaclPresent
0x180018822  call    cs:__imp_GetSecurityDescriptorDacl
0x180018828  test    eax, eax
0x18001882a  jz      loc_18001891F
0x180018830  cmp     byte ptr [rbx+10h], 0
0x180018834  jnz     short loc_18001889A
0x180018836  mov     rax, [rbx]
0x180018839  mov     rcx, rbx
0x18001883c  mov     rax, [rax+8]
0x180018840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018845  test    eax, eax
0x180018847  jz      short loc_18001889A
0x180018849  mov     rcx, rbx; this
0x18001884c  call    ?GetLength@CAcl@ATL@@QEBAIXZ; ATL::CAcl::GetLength(void)
0x180018851  mov     ecx, eax; Size
0x180018853  mov     ebp, eax
0x180018855  call    cs:__imp_malloc
0x18001885b  mov     rdi, rax
0x18001885e  test    rax, rax
0x180018861  jz      loc_180018914
0x180018867  mov     rcx, rbx; this
0x18001886a  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18001886f  test    rbp, rbp
0x180018872  jz      short loc_1800188A6
0x180018874  mov     r8d, ebp; Size
0x180018877  mov     rcx, rdi; void *
0x18001887a  test    rax, rax
0x18001887d  jnz     short loc_18001889E
0x18001887f  xor     edx, edx; Val
0x180018881  call    memset_0
0x180018886  call    cs:__imp__o__errno
0x18001888c  mov     ebp, 16h
0x180018891  mov     [rax], ebp
0x180018893  call    _invalid_parameter_noinfo
0x180018898  jmp     short loc_1800188A8
0x18001889a  xor     edi, edi
0x18001889c  jmp     short loc_1800188AF
0x18001889e  mov     rdx, rax; Src
0x1800188a1  call    memcpy_0
0x1800188a6  xor     ebp, ebp
0x1800188a8  mov     ecx, ebp; int
0x1800188aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800188af  cmp     byte ptr [rbx+10h], 0
0x1800188b3  jnz     short loc_1800188BA
0x1800188b5  test    rdi, rdi
0x1800188b8  jz      short loc_1800188F8
0x1800188ba  mov     edx, 1; bDaclPresent
0x1800188bf  mov     rcx, [rsi+8]; pSecurityDescriptor
0x1800188c3  xor     r9d, r9d; bDaclDefaulted
0x1800188c6  mov     r8, rdi; pDacl
0x1800188c9  call    cs:__imp_SetSecurityDescriptorDacl
0x1800188cf  test    eax, eax
0x1800188d1  jz      short loc_1800188FC
0x1800188d3  mov     rcx, [rsp+58h+pDacl]; Block
0x1800188d8  call    cs:__imp_free
0x1800188de  mov     rcx, [rsp+58h+var_28]
0x1800188e3  xor     rcx, rsp; StackCookie
0x1800188e6  call    __security_check_cookie
0x1800188eb  mov     rbx, [rsp+58h+arg_10]
0x1800188f0  add     rsp, 40h
0x1800188f4  pop     rdi
0x1800188f5  pop     rsi
0x1800188f6  pop     rbp
0x1800188f7  retn
0x1800188f8  xor     edx, edx
0x1800188fa  jmp     short loc_1800188BF
0x1800188fc  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x180018901  mov     rcx, rdi; Block
0x180018904  mov     ebx, eax
0x180018906  call    cs:__imp_free
0x18001890c  mov     ecx, ebx; int
0x18001890e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180018914  mov     ecx, 8007000Eh; int
0x180018919  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001891f  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180018925  mov     rcx, rsi; this
0x180018928  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x18001892d  jmp     loc_180018830
```
