# GetPackageExecutionContextForAumidAndUser

- ea: `0x18002c930`
- end: `0x18002cc51`
- name: `GetPackageExecutionContextForAumidAndUser`
- size: `801`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180029270`
- `0x18007ea90`
- `0x18008e2b0`

## callees

- `0x180007120`
- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x18002c900`
- `0x18002c930`
- `0x18002cd1c`
- `0x18002d5e0`
- `0x18002dce8`
- `0x18005b3c4`
- `0x18005e96c`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002c987`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002c987`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002ca14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002ca14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002ca6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002caf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002cbef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002cc25`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002ca6a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002caf7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002cbef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002cc25`

## string_xrefs

- `0x18002c997`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002c9cf`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002ca49`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002ca8b`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002cad6`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002cb1e`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002cb96`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002cbc2`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18002ca31`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall GetPackageExecutionContextForAumidAndUser(const unsigned __int16 *a1, __int64 a2, _DWORD *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int token_information; // eax
  __int64 v9; // rcx
  int v10; // eax
  void *v12; // rbx
  int v13; // eax
  __int64 v14; // r9
  unsigned int v15; // edi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-69h]
  int v21; // [rsp+20h] [rbp-69h]
  int v22; // [rsp+20h] [rbp-69h]
  __int64 v23; // [rsp+30h] [rbp-59h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-51h] BYREF
  __int64 v25; // [rsp+40h] [rbp-49h] BYREF
  char v26; // [rsp+48h] [rbp-41h]
  int v27[4]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v28; // [rsp+60h] [rbp-29h]
  __int128 v29; // [rsp+68h] [rbp-21h]
  __int64 v30; // [rsp+78h] [rbp-11h]
  __int64 v31; // [rsp+80h] [rbp-9h]
  __int64 v32; // [rsp+88h] [rbp-1h]
  __int128 v33; // [rsp+90h] [rbp+7h]
  int v34; // [rsp+A0h] [rbp+17h]
  __int64 v35; // [rsp+A8h] [rbp+1Fh]
  __int64 v36; // [rsp+B0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  __int64 v38; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v39; // [rsp+100h] [rbp+77h] BYREF
  void *Block; // [rsp+108h] [rbp+7Fh] BYREF

  *a3 = 0;
  Block = 0;
  if ( a2 && (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
  {
    v38 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v38,
      0);
    v6 = UMgrQueryUserToken(a2, &v38);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)v6,
        v20);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      return v7;
    }
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v38);
    v7 = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)token_information,
        v20);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v38);
  }
  else
  {
    v10 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)v10,
        v20);
LABEL_13:
      if ( Block )
        operator delete(Block);
      return v7;
    }
  }
  v39 = 0;
  v24 = &v39;
  v25 = 0;
  v26 = 1;
  v7 = SRCacheManager_Open(0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v24);
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v7,
      v20);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)v7,
      v21);
    v9 = v39;
    v39 = 0;
    if ( v9 )
      SRCacheManager_Close();
    goto LABEL_13;
  }
  v12 = Block;
  v23 = 0;
  v13 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
          (struct StateRepository::Cache::Manager_NoThrow *)&v39,
          *(PSID *)Block,
          &v23);
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)(unsigned int)v13,
      v20);
LABEL_18:
    v16 = v39;
    v39 = 0;
    if ( v16 )
      SRCacheManager_Close();
    if ( v12 )
      operator delete(v12);
    return v15;
  }
  if ( !v23 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)0x80070002LL,
      v20);
LABEL_29:
    v18 = v39;
    v39 = 0;
    if ( v18 )
      SRCacheManager_Close();
    if ( v12 )
      operator delete(v12);
    return 2147942402LL;
  }
  LOBYTE(v38) = 0;
  *(_OWORD *)v27 = 0;
  v28 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v17 = StateRepository::Cache::Entity::Package_NoThrow::GetByUserAndApplicationUserModelId(
          (struct StateRepository::Cache::Manager_NoThrow *)&v39,
          v23,
          a1,
          v14,
          (__int64)v27,
          (bool *)&v38);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)(unsigned int)v17,
      v22);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v27);
    goto LABEL_18;
  }
  if ( !(_BYTE)v38 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)0x80070002LL,
      v22);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v27);
    goto LABEL_29;
  }
  *a3 = 1;
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v27);
  v19 = v39;
  v39 = 0;
  if ( v19 )
    SRCacheManager_Close();
  if ( v12 )
    operator delete(v12);
  return 0;
}

```

## disassembly

```asm
0x18002c930  mov     [rsp-8+arg_0], rbx
0x18002c935  push    rbp
0x18002c936  push    rsi
0x18002c937  push    rdi
0x18002c938  push    r14
0x18002c93a  push    r15
0x18002c93c  lea     rbp, [rsp-37h]
0x18002c941  sub     rsp, 0C0h
0x18002c948  xor     r15d, r15d
0x18002c94b  mov     rsi, r8
0x18002c94e  mov     [r8], r15d
0x18002c951  mov     rbx, rdx
0x18002c954  mov     [rbp+57h+Block], r15
0x18002c958  mov     r14, rcx
0x18002c95b  test    rdx, rdx
0x18002c95e  jz      loc_18002CA72
0x18002c964  call    IsUMgrOpenProcessHandleForAccessPresent
0x18002c969  test    al, al
0x18002c96b  jz      loc_18002CA72
0x18002c971  xor     edx, edx
0x18002c973  mov     [rbp+57h+arg_8], r15
0x18002c977  lea     rcx, [rbp+57h+arg_8]
0x18002c97b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002c980  lea     rdx, [rbp+57h+arg_8]
0x18002c984  mov     rcx, rbx
0x18002c987  call    cs:__imp_UMgrQueryUserToken
0x18002c98d  mov     ebx, eax
0x18002c98f  test    eax, eax
0x18002c991  jns     short loc_18002C9B8
0x18002c993  mov     rcx, [rbp+5Fh]; this
0x18002c997  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c99e  mov     r9d, eax; char *
0x18002c9a1  lea     edx, [r15+17h]; void *
0x18002c9a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9aa  lea     rcx, [rbp+57h+arg_8]
0x18002c9ae  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c9b3  jmp     loc_18002CAAD
0x18002c9b8  mov     rdx, [rbp+57h+arg_8]
0x18002c9bc  lea     rcx, [rbp+57h+Block]
0x18002c9c0  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002c9c5  mov     ebx, eax
0x18002c9c7  test    eax, eax
0x18002c9c9  jns     short loc_18002C9F1
0x18002c9cb  mov     rcx, [rbp+5Fh]; this
0x18002c9cf  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002c9d6  mov     r9d, eax; char *
0x18002c9d9  mov     edx, 18h; void *
0x18002c9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9e3  lea     rcx, [rbp+57h+arg_8]
0x18002c9e7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c9ec  jmp     loc_18002CA9F
0x18002c9f1  lea     rcx, [rbp+57h+arg_8]
0x18002c9f5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002c9fa  lea     rax, [rbp+57h+arg_10]
0x18002c9fe  mov     [rbp+57h+arg_10], r15
0x18002ca02  lea     rdx, [rbp+57h+var_A0]
0x18002ca06  mov     [rbp+57h+var_A8], rax
0x18002ca0a  xor     ecx, ecx
0x18002ca0c  mov     [rbp+57h+var_A0], r15
0x18002ca10  mov     [rbp+57h+var_98], 1
0x18002ca14  call    cs:__imp_SRCacheManager_Open
0x18002ca1a  lea     rcx, [rbp+57h+var_A8]
0x18002ca1e  mov     ebx, eax
0x18002ca20  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18002ca25  test    ebx, ebx
0x18002ca27  jns     loc_18002CAB4
0x18002ca2d  mov     rcx, [rbp+5Fh]; this
0x18002ca31  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002ca38  mov     r9d, ebx; char *
0x18002ca3b  mov     edx, 0A5h; void *
0x18002ca40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca45  mov     rcx, [rbp+5Fh]; this
0x18002ca49  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002ca50  mov     r9d, ebx; char *
0x18002ca53  mov     edx, 1Ch; void *
0x18002ca58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca5d  mov     rcx, [rbp+57h+arg_10]
0x18002ca61  mov     [rbp+57h+arg_10], r15
0x18002ca65  test    rcx, rcx
0x18002ca68  jz      short loc_18002CA9F
0x18002ca6a  call    cs:__imp_SRCacheManager_Close
0x18002ca70  jmp     short loc_18002CA9F
0x18002ca72  xor     edx, edx
0x18002ca74  lea     rcx, [rbp+57h+Block]
0x18002ca78  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18002ca7d  mov     ebx, eax
0x18002ca7f  test    eax, eax
0x18002ca81  jns     loc_18002C9FA
0x18002ca87  mov     rcx, [rbp+5Fh]; this
0x18002ca8b  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002ca92  mov     r9d, eax; char *
0x18002ca95  mov     edx, 12h; void *
0x18002ca9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ca9f  mov     rcx, [rbp+57h+Block]; Block
0x18002caa3  test    rcx, rcx
0x18002caa6  jz      short loc_18002CAAD
0x18002caa8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002caad  mov     eax, ebx
0x18002caaf  jmp     loc_18002CC3A
0x18002cab4  mov     rbx, [rbp+57h+Block]
0x18002cab8  lea     r8, [rbp+57h+var_B0]; __int64 *
0x18002cabc  mov     [rbp+57h+var_B0], r15
0x18002cac0  lea     rcx, [rbp+57h+arg_10]; struct StateRepository::Cache::Manager_NoThrow *
0x18002cac4  mov     rdx, [rbx]; Sid
0x18002cac7  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18002cacc  mov     edi, eax
0x18002cace  test    eax, eax
0x18002cad0  jns     short loc_18002CB11
0x18002cad2  mov     rcx, [rbp+5Fh]; this
0x18002cad6  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002cadd  mov     r9d, eax; char *
0x18002cae0  mov     edx, 1Fh; void *
0x18002cae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002caea  mov     rcx, [rbp+57h+arg_10]
0x18002caee  mov     [rbp+57h+arg_10], r15
0x18002caf2  test    rcx, rcx
0x18002caf5  jz      short loc_18002CAFD
0x18002caf7  call    cs:__imp_SRCacheManager_Close
0x18002cafd  test    rbx, rbx
0x18002cb00  jz      short loc_18002CB0A
0x18002cb02  mov     rcx, rbx; Block
0x18002cb05  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cb0a  mov     eax, edi
0x18002cb0c  jmp     loc_18002CC3A
0x18002cb11  mov     rdx, [rbp+57h+var_B0]
0x18002cb15  test    rdx, rdx
0x18002cb18  jnz     short loc_18002CB3A
0x18002cb1a  mov     rcx, [rbp+5Fh]; this
0x18002cb1e  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002cb25  mov     r9d, 80070002h; char *
0x18002cb2b  mov     edx, 20h ; ' '; void *
0x18002cb30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cb35  jmp     loc_18002CBE2
0x18002cb3a  xorps   xmm0, xmm0
0x18002cb3d  mov     byte ptr [rbp+57h+arg_8], r15b
0x18002cb41  lea     rax, [rbp+57h+arg_8]
0x18002cb45  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x18002cb4a  mov     [rsp+0E0h+var_B8], rax
0x18002cb4f  lea     rcx, [rbp+57h+arg_10]
0x18002cb53  lea     rax, [rbp+57h+var_90]
0x18002cb57  mov     [rbp+57h+var_80], r15
0x18002cb5b  xorps   xmm1, xmm1
0x18002cb5e  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18002cb63  mov     r8, r14
0x18002cb66  mov     [rbp+57h+var_68], r15
0x18002cb6a  movups  [rbp+57h+var_78], xmm1
0x18002cb6e  mov     [rbp+57h+var_60], r15
0x18002cb72  mov     [rbp+57h+var_58], r15
0x18002cb76  movdqa  [rbp+57h+var_50], xmm0
0x18002cb7b  mov     [rbp+57h+var_40], r15d
0x18002cb7f  mov     [rbp+57h+var_38], r15
0x18002cb83  mov     [rbp+57h+var_30], r15
0x18002cb87  call    ?GetByUserAndApplicationUserModelId@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18002cb8c  mov     edi, eax
0x18002cb8e  test    eax, eax
0x18002cb90  jns     short loc_18002CBB8
0x18002cb92  mov     rcx, [rbp+5Fh]; this
0x18002cb96  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002cb9d  mov     r9d, eax; char *
0x18002cba0  mov     edx, 25h ; '%'; void *
0x18002cba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cbaa  lea     rcx, [rbp+57h+var_90]; this
0x18002cbae  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002cbb3  jmp     loc_18002CAEA
0x18002cbb8  cmp     byte ptr [rbp+57h+arg_8], r15b
0x18002cbbc  jnz     short loc_18002CC09
0x18002cbbe  mov     rcx, [rbp+5Fh]; this
0x18002cbc2  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002cbc9  mov     r9d, 80070002h; char *
0x18002cbcf  mov     edx, 26h ; '&'; void *
0x18002cbd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cbd9  lea     rcx, [rbp+57h+var_90]; this
0x18002cbdd  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002cbe2  mov     rcx, [rbp+57h+arg_10]
0x18002cbe6  mov     [rbp+57h+arg_10], r15
0x18002cbea  test    rcx, rcx
0x18002cbed  jz      short loc_18002CBF5
0x18002cbef  call    cs:__imp_SRCacheManager_Close
0x18002cbf5  test    rbx, rbx
0x18002cbf8  jz      short loc_18002CC02
0x18002cbfa  mov     rcx, rbx; Block
0x18002cbfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cc02  mov     eax, 80070002h
0x18002cc07  jmp     short loc_18002CC3A
0x18002cc09  lea     rcx, [rbp+57h+var_90]; this
0x18002cc0d  mov     dword ptr [rsi], 1
0x18002cc13  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18002cc18  mov     rcx, [rbp+57h+arg_10]
0x18002cc1c  mov     [rbp+57h+arg_10], r15
0x18002cc20  test    rcx, rcx
0x18002cc23  jz      short loc_18002CC2B
0x18002cc25  call    cs:__imp_SRCacheManager_Close
0x18002cc2b  test    rbx, rbx
0x18002cc2e  jz      short loc_18002CC38
0x18002cc30  mov     rcx, rbx; Block
0x18002cc33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002cc38  xor     eax, eax
0x18002cc3a  mov     rbx, [rsp+0E0h+arg_0]
0x18002cc42  add     rsp, 0C0h
0x18002cc49  pop     r15
0x18002cc4b  pop     r14
0x18002cc4d  pop     rdi
0x18002cc4e  pop     rsi
0x18002cc4f  pop     rbp
0x18002cc50  retn
```
