# SecUtil::CSecurityDescriptor::InitializeFromToken(void *)

- ea: `0x1800acac4`
- end: `0x1800acc6d`
- name: `?InitializeFromToken@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z`
- size: `425`
- prototype: `void __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010110c`
- `0x18014ab94`

## callees

- `0x1800acac4`
- `0x1800ad2b4`
- `0x1800e95f0`
- `0x1801244c0`
- `0x180222f70`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800acb84`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800acb84`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800acc34`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x1800acc34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acbc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acbfe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acb4e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acbc3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800acbfe`

## string_xrefs

- `0x1800acb5c`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800acb92`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800acc0c`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x1800acc42`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
void __fastcall SecUtil::CSecurityDescriptor::InitializeFromToken(PSID *pSecurityDescriptor, HANDLE TokenHandle)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  void *v6; // rsp
  void *v7; // rsp
  const char *v8; // r9
  const char *v9; // r9
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  const char *v14; // r9
  const char *v15; // r9
  __int64 TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+48h]

  LODWORD(TokenInformation) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformation);
  v4 = (unsigned int)TokenInformation + 15LL;
  if ( v4 <= (unsigned int)TokenInformation )
    v4 = 0xFFFFFFFFFFFFFF0LL;
  v5 = v4 & 0xFFFFFFFFFFFFFFF0uLL;
  v6 = alloca(v5);
  v7 = alloca(v5);
  if ( !GetTokenInformation(TokenHandle, TokenUser, &TokenInformation, TokenInformation, (PDWORD)&TokenInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      v8);
  SecUtil::CSID::operator=(pSecurityDescriptor + 5, TokenInformation);
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pSecurityDescriptor[5], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      v9);
  LODWORD(TokenInformation) = 0;
  GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, (PDWORD)&TokenInformation);
  v10 = (unsigned int)TokenInformation + 15LL;
  if ( v10 <= (unsigned int)TokenInformation )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  if ( !GetTokenInformation(
          TokenHandle,
          TokenPrimaryGroup,
          &TokenInformation,
          TokenInformation,
          (PDWORD)&TokenInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      v14);
  SecUtil::CSID::operator=(pSecurityDescriptor + 6, TokenInformation);
  if ( !SetSecurityDescriptorGroup(pSecurityDescriptor, pSecurityDescriptor[6], 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      v15);
}

```

## disassembly

```asm
0x1800acac4  push    rbp
0x1800acac6  push    rbx
0x1800acac7  push    rsi
0x1800acac8  push    rdi
0x1800acac9  push    r14
0x1800acacb  push    r15
0x1800acacd  sub     rsp, 48h
0x1800acad1  lea     rbp, [rsp+30h]
0x1800acad6  mov     rax, cs:__security_cookie
0x1800acadd  xor     rax, rbp
0x1800acae0  mov     [rbp+40h+var_38], rax
0x1800acae4  mov     rsi, rdx
0x1800acae7  mov     dword ptr [rbp+40h+TokenInformation], 0
0x1800acaee  xor     r9d, r9d; TokenInformationLength
0x1800acaf1  lea     rax, [rbp+40h+TokenInformation]
0x1800acaf5  mov     rdi, rcx
0x1800acaf8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800acafd  xor     r8d, r8d; TokenInformation
0x1800acb00  mov     rcx, rsi; TokenHandle
0x1800acb03  lea     ebx, [r9+1]
0x1800acb07  mov     edx, ebx; TokenInformationClass
0x1800acb09  call    cs:__imp_GetTokenInformation
0x1800acb0f  mov     r9d, dword ptr [rbp+40h+TokenInformation]
0x1800acb13  mov     r15, 0FFFFFFFFFFFFFF0h
0x1800acb1d  lea     rdx, [r9+0Fh]
0x1800acb21  cmp     rdx, r9
0x1800acb24  ja      short loc_1800ACB29
0x1800acb26  mov     rdx, r15
0x1800acb29  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800acb2d  mov     rax, rdx
0x1800acb30  call    _alloca_probe
0x1800acb35  sub     rsp, rdx
0x1800acb38  lea     rax, [rbp+40h+TokenInformation]
0x1800acb3c  mov     edx, ebx; TokenInformationClass
0x1800acb3e  mov     rcx, rsi; TokenHandle
0x1800acb41  lea     r14, [rsp+70h+TokenInformation]
0x1800acb46  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800acb4b  mov     r8, r14; TokenInformation
0x1800acb4e  call    cs:__imp_GetTokenInformation
0x1800acb54  test    eax, eax
0x1800acb56  jnz     short loc_1800ACB6E
0x1800acb58  mov     rcx, [rbp+48h]; this
0x1800acb5c  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800acb63  mov     edx, 11Fh; void *
0x1800acb68  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800acb6e  mov     rdx, [r14]
0x1800acb71  lea     rcx, [rdi+28h]
0x1800acb75  call    ??4CSID@SecUtil@@QEAAXPEAX@Z; SecUtil::CSID::operator=(void *)
0x1800acb7a  mov     rdx, [rdi+28h]; pOwner
0x1800acb7e  xor     r8d, r8d; bOwnerDefaulted
0x1800acb81  mov     rcx, rdi; pSecurityDescriptor
0x1800acb84  call    cs:__imp_SetSecurityDescriptorOwner
0x1800acb8a  test    eax, eax
0x1800acb8c  jnz     short loc_1800ACBA4
0x1800acb8e  mov     rcx, [rbp+48h]; this
0x1800acb92  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800acb99  mov     edx, 0D8h; void *
0x1800acb9e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800acba4  xor     r9d, r9d; TokenInformationLength
0x1800acba7  mov     dword ptr [rbp+40h+TokenInformation], 0
0x1800acbae  lea     rax, [rbp+40h+TokenInformation]
0x1800acbb2  xor     r8d, r8d; TokenInformation
0x1800acbb5  mov     rcx, rsi; TokenHandle
0x1800acbb8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800acbbd  lea     ebx, [r9+5]
0x1800acbc1  mov     edx, ebx; TokenInformationClass
0x1800acbc3  call    cs:__imp_GetTokenInformation
0x1800acbc9  mov     r9d, dword ptr [rbp+40h+TokenInformation]
0x1800acbcd  lea     rcx, [r9+0Fh]
0x1800acbd1  cmp     rcx, r9
0x1800acbd4  ja      short loc_1800ACBD9
0x1800acbd6  mov     rcx, r15
0x1800acbd9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800acbdd  mov     rax, rcx
0x1800acbe0  call    _alloca_probe
0x1800acbe5  sub     rsp, rcx
0x1800acbe8  lea     rax, [rbp+40h+TokenInformation]
0x1800acbec  mov     edx, ebx; TokenInformationClass
0x1800acbee  mov     rcx, rsi; TokenHandle
0x1800acbf1  lea     r14, [rsp+70h+TokenInformation]
0x1800acbf6  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800acbfb  mov     r8, r14; TokenInformation
0x1800acbfe  call    cs:__imp_GetTokenInformation
0x1800acc04  test    eax, eax
0x1800acc06  jnz     short loc_1800ACC1E
0x1800acc08  mov     rcx, [rbp+48h]; this
0x1800acc0c  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800acc13  mov     edx, 130h; void *
0x1800acc18  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800acc1e  mov     rdx, [r14]
0x1800acc21  lea     rcx, [rdi+30h]
0x1800acc25  call    ??4CSID@SecUtil@@QEAAXPEAX@Z; SecUtil::CSID::operator=(void *)
0x1800acc2a  mov     rdx, [rdi+30h]; pGroup
0x1800acc2e  xor     r8d, r8d; bGroupDefaulted
0x1800acc31  mov     rcx, rdi; pSecurityDescriptor
0x1800acc34  call    cs:__imp_SetSecurityDescriptorGroup
0x1800acc3a  test    eax, eax
0x1800acc3c  jnz     short loc_1800ACC54
0x1800acc3e  mov     rcx, [rbp+48h]; this
0x1800acc42  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800acc49  mov     edx, 0E1h; void *
0x1800acc4e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800acc54  mov     rcx, [rbp+40h+var_38]
0x1800acc58  xor     rcx, rbp; StackCookie
0x1800acc5b  call    __security_check_cookie
0x1800acc60  lea     rsp, [rbp+18h]
0x1800acc64  pop     r15
0x1800acc66  pop     r14
0x1800acc68  pop     rdi
0x1800acc69  pop     rsi
0x1800acc6a  pop     rbx
0x1800acc6b  pop     rbp
0x1800acc6c  retn
```
