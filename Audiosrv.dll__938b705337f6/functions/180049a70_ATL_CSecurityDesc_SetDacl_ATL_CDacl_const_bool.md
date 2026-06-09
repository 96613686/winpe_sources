# ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)

- ea: `0x180049a70`
- end: `0x180049b8f`
- name: `?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z`
- size: `287`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CDacl *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800378b0`

## callees

- `0x180049a70`
- `0x180049b98`
- `0x180049c08`
- `0x180049c78`
- `0x180049dd8`
- `0x1800b3620`
- `0x1800b365c`
- `0x1800d60d4`
- `0x1800d6168`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049b69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049b7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049b69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049b7c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180049b01`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180049b01`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180049b55`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180049b55`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049ac4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180049ac4`

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
0x180049a70  mov     [rsp+arg_8], rbx
0x180049a75  mov     byte ptr [rsp+bDaclDefaulted], r8b
0x180049a7a  push    rbp
0x180049a7b  push    rsi
0x180049a7c  push    rdi; unsigned __int64
0x180049a7d  sub     rsp, 20h
0x180049a81  cmp     qword ptr [rcx+8], 0
0x180049a86  mov     rbx, rdx
0x180049a89  mov     rsi, rcx
0x180049a8c  jz      short loc_180049A93
0x180049a8e  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x180049a93  mov     rcx, [rsi+8]; pSecurityDescriptor
0x180049a97  mov     [rsp+38h+pDacl], 0
0x180049aa0  test    rcx, rcx
0x180049aa3  jz      short loc_180049AD4
0x180049aa5  lea     r9, [rsp+38h+bDaclDefaulted]; lpbDaclDefaulted
0x180049aaa  mov     [rsp+38h+bDaclDefaulted], 0
0x180049ab2  lea     r8, [rsp+38h+pDacl]; pDacl
0x180049ab7  mov     [rsp+38h+bDaclPresent], 0
0x180049abf  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x180049ac4  call    cs:__imp_GetSecurityDescriptorDacl
0x180049aca  test    eax, eax
0x180049acc  jnz     short loc_180049ADC
0x180049ace  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180049ad4  mov     rcx, rsi; this
0x180049ad7  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x180049adc  cmp     byte ptr [rbx+10h], 0
0x180049ae0  jnz     short loc_180049B35
0x180049ae2  mov     rax, [rbx]
0x180049ae5  mov     rcx, rbx
0x180049ae8  mov     rax, [rax+8]
0x180049aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049af1  test    eax, eax
0x180049af3  jz      short loc_180049B35
0x180049af5  mov     rcx, rbx; this
0x180049af8  call    ?GetLength@CAcl@ATL@@QEBAIXZ; ATL::CAcl::GetLength(void)
0x180049afd  mov     ecx, eax; Size
0x180049aff  mov     ebp, eax
0x180049b01  call    cs:__imp_malloc
0x180049b07  mov     rdi, rax
0x180049b0a  test    rax, rax
0x180049b0d  jnz     short loc_180049B1A
0x180049b0f  mov     ecx, 8007000Eh; int
0x180049b14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180049b1a  mov     rcx, rbx; this
0x180049b1d  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x180049b22  mov     r8, rax; unsigned __int64
0x180049b25  mov     r9, rbp; void *
0x180049b28  mov     rdx, rbp; void *
0x180049b2b  mov     rcx, rdi; this
0x180049b2e  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180049b33  jmp     short loc_180049B37
0x180049b35  xor     edi, edi
0x180049b37  cmp     byte ptr [rbx+10h], 0
0x180049b3b  jnz     short loc_180049B46
0x180049b3d  test    rdi, rdi
0x180049b40  jnz     short loc_180049B46
0x180049b42  xor     edx, edx
0x180049b44  jmp     short loc_180049B4B
0x180049b46  mov     edx, 1; bDaclPresent
0x180049b4b  mov     rcx, [rsi+8]; pSecurityDescriptor
0x180049b4f  xor     r9d, r9d; bDaclDefaulted
0x180049b52  mov     r8, rdi; pDacl
0x180049b55  call    cs:__imp_SetSecurityDescriptorDacl
0x180049b5b  test    eax, eax
0x180049b5d  jnz     short loc_180049B77
0x180049b5f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180049b64  mov     rcx, rdi; Block
0x180049b67  mov     ebx, eax
0x180049b69  call    cs:__imp_free
0x180049b6f  mov     ecx, ebx; int
0x180049b71  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180049b77  mov     rcx, [rsp+38h+pDacl]; Block
0x180049b7c  call    cs:__imp_free
0x180049b82  mov     rbx, [rsp+38h+arg_8]
0x180049b87  add     rsp, 20h
0x180049b8b  pop     rdi
0x180049b8c  pop     rsi
0x180049b8d  pop     rbp
0x180049b8e  retn
```
