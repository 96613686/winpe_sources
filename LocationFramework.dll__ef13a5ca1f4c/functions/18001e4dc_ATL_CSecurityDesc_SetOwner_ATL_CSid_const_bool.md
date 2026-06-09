# ATL::CSecurityDesc::SetOwner(ATL::CSid const &,bool)

- ea: `0x18001e4dc`
- end: `0x18001e60b`
- name: `?SetOwner@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
- size: `303`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CSid *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001733c`
- `0x18009b528`

## callees

- `0x180018938`
- `0x18001e46c`
- `0x18001e4dc`
- `0x18001e838`
- `0x18001eb88`
- `0x18009e0f8`
- `0x18009e2e4`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e58d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e58d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e5fd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e550`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001e550`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e56a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001e56a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001e5c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001e5c9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e546`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001e546`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001e57e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001e57e`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetOwner(PSECURITY_DESCRIPTOR *this, const struct ATL::CSid *a2)
{
  PSECURITY_DESCRIPTOR v4; // rcx
  char *v5; // rsi
  DWORD LengthSid; // ebp
  void *v7; // rax
  void *v8; // rdi
  int LastErrorAsHResult; // ebx
  void *Block; // [rsp+20h] [rbp-38h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+28h] [rbp-30h] BYREF

  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v4 = this[1];
  Block = 0;
  if ( v4 )
  {
    bOwnerDefaulted = 0;
    if ( !GetSecurityDescriptorOwner(v4, &Block, &bOwnerDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
    Block = 0;
  }
  if ( !ATL::CSid::IsValid(a2) )
    ATL::AtlThrowImpl(-2147467259);
  v5 = (char *)a2 + 8;
  LengthSid = GetLengthSid((char *)a2 + 8);
  v7 = malloc(LengthSid);
  v8 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(LengthSid, v7, v5) || !SetSecurityDescriptorOwner(this[1], v8, 0) )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    free(v8);
    ATL::AtlThrowImpl(LastErrorAsHResult);
  }
  free(Block);
}

```

## disassembly

```asm
0x18001e4dc  mov     [rsp+arg_10], rbx
0x18001e4e1  push    rbp
0x18001e4e2  push    rsi
0x18001e4e3  push    rdi
0x18001e4e4  sub     rsp, 40h
0x18001e4e8  mov     rax, cs:__security_cookie
0x18001e4ef  xor     rax, rsp
0x18001e4f2  mov     [rsp+58h+var_28], rax
0x18001e4f7  cmp     qword ptr [rcx+8], 0
0x18001e4fc  mov     rdi, rdx
0x18001e4ff  mov     rbx, rcx
0x18001e502  jnz     loc_18001E5AD
0x18001e508  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18001e50c  mov     [rsp+58h+Block], 0
0x18001e515  test    rcx, rcx
0x18001e518  jnz     loc_18001E5B7
0x18001e51e  mov     rcx, rbx; this
0x18001e521  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x18001e526  mov     [rsp+58h+Block], 0
0x18001e52f  mov     rcx, rdi; this
0x18001e532  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18001e537  test    al, al
0x18001e539  jz      loc_18001E5DD
0x18001e53f  lea     rsi, [rdi+8]
0x18001e543  mov     rcx, rsi; pSid
0x18001e546  call    cs:__imp_GetLengthSid
0x18001e54c  mov     ecx, eax; Size
0x18001e54e  mov     ebp, eax
0x18001e550  call    cs:__imp_malloc
0x18001e556  mov     rdi, rax
0x18001e559  test    rax, rax
0x18001e55c  jz      loc_18001E5E8
0x18001e562  mov     r8, rsi; pSourceSid
0x18001e565  mov     rdx, rax; pDestinationSid
0x18001e568  mov     ecx, ebp; nDestinationSidLength
0x18001e56a  call    cs:__imp_CopySid
0x18001e570  test    eax, eax
0x18001e572  jz      short loc_18001E5F3
0x18001e574  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18001e578  xor     r8d, r8d; bOwnerDefaulted
0x18001e57b  mov     rdx, rdi; pOwner
0x18001e57e  call    cs:__imp_SetSecurityDescriptorOwner
0x18001e584  test    eax, eax
0x18001e586  jz      short loc_18001E5F3
0x18001e588  mov     rcx, [rsp+58h+Block]; Block
0x18001e58d  call    cs:__imp_free
0x18001e593  mov     rcx, [rsp+58h+var_28]
0x18001e598  xor     rcx, rsp; StackCookie
0x18001e59b  call    __security_check_cookie
0x18001e5a0  mov     rbx, [rsp+58h+arg_10]
0x18001e5a5  add     rsp, 40h
0x18001e5a9  pop     rdi
0x18001e5aa  pop     rsi
0x18001e5ab  pop     rbp
0x18001e5ac  retn
0x18001e5ad  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x18001e5b2  jmp     loc_18001E508
0x18001e5b7  lea     r8, [rsp+58h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001e5bc  mov     [rsp+58h+bOwnerDefaulted], 0
0x18001e5c4  lea     rdx, [rsp+58h+Block]; pOwner
0x18001e5c9  call    cs:__imp_GetSecurityDescriptorOwner
0x18001e5cf  test    eax, eax
0x18001e5d1  jnz     loc_18001E52F
0x18001e5d7  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18001e5dd  mov     ecx, 80004005h; int
0x18001e5e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e5e8  mov     ecx, 8007000Eh; int
0x18001e5ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e5f3  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18001e5f8  mov     rcx, rdi; Block
0x18001e5fb  mov     ebx, eax
0x18001e5fd  call    cs:__imp_free
0x18001e603  mov     ecx, ebx; int
0x18001e605  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
