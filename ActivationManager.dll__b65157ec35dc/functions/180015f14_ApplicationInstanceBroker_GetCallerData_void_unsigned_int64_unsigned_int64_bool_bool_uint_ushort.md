# ApplicationInstanceBroker::GetCallerData(void * *,unsigned __int64 *,unsigned __int64 *,bool &,bool &,uint *,ushort *)

- ea: `0x180015f14`
- end: `0x1800162be`
- name: `?GetCallerData@ApplicationInstanceBroker@@CAXPEAPEAXPEA_K1AEA_N2PEAIPEAG@Z`
- size: `938`
- prototype: `static void(void **, unsigned __int64 *, unsigned __int64 *, bool *, bool *, unsigned int *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014390`
- `0x1800167f0`
- `0x180086cb0`
- `0x1800884a0`
- `0x180088610`
- `0x180088dd0`

## callees

- `0x180006530`
- `0x180008ec0`
- `0x18000b5c0`
- `0x180015f14`
- `0x1800169e4`
- `0x1800174e0`
- `0x180017da4`
- `0x18002c900`
- `0x18002cc58`
- `0x18004fec8`
- `0x180056208`
- `0x18005ae90`
- `0x1800763ec`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016295`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016295`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180016087`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x180016087`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180015fd7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180015fd7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180015fa0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180015fa0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001600c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001600c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180016119`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180016119`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001626e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001626e`

## string_xrefs

- `0x180016139`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x180015f82`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x180015fb7`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x180015feb`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x180016020`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x18001605f`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x18001609b`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x1800160d0`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x18001615d`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x180016196`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x18001620b`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`
- `0x180016236`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\applicationinstancebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ApplicationInstanceBroker::GetCallerData(
        void **a1,
        unsigned int *a2,
        unsigned __int64 *a3,
        bool *a4,
        bool *a5,
        unsigned int *a6,
        unsigned __int16 *a7)
{
  int RPCClientProcessId; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned __int64 *v15; // r8
  int HostIdFromProcessToken; // eax
  unsigned int ApplicationUserModelIdFromToken; // eax
  int v18; // eax
  int AppInstancingErrorBehaviorPolicy; // edi
  int v20; // ebx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+20h] [rbp-E0h]
  bool v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE token; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v32; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  char v34; // [rsp+70h] [rbp-90h]
  int v35[4]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int128 v38; // [rsp+A0h] [rbp-60h]
  __int128 v39; // [rsp+B0h] [rbp-50h]
  __int128 v40; // [rsp+C0h] [rbp-40h]
  __int128 v41; // [rsp+D0h] [rbp-30h]
  WCHAR applicationUserModelId[136]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  LODWORD(v27) = 0;
  RPCClientProcessId = DevPlat::Shared::GetRPCClientProcessId((DevPlat::Shared *)&v27, a2);
  if ( RPCClientProcessId < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)(unsigned int)RPCClientProcessId,
      v24);
  v12 = UMgrOpenProcessHandleForAccess(1052672, (unsigned int)v27, a1);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)(unsigned int)v12,
      v24);
  token = 0;
  v13 = UMgrOpenProcessTokenForQuery((unsigned int)v27, &token);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)(unsigned int)v13,
      v24);
  v30 = 0;
  v14 = UMgrQueryUserContext(token, &v30);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)(unsigned int)v14,
      v24);
  if ( a2 )
    *(_QWORD *)a2 = v30;
  if ( a3 )
  {
    HostIdFromProcessToken = DevPlat::Shared::GetHostIdFromProcessToken((DevPlat::Shared *)token, a3, v15);
    if ( HostIdFromProcessToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)HostIdFromProcessToken,
        v24);
  }
  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( ApplicationUserModelIdFromToken )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
      (const char *)ApplicationUserModelIdFromToken,
      v24);
  if ( a7 )
  {
    v18 = StringCchCopyW(a7, *a6, applicationUserModelId);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCD,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)v18,
        v24);
  }
  AppInstancingErrorBehaviorPolicy = AppModelPolicy::GetAppInstancingErrorBehaviorPolicy(token);
  if ( AppInstancingErrorBehaviorPolicy == 3670017 )
  {
    v27 = 0;
    v32 = &v27;
    v33 = 0;
    v34 = 1;
    v20 = SRCacheManager_Open(0, &v33);
    wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v32);
    if ( v20 >= 0 )
      v20 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
        (const char *)(unsigned int)v20,
        v24);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)v20,
        v24);
    v31 = 0;
    v21 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
            (struct StateRepository::Cache::Manager_NoThrow *)&v27,
            token,
            &v31);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)v21,
        v24);
    v26 = 0;
    *(_OWORD *)v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v22 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
            (struct StateRepository::Cache::Manager_NoThrow *)&v27,
            v31,
            applicationUserModelId,
            0,
            (__int64)v35,
            &v26);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)(unsigned int)v22,
        v25);
    if ( !v26 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationinstancebroker.cpp",
        (const char *)0x8000FFFFLL,
        v25);
    *a5 = (v36 & 0x800000000LL) == 0;
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v35);
    v23 = v27;
    v27 = 0;
    if ( v23 )
      SRCacheManager_Close();
  }
  else
  {
    *a5 = 0;
  }
  *a4 = AppInstancingErrorBehaviorPolicy == 3670016;
  if ( (char *)token - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(token);
}

```

## disassembly

```asm
0x180015f14  push    rbp
0x180015f16  push    rbx
0x180015f17  push    rsi
0x180015f18  push    rdi
0x180015f19  push    r12
0x180015f1b  push    r13
0x180015f1d  push    r14
0x180015f1f  push    r15
0x180015f21  lea     rbp, [rsp-108h]
0x180015f29  sub     rsp, 208h
0x180015f30  mov     rax, cs:__security_cookie
0x180015f37  xor     rax, rsp
0x180015f3a  mov     [rbp+140h+var_50], rax
0x180015f41  mov     r13, r9
0x180015f44  mov     rdi, r8
0x180015f47  mov     rbx, rdx
0x180015f4a  mov     r15, rcx
0x180015f4d  mov     r14, [rbp+140h+arg_20]
0x180015f54  mov     r12, [rbp+140h+arg_28]
0x180015f5b  mov     rsi, [rbp+140h+arg_30]
0x180015f62  mov     dword ptr [rsp+240h+var_208], 0
0x180015f6a  lea     rcx, [rsp+240h+var_208]; this
0x180015f6f  call    ?GetRPCClientProcessId@Shared@DevPlat@@YAJPEAK@Z; DevPlat::Shared::GetRPCClientProcessId(ulong *)
0x180015f74  mov     rcx, [rbp+148h]; this
0x180015f7b  test    eax, eax
0x180015f7d  jns     short loc_180015F94
0x180015f7f  mov     r9d, eax; char *
0x180015f82  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180015f89  mov     edx, 0B2h; void *
0x180015f8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015f94  mov     r8, r15
0x180015f97  mov     edx, dword ptr [rsp+240h+var_208]
0x180015f9b  mov     ecx, 101000h
0x180015fa0  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x180015fa6  mov     rcx, [rbp+148h]; this
0x180015fad  xor     r15d, r15d
0x180015fb0  test    eax, eax
0x180015fb2  jns     short loc_180015FC9
0x180015fb4  mov     r9d, eax; char *
0x180015fb7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180015fbe  mov     edx, 0B4h; void *
0x180015fc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015fc9  mov     [rsp+240h+token], r15
0x180015fce  lea     rdx, [rsp+240h+token]
0x180015fd3  mov     ecx, dword ptr [rsp+240h+var_208]
0x180015fd7  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180015fdd  mov     rcx, [rbp+148h]; this
0x180015fe4  test    eax, eax
0x180015fe6  jns     short loc_180015FFD
0x180015fe8  mov     r9d, eax; char *
0x180015feb  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180015ff2  mov     edx, 0B7h; void *
0x180015ff7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015ffd  mov     [rsp+240h+var_1F0], r15
0x180016002  lea     rdx, [rsp+240h+var_1F0]
0x180016007  mov     rcx, [rsp+240h+token]
0x18001600c  call    cs:__imp_UMgrQueryUserContext
0x180016012  mov     rcx, [rbp+148h]; this
0x180016019  test    eax, eax
0x18001601b  jns     short loc_180016032
0x18001601d  mov     r9d, eax; char *
0x180016020  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016027  mov     edx, 0BBh; void *
0x18001602c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016032  test    rbx, rbx
0x180016035  jz      short loc_18001603F
0x180016037  mov     rax, [rsp+240h+var_1F0]
0x18001603c  mov     [rbx], rax
0x18001603f  test    rdi, rdi
0x180016042  jz      short loc_180016071
0x180016044  mov     rdx, rdi; void *
0x180016047  mov     rcx, [rsp+240h+token]; this
0x18001604c  call    ?GetHostIdFromProcessToken@Shared@DevPlat@@YAJPEAXPEA_K@Z; DevPlat::Shared::GetHostIdFromProcessToken(void *,unsigned __int64 *)
0x180016051  mov     rcx, [rbp+148h]; this
0x180016058  test    eax, eax
0x18001605a  jns     short loc_180016071
0x18001605c  mov     r9d, eax; char *
0x18001605f  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016066  mov     edx, 0C3h; void *
0x18001606b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016071  mov     [rsp+240h+applicationUserModelIdLength], 82h
0x180016079  lea     r8, [rbp+140h+applicationUserModelId]; applicationUserModelId
0x18001607d  lea     rdx, [rsp+240h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180016082  mov     rcx, [rsp+240h+token]; token
0x180016087  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18001608d  mov     rcx, [rbp+148h]; this
0x180016094  test    eax, eax
0x180016096  jz      short loc_1800160AD
0x180016098  mov     r9d, eax; char *
0x18001609b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800160a2  mov     edx, 0C9h; void *
0x1800160a7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800160ad  test    rsi, rsi
0x1800160b0  jz      short loc_1800160E2
0x1800160b2  mov     edx, [r12]; unsigned __int64
0x1800160b6  lea     r8, [rbp+140h+applicationUserModelId]; unsigned __int16 *
0x1800160ba  mov     rcx, rsi; unsigned __int16 *
0x1800160bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800160c2  mov     rcx, [rbp+148h]; this
0x1800160c9  test    eax, eax
0x1800160cb  jns     short loc_1800160E2
0x1800160cd  mov     r9d, eax; char *
0x1800160d0  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800160d7  mov     edx, 0CDh; void *
0x1800160dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800160e2  mov     rcx, [rsp+240h+token]
0x1800160e7  call    ?GetAppInstancingErrorBehaviorPolicy@AppModelPolicy@@YA?AW4AppInstancingErrorBehaviorPolicy@1@PEAX@Z; AppModelPolicy::GetAppInstancingErrorBehaviorPolicy(void *)
0x1800160ec  mov     edi, eax
0x1800160ee  cmp     eax, 380001h
0x1800160f3  jnz     loc_180016276
0x1800160f9  mov     [rsp+240h+var_208], r15
0x1800160fe  lea     rax, [rsp+240h+var_208]
0x180016103  mov     [rsp+240h+var_1E0], rax
0x180016108  mov     [rsp+240h+var_1D8], r15
0x18001610d  mov     [rsp+240h+var_1D0], 1
0x180016112  lea     rdx, [rsp+240h+var_1D8]
0x180016117  xor     ecx, ecx
0x180016119  call    cs:__imp_SRCacheManager_Open
0x18001611f  mov     ebx, eax
0x180016121  lea     rcx, [rsp+240h+var_1E0]
0x180016126  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18001612b  test    ebx, ebx
0x18001612d  jns     short loc_18001614C
0x18001612f  mov     rcx, [rbp+148h]; this
0x180016136  mov     r9d, ebx; char *
0x180016139  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016140  mov     edx, 0A5h; void *
0x180016145  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001614a  jmp     short loc_18001614F
0x18001614c  mov     ebx, r15d
0x18001614f  mov     rcx, [rbp+148h]; this
0x180016156  test    ebx, ebx
0x180016158  jns     short loc_18001616F
0x18001615a  mov     r9d, ebx; char *
0x18001615d  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016164  mov     edx, 0D5h; void *
0x180016169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001616f  mov     [rsp+240h+var_1E8], r15
0x180016174  lea     r8, [rsp+240h+var_1E8]; __int64 *
0x180016179  mov     rdx, [rsp+240h+token]; void *
0x18001617e  lea     rcx, [rsp+240h+var_208]; struct StateRepository::Cache::Manager_NoThrow *
0x180016183  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180016188  mov     rcx, [rbp+148h]; this
0x18001618f  test    eax, eax
0x180016191  jns     short loc_1800161A8
0x180016193  mov     r9d, eax; char *
0x180016196  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001619d  mov     edx, 0D8h; void *
0x1800161a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800161a8  mov     [rsp+240h+var_210], r15b
0x1800161ad  xorps   xmm0, xmm0
0x1800161b0  movdqa  xmmword ptr [rbp+140h+var_1C0], xmm0
0x1800161b5  mov     [rbp+140h+var_1B0], r15
0x1800161b9  mov     [rbp+140h+var_1A8], r15
0x1800161bd  movdqa  [rbp+140h+var_1A0], xmm0
0x1800161c2  xorps   xmm1, xmm1
0x1800161c5  movdqa  [rbp+140h+var_190], xmm1
0x1800161ca  movdqa  [rbp+140h+var_180], xmm0
0x1800161cf  movdqa  [rbp+140h+var_170], xmm1
0x1800161d4  lea     rax, [rsp+240h+var_210]
0x1800161d9  mov     [rsp+240h+var_218], rax
0x1800161de  lea     rax, [rbp+140h+var_1C0]
0x1800161e2  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800161e7  xor     r9d, r9d
0x1800161ea  lea     r8, [rbp+140h+applicationUserModelId]
0x1800161ee  mov     rdx, [rsp+240h+var_1E8]
0x1800161f3  lea     rcx, [rsp+240h+var_208]
0x1800161f8  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1800161fd  mov     rcx, [rbp+148h]; this
0x180016204  test    eax, eax
0x180016206  jns     short loc_18001621D
0x180016208  mov     r9d, eax; char *
0x18001620b  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016212  mov     edx, 0DCh; void *
0x180016217  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001621d  cmp     [rsp+240h+var_210], r15b
0x180016222  setz    al
0x180016225  mov     rcx, [rbp+148h]; this
0x18001622c  test    al, al
0x18001622e  jz      short loc_180016248
0x180016230  mov     r9d, 8000FFFFh; char *
0x180016236  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001623d  mov     edx, 0DDh; void *
0x180016242  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016248  mov     eax, dword ptr [rbp+140h+var_1B0+4]
0x18001624b  shr     eax, 3
0x18001624e  not     al
0x180016250  and     al, 1
0x180016252  mov     [r14], al
0x180016255  lea     rcx, [rbp+140h+var_1C0]; this
0x180016259  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18001625e  nop
0x18001625f  mov     rcx, [rsp+240h+var_208]
0x180016264  mov     [rsp+240h+var_208], r15
0x180016269  test    rcx, rcx
0x18001626c  jz      short loc_180016279
0x18001626e  call    cs:__imp_SRCacheManager_Close
0x180016274  jmp     short loc_180016279
0x180016276  mov     [r14], r15b
0x180016279  cmp     edi, 380000h
0x18001627f  setz    al
0x180016282  mov     [r13+0], al
0x180016286  mov     rcx, [rsp+240h+token]; hObject
0x18001628b  lea     rax, [rcx-1]
0x18001628f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016293  ja      short loc_18001629B
0x180016295  call    cs:__imp_CloseHandle
0x18001629b  mov     rcx, [rbp+140h+var_50]
0x1800162a2  xor     rcx, rsp; StackCookie
0x1800162a5  call    __security_check_cookie
0x1800162aa  add     rsp, 208h
0x1800162b1  pop     r15
0x1800162b3  pop     r14
0x1800162b5  pop     r13
0x1800162b7  pop     r12
0x1800162b9  pop     rdi
0x1800162ba  pop     rsi
0x1800162bb  pop     rbx
0x1800162bc  pop     rbp
0x1800162bd  retn
```
