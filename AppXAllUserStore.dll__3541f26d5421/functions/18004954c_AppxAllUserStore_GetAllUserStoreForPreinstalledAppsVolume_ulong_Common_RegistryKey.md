# AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(ulong,Common::RegistryKey &)

- ea: `0x18004954c`
- end: `0x180049632`
- name: `?GetAllUserStoreForPreinstalledAppsVolume@AppxAllUserStore@@YAJKAEAVRegistryKey@Common@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(REGSAM samDesired, PHKEY phkResult, struct Common::RegistryKey *)`
- caller_count: `18`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180010eac`
- `0x1800124c0`
- `0x180013a60`
- `0x180014694`
- `0x180029c74`
- `0x18002a21c`
- `0x18002b018`
- `0x18002b44c`
- `0x18002fdf0`
- `0x1800302a0`
- `0x1800313f8`
- `0x180031ab8`
- `0x180033248`
- `0x18003a274`
- `0x18003a884`
- `0x18003adb0`
- `0x18003dd38`
- `0x18003e29c`

## callees

- `0x180007860`
- `0x180017f50`
- `0x18001a604`
- `0x18003eba4`
- `0x180040880`
- `0x1800455bc`
- `0x18004954c`
- `0x18004a6e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180049582`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180049582`

## string_xrefs

- `0x1800495c3`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x18004960f`: `onecore\admin\appmodel\common\alluserstorepaths.cpp`
- `0x1800495ef`: `Failed to Load the PreInstalled AppxAllUserStore Hive. DACL: %ws`

## pseudocode

```c
int __fastcall AppxAllUserStore::GetAllUserStoreForPreinstalledAppsVolume(
        REGSAM samDesired,
        PHKEY phkResult,
        struct Common::RegistryKey *a3)
{
  unsigned int AppKeyW; // ebx
  WCHAR *v6; // rcx
  unsigned int *v7; // r9
  int SharedFileSecurityDescriptor; // eax
  unsigned int Reserved; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int16 *v12; // [rsp+48h] [rbp+10h] BYREF
  char *v13; // [rsp+50h] [rbp+18h] BYREF

  Common::AutoHandleCloseHKEY<HKEY__ *>(*phkResult);
  *phkResult = 0;
  AppKeyW = RegLoadAppKeyW(L"P:\\WindowsApps\\AppxAllUserStore.dat", phkResult, samDesired, 0, 0);
  if ( !AppKeyW )
    return 0;
  v13 = 0;
  LODWORD(v12) = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v13,
    0);
  SharedFileSecurityDescriptor = DirectoryACLs::GetSharedFileSecurityDescriptor(
                                   v6,
                                   (unsigned __int16 *)&v13,
                                   (ULONG *)&v12,
                                   v7);
  if ( SharedFileSecurityDescriptor >= 0 )
    wil::details::in1diag3::Log_Win32Msg(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
      (const char *)AppKeyW,
      (unsigned int)"Failed to Load the PreInstalled AppxAllUserStore Hive. DACL: %ws",
      v13);
  else
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x46,
      (int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
      (const char *)(unsigned int)SharedFileSecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x4C,
           (unsigned int)"onecore\\admin\\appmodel\\common\\alluserstorepaths.cpp",
           (const char *)AppKeyW,
           Reserved);
}

```

## disassembly

```asm
0x18004954c  mov     [rsp+arg_0], rbx
0x180049551  push    rdi
0x180049552  sub     rsp, 30h
0x180049556  mov     ebx, ecx
0x180049558  mov     rdi, rdx
0x18004955b  mov     rcx, [rdx]
0x18004955e  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180049563  xor     r9d, r9d; dwOptions
0x180049566  mov     qword ptr [rdi], 0
0x18004956d  mov     r8d, ebx; samDesired
0x180049570  mov     [rsp+38h+Reserved], 0; int
0x180049578  mov     rdx, rdi; phkResult
0x18004957b  lea     rcx, pObjectName; "P:\\WindowsApps\\AppxAllUserStore.dat"
0x180049582  call    cs:__imp_RegLoadAppKeyW
0x180049588  mov     ebx, eax
0x18004958a  test    eax, eax
0x18004958c  jz      loc_180049625
0x180049592  xor     edx, edx
0x180049594  mov     [rsp+38h+arg_10], 0
0x18004959d  lea     rcx, [rsp+38h+arg_10]
0x1800495a2  mov     dword ptr [rsp+38h+arg_8], 0
0x1800495aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800495af  lea     r8, [rsp+38h+arg_8]; unsigned __int16 **
0x1800495b4  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 *
0x1800495b9  call    ?GetSharedFileSecurityDescriptor@DirectoryACLs@@YAJPEBGPEAPEAGPEAK@Z; DirectoryACLs::GetSharedFileSecurityDescriptor(ushort const *,ushort * *,ulong *)
0x1800495be  mov     rcx, [rsp+38h]; this
0x1800495c3  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x1800495ca  test    eax, eax
0x1800495cc  jns     short loc_1800495DD
0x1800495ce  mov     r9d, eax; char *
0x1800495d1  mov     edx, 46h ; 'F'; void *
0x1800495d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800495db  jmp     short loc_180049600
0x1800495dd  mov     rax, [rsp+38h+arg_10]
0x1800495e2  mov     r9d, ebx; char *
0x1800495e5  mov     [rsp+38h+var_10], rax; char *
0x1800495ea  mov     edx, 48h ; 'H'; void *
0x1800495ef  lea     rax, aFailedToLoadTh; "Failed to Load the PreInstalled AppxAll"...
0x1800495f6  mov     qword ptr [rsp+38h+Reserved], rax; unsigned int
0x1800495fb  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180049600  lea     rcx, [rsp+38h+arg_10]
0x180049605  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004960a  mov     rcx, [rsp+38h]; this
0x18004960f  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\common\\allus"...
0x180049616  mov     r9d, ebx; char *
0x180049619  mov     edx, 4Ch ; 'L'; void *
0x18004961e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180049623  jmp     short loc_180049627
0x180049625  xor     eax, eax
0x180049627  mov     rbx, [rsp+38h+arg_0]
0x18004962c  add     rsp, 30h
0x180049630  pop     rdi
0x180049631  retn
```
