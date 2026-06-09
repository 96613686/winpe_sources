# GetPackageExecutionContextForPackageByFamilyNameAndUser

- ea: `0x18008e300`
- end: `0x18008e680`
- name: `GetPackageExecutionContextForPackageByFamilyNameAndUser`
- size: `896`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x18002c900`
- `0x18002cd1c`
- `0x18002d5e0`
- `0x18003f0a0`
- `0x18005ae90`
- `0x18005b3c4`
- `0x18005ba40`
- `0x18005e96c`
- `0x18008df24`
- `0x18008e300`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008e369`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008e369`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18008e402`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18008e402`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e60f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e648`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e45b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e510`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e60f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18008e648`

## string_xrefs

- `0x18008e379`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e3b5`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e438`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e47d`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e4ed`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e535`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e5b1`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e5df`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\packageexecutioncontext.cpp`
- `0x18008e420`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall GetPackageExecutionContextForPackageByFamilyNameAndUser(
        unsigned __int16 *a1,
        __int64 a2,
        _DWORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int token_information; // eax
  __int64 v7; // rcx
  int v8; // eax
  void *v10; // rbx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  bool v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  char v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v26[72]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v27; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *a3 = 0;
  Block = 0;
  if ( a2 && (unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent() )
  {
    v20 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v20,
      0);
    v4 = UMgrQueryUserToken(a2, &v20);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)v4,
        v16);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      return v5;
    }
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v20);
    v5 = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)token_information,
        v16);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  }
  else
  {
    v8 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, 0);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
        (const char *)(unsigned int)v8,
        v16);
LABEL_13:
      if ( Block )
        operator delete(Block);
      return v5;
    }
  }
  v19 = 0;
  v22 = &v19;
  v23 = 0;
  v24 = 1;
  v5 = SRCacheManager_Open(0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v22);
  if ( (v5 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
      (const char *)v5,
      v16);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)v5,
      v17);
    v7 = v19;
    v19 = 0;
    if ( v7 )
      SRCacheManager_Close();
    goto LABEL_13;
  }
  v25 = 0;
  memset_0(v26, 0, 0x44u);
  v10 = Block;
  v27 = 0;
  v18[0] = 0;
  v12 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(&v19, *(_QWORD *)Block, v11, &v25);
  v13 = v12;
  if ( v12 >= 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)0x80070002LL,
      (int)v18);
    v15 = v19;
    v19 = 0;
    if ( v15 )
      SRCacheManager_Close();
    if ( v10 )
      operator delete(v10);
    return 2147942402LL;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\packageexecutioncontext.cpp",
      (const char *)(unsigned int)v12,
      (int)v18);
    v14 = v19;
    v19 = 0;
    if ( v14 )
      SRCacheManager_Close();
    if ( v10 )
      operator delete(v10);
    return v13;
  }
}

```

## disassembly

```asm
0x18008e300  mov     [rsp-8+arg_18], rbx
0x18008e305  push    rbp
0x18008e306  push    rsi
0x18008e307  push    rdi
0x18008e308  push    r14
0x18008e30a  push    r15
0x18008e30c  lea     rbp, [rsp-50h]
0x18008e311  sub     rsp, 150h
0x18008e318  mov     rax, cs:__security_cookie
0x18008e31f  xor     rax, rsp
0x18008e322  mov     [rbp+70h+var_30], rax
0x18008e326  xor     r15d, r15d
0x18008e329  mov     rsi, r8
0x18008e32c  mov     [r8], r15d
0x18008e32f  mov     rbx, rdx
0x18008e332  mov     [rsp+170h+Block], r15
0x18008e337  mov     r14, rcx
0x18008e33a  test    rdx, rdx
0x18008e33d  jz      loc_18008E463
0x18008e343  call    IsUMgrOpenProcessHandleForAccessPresent
0x18008e348  test    al, al
0x18008e34a  jz      loc_18008E463
0x18008e350  xor     edx, edx
0x18008e352  mov     [rsp+170h+var_130], r15
0x18008e357  lea     rcx, [rsp+170h+var_130]
0x18008e35c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18008e361  lea     rdx, [rsp+170h+var_130]
0x18008e366  mov     rcx, rbx
0x18008e369  call    cs:__imp_UMgrQueryUserToken
0x18008e36f  mov     ebx, eax
0x18008e371  test    eax, eax
0x18008e373  jns     short loc_18008E39C
0x18008e375  mov     rcx, [rbp+78h]; this
0x18008e379  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e380  mov     r9d, eax; char *
0x18008e383  mov     edx, 84h; void *
0x18008e388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e38d  lea     rcx, [rsp+170h+var_130]
0x18008e392  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e397  jmp     loc_18008E4A0
0x18008e39c  mov     rdx, [rsp+170h+var_130]
0x18008e3a1  lea     rcx, [rsp+170h+Block]
0x18008e3a6  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18008e3ab  mov     ebx, eax
0x18008e3ad  test    eax, eax
0x18008e3af  jns     short loc_18008E3D8
0x18008e3b1  mov     rcx, [rbp+78h]; this
0x18008e3b5  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e3bc  mov     r9d, eax; char *
0x18008e3bf  mov     edx, 85h; void *
0x18008e3c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e3c9  lea     rcx, [rsp+170h+var_130]
0x18008e3ce  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e3d3  jmp     loc_18008E491
0x18008e3d8  lea     rcx, [rsp+170h+var_130]
0x18008e3dd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008e3e2  lea     rax, [rsp+170h+var_138]
0x18008e3e7  mov     [rsp+170h+var_138], r15
0x18008e3ec  lea     rdx, [rsp+170h+var_118]
0x18008e3f1  mov     [rsp+170h+var_120], rax
0x18008e3f6  xor     ecx, ecx
0x18008e3f8  mov     [rsp+170h+var_118], r15
0x18008e3fd  mov     [rsp+170h+var_110], 1
0x18008e402  call    cs:__imp_SRCacheManager_Open
0x18008e408  lea     rcx, [rsp+170h+var_120]
0x18008e40d  mov     ebx, eax
0x18008e40f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18008e414  test    ebx, ebx
0x18008e416  jns     loc_18008E4A7
0x18008e41c  mov     rcx, [rbp+78h]; this
0x18008e420  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18008e427  mov     r9d, ebx; char *
0x18008e42a  mov     edx, 0A5h; void *
0x18008e42f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e434  mov     rcx, [rbp+78h]; this
0x18008e438  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e43f  mov     r9d, ebx; char *
0x18008e442  mov     edx, 89h; void *
0x18008e447  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e44c  mov     rcx, [rsp+170h+var_138]
0x18008e451  mov     [rsp+170h+var_138], r15
0x18008e456  test    rcx, rcx
0x18008e459  jz      short loc_18008E491
0x18008e45b  call    cs:__imp_SRCacheManager_Close
0x18008e461  jmp     short loc_18008E491
0x18008e463  xor     edx, edx
0x18008e465  lea     rcx, [rsp+170h+Block]
0x18008e46a  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18008e46f  mov     ebx, eax
0x18008e471  test    eax, eax
0x18008e473  jns     loc_18008E3E2
0x18008e479  mov     rcx, [rbp+78h]; this
0x18008e47d  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e484  mov     r9d, eax; char *
0x18008e487  mov     edx, 7Fh; void *
0x18008e48c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e491  mov     rcx, [rsp+170h+Block]; Block
0x18008e496  test    rcx, rcx
0x18008e499  jz      short loc_18008E4A0
0x18008e49b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008e4a0  mov     eax, ebx
0x18008e4a2  jmp     loc_18008E65D
0x18008e4a7  xor     edx, edx; Val
0x18008e4a9  mov     [rbp+70h+var_90], r15
0x18008e4ad  lea     rcx, [rbp+70h+var_88]; void *
0x18008e4b1  lea     r8d, [rdx+44h]; Size
0x18008e4b5  call    memset_0
0x18008e4ba  mov     rbx, [rsp+170h+Block]
0x18008e4bf  lea     rax, [rsp+170h+var_140]
0x18008e4c4  mov     [rbp+70h+var_40], r15
0x18008e4c8  lea     r9, [rbp+70h+var_90]
0x18008e4cc  lea     rcx, [rsp+170h+var_138]
0x18008e4d1  mov     [rsp+170h+var_140], r15b
0x18008e4d6  mov     qword ptr [rsp+170h+var_150], rax; int
0x18008e4db  mov     rdx, [rbx]
0x18008e4de  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x18008e4e3  mov     edi, eax
0x18008e4e5  test    eax, eax
0x18008e4e7  jns     short loc_18008E52A
0x18008e4e9  mov     rcx, [rbp+78h]; this
0x18008e4ed  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e4f4  mov     r9d, eax; char *
0x18008e4f7  mov     edx, 8Dh; void *
0x18008e4fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e501  mov     rcx, [rsp+170h+var_138]
0x18008e506  mov     [rsp+170h+var_138], r15
0x18008e50b  test    rcx, rcx
0x18008e50e  jz      short loc_18008E516
0x18008e510  call    cs:__imp_SRCacheManager_Close
0x18008e516  test    rbx, rbx
0x18008e519  jz      short loc_18008E523
0x18008e51b  mov     rcx, rbx; Block
0x18008e51e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008e523  mov     eax, edi
0x18008e525  jmp     loc_18008E65D
0x18008e52a  cmp     [rsp+170h+var_140], r15b
0x18008e52f  jnz     short loc_18008E551
0x18008e531  mov     rcx, [rbp+78h]; this
0x18008e535  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e53c  mov     r9d, 80070002h; char *
0x18008e542  mov     edx, 8Eh; void *
0x18008e547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e54c  jmp     loc_18008E600
0x18008e551  xorps   xmm0, xmm0
0x18008e554  mov     [rsp+170h+var_140], r15b
0x18008e559  xorps   xmm1, xmm1
0x18008e55c  movdqa  [rsp+170h+var_100], xmm0
0x18008e562  lea     rax, [rsp+170h+var_140]
0x18008e567  movdqa  [rbp+70h+var_C0], xmm0
0x18008e56c  lea     r9, [rsp+170h+var_100]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x18008e571  mov     qword ptr [rsp+170h+var_150], rax; int
0x18008e576  lea     r8, [rbp+70h+var_90]; struct StateRepository::Cache::Entity::User_NoThrow *
0x18008e57a  mov     [rbp+70h+var_F0], r15
0x18008e57e  mov     rdx, r14; unsigned __int16 *
0x18008e581  mov     [rbp+70h+var_D8], r15
0x18008e585  lea     rcx, [rsp+170h+var_138]; struct StateRepository::Cache::Manager_NoThrow *
0x18008e58a  mov     [rbp+70h+var_D0], r15
0x18008e58e  movups  [rbp+70h+var_E8], xmm1
0x18008e592  mov     [rbp+70h+var_C8], r15
0x18008e596  mov     [rbp+70h+var_B0], r15d
0x18008e59a  mov     [rbp+70h+var_A8], r15
0x18008e59e  mov     [rbp+70h+var_A0], r15
0x18008e5a2  call    ?GetMainOrOptionalPackageForUser@@YAJAEAVManager_NoThrow@Cache@StateRepository@@PEBGAEAVUser_NoThrow@Entity@23@AEAVPackage_NoThrow@523@AEA_N@Z; GetMainOrOptionalPackageForUser(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18008e5a7  mov     edi, eax
0x18008e5a9  test    eax, eax
0x18008e5ab  jns     short loc_18008E5D4
0x18008e5ad  mov     rcx, [rbp+78h]; this
0x18008e5b1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e5b8  mov     r9d, eax; char *
0x18008e5bb  mov     edx, 92h; void *
0x18008e5c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e5c5  lea     rcx, [rsp+170h+var_100]; this
0x18008e5ca  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18008e5cf  jmp     loc_18008E501
0x18008e5d4  cmp     [rsp+170h+var_140], r15b
0x18008e5d9  jnz     short loc_18008E629
0x18008e5db  mov     rcx, [rbp+78h]; this
0x18008e5df  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008e5e6  mov     r9d, 80070002h; char *
0x18008e5ec  mov     edx, 93h; void *
0x18008e5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e5f6  lea     rcx, [rsp+170h+var_100]; this
0x18008e5fb  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18008e600  mov     rcx, [rsp+170h+var_138]
0x18008e605  mov     [rsp+170h+var_138], r15
0x18008e60a  test    rcx, rcx
0x18008e60d  jz      short loc_18008E615
0x18008e60f  call    cs:__imp_SRCacheManager_Close
0x18008e615  test    rbx, rbx
0x18008e618  jz      short loc_18008E622
0x18008e61a  mov     rcx, rbx; Block
0x18008e61d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008e622  mov     eax, 80070002h
0x18008e627  jmp     short loc_18008E65D
0x18008e629  lea     rcx, [rsp+170h+var_100]; this
0x18008e62e  mov     dword ptr [rsi], 1
0x18008e634  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18008e639  mov     rcx, [rsp+170h+var_138]
0x18008e63e  mov     [rsp+170h+var_138], r15
0x18008e643  test    rcx, rcx
0x18008e646  jz      short loc_18008E64E
0x18008e648  call    cs:__imp_SRCacheManager_Close
0x18008e64e  test    rbx, rbx
0x18008e651  jz      short loc_18008E65B
0x18008e653  mov     rcx, rbx; Block
0x18008e656  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008e65b  xor     eax, eax
0x18008e65d  mov     rcx, [rbp+70h+var_30]
0x18008e661  xor     rcx, rsp; StackCookie
0x18008e664  call    __security_check_cookie
0x18008e669  mov     rbx, [rsp+170h+arg_18]
0x18008e671  add     rsp, 150h
0x18008e678  pop     r15
0x18008e67a  pop     r14
0x18008e67c  pop     rdi
0x18008e67d  pop     rsi
0x18008e67e  pop     rbp
0x18008e67f  retn
```
