# OSIntegration::DEH::CMrtHelpers::_AddAccessAllowedAceToMainPackageRegistryKeyDacl(void *,_ACL *)

- ea: `0x18013e7b0`
- end: `0x18013e9ce`
- name: `?_AddAccessAllowedAceToMainPackageRegistryKeyDacl@CMrtHelpers@DEH@OSIntegration@@AEAAJPEAXPEAU_ACL@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(HANDLE *this, void *, struct _ACL *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18013e2fc`

## callees

- `0x18001f430`
- `0x1800a021c`
- `0x1800a2854`
- `0x1800f0260`
- `0x1800f0700`
- `0x18013e7b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18013e7f7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18013e7f7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18013e8f1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18013e8f1`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18013e881`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18013e910`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18013e881`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18013e910`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013e81e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013e81e`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18013e8a9`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18013e931`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18013e8a9`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18013e931`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18013e858`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18013e858`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18013e978`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18013e978`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::CMrtHelpers::_AddAccessAllowedAceToMainPackageRegistryKeyDacl(
        HANDLE *this,
        void *a2,
        struct _ACL *a3)
{
  const char *v6; // r9
  DWORD LengthSid; // eax
  DWORD v9; // ebx
  struct _ACL *pDacl; // rdi
  const char *v11; // r9
  __int64 v12; // rdx
  DWORD i; // ebx
  unsigned int LastError; // eax
  unsigned int v15; // ebx
  DWORD v16; // eax
  unsigned int nAceListLength; // [rsp+20h] [rbp-60h]
  LPVOID pAce; // [rsp+40h] [rbp-40h] BYREF
  int v19; // [rsp+48h] [rbp-38h] BYREF
  PACL pAcl; // [rsp+50h] [rbp-30h]
  int v21; // [rsp+58h] [rbp-28h]
  __int64 pAclInformation; // [rsp+60h] [rbp-20h] BYREF
  int v23; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  pAclInformation = 0;
  v23 = 0;
  if ( !GetAclInformation(a3, &pAclInformation, 0xCu, AclSizeInformation) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4FA,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
             v6);
  LengthSid = GetLengthSid(a2);
  v9 = LengthSid + HIDWORD(pAclInformation);
  pAcl = 0;
  v19 = 0;
  v21 = 0;
  Common::ByteBuffer::SetLength((Common::ByteBuffer *)&v19, LengthSid + HIDWORD(pAclInformation) + 8);
  pDacl = pAcl;
  if ( !InitializeAcl(pAcl, v9 + 8, 2u) )
  {
    v12 = 1283;
LABEL_13:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
                  v11);
    goto LABEL_14;
  }
  pAce = 0;
  for ( i = 0; i < (unsigned int)pAclInformation; ++i )
  {
    if ( !GetAce(a3, i, &pAce) )
    {
      v12 = 1290;
      goto LABEL_13;
    }
    if ( (*((_BYTE *)pAce + 1) & 0x10) != 0 )
      break;
    if ( !AddAce(pDacl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
    {
      v12 = 1298;
      goto LABEL_13;
    }
  }
  if ( !AddAccessAllowedAceEx(pDacl, 2u, 3u, 0x20019u, a2) )
  {
    v12 = 1301;
    goto LABEL_13;
  }
  while ( i < (unsigned int)pAclInformation )
  {
    if ( !GetAce(a3, i, &pAce) )
    {
      v12 = 1305;
      goto LABEL_13;
    }
    if ( !AddAce(pDacl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
    {
      v12 = 1306;
      goto LABEL_13;
    }
    ++i;
  }
  v16 = SetSecurityInfo(this[1], SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
  if ( !v16 )
  {
    v15 = 0;
    goto LABEL_26;
  }
  LastError = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x51D,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\gdx\\mrthandler.cpp",
                (const char *)v16,
                nAceListLength);
LABEL_14:
  v15 = LastError;
LABEL_26:
  operator delete(pDacl, 1u);
  return v15;
}

```

## disassembly

```asm
0x18013e7b0  push    rbp
0x18013e7b2  push    rbx
0x18013e7b3  push    rsi
0x18013e7b4  push    rdi
0x18013e7b5  push    r13
0x18013e7b7  push    r14
0x18013e7b9  push    r15
0x18013e7bb  mov     rbp, rsp
0x18013e7be  sub     rsp, 80h
0x18013e7c5  mov     rax, cs:__security_cookie
0x18013e7cc  xor     rax, rsp
0x18013e7cf  mov     [rbp+var_10], rax
0x18013e7d3  xor     eax, eax
0x18013e7d5  mov     rsi, r8
0x18013e7d8  mov     r14, rdx
0x18013e7db  mov     [rbp+pAclInformation], rax
0x18013e7df  mov     r15, rcx
0x18013e7e2  mov     [rbp+var_18], eax
0x18013e7e5  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18013e7e9  mov     rcx, rsi; pAcl
0x18013e7ec  lea     r13d, [rax+2]
0x18013e7f0  mov     r9d, r13d; dwAclInformationClass
0x18013e7f3  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18013e7f7  call    cs:__imp_GetAclInformation
0x18013e7fd  test    eax, eax
0x18013e7ff  jnz     short loc_18013E81B
0x18013e801  mov     rcx, [rbp+38h]; this
0x18013e805  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013e80c  mov     edx, 4FAh; void *
0x18013e811  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18013e816  jmp     loc_18013E9B0
0x18013e81b  mov     rcx, r14; pSid
0x18013e81e  call    cs:__imp_GetLengthSid
0x18013e824  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x18013e827  lea     rcx, [rbp+var_38]; this
0x18013e82b  add     ebx, eax
0x18013e82d  mov     [rbp+pAcl], 0
0x18013e835  mov     [rbp+var_38], 0
0x18013e83c  mov     [rbp+var_28], 0
0x18013e843  lea     edx, [rbx+8]; unsigned int
0x18013e846  call    ?SetLength@ByteBuffer@Common@@QEAAJK@Z; Common::ByteBuffer::SetLength(ulong)
0x18013e84b  mov     rdi, [rbp+pAcl]
0x18013e84f  lea     edx, [rbx+8]; nAclLength
0x18013e852  mov     rcx, rdi; pAcl
0x18013e855  mov     r8d, r13d; dwAclRevision
0x18013e858  call    cs:__imp_InitializeAcl
0x18013e85e  test    eax, eax
0x18013e860  jnz     short loc_18013E869
0x18013e862  mov     edx, 503h
0x18013e867  jmp     short loc_18013E8C3
0x18013e869  mov     [rbp+pAce], 0
0x18013e871  xor     ebx, ebx
0x18013e873  cmp     ebx, dword ptr [rbp+pAclInformation]
0x18013e876  jnb     short loc_18013E8DA
0x18013e878  lea     r8, [rbp+pAce]; pAce
0x18013e87c  mov     edx, ebx; dwAceIndex
0x18013e87e  mov     rcx, rsi; pAcl
0x18013e881  call    cs:__imp_GetAce
0x18013e887  test    eax, eax
0x18013e889  jz      short loc_18013E8BE
0x18013e88b  mov     r9, [rbp+pAce]; pAceList
0x18013e88f  test    byte ptr [r9+1], 10h
0x18013e894  jnz     short loc_18013E8DA
0x18013e896  movzx   eax, word ptr [r9+2]
0x18013e89b  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18013e89f  mov     edx, r13d; dwAceRevision
0x18013e8a2  mov     [rsp+80h+nAceListLength], eax; nAceListLength
0x18013e8a6  mov     rcx, rdi; pAcl
0x18013e8a9  call    cs:__imp_AddAce
0x18013e8af  test    eax, eax
0x18013e8b1  jz      short loc_18013E8B7
0x18013e8b3  inc     ebx
0x18013e8b5  jmp     short loc_18013E873
0x18013e8b7  mov     edx, 512h
0x18013e8bc  jmp     short loc_18013E8C3
0x18013e8be  mov     edx, 50Ah; void *
0x18013e8c3  mov     rcx, [rbp+38h]; this
0x18013e8c7  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013e8ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18013e8d3  mov     ebx, eax
0x18013e8d5  jmp     loc_18013E9A1
0x18013e8da  mov     r9d, 20019h; AccessMask
0x18013e8e0  mov     qword ptr [rsp+80h+nAceListLength], r14; pSid
0x18013e8e5  mov     r8d, 3; AceFlags
0x18013e8eb  mov     edx, r13d; dwAceRevision
0x18013e8ee  mov     rcx, rdi; pAcl
0x18013e8f1  call    cs:__imp_AddAccessAllowedAceEx
0x18013e8f7  test    eax, eax
0x18013e8f9  jnz     short loc_18013E902
0x18013e8fb  mov     edx, 515h
0x18013e900  jmp     short loc_18013E8C3
0x18013e902  cmp     ebx, dword ptr [rbp+pAclInformation]
0x18013e905  jnb     short loc_18013E953
0x18013e907  lea     r8, [rbp+pAce]; pAce
0x18013e90b  mov     edx, ebx; dwAceIndex
0x18013e90d  mov     rcx, rsi; pAcl
0x18013e910  call    cs:__imp_GetAce
0x18013e916  test    eax, eax
0x18013e918  jz      short loc_18013E949
0x18013e91a  mov     r9, [rbp+pAce]; pAceList
0x18013e91e  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18013e922  mov     edx, r13d; dwAceRevision
0x18013e925  mov     rcx, rdi; pAcl
0x18013e928  movzx   eax, word ptr [r9+2]
0x18013e92d  mov     [rsp+80h+nAceListLength], eax; nAceListLength
0x18013e931  call    cs:__imp_AddAce
0x18013e937  test    eax, eax
0x18013e939  jz      short loc_18013E93F
0x18013e93b  inc     ebx
0x18013e93d  jmp     short loc_18013E902
0x18013e93f  mov     edx, 51Ah
0x18013e944  jmp     loc_18013E8C3
0x18013e949  mov     edx, 519h
0x18013e94e  jmp     loc_18013E8C3
0x18013e953  mov     rcx, [r15+8]; handle
0x18013e957  xor     r9d, r9d; psidOwner
0x18013e95a  mov     [rsp+80h+pSacl], 0; pSacl
0x18013e963  mov     [rsp+80h+pDacl], rdi; pDacl
0x18013e968  mov     qword ptr [rsp+80h+nAceListLength], 0; unsigned int
0x18013e971  lea     edx, [r9+4]; ObjectType
0x18013e975  mov     r8d, edx; SecurityInfo
0x18013e978  call    cs:__imp_SetSecurityInfo
0x18013e97e  test    eax, eax
0x18013e980  jz      short loc_18013E99F
0x18013e982  mov     rcx, [rbp+38h]; this
0x18013e986  lea     r8, aOnecoreAdminAp_34; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18013e98d  mov     r9d, eax; char *
0x18013e990  mov     edx, 51Dh; void *
0x18013e995  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013e99a  jmp     loc_18013E8D3
0x18013e99f  xor     ebx, ebx
0x18013e9a1  mov     edx, 1; unsigned __int64
0x18013e9a6  mov     rcx, rdi; void *
0x18013e9a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18013e9ae  mov     eax, ebx
0x18013e9b0  mov     rcx, [rbp+var_10]
0x18013e9b4  xor     rcx, rsp; StackCookie
0x18013e9b7  call    __security_check_cookie
0x18013e9bc  add     rsp, 80h
0x18013e9c3  pop     r15
0x18013e9c5  pop     r14
0x18013e9c7  pop     r13
0x18013e9c9  pop     rdi
0x18013e9ca  pop     rsi
0x18013e9cb  pop     rbx
0x18013e9cc  pop     rbp
0x18013e9cd  retn
```
