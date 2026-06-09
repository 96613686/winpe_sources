# Common::Deployment::EnumerateActiveUsersAndDoAction(wistd::function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>,bool)

- ea: `0x180085898`
- end: `0x1800860d3`
- name: `?EnumerateActiveUsersAndDoAction@Deployment@Common@@YAJV?$function@$$A6AJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@Z@wistd@@_N@Z`
- size: `2107`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018722c`
- `0x1801872c4`

## callees

- `0x18000669c`
- `0x180012fc8`
- `0x18001adb4`
- `0x1800225fc`
- `0x18004e96c`
- `0x180050e60`
- `0x1800529ec`
- `0x180056208`
- `0x180085898`
- `0x1800860dc`
- `0x180086104`
- `0x180086170`
- `0x1800861ac`
- `0x1800861b8`
- `0x180089784`
- `0x1800af220`
- `0x1800af6ec`
- `0x1800b0fa8`
- `0x1800ba584`
- `0x1800dd034`
- `0x180100f3c`
- `0x180116d48`
- `0x180116d64`
- `0x1801867dc`
- `0x18018790c`
- `0x18018b79c`
- `0x18018b7e0`
- `0x18018b8b8`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085a42`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085c72`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085a42`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180085c72`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085a0d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085ccb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085f48`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085a0d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085ccb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180085f48`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800859cc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085c8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085f09`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800859cc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085c8a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180085f09`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180085b40`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180085b40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800859e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085c9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085f1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800859e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085c9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180085f1f`
- `WTSAPI32!WTSQueryUserToken` at `0x1800859b3`
- `WTSAPI32!WTSQueryUserToken` at `0x1800859b3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180085c17`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180085c17`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180085b8b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180085b8b`

## string_xrefs

- `0x1800858dc`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18008592b`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085a95`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085aac`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085b03`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085bad`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085d36`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085d75`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085d9d`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085dd0`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085ec5`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085f5c`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180085ff7`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x180086020`: `onecore\admin\appmodel\common\sessionutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Common::Deployment::EnumerateActiveUsersAndDoAction(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // r15
  unsigned __int64 v5; // rsi
  int v6; // eax
  unsigned __int64 i; // r14
  __int64 v8; // rdi
  PSID *v9; // rbx
  PSID *v10; // r12
  SIZE_T LengthSid; // r13
  HLOCAL v12; // rax
  const char *v13; // r9
  unsigned __int64 j; // rdi
  __int64 v15; // rcx
  int v16; // eax
  int LastError; // edi
  bool v18; // zf
  int v19; // esi
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // r8
  _QWORD *v23; // r12
  _QWORD *v24; // rax
  PSID *v25; // rbx
  PSID *v26; // r13
  unsigned __int64 v27; // r14
  PSID v28; // rdx
  int token_information; // eax
  PSID *v30; // rdi
  __int64 v31; // rcx
  SIZE_T v32; // rsi
  HLOCAL v33; // rax
  const char *v34; // r9
  __int64 v35; // rdx
  __int64 v36; // rdx
  void **v37; // rdx
  _QWORD *v38; // rdi
  PSID *v39; // rsi
  int v40; // eax
  PSID *v41; // rbx
  SIZE_T v42; // r14
  HLOCAL v43; // rax
  const char *v44; // r9
  __int64 v45; // rdx
  unsigned __int64 k; // rdi
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // eax
  int v50; // r14d
  __int64 v51; // rcx
  int v53[4]; // [rsp+20h] [rbp-49h] BYREF
  void *v54[2]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v55[2]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v56[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v57; // [rsp+60h] [rbp-9h]
  char v58; // [rsp+68h] [rbp-1h]
  _QWORD v59[2]; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v60; // [rsp+80h] [rbp+17h]
  char v61; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  void *Block; // [rsp+E0h] [rbp+77h] BYREF
  void *v65; // [rsp+E8h] [rbp+7Fh] BYREF

  v54[0] = 0;
  v54[1] = 0;
  v1 = Common::ImpersonationContext::Impersonate(v54, 0);
  v3 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
      (const char *)(unsigned int)v1,
      v53[0]);
    goto LABEL_6;
  }
  v4 = 0;
  v56[0] = 0;
  v56[1] = 0;
  v5 = 0;
  v57 = 0;
  v58 = 1;
  v59[0] = 0;
  v59[1] = 0;
  v60 = 0;
  v61 = 1;
  v6 = Common::Deployment::SessionInfoCache::All(v2, v59);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
      (const char *)(unsigned int)v6,
      v53[0]);
LABEL_5:
    Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
    Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
LABEL_6:
    if ( LODWORD(v54[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
LABEL_110:
    v51 = a1;
    goto LABEL_115;
  }
  for ( i = 0; i != v60; ++i )
  {
    if ( i < v60 )
    {
      _mm_lfence();
      v8 = *(_QWORD *)(v59[0] + 8 * i);
    }
    else
    {
      v8 = 0;
    }
    v9 = (PSID *)operator new(0x10u);
    *v9 = 0;
    v10 = v9 + 1;
    v9[1] = 0;
    Block = v9;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v9,
      0);
    if ( WTSQueryUserToken(*(_DWORD *)v8, v9) )
    {
      LengthSid = GetLengthSid(*(PSID *)(v8 + 8));
      v12 = LocalAlloc(0x40u, LengthSid);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v10,
        v12);
      if ( !*v10 )
      {
        v19 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)0x8007000ELL,
          v53[0]);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
        v20 = LODWORD(v54[0]) == 0;
        goto LABEL_107;
      }
      if ( !CopySid(LengthSid, *v10, *(PSID *)(v8 + 8)) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x146,
                      (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                      v13);
LABEL_30:
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
        v18 = LODWORD(v54[0]) == 0;
        goto LABEL_31;
      }
      for ( j = 0; j != v5; ++j )
      {
        if ( j < v5 )
        {
          _mm_lfence();
          v15 = *(_QWORD *)(v4 + 8 * j);
        }
        else
        {
          v15 = 0;
        }
        if ( EqualSid(*(PSID *)(v15 + 8), *v10) )
          goto LABEL_25;
      }
      v16 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
              v56,
              v9);
      LastError = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)v16,
          v53[0]);
        goto LABEL_30;
      }
      v9 = 0;
      v5 = v57;
      v4 = v56[0];
LABEL_25:
      if ( !v9 )
        continue;
    }
    Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
  }
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    wil::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<unsigned char,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(v55);
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::operator&(v55);
    v21 = wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<unsigned long>(
            v55,
            v53);
    v3 = UMgrEnumerateSessionUsers(v21 + 8, v22);
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v53);
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
        (const char *)(unsigned int)v3,
        v53[0]);
      wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(v55);
      goto LABEL_5;
    }
    v23 = (_QWORD *)v55[0];
    v24 = (_QWORD *)wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::end(v55);
    v65 = v24;
    while ( 2 )
    {
      if ( v23 != v24 )
      {
        v25 = (PSID *)operator new(0x10u);
        *v25 = 0;
        v26 = v25 + 1;
        v27 = 0;
        v25[1] = 0;
        *(_QWORD *)v53 = v25;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v25,
          0);
        LastError = UMgrQueryUserToken(*v23, v25);
        if ( LastError < 0 )
        {
          v36 = 355;
        }
        else
        {
          v28 = *v25;
          if ( (char *)*v25 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            Block = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v28);
            LastError = token_information;
            if ( token_information >= 0 )
            {
              v30 = (PSID *)Block;
              while ( v27 != v5 )
              {
                if ( v27 < v5 )
                {
                  _mm_lfence();
                  v31 = *(_QWORD *)(v4 + 8 * v27);
                }
                else
                {
                  v31 = 0;
                }
                if ( EqualSid(*(PSID *)(v31 + 8), *v30) )
                  goto LABEL_55;
                ++v27;
              }
              v32 = GetLengthSid(*v30);
              v33 = LocalAlloc(0x40u, v32);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                v26,
                v33);
              if ( *v26 )
              {
                if ( !CopySid(v32, *v26, *v30) )
                {
                  v19 = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x179,
                          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                          v34);
                  goto LABEL_62;
                }
                v19 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
                        v56,
                        v25);
                if ( v19 >= 0 )
                {
                  v25 = 0;
                  v5 = v57;
                  v4 = v56[0];
LABEL_55:
                  if ( v30 )
                    operator delete(v30);
                  if ( v25 )
                    Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v25);
                  v23 += 2;
                  v24 = v65;
                  continue;
                }
                v35 = 379;
              }
              else
              {
                v19 = -2147024882;
                v35 = 376;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v35,
                (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                (const char *)(unsigned int)v19,
                v53[0]);
LABEL_62:
              if ( v30 )
                operator delete(v30);
              Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v25);
              wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(v55);
              goto LABEL_106;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x167,
              (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
              (const char *)(unsigned int)token_information,
              v53[0]);
            if ( Block )
              operator delete(Block);
LABEL_72:
            Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v25);
            wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(v55);
            Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
            Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
            v18 = LODWORD(v54[0]) == 0;
LABEL_31:
            if ( !v18 )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
            v3 = LastError;
            goto LABEL_110;
          }
          LastError = -2147024581;
          v36 = 356;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)LastError,
          v53[0]);
        goto LABEL_72;
      }
      break;
    }
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(v55);
  }
  if ( !v5 && !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    Block = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &Block,
      0);
    if ( (int)Common::Deployment::QuerySingleSessionActiveUserToken((Common::Deployment *)&Block, v37) >= 0
      && (char *)Block - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v38 = operator new(0x10u);
      v39 = (PSID *)(v38 + 1);
      v38[1] = 0;
      *(_QWORD *)v53 = v38;
      v65 = 0;
      *v38 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        v38,
        &Block);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &Block,
        &v65);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v65);
      v65 = 0;
      v40 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v65, *v38);
      v3 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)v40,
          v53[0]);
        if ( v65 )
          operator delete(v65);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v38);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
        goto LABEL_5;
      }
      v41 = (PSID *)v65;
      v42 = GetLengthSid(*(PSID *)v65);
      v43 = LocalAlloc(0x40u, v42);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v39,
        v43);
      if ( !*v39 )
      {
        v19 = -2147024882;
        v45 = 402;
        goto LABEL_102;
      }
      if ( !CopySid(v42, *v39, *v41) )
      {
        v19 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x193,
                (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                v44);
LABEL_103:
        if ( v41 )
          operator delete(v41);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v38);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
LABEL_106:
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
        v20 = LODWORD(v54[0]) == 0;
LABEL_107:
        if ( !v20 )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        v3 = v19;
        goto LABEL_110;
      }
      v19 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
              v56,
              v38);
      if ( v19 < 0 )
      {
        v45 = 405;
LABEL_102:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v45,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)v19,
          v53[0]);
        goto LABEL_103;
      }
      if ( v41 )
        operator delete(v41);
      v5 = v57;
      v4 = v56[0];
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
  }
  v3 = 0;
  for ( k = 0; k != v5; ++k )
  {
    v47 = 0;
    if ( k < v5 )
      v47 = *(_QWORD *)(v4 + 8 * k);
    v48 = *(_QWORD *)(a1 + 112);
    if ( !v48 )
      __fastfail(7u);
    v49 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v48 + 32LL))(v48, v47, v47 + 8);
    v50 = v49;
    if ( v49 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
        (const char *)(unsigned int)v49,
        v53[0]);
    if ( v3 >= 0 )
      v3 = v50;
  }
  Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v59);
  Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v56);
  if ( LODWORD(v54[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
  v51 = a1;
LABEL_115:
  wistd::function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>::~function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>(v51);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180085898  mov     [rsp-8+arg_8], rbx
0x18008589d  mov     [rsp-8+arg_0], rcx
0x1800858a2  push    rbp
0x1800858a3  push    rsi
0x1800858a4  push    rdi
0x1800858a5  push    r12
0x1800858a7  push    r13
0x1800858a9  push    r14
0x1800858ab  push    r15
0x1800858ad  lea     rbp, [rsp-27h]
0x1800858b2  sub     rsp, 90h
0x1800858b9  xor     r13d, r13d
0x1800858bc  mov     [rbp+57h+var_90], r13
0x1800858c0  mov     [rbp+57h+var_88], r13
0x1800858c4  xor     edx, edx; void *
0x1800858c6  lea     rcx, [rbp+57h+var_90]; this
0x1800858ca  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x1800858cf  mov     ebx, eax
0x1800858d1  test    eax, eax
0x1800858d3  jns     short loc_1800858EF
0x1800858d5  mov     rcx, [rbp+5Fh]; this
0x1800858d9  mov     r9d, eax; char *
0x1800858dc  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x1800858e3  mov     edx, 12Eh; void *
0x1800858e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800858ed  jmp     short loc_180085951
0x1800858ef  mov     r15, r13
0x1800858f2  mov     [rbp+57h+var_70], r13
0x1800858f6  mov     [rbp+57h+var_68], r13
0x1800858fa  mov     rsi, r13
0x1800858fd  mov     [rbp+57h+var_60], r13
0x180085901  mov     [rbp+57h+var_58], 1
0x180085905  mov     [rbp+57h+var_50], r13
0x180085909  mov     [rbp+57h+var_48], r13
0x18008590d  mov     [rbp+57h+var_40], r13
0x180085911  mov     [rbp+57h+var_38], 1
0x180085915  lea     rdx, [rbp+57h+var_50]
0x180085919  call    ?All@SessionInfoCache@Deployment@Common@@QEAAJAEAV?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@3@@Z; Common::Deployment::SessionInfoCache::All(Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>> &)
0x18008591e  mov     ebx, eax
0x180085920  test    eax, eax
0x180085922  jns     short loc_180085969
0x180085924  mov     rcx, [rbp+5Fh]; this
0x180085928  mov     r9d, eax; char *
0x18008592b  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x180085932  mov     edx, 137h; void *
0x180085937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008593c  nop
0x18008593d  lea     rcx, [rbp+57h+var_50]
0x180085941  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x180085946  nop
0x180085947  lea     rcx, [rbp+57h+var_70]
0x18008594b  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x180085950  nop
0x180085951  cmp     dword ptr [rbp+57h+var_90], r13d
0x180085955  jz      loc_18008607C
0x18008595b  lea     rcx, [rbp+57h+var_90]; this
0x18008595f  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180085964  jmp     loc_18008607C
0x180085969  mov     r14, r13
0x18008596c  cmp     r14, [rbp+57h+var_40]
0x180085970  jz      loc_180085B40
0x180085976  jb      short loc_18008597D
0x180085978  mov     rdi, r13
0x18008597b  jmp     short loc_180085988
0x18008597d  lfence
0x180085980  mov     rax, [rbp+57h+var_50]
0x180085984  mov     rdi, [rax+r14*8]
0x180085988  mov     ecx, 10h; Size
0x18008598d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180085992  mov     rbx, rax
0x180085995  mov     [rax], r13
0x180085998  lea     r12, [rax+8]
0x18008599c  mov     [r12], r13
0x1800859a0  mov     [rbp+57h+Block], rax
0x1800859a4  xor     edx, edx
0x1800859a6  mov     rcx, rax
0x1800859a9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800859ae  mov     rdx, rbx; phToken
0x1800859b1  mov     ecx, [rdi]; SessionId
0x1800859b3  call    cs:__imp_WTSQueryUserToken
0x1800859ba  nop     dword ptr [rax+rax+00h]
0x1800859bf  test    eax, eax
0x1800859c1  jnz     short loc_1800859C8
0x1800859c3  jmp     loc_180085A79
0x1800859c8  mov     rcx, [rdi+8]; pSid
0x1800859cc  call    cs:__imp_GetLengthSid
0x1800859d3  nop     dword ptr [rax+rax+00h]
0x1800859d8  mov     r13d, eax
0x1800859db  mov     edx, eax; uBytes
0x1800859dd  mov     ecx, 40h ; '@'; uFlags
0x1800859e2  call    cs:__imp_LocalAlloc
0x1800859e9  nop     dword ptr [rax+rax+00h]
0x1800859ee  mov     rdx, rax
0x1800859f1  mov     rcx, r12
0x1800859f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800859f9  mov     rdx, [r12]; pDestinationSid
0x1800859fd  test    rdx, rdx
0x180085a00  jz      loc_180085AF7
0x180085a06  mov     r8, [rdi+8]; pSourceSid
0x180085a0a  mov     ecx, r13d; nDestinationSidLength
0x180085a0d  call    cs:__imp_CopySid
0x180085a14  nop     dword ptr [rax+rax+00h]
0x180085a19  xor     r13d, r13d
0x180085a1c  test    eax, eax
0x180085a1e  jz      loc_180085AA8
0x180085a24  mov     edi, r13d
0x180085a27  cmp     rdi, rsi
0x180085a2a  jz      short loc_180085A57
0x180085a2c  jb      short loc_180085A33
0x180085a2e  mov     rcx, r13
0x180085a31  jmp     short loc_180085A3A
0x180085a33  lfence
0x180085a36  mov     rcx, [r15+rdi*8]
0x180085a3a  mov     rdx, [r12]; pSid2
0x180085a3e  mov     rcx, [rcx+8]; pSid1
0x180085a42  call    cs:__imp_EqualSid
0x180085a49  nop     dword ptr [rax+rax+00h]
0x180085a4e  test    eax, eax
0x180085a50  jnz     short loc_180085A74
0x180085a52  inc     rdi
0x180085a55  jmp     short loc_180085A27
0x180085a57  mov     rdx, rbx
0x180085a5a  lea     rcx, [rbp+57h+var_70]
0x180085a5e  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey_____Add
0x180085a63  mov     edi, eax
0x180085a65  test    eax, eax
0x180085a67  js      short loc_180085A8E
0x180085a69  mov     rbx, r13
0x180085a6c  mov     rsi, [rbp+57h+var_60]
0x180085a70  mov     r15, [rbp+57h+var_70]
0x180085a74  test    rbx, rbx
0x180085a77  jz      short loc_180085A86
0x180085a79  mov     edx, 1
0x180085a7e  mov     rcx, rbx; void *
0x180085a81  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x180085a86  inc     r14
0x180085a89  jmp     loc_18008596C
0x180085a8e  mov     rcx, [rbp+5Fh]; this
0x180085a92  mov     r9d, edi; char *
0x180085a95  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x180085a9c  mov     edx, 155h; void *
0x180085aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085aa6  jmp     short loc_180085ABF
0x180085aa8  mov     rcx, [rbp+5Fh]; this
0x180085aac  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x180085ab3  mov     edx, 146h; void *
0x180085ab8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085abd  mov     edi, eax
0x180085abf  mov     edx, 1
0x180085ac4  mov     rcx, rbx; void *
0x180085ac7  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x180085acc  nop
0x180085acd  lea     rcx, [rbp+57h+var_50]
0x180085ad1  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x180085ad6  nop
0x180085ad7  lea     rcx, [rbp+57h+var_70]
0x180085adb  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x180085ae0  nop
0x180085ae1  cmp     dword ptr [rbp+57h+var_90], r13d
0x180085ae5  jz      short loc_180085AF0
0x180085ae7  lea     rcx, [rbp+57h+var_90]; this
0x180085aeb  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x180085af0  mov     ebx, edi
0x180085af2  jmp     loc_18008607C
0x180085af7  mov     rcx, [rbp+5Fh]; this
0x180085afb  mov     esi, 8007000Eh
0x180085b00  mov     r9d, esi; char *
0x180085b03  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x180085b0a  mov     edx, 145h; void *
0x180085b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085b14  nop
0x180085b15  mov     edx, 1
0x180085b1a  mov     rcx, rbx; void *
0x180085b1d  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x180085b22  nop
0x180085b23  lea     rcx, [rbp+57h+var_50]
0x180085b27  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x180085b2c  nop
0x180085b2d  lea     rcx, [rbp+57h+var_70]
0x180085b31  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x180085b36  nop
0x180085b37  cmp     dword ptr [rbp+57h+var_90], 0
0x180085b3b  jmp     loc_18008606F
0x180085b40  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180085b47  nop     dword ptr [rax+rax+00h]
0x180085b4c  test    al, al
0x180085b4e  jz      loc_180085E22
0x180085b54  call    IsUMgrEnumerateSessionUsersPresent
0x180085b59  test    al, al
0x180085b5b  jz      loc_180085E22
0x180085b61  lea     rcx, [rbp+57h+var_80]
0x180085b65  call    ??0?$unique_any_array_ptr@EUprocess_heap_deleter@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>::unique_any_array_ptr<uchar,wil::process_heap_deleter,wil::empty_deleter,unsigned __int64>(void)
0x180085b6a  nop
0x180085b6b  lea     rcx, [rbp+57h+var_80]
0x180085b6f  call    ??I?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAPEAU_SESSION_USER_CONTEXT@@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::operator&(void)
0x180085b74  mov     r8, rax
0x180085b77  lea     rdx, [rbp+57h+var_A0]
0x180085b7b  lea     rcx, [rbp+57h+var_80]
0x180085b7f  call    ??$size_address@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA?AU?$size_address_ptr@K@01@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address<ulong>(void)
0x180085b84  lea     rcx, [rax+8]
0x180085b88  mov     rdx, r8
0x180085b8b  call    cs:__imp_UMgrEnumerateSessionUsers
0x180085b92  nop     dword ptr [rax+rax+00h]
0x180085b97  mov     ebx, eax
0x180085b99  lea     rcx, [rbp+57h+var_A0]
0x180085b9d  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x180085ba2  test    ebx, ebx
0x180085ba4  jns     short loc_180085BCD
0x180085ba6  mov     rcx, [rbp+5Fh]; this
0x180085baa  mov     r9d, ebx; char *
0x180085bad  lea     r8, aOnecoreAdminAp_40; "onecore\\admin\\appmodel\\common\\sessi"...
0x180085bb4  mov     edx, 15Eh; void *
0x180085bb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085bbe  nop
0x180085bbf  lea     rcx, [rbp+57h+var_80]
0x180085bc3  call    ??1?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>(void)
0x180085bc8  jmp     loc_18008593D
0x180085bcd  mov     r12, [rbp+57h+var_80]
0x180085bd1  lea     rcx, [rbp+57h+var_80]
0x180085bd5  call    ?end@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAPEAU_SESSION_USER_CONTEXT@@XZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::end(void)
0x180085bda  mov     [rbp+57h+arg_18], rax
0x180085bde  cmp     r12, rax
0x180085be1  jz      loc_180085E19
0x180085be7  mov     ecx, 10h; Size
0x180085bec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180085bf1  mov     rbx, rax
0x180085bf4  mov     [rax], r13
0x180085bf7  lea     r13, [rax+8]
0x180085bfb  xor     r14d, r14d
0x180085bfe  mov     [r13+0], r14
0x180085c02  mov     qword ptr [rbp+57h+var_A0], rax
0x180085c06  xor     edx, edx
0x180085c08  mov     rcx, rax
0x180085c0b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180085c10  mov     rdx, rbx
0x180085c13  mov     rcx, [r12]
0x180085c17  call    cs:__imp_UMgrQueryUserToken
0x180085c1e  nop     dword ptr [rax+rax+00h]
0x180085c23  mov     edi, eax
0x180085c25  test    eax, eax
0x180085c27  js      loc_180085DCB
0x180085c2d  mov     rdx, [rbx]
0x180085c30  lea     rax, [rdx-1]
0x180085c34  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180085c38  ja      loc_180085DBF
0x180085c3e  mov     [rbp+57h+Block], r14
0x180085c42  lea     rcx, [rbp+57h+Block]
0x180085c46  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180085c4b  mov     edi, eax
0x180085c4d  test    eax, eax
0x180085c4f  js      loc_180085D96
0x180085c55  mov     rdi, [rbp+57h+Block]
0x180085c59  cmp     r14, rsi
0x180085c5c  jz      short loc_180085C87
0x180085c5e  jb      short loc_180085C64
0x180085c60  xor     ecx, ecx
0x180085c62  jmp     short loc_180085C6B
0x180085c64  lfence
0x180085c67  mov     rcx, [r15+r14*8]
0x180085c6b  mov     rdx, [rdi]; pSid2
0x180085c6e  mov     rcx, [rcx+8]; pSid1
0x180085c72  call    cs:__imp_EqualSid
0x180085c79  nop     dword ptr [rax+rax+00h]
0x180085c7e  test    eax, eax
0x180085c80  jnz     short loc_180085CFE
0x180085c82  inc     r14
0x180085c85  jmp     short loc_180085C59
0x180085c87  mov     rcx, [rdi]; pSid
0x180085c8a  call    cs:__imp_GetLengthSid
0x180085c91  nop     dword ptr [rax+rax+00h]
0x180085c96  mov     esi, eax
0x180085c98  mov     edx, eax; uBytes
0x180085c9a  mov     ecx, 40h ; '@'; uFlags
0x180085c9f  call    cs:__imp_LocalAlloc
0x180085ca6  nop     dword ptr [rax+rax+00h]
0x180085cab  mov     rdx, rax
0x180085cae  mov     rcx, r13
0x180085cb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180085cb6  mov     rdx, [r13+0]; pDestinationSid
0x180085cba  xor     r13d, r13d
0x180085cbd  test    rdx, rdx
0x180085cc0  jz      loc_180085D8A
0x180085cc6  mov     r8, [rdi]; pSourceSid
0x180085cc9  mov     ecx, esi; nDestinationSidLength
0x180085ccb  call    cs:__imp_CopySid
0x180085cd2  nop     dword ptr [rax+rax+00h]
0x180085cd7  test    eax, eax
0x180085cd9  jz      loc_180085D71
0x180085cdf  mov     rdx, rbx
0x180085ce2  lea     rcx, [rbp+57h+var_70]
0x180085ce6  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey_____Add
0x180085ceb  mov     esi, eax
0x180085ced  test    eax, eax
0x180085cef  js      short loc_180085D2E
0x180085cf1  mov     ebx, r13d
0x180085cf4  mov     rsi, [rbp+57h+var_60]
0x180085cf8  mov     r15, [rbp+57h+var_70]
0x180085cfc  jmp     short loc_180085D01
0x180085cfe  xor     r13d, r13d
0x180085d01  test    rdi, rdi
  ... truncated ...
```
