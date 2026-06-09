# GetUtcRealtimeUploadTime(unsigned __int64 *)

- ea: `0x18003e5f8`
- end: `0x18003e6a4`
- name: `?GetUtcRealtimeUploadTime@@YAJPEA_K@Z`
- size: `172`
- prototype: `__int64 __fastcall(LPBYTE lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`

## callees

- `0x18000e48c`
- `0x180024780`
- `0x18003c0b8`
- `0x18003e5f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e668`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e668`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e63b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e63b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetUtcRealtimeUploadTime(LPBYTE lpData)
{
  HKEY *phkResult; // rax
  int v3; // ebx
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  cbData = 8;
  hKey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\DiagTrack",
         0,
         0x20019u,
         phkResult);
  if ( v3 || (v3 = RegQueryValueExW(hKey, L"LastSuccessfulRealtimeUploadTime", 0, 0, lpData, &cbData)) != 0 )
    SBServicingLogMessage((wchar_t *)L"Failed getting UTC realtime last upload time.");
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003e5f8  mov     rax, rsp
0x18003e5fb  mov     [rax+8], rbx
0x18003e5ff  push    rdi
0x18003e600  sub     rsp, 30h
0x18003e604  mov     rdi, rcx
0x18003e607  mov     dword ptr [rax+10h], 8
0x18003e60e  mov     qword ptr [rax+18h], 0
0x18003e616  lea     rcx, [rax+18h]
0x18003e61a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003e61f  mov     [rsp+38h+phkResult], rax; phkResult
0x18003e624  mov     r9d, 20019h; samDesired
0x18003e62a  xor     r8d, r8d; ulOptions
0x18003e62d  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003e634  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e63b  call    cs:__imp_RegOpenKeyExW
0x18003e641  mov     ebx, eax
0x18003e643  test    eax, eax
0x18003e645  jnz     short loc_18003E674
0x18003e647  lea     rax, [rsp+38h+cbData]
0x18003e64c  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18003e651  mov     [rsp+38h+phkResult], rdi; lpData
0x18003e656  xor     r9d, r9d; lpType
0x18003e659  xor     r8d, r8d; lpReserved
0x18003e65c  lea     rdx, aLastsuccessful; "LastSuccessfulRealtimeUploadTime"
0x18003e663  mov     rcx, [rsp+38h+hKey]; hKey
0x18003e668  call    cs:__imp_RegQueryValueExW
0x18003e66e  mov     ebx, eax
0x18003e670  test    eax, eax
0x18003e672  jz      short loc_18003E680
0x18003e674  lea     rcx, aFailedGettingU; "Failed getting UTC realtime last upload"...
0x18003e67b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e680  test    ebx, ebx
0x18003e682  jle     short loc_18003E68D
0x18003e684  movzx   ebx, bx
0x18003e687  or      ebx, 80070000h
0x18003e68d  lea     rcx, [rsp+38h+hKey]
0x18003e692  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003e697  mov     eax, ebx
0x18003e699  mov     rbx, [rsp+38h+arg_0]
0x18003e69e  add     rsp, 30h
0x18003e6a2  pop     rdi
0x18003e6a3  retn
```
