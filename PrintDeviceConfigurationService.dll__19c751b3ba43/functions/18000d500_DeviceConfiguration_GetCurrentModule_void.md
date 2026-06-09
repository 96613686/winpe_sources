# DeviceConfiguration::GetCurrentModule(void)

- ea: `0x18000d500`
- end: `0x18000d56f`
- name: `?GetCurrentModule@DeviceConfiguration@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `111`
- prototype: `HMODULE *__fastcall(HMODULE *phModule)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`

## callees

- `0x18000d8e4`
- `0x18000dd08`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d53a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d53a`

## string_xrefs

- `0x18000d554`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\wnflistener.cpp`

## pseudocode

```c
HMODULE *__fastcall DeviceConfiguration::GetCurrentModule(HMODULE *phModule)
{
  unsigned int ModuleHandle; // eax
  const char *v4; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *phModule = 0;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    phModule,
    0);
  ModuleHandle = GetModuleHandleExW(4u, (LPCWSTR)DeviceConfiguration::GetCurrentModule, phModule);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x1C,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\wnflistener.cpp",
    (const char *)ModuleHandle,
    (int)"GetModuleHandleExW failed!",
    v4);
  return phModule;
}

```

## disassembly

```asm
0x18000d500  mov     [rsp+arg_0], rcx
0x18000d505  push    rbx
0x18000d506  sub     rsp, 40h
0x18000d50a  mov     rbx, rcx
0x18000d50d  mov     [rsp+48h+var_18], 0
0x18000d515  mov     qword ptr [rcx], 0
0x18000d51c  mov     [rsp+48h+var_18], 1
0x18000d524  xor     edx, edx
0x18000d526  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000d52b  mov     r8, rbx; phModule
0x18000d52e  lea     rdx, ?GetCurrentModule@DeviceConfiguration@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; lpModuleName
0x18000d535  mov     ecx, 4; dwFlags
0x18000d53a  call    cs:__imp_GetModuleHandleExW
0x18000d540  mov     rcx, [rsp+48h]; this
0x18000d545  lea     rdx, aGetmodulehandl; "GetModuleHandleExW failed!"
0x18000d54c  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18000d551  mov     r9d, eax; char *
0x18000d554  lea     r8, aPrintscanPrint; "printscan\\print\\spooler\\configuratio"...
0x18000d55b  mov     edx, 1Ch; void *
0x18000d560  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18000d565  mov     rax, rbx
0x18000d568  add     rsp, 40h
0x18000d56c  pop     rbx
0x18000d56d  retn
```
