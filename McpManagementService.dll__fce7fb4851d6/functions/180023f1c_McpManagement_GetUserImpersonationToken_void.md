# McpManagement::GetUserImpersonationToken(void * *)

- ea: `0x180023f1c`
- end: `0x1800242ea`
- name: `?GetUserImpersonationToken@McpManagement@@YAJPEAPEAX@Z`
- size: `974`
- prototype: `__int64 __fastcall(PHANDLE phNewToken, void **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180022580`
- `0x180022e80`

## callees

- `0x180003eb4`
- `0x180004970`
- `0x18000c4cc`
- `0x180012684`
- `0x1800126c8`
- `0x1800176f4`
- `0x18001b0ac`
- `0x18001b0e8`
- `0x18001dae4`
- `0x18001e418`
- `0x18001e470`
- `0x180023d44`
- `0x180023e78`
- `0x180023f1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023f30`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180023f30`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f84`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f9c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f84`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180023f9c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024175`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024175`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002419f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002419f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180024002`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180024002`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180024099`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180024099`

## string_xrefs

- `0x180023f64`: `Failed to GetUserSidRaw.`
- `0x180024113`: `Failed to get token information`
- `0x1800240aa`: `Failed to Query the User Token from UMgr`
- `0x180024253`: `Couldn't get an Impersonation User Token from UMgr`
- `0x1800241ae`: `Failed to Duplicate Token to impersonation token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall McpManagement::GetUserImpersonationToken(PHANDLE phNewToken, void **a2)
{
  HRESULT v3; // eax
  int UserSidRaw; // ebx
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int i; // edi
  int v9; // ebx
  int token_information; // ebx
  void *v11; // rbx
  unsigned int LastErrorMsg; // edi
  const char *v13; // r9
  __int64 v14; // rdx
  TOKEN_TYPE TokenType[2]; // [rsp+20h] [rbp-38h]
  PHANDLE phNewTokena; // [rsp+28h] [rbp-30h]
  HANDLE hExistingToken; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v20; // [rsp+68h] [rbp+10h] BYREF
  PSID pSid2; // [rsp+70h] [rbp+18h] BYREF
  __int64 v22; // [rsp+78h] [rbp+20h] BYREF

  pSid2 = 0;
  v3 = CoImpersonateClient();
  if ( v3 < 0 )
  {
    try
    {
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
        (const char *)(unsigned int)v3,
        TokenType[0]);
    }
    catch ( ... )
    {
      *(_DWORD *)(v14 + 104) = wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x57,
                                 (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                                 v13);
      return v20;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &pSid2,
    0);
  UserSidRaw = PrintCore::TokenHelpers::GetUserSidRaw(&pSid2);
  if ( UserSidRaw >= 0 )
  {
    CoRevertToSelf();
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      v20 = 0;
      v22 = 0;
      v6 = UMgrEnumerateSessionUsers(&v20, &v22);
      if ( v6 >= 0 )
      {
        v7 = v20;
        if ( v20 && v22 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v7 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x55,
                (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                (const char *)0x80070520LL,
                (int)"Couldn't get an Impersonation User Token from UMgr",
                (const char *)phNewTokena);
              wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
              return 2147943712LL;
            }
            hExistingToken = 0;
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &hExistingToken,
              0);
            v9 = UMgrQueryUserToken(*(_QWORD *)(v22 + 16LL * i), &hExistingToken);
            if ( v9 < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x46,
                (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                (const char *)(unsigned int)v9,
                (int)"Failed to Query the User Token from UMgr",
                (const char *)phNewTokena);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
              wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
              return (unsigned int)v9;
            }
            Block = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, hExistingToken);
            if ( token_information < 0 )
            {
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                (void *)0x49,
                (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                (const char *)(unsigned int)token_information,
                (int)"Failed to get token information",
                (const char *)phNewTokena);
              if ( Block )
                operator delete(Block);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
              wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
              return (unsigned int)token_information;
            }
            v11 = Block;
            if ( EqualSid(*(PSID *)Block, pSid2) )
              break;
            if ( v11 )
              operator delete(v11);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
            v7 = v20;
          }
          if ( DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
          {
            if ( v11 )
              operator delete(v11);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
            wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
            return 0;
          }
          else
          {
            LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                             retaddr,
                             (void *)0x4F,
                             (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
                             "Failed to Duplicate Token to impersonation token.",
                             *(const char **)TokenType);
            if ( v11 )
              operator delete(v11);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
            wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
            return LastErrorMsg;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41,
            (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
            (const char *)0x80070520LL,
            TokenType[0]);
          wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
          return 2147943712LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x40,
          (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
          (const char *)(unsigned int)v6,
          (int)"Failed to Enumerate SessionUsers from UMgr",
          (const char *)phNewTokena);
        wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v22);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
        return (unsigned int)v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
        (const char *)0x8000FFFFLL,
        (int)"IsUMgrEnumerateSessionUsersPresent is not present on this SKU",
        (const char *)phNewTokena);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
      return 2147549183LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x35,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\utils.cpp",
      (const char *)(unsigned int)UserSidRaw,
      (int)"Failed to GetUserSidRaw.",
      (const char *)phNewTokena);
    CoRevertToSelf();
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSid2);
    return (unsigned int)UserSidRaw;
  }
}

```

## disassembly

```asm
0x180023f1c  push    rbx
0x180023f1e  push    rsi
0x180023f1f  push    rdi
0x180023f20  sub     rsp, 40h
0x180023f24  mov     rsi, rcx
0x180023f27  mov     [rsp+58h+pSid2], 0
0x180023f30  call    cs:__imp_CoImpersonateClient
0x180023f36  mov     rcx, [rsp+58h]; this
0x180023f3b  test    eax, eax
0x180023f3d  js      loc_1800242D4
0x180023f43  xor     edx, edx
0x180023f45  lea     rcx, [rsp+58h+pSid2]
0x180023f4a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180023f4f  lea     rcx, [rsp+58h+pSid2]; void **
0x180023f54  call    ?GetUserSidRaw@TokenHelpers@PrintCore@@SAJPEAPEAX@Z; PrintCore::TokenHelpers::GetUserSidRaw(void * *)
0x180023f59  mov     ebx, eax
0x180023f5b  test    eax, eax
0x180023f5d  jns     short loc_180023F9C
0x180023f5f  mov     rcx, [rsp+58h]; this
0x180023f64  lea     rax, aFailedToGetuse; "Failed to GetUserSidRaw."
0x180023f6b  mov     qword ptr [rsp+58h+TokenType], rax; int
0x180023f70  mov     r9d, ebx; char *
0x180023f73  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023f7a  mov     edx, 35h ; '5'; void *
0x180023f7f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023f84  call    cs:__imp_CoRevertToSelf
0x180023f8a  nop
0x180023f8b  lea     rcx, [rsp+58h+pSid2]
0x180023f90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023f95  mov     eax, ebx
0x180023f97  jmp     loc_1800242CC
0x180023f9c  call    cs:__imp_CoRevertToSelf
0x180023fa2  call    IsUMgrEnumerateSessionUsersPresent
0x180023fa7  test    al, al
0x180023fa9  jnz     short loc_180023FE7
0x180023fab  mov     rcx, [rsp+58h]; this
0x180023fb0  lea     rax, aIsumgrenumerat; "IsUMgrEnumerateSessionUsersPresent is n"...
0x180023fb7  mov     qword ptr [rsp+58h+TokenType], rax; int
0x180023fbc  mov     ebx, 8000FFFFh
0x180023fc1  mov     r9d, ebx; char *
0x180023fc4  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023fcb  mov     edx, 3Ah ; ':'; void *
0x180023fd0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180023fd5  nop
0x180023fd6  lea     rcx, [rsp+58h+pSid2]
0x180023fdb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180023fe0  mov     eax, ebx
0x180023fe2  jmp     loc_1800242CC
0x180023fe7  mov     [rsp+58h+arg_8], 0
0x180023fef  mov     [rsp+58h+arg_18], 0
0x180023ff8  lea     rdx, [rsp+58h+arg_18]
0x180023ffd  lea     rcx, [rsp+58h+arg_8]
0x180024002  call    cs:__imp_UMgrEnumerateSessionUsers
0x180024008  mov     ebx, eax
0x18002400a  test    eax, eax
0x18002400c  jns     short loc_18002404F
0x18002400e  mov     rcx, [rsp+58h]; this
0x180024013  lea     rax, aFailedToEnumer; "Failed to Enumerate SessionUsers from U"...
0x18002401a  mov     qword ptr [rsp+58h+TokenType], rax; int
0x18002401f  mov     r9d, ebx; char *
0x180024022  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180024029  mov     edx, 40h ; '@'; void *
0x18002402e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024033  lea     rcx, [rsp+58h+arg_18]
0x180024038  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18002403d  nop
0x18002403e  lea     rcx, [rsp+58h+pSid2]
0x180024043  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024048  mov     eax, ebx
0x18002404a  jmp     loc_1800242CC
0x18002404f  mov     eax, [rsp+58h+arg_8]
0x180024053  test    eax, eax
0x180024055  jz      loc_180024291
0x18002405b  cmp     [rsp+58h+arg_18], 0
0x180024061  jz      loc_180024291
0x180024067  xor     edi, edi
0x180024069  cmp     edi, eax
0x18002406b  jnb     loc_18002424E
0x180024071  mov     [rsp+58h+hExistingToken], 0
0x18002407a  xor     edx, edx
0x18002407c  lea     rcx, [rsp+58h+hExistingToken]
0x180024081  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024086  mov     eax, edi
0x180024088  add     rax, rax
0x18002408b  lea     rdx, [rsp+58h+hExistingToken]
0x180024090  mov     rcx, [rsp+58h+arg_18]
0x180024095  mov     rcx, [rcx+rax*8]
0x180024099  call    cs:__imp_UMgrQueryUserToken
0x18002409f  mov     ebx, eax
0x1800240a1  test    eax, eax
0x1800240a3  jns     short loc_1800240F0
0x1800240a5  mov     rcx, [rsp+58h]; this
0x1800240aa  lea     rax, aFailedToQueryT; "Failed to Query the User Token from UMg"...
0x1800240b1  mov     qword ptr [rsp+58h+TokenType], rax; int
0x1800240b6  mov     r9d, ebx; char *
0x1800240b9  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800240c0  mov     edx, 46h ; 'F'; void *
0x1800240c5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800240ca  lea     rcx, [rsp+58h+hExistingToken]
0x1800240cf  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800240d4  lea     rcx, [rsp+58h+arg_18]
0x1800240d9  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x1800240de  nop
0x1800240df  lea     rcx, [rsp+58h+pSid2]
0x1800240e4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800240e9  mov     eax, ebx
0x1800240eb  jmp     loc_1800242CC
0x1800240f0  mov     [rsp+58h+Block], 0
0x1800240f9  mov     rdx, [rsp+58h+hExistingToken]
0x1800240fe  lea     rcx, [rsp+58h+Block]
0x180024103  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180024108  mov     ebx, eax
0x18002410a  test    eax, eax
0x18002410c  jns     short loc_180024168
0x18002410e  mov     rcx, [rsp+58h]; this
0x180024113  lea     rax, aFailedToGetTok; "Failed to get token information"
0x18002411a  mov     qword ptr [rsp+58h+TokenType], rax; int
0x18002411f  mov     r9d, ebx; char *
0x180024122  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180024129  mov     edx, 49h ; 'I'; void *
0x18002412e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024133  mov     rcx, [rsp+58h+Block]; Block
0x180024138  test    rcx, rcx
0x18002413b  jz      short loc_180024142
0x18002413d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024142  lea     rcx, [rsp+58h+hExistingToken]
0x180024147  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002414c  lea     rcx, [rsp+58h+arg_18]
0x180024151  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180024156  nop
0x180024157  lea     rcx, [rsp+58h+pSid2]
0x18002415c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024161  mov     eax, ebx
0x180024163  jmp     loc_1800242CC
0x180024168  mov     rdx, [rsp+58h+pSid2]; pSid2
0x18002416d  mov     rbx, [rsp+58h+Block]
0x180024172  mov     rcx, [rbx]; pSid1
0x180024175  call    cs:__imp_EqualSid
0x18002417b  test    eax, eax
0x18002417d  jz      loc_18002422C
0x180024183  mov     [rsp+58h+phNewToken], rsi; phNewToken
0x180024188  mov     r9d, 2; ImpersonationLevel
0x18002418e  mov     [rsp+58h+TokenType], r9d; char *
0x180024193  xor     r8d, r8d; lpTokenAttributes
0x180024196  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18002419a  mov     rcx, [rsp+58h+hExistingToken]; hExistingToken
0x18002419f  call    cs:__imp_DuplicateTokenEx
0x1800241a5  test    eax, eax
0x1800241a7  jnz     short loc_1800241F9
0x1800241a9  mov     rcx, [rsp+58h]; this
0x1800241ae  lea     r9, aFailedToDuplic; "Failed to Duplicate Token to impersonat"...
0x1800241b5  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800241bc  lea     edx, [rax+4Fh]; void *
0x1800241bf  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800241c4  mov     edi, eax
0x1800241c6  test    rbx, rbx
0x1800241c9  jz      short loc_1800241D3
0x1800241cb  mov     rcx, rbx; Block
0x1800241ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800241d3  lea     rcx, [rsp+58h+hExistingToken]
0x1800241d8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800241dd  lea     rcx, [rsp+58h+arg_18]
0x1800241e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x1800241e7  nop
0x1800241e8  lea     rcx, [rsp+58h+pSid2]
0x1800241ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800241f2  mov     eax, edi
0x1800241f4  jmp     loc_1800242CC
0x1800241f9  test    rbx, rbx
0x1800241fc  jz      short loc_180024206
0x1800241fe  mov     rcx, rbx; Block
0x180024201  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024206  lea     rcx, [rsp+58h+hExistingToken]
0x18002420b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024210  lea     rcx, [rsp+58h+arg_18]
0x180024215  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18002421a  nop
0x18002421b  lea     rcx, [rsp+58h+pSid2]
0x180024220  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024225  xor     eax, eax
0x180024227  jmp     loc_1800242CC
0x18002422c  test    rbx, rbx
0x18002422f  jz      short loc_180024239
0x180024231  mov     rcx, rbx; Block
0x180024234  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024239  lea     rcx, [rsp+58h+hExistingToken]
0x18002423e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024243  inc     edi
0x180024245  mov     eax, [rsp+58h+arg_8]
0x180024249  jmp     loc_180024069
0x18002424e  mov     rcx, [rsp+58h]; this
0x180024253  lea     rax, aCouldnTGetAnIm; "Couldn't get an Impersonation User Toke"...
0x18002425a  mov     qword ptr [rsp+58h+TokenType], rax; int
0x18002425f  mov     ebx, 80070520h
0x180024264  mov     r9d, ebx; char *
0x180024267  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002426e  mov     edx, 55h ; 'U'; void *
0x180024273  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180024278  lea     rcx, [rsp+58h+arg_18]
0x18002427d  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180024282  nop
0x180024283  lea     rcx, [rsp+58h+pSid2]
0x180024288  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002428d  mov     eax, ebx
0x18002428f  jmp     short loc_1800242CC
0x180024291  mov     rcx, [rsp+58h]; this
0x180024296  mov     ebx, 80070520h
0x18002429b  mov     r9d, ebx; char *
0x18002429e  lea     r8, aOnecoreuapPrin_8; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800242a5  mov     edx, 41h ; 'A'; void *
0x1800242aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800242af  lea     rcx, [rsp+58h+arg_18]
0x1800242b4  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x1800242b9  nop
0x1800242ba  lea     rcx, [rsp+58h+pSid2]
0x1800242bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800242c4  mov     eax, ebx
0x1800242c6  jmp     short loc_1800242CC
0x1800242c8  mov     eax, [rsp+58h+arg_8]
0x1800242cc  add     rsp, 40h
0x1800242d0  pop     rdi
0x1800242d1  pop     rsi
0x1800242d2  pop     rbx
0x1800242d3  retn
0x1800242d4  mov     r9d, eax; char *
0x1800242d7  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800242de  mov     edx, 1B0h; void *
0x1800242e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
