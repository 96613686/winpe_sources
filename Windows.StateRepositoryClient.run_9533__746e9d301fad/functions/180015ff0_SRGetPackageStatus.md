# SRGetPackageStatus

- ea: `0x180015ff0`
- end: `0x180016102`
- name: `SRGetPackageStatus`
- size: `274`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800075e4`
- `0x1800094a4`
- `0x1800155dc`
- `0x180015ff0`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800160c3`
- `api-ms-win-appmodel-runtime-l1-1-1!VerifyPackageFullName` at `0x1800160c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001607d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800160ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18001607d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800160ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180016027`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180016027`

## string_xrefs

- `0x180016040`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Manager.hpp`

## pseudocode

```c
__int64 __fastcall SRGetPackageStatus(unsigned __int16 *a1, _DWORD *a2)
{
  LONG StatusByPackageFullName; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  char v12; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  bool v14; // [rsp+70h] [rbp+30h] BYREF
  int v15; // [rsp+78h] [rbp+38h] BYREF

  v9 = 0;
  v11 = 0;
  v12 = 1;
  v10 = &v9;
  StatusByPackageFullName = SRCacheManager_Open(0, &v11);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v10);
  if ( StatusByPackageFullName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Manager.hpp",
      (const char *)(unsigned int)StatusByPackageFullName,
      v9);
    v5 = 22;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)StatusByPackageFullName,
      v9);
    v6 = v9;
    v9 = 0;
    if ( v6 )
      SRCacheManager_Close(v6);
    return (unsigned int)StatusByPackageFullName;
  }
  v15 = 0;
  v14 = 0;
  StatusByPackageFullName = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(
                              (struct StateRepository::Cache::Manager_NoThrow *)&v9,
                              a1,
                              (enum StateRepository::Cache::PackageStatus *)&v15,
                              &v14);
  if ( StatusByPackageFullName < 0 )
  {
    v5 = 26;
    goto LABEL_3;
  }
  if ( v14 )
  {
    *a2 = v15;
  }
  else
  {
    StatusByPackageFullName = VerifyPackageFullName(a1);
    if ( StatusByPackageFullName < 0 )
    {
      v5 = 34;
      goto LABEL_3;
    }
    *a2 = 0;
  }
  v8 = v9;
  v9 = 0;
  if ( v8 )
    SRCacheManager_Close(v8);
  return 0;
}

```

## disassembly

```asm
0x180015ff0  mov     [rsp-18h+arg_0], rbx
0x180015ff5  push    rbp
0x180015ff6  push    rsi
0x180015ff7  push    rdi
0x180015ff8  mov     rbp, rsp
0x180015ffb  sub     rsp, 40h
0x180015fff  mov     rdi, rdx
0x180016002  mov     [rbp+var_20], 0
0x18001600a  mov     rsi, rcx
0x18001600d  mov     [rbp+var_10], 0
0x180016015  lea     rax, [rbp+var_20]
0x180016019  mov     [rbp+var_8], 1
0x18001601d  lea     rdx, [rbp+var_10]
0x180016021  mov     [rbp+var_18], rax
0x180016025  xor     ecx, ecx
0x180016027  call    cs:__imp_SRCacheManager_Open
0x18001602d  lea     rcx, [rbp+var_18]
0x180016031  mov     ebx, eax
0x180016033  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x180016038  test    ebx, ebx
0x18001603a  jns     short loc_180016087
0x18001603c  mov     rcx, [rbp+18h]; this
0x180016040  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\StateRepositor"...
0x180016047  mov     r9d, ebx; char *
0x18001604a  mov     edx, 0A5h; void *
0x18001604f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016054  mov     edx, 16h; void *
0x180016059  mov     rcx, [rbp+18h]; this
0x18001605d  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016064  mov     r9d, ebx; char *
0x180016067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001606c  mov     rcx, [rbp+var_20]
0x180016070  mov     [rbp+var_20], 0
0x180016078  test    rcx, rcx
0x18001607b  jz      short loc_180016083
0x18001607d  call    cs:__imp_SRCacheManager_Close
0x180016083  mov     eax, ebx
0x180016085  jmp     short loc_1800160F5
0x180016087  lea     r9, [rbp+arg_10]; bool *
0x18001608b  mov     [rbp+arg_18], 0
0x180016092  lea     r8, [rbp+arg_18]; enum StateRepository::Cache::PackageStatus *
0x180016096  mov     [rbp+arg_10], 0
0x18001609a  mov     rdx, rsi; unsigned __int16 *
0x18001609d  lea     rcx, [rbp+var_20]; struct StateRepository::Cache::Manager_NoThrow *
0x1800160a1  call    ?GetStatusByPackageFullName@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEAW4PackageStatus@34@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetStatusByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::PackageStatus &,bool &)
0x1800160a6  mov     ebx, eax
0x1800160a8  test    eax, eax
0x1800160aa  jns     short loc_1800160B3
0x1800160ac  mov     edx, 1Ah
0x1800160b1  jmp     short loc_180016059
0x1800160b3  cmp     [rbp+arg_10], 0
0x1800160b7  jz      short loc_1800160C0
0x1800160b9  mov     eax, [rbp+arg_18]
0x1800160bc  mov     [rdi], eax
0x1800160be  jmp     short loc_1800160DC
0x1800160c0  mov     rcx, rsi; packageFullName
0x1800160c3  call    cs:__imp_VerifyPackageFullName
0x1800160c9  mov     ebx, eax
0x1800160cb  test    eax, eax
0x1800160cd  jns     short loc_1800160D6
0x1800160cf  mov     edx, 22h ; '"'
0x1800160d4  jmp     short loc_180016059
0x1800160d6  mov     dword ptr [rdi], 0
0x1800160dc  mov     rcx, [rbp+var_20]
0x1800160e0  mov     [rbp+var_20], 0
0x1800160e8  test    rcx, rcx
0x1800160eb  jz      short loc_1800160F3
0x1800160ed  call    cs:__imp_SRCacheManager_Close
0x1800160f3  xor     eax, eax
0x1800160f5  mov     rbx, [rsp+40h+arg_0]
0x1800160fa  add     rsp, 40h
0x1800160fe  pop     rdi
0x1800160ff  pop     rsi
0x180016100  pop     rbp
0x180016101  retn
```
