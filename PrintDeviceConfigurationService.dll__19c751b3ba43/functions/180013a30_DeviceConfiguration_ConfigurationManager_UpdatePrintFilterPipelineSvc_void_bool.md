# DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(void *,bool)

- ea: `0x180013a30`
- end: `0x180013b1d`
- name: `?_UpdatePrintFilterPipelineSvc@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z`
- size: `237`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, void *, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x18000c158`
- `0x18000ea48`
- `0x180013a30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ae1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013ae1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013aad`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013aad`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013a72`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013a72`

## string_xrefs

- `0x180013a8c`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013afb`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013a80`: `RegOpenKeyTransacted (Pipeline) failed!`
- `0x180013ab6`: `RegDeleteValue (Pipeline RunAs) failed!`
- `0x180013aea`: `RegSetValueEx (Pipeline RunAs) failed!`
- `0x180013acc`: `NT Authority\LocalService`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_UpdatePrintFilterPipelineSvc(
        DeviceConfiguration::ConfigurationManager *this,
        void *a2,
        char a3)
{
  unsigned int v4; // eax
  unsigned __int64 v5; // r9
  const char *v6; // rax
  __int64 v7; // rdx
  const char *cbDataa; // [rsp+28h] [rbp-20h]
  const char *cbData; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  hKey = 0;
  v4 = RegOpenKeyTransactedW(HKEY_CLASSES_ROOT, L"AppID\\{76db1bf3-e820-4765-a1b2-0b16a86b1950}", 0, 2u, &hKey, a2, 0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x1A6,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v4,
    (unsigned int)"RegOpenKeyTransacted (Pipeline) failed!",
    cbDataa);
  if ( a3 )
  {
    v5 = (unsigned int)RegDeleteValueW(hKey, L"RunAs");
    v6 = "RegDeleteValue (Pipeline RunAs) failed!";
    v7 = 426;
  }
  else
  {
    v5 = (unsigned int)RegSetValueExW(hKey, L"RunAs", 0, 1u, L"NT Authority\\LocalService", 0x34u);
    v6 = "RegSetValueEx (Pipeline RunAs) failed!";
    v7 = 431;
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)v7,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v5,
    (unsigned int)v6,
    cbData);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180013a30  mov     r11, rsp
0x180013a33  mov     [r11+8], rcx
0x180013a37  push    rbx
0x180013a38  sub     rsp, 40h
0x180013a3c  mov     bl, r8b
0x180013a3f  mov     qword ptr [r11+8], 0
0x180013a47  mov     qword ptr [r11-18h], 0
0x180013a4f  mov     [r11-20h], rdx
0x180013a53  lea     rax, [r11+8]
0x180013a57  mov     [r11-28h], rax
0x180013a5b  mov     r9d, 2; samDesired
0x180013a61  xor     r8d, r8d; ulOptions
0x180013a64  lea     rdx, aAppid76db1bf3E; "AppID\\{76db1bf3-e820-4765-a1b2-0b16a86"...
0x180013a6b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180013a72  call    cs:__imp_RegOpenKeyTransactedW
0x180013a78  mov     r9d, eax; char *
0x180013a7b  mov     rcx, [rsp+48h]; this
0x180013a80  lea     rax, aRegopenkeytran_0; "RegOpenKeyTransacted (Pipeline) failed!"
0x180013a87  mov     [rsp+48h+lpData], rax; unsigned int
0x180013a8c  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013a93  mov     edx, 1A6h; void *
0x180013a98  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013a9d  lea     rdx, aRunas; "RunAs"
0x180013aa4  mov     rcx, [rsp+48h+hKey]; hKey
0x180013aa9  test    bl, bl
0x180013aab  jz      short loc_180013AC4
0x180013aad  call    cs:__imp_RegDeleteValueW
0x180013ab3  mov     r9d, eax
0x180013ab6  lea     rax, aRegdeletevalue; "RegDeleteValue (Pipeline RunAs) failed!"
0x180013abd  mov     edx, 1AAh
0x180013ac2  jmp     short loc_180013AF6
0x180013ac4  mov     [rsp+48h+cbData], 34h ; '4'; char *
0x180013acc  lea     rax, Data; "NT Authority\\LocalService"
0x180013ad3  mov     [rsp+48h+lpData], rax; lpData
0x180013ad8  mov     r9d, 1; dwType
0x180013ade  xor     r8d, r8d; Reserved
0x180013ae1  call    cs:__imp_RegSetValueExW
0x180013ae7  mov     r9d, eax; char *
0x180013aea  lea     rax, aRegsetvalueexP; "RegSetValueEx (Pipeline RunAs) failed!"
0x180013af1  mov     edx, 1AFh; void *
0x180013af6  mov     [rsp+48h+lpData], rax; unsigned int
0x180013afb  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013b02  mov     rcx, [rsp+48h]; this
0x180013b07  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013b0c  nop
0x180013b0d  lea     rcx, [rsp+48h+hKey]
0x180013b12  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013b17  add     rsp, 40h
0x180013b1b  pop     rbx
0x180013b1c  retn
```
