# ATL::CSecurityDesc::SetGroup(ATL::CSid const &,bool)

- ea: `0x18004561c`
- end: `0x180045717`
- name: `?SetGroup@CSecurityDesc@ATL@@QEAAXAEBVCSid@2@_N@Z`
- size: `251`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this, const struct ATL::CSid *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800435fc`

## callees

- `0x180006d14`
- `0x180007598`
- `0x180010290`
- `0x180042458`
- `0x180042e4c`
- `0x180043b5c`
- `0x180043bec`
- `0x18004561c`

## import_xrefs

- `msvcrt!malloc` at `0x1800456a7`
- `msvcrt!malloc` at `0x1800456a7`
- `msvcrt!free` at `0x1800456ec`
- `msvcrt!free` at `0x180045709`
- `msvcrt!free` at `0x1800456ec`
- `msvcrt!free` at `0x180045709`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800456dd`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x1800456dd`
- `ADVAPI32!CopySid` at `0x1800456c9`
- `ADVAPI32!CopySid` at `0x1800456c9`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180045663`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x180045663`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::SetGroup(PSECURITY_DESCRIPTOR *this, const struct ATL::CSid *a2, char a3)
{
  PSECURITY_DESCRIPTOR v5; // rcx
  DWORD Length; // ebp
  void *v7; // rax
  void *v8; // rdi
  int Error; // ebx
  PSID pGroup; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(bGroupDefaulted) = a3;
  if ( this[1] )
    ATL::CSecurityDesc::MakeAbsolute((ATL::CSecurityDesc *)this);
  v5 = this[1];
  pGroup = 0;
  if ( v5 )
  {
    bGroupDefaulted = 0;
    if ( !GetSecurityDescriptorGroup(v5, &pGroup, &bGroupDefaulted) )
      ATL::AtlThrowLastWin32();
  }
  else
  {
    ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor((ATL::CSecurityDesc *)this);
    pGroup = 0;
  }
  if ( !ATL::CSid::IsValid(a2) )
    ATL::AtlThrowImpl(-2147467259);
  Length = ATL::CSid::GetLength(a2);
  v7 = malloc(Length);
  v8 = v7;
  if ( !v7 )
    ATL::AtlThrowImpl(-2147024882);
  if ( !CopySid(Length, v7, (char *)a2 + 8) || !SetSecurityDescriptorGroup(this[1], v8, 0) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(v8);
    ATL::AtlThrowImpl(Error);
  }
  free(pGroup);
}

```

## disassembly

```asm
0x18004561c  mov     [rsp+arg_8], rbx
0x180045621  mov     byte ptr [rsp+bGroupDefaulted], r8b
0x180045626  push    rbp
0x180045627  push    rsi
0x180045628  push    rdi
0x180045629  sub     rsp, 20h
0x18004562d  cmp     qword ptr [rcx+8], 0
0x180045632  mov     rsi, rdx
0x180045635  mov     rbx, rcx
0x180045638  jz      short loc_18004563F
0x18004563a  call    ?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ; ATL::CSecurityDesc::MakeAbsolute(void)
0x18004563f  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180045643  mov     [rsp+38h+pGroup], 0
0x18004564c  test    rcx, rcx
0x18004564f  jz      short loc_180045673
0x180045651  lea     r8, [rsp+38h+bGroupDefaulted]; lpbGroupDefaulted
0x180045656  mov     [rsp+38h+bGroupDefaulted], 0
0x18004565e  lea     rdx, [rsp+38h+pGroup]; pGroup
0x180045663  call    cs:__imp_GetSecurityDescriptorGroup
0x180045669  test    eax, eax
0x18004566b  jnz     short loc_180045684
0x18004566d  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180045673  mov     rcx, rbx; this
0x180045676  call    ?AllocateAndInitializeSecurityDescriptor@CSecurityDesc@ATL@@IEAAXXZ; ATL::CSecurityDesc::AllocateAndInitializeSecurityDescriptor(void)
0x18004567b  mov     [rsp+38h+pGroup], 0
0x180045684  mov     rcx, rsi; this
0x180045687  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x18004568c  test    al, al
0x18004568e  jnz     short loc_18004569B
0x180045690  mov     ecx, 80004005h; int
0x180045695  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18004569b  mov     rcx, rsi; this
0x18004569e  call    ?GetLength@CSid@ATL@@QEBAIXZ; ATL::CSid::GetLength(void)
0x1800456a3  mov     ecx, eax; Size
0x1800456a5  mov     ebp, eax
0x1800456a7  call    cs:__imp_malloc
0x1800456ad  mov     rdi, rax
0x1800456b0  test    rax, rax
0x1800456b3  jnz     short loc_1800456C0
0x1800456b5  mov     ecx, 8007000Eh; int
0x1800456ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800456c0  lea     r8, [rsi+8]; pSourceSid
0x1800456c4  mov     rdx, rdi; pDestinationSid
0x1800456c7  mov     ecx, ebp; nDestinationSidLength
0x1800456c9  call    cs:__imp_CopySid
0x1800456cf  test    eax, eax
0x1800456d1  jz      short loc_1800456FF
0x1800456d3  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800456d7  xor     r8d, r8d; bGroupDefaulted
0x1800456da  mov     rdx, rdi; pGroup
0x1800456dd  call    cs:__imp_SetSecurityDescriptorGroup
0x1800456e3  test    eax, eax
0x1800456e5  jz      short loc_1800456FF
0x1800456e7  mov     rcx, [rsp+38h+pGroup]; Block
0x1800456ec  call    cs:__imp_free
0x1800456f2  mov     rbx, [rsp+38h+arg_8]
0x1800456f7  add     rsp, 20h
0x1800456fb  pop     rdi
0x1800456fc  pop     rsi
0x1800456fd  pop     rbp
0x1800456fe  retn
0x1800456ff  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180045704  mov     rcx, rdi; Block
0x180045707  mov     ebx, eax
0x180045709  call    cs:__imp_free
0x18004570f  mov     ecx, ebx; int
0x180045711  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
