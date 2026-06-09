# SystemSettings::DataModel::CopyCurrentUserSettings::CopySettingsApplyChanges(bool,bool)

- ea: `0x1400436f8`
- end: `0x1400437de`
- name: `?CopySettingsApplyChanges@CopyCurrentUserSettings@DataModel@SystemSettings@@SAJ_N0@Z`
- size: `230`
- prototype: `static int(bool, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140020120`

## callees

- `0x14000ed18`
- `0x14001f3d4`
- `0x14002c280`
- `0x1400436f8`
- `0x1400437e4`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140043749`
- `KERNEL32!GetProcAddress` at `0x140043760`
- `KERNEL32!GetProcAddress` at `0x140043749`
- `KERNEL32!GetProcAddress` at `0x140043760`
- `KERNEL32!LoadLibraryExW` at `0x14004372c`
- `KERNEL32!LoadLibraryExW` at `0x14004372c`

## string_xrefs

- `0x140043791`: `pcshell\shell\systemsettings\adminflows\languagemanager\lib\copycurrentusersettings.cpp`
- `0x140043725`: `input.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::CopySettingsApplyChanges(
        unsigned __int8 a1,
        unsigned __int8 a2)
{
  int v2; // ebx
  int v3; // edi
  HMODULE Library; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v10; // [rsp+30h] [rbp+8h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp+18h] BYREF

  v2 = a2;
  v3 = a1;
  if ( a1 || a2 )
  {
    hModule = 0;
    Library = LoadLibraryExW(L"input.dll", 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hModule,
      Library);
    SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveDefaultUserInputSettings = (int (*)(HWND, HKEY))GetProcAddress(hModule, (LPCSTR)0x69);
    SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings = (int (*)(HWND, HKEY))GetProcAddress(hModule, (LPCSTR)0x6A);
    v10 = 0;
    v5 = SystemSettings::DataModel::CopyCurrentUserSettings::CopyToReservedAccounts(v2, v3, &v10);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\copycurrentusersettings.cpp",
        (const char *)(unsigned int)v5,
        v8);
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
      return v6;
    }
    SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveDefaultUserInputSettings = 0;
    SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings = 0;
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  }
  return 0;
}

```

## disassembly

```asm
0x1400436f8  mov     [rsp+arg_8], rbx
0x1400436fd  push    rdi; int
0x1400436fe  sub     rsp, 20h
0x140043702  movzx   ebx, dl
0x140043705  movzx   edi, cl
0x140043708  test    cl, cl
0x14004370a  jnz     short loc_140043714
0x14004370c  test    dl, dl
0x14004370e  jz      loc_1400437D1
0x140043714  mov     [rsp+28h+hModule], 0
0x14004371d  xor     edx, edx; hFile
0x14004371f  mov     r8d, 800h; dwFlags
0x140043725  lea     rcx, aInputDll; "input.dll"
0x14004372c  call    cs:__imp_LoadLibraryExW
0x140043732  mov     rdx, rax
0x140043735  lea     rcx, [rsp+28h+hModule]
0x14004373a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x14004373f  mov     edx, 69h ; 'i'; lpProcName
0x140043744  mov     rcx, [rsp+28h+hModule]; hModule
0x140043749  call    cs:__imp_GetProcAddress
0x14004374f  mov     cs:?s_pfnSaveDefaultUserInputSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@0P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rax; int (*SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveDefaultUserInputSettings)(HWND__ *,HKEY__ *)
0x140043756  mov     edx, 6Ah ; 'j'; lpProcName
0x14004375b  mov     rcx, [rsp+28h+hModule]; hModule
0x140043760  call    cs:__imp_GetProcAddress
0x140043766  mov     cs:?s_pfnSaveSystemAcctInputSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@0P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, rax; int (*SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings)(HWND__ *,HKEY__ *)
0x14004376d  mov     [rsp+28h+arg_0], 0
0x140043775  mov     edx, edi; int
0x140043777  mov     ecx, ebx; int
0x140043779  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x14004377e  call    ?CopyToReservedAccounts@CopyCurrentUserSettings@DataModel@SystemSettings@@CAJHHPEAK@Z; SystemSettings::DataModel::CopyCurrentUserSettings::CopyToReservedAccounts(int,int,ulong *)
0x140043783  mov     ebx, eax
0x140043785  test    eax, eax
0x140043787  jns     short loc_1400437B1
0x140043789  mov     rcx, [rsp+28h]; this
0x14004378e  mov     r9d, eax; char *
0x140043791  lea     r8, aPcshellShellSy_33; "pcshell\\shell\\systemsettings\\adminfl"...
0x140043798  mov     edx, 1Ah; void *
0x14004379d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400437a2  nop
0x1400437a3  lea     rcx, [rsp+28h+hModule]
0x1400437a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1400437ad  mov     eax, ebx
0x1400437af  jmp     short loc_1400437D3
0x1400437b1  mov     cs:?s_pfnSaveDefaultUserInputSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@0P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, 0; int (*SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveDefaultUserInputSettings)(HWND__ *,HKEY__ *)
0x1400437bc  mov     cs:?s_pfnSaveSystemAcctInputSettings@CopyCurrentUserSettings@DataModel@SystemSettings@@0P6AHPEAUHWND__@@PEAUHKEY__@@@ZEA, 0; int (*SystemSettings::DataModel::CopyCurrentUserSettings::s_pfnSaveSystemAcctInputSettings)(HWND__ *,HKEY__ *)
0x1400437c7  lea     rcx, [rsp+28h+hModule]
0x1400437cc  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1400437d1  xor     eax, eax
0x1400437d3  mov     rbx, [rsp+28h+arg_8]
0x1400437d8  add     rsp, 20h
0x1400437dc  pop     rdi
0x1400437dd  retn
```
