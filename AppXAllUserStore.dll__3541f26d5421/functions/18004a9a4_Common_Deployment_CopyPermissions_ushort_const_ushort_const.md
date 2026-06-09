# Common::Deployment::CopyPermissions(ushort const *,ushort const *)

- ea: `0x18004a9a4`
- end: `0x18004ab50`
- name: `?CopyPermissions@Deployment@Common@@YAJPEBG0@Z`
- size: `428`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, LPWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18004ae14`

## callees

- `0x180018248`
- `0x180019e48`
- `0x180019eb4`
- `0x18001a604`
- `0x180020248`
- `0x180020290`
- `0x180020bb4`
- `0x1800475f0`
- `0x18004a9a4`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18004aaa6`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18004aaa6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004ab04`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004ab04`

## string_xrefs

- `0x18004a9e0`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`
- `0x18004aa3a`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`
- `0x18004aab7`: `onecore\admin\appmodel\common\hardlinkdirectorytree.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::CopyPermissions(LPCWSTR pObjectName, LPWSTR a2, const unsigned __int16 *a3)
{
  int v5; // eax
  int v6; // ebx
  __int64 v8; // rdx
  DWORD NamedSecurityInfoW; // eax
  __int64 v10; // rdx
  int ppsidGroup; // [rsp+20h] [rbp-60h]
  unsigned int ppsidGroupa; // [rsp+20h] [rbp-60h]
  PACL pDacl; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v14[2]; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle[2]; // [rsp+58h] [rbp-28h] BYREF
  char v16; // [rsp+68h] [rbp-18h]
  char v17; // [rsp+70h] [rbp-10h]
  __int64 v18; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  PSECURITY_DESCRIPTOR P; // [rsp+B0h] [rbp+30h] BYREF
  PACL pSacl; // [rsp+B8h] [rbp+38h] BYREF

  v14[0] = 0;
  v14[1] = 0;
  v5 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v14, a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
      (const char *)(unsigned int)v5,
      ppsidGroup);
LABEL_3:
    if ( LODWORD(v14[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v14);
    return (unsigned int)v6;
  }
  v16 = 0;
  v17 = 0;
  v18 = 0;
  *(_OWORD *)TokenHandle = 0;
  v6 = Common::Deployment::Privilege::Initialize(TokenHandle, 8);
  if ( v6 < 0 )
  {
    v8 = 26;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
      (const char *)(unsigned int)v6,
      ppsidGroup);
LABEL_9:
    Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
    goto LABEL_3;
  }
  v6 = Common::Deployment::Privilege::Enable((Common::Deployment::Privilege *)TokenHandle);
  if ( v6 < 0 )
  {
    v8 = 27;
    goto LABEL_8;
  }
  pDacl = 0;
  pSacl = 0;
  P = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x1Cu, 0, 0, &pDacl, &pSacl, &P);
  if ( NamedSecurityInfoW )
  {
    v10 = 41;
LABEL_14:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\admin\\appmodel\\common\\hardlinkdirectorytree.cpp",
           (const char *)NamedSecurityInfoW,
           ppsidGroupa);
    AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(P);
    goto LABEL_9;
  }
  if ( pDacl || pSacl )
  {
    NamedSecurityInfoW = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 0x1Cu, 0, 0, pDacl, pSacl);
    if ( NamedSecurityInfoW )
    {
      v10 = 51;
      goto LABEL_14;
    }
  }
  AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(P);
  Common::Deployment::Privilege::~Privilege((Common::Deployment::Privilege *)TokenHandle);
  if ( LODWORD(v14[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v14);
  return 0;
}

```

## disassembly

```asm
0x18004a9a4  mov     [rsp-18h+arg_0], rbx
0x18004a9a9  mov     [rsp-18h+arg_8], rsi
0x18004a9ae  push    rbp
0x18004a9af  push    rdi
0x18004a9b0  push    r14
0x18004a9b2  mov     rbp, rsp
0x18004a9b5  sub     rsp, 80h
0x18004a9bc  mov     rdi, rcx
0x18004a9bf  xor     r14d, r14d
0x18004a9c2  lea     rcx, [rbp+var_38]; this
0x18004a9c6  mov     [rbp+var_38], r14
0x18004a9ca  mov     [rbp+var_30], r14
0x18004a9ce  mov     rsi, rdx
0x18004a9d1  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18004a9d6  mov     ebx, eax
0x18004a9d8  test    eax, eax
0x18004a9da  jns     short loc_18004AA09
0x18004a9dc  mov     rcx, [rbp+18h]; this
0x18004a9e0  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004a9e7  mov     r9d, eax; char *
0x18004a9ea  lea     edx, [r14+16h]; void *
0x18004a9ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a9f3  cmp     dword ptr [rbp+var_38], r14d
0x18004a9f7  jz      short loc_18004AA02
0x18004a9f9  lea     rcx, [rbp+var_38]; this
0x18004a9fd  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18004aa02  mov     eax, ebx
0x18004aa04  jmp     loc_18004AB38
0x18004aa09  xorps   xmm0, xmm0
0x18004aa0c  mov     [rbp+var_18], r14b
0x18004aa10  mov     edx, 8; int
0x18004aa15  mov     [rbp+var_10], r14b
0x18004aa19  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x18004aa1d  mov     [rbp+var_8], r14
0x18004aa21  movdqu  xmmword ptr [rbp+TokenHandle], xmm0
0x18004aa26  call    ?Initialize@Privilege@Deployment@Common@@QEAAJJ@Z; Common::Deployment::Privilege::Initialize(long)
0x18004aa2b  mov     ebx, eax
0x18004aa2d  test    eax, eax
0x18004aa2f  jns     short loc_18004AA54
0x18004aa31  mov     edx, 1Ah; void *
0x18004aa36  mov     rcx, [rbp+18h]; this
0x18004aa3a  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004aa41  mov     r9d, ebx; char *
0x18004aa44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aa49  lea     rcx, [rbp+TokenHandle]; this
0x18004aa4d  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18004aa52  jmp     short loc_18004A9F3
0x18004aa54  lea     rcx, [rbp+TokenHandle]; this
0x18004aa58  call    ?Enable@Privilege@Deployment@Common@@QEAAJXZ; Common::Deployment::Privilege::Enable(void)
0x18004aa5d  mov     ebx, eax
0x18004aa5f  test    eax, eax
0x18004aa61  jns     short loc_18004AA6A
0x18004aa63  mov     edx, 1Bh
0x18004aa68  jmp     short loc_18004AA36
0x18004aa6a  lea     rax, [rbp+P]
0x18004aa6e  mov     [rbp+pDacl], r14
0x18004aa72  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18004aa77  xor     r9d, r9d; ppsidOwner
0x18004aa7a  lea     rax, [rbp+pSacl]
0x18004aa7e  mov     [rbp+pSacl], r14
0x18004aa82  mov     [rsp+80h+ppSacl], rax; ppSacl
0x18004aa87  mov     rcx, rdi; pObjectName
0x18004aa8a  lea     rax, [rbp+pDacl]
0x18004aa8e  mov     [rbp+P], r14
0x18004aa92  lea     ebx, [r9+1Ch]
0x18004aa96  mov     [rsp+80h+ppDacl], rax; ppDacl
0x18004aa9b  mov     r8d, ebx; SecurityInfo
0x18004aa9e  mov     [rsp+80h+ppsidGroup], r14; unsigned int
0x18004aaa3  lea     edx, [rbx-1Bh]; ObjectType
0x18004aaa6  call    cs:__imp_GetNamedSecurityInfoW
0x18004aaac  test    eax, eax
0x18004aaae  jz      short loc_18004AAD6
0x18004aab0  lea     edx, [rbx+0Dh]; void *
0x18004aab3  mov     rcx, [rbp+18h]; this
0x18004aab7  lea     r8, aOnecoreAdminAp_24; "onecore\\admin\\appmodel\\common\\hardl"...
0x18004aabe  mov     r9d, eax; char *
0x18004aac1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004aac6  mov     rcx, [rbp+P]; P
0x18004aaca  mov     ebx, eax
0x18004aacc  call    ??$AutoPtrRtlHeapDeallocate@U_SECURITY_DESCRIPTOR@@@@YAXPEAU_SECURITY_DESCRIPTOR@@@Z; AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(_SECURITY_DESCRIPTOR *)
0x18004aad1  jmp     loc_18004AA49
0x18004aad6  mov     rcx, [rbp+pDacl]
0x18004aada  mov     rax, [rbp+pSacl]
0x18004aade  test    rcx, rcx
0x18004aae1  jnz     short loc_18004AAE8
0x18004aae3  test    rax, rax
0x18004aae6  jz      short loc_18004AB15
0x18004aae8  mov     [rsp+80h+ppSacl], rax; pSacl
0x18004aaed  xor     r9d, r9d; psidOwner
0x18004aaf0  mov     [rsp+80h+ppDacl], rcx; pDacl
0x18004aaf5  mov     r8d, ebx; SecurityInfo
0x18004aaf8  mov     rcx, rsi; pObjectName
0x18004aafb  mov     [rsp+80h+ppsidGroup], r14; psidGroup
0x18004ab00  lea     edx, [r9+1]; ObjectType
0x18004ab04  call    cs:__imp_SetNamedSecurityInfoW
0x18004ab0a  test    eax, eax
0x18004ab0c  jz      short loc_18004AB15
0x18004ab0e  mov     edx, 33h ; '3'
0x18004ab13  jmp     short loc_18004AAB3
0x18004ab15  mov     rcx, [rbp+P]; P
0x18004ab19  call    ??$AutoPtrRtlHeapDeallocate@U_SECURITY_DESCRIPTOR@@@@YAXPEAU_SECURITY_DESCRIPTOR@@@Z; AutoPtrRtlHeapDeallocate<_SECURITY_DESCRIPTOR>(_SECURITY_DESCRIPTOR *)
0x18004ab1e  lea     rcx, [rbp+TokenHandle]; this
0x18004ab22  call    ??1Privilege@Deployment@Common@@QEAA@XZ; Common::Deployment::Privilege::~Privilege(void)
0x18004ab27  cmp     dword ptr [rbp+var_38], r14d
0x18004ab2b  jz      short loc_18004AB36
0x18004ab2d  lea     rcx, [rbp+var_38]; this
0x18004ab31  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18004ab36  xor     eax, eax
0x18004ab38  lea     r11, [rsp+80h+var_s0]
0x18004ab40  mov     rbx, [r11+20h]
0x18004ab44  mov     rsi, [r11+28h]
0x18004ab48  mov     rsp, r11
0x18004ab4b  pop     r14
0x18004ab4d  pop     rdi
0x18004ab4e  pop     rbp
0x18004ab4f  retn
```
