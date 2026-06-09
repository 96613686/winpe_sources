# Microsoft::Bluetooth::Audio::GetBatsTransportPreference

- ea: `0x18003cc6c`
- end: `0x18003cd1a`
- name: `Microsoft::Bluetooth::Audio::GetBatsTransportPreference`
- size: `174`
- prototype: `__int64 __fastcall(LPCWSTR lpValue)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003cc44`
- `0x18003d280`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x18003cc6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ccab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ccab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ccee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ccee`

## string_xrefs

- `0x18003cc9d`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Audio::GetBatsTransportPreference(LPCWSTR lpValue)
{
  unsigned int v2; // ebx
  int pvData; // [rsp+58h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp+18h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+20h] BYREF

  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
         0,
         0x20019u,
         &hkey)
    || (pvData = 0, pcbData = 4, RegGetValueW(hkey, 0, lpValue, 0x10u, 0, &pvData, &pcbData)) )
  {
    v2 = 0;
  }
  else
  {
    v2 = 1;
    if ( pvData == 1 )
      v2 = 2;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v2;
}

```

## disassembly

```asm
0x18003cc6c  push    rbx
0x18003cc6e  sub     rsp, 40h
0x18003cc72  mov     rbx, rcx
0x18003cc75  mov     [rsp+48h+hkey], 0
0x18003cc7e  lea     rcx, [rsp+48h+hkey]
0x18003cc83  xor     edx, edx
0x18003cc85  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003cc8a  lea     rax, [rsp+48h+hkey]
0x18003cc8f  mov     r9d, 20019h; samDesired
0x18003cc95  xor     r8d, r8d; ulOptions
0x18003cc98  mov     [rsp+48h+phkResult], rax; phkResult
0x18003cc9d  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x18003cca4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ccab  call    cs:__imp_RegOpenKeyExW
0x18003ccb1  test    eax, eax
0x18003ccb3  jnz     short loc_18003CD06
0x18003ccb5  mov     rcx, [rsp+48h+hkey]; hkey
0x18003ccba  mov     r9d, 10h; dwFlags
0x18003ccc0  mov     [rsp+48h+arg_8], eax
0x18003ccc4  mov     r8, rbx; lpValue
0x18003ccc7  lea     rax, [rsp+48h+arg_10]
0x18003cccc  mov     [rsp+48h+arg_10], 4
0x18003ccd4  mov     [rsp+48h+pcbData], rax; pcbData
0x18003ccd9  xor     edx, edx; lpSubKey
0x18003ccdb  lea     rax, [rsp+48h+arg_8]
0x18003cce0  mov     [rsp+48h+pvData], rax; pvData
0x18003cce5  mov     [rsp+48h+phkResult], 0; pdwType
0x18003ccee  call    cs:__imp_RegGetValueW
0x18003ccf4  test    eax, eax
0x18003ccf6  jnz     short loc_18003CD06
0x18003ccf8  lea     ebx, [rax+1]
0x18003ccfb  cmp     [rsp+48h+arg_8], ebx
0x18003ccff  jnz     short loc_18003CD08
0x18003cd01  lea     ebx, [rax+2]
0x18003cd04  jmp     short loc_18003CD08
0x18003cd06  xor     ebx, ebx
0x18003cd08  lea     rcx, [rsp+48h+hkey]
0x18003cd0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003cd12  mov     eax, ebx
0x18003cd14  add     rsp, 40h
0x18003cd18  pop     rbx
0x18003cd19  retn
```
