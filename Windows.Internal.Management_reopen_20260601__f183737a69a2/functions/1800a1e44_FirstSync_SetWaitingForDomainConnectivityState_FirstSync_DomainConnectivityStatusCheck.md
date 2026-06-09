# FirstSync::SetWaitingForDomainConnectivityState(FirstSync::DomainConnectivityStatusCheck)

- ea: `0x1800a1e44`
- end: `0x1800a1f9f`
- name: `?SetWaitingForDomainConnectivityState@FirstSync@@YAJW4DomainConnectivityStatusCheck@1@@Z`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026894`

## callees

- `0x180016698`
- `0x180017118`
- `0x180033500`
- `0x18003a7cc`
- `0x1800a1e44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1eaf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a1eaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a1f5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a1f5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a1f1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a1f1b`

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
0x1800a1e44  mov     [rsp-8+arg_0], rbx
0x1800a1e49  push    rbp
0x1800a1e4a  mov     rbp, rsp
0x1800a1e4d  sub     rsp, 60h
0x1800a1e51  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x1800a1e58  mov     ebx, ecx
0x1800a1e5a  jz      short loc_1800A1E6B
0x1800a1e5c  mov     r8d, ecx
0x1800a1e5f  lea     rdx, EnterpriseDiagnosticsSettingDomainConnectivityState
0x1800a1e66  call    McTemplateU0d_EventWriteTransfer
0x1800a1e6b  lea     rax, [rbp+arg_10]
0x1800a1e6f  mov     [rbp+arg_8], 0
0x1800a1e76  mov     [rsp+60h+pcbData], rax; pcbData
0x1800a1e7b  lea     r8, aOdjstatus; "OdjStatus"
0x1800a1e82  lea     rax, [rbp+arg_8]
0x1800a1e86  mov     [rbp+arg_10], 4
0x1800a1e8d  mov     [rsp+60h+pvData], rax; pvData
0x1800a1e92  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Enrollment"
0x1800a1e99  mov     r9d, 10h; dwFlags
0x1800a1e9f  mov     [rsp+60h+pdwType], 0; pdwType
0x1800a1ea8  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800a1eaf  call    cs:__imp_RegGetValueW
0x1800a1eb6  nop     dword ptr [rax+rax+00h]
0x1800a1ebb  test    eax, eax
0x1800a1ebd  jnz     short loc_1800A1EC9
0x1800a1ebf  cmp     [rbp+arg_8], 2
0x1800a1ec3  jz      loc_1800A1F93
0x1800a1ec9  xor     edx, edx
0x1800a1ecb  mov     [rbp+hKey], 0
0x1800a1ed3  lea     rcx, [rbp+hKey]
0x1800a1ed7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a1edc  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800a1ee5  lea     rax, [rbp+hKey]
0x1800a1ee9  mov     [rsp+60h+phkResult], rax; phkResult
0x1800a1eee  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Enrollment"
0x1800a1ef5  mov     [rsp+60h+pcbData], 0; lpSecurityAttributes
0x1800a1efe  xor     r9d, r9d; lpClass
0x1800a1f01  mov     dword ptr [rsp+60h+pvData], 20006h; samDesired
0x1800a1f09  xor     r8d, r8d; Reserved
0x1800a1f0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a1f13  mov     dword ptr [rsp+60h+pdwType], 0; dwOptions
0x1800a1f1b  call    cs:__imp_RegCreateKeyExW
0x1800a1f22  nop     dword ptr [rax+rax+00h]
0x1800a1f27  test    eax, eax
0x1800a1f29  jz      short loc_1800A1F32
0x1800a1f2b  mov     edx, 417h
0x1800a1f30  jmp     short loc_1800A1F6F
0x1800a1f32  mov     rcx, [rbp+hKey]; hKey
0x1800a1f36  lea     rax, [rbp+Data]
0x1800a1f3a  mov     dword ptr [rsp+60h+pvData], 4; cbData
0x1800a1f42  lea     rdx, aOdjstatus; "OdjStatus"
0x1800a1f49  mov     r9d, 4; dwType
0x1800a1f4f  mov     [rsp+60h+pdwType], rax; unsigned int
0x1800a1f54  xor     r8d, r8d; Reserved
0x1800a1f57  mov     [rbp+Data], ebx
0x1800a1f5a  call    cs:__imp_RegSetValueExW
0x1800a1f61  nop     dword ptr [rax+rax+00h]
0x1800a1f66  test    eax, eax
0x1800a1f68  jz      short loc_1800A1F86
0x1800a1f6a  mov     edx, 422h; void *
0x1800a1f6f  mov     rcx, [rbp+8]; this
0x1800a1f73  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1f7a  mov     r9d, eax; char *
0x1800a1f7d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a1f82  mov     ebx, eax
0x1800a1f84  jmp     short loc_1800A1F88
0x1800a1f86  xor     ebx, ebx
0x1800a1f88  lea     rcx, [rbp+hKey]
0x1800a1f8c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1f91  mov     eax, ebx
0x1800a1f93  mov     rbx, [rsp+60h+arg_0]
0x1800a1f98  add     rsp, 60h
0x1800a1f9c  pop     rbp
0x1800a1f9d  retn
```
