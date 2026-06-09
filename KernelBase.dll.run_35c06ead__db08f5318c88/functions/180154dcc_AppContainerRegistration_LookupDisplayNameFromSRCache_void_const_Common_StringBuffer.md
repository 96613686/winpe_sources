# AppContainerRegistration::LookupDisplayNameFromSRCache(void * const,Common::StringBuffer *)

- ea: `0x180154dcc`
- end: `0x180155213`
- name: `?LookupDisplayNameFromSRCache@AppContainerRegistration@@CAJQEAXPEAVStringBuffer@Common@@@Z`
- size: `1095`
- prototype: `static int(void *const, struct Common::StringBuffer *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800bea54`
- `0x1800bebac`

## callees

- `0x18002c6dc`
- `0x18002cd6c`
- `0x18002ce88`
- `0x18002da14`
- `0x18002f738`
- `0x18002fd98`
- `0x180056ec0`
- `0x180058768`
- `0x18006961c`
- `0x1800ead10`
- `0x1800fe940`
- `0x18012c864`
- `0x18012d119`
- `0x180154dcc`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180154e19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180154e19`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180154fed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801550f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015517f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801551de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180154fed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801550f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015517f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801551de`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180154ea5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180155117`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18015519d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801551fc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180154ea5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180155117`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18015519d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1801551fc`

## string_xrefs

- `0x180154e35`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`

## pseudocode

```c
__int64 __fastcall AppContainerRegistration::LookupDisplayNameFromSRCache(
        void *const a1,
        struct Common::StringBuffer *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-E0h]
  bool v9; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v11; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v12; // [rsp+E8h] [rbp-18h] BYREF
  char v13; // [rsp+F0h] [rbp-10h]
  __int64 v14[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v15[72]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v16; // [rsp+158h] [rbp+58h]
  __int64 v17; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v13 = 1;
  v11 = &v10;
  v10 = 0;
  v12 = 0;
  v3 = SRCacheManager_Open(0, &v12);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v11);
  if ( v3 >= 0 )
  {
    v3 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)(unsigned int)v3,
      v8);
    if ( v3 == -2140733419 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x338,
        (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
        (const char *)0x80070002LL,
        v8);
LABEL_13:
      v7 = v10;
      v10 = 0;
      if ( v7 )
        SRCacheManager_Close(v7);
      return 2147942402LL;
    }
  }
  if ( v3 >= 0 )
  {
    *(_OWORD *)v14 = 0;
    memset_0(v15, 0, 0x44u);
    v16 = 0;
    v17 = 0;
    v9 = 0;
    v3 = AppContainerRegistration::SRCachePackageFamilyFromSid(v6, &v10, a1, 0);
    if ( v3 >= 0 )
    {
      StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)v14);
      goto LABEL_13;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33E,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v3,
      (int)v14);
    StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x339,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v3,
      v8);
  }
  v4 = v10;
  v10 = 0;
  if ( v4 )
    SRCacheManager_Close(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180154dcc  mov     [rsp-8+arg_10], rbx
0x180154dd1  mov     [rsp-8+arg_18], rsi
0x180154dd6  push    rbp
0x180154dd7  push    rdi
0x180154dd8  push    r14
0x180154dda  lea     rbp, [rsp-80h]
0x180154ddf  sub     rsp, 180h
0x180154de6  mov     rax, cs:__security_cookie
0x180154ded  xor     rax, rsp
0x180154df0  mov     [rbp+90h+var_20], rax
0x180154df4  mov     rsi, rdx
0x180154df7  mov     [rbp+90h+var_A0], 1
0x180154dfb  mov     rdi, rcx
0x180154dfe  lea     rax, [rsp+190h+var_158]
0x180154e03  xor     r14d, r14d
0x180154e06  mov     [rbp+90h+var_B0], rax
0x180154e0a  lea     rdx, [rbp+90h+var_A8]
0x180154e0e  mov     [rsp+190h+var_158], r14
0x180154e13  xor     ecx, ecx
0x180154e15  mov     [rbp+90h+var_A8], r14
0x180154e19  call    cs:__imp_SRCacheManager_Open
0x180154e1f  lea     rcx, [rbp+90h+var_B0]
0x180154e23  mov     ebx, eax
0x180154e25  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180154e2a  test    ebx, ebx
0x180154e2c  jns     short loc_180154E74
0x180154e2e  mov     rcx, [rbp+98h]; this
0x180154e35  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180154e3c  mov     r9d, ebx; char *
0x180154e3f  mov     edx, 0A5h; void *
0x180154e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154e49  cmp     ebx, 80670015h
0x180154e4f  jnz     short loc_180154E77
0x180154e51  mov     rcx, [rbp+98h]; this
0x180154e58  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x180154e5f  mov     r9d, 80070002h; char *
0x180154e65  mov     edx, 338h; void *
0x180154e6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154e6f  jmp     loc_180155108
0x180154e74  mov     ebx, r14d
0x180154e77  test    ebx, ebx
0x180154e79  jns     short loc_180154EB2
0x180154e7b  mov     rcx, [rbp+98h]; this
0x180154e82  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x180154e89  mov     r9d, ebx; char *
0x180154e8c  mov     edx, 339h; void *
0x180154e91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154e96  mov     rcx, [rsp+190h+var_158]
0x180154e9b  mov     [rsp+190h+var_158], r14
0x180154ea0  test    rcx, rcx
0x180154ea3  jz      short loc_180154EAB
0x180154ea5  call    cs:__imp_SRCacheManager_Close
0x180154eab  mov     eax, ebx
0x180154ead  jmp     loc_180155122
0x180154eb2  xor     edx, edx; Val
0x180154eb4  lea     rcx, [rbp+90h+var_80]; void *
0x180154eb8  xorps   xmm0, xmm0
0x180154ebb  movdqa  xmmword ptr [rbp+90h+var_90], xmm0
0x180154ec0  lea     r8d, [rdx+44h]; Size
0x180154ec4  call    memset_0
0x180154ec9  lea     rax, [rsp+190h+var_160]
0x180154ece  mov     [rbp+90h+var_38], r14
0x180154ed2  mov     [rsp+190h+var_168], rax
0x180154ed7  lea     rdx, [rsp+190h+var_158]
0x180154edc  lea     rax, [rbp+90h+var_90]
0x180154ee0  mov     [rbp+90h+var_30], r14
0x180154ee4  xor     r9d, r9d
0x180154ee7  mov     qword ptr [rsp+190h+var_170], rax; int
0x180154eec  mov     r8, rdi
0x180154eef  mov     [rsp+190h+var_160], r14b
0x180154ef4  call    ?SRCachePackageFamilyFromSid@AppContainerRegistration@@CAJPEBU_GUID@@AEAVManager_NoThrow@Cache@StateRepository@@PEAXW4CacheFlags@PackageFamily_NoThrow@Entity@45@AEAV7845@AEA_N@Z; AppContainerRegistration::SRCachePackageFamilyFromSid(_GUID const *,StateRepository::Cache::Manager_NoThrow &,void *,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x180154ef9  mov     ebx, eax
0x180154efb  test    eax, eax
0x180154efd  jns     short loc_180154F28
0x180154eff  mov     edx, 33Eh; void *
0x180154f04  mov     rcx, [rbp+98h]; this
0x180154f0b  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x180154f12  mov     r9d, ebx; char *
0x180154f15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154f1a  lea     rcx, [rbp+90h+var_90]; this
0x180154f1e  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180154f23  jmp     loc_180154E96
0x180154f28  cmp     [rsp+190h+var_160], r14b
0x180154f2d  jz      loc_1801550FF
0x180154f33  lea     r8, [rsp+190h+var_130]; __int64 *
0x180154f38  mov     [rsp+190h+var_130], r14
0x180154f3d  xor     edx, edx; void *
0x180154f3f  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180154f44  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180154f49  mov     ebx, eax
0x180154f4b  test    eax, eax
0x180154f4d  jns     short loc_180154F56
0x180154f4f  mov     edx, 347h
0x180154f54  jmp     short loc_180154F04
0x180154f56  mov     rdx, [rsp+190h+var_130]; __int64
0x180154f5b  test    rdx, rdx
0x180154f5e  jz      loc_1801550FF
0x180154f64  mov     r8, [rbp+90h+var_90]; __int64
0x180154f68  lea     r9, [rsp+190h+var_160]; bool *
0x180154f6d  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180154f72  mov     [rsp+190h+var_160], r14b
0x180154f77  call    ?ExistsByUserAndPackageFamily@PackageFamilyUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageFamilyUser_NoThrow::ExistsByUserAndPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x180154f7c  mov     ebx, eax
0x180154f7e  test    eax, eax
0x180154f80  jns     short loc_180154F8C
0x180154f82  mov     edx, 34Fh
0x180154f87  jmp     loc_180154F04
0x180154f8c  cmp     [rsp+190h+var_160], r14b
0x180154f91  jz      loc_1801550FF
0x180154f97  mov     rdx, [rbp+90h+var_90]; __int64
0x180154f9b  lea     r8, [rsp+190h+var_148]; struct StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *
0x180154fa0  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180154fa5  mov     [rsp+190h+var_148], r14
0x180154faa  mov     [rsp+190h+var_140], r14d
0x180154faf  mov     [rsp+190h+var_138], r14
0x180154fb4  call    ?FindByPackageFamily@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JAEAVPackageIndexIterator_NoThrow@234@@Z; StateRepository::Cache::Entity::Package_NoThrow::FindByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageIndexIterator_NoThrow &)
0x180154fb9  mov     ebx, eax
0x180154fbb  test    eax, eax
0x180154fbd  jns     short loc_180154FF8
0x180154fbf  mov     rcx, [rbp+98h]; this
0x180154fc6  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x180154fcd  mov     r9d, eax; char *
0x180154fd0  mov     edx, 358h; void *
0x180154fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154fda  mov     rcx, [rsp+190h+var_148]
0x180154fdf  mov     [rsp+190h+var_148], r14
0x180154fe4  test    rcx, rcx
0x180154fe7  jz      loc_180154F1A
0x180154fed  call    cs:__imp_SRCacheContext_Close
0x180154ff3  jmp     loc_180154F1A
0x180154ff8  xorps   xmm0, xmm0
0x180154ffb  mov     [rbp+90h+var_110], r14
0x180154fff  lea     r9, [rsp+190h+var_160]
0x180155004  movdqa  xmmword ptr [rsp+190h+var_120], xmm0
0x18015500a  lea     r8, [rsp+190h+var_120]
0x18015500f  movdqa  [rbp+90h+var_E0], xmm0
0x180155014  mov     edx, 1004h
0x180155019  mov     [rbp+90h+var_108], r14
0x18015501d  lea     rcx, [rsp+190h+var_148]
0x180155022  mov     [rbp+90h+var_100], r14
0x180155026  mov     [rbp+90h+var_F8], r14
0x18015502a  mov     [rbp+90h+var_F0], r14
0x18015502e  mov     [rbp+90h+var_E8], r14
0x180155032  mov     [rbp+90h+var_D0], r14d
0x180155036  mov     [rbp+90h+var_C8], r14
0x18015503a  mov     [rbp+90h+var_C0], r14
0x18015503e  mov     [rsp+190h+var_160], r14b
0x180155043  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180155048  mov     ebx, eax
0x18015504a  test    eax, eax
0x18015504c  jns     loc_1801550D8
0x180155052  mov     edx, 35Dh; void *
0x180155057  mov     rcx, [rbp+98h]; this
0x18015505e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x180155065  mov     r9d, ebx; char *
0x180155068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015506d  lea     rcx, [rsp+190h+var_120]; this
0x180155072  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180155077  jmp     loc_180154FDA
0x18015507c  cmp     dword ptr [rbp+90h+var_108], 1
0x180155080  jnz     short loc_1801550B5
0x180155082  mov     r8, [rsp+190h+var_120]; __int64
0x180155087  lea     r9, [rsp+190h+var_150]; bool *
0x18015508c  mov     rdx, [rsp+190h+var_130]; __int64
0x180155091  lea     rcx, [rsp+190h+var_158]; struct StateRepository::Cache::Manager_NoThrow *
0x180155096  mov     [rsp+190h+var_150], r14b
0x18015509b  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x1801550a0  mov     edi, eax
0x1801550a2  test    eax, eax
0x1801550a4  js      loc_1801551AA
0x1801550aa  cmp     [rsp+190h+var_150], r14b
0x1801550af  jnz     loc_180155146
0x1801550b5  lea     r9, [rsp+190h+var_160]
0x1801550ba  mov     edx, 1004h
0x1801550bf  lea     r8, [rsp+190h+var_120]
0x1801550c4  lea     rcx, [rsp+190h+var_148]
0x1801550c9  call    ?GetNext@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1801550ce  mov     ebx, eax
0x1801550d0  test    eax, eax
0x1801550d2  js      loc_180155209
0x1801550d8  mov     bl, [rsp+190h+var_160]
0x1801550dc  test    bl, bl
0x1801550de  jnz     short loc_18015507C
0x1801550e0  lea     rcx, [rsp+190h+var_120]; this
0x1801550e5  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1801550ea  mov     rcx, [rsp+190h+var_148]
0x1801550ef  mov     [rsp+190h+var_148], r14
0x1801550f4  test    rcx, rcx
0x1801550f7  jz      short loc_1801550FF
0x1801550f9  call    cs:__imp_SRCacheContext_Close
0x1801550ff  lea     rcx, [rbp+90h+var_90]; this
0x180155103  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x180155108  mov     rcx, [rsp+190h+var_158]
0x18015510d  mov     [rsp+190h+var_158], r14
0x180155112  test    rcx, rcx
0x180155115  jz      short loc_18015511D
0x180155117  call    cs:__imp_SRCacheManager_Close
0x18015511d  mov     eax, 80070002h
0x180155122  mov     rcx, [rbp+90h+var_20]
0x180155126  xor     rcx, rsp; StackCookie
0x180155129  call    __security_check_cookie
0x18015512e  lea     r11, [rsp+190h+var_10]
0x180155136  mov     rbx, [r11+30h]
0x18015513a  mov     rsi, [r11+38h]
0x18015513e  mov     rsp, r11
0x180155141  pop     r14
0x180155143  pop     rdi
0x180155144  pop     rbp
0x180155145  retn
0x180155146  test    bl, bl
0x180155148  jz      short loc_1801550E0
0x18015514a  mov     rdx, [rbp+90h+var_C8]; unsigned __int16 *
0x18015514e  mov     rcx, rsi; this
0x180155151  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x180155156  mov     ebx, eax
0x180155158  test    eax, eax
0x18015515a  jns     short loc_180155166
0x18015515c  mov     edx, 374h
0x180155161  jmp     loc_180155057
0x180155166  lea     rcx, [rsp+190h+var_120]; this
0x18015516b  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180155170  mov     rcx, [rsp+190h+var_148]
0x180155175  mov     [rsp+190h+var_148], r14
0x18015517a  test    rcx, rcx
0x18015517d  jz      short loc_180155185
0x18015517f  call    cs:__imp_SRCacheContext_Close
0x180155185  lea     rcx, [rbp+90h+var_90]; this
0x180155189  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x18015518e  mov     rcx, [rsp+190h+var_158]
0x180155193  mov     [rsp+190h+var_158], r14
0x180155198  test    rcx, rcx
0x18015519b  jz      short loc_1801551A3
0x18015519d  call    cs:__imp_SRCacheManager_Close
0x1801551a3  xor     eax, eax
0x1801551a5  jmp     loc_180155122
0x1801551aa  mov     rcx, [rbp+98h]; this
0x1801551b1  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1801551b8  mov     r9d, edi; char *
0x1801551bb  mov     edx, 363h; void *
0x1801551c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801551c5  lea     rcx, [rsp+190h+var_120]; this
0x1801551ca  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1801551cf  mov     rcx, [rsp+190h+var_148]
0x1801551d4  mov     [rsp+190h+var_148], r14
0x1801551d9  test    rcx, rcx
0x1801551dc  jz      short loc_1801551E4
0x1801551de  call    cs:__imp_SRCacheContext_Close
0x1801551e4  lea     rcx, [rbp+90h+var_90]; this
0x1801551e8  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1801551ed  mov     rcx, [rsp+190h+var_158]
0x1801551f2  mov     [rsp+190h+var_158], r14
0x1801551f7  test    rcx, rcx
0x1801551fa  jz      short loc_180155202
0x1801551fc  call    cs:__imp_SRCacheManager_Close
0x180155202  mov     eax, edi
0x180155204  jmp     loc_180155122
0x180155209  mov     edx, 36Bh
0x18015520e  jmp     loc_180155057
```
