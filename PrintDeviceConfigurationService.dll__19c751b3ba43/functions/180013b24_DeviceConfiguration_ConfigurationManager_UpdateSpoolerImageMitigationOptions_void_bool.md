# DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(void *,bool)

- ea: `0x180013b24`
- end: `0x180013c34`
- name: `?_UpdateSpoolerImageMitigationOptions@ConfigurationManager@DeviceConfiguration@@AEAAXPEAX_N@Z`
- size: `272`
- prototype: `void __fastcall(DeviceConfiguration::ConfigurationManager *this, void *, char)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800121c0`
- `0x180012a50`
- `0x180012df8`

## callees

- `0x18000c158`
- `0x18000ea48`
- `0x1800131dc`
- `0x180013b24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bf7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bf7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013bbc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013bbc`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013b7e`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180013b7e`

## string_xrefs

- `0x180013b98`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180013b8c`: `RegOpenKeyTransacted (Execution Options) failed!`
- `0x180013bc5`: `RegDeleteValue (MitigationOptions) failed!`
- `0x180013c00`: `RegSetValueEx (ASLR Mitigations) failed!`

## pseudocode

```c
void __fastcall DeviceConfiguration::ConfigurationManager::_UpdateSpoolerImageMitigationOptions(
        DeviceConfiguration::ConfigurationManager *this,
        void *a2,
        char a3)
{
  unsigned int v5; // eax
  unsigned __int64 v6; // r9
  const char *v7; // rax
  __int64 v8; // rdx
  const char *hTransactiona; // [rsp+28h] [rbp-20h]
  const char *hTransaction; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  __int64 Data; // [rsp+68h] [rbp+20h] BYREF

  hKey = (HKEY)this;
  if ( DeviceConfiguration::ConfigurationManager::_IsClientSKU(this) )
  {
    hKey = 0;
    v5 = RegOpenKeyTransactedW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\spoolsv.exe",
           0,
           2u,
           &hKey,
           a2,
           0);
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0x20B,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v5,
      (unsigned int)"RegOpenKeyTransacted (Execution Options) failed!",
      hTransactiona);
    if ( a3 )
    {
      v6 = (unsigned int)RegDeleteValueW(hKey, L"MitigationOptions");
      v7 = "RegDeleteValue (MitigationOptions) failed!";
      v8 = 527;
    }
    else
    {
      Data = 0x200000;
      v6 = (unsigned int)RegSetValueExW(hKey, L"MitigationOptions", 0, 0xBu, (const BYTE *)&Data, 8u);
      v7 = "RegSetValueEx (ASLR Mitigations) failed!";
      v8 = 534;
    }
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)v8,
      (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
      (const char *)v6,
      (unsigned int)v7,
      hTransaction);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
}

```

## disassembly

```asm
0x180013b24  mov     [rsp+arg_8], rbx
0x180013b29  mov     [rsp+hKey], rcx
0x180013b2e  push    rdi
0x180013b2f  sub     rsp, 40h
0x180013b33  mov     bl, r8b
0x180013b36  mov     rdi, rdx
0x180013b39  call    ?_IsClientSKU@ConfigurationManager@DeviceConfiguration@@AEAA_NXZ; DeviceConfiguration::ConfigurationManager::_IsClientSKU(void)
0x180013b3e  test    al, al
0x180013b40  jz      loc_180013C29
0x180013b46  mov     [rsp+48h+hKey], 0
0x180013b4f  mov     [rsp+48h+pExtendedParemeter], 0; pExtendedParemeter
0x180013b58  mov     [rsp+48h+hTransaction], rdi; char *
0x180013b5d  lea     rax, [rsp+48h+hKey]
0x180013b62  mov     [rsp+48h+phkResult], rax; phkResult
0x180013b67  mov     r9d, 2; samDesired
0x180013b6d  xor     r8d, r8d; ulOptions
0x180013b70  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180013b77  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013b7e  call    cs:__imp_RegOpenKeyTransactedW
0x180013b84  mov     r9d, eax; char *
0x180013b87  mov     rcx, [rsp+48h]; this
0x180013b8c  lea     rax, aRegopenkeytran_1; "RegOpenKeyTransacted (Execution Options"...
0x180013b93  mov     [rsp+48h+phkResult], rax; unsigned int
0x180013b98  lea     rdi, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180013b9f  mov     r8, rdi; unsigned int
0x180013ba2  mov     edx, 20Bh; void *
0x180013ba7  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013bac  lea     rdx, aMitigationopti; "MitigationOptions"
0x180013bb3  mov     rcx, [rsp+48h+hKey]; hKey
0x180013bb8  test    bl, bl
0x180013bba  jz      short loc_180013BD3
0x180013bbc  call    cs:__imp_RegDeleteValueW
0x180013bc2  mov     r9d, eax
0x180013bc5  lea     rax, aRegdeletevalue_1; "RegDeleteValue (MitigationOptions) fail"...
0x180013bcc  mov     edx, 20Fh
0x180013bd1  jmp     short loc_180013C0C
0x180013bd3  mov     [rsp+48h+Data], 200000h
0x180013bdc  mov     dword ptr [rsp+48h+hTransaction], 8; char *
0x180013be4  lea     rax, [rsp+48h+Data]
0x180013be9  mov     [rsp+48h+phkResult], rax; lpData
0x180013bee  mov     r9d, 0Bh; dwType
0x180013bf4  xor     r8d, r8d; Reserved
0x180013bf7  call    cs:__imp_RegSetValueExW
0x180013bfd  mov     r9d, eax; char *
0x180013c00  lea     rax, aRegsetvalueexA; "RegSetValueEx (ASLR Mitigations) failed"...
0x180013c07  mov     edx, 216h; void *
0x180013c0c  mov     [rsp+48h+phkResult], rax; unsigned int
0x180013c11  mov     r8, rdi; unsigned int
0x180013c14  mov     rcx, [rsp+48h]; this
0x180013c19  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180013c1e  nop
0x180013c1f  lea     rcx, [rsp+48h+hKey]
0x180013c24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013c29  mov     rbx, [rsp+48h+arg_8]
0x180013c2e  add     rsp, 40h
0x180013c32  pop     rdi
0x180013c33  retn
```
