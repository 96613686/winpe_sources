# SecUtil::AddPrincipalToProcessDacl(void *,void *)

- ea: `0x1800ad4d4`
- end: `0x1800ad6da`
- name: `?AddPrincipalToProcessDacl@SecUtil@@YAJPEAX0@Z`
- size: `518`
- prototype: `int(SecUtil *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad384`

## callees

- `0x18005e788`
- `0x1800ad4d4`
- `0x1801244c0`
- `0x180222f70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad50e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad688`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad504`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ad504`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad531`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad531`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800ad67e`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800ad67e`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1800ad664`
- `api-ms-win-security-base-l1-1-0!IsValidAcl` at `0x1800ad664`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ad634`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800ad634`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800ad657`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800ad657`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ad590`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ad5fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ad590`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ad5fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad55c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad5e0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad55c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad5e0`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800ad61f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800ad61f`

## pseudocode

```c
__int64 __fastcall SecUtil::AddPrincipalToProcessDacl(SecUtil *this, void *a2, void *a3)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  signed int v7; // eax
  DWORD LengthSid; // eax
  DWORD v9; // r9d
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  __int16 v14; // ax
  DWORD v15; // edi
  signed int v16; // eax
  PACL TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+8h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp+10h] BYREF

  TokenHandle = 0;
  if ( !OpenProcessToken(this, 0x88u, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v5;
  }
  LODWORD(TokenInformation) = 0;
  if ( GetTokenInformation(TokenHandle, TokenDefaultDacl, 0, 0, (PDWORD)&TokenInformation) )
    goto LABEL_27;
  v7 = GetLastError();
  v5 = v7;
  if ( v7 != 122 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
LABEL_25:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return v5;
  }
  LengthSid = GetLengthSid(a2);
  v9 = LengthSid + (_DWORD)TokenInformation + 12;
  LODWORD(TokenInformation) = v9;
  v10 = v9 + 15LL;
  if ( v10 <= v9 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  if ( !GetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, v9, (PDWORD)&TokenInformation) )
  {
LABEL_22:
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v5 = v16;
    goto LABEL_25;
  }
  if ( !TokenInformation )
  {
LABEL_27:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 2147500037LL;
  }
  else
  {
    v14 = GetLengthSid(a2);
    TokenInformation->AclSize += v14 + 8;
    v15 = 0;
    pAce = 0;
    while ( GetAce(TokenInformation, v15, &pAce) )
    {
      if ( EqualSid(a2, (char *)pAce + 8) )
      {
        v5 = 0;
        goto LABEL_25;
      }
      ++v15;
    }
    if ( !AddAccessAllowedAce(TokenInformation, 2u, 0x10000000u, a2) )
      goto LABEL_22;
    IsValidAcl(TokenInformation);
    if ( !SetTokenInformation(TokenHandle, TokenDefaultDacl, &TokenInformation, TokenInformation->AclSize) )
      goto LABEL_22;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x1800ad4d4  push    rbp
0x1800ad4d6  push    rbx
0x1800ad4d7  push    rsi
0x1800ad4d8  push    rdi
0x1800ad4d9  sub     rsp, 58h
0x1800ad4dd  lea     rbp, [rsp+30h]
0x1800ad4e2  mov     rax, cs:__security_cookie
0x1800ad4e9  xor     rax, rbp
0x1800ad4ec  mov     [rbp+40h+var_28], rax
0x1800ad4f0  mov     rsi, rdx
0x1800ad4f3  mov     [rbp+40h+TokenHandle], 0
0x1800ad4fb  mov     edx, 88h; DesiredAccess
0x1800ad500  lea     r8, [rbp+40h+TokenHandle]; TokenHandle
0x1800ad504  call    cs:__imp_OpenProcessToken
0x1800ad50a  test    eax, eax
0x1800ad50c  jnz     short loc_1800AD53E
0x1800ad50e  call    cs:__imp_GetLastError
0x1800ad514  mov     ebx, eax
0x1800ad516  test    eax, eax
0x1800ad518  jle     short loc_1800AD523
0x1800ad51a  movzx   ebx, ax
0x1800ad51d  or      ebx, 80070000h
0x1800ad523  mov     rcx, [rbp+40h+TokenHandle]; hObject
0x1800ad527  lea     rdx, [rcx-1]
0x1800ad52b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800ad52f  ja      short loc_1800AD537
0x1800ad531  call    cs:__imp_CloseHandle
0x1800ad537  mov     eax, ebx
0x1800ad539  jmp     loc_1800AD6C5
0x1800ad53e  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800ad542  lea     rax, [rbp+40h+TokenInformation]
0x1800ad546  xor     r9d, r9d; TokenInformationLength
0x1800ad549  mov     dword ptr [rbp+40h+TokenInformation], 0
0x1800ad550  xor     r8d, r8d; TokenInformation
0x1800ad553  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800ad558  lea     edx, [r9+6]; TokenInformationClass
0x1800ad55c  call    cs:__imp_GetTokenInformation
0x1800ad562  test    eax, eax
0x1800ad564  jnz     loc_1800AD6B7
0x1800ad56a  call    cs:__imp_GetLastError
0x1800ad570  mov     ebx, eax
0x1800ad572  cmp     eax, 7Ah ; 'z'
0x1800ad575  jz      short loc_1800AD58D
0x1800ad577  test    eax, eax
0x1800ad579  jle     loc_1800AD69C
0x1800ad57f  movzx   ebx, ax
0x1800ad582  or      ebx, 80070000h
0x1800ad588  jmp     loc_1800AD69C
0x1800ad58d  mov     rcx, rsi; pSid
0x1800ad590  call    cs:__imp_GetLengthSid
0x1800ad596  mov     edx, dword ptr [rbp+40h+TokenInformation]
0x1800ad599  add     edx, 0Ch
0x1800ad59c  add     edx, eax
0x1800ad59e  mov     r9d, edx
0x1800ad5a1  mov     dword ptr [rbp+40h+TokenInformation], edx
0x1800ad5a4  lea     rcx, [rdx+0Fh]
0x1800ad5a8  cmp     rcx, r9
0x1800ad5ab  ja      short loc_1800AD5B7
0x1800ad5ad  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ad5b7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800ad5bb  mov     rax, rcx
0x1800ad5be  call    _alloca_probe
0x1800ad5c3  sub     rsp, rcx
0x1800ad5c6  lea     rax, [rbp+40h+TokenInformation]
0x1800ad5ca  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800ad5ce  mov     edx, 6; TokenInformationClass
0x1800ad5d3  lea     rbx, [rsp+70h+TokenInformation]
0x1800ad5d8  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800ad5dd  mov     r8, rbx; TokenInformation
0x1800ad5e0  call    cs:__imp_GetTokenInformation
0x1800ad5e6  test    eax, eax
0x1800ad5e8  jz      loc_1800AD688
0x1800ad5ee  cmp     qword ptr [rbx], 0
0x1800ad5f2  jz      loc_1800AD6B7
0x1800ad5f8  mov     rcx, rsi; pSid
0x1800ad5fb  call    cs:__imp_GetLengthSid
0x1800ad601  mov     rcx, [rbx]
0x1800ad604  add     ax, 8
0x1800ad608  add     [rcx+2], ax
0x1800ad60c  xor     edi, edi
0x1800ad60e  mov     [rbp+40h+pAce], 0
0x1800ad616  mov     rcx, [rbx]; pAcl
0x1800ad619  lea     r8, [rbp+40h+pAce]; pAce
0x1800ad61d  mov     edx, edi; dwAceIndex
0x1800ad61f  call    cs:__imp_GetAce
0x1800ad625  test    eax, eax
0x1800ad627  jz      short loc_1800AD646
0x1800ad629  mov     rdx, [rbp+40h+pAce]
0x1800ad62d  mov     rcx, rsi; pSid1
0x1800ad630  add     rdx, 8; pSid2
0x1800ad634  call    cs:__imp_EqualSid
0x1800ad63a  test    eax, eax
0x1800ad63c  jnz     short loc_1800AD642
0x1800ad63e  inc     edi
0x1800ad640  jmp     short loc_1800AD616
0x1800ad642  xor     ebx, ebx
0x1800ad644  jmp     short loc_1800AD69C
0x1800ad646  mov     rcx, [rbx]; pAcl
0x1800ad649  mov     r9, rsi; pSid
0x1800ad64c  mov     edx, 2; dwAceRevision
0x1800ad651  mov     r8d, 10000000h; AccessMask
0x1800ad657  call    cs:__imp_AddAccessAllowedAce
0x1800ad65d  test    eax, eax
0x1800ad65f  jz      short loc_1800AD688
0x1800ad661  mov     rcx, [rbx]; pAcl
0x1800ad664  call    cs:__imp_IsValidAcl
0x1800ad66a  mov     rax, [rbx]
0x1800ad66d  mov     r8, rbx; TokenInformation
0x1800ad670  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x1800ad674  mov     edx, 6; TokenInformationClass
0x1800ad679  movzx   r9d, word ptr [rax+2]; TokenInformationLength
0x1800ad67e  call    cs:__imp_SetTokenInformation
0x1800ad684  test    eax, eax
0x1800ad686  jnz     short loc_1800AD6AA
0x1800ad688  call    cs:__imp_GetLastError
0x1800ad68e  test    eax, eax
0x1800ad690  jle     short loc_1800AD69A
0x1800ad692  movzx   eax, ax
0x1800ad695  or      eax, 80070000h
0x1800ad69a  mov     ebx, eax
0x1800ad69c  lea     rcx, [rbp+40h+TokenHandle]
0x1800ad6a0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad6a5  jmp     loc_1800AD537
0x1800ad6aa  lea     rcx, [rbp+40h+TokenHandle]
0x1800ad6ae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad6b3  xor     eax, eax
0x1800ad6b5  jmp     short loc_1800AD6C5
0x1800ad6b7  lea     rcx, [rbp+40h+TokenHandle]
0x1800ad6bb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad6c0  mov     eax, 80004005h
0x1800ad6c5  mov     rcx, [rbp+40h+var_28]
0x1800ad6c9  xor     rcx, rbp; StackCookie
0x1800ad6cc  call    __security_check_cookie
0x1800ad6d1  lea     rsp, [rbp+28h]
0x1800ad6d5  pop     rdi
0x1800ad6d6  pop     rsi
0x1800ad6d7  pop     rbx
0x1800ad6d8  pop     rbp
0x1800ad6d9  retn
```
