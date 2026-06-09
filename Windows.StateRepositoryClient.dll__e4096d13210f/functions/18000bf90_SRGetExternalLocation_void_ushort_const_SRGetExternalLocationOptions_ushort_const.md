# SRGetExternalLocation(void *,ushort const *,SRGetExternalLocationOptions,ushort const * *)

- ea: `0x18000bf90`
- end: `0x18000c269`
- name: `?SRGetExternalLocation@@YAJPEAXPEBGW4SRGetExternalLocationOptions@@PEAPEBG@Z`
- size: `729`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation`

## callees

- `0x1800075e4`
- `0x180009220`
- `0x1800094a4`
- `0x1800094d4`
- `0x18000a1c4`
- `0x18000a464`
- `0x18000a914`
- `0x18000a9bc`
- `0x18000bf90`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c072`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c114`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c24a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c072`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c114`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000c24a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c05b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c101`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c1e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c05b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c101`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000c1e2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000c009`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000c009`

## string_xrefs

- `0x18000c022`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall SRGetExternalLocation(void *a1, const unsigned __int16 *a2, char a3, _QWORD *a4)
{
  int v6; // ebx
  void *v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  int *v19; // [rsp+20h] [rbp-60h]
  __int64 v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  __int64 *v22; // [rsp+48h] [rbp-38h] BYREF
  __int64 v23; // [rsp+50h] [rbp-30h] BYREF
  char v24; // [rsp+58h] [rbp-28h]
  int v25[4]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v26; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  __int64 v28; // [rsp+C8h] [rbp+48h] BYREF

  *a4 = 0;
  if ( (a3 & 1) == 0 )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)0x80070057LL,
      (int)v19);
    return (unsigned int)v6;
  }
  v28 = 0;
  v23 = 0;
  v24 = 1;
  v22 = &v28;
  *(_OWORD *)v25 = 0;
  v26 = 0;
  v6 = SRCacheManager_Open(0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v22);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
      (const char *)(unsigned int)v6,
      (int)v19);
    v9 = 328;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)(unsigned int)v6,
      (int)v19);
    v10 = v28;
    v28 = 0;
    if ( v10 )
      SRCacheManager_Close(v10);
    v11 = *((_QWORD *)&v26 + 1);
    *((_QWORD *)&v26 + 1) = 0;
    if ( v11 )
      SRCache_Free(v11);
    return (unsigned int)v6;
  }
  v20 = 0;
  v21 = 0;
  if ( a1 )
  {
    v6 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
           (struct StateRepository::Cache::Manager_NoThrow *)&v28,
           a1,
           &v21);
    if ( v6 < 0 )
    {
      v9 = 337;
      goto LABEL_6;
    }
  }
  else
  {
    v6 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
           (struct StateRepository::Cache::Manager_NoThrow *)&v28,
           v8,
           &v21);
    if ( v6 < 0 )
    {
      v9 = 341;
      goto LABEL_6;
    }
  }
  if ( v21 )
  {
    v12 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v28,
            a2,
            &v20);
    if ( v12 < 0 )
    {
      v13 = 345;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
        (const char *)(unsigned int)v12,
        (int)v19);
      v14 = v28;
      v28 = 0;
      if ( v14 )
        SRCacheManager_Close(v14);
      v15 = *((_QWORD *)&v26 + 1);
      *((_QWORD *)&v26 + 1) = 0;
      if ( v15 )
        SRCache_Free(v15);
      return (unsigned int)v12;
    }
    if ( !v20 )
      goto LABEL_27;
    v19 = v25;
    v12 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
            (struct StateRepository::Cache::Manager_NoThrow *)&v28,
            v21,
            v20);
    if ( v12 < 0 )
    {
      v13 = 350;
      goto LABEL_18;
    }
  }
  v16 = v20;
  if ( v20 )
  {
LABEL_30:
    v19 = v25;
    v12 = StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(
            (struct StateRepository::Cache::Manager_NoThrow *)&v28,
            0,
            v16);
    if ( v12 < 0 )
    {
      v13 = 369;
      goto LABEL_18;
    }
    goto LABEL_32;
  }
LABEL_27:
  v12 = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v28,
          a2,
          &v20);
  if ( v12 < 0 )
  {
    v13 = 362;
    goto LABEL_18;
  }
  v16 = v20;
  if ( v20 )
    goto LABEL_30;
LABEL_32:
  v17 = v28;
  v28 = 0;
  if ( v17 )
    SRCacheManager_Close(v17);
  v18 = *((_QWORD *)&v26 + 1);
  *((_QWORD *)&v26 + 1) = 0;
  if ( v18 )
    SRCache_Free(v18);
  return 0;
}

```

## disassembly

```asm
0x18000bf90  mov     [rsp-28h+arg_0], rbx
0x18000bf95  push    rbp
0x18000bf96  push    rsi
0x18000bf97  push    rdi
0x18000bf98  push    r14
0x18000bf9a  push    r15
0x18000bf9c  mov     rbp, rsp
0x18000bf9f  sub     rsp, 80h
0x18000bfa6  xor     r15d, r15d
0x18000bfa9  mov     r14, r9
0x18000bfac  mov     [r9], r15
0x18000bfaf  mov     rsi, rdx
0x18000bfb2  mov     rdi, rcx
0x18000bfb5  test    r8b, 1
0x18000bfb9  jnz     short loc_18000BFDF
0x18000bfbb  mov     rcx, [rbp+28h]; this
0x18000bfbf  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000bfc6  mov     ebx, 80070057h
0x18000bfcb  mov     edx, 141h; void *
0x18000bfd0  mov     r9d, ebx; char *
0x18000bfd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bfd8  mov     eax, ebx
0x18000bfda  jmp     loc_18000C252
0x18000bfdf  xorps   xmm0, xmm0
0x18000bfe2  mov     [rbp+arg_18], r15
0x18000bfe6  xorps   xmm1, xmm1
0x18000bfe9  mov     [rbp+var_30], r15
0x18000bfed  lea     rax, [rbp+arg_18]
0x18000bff1  mov     [rbp+var_28], 1
0x18000bff5  lea     rdx, [rbp+var_30]
0x18000bff9  mov     [rbp+var_38], rax
0x18000bffd  xor     ecx, ecx
0x18000bfff  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18000c004  movdqu  [rbp+var_10], xmm1
0x18000c009  call    cs:__imp_SRCacheManager_Open
0x18000c00f  lea     rcx, [rbp+var_38]
0x18000c013  mov     ebx, eax
0x18000c015  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18000c01a  test    ebx, ebx
0x18000c01c  jns     short loc_18000C07D
0x18000c01e  mov     rcx, [rbp+28h]; this
0x18000c022  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x18000c029  mov     r9d, ebx; char *
0x18000c02c  mov     edx, 0A5h; void *
0x18000c031  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c036  mov     edx, 148h; void *
0x18000c03b  mov     rcx, [rbp+28h]; this
0x18000c03f  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c046  mov     r9d, ebx; char *
0x18000c049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c04e  mov     rcx, [rbp+arg_18]
0x18000c052  mov     [rbp+arg_18], r15
0x18000c056  test    rcx, rcx
0x18000c059  jz      short loc_18000C061
0x18000c05b  call    cs:__imp_SRCacheManager_Close
0x18000c061  mov     rcx, qword ptr [rbp+var_10+8]
0x18000c065  mov     qword ptr [rbp+var_10+8], r15
0x18000c069  test    rcx, rcx
0x18000c06c  jz      loc_18000BFD8
0x18000c072  call    cs:__imp_SRCache_Free
0x18000c078  jmp     loc_18000BFD8
0x18000c07d  mov     [rbp+var_50], r15
0x18000c081  lea     r8, [rbp+var_48]; __int64 *
0x18000c085  mov     [rbp+var_48], r15
0x18000c089  lea     rcx, [rbp+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18000c08d  test    rdi, rdi
0x18000c090  jz      short loc_18000C0A7
0x18000c092  mov     rdx, rdi; Sid
0x18000c095  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18000c09a  mov     ebx, eax
0x18000c09c  test    eax, eax
0x18000c09e  jns     short loc_18000C0B9
0x18000c0a0  mov     edx, 151h
0x18000c0a5  jmp     short loc_18000C03B
0x18000c0a7  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18000c0ac  mov     ebx, eax
0x18000c0ae  test    eax, eax
0x18000c0b0  jns     short loc_18000C0B9
0x18000c0b2  mov     edx, 155h
0x18000c0b7  jmp     short loc_18000C03B
0x18000c0b9  mov     rbx, r15
0x18000c0bc  cmp     [rbp+var_48], r15
0x18000c0c0  jz      loc_18000C169
0x18000c0c6  lea     r8, [rbp+var_50]; __int64 *
0x18000c0ca  mov     rdx, rsi; unsigned __int16 *
0x18000c0cd  lea     rcx, [rbp+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18000c0d1  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000c0d6  mov     edi, eax
0x18000c0d8  test    eax, eax
0x18000c0da  jns     short loc_18000C121
0x18000c0dc  mov     edx, 159h; void *
0x18000c0e1  mov     rcx, [rbp+28h]; this
0x18000c0e5  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c0ec  mov     r9d, edi; char *
0x18000c0ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0f4  mov     rcx, [rbp+arg_18]
0x18000c0f8  mov     [rbp+arg_18], r15
0x18000c0fc  test    rcx, rcx
0x18000c0ff  jz      short loc_18000C107
0x18000c101  call    cs:__imp_SRCacheManager_Close
0x18000c107  mov     rcx, qword ptr [rbp+var_10+8]
0x18000c10b  mov     qword ptr [rbp+var_10+8], r15
0x18000c10f  test    rcx, rcx
0x18000c112  jz      short loc_18000C11A
0x18000c114  call    cs:__imp_SRCache_Free
0x18000c11a  mov     eax, edi
0x18000c11c  jmp     loc_18000C252
0x18000c121  mov     r8, [rbp+var_50]
0x18000c125  test    r8, r8
0x18000c128  jz      short loc_18000C172
0x18000c12a  mov     rdx, [rbp+var_48]
0x18000c12e  lea     rax, [rbp+arg_10]
0x18000c132  mov     [rsp+80h+var_58], rax
0x18000c137  lea     rcx, [rbp+arg_18]
0x18000c13b  lea     rax, [rbp+var_20]
0x18000c13f  mov     [rbp+arg_10], r15b
0x18000c143  mov     qword ptr [rsp+80h+var_60], rax
0x18000c148  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18000c14d  mov     edi, eax
0x18000c14f  test    eax, eax
0x18000c151  jns     short loc_18000C15A
0x18000c153  mov     edx, 15Eh
0x18000c158  jmp     short loc_18000C0E1
0x18000c15a  cmp     [rbp+arg_10], r15b
0x18000c15e  jz      short loc_18000C169
0x18000c160  mov     rbx, qword ptr [rbp+var_10+8]
0x18000c164  test    rbx, rbx
0x18000c167  jnz     short loc_18000C1D5
0x18000c169  mov     r8, [rbp+var_50]
0x18000c16d  test    r8, r8
0x18000c170  jnz     short loc_18000C19B
0x18000c172  lea     r8, [rbp+var_50]; __int64 *
0x18000c176  mov     rdx, rsi; unsigned __int16 *
0x18000c179  lea     rcx, [rbp+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x18000c17d  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000c182  mov     edi, eax
0x18000c184  test    eax, eax
0x18000c186  jns     short loc_18000C192
0x18000c188  mov     edx, 16Ah
0x18000c18d  jmp     loc_18000C0E1
0x18000c192  mov     r8, [rbp+var_50]
0x18000c196  test    r8, r8
0x18000c199  jz      short loc_18000C1D5
0x18000c19b  lea     rax, [rbp+arg_10]
0x18000c19f  mov     [rbp+arg_10], r15b
0x18000c1a3  mov     [rsp+80h+var_58], rax
0x18000c1a8  lea     rcx, [rbp+arg_18]
0x18000c1ac  lea     rax, [rbp+var_20]
0x18000c1b0  xor     edx, edx
0x18000c1b2  mov     qword ptr [rsp+80h+var_60], rax; int
0x18000c1b7  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18000c1bc  mov     edi, eax
0x18000c1be  test    eax, eax
0x18000c1c0  jns     short loc_18000C1CC
0x18000c1c2  mov     edx, 171h
0x18000c1c7  jmp     loc_18000C0E1
0x18000c1cc  cmp     [rbp+arg_10], r15b
0x18000c1d0  cmovnz  rbx, qword ptr [rbp+var_10+8]
0x18000c1d5  mov     rcx, [rbp+arg_18]
0x18000c1d9  mov     [rbp+arg_18], r15
0x18000c1dd  test    rcx, rcx
0x18000c1e0  jz      short loc_18000C1E8
0x18000c1e2  call    cs:__imp_SRCacheManager_Close
0x18000c1e8  test    rbx, rbx
0x18000c1eb  jz      short loc_18000C23D
0x18000c1ed  mov     rdx, rbx
0x18000c1f0  lea     rcx, [rbp+var_40]
0x18000c1f4  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000c1f9  mov     rax, [rbp+var_40]
0x18000c1fd  test    rax, rax
0x18000c200  jnz     short loc_18000C22D
0x18000c202  mov     rcx, [rbp+28h]; this
0x18000c206  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000c20d  mov     ebx, 8007000Eh
0x18000c212  mov     edx, 17Dh; void *
0x18000c217  mov     r9d, ebx; char *
0x18000c21a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c21f  lea     rcx, [rbp+var_40]
0x18000c223  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c228  jmp     loc_18000C061
0x18000c22d  lea     rcx, [rbp+var_40]
0x18000c231  mov     [rbp+var_40], r15
0x18000c235  mov     [r14], rax
0x18000c238  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000c23d  mov     rcx, qword ptr [rbp+var_10+8]
0x18000c241  mov     qword ptr [rbp+var_10+8], r15
0x18000c245  test    rcx, rcx
0x18000c248  jz      short loc_18000C250
0x18000c24a  call    cs:__imp_SRCache_Free
0x18000c250  xor     eax, eax
0x18000c252  mov     rbx, [rsp+80h+arg_0]
0x18000c25a  add     rsp, 80h
0x18000c261  pop     r15
0x18000c263  pop     r14
0x18000c265  pop     rdi
0x18000c266  pop     rsi
0x18000c267  pop     rbp
0x18000c268  retn
```
