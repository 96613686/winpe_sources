# SecUtil::AddAdministratorsToProcessDacl(void *)

- ea: `0x1800ad384`
- end: `0x1800ad4ce`
- name: `?AddAdministratorsToProcessDacl@SecUtil@@YAJPEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(SecUtil *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002538c`

## callees

- `0x1800ad360`
- `0x1800ad384`
- `0x1800ad4d4`
- `0x1801249b0`
- `0x180124d00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ad3e7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ad45e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ad3e7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800ad45e`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ad3bf`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ad43a`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ad3bf`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x1800ad43a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ad3a2`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ad41d`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ad3a2`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x1800ad41d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SecUtil::AddAdministratorsToProcessDacl(SecUtil *this, void *a2)
{
  void *v3; // rbx
  DWORD SidLengthRequired; // eax
  void *v5; // rdi
  __int64 v6; // rsi
  DWORD v7; // ebx
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  void *v10; // rdi
  void *v11; // r8
  DWORD v12; // edi
  int v13; // esi
  void *v14; // r8
  const ATL::CAtlException *v16; // [rsp+20h] [rbp-28h] BYREF
  void *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF
  void *v19; // [rsp+60h] [rbp+18h]

  v3 = 0;
  v19 = 0;
  v18 = 0;
  SidLengthRequired = GetSidLengthRequired(2u);
  try
  {
    v5 = operator new[](SidLengthRequired);
    if ( InitializeSid(v5, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_EveryoneAccount::s_sia.SubAuthority, 2u) )
    {
      v6 = 0;
      do
      {
        v7 = *(&SecUtil::CSID_AdministratorsGroup::s_rgSubAuth + v6);
        *GetSidSubAuthority(v5, v6) = v7;
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < 2 );
      v3 = v5;
      v18 = 0;
      v19 = v5;
      TPointer<unsigned char>::~TPointer<unsigned char>(&v18);
    }
    else
    {
      operator delete(v5);
    }
    v18 = 0;
    v8 = GetSidLengthRequired(1u);
    v9 = operator new[](v8);
    if ( InitializeSid(v9, (PSID_IDENTIFIER_AUTHORITY)SecUtil::CSID_NetworkServiceAccount::s_sia.SubAuthority, 1u) )
    {
      v12 = SecUtil::CSID_SystemAccount::s_rgSubAuth;
      *GetSidSubAuthority(v9, 0) = v12;
      v18 = 0;
      v10 = v9;
      TPointer<unsigned char>::~TPointer<unsigned char>(&v18);
    }
    else
    {
      v10 = 0;
      operator delete(v9);
    }
    v13 = SecUtil::AddPrincipalToProcessDacl(this, v3, v11);
    if ( v13 >= 0 )
      v13 = SecUtil::AddPrincipalToProcessDacl(this, v10, v14);
    if ( v10 )
      operator delete(v10);
    if ( v3 )
      operator delete(v3);
  }
  catch ( const ATL::CAtlException *v16 )
  {
    return *(unsigned int *)v16;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      465,
      "onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx");
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800ad384  mov     [rsp+arg_0], rbx
0x1800ad389  push    rsi
0x1800ad38a  push    rdi
0x1800ad38b  push    r14
0x1800ad38d  sub     rsp, 30h
0x1800ad391  mov     r14, rcx
0x1800ad394  xor     ebx, ebx
0x1800ad396  mov     [rsp+48h+arg_10], rbx
0x1800ad39b  mov     [rsp+48h+arg_8], rbx
0x1800ad3a0  mov     cl, 2; nSubAuthorityCount
0x1800ad3a2  call    cs:__imp_GetSidLengthRequired
0x1800ad3a8  mov     ecx, eax; unsigned __int64
0x1800ad3aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ad3af  mov     rdi, rax
0x1800ad3b2  mov     r8b, 2; nSubAuthorityCount
0x1800ad3b5  lea     rdx, ?s_sia@CSID_EveryoneAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ad3bc  mov     rcx, rax; Sid
0x1800ad3bf  call    cs:__imp_InitializeSid
0x1800ad3c5  test    eax, eax
0x1800ad3c7  jnz     short loc_1800AD3D6
0x1800ad3c9  lea     edx, [rbx+1]
0x1800ad3cc  mov     rcx, rdi; Block
0x1800ad3cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad3d4  jmp     short loc_1800AD412
0x1800ad3d6  xor     esi, esi
0x1800ad3d8  lea     rbx, ?s_rgSubAuth@CSID_AdministratorsGroup@SecUtil@@0PAKA; ulong near * SecUtil::CSID_AdministratorsGroup::s_rgSubAuth
0x1800ad3df  mov     ebx, [rbx+rsi*4]
0x1800ad3e2  mov     edx, esi; nSubAuthority
0x1800ad3e4  mov     rcx, rdi; pSid
0x1800ad3e7  call    cs:__imp_GetSidSubAuthority
0x1800ad3ed  mov     [rax], ebx
0x1800ad3ef  inc     esi
0x1800ad3f1  cmp     esi, 2
0x1800ad3f4  jb      short loc_1800AD3D8
0x1800ad3f6  mov     rbx, rdi
0x1800ad3f9  mov     [rsp+48h+arg_8], 0
0x1800ad402  mov     [rsp+48h+arg_10], rbx
0x1800ad407  lea     rcx, [rsp+48h+arg_8]
0x1800ad40c  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ad411  nop
0x1800ad412  mov     [rsp+48h+arg_8], 0
0x1800ad41b  mov     cl, 1; nSubAuthorityCount
0x1800ad41d  call    cs:__imp_GetSidLengthRequired
0x1800ad423  mov     ecx, eax; unsigned __int64
0x1800ad425  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800ad42a  mov     rsi, rax
0x1800ad42d  mov     r8b, 1; nSubAuthorityCount
0x1800ad430  lea     rdx, ?s_sia@CSID_NetworkServiceAccount@SecUtil@@0U_SID_IDENTIFIER_AUTHORITY@@A.SubAuthority; pIdentifierAuthority
0x1800ad437  mov     rcx, rax; Sid
0x1800ad43a  call    cs:__imp_InitializeSid
0x1800ad440  test    eax, eax
0x1800ad442  jnz     short loc_1800AD453
0x1800ad444  xor     edi, edi
0x1800ad446  lea     edx, [rax+1]
0x1800ad449  mov     rcx, rsi; Block
0x1800ad44c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad451  jmp     short loc_1800AD47C
0x1800ad453  mov     edi, cs:?s_rgSubAuth@CSID_SystemAccount@SecUtil@@0PAKA; ulong near * SecUtil::CSID_SystemAccount::s_rgSubAuth
0x1800ad459  xor     edx, edx; nSubAuthority
0x1800ad45b  mov     rcx, rsi; pSid
0x1800ad45e  call    cs:__imp_GetSidSubAuthority
0x1800ad464  mov     [rax], edi
0x1800ad466  mov     [rsp+48h+arg_8], 0
0x1800ad46f  mov     rdi, rsi
0x1800ad472  lea     rcx, [rsp+48h+arg_8]
0x1800ad477  call    ??1?$TPointer@E@@QEAA@XZ; TPointer<uchar>::~TPointer<uchar>(void)
0x1800ad47c  mov     rdx, rbx; void *
0x1800ad47f  mov     rcx, r14; this
0x1800ad482  call    ?AddPrincipalToProcessDacl@SecUtil@@YAJPEAX0@Z; SecUtil::AddPrincipalToProcessDacl(void *,void *)
0x1800ad487  mov     esi, eax
0x1800ad489  test    eax, eax
0x1800ad48b  js      short loc_1800AD49A
0x1800ad48d  mov     rdx, rdi; void *
0x1800ad490  mov     rcx, r14; this
0x1800ad493  call    ?AddPrincipalToProcessDacl@SecUtil@@YAJPEAX0@Z; SecUtil::AddPrincipalToProcessDacl(void *,void *)
0x1800ad498  mov     esi, eax
0x1800ad49a  test    rdi, rdi
0x1800ad49d  jz      short loc_1800AD4A8
0x1800ad49f  mov     rcx, rdi; Block
0x1800ad4a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad4a7  nop
0x1800ad4a8  test    rbx, rbx
0x1800ad4ab  jz      short loc_1800AD4B6
0x1800ad4ad  mov     rcx, rbx; Block
0x1800ad4b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad4b5  nop
0x1800ad4b6  jmp     short loc_1800AD4BE
0x1800ad4b8  jmp     short $+2
0x1800ad4ba  mov     esi, dword ptr [rsp+48h+arg_8]
0x1800ad4be  mov     eax, esi
0x1800ad4c0  mov     rbx, [rsp+48h+arg_0]
0x1800ad4c5  add     rsp, 30h
0x1800ad4c9  pop     r14
0x1800ad4cb  pop     rdi
0x1800ad4cc  pop     rsi
0x1800ad4cd  retn
```
