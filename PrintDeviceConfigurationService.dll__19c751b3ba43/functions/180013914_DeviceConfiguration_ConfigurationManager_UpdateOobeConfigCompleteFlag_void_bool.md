# DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(void *,bool)

- ea: `0x180013914`
- end: `0x180013a27`
- name: `?_UpdateOobeConfigCompleteFlag@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z`
- size: `275`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, void *, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x18000c158`
- `0x18000ea48`
- `0x180013914`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800139d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800139d4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800139eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800139eb`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180013973`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180013973`

## string_xrefs

- `0x180013965`: `SYSTEM\CurrentControlSet\Services\PrintDeviceConfigurationService\State\WPP`
- `0x18001399e`: `WindowsProtectedPrintOobeConfigComplete`
- `0x18001398d`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013a05`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013981`: `RegCreateKeyTransacted (PDCS WPP State) failed!`
- `0x1800139dd`: `RegSetValueEx (WPP OOBE Configuration Complete) failed!`
- `0x1800139f4`: `RegDeleteValue (WPP OOBE Configuration Complete) failed!`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_UpdateOobeConfigCompleteFlag(
        DeviceConfiguration::ConfigurationManager *this,
        void *a2,
        char a3)
{
  unsigned int v4; // eax
  unsigned __int64 v5; // r9
  const char *v6; // rax
  __int64 v7; // rdx
  const char *samDesireda; // [rsp+28h] [rbp-40h]
  const char *samDesired; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF

  hKey = 0;
  v4 = RegCreateKeyTransactedW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\PrintDeviceConfigurationService\\State\\WPP",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         0,
         a2,
         0);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x21E,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v4,
    (unsigned int)"RegCreateKeyTransacted (PDCS WPP State) failed!",
    samDesireda);
  if ( a3 )
  {
    Data = 1;
    v5 = (unsigned int)RegSetValueExW(hKey, L"WindowsProtectedPrintOobeConfigComplete", 0, 4u, (const BYTE *)&Data, 4u);
    v6 = "RegSetValueEx (WPP OOBE Configuration Complete) failed!";
    v7 = 546;
  }
  else
  {
    v5 = (unsigned int)RegDeleteValueW(hKey, L"WindowsProtectedPrintOobeConfigComplete");
    v6 = "RegDeleteValue (WPP OOBE Configuration Complete) failed!";
    v7 = 550;
  }
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)v7,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v5,
    (unsigned int)v6,
    samDesired);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180013914  mov     r11, rsp
0x180013917  mov     [r11+8], rcx
0x18001391b  push    rbx
0x18001391c  sub     rsp, 60h
0x180013920  mov     bl, r8b
0x180013923  mov     qword ptr [r11+8], 0
0x18001392b  mov     qword ptr [r11-18h], 0
0x180013933  mov     [r11-20h], rdx
0x180013937  mov     qword ptr [r11-28h], 0
0x18001393f  lea     rax, [r11+8]
0x180013943  mov     [r11-30h], rax
0x180013947  mov     qword ptr [r11-38h], 0
0x18001394f  mov     [rsp+68h+samDesired], 0F003Fh; char *
0x180013957  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18001395f  xor     r9d, r9d; lpClass
0x180013962  xor     r8d, r8d; Reserved
0x180013965  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Pr"...
0x18001396c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013973  call    cs:__imp_RegCreateKeyTransactedW
0x180013979  mov     r9d, eax; char *
0x18001397c  mov     rcx, [rsp+68h]; this
0x180013981  lea     rax, aRegcreatekeytr_1; "RegCreateKeyTransacted (PDCS WPP State)"...
0x180013988  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x18001398d  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013994  mov     edx, 21Eh; void *
0x180013999  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18001399e  lea     rdx, aWindowsprotect; "WindowsProtectedPrintOobeConfigComplete"
0x1800139a5  mov     rcx, [rsp+68h+hKey]; hKey
0x1800139aa  test    bl, bl
0x1800139ac  jz      short loc_1800139EB
0x1800139ae  mov     [rsp+68h+Data], 1
0x1800139b9  mov     r9d, 4; dwType
0x1800139bf  mov     [rsp+68h+samDesired], r9d; cbData
0x1800139c4  lea     rax, [rsp+68h+Data]
0x1800139cc  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800139d1  xor     r8d, r8d; Reserved
0x1800139d4  call    cs:__imp_RegSetValueExW
0x1800139da  mov     r9d, eax
0x1800139dd  lea     rax, aRegsetvalueexW_0; "RegSetValueEx (WPP OOBE Configuration C"...
0x1800139e4  mov     edx, 222h
0x1800139e9  jmp     short loc_180013A00
0x1800139eb  call    cs:__imp_RegDeleteValueW
0x1800139f1  mov     r9d, eax; char *
0x1800139f4  lea     rax, aRegdeletevalue_3; "RegDeleteValue (WPP OOBE Configuration "...
0x1800139fb  mov     edx, 226h; void *
0x180013a00  mov     qword ptr [rsp+68h+dwOptions], rax; unsigned int
0x180013a05  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013a0c  mov     rcx, [rsp+68h]; this
0x180013a11  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013a16  nop
0x180013a17  lea     rcx, [rsp+68h+hKey]
0x180013a1c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013a21  add     rsp, 60h
0x180013a25  pop     rbx
0x180013a26  retn
```
