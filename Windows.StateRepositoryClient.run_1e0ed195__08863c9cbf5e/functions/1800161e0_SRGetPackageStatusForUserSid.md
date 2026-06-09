# SRGetPackageStatusForUserSid

- ea: `0x1800161e0`
- end: `0x1800162e7`
- name: `SRGetPackageStatusForUserSid`
- size: `263`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180016110`

## callees

- `0x1800075e4`
- `0x1800094a4`
- `0x180015824`
- `0x180016110`
- `0x1800161e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180016285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800162cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180016285`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800162cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18001622f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18001622f`

## string_xrefs

- `0x180016248`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall SRGetPackageStatusForUserSid(PSID Sid, unsigned __int16 *a2, _DWORD *a3)
{
  int StatusByUserSidAndPackageFullName; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 *v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  char v13; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v15; // [rsp+60h] [rbp+20h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  if ( !Sid )
    return SRGetPackageStatusForUserFromToken();
  v16 = 0;
  v11 = &v16;
  v12 = 0;
  v13 = 1;
  StatusByUserSidAndPackageFullName = SRCacheManager_Open(0, &v12);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v11);
  if ( StatusByUserSidAndPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
      (const char *)(unsigned int)StatusByUserSidAndPackageFullName,
      (int)v11);
    v8 = 62;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)StatusByUserSidAndPackageFullName,
      (int)v11);
    v9 = v16;
    v16 = 0;
    if ( v9 )
      SRCacheManager_Close(v9);
    return (unsigned int)StatusByUserSidAndPackageFullName;
  }
  v15 = 0;
  StatusByUserSidAndPackageFullName = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserSidAndPackageFullName(
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v16,
                                        Sid,
                                        a2,
                                        (enum StateRepository::Cache::PackageStatus *)&v15);
  if ( StatusByUserSidAndPackageFullName < 0 )
  {
    v8 = 65;
    goto LABEL_5;
  }
  v10 = v16;
  *a3 = v15;
  v16 = 0;
  if ( v10 )
    SRCacheManager_Close(v10);
  return 0;
}

```

## disassembly

```asm
0x1800161e0  mov     [rsp-18h+arg_8], rbx
0x1800161e5  mov     [rsp-18h+arg_10], rsi
0x1800161ea  push    rbp
0x1800161eb  push    rdi
0x1800161ec  push    r14
0x1800161ee  mov     rbp, rsp
0x1800161f1  sub     rsp, 40h
0x1800161f5  mov     rdi, r8
0x1800161f8  mov     rsi, rdx
0x1800161fb  mov     r14, rcx
0x1800161fe  test    rcx, rcx
0x180016201  jnz     short loc_18001620D
0x180016203  call    SRGetPackageStatusForUserFromToken
0x180016208  jmp     loc_1800162D4
0x18001620d  lea     rax, [rbp+arg_18]
0x180016211  mov     [rbp+arg_18], 0
0x180016219  lea     rdx, [rbp+var_18]
0x18001621d  mov     [rbp+var_20], rax
0x180016221  xor     ecx, ecx
0x180016223  mov     [rbp+var_18], 0
0x18001622b  mov     [rbp+var_10], 1
0x18001622f  call    cs:__imp_SRCacheManager_Open
0x180016235  lea     rcx, [rbp+var_20]
0x180016239  mov     ebx, eax
0x18001623b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180016240  test    ebx, ebx
0x180016242  jns     short loc_18001628F
0x180016244  mov     rcx, [rbp+18h]; this
0x180016248  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x18001624f  mov     r9d, ebx; char *
0x180016252  mov     edx, 0A5h; void *
0x180016257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001625c  mov     edx, 3Eh ; '>'; void *
0x180016261  mov     rcx, [rbp+18h]; this
0x180016265  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x18001626c  mov     r9d, ebx; char *
0x18001626f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016274  mov     rcx, [rbp+arg_18]
0x180016278  mov     [rbp+arg_18], 0
0x180016280  test    rcx, rcx
0x180016283  jz      short loc_18001628B
0x180016285  call    cs:__imp_SRCacheManager_Close
0x18001628b  mov     eax, ebx
0x18001628d  jmp     short loc_1800162D4
0x18001628f  lea     r9, [rbp+arg_0]; enum StateRepository::Cache::PackageStatus *
0x180016293  mov     [rbp+arg_0], 0
0x18001629a  mov     r8, rsi; unsigned __int16 *
0x18001629d  lea     rcx, [rbp+arg_18]; struct StateRepository::Cache::Manager_NoThrow *
0x1800162a1  mov     rdx, r14; Sid
0x1800162a4  call    ?GetStatusByUserSidAndPackageFullName@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXPEBGAEAW4PackageStatus@34@@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::GetStatusByUserSidAndPackageFullName(StateRepository::Cache::Manager_NoThrow &,void *,ushort const *,StateRepository::Cache::PackageStatus &)
0x1800162a9  mov     ebx, eax
0x1800162ab  test    eax, eax
0x1800162ad  jns     short loc_1800162B6
0x1800162af  mov     edx, 41h ; 'A'
0x1800162b4  jmp     short loc_180016261
0x1800162b6  mov     rcx, [rbp+arg_18]
0x1800162ba  mov     eax, [rbp+arg_0]
0x1800162bd  mov     [rdi], eax
0x1800162bf  mov     [rbp+arg_18], 0
0x1800162c7  test    rcx, rcx
0x1800162ca  jz      short loc_1800162D2
0x1800162cc  call    cs:__imp_SRCacheManager_Close
0x1800162d2  xor     eax, eax
0x1800162d4  mov     rbx, [rsp+40h+arg_8]
0x1800162d9  mov     rsi, [rsp+40h+arg_10]
0x1800162de  add     rsp, 40h
0x1800162e2  pop     r14
0x1800162e4  pop     rdi
0x1800162e5  pop     rbp
0x1800162e6  retn
```
