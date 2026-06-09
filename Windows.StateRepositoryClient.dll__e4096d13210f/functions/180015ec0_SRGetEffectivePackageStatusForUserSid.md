# SRGetEffectivePackageStatusForUserSid

- ea: `0x180015ec0`
- end: `0x180015fea`
- name: `SRGetEffectivePackageStatusForUserSid`
- size: `298`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180015df0`

## callees

- `0x1800075e4`
- `0x1800094a4`
- `0x1800155dc`
- `0x180015824`
- `0x180015ec0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180015f56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180015fcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180015f56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180015fcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180015f00`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180015f00`

## string_xrefs

- `0x180015f19`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall SRGetEffectivePackageStatusForUserSid(PSID Sid, unsigned __int16 *a2, int *a3)
{
  int StatusByPackageFullName; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v10; // rcx
  int v11; // [rsp+20h] [rbp-30h] BYREF
  __int64 v12; // [rsp+28h] [rbp-28h] BYREF
  __int64 *v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+38h] [rbp-18h] BYREF
  char v15; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v17; // [rsp+88h] [rbp+38h] BYREF

  v12 = 0;
  v14 = 0;
  v15 = 1;
  v13 = &v12;
  StatusByPackageFullName = SRCacheManager_Open(0, &v14);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v13);
  if ( StatusByPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
      (const char *)(unsigned int)StatusByPackageFullName,
      v11);
    v7 = 93;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)StatusByPackageFullName,
      v11);
    v8 = v12;
    v12 = 0;
    if ( v8 )
      SRCacheManager_Close(v8);
    return (unsigned int)StatusByPackageFullName;
  }
  v11 = 0;
  LOBYTE(v17) = 0;
  StatusByPackageFullName = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(
                              (struct StateRepository::Cache::Manager_NoThrow *)&v12,
                              a2,
                              (enum StateRepository::Cache::PackageStatus *)&v11,
                              (bool *)&v17);
  if ( StatusByPackageFullName < 0 )
  {
    v7 = 96;
    goto LABEL_3;
  }
  v17 = 0;
  StatusByPackageFullName = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserSidAndPackageFullName(
                              (struct StateRepository::Cache::Manager_NoThrow *)&v12,
                              Sid,
                              a2,
                              (enum StateRepository::Cache::PackageStatus *)&v17);
  if ( StatusByPackageFullName < 0 )
  {
    v7 = 99;
    goto LABEL_3;
  }
  v10 = v12;
  *a3 = v11 | v17;
  v12 = 0;
  if ( v10 )
    SRCacheManager_Close(v10);
  return 0;
}

```

## disassembly

```asm
0x180015ec0  mov     [rsp-18h+arg_0], rbx
0x180015ec5  mov     [rsp-18h+arg_8], rsi
0x180015eca  push    rbp
0x180015ecb  push    rdi
0x180015ecc  push    r14
0x180015ece  mov     rbp, rsp
0x180015ed1  sub     rsp, 50h
0x180015ed5  mov     rdi, rdx
0x180015ed8  mov     [rbp+var_28], 0
0x180015ee0  mov     r14, rcx
0x180015ee3  mov     [rbp+var_18], 0
0x180015eeb  lea     rax, [rbp+var_28]
0x180015eef  mov     [rbp+var_10], 1
0x180015ef3  lea     rdx, [rbp+var_18]
0x180015ef7  mov     [rbp+var_20], rax
0x180015efb  xor     ecx, ecx
0x180015efd  mov     rsi, r8
0x180015f00  call    cs:__imp_SRCacheManager_Open
0x180015f06  lea     rcx, [rbp+var_20]
0x180015f0a  mov     ebx, eax
0x180015f0c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180015f11  test    ebx, ebx
0x180015f13  jns     short loc_180015F60
0x180015f15  mov     rcx, [rbp+18h]; this
0x180015f19  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x180015f20  mov     r9d, ebx; char *
0x180015f23  mov     edx, 0A5h; void *
0x180015f28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f2d  mov     edx, 5Dh ; ']'; void *
0x180015f32  mov     rcx, [rbp+18h]; this
0x180015f36  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180015f3d  mov     r9d, ebx; char *
0x180015f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f45  mov     rcx, [rbp+var_28]
0x180015f49  mov     [rbp+var_28], 0
0x180015f51  test    rcx, rcx
0x180015f54  jz      short loc_180015F5C
0x180015f56  call    cs:__imp_SRCacheManager_Close
0x180015f5c  mov     eax, ebx
0x180015f5e  jmp     short loc_180015FD7
0x180015f60  lea     r9, [rbp+arg_18]; bool *
0x180015f64  mov     [rbp+var_30], 0
0x180015f6b  lea     r8, [rbp+var_30]; enum StateRepository::Cache::PackageStatus *
0x180015f6f  mov     byte ptr [rbp+arg_18], 0
0x180015f73  mov     rdx, rdi; unsigned __int16 *
0x180015f76  lea     rcx, [rbp+var_28]; struct StateRepository::Cache::Manager_NoThrow *
0x180015f7a  call    ?GetStatusByPackageFullName@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAW4PackageStatus@34@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::PackageStatus &,bool &)
0x180015f7f  mov     ebx, eax
0x180015f81  test    eax, eax
0x180015f83  jns     short loc_180015F8C
0x180015f85  mov     edx, 60h ; '`'
0x180015f8a  jmp     short loc_180015F32
0x180015f8c  lea     r9, [rbp+arg_18]; enum StateRepository::Cache::PackageStatus *
0x180015f90  mov     [rbp+arg_18], 0
0x180015f97  mov     r8, rdi; unsigned __int16 *
0x180015f9a  lea     rcx, [rbp+var_28]; struct StateRepository::Cache::Manager_NoThrow *
0x180015f9e  mov     rdx, r14; Sid
0x180015fa1  call    ?GetStatusByUserSidAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXPEBGAEAW4PackageStatus@34@@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserSidAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,void *,ushort const *,StateRepository::Cache::PackageStatus &)
0x180015fa6  mov     ebx, eax
0x180015fa8  test    eax, eax
0x180015faa  jns     short loc_180015FB6
0x180015fac  mov     edx, 63h ; 'c'
0x180015fb1  jmp     loc_180015F32
0x180015fb6  mov     rcx, [rbp+var_28]
0x180015fba  mov     eax, [rbp+arg_18]
0x180015fbd  or      eax, [rbp+var_30]
0x180015fc0  mov     [rsi], eax
0x180015fc2  mov     [rbp+var_28], 0
0x180015fca  test    rcx, rcx
0x180015fcd  jz      short loc_180015FD5
0x180015fcf  call    cs:__imp_SRCacheManager_Close
0x180015fd5  xor     eax, eax
0x180015fd7  mov     rbx, [rsp+50h+arg_0]
0x180015fdc  mov     rsi, [rsp+50h+arg_8]
0x180015fe1  add     rsp, 50h
0x180015fe5  pop     r14
0x180015fe7  pop     rdi
0x180015fe8  pop     rbp
0x180015fe9  retn
```
