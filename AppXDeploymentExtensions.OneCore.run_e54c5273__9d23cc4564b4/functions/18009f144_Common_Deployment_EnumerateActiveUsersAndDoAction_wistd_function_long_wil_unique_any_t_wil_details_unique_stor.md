# Common::Deployment::EnumerateActiveUsersAndDoAction(wistd::function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>,bool)

- ea: `0x18009f144`
- end: `0x18009fbb0`
- name: `?EnumerateActiveUsersAndDoAction@Deployment@Common@@YAJV?$function@$$A6AJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@@Z@wistd@@_N@Z`
- size: `2668`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e59c4`
- `0x1801e5a54`

## callees

- `0x1800210f0`
- `0x180056994`
- `0x180057010`
- `0x18006cb78`
- `0x1800853cc`
- `0x180098bf4`
- `0x18009f144`
- `0x18009fbb8`
- `0x18009fbdc`
- `0x18009fc48`
- `0x18009fc9c`
- `0x18009fcd8`
- `0x1800a021c`
- `0x1800a219c`
- `0x1800baaac`
- `0x1800c3328`
- `0x1800f0760`
- `0x1800f0f0c`
- `0x1800f163c`
- `0x1800fc6d8`
- `0x1801ecd6c`
- `0x1801ecdb0`
- `0x1801ece80`
- `0x180211010`

## import_xrefs

- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009f416`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18009f416`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f2bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f5a7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f9fb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f2bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f5a7`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18009f9fb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009f2ef`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009f560`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009f2ef`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009f560`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f289`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f572`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f961`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f289`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f572`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f961`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f299`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f581`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f971`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f299`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f581`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f971`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18009f45a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18009f45a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009f507`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18009f507`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18009f269`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18009f269`

## string_xrefs

- `0x18009f188`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f1e8`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f32d`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f376`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f3ce`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f47e`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f602`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f665`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f6d2`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f738`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f7a4`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f7fd`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f8fa`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009f996`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009fa09`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009fa80`: `onecore\admin\appmodel\common\sessionutilities.cpp`
- `0x18009fb44`: `onecore\admin\appmodel\common\sessionutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Common::Deployment::EnumerateActiveUsersAndDoAction(__int64 a1)
{
  int v1; // eax
  __int64 v2; // rcx
  int v3; // ebx
  unsigned __int64 v4; // rsi
  int v5; // eax
  unsigned __int64 v6; // r14
  __int64 v7; // r13
  __int64 v8; // rdi
  PSID *v9; // rbx
  PSID *v10; // r15
  SIZE_T LengthSid; // r12
  HLOCAL v12; // rax
  const char *v13; // r9
  unsigned __int64 i; // rdi
  __int64 v15; // rcx
  int v16; // eax
  int LastError; // edi
  int v18; // esi
  int v19; // eax
  _QWORD *v20; // r12
  _QWORD *v21; // r15
  unsigned __int64 v22; // r14
  PSID *v23; // rbx
  PSID *v24; // r13
  int UserToken; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  PSID v28; // rdx
  int token_information; // eax
  PSID *v30; // rdi
  __int64 v31; // rcx
  SIZE_T v32; // rsi
  HLOCAL v33; // rax
  const char *v34; // r9
  int v35; // eax
  void **v36; // rdx
  _QWORD *v37; // rdi
  PSID *v38; // rsi
  __int64 v39; // r8
  __int64 v40; // r9
  int v41; // eax
  PSID *v42; // rbx
  SIZE_T v43; // r14
  HLOCAL v44; // rax
  const char *v45; // r9
  int v46; // eax
  __int64 v47; // rcx
  unsigned __int64 j; // rdi
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  int v52; // r14d
  _QWORD v54[2]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD *v55; // [rsp+30h] [rbp-39h] BYREF
  __int64 v56; // [rsp+38h] [rbp-31h]
  _QWORD *v57; // [rsp+40h] [rbp-29h]
  unsigned int v58; // [rsp+48h] [rbp-21h] BYREF
  char v59; // [rsp+4Ch] [rbp-1Dh]
  _QWORD v60[2]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v61; // [rsp+60h] [rbp-9h]
  char v62; // [rsp+68h] [rbp-1h]
  _QWORD v63[2]; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int64 v64; // [rsp+80h] [rbp+17h]
  char v65; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  void *Block; // [rsp+E0h] [rbp+77h] BYREF
  void *v69; // [rsp+E8h] [rbp+7Fh] BYREF

  v54[0] = 0;
  v54[1] = 0;
  v1 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v54, 0);
  v3 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
      (const char *)(unsigned int)v1,
      v54[0]);
    if ( LODWORD(v54[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
LABEL_124:
    v47 = a1;
    goto LABEL_144;
  }
  v60[0] = 0;
  v60[1] = 0;
  v4 = 0;
  v61 = 0;
  v62 = 1;
  v63[0] = 0;
  v63[1] = 0;
  v64 = 0;
  v65 = 1;
  v5 = Common::Deployment::SessionInfoCache::All(v2, v63);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
      (const char *)(unsigned int)v5,
      v54[0]);
    Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
    Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
    if ( LODWORD(v54[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
    goto LABEL_124;
  }
  v6 = 0;
  v7 = v63[0];
  while ( v6 != v64 )
  {
    if ( v6 < v64 )
    {
      _mm_lfence();
      v8 = *(_QWORD *)(v7 + 8 * v6);
    }
    else
    {
      v8 = 0;
    }
    v9 = (PSID *)operator new(0x10u);
    *v9 = 0;
    v10 = v9 + 1;
    v9[1] = 0;
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
      if ( *v10 )
      {
        if ( CopySid(LengthSid, *v10, *(PSID *)(v8 + 8)) )
        {
          for ( i = 0; i != v4; ++i )
          {
            if ( i < v4 )
            {
              _mm_lfence();
              v15 = *(_QWORD *)(v60[0] + 8 * i);
            }
            else
            {
              v15 = 0;
            }
            if ( EqualSid(*(PSID *)(v15 + 8), *v10) )
            {
              if ( !v9 )
                goto LABEL_29;
              goto LABEL_15;
            }
          }
          v16 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
                  v60,
                  v9);
          LastError = v16;
          if ( v16 >= 0 )
          {
            v4 = v61;
            goto LABEL_29;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x155,
            (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
            (const char *)(unsigned int)v16,
            v54[0]);
          Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
          Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
          Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
          if ( LODWORD(v54[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x146,
                        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                        v13);
          Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
          Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
          Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
          if ( LODWORD(v54[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        }
        goto LABEL_35;
      }
      v18 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
        (const char *)0x8007000ELL,
        v54[0]);
      Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
      Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
      Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
      if ( LODWORD(v54[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
LABEL_123:
      v3 = v18;
      goto LABEL_124;
    }
LABEL_15:
    Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v9);
LABEL_29:
    ++v6;
  }
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v55 = 0;
    v56 = 0;
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
    v57 = &v55;
    v58 = 0;
    v59 = 1;
    v19 = UMgrEnumerateSessionUsers(&v58, &v55);
    v3 = v19;
    if ( v59 )
      v57[1] = v58;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
        (const char *)(unsigned int)v19,
        v54[0]);
      wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
      Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
      Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
      if ( LODWORD(v54[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
      goto LABEL_124;
    }
    v20 = v55;
    v21 = &v55[2 * v56];
    v22 = 0;
    while ( 2 )
    {
      if ( v20 != v21 )
      {
        v23 = (PSID *)operator new(0x10u);
        *v23 = 0;
        v24 = v23 + 1;
        v23[1] = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          v23,
          0);
        UserToken = UMgrQueryUserToken(*v20, v23);
        LastError = UserToken;
        if ( UserToken < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x163,
            (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
            (const char *)(unsigned int)UserToken,
            v54[0]);
          Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
          wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
          Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
          Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
          if ( LODWORD(v54[0]) )
            Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        }
        else
        {
          v28 = *v23;
          if ( (char *)*v23 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            LastError = -2147024581;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x164,
              (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
              (const char *)0x8007013BLL,
              v54[0]);
            Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
            wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
            Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
            Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
            if ( LODWORD(v54[0]) )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
          }
          else
          {
            Block = 0;
            token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v28, v26, v27);
            LastError = token_information;
            if ( token_information >= 0 )
            {
              v30 = (PSID *)Block;
              while ( v22 != v4 )
              {
                if ( v22 < v4 )
                {
                  _mm_lfence();
                  v31 = *(_QWORD *)(v60[0] + 8 * v22);
                }
                else
                {
                  v31 = 0;
                }
                if ( EqualSid(*(PSID *)(v31 + 8), *v30) )
                {
                  v22 = 0;
                  goto LABEL_64;
                }
                ++v22;
              }
              v32 = GetLengthSid(*v30);
              v33 = LocalAlloc(0x40u, v32);
              wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
                v24,
                v33);
              v22 = 0;
              if ( *v24 )
              {
                if ( CopySid(v32, *v24, *v30) )
                {
                  v35 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
                          v60,
                          v23);
                  v18 = v35;
                  if ( v35 >= 0 )
                  {
                    v23 = 0;
                    v4 = v61;
LABEL_64:
                    if ( v30 )
                      operator delete(v30);
                    if ( v23 )
                      Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
                    v20 += 2;
                    continue;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x17B,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                    (const char *)(unsigned int)v35,
                    v54[0]);
                  if ( v30 )
                    operator delete(v30);
                  Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
                  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
                  Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
                  Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
                  if ( LODWORD(v54[0]) )
                    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
                }
                else
                {
                  v18 = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x179,
                          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                          v34);
                  if ( v30 )
                    operator delete(v30);
                  Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
                  wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
                  Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
                  Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
                  if ( LODWORD(v54[0]) )
                    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
                }
              }
              else
              {
                v18 = -2147024882;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x178,
                  (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                  (const char *)0x8007000ELL,
                  v54[0]);
                if ( v30 )
                  operator delete(v30);
                Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
                wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
                Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
                Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
                if ( LODWORD(v54[0]) )
                  Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
              }
              goto LABEL_123;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x167,
              (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
              (const char *)(unsigned int)token_information,
              v54[0]);
            if ( Block )
              operator delete(Block);
            Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v23);
            wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
            Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
            Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
            if ( LODWORD(v54[0]) )
              Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
          }
        }
LABEL_35:
        v3 = LastError;
        goto LABEL_124;
      }
      break;
    }
    wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(&v55);
  }
  if ( !v4 && !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    Block = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &Block,
      0);
    if ( (int)Common::Deployment::QuerySingleSessionActiveUserToken((Common::Deployment *)&Block, v36) >= 0
      && (char *)Block - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v37 = operator new(0x10u);
      v38 = (PSID *)(v37 + 1);
      v37[1] = 0;
      v69 = 0;
      *v37 = 0;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        v37,
        &Block);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
        &Block,
        &v69);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v69);
      v69 = 0;
      v41 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v69, *v37, v39, v40);
      v3 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)v41,
          v54[0]);
        if ( v69 )
          operator delete(v69);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
        if ( LODWORD(v54[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        goto LABEL_124;
      }
      v42 = (PSID *)v69;
      v43 = GetLengthSid(*(PSID *)v69);
      v44 = LocalAlloc(0x40u, v43);
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        v38,
        v44);
      if ( !*v38 )
      {
        v18 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x192,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)0x8007000ELL,
          v54[0]);
        if ( v42 )
          operator delete(v42);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
        if ( LODWORD(v54[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        goto LABEL_123;
      }
      if ( !CopySid(v43, *v38, *v42) )
      {
        v18 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x193,
                (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
                v45);
        if ( v42 )
          operator delete(v42);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
        if ( LODWORD(v54[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        goto LABEL_123;
      }
      v46 = Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::Add(
              v60,
              v37);
      v18 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
          (const char *)(unsigned int)v46,
          v54[0]);
        if ( v42 )
          operator delete(v42);
        Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid::_scalar_deleting_destructor_(v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
        Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
        Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
        if ( LODWORD(v54[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
        goto LABEL_123;
      }
      if ( v42 )
        operator delete(v42);
      v4 = v61;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Block);
  }
  v3 = 0;
  for ( j = 0; j != v4; ++j )
  {
    if ( j < v4 )
      v49 = *(_QWORD *)(v60[0] + 8 * j);
    else
      v49 = 0;
    v50 = *(_QWORD *)(a1 + 112);
    if ( !v50 )
      __fastfail(7u);
    v51 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v50 + 32LL))(v50, v49, v49 + 8);
    v52 = v51;
    if ( v51 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19E,
        (unsigned int)"onecore\\admin\\appmodel\\common\\sessionutilities.cpp",
        (const char *)(unsigned int)v51,
        v54[0]);
    if ( v3 >= 0 )
      v3 = v52;
  }
  Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(v63);
  Common::Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___::_Array__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::ContainerOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::NoKey_Common::ContainerOperations_Common::NoKey__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid__Common::ArrayOperations__Common::Deployment::EnumerateActiveUsersAndDoAction_::_2_::UserTokenAndSid_Common::NoKey___(v60);
  if ( LODWORD(v54[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v54);
  v47 = a1;
LABEL_144:
  wistd::function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>::~function<long (wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)>(v47);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18009f144  mov     [rsp-8+arg_8], rbx
0x18009f149  mov     [rsp-8+arg_0], rcx
0x18009f14e  push    rbp
0x18009f14f  push    rsi
0x18009f150  push    rdi
0x18009f151  push    r12
0x18009f153  push    r13
0x18009f155  push    r14
0x18009f157  push    r15
0x18009f159  lea     rbp, [rsp-27h]
0x18009f15e  sub     rsp, 90h
0x18009f165  xor     r12d, r12d
0x18009f168  mov     [rbp+57h+var_A0], r12
0x18009f16c  mov     [rbp+57h+var_98], r12
0x18009f170  xor     edx, edx; void *
0x18009f172  lea     rcx, [rbp+57h+var_A0]; this
0x18009f176  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18009f17b  mov     ebx, eax
0x18009f17d  test    eax, eax
0x18009f17f  jns     short loc_18009F1AF
0x18009f181  mov     rcx, [rbp+5Fh]; this
0x18009f185  mov     r9d, eax; char *
0x18009f188  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f18f  mov     edx, 12Eh; void *
0x18009f194  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f199  nop
0x18009f19a  cmp     dword ptr [rbp+57h+var_A0], r12d
0x18009f19e  jz      short loc_18009F1AA
0x18009f1a0  lea     rcx, [rbp+57h+var_A0]; this
0x18009f1a4  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f1a9  nop
0x18009f1aa  jmp     loc_18009FADC
0x18009f1af  mov     [rbp+57h+var_70], r12
0x18009f1b3  mov     [rbp+57h+var_68], r12
0x18009f1b7  mov     rsi, r12
0x18009f1ba  mov     [rbp+57h+var_60], r12
0x18009f1be  mov     [rbp+57h+var_58], 1
0x18009f1c2  mov     [rbp+57h+var_50], r12
0x18009f1c6  mov     [rbp+57h+var_48], r12
0x18009f1ca  mov     [rbp+57h+var_40], r12
0x18009f1ce  mov     [rbp+57h+var_38], 1
0x18009f1d2  lea     rdx, [rbp+57h+var_50]
0x18009f1d6  call    ?All@SessionInfoCache@Deployment@Common@@QEAAJAEAV?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@3@@Z; Common::Deployment::SessionInfoCache::All(Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>> &)
0x18009f1db  mov     ebx, eax
0x18009f1dd  test    eax, eax
0x18009f1df  jns     short loc_18009F223
0x18009f1e1  mov     rcx, [rbp+5Fh]; this
0x18009f1e5  mov     r9d, eax; char *
0x18009f1e8  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f1ef  mov     edx, 137h; void *
0x18009f1f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f1f9  nop
0x18009f1fa  lea     rcx, [rbp+57h+var_50]
0x18009f1fe  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x18009f203  nop
0x18009f204  lea     rcx, [rbp+57h+var_70]
0x18009f208  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x18009f20d  nop
0x18009f20e  cmp     dword ptr [rbp+57h+var_A0], r12d
0x18009f212  jz      short loc_18009F21E
0x18009f214  lea     rcx, [rbp+57h+var_A0]; this
0x18009f218  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f21d  nop
0x18009f21e  jmp     loc_18009FADC
0x18009f223  mov     r14, r12
0x18009f226  mov     r13, [rbp+57h+var_50]
0x18009f22a  cmp     r14, [rbp+57h+var_40]
0x18009f22e  jz      loc_18009F416
0x18009f234  jb      short loc_18009F23B
0x18009f236  mov     rdi, r12
0x18009f239  jmp     short loc_18009F243
0x18009f23b  lfence
0x18009f23e  mov     rdi, [r13+r14*8+0]
0x18009f243  mov     ecx, 10h; Size
0x18009f248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f24d  mov     rbx, rax
0x18009f250  mov     [rax], r12
0x18009f253  lea     r15, [rax+8]
0x18009f257  mov     [r15], r12
0x18009f25a  xor     edx, edx
0x18009f25c  mov     rcx, rax
0x18009f25f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009f264  mov     rdx, rbx; phToken
0x18009f267  mov     ecx, [rdi]; SessionId
0x18009f269  call    cs:__imp_WTSQueryUserToken
0x18009f26f  test    eax, eax
0x18009f271  jnz     short loc_18009F285
0x18009f273  mov     edx, 1
0x18009f278  mov     rcx, rbx; void *
0x18009f27b  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x18009f280  jmp     loc_18009F31E
0x18009f285  mov     rcx, [rdi+8]; pSid
0x18009f289  call    cs:__imp_GetLengthSid
0x18009f28f  mov     r12d, eax
0x18009f292  mov     edx, eax; uBytes
0x18009f294  mov     ecx, 40h ; '@'; uFlags
0x18009f299  call    cs:__imp_LocalAlloc
0x18009f29f  mov     rdx, rax
0x18009f2a2  mov     rcx, r15
0x18009f2a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18009f2aa  mov     rdx, [r15]; pDestinationSid
0x18009f2ad  test    rdx, rdx
0x18009f2b0  jz      loc_18009F3C2
0x18009f2b6  mov     r8, [rdi+8]; pSourceSid
0x18009f2ba  mov     ecx, r12d; nDestinationSidLength
0x18009f2bd  call    cs:__imp_CopySid
0x18009f2c3  xor     r12d, r12d
0x18009f2c6  test    eax, eax
0x18009f2c8  jz      loc_18009F372
0x18009f2ce  mov     edi, r12d
0x18009f2d1  cmp     rdi, rsi
0x18009f2d4  jz      short loc_18009F308
0x18009f2d6  jb      short loc_18009F2DD
0x18009f2d8  mov     rcx, r12
0x18009f2db  jmp     short loc_18009F2E8
0x18009f2dd  lfence
0x18009f2e0  mov     rax, [rbp+57h+var_70]
0x18009f2e4  mov     rcx, [rax+rdi*8]
0x18009f2e8  mov     rdx, [r15]; pSid2
0x18009f2eb  mov     rcx, [rcx+8]; pSid1
0x18009f2ef  call    cs:__imp_EqualSid
0x18009f2f5  test    eax, eax
0x18009f2f7  jnz     short loc_18009F2FE
0x18009f2f9  inc     rdi
0x18009f2fc  jmp     short loc_18009F2D1
0x18009f2fe  test    rbx, rbx
0x18009f301  jz      short loc_18009F31E
0x18009f303  jmp     loc_18009F273
0x18009f308  mov     rdx, rbx
0x18009f30b  lea     rcx, [rbp+57h+var_70]
0x18009f30f  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey_____Add
0x18009f314  mov     edi, eax
0x18009f316  test    eax, eax
0x18009f318  js      short loc_18009F326
0x18009f31a  mov     rsi, [rbp+57h+var_60]
0x18009f31e  inc     r14
0x18009f321  jmp     loc_18009F22A
0x18009f326  mov     rcx, [rbp+5Fh]; this
0x18009f32a  mov     r9d, edi; char *
0x18009f32d  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f334  mov     edx, 155h; void *
0x18009f339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f33e  mov     edx, 1
0x18009f343  mov     rcx, rbx; void *
0x18009f346  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x18009f34b  nop
0x18009f34c  lea     rcx, [rbp+57h+var_50]
0x18009f350  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x18009f355  nop
0x18009f356  lea     rcx, [rbp+57h+var_70]
0x18009f35a  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x18009f35f  nop
0x18009f360  cmp     dword ptr [rbp+57h+var_A0], r12d
0x18009f364  jz      short loc_18009F370
0x18009f366  lea     rcx, [rbp+57h+var_A0]; this
0x18009f36a  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f36f  nop
0x18009f370  jmp     short loc_18009F3BB
0x18009f372  mov     rcx, [rbp+5Fh]; this
0x18009f376  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f37d  mov     edx, 146h; void *
0x18009f382  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009f387  mov     edi, eax
0x18009f389  mov     edx, 1
0x18009f38e  mov     rcx, rbx; void *
0x18009f391  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x18009f396  nop
0x18009f397  lea     rcx, [rbp+57h+var_50]
0x18009f39b  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x18009f3a0  nop
0x18009f3a1  lea     rcx, [rbp+57h+var_70]
0x18009f3a5  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x18009f3aa  nop
0x18009f3ab  cmp     dword ptr [rbp+57h+var_A0], r12d
0x18009f3af  jz      short loc_18009F3BB
0x18009f3b1  lea     rcx, [rbp+57h+var_A0]; this
0x18009f3b5  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f3ba  nop
0x18009f3bb  mov     ebx, edi
0x18009f3bd  jmp     loc_18009FADC
0x18009f3c2  mov     rcx, [rbp+5Fh]; this
0x18009f3c6  mov     esi, 8007000Eh
0x18009f3cb  mov     r9d, esi; char *
0x18009f3ce  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f3d5  mov     edx, 145h; void *
0x18009f3da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f3df  mov     edx, 1
0x18009f3e4  mov     rcx, rbx; void *
0x18009f3e7  call    _Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid___scalar_deleting_destructor_
0x18009f3ec  nop
0x18009f3ed  lea     rcx, [rbp+57h+var_50]
0x18009f3f1  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x18009f3f6  nop
0x18009f3f7  lea     rcx, [rbp+57h+var_70]
0x18009f3fb  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x18009f400  nop
0x18009f401  cmp     dword ptr [rbp+57h+var_A0], 0
0x18009f405  jz      short loc_18009F411
0x18009f407  lea     rcx, [rbp+57h+var_A0]; this
0x18009f40b  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f410  nop
0x18009f411  jmp     loc_18009FADA
0x18009f416  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x18009f41c  test    al, al
0x18009f41e  jz      loc_18009F85B
0x18009f424  call    IsUMgrEnumerateSessionUsersPresent
0x18009f429  test    al, al
0x18009f42b  jz      loc_18009F85B
0x18009f431  mov     [rbp+57h+var_90], r12
0x18009f435  mov     [rbp+57h+var_88], r12
0x18009f439  lea     rcx, [rbp+57h+var_90]
0x18009f43d  call    ?reset@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18009f442  lea     rax, [rbp+57h+var_90]
0x18009f446  mov     [rbp+57h+var_80], rax
0x18009f44a  mov     [rbp+57h+var_78], r12d
0x18009f44e  mov     [rbp+57h+var_74], 1
0x18009f452  lea     rdx, [rbp+57h+var_90]
0x18009f456  lea     rcx, [rbp+57h+var_78]
0x18009f45a  call    cs:__imp_UMgrEnumerateSessionUsers
0x18009f460  mov     ebx, eax
0x18009f462  cmp     [rbp+57h+var_74], r12b
0x18009f466  jz      short loc_18009F473
0x18009f468  mov     edx, [rbp+57h+var_78]
0x18009f46b  mov     rcx, [rbp+57h+var_80]
0x18009f46f  mov     [rcx+8], rdx
0x18009f473  test    eax, eax
0x18009f475  jns     short loc_18009F4C3
0x18009f477  mov     rcx, [rbp+5Fh]; this
0x18009f47b  mov     r9d, eax; char *
0x18009f47e  lea     r8, aOnecoreAdminAp_36; "onecore\\admin\\appmodel\\common\\sessi"...
0x18009f485  mov     edx, 15Eh; void *
0x18009f48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f48f  nop
0x18009f490  lea     rcx, [rbp+57h+var_90]
0x18009f494  call    ?reset@?$unique_any_array_ptr@U_SESSION_USER_CONTEXT@@U?$function_deleter@P6AXPEAU_SESSION_USER_CONTEXT@@@Z$1?UMgrFreeSessionUsers@@YAX0@Z@wil@@Uempty_deleter@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<_SESSION_USER_CONTEXT,wil::function_deleter<void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *)>,wil::empty_deleter,unsigned __int64>::reset(void)
0x18009f499  nop
0x18009f49a  lea     rcx, [rbp+57h+var_50]
0x18009f49e  call    ??1?$Array@USessionInfo@Deployment@Common@@VSessionInfoArrayOperations@23@VNoKey@3@V?$ContainerOperations@VNoKey@Common@@USessionInfo@Deployment@2@@3@V?$ArrayOperations@USessionInfo@Deployment@Common@@VNoKey@3@@3@@Common@@QEAA@XZ; Common::Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>::~Array<Common::Deployment::SessionInfo,Common::Deployment::SessionInfoArrayOperations,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::Deployment::SessionInfo>,Common::ArrayOperations<Common::Deployment::SessionInfo,Common::NoKey>>(void)
0x18009f4a3  nop
0x18009f4a4  lea     rcx, [rbp+57h+var_70]
0x18009f4a8  call    Common__Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey______Array__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__ContainerOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__NoKey_Common__ContainerOperations_Common__NoKey__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid__Common__ArrayOperations__Common__Deployment__EnumerateActiveUsersAndDoAction____2___UserTokenAndSid_Common__NoKey___
0x18009f4ad  nop
0x18009f4ae  cmp     dword ptr [rbp+57h+var_A0], r12d
0x18009f4b2  jz      short loc_18009F4BE
0x18009f4b4  lea     rcx, [rbp+57h+var_A0]; this
0x18009f4b8  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18009f4bd  nop
0x18009f4be  jmp     loc_18009FADC
0x18009f4c3  mov     r12, [rbp+57h+var_90]
0x18009f4c7  mov     r15, [rbp+57h+var_88]
0x18009f4cb  shl     r15, 4
0x18009f4cf  add     r15, r12
0x18009f4d2  xor     r14d, r14d
0x18009f4d5  cmp     r12, r15
0x18009f4d8  jz      loc_18009F84F
0x18009f4de  mov     ecx, 10h; Size
0x18009f4e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f4e8  mov     rbx, rax
0x18009f4eb  mov     [rax], r14
0x18009f4ee  lea     r13, [rax+8]
0x18009f4f2  mov     [r13+0], r14
0x18009f4f6  xor     edx, edx
0x18009f4f8  mov     rcx, rax
0x18009f4fb  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009f500  mov     rdx, rbx
0x18009f503  mov     rcx, [r12]
0x18009f507  call    cs:__imp_UMgrQueryUserToken
0x18009f50d  mov     edi, eax
0x18009f50f  test    eax, eax
0x18009f511  js      loc_18009F7F6
0x18009f517  mov     rdx, [rbx]
0x18009f51a  lea     rax, [rdx-1]
0x18009f51e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009f522  ja      loc_18009F798
0x18009f528  mov     [rbp+57h+Block], r14
0x18009f52c  lea     rcx, [rbp+57h+Block]
0x18009f530  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18009f535  mov     edi, eax
0x18009f537  test    eax, eax
0x18009f539  js      loc_18009F731
0x18009f53f  mov     rdi, [rbp+57h+Block]
0x18009f543  cmp     r14, rsi
0x18009f546  jz      short loc_18009F56F
0x18009f548  jb      short loc_18009F54E
0x18009f54a  xor     ecx, ecx
0x18009f54c  jmp     short loc_18009F559
0x18009f54e  lfence
0x18009f551  mov     rax, [rbp+57h+var_70]
0x18009f555  mov     rcx, [rax+r14*8]
0x18009f559  mov     rdx, [rdi]; pSid2
0x18009f55c  mov     rcx, [rcx+8]; pSid1
0x18009f560  call    cs:__imp_EqualSid
0x18009f566  test    eax, eax
0x18009f568  jnz     short loc_18009F5D0
0x18009f56a  inc     r14
0x18009f56d  jmp     short loc_18009F543
0x18009f56f  mov     rcx, [rdi]; pSid
0x18009f572  call    cs:__imp_GetLengthSid
0x18009f578  mov     esi, eax
0x18009f57a  mov     edx, eax; uBytes
  ... truncated ...
```
