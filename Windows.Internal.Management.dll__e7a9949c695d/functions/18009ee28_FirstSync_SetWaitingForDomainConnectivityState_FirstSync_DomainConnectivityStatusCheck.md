# FirstSync::SetWaitingForDomainConnectivityState(FirstSync::DomainConnectivityStatusCheck)

- ea: `0x18009ee28`
- end: `0x18009ef70`
- name: `?SetWaitingForDomainConnectivityState@FirstSync@@YAJW4DomainConnectivityStatusCheck@1@@Z`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028068`

## callees

- `0x180015f70`
- `0x1800169b8`
- `0x18003446c`
- `0x18003b414`
- `0x18009ee28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009ee93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009ee93`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ef32`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009ef32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009eef9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009eef9`

## pseudocode

```c
LSTATUS __fastcall FirstSync::SetWaitingForDomainConnectivityState(__int64 a1)
{
  int v1; // ebx
  LSTATUS result; // eax
  unsigned int Key; // eax
  __int64 v4; // rdx
  int v5; // ebx
  unsigned int pdwType; // [rsp+20h] [rbp-40h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  int pvData; // [rsp+78h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+20h] BYREF
  int Data; // [rsp+88h] [rbp+28h] BYREF

  v1 = a1;
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    McTemplateU0d_EventWriteTransfer(a1, EnterpriseDiagnosticsSettingDomainConnectivityState, (unsigned int)a1);
  pvData = 0;
  pcbData = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Enrollment",
             L"OdjStatus",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( result || pvData != 2 )
  {
    hKey[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollment", 0, 0, 0, 0x20006u, 0, hKey, 0);
    if ( Key )
    {
      v4 = 1047;
    }
    else
    {
      Data = v1;
      Key = RegSetValueExW(hKey[0], L"OdjStatus", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !Key )
      {
        v5 = 0;
        goto LABEL_11;
      }
      v4 = 1058;
    }
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v4,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
           (const char *)Key,
           pdwType);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18009ee28  mov     [rsp-8+arg_0], rbx
0x18009ee2d  push    rbp
0x18009ee2e  mov     rbp, rsp
0x18009ee31  sub     rsp, 60h
0x18009ee35  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x18009ee3c  mov     ebx, ecx
0x18009ee3e  jz      short loc_18009EE4F
0x18009ee40  mov     r8d, ecx
0x18009ee43  lea     rdx, EnterpriseDiagnosticsSettingDomainConnectivityState
0x18009ee4a  call    McTemplateU0d_EventWriteTransfer
0x18009ee4f  lea     rax, [rbp+arg_10]
0x18009ee53  mov     [rbp+arg_8], 0
0x18009ee5a  mov     [rsp+60h+pcbData], rax; pcbData
0x18009ee5f  lea     r8, aOdjstatus; "OdjStatus"
0x18009ee66  lea     rax, [rbp+arg_8]
0x18009ee6a  mov     [rbp+arg_10], 4
0x18009ee71  mov     [rsp+60h+pvData], rax; pvData
0x18009ee76  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Enrollment"
0x18009ee7d  mov     r9d, 10h; dwFlags
0x18009ee83  mov     [rsp+60h+pdwType], 0; pdwType
0x18009ee8c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18009ee93  call    cs:__imp_RegGetValueW
0x18009ee99  test    eax, eax
0x18009ee9b  jnz     short loc_18009EEA7
0x18009ee9d  cmp     [rbp+arg_8], 2
0x18009eea1  jz      loc_18009EF65
0x18009eea7  xor     edx, edx
0x18009eea9  mov     [rbp+hKey], 0
0x18009eeb1  lea     rcx, [rbp+hKey]
0x18009eeb5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009eeba  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x18009eec3  lea     rax, [rbp+hKey]
0x18009eec7  mov     [rsp+60h+phkResult], rax; phkResult
0x18009eecc  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Enrollment"
0x18009eed3  mov     [rsp+60h+pcbData], 0; lpSecurityAttributes
0x18009eedc  xor     r9d, r9d; lpClass
0x18009eedf  mov     dword ptr [rsp+60h+pvData], 20006h; samDesired
0x18009eee7  xor     r8d, r8d; Reserved
0x18009eeea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009eef1  mov     dword ptr [rsp+60h+pdwType], 0; dwOptions
0x18009eef9  call    cs:__imp_RegCreateKeyExW
0x18009eeff  test    eax, eax
0x18009ef01  jz      short loc_18009EF0A
0x18009ef03  mov     edx, 417h
0x18009ef08  jmp     short loc_18009EF41
0x18009ef0a  mov     rcx, [rbp+hKey]; hKey
0x18009ef0e  lea     rax, [rbp+Data]
0x18009ef12  mov     dword ptr [rsp+60h+pvData], 4; cbData
0x18009ef1a  lea     rdx, aOdjstatus; "OdjStatus"
0x18009ef21  mov     r9d, 4; dwType
0x18009ef27  mov     [rsp+60h+pdwType], rax; unsigned int
0x18009ef2c  xor     r8d, r8d; Reserved
0x18009ef2f  mov     [rbp+Data], ebx
0x18009ef32  call    cs:__imp_RegSetValueExW
0x18009ef38  test    eax, eax
0x18009ef3a  jz      short loc_18009EF58
0x18009ef3c  mov     edx, 422h; void *
0x18009ef41  mov     rcx, [rbp+8]; this
0x18009ef45  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009ef4c  mov     r9d, eax; char *
0x18009ef4f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009ef54  mov     ebx, eax
0x18009ef56  jmp     short loc_18009EF5A
0x18009ef58  xor     ebx, ebx
0x18009ef5a  lea     rcx, [rbp+hKey]
0x18009ef5e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ef63  mov     eax, ebx
0x18009ef65  mov     rbx, [rsp+60h+arg_0]
0x18009ef6a  add     rsp, 60h
0x18009ef6e  pop     rbp
0x18009ef6f  retn
```
