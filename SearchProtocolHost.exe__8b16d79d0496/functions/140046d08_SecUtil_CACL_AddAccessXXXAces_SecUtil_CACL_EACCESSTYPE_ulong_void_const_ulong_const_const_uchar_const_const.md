# SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)

- ea: `0x140046d08`
- end: `0x140046e92`
- name: `?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140022778`
- `0x14003a8e8`

## callees

- `0x140005240`
- `0x140005264`
- `0x140005918`
- `0x14000ea6c`
- `0x1400317c8`
- `0x140046d08`
- `0x140046edc`
- `0x140070010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140046dec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140046d6b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140046d6b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140046d89`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140046d89`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140046d5b`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140046d5b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140046e1a`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140046e1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046e33`

## string_xrefs

- `0x140046da0`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x140046e40`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SecUtil::CACL::AddAccessXXXAces(PACL *a1, __int64 a2, __int64 a3, PSID *a4, __int64 a5, _BYTE *a6)
{
  int v8; // ebx
  DWORD v9; // ebx
  struct _ACL *v10; // rsi
  struct _ACL *v11; // r8
  const char *LastError; // r9
  __int64 i; // rbx
  __int64 v14; // r8
  DWORD v15; // eax
  unsigned int v17; // [rsp+20h] [rbp-40h]
  LPVOID pAce; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v19[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v19[1] = -2;
  pAclInformation = 0;
  v21 = 0;
  GetAclInformation(*a1, &pAclInformation, 0xCu, AclSizeInformation);
  v8 = HIDWORD(pAclInformation) + 8;
  v9 = GetLengthSid(*a4) + v8;
  v10 = (struct _ACL *)operator new[](v9);
  v19[0] = v10;
  if ( !InitializeAcl(v10, v9, 2u) )
  {
    LastError = (const char *)GetLastError();
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x366,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      LastError,
      v17);
  }
  SecUtil::AppendACL(v10, *a1, v11);
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    if ( a5 )
      v14 = *(unsigned int *)(a5 + 4 * i);
    else
      v14 = 270467072;
    if ( !(unsigned int)((__int64 (__fastcall *)(struct _ACL *, __int64, __int64, PSID))AddAccessAllowedAce)(
                          v10,
                          2,
                          v14,
                          *a4) )
    {
      v15 = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        (const char *)v15,
        v17);
    }
    if ( a6 && *a6 )
    {
      pAce = 0;
      if ( GetAce(v10, pAclInformation, &pAce) )
        *((_BYTE *)pAce + 1) = *a6;
    }
  }
  operator delete(*a1);
  v19[0] = 0;
  *a1 = v10;
  return TPointer<unsigned char>::~TPointer<unsigned char>(v19);
}

```

## disassembly

```asm
0x140046d08  mov     rax, rsp
0x140046d0b  push    rbp
0x140046d0c  push    rsi
0x140046d0d  push    rdi
0x140046d0e  push    r12
0x140046d10  push    r13
0x140046d12  push    r14
0x140046d14  push    r15
0x140046d16  mov     rbp, rsp
0x140046d19  sub     rsp, 60h
0x140046d1d  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x140046d25  mov     [rax+10h], rbx
0x140046d29  mov     rax, cs:__security_cookie
0x140046d30  xor     rax, rsp
0x140046d33  mov     [rbp+var_8], rax
0x140046d37  mov     r13, r9
0x140046d3a  mov     r14, rcx
0x140046d3d  mov     r12, [rbp+arg_20]
0x140046d41  xor     eax, eax
0x140046d43  mov     [rbp+pAclInformation], rax
0x140046d47  mov     [rbp+var_10], eax
0x140046d4a  lea     edi, [rax+2]
0x140046d4d  mov     r9d, edi; dwAclInformationClass
0x140046d50  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140046d54  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x140046d58  mov     rcx, [rcx]; pAcl
0x140046d5b  call    cs:__imp_GetAclInformation
0x140046d61  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x140046d64  add     ebx, 8
0x140046d67  mov     rcx, [r13+0]; pSid
0x140046d6b  call    cs:__imp_GetLengthSid
0x140046d71  add     ebx, eax
0x140046d73  mov     ecx, ebx; unsigned __int64
0x140046d75  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140046d7a  mov     rsi, rax
0x140046d7d  mov     [rbp+var_28], rax
0x140046d81  mov     r8d, edi; dwAclRevision
0x140046d84  mov     edx, ebx; nAclLength
0x140046d86  mov     rcx, rax; pAcl
0x140046d89  call    cs:__imp_InitializeAcl
0x140046d8f  test    eax, eax
0x140046d91  jnz     short loc_140046DB2
0x140046d93  call    cs:__imp_GetLastError
0x140046d99  mov     r9d, eax; char *
0x140046d9c  mov     rcx, [rbp+38h]; this
0x140046da0  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046da7  mov     edx, 366h; void *
0x140046dac  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140046db2  mov     r15, [rbp+arg_28]
0x140046db6  mov     rdx, [r14]; PACL
0x140046db9  mov     rcx, rsi; pAcl
0x140046dbc  call    ?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z; SecUtil::AppendACL(_ACL *,_ACL *)
0x140046dc1  xor     ebx, ebx
0x140046dc3  cmp     ebx, 1
0x140046dc6  jnb     loc_140046E52
0x140046dcc  mov     edi, ebx
0x140046dce  test    r12, r12
0x140046dd1  jz      short loc_140046DD9
0x140046dd3  mov     r8d, [r12+rbx*4]
0x140046dd7  jmp     short loc_140046DDF
0x140046dd9  mov     r8d, 101F0000h
0x140046ddf  mov     r9, [r13+rdi*8+0]
0x140046de4  mov     edx, 2
0x140046de9  mov     rcx, rsi
0x140046dec  mov     rax, cs:__imp_AddAccessAllowedAce
0x140046df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046df8  test    eax, eax
0x140046dfa  jz      short loc_140046E33
0x140046dfc  test    r15, r15
0x140046dff  jz      short loc_140046E2F
0x140046e01  cmp     byte ptr [r15+rdi], 0
0x140046e06  jz      short loc_140046E2F
0x140046e08  mov     [rbp+pAce], 0
0x140046e10  lea     r8, [rbp+pAce]; pAce
0x140046e14  mov     edx, dword ptr [rbp+pAclInformation]; dwAceIndex
0x140046e17  mov     rcx, rsi; pAcl
0x140046e1a  call    cs:__imp_GetAce
0x140046e20  test    eax, eax
0x140046e22  jz      short loc_140046E2F
0x140046e24  mov     cl, [r15+rdi]
0x140046e28  mov     rax, [rbp+pAce]
0x140046e2c  mov     [rax+1], cl
0x140046e2f  inc     ebx
0x140046e31  jmp     short loc_140046DC3
0x140046e33  call    cs:__imp_GetLastError
0x140046e39  mov     r9d, eax; char *
0x140046e3c  mov     rcx, [rbp+38h]; this
0x140046e40  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046e47  mov     edx, 382h; void *
0x140046e4c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140046e52  mov     rcx, [r14]; Block
0x140046e55  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140046e5a  mov     [rbp+var_28], 0
0x140046e62  mov     [r14], rsi
0x140046e65  lea     rcx, [rbp+var_28]
0x140046e69  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x140046e6e  mov     rcx, [rbp+var_8]
0x140046e72  xor     rcx, rsp; StackCookie
0x140046e75  call    __security_check_cookie
0x140046e7a  mov     rbx, [rsp+60h+arg_8]
0x140046e82  add     rsp, 60h
0x140046e86  pop     r15
0x140046e88  pop     r14
0x140046e8a  pop     r13
0x140046e8c  pop     r12
0x140046e8e  pop     rdi
0x140046e8f  pop     rsi
0x140046e90  pop     rbp
0x140046e91  retn
```
