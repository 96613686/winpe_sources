# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x140012754`
- end: `0x140012972`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `542`
- prototype: `void(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a5a0`

## callees

- `0x140004280`
- `0x14000a220`
- `0x14000a2e8`
- `0x14000a310`
- `0x14000cc28`
- `0x140010a58`
- `0x140012754`
- `0x140014860`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400127ea`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1400127ea`
- `ADVAPI32!GetAclInformation` at `0x140012847`
- `ADVAPI32!GetAclInformation` at `0x140012847`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400127bd`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400127bd`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400128ca`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1400128ca`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400128d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001290b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140012940`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400128d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001290b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140012940`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400127d2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001285e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400127d2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001285e`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(void **this, const struct ATL::CDacl *a2)
{
  void *v4; // rcx
  BOOL v5; // ebp
  void *v6; // rax
  ACL *PACL; // rax
  unsigned int v8; // eax
  unsigned int v9; // r14d
  ACL *v10; // rsi
  const struct _ACL *v11; // rax
  errno_t v12; // eax
  int v13; // ebx
  int Error; // ebx
  BOOL bDaclDefaulted; // [rsp+20h] [rbp-48h] BYREF
  BOOL bDaclPresent; // [rsp+24h] [rbp-44h] BYREF
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
      goto LABEL_30;
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
    v10 = 0;
    goto LABEL_22;
  }
  PACL = (ACL *)ATL::CAcl::GetPACL(a2);
  pAclInformation = 0;
  v19 = 0;
  if ( *((_BYTE *)a2 + 16) )
  {
    v8 = 0;
  }
  else
  {
    if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
      ATL::AtlThrowLastWin32();
    v8 = HIDWORD(pAclInformation);
  }
  v9 = v8;
  v10 = (ACL *)malloc(v8);
  if ( !v10 )
LABEL_30:
    ATL::AtlThrowImpl(-2147024882);
  v11 = ATL::CAcl::GetPACL(a2);
  v12 = memcpy_s(v10, v9, v11, v9);
  if ( v12 )
  {
    if ( v12 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v12 == 22 || v12 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v12 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
LABEL_22:
  if ( !*((_BYTE *)a2 + 16) && !v10 )
    v5 = 0;
  if ( !SetSecurityDescriptorDacl(this[1], v5, v10, 0) )
  {
    v13 = ATL::AtlHresultFromLastError();
    free(v10);
    ATL::AtlThrowImpl(v13);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x140012754  mov     [rsp+arg_10], rbx
0x140012759  mov     [rsp+arg_18], rbp
0x14001275e  push    rsi
0x14001275f  push    rdi
0x140012760  push    r14
0x140012762  sub     rsp, 50h
0x140012766  mov     rax, cs:__security_cookie
0x14001276d  xor     rax, rsp
0x140012770  mov     [rsp+68h+var_28], rax
0x140012775  cmp     qword ptr [rcx+8], 0
0x14001277a  mov     rbx, rdx
0x14001277d  mov     rdi, rcx
0x140012780  jz      short loc_140012787
0x140012782  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x140012787  mov     rcx, [rdi+8]; pSecurityDescriptor
0x14001278b  mov     ebp, 1
0x140012790  mov     [rsp+68h+pDacl], 0
0x140012799  test    rcx, rcx
0x14001279c  jz      short loc_1400127CD
0x14001279e  lea     r9, [rsp+68h+bDaclDefaulted]; lpbDaclDefaulted
0x1400127a3  mov     [rsp+68h+bDaclDefaulted], 0
0x1400127ab  lea     r8, [rsp+68h+pDacl]; pDacl
0x1400127b0  mov     [rsp+68h+bDaclPresent], 0
0x1400127b8  lea     rdx, [rsp+68h+bDaclPresent]; lpbDaclPresent
0x1400127bd  call    cs:__imp_GetSecurityDescriptorDacl
0x1400127c3  test    eax, eax
0x1400127c5  jz      loc_140012919
0x1400127cb  jmp     short loc_1400127F8
0x1400127cd  mov     ecx, 28h ; '('; Size
0x1400127d2  call    cs:__imp_malloc
0x1400127d8  mov     [rdi+8], rax
0x1400127dc  test    rax, rax
0x1400127df  jz      loc_14001292A
0x1400127e5  mov     edx, ebp; dwRevision
0x1400127e7  mov     rcx, rax; pSecurityDescriptor
0x1400127ea  call    cs:__imp_InitializeSecurityDescriptor
0x1400127f0  test    eax, eax
0x1400127f2  jz      loc_140012935
0x1400127f8  cmp     byte ptr [rbx+10h], 0
0x1400127fc  jnz     loc_1400128AF
0x140012802  mov     rax, [rbx]
0x140012805  mov     rcx, rbx
0x140012808  mov     rax, [rax+8]
0x14001280c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012811  test    eax, eax
0x140012813  jz      loc_1400128AF
0x140012819  mov     rcx, rbx; this
0x14001281c  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x140012821  xor     ecx, ecx
0x140012823  mov     [rsp+68h+pAclInformation], rcx
0x140012828  mov     [rsp+68h+var_30], ecx
0x14001282c  cmp     [rbx+10h], cl
0x14001282f  jz      short loc_140012835
0x140012831  xor     eax, eax
0x140012833  jmp     short loc_140012859
0x140012835  mov     r9d, 2; dwAclInformationClass
0x14001283b  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x140012840  mov     rcx, rax; pAcl
0x140012843  lea     r8d, [r9+0Ah]; nAclInformationLength
0x140012847  call    cs:__imp_GetAclInformation
0x14001284d  test    eax, eax
0x14001284f  jz      loc_140012956
0x140012855  mov     eax, dword ptr [rsp+68h+pAclInformation+4]
0x140012859  mov     ecx, eax; Size
0x14001285b  mov     r14d, eax
0x14001285e  call    cs:__imp_malloc
0x140012864  mov     rsi, rax
0x140012867  test    rax, rax
0x14001286a  jz      loc_14001292A
0x140012870  mov     rcx, rbx; this
0x140012873  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x140012878  mov     r9d, r14d; SourceSize
0x14001287b  mov     r8, rax; Source
0x14001287e  mov     edx, r14d; DestinationSize
0x140012881  mov     rcx, rsi; Destination
0x140012884  call    memcpy_s
0x140012889  test    eax, eax
0x14001288b  jz      short loc_1400128B1
0x14001288d  cmp     eax, 0Ch
0x140012890  jz      loc_140012967
0x140012896  cmp     eax, 16h
0x140012899  jz      loc_14001295C
0x14001289f  cmp     eax, 22h ; '"'
0x1400128a2  jz      loc_14001295C
0x1400128a8  cmp     eax, 50h ; 'P'
0x1400128ab  jnz     short loc_14001291F
0x1400128ad  jmp     short loc_1400128B1
0x1400128af  xor     esi, esi
0x1400128b1  cmp     byte ptr [rbx+10h], 0
0x1400128b5  jnz     short loc_1400128BE
0x1400128b7  test    rsi, rsi
0x1400128ba  jnz     short loc_1400128BE
0x1400128bc  xor     ebp, ebp
0x1400128be  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1400128c2  xor     r9d, r9d; bDaclDefaulted
0x1400128c5  mov     r8, rsi; pDacl
0x1400128c8  mov     edx, ebp; bDaclPresent
0x1400128ca  call    cs:__imp_SetSecurityDescriptorDacl
0x1400128d0  test    eax, eax
0x1400128d2  jz      short loc_140012901
0x1400128d4  mov     rcx, [rsp+68h+pDacl]; Block
0x1400128d9  call    cs:__imp_free
0x1400128df  mov     rcx, [rsp+68h+var_28]
0x1400128e4  xor     rcx, rsp; StackCookie
0x1400128e7  call    __security_check_cookie
0x1400128ec  lea     r11, [rsp+68h+var_18]
0x1400128f1  mov     rbx, [r11+30h]
0x1400128f5  mov     rbp, [r11+38h]
0x1400128f9  mov     rsp, r11
0x1400128fc  pop     r14
0x1400128fe  pop     rdi
0x1400128ff  pop     rsi
0x140012900  retn
0x140012901  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140012906  mov     rcx, rsi; Block
0x140012909  mov     ebx, eax
0x14001290b  call    cs:__imp_free
0x140012911  mov     ecx, ebx; int
0x140012913  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012919  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x14001291f  mov     ecx, 80004005h; int
0x140012924  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001292a  mov     ecx, 8007000Eh; int
0x14001292f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012935  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14001293a  mov     rcx, [rdi+8]; Block
0x14001293e  mov     ebx, eax
0x140012940  call    cs:__imp_free
0x140012946  mov     ecx, ebx; int
0x140012948  mov     qword ptr [rdi+8], 0
0x140012950  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012956  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x14001295c  mov     ecx, 80070057h; int
0x140012961  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140012967  mov     ecx, 8007000Eh; int
0x14001296c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
