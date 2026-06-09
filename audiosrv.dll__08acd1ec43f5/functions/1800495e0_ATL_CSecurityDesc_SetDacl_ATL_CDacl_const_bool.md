# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x1800495e0`
- end: `0x1800496ff`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `287`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037a10`

## callees

- `0x1800495e0`
- `0x180049708`
- `0x180049778`
- `0x1800497e8`
- `0x180049948`
- `0x1800b1930`
- `0x1800b196c`
- `0x1800d40e4`
- `0x1800d4178`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800496d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800496ec`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800496d9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800496ec`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180049671`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180049671`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800496c5`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800496c5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049634`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049634`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetDacl(PSECURITY_DESCRIPTOR *this, const struct ATL::CDacl *a2, char a3)
{
  PSECURITY_DESCRIPTOR v5; // rcx
  size_t Length; // rbp
  ATL::Checked *v7; // rdi
  const struct _ACL *PACL; // rax
  BOOL v9; // edx
  int Error; // ebx
  unsigned __int64 v11; // [rsp+20h] [rbp-18h]
  WINBOOL bDaclPresent; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+58h] [rbp+20h] BYREF

  LOBYTE(bDaclDefaulted) = a3;
  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v5 = this[1];
  pDacl = 0;
  if ( v5 )
  {
    bDaclDefaulted = 0;
    bDaclPresent = 0;
    if ( !GetSecurityDescriptorDacl(v5, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
  }
  if ( *((_BYTE *)a2 + 16) || !(*(unsigned int (__fastcall **)(const struct ATL::CDacl *))(*(_QWORD *)a2 + 8LL))(a2) )
  {
    v7 = 0;
  }
  else
  {
    Length = ATL::CAcl::GetLength(a2);
    v7 = (ATL::Checked *)malloc(Length);
    if ( !v7 )
      ATL::AtlThrowImpl(-2147024882);
    PACL = ATL::CAcl::GetPACL(a2);
    ATL::Checked::memcpy_s(v7, (void *)Length, (unsigned __int64)PACL, (const void *)Length, v11);
  }
  v9 = *((_BYTE *)a2 + 16) || v7;
  if ( !SetSecurityDescriptorDacl(this[1], v9, (PACL)v7, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v7);
    ATL::AtlThrowImpl(Error);
  }
  free(pDacl);
}

```

## disassembly

```asm
0x1800495e0  mov     [rsp+arg_8], rbx
0x1800495e5  mov     byte ptr [rsp+bDaclDefaulted], r8b
0x1800495ea  push    rbp
0x1800495eb  push    rsi
0x1800495ec  push    rdi; unsigned __int64
0x1800495ed  sub     rsp, 20h
0x1800495f1  cmp     qword ptr [rcx+8], 0
0x1800495f6  mov     rbx, rdx
0x1800495f9  mov     rsi, rcx
0x1800495fc  jz      short loc_180049603
0x1800495fe  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x180049603  mov     rcx, [rsi+8]; pSecurityDescriptor
0x180049607  mov     [rsp+38h+pDacl], 0
0x180049610  test    rcx, rcx
0x180049613  jz      short loc_180049644
0x180049615  lea     r9, [rsp+38h+bDaclDefaulted]; lpbDaclDefaulted
0x18004961a  mov     [rsp+38h+bDaclDefaulted], 0
0x180049622  lea     r8, [rsp+38h+pDacl]; pDacl
0x180049627  mov     [rsp+38h+bDaclPresent], 0
0x18004962f  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x180049634  call    cs:__imp_GetSecurityDescriptorDacl
0x18004963a  test    eax, eax
0x18004963c  jnz     short loc_18004964C
0x18004963e  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180049644  mov     rcx, rsi; this
0x180049647  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x18004964c  cmp     byte ptr [rbx+10h], 0
0x180049650  jnz     short loc_1800496A5
0x180049652  mov     rax, [rbx]
0x180049655  mov     rcx, rbx
0x180049658  mov     rax, [rax+8]
0x18004965c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049661  test    eax, eax
0x180049663  jz      short loc_1800496A5
0x180049665  mov     rcx, rbx; this
0x180049668  call    ?GetLength@CAcl@ATL@@QEBAIXZ; ATL::CAcl::GetLength(void)
0x18004966d  mov     ecx, eax; Size
0x18004966f  mov     ebp, eax
0x180049671  call    cs:__imp_malloc
0x180049677  mov     rdi, rax
0x18004967a  test    rax, rax
0x18004967d  jnz     short loc_18004968A
0x18004967f  mov     ecx, 8007000Eh; int
0x180049684  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004968a  mov     rcx, rbx; this
0x18004968d  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x180049692  mov     r8, rax; unsigned __int64
0x180049695  mov     r9, rbp; void *
0x180049698  mov     rdx, rbp; void *
0x18004969b  mov     rcx, rdi; this
0x18004969e  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x1800496a3  jmp     short loc_1800496A7
0x1800496a5  xor     edi, edi
0x1800496a7  cmp     byte ptr [rbx+10h], 0
0x1800496ab  jnz     short loc_1800496B6
0x1800496ad  test    rdi, rdi
0x1800496b0  jnz     short loc_1800496B6
0x1800496b2  xor     edx, edx
0x1800496b4  jmp     short loc_1800496BB
0x1800496b6  mov     edx, 1; bDaclPresent
0x1800496bb  mov     rcx, [rsi+8]; pSecurityDescriptor
0x1800496bf  xor     r9d, r9d; bDaclDefaulted
0x1800496c2  mov     r8, rdi; pDacl
0x1800496c5  call    cs:__imp_SetSecurityDescriptorDacl
0x1800496cb  test    eax, eax
0x1800496cd  jnz     short loc_1800496E7
0x1800496cf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800496d4  mov     rcx, rdi; Block
0x1800496d7  mov     ebx, eax
0x1800496d9  call    cs:__imp_free
0x1800496df  mov     ecx, ebx; int
0x1800496e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800496e7  mov     rcx, [rsp+38h+pDacl]; Block
0x1800496ec  call    cs:__imp_free
0x1800496f2  mov     rbx, [rsp+38h+arg_8]
0x1800496f7  add     rsp, 20h
0x1800496fb  pop     rdi
0x1800496fc  pop     rsi
0x1800496fd  pop     rbp
0x1800496fe  retn
```
