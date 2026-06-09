# SecUtil::CSecurityDescriptor::InitializeFromToken(void *)

- ea: `0x18010bf5c`
- end: `0x18010c1a4`
- name: `?InitializeFromToken@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z`
- size: `584`
- prototype: `void(SecUtil::CSecurityDescriptor *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18010bee4`

## callees

- `0x180038f08`
- `0x18010bf5c`
- `0x180147154`
- `0x18015854c`
- `0x1801585a0`
- `0x180188d90`
- `0x180189280`
- `0x1801895b0`
- `0x180294310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bfc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bfc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010c0c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010bfa1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c052`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c09a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c142`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010bfa1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c052`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c09a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18010c142`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SecUtil::CSecurityDescriptor::InitializeFromToken(SecUtil::CSecurityDescriptor *this, void *a2)
{
  const char *v4; // r9
  DWORD *v5; // rdi
  DWORD v6; // r9d
  DWORD *v7; // rbx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  int v12; // r8d
  const char *v13; // r9
  const char *v14; // r9
  DWORD *v15; // rbx
  DWORD v16; // r9d
  DWORD *v17; // rsi
  DWORD *v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  int v23; // r8d
  const char *v24; // r9
  int ReturnLength; // [rsp+20h] [rbp-10h]
  int ReturnLengtha; // [rsp+20h] [rbp-10h]
  DWORD v27; // [rsp+30h] [rbp+0h] BYREF
  DWORD *v28; // [rsp+38h] [rbp+8h]
  DWORD *v29; // [rsp+40h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+58h]

  v27 = 0;
  if ( GetTokenInformation(a2, TokenUser, 0, 0, &v27) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x118,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v4);
  v5 = 0;
  v28 = 0;
  v6 = v27;
  if ( v27 <= 0x80 )
  {
    v8 = v27 + 15LL;
    if ( v8 < v27 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = v8 & 0xFFFFFFFFFFFFFFF0uLL;
    v10 = alloca(v9);
    v11 = alloca(v9);
    v7 = &v27;
  }
  else
  {
    v5 = (DWORD *)operator new[](v27);
    v28 = v5;
    v7 = v5;
    v6 = v27;
  }
  if ( !GetTokenInformation(a2, TokenUser, v7, v6, &v27) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v13);
  SecUtil::CSecurityDescriptor::SetOwner(this, *(void **)v7, v12);
  v27 = 0;
  if ( GetTokenInformation(a2, TokenPrimaryGroup, 0, 0, &v27) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      (const char *)0x8000FFFFLL,
      ReturnLengtha);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v14);
  v15 = 0;
  v29 = 0;
  v16 = v27;
  if ( v27 <= 0x80 )
  {
    v19 = v27 + 15LL;
    if ( v19 < v27 )
      v19 = 0xFFFFFFFFFFFFFF0LL;
    v20 = v19 & 0xFFFFFFFFFFFFFFF0uLL;
    v21 = alloca(v20);
    v22 = alloca(v20);
    v17 = &v27;
    v18 = 0;
  }
  else
  {
    v15 = (DWORD *)operator new[](v27);
    v29 = v15;
    v17 = v15;
    v18 = v15;
    v16 = v27;
  }
  if ( !GetTokenInformation(a2, TokenPrimaryGroup, v17, v16, &v27) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v24);
  SecUtil::CSecurityDescriptor::SetGroup(this, *(void **)v17, v23);
  if ( v18 )
    operator delete(v15);
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x18010bf5c  push    rbp
0x18010bf5e  push    rbx
0x18010bf5f  push    rsi
0x18010bf60  push    rdi
0x18010bf61  push    r12
0x18010bf63  push    r14
0x18010bf65  push    r15
0x18010bf67  sub     rsp, 50h
0x18010bf6b  lea     rbp, [rsp+30h]
0x18010bf70  mov     rax, cs:__security_cookie
0x18010bf77  xor     rax, rbp
0x18010bf7a  mov     [rbp+50h+var_38], rax
0x18010bf7e  mov     r15, rdx
0x18010bf81  mov     r12, rcx
0x18010bf84  mov     [rbp+50h+var_50], 0
0x18010bf8b  lea     rax, [rbp+50h+var_50]
0x18010bf8f  mov     qword ptr [rsp+80h+ReturnLength], rax; int
0x18010bf94  xor     r9d, r9d; TokenInformationLength
0x18010bf97  xor     r8d, r8d; TokenInformation
0x18010bf9a  lea     edx, [r9+1]; TokenInformationClass
0x18010bf9e  mov     rcx, r15; TokenHandle
0x18010bfa1  call    cs:__imp_GetTokenInformation
0x18010bfa7  test    eax, eax
0x18010bfa9  jz      short loc_18010BFC7
0x18010bfab  mov     rcx, [rbp+58h]; this
0x18010bfaf  mov     r9d, 8000FFFFh; char *
0x18010bfb5  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010bfbc  mov     edx, 118h; void *
0x18010bfc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010bfc7  call    cs:__imp_GetLastError
0x18010bfcd  cmp     eax, 7Ah ; 'z'
0x18010bfd0  jz      short loc_18010BFE8
0x18010bfd2  mov     rcx, [rbp+58h]; this
0x18010bfd6  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010bfdd  mov     edx, 11Dh; void *
0x18010bfe2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010bfe8  xor     edi, edi
0x18010bfea  mov     [rbp+50h+var_48], rdi
0x18010bfee  mov     r14, 0FFFFFFFFFFFFFF0h
0x18010bff8  mov     r9d, [rbp+50h+var_50]
0x18010bffc  mov     esi, 80h
0x18010c001  cmp     r9d, esi
0x18010c004  jbe     short loc_18010C01E
0x18010c006  mov     ecx, r9d; unsigned __int64
0x18010c009  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010c00e  mov     rdi, rax
0x18010c011  mov     [rbp+50h+var_48], rax
0x18010c015  mov     rbx, rax
0x18010c018  mov     r9d, [rbp+50h+var_50]
0x18010c01c  jmp     short loc_18010C03E
0x18010c01e  lea     rcx, [r9+0Fh]
0x18010c022  cmp     rcx, r9
0x18010c025  ja      short loc_18010C02A
0x18010c027  mov     rcx, r14
0x18010c02a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18010c02e  mov     rax, rcx
0x18010c031  call    _alloca_probe
0x18010c036  sub     rsp, rcx
0x18010c039  lea     rbx, [rsp+80h+var_50]
0x18010c03e  lea     rax, [rbp+50h+var_50]
0x18010c042  mov     qword ptr [rsp+80h+ReturnLength], rax; ReturnLength
0x18010c047  mov     r8, rbx; TokenInformation
0x18010c04a  mov     edx, 1; TokenInformationClass
0x18010c04f  mov     rcx, r15; TokenHandle
0x18010c052  call    cs:__imp_GetTokenInformation
0x18010c058  test    eax, eax
0x18010c05a  jnz     short loc_18010C072
0x18010c05c  mov     rcx, [rbp+58h]; this
0x18010c060  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010c067  mov     edx, 130h; void *
0x18010c06c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010c072  mov     rdx, [rbx]; void *
0x18010c075  mov     rcx, r12; pSecurityDescriptor
0x18010c078  call    ?SetOwner@CSecurityDescriptor@SecUtil@@QEAAXPEAXH@Z; SecUtil::CSecurityDescriptor::SetOwner(void *,int)
0x18010c07d  mov     [rbp+50h+var_50], 0
0x18010c084  lea     rax, [rbp+50h+var_50]
0x18010c088  mov     qword ptr [rsp+80h+ReturnLength], rax; int
0x18010c08d  xor     r9d, r9d; TokenInformationLength
0x18010c090  xor     r8d, r8d; TokenInformation
0x18010c093  lea     edx, [r9+5]; TokenInformationClass
0x18010c097  mov     rcx, r15; TokenHandle
0x18010c09a  call    cs:__imp_GetTokenInformation
0x18010c0a0  test    eax, eax
0x18010c0a2  jz      short loc_18010C0C0
0x18010c0a4  mov     rcx, [rbp+58h]; this
0x18010c0a8  mov     r9d, 8000FFFFh; char *
0x18010c0ae  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010c0b5  mov     edx, 13Ch; void *
0x18010c0ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010c0c0  call    cs:__imp_GetLastError
0x18010c0c6  cmp     eax, 7Ah ; 'z'
0x18010c0c9  jz      short loc_18010C0E1
0x18010c0cb  mov     rcx, [rbp+58h]; this
0x18010c0cf  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010c0d6  mov     edx, 141h; void *
0x18010c0db  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010c0e1  xor     ebx, ebx
0x18010c0e3  mov     [rbp+50h+var_40], rbx
0x18010c0e7  mov     r9d, [rbp+50h+var_50]
0x18010c0eb  cmp     r9d, esi
0x18010c0ee  jbe     short loc_18010C10B
0x18010c0f0  mov     ecx, r9d; unsigned __int64
0x18010c0f3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010c0f8  mov     rbx, rax
0x18010c0fb  mov     [rbp+50h+var_40], rax
0x18010c0ff  mov     rsi, rax
0x18010c102  mov     r14, rax
0x18010c105  mov     r9d, [rbp+50h+var_50]
0x18010c109  jmp     short loc_18010C12E
0x18010c10b  lea     rcx, [r9+0Fh]
0x18010c10f  cmp     rcx, r9
0x18010c112  ja      short loc_18010C117
0x18010c114  mov     rcx, r14
0x18010c117  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18010c11b  mov     rax, rcx
0x18010c11e  call    _alloca_probe
0x18010c123  sub     rsp, rcx
0x18010c126  lea     rsi, [rsp+80h+var_50]
0x18010c12b  xor     r14d, r14d
0x18010c12e  lea     rax, [rbp+50h+var_50]
0x18010c132  mov     qword ptr [rsp+80h+ReturnLength], rax; ReturnLength
0x18010c137  mov     r8, rsi; TokenInformation
0x18010c13a  mov     edx, 5; TokenInformationClass
0x18010c13f  mov     rcx, r15; TokenHandle
0x18010c142  call    cs:__imp_GetTokenInformation
0x18010c148  test    eax, eax
0x18010c14a  jnz     short loc_18010C162
0x18010c14c  mov     rcx, [rbp+58h]; this
0x18010c150  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010c157  mov     edx, 154h; void *
0x18010c15c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010c162  mov     rdx, [rsi]; void *
0x18010c165  mov     rcx, r12; pSecurityDescriptor
0x18010c168  call    ?SetGroup@CSecurityDescriptor@SecUtil@@QEAAXPEAXH@Z; SecUtil::CSecurityDescriptor::SetGroup(void *,int)
0x18010c16d  nop
0x18010c16e  test    r14, r14
0x18010c171  jz      short loc_18010C17C
0x18010c173  mov     rcx, rbx; Block
0x18010c176  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010c17b  nop
0x18010c17c  test    rdi, rdi
0x18010c17f  jz      short loc_18010C189
0x18010c181  mov     rcx, rdi; Block
0x18010c184  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010c189  mov     rcx, [rbp+50h+var_38]
0x18010c18d  xor     rcx, rbp; StackCookie
0x18010c190  call    __security_check_cookie
0x18010c195  lea     rsp, [rbp+20h]
0x18010c199  pop     r15
0x18010c19b  pop     r14
0x18010c19d  pop     r12
0x18010c19f  pop     rdi
0x18010c1a0  pop     rsi
0x18010c1a1  pop     rbx
0x18010c1a2  pop     rbp
0x18010c1a3  retn
```
