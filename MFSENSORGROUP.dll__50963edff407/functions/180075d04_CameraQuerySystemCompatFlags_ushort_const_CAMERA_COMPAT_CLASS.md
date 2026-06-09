# CameraQuerySystemCompatFlags(ushort const *,CAMERA_COMPAT_CLASS)

- ea: `0x180075d04`
- end: `0x180075ee7`
- name: `?CameraQuerySystemCompatFlags@@YA?ATCAMERA_DEVICE_FLAGS@@PEBGW4CAMERA_COMPAT_CLASS@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800163d0`

## callees

- `0x18000f518`
- `0x180016690`
- `0x180028d5c`
- `0x180028e5c`
- `0x1800310f0`
- `0x180044f30`
- `0x180045900`
- `0x180075d04`
- `0x180075ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075def`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075def`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180075ea7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180075ea7`

## string_xrefs

- `0x180075de8`: `ComputerIds`

## pseudocode

```c
__int64 __fastcall CameraQuerySystemCompatFlags(const unsigned __int16 *a1, int a2)
{
  unsigned int v4; // r8d
  const WCHAR *v5; // rdi
  __int64 DeviceCompatFlagsInternal; // rbx
  __int64 v7; // rcx
  DWORD v8; // esi
  DWORD i; // edx
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[40]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v15[112]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v16[152]; // [rsp+190h] [rbp+90h] BYREF

  memset_0(v15, 0, 0xD2u);
  memset_0(v16, 0, sizeof(v16));
  if ( a2 )
  {
    if ( a2 == 1 )
      v5 = L"CamDevice";
    else
      v5 = L"Unknown";
  }
  else
  {
    v5 = L"CamAcpiRotation";
  }
  DeviceCompatFlagsInternal = 0;
  hKey[0] = 0;
  phkResult = 0;
  if ( a1 )
  {
    if ( (int)GetFingerprintStringPrefix(a1, v15, v4) >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        hKey,
        0);
      if ( !(unsigned int)HwCfgGetCurrentKey(v7, hKey) )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &phkResult,
          0);
        if ( !RegOpenKeyExW(hKey[0], L"ComputerIds", 0, 0x20019u, &phkResult) )
        {
          v8 = 0;
          memset_0(ValueName, 0, 0x4Eu);
          for ( i = 0; ; i = v8 )
          {
            cchValueName = 39;
            if ( RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, 0, 0, 0) )
              break;
            if ( (int)StringCchPrintfW(v16, 0x98u, L"System:%ws%ws;", v15, ValueName) < 0 )
              break;
            DeviceCompatFlagsInternal = CameraQueryDeviceCompatFlagsInternal(v5, v16);
            if ( DeviceCompatFlagsInternal )
              break;
            ++v8;
            memset_0(ValueName, 0, 0x4Eu);
          }
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return DeviceCompatFlagsInternal;
}

```

## disassembly

```asm
0x180075d04  push    rbp
0x180075d06  push    rbx
0x180075d07  push    rsi
0x180075d08  push    rdi
0x180075d09  lea     rbp, [rsp-1D8h]
0x180075d11  sub     rsp, 2D8h
0x180075d18  mov     rax, cs:__security_cookie
0x180075d1f  xor     rax, rsp
0x180075d22  mov     [rbp+1F0h+var_30], rax
0x180075d29  mov     ebx, edx
0x180075d2b  mov     rsi, rcx
0x180075d2e  xor     edx, edx; Val
0x180075d30  lea     rcx, [rbp+1F0h+var_240]; void *
0x180075d34  mov     r8d, 0D2h; Size
0x180075d3a  call    memset_0
0x180075d3f  xor     edx, edx; Val
0x180075d41  lea     rcx, [rbp+1F0h+var_160]; void *
0x180075d48  mov     r8d, 130h; Size
0x180075d4e  call    memset_0
0x180075d53  test    ebx, ebx
0x180075d55  jz      short loc_180075D6E
0x180075d57  cmp     ebx, 1
0x180075d5a  jz      short loc_180075D65
0x180075d5c  lea     rdi, aUnknown_0; "Unknown"
0x180075d63  jmp     short loc_180075D75
0x180075d65  lea     rdi, aCamdevice; "CamDevice"
0x180075d6c  jmp     short loc_180075D75
0x180075d6e  lea     rdi, aCamacpirotatio; "CamAcpiRotation"
0x180075d75  xor     ebx, ebx
0x180075d77  mov     [rsp+2F0h+hKey], 0
0x180075d80  mov     [rsp+2F0h+var_2A8], 0
0x180075d89  test    rsi, rsi
0x180075d8c  jz      loc_180075EB5
0x180075d92  lea     rdx, [rbp+1F0h+var_240]; unsigned __int16 *
0x180075d96  mov     rcx, rsi; unsigned __int16 *
0x180075d99  call    ?GetFingerprintStringPrefix@@YAJPEBGPEAGK@Z; GetFingerprintStringPrefix(ushort const *,ushort *,ulong)
0x180075d9e  test    eax, eax
0x180075da0  js      loc_180075EB5
0x180075da6  xor     edx, edx
0x180075da8  lea     rcx, [rsp+2F0h+hKey]
0x180075dad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180075db2  lea     rdx, [rsp+2F0h+hKey]
0x180075db7  call    HwCfgGetCurrentKey
0x180075dbc  test    eax, eax
0x180075dbe  jnz     loc_180075EB5
0x180075dc4  xor     edx, edx
0x180075dc6  lea     rcx, [rsp+2F0h+var_2A8]
0x180075dcb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180075dd0  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180075dd5  lea     rax, [rsp+2F0h+var_2A8]
0x180075dda  mov     r9d, 20019h; samDesired
0x180075de0  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180075de5  xor     r8d, r8d; ulOptions
0x180075de8  lea     rdx, aComputerids; "ComputerIds"
0x180075def  call    cs:__imp_RegOpenKeyExW
0x180075df5  test    eax, eax
0x180075df7  jnz     loc_180075EB5
0x180075dfd  xor     edx, edx; Val
0x180075dff  lea     r8d, [rbx+4Eh]; Size
0x180075e03  lea     rcx, [rsp+2F0h+ValueName]; void *
0x180075e08  xor     esi, esi
0x180075e0a  call    memset_0
0x180075e0f  mov     [rsp+2F0h+lpcbData], rbx
0x180075e14  xor     edx, edx
0x180075e16  mov     [rsp+2F0h+lpData], rbx
0x180075e1b  mov     [rsp+2F0h+lpType], rbx
0x180075e20  mov     [rsp+2F0h+phkResult], rbx
0x180075e25  jmp     short loc_180075E90
0x180075e27  lea     rax, [rsp+2F0h+ValueName]
0x180075e2c  mov     edx, 98h; unsigned __int64
0x180075e31  lea     r9, [rbp+1F0h+var_240]
0x180075e35  mov     [rsp+2F0h+phkResult], rax
0x180075e3a  lea     r8, aSystemWsWs; "System:%ws%ws;"
0x180075e41  lea     rcx, [rbp+1F0h+var_160]; unsigned __int16 *
0x180075e48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180075e4d  test    eax, eax
0x180075e4f  js      short loc_180075EB5
0x180075e51  lea     rdx, [rbp+1F0h+var_160]
0x180075e58  mov     rcx, rdi
0x180075e5b  call    ?CameraQueryDeviceCompatFlagsInternal@@YA?ATCAMERA_DEVICE_FLAGS@@PEBGPEAG@Z; CameraQueryDeviceCompatFlagsInternal(ushort const *,ushort *)
0x180075e60  mov     rbx, rax
0x180075e63  test    rax, rax
0x180075e66  jnz     short loc_180075EB5
0x180075e68  inc     esi
0x180075e6a  lea     r8d, [rax+4Eh]; Size
0x180075e6e  xor     edx, edx; Val
0x180075e70  lea     rcx, [rsp+2F0h+ValueName]; void *
0x180075e75  call    memset_0
0x180075e7a  mov     [rsp+2F0h+lpcbData], rbx; lpcbData
0x180075e7f  mov     edx, esi; dwIndex
0x180075e81  mov     [rsp+2F0h+lpData], rbx; lpData
0x180075e86  mov     [rsp+2F0h+lpType], rbx; lpType
0x180075e8b  mov     [rsp+2F0h+phkResult], rbx; lpReserved
0x180075e90  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x180075e95  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x180075e9a  lea     r8, [rsp+2F0h+ValueName]; lpValueName
0x180075e9f  mov     [rsp+2F0h+cchValueName], 27h ; '''
0x180075ea7  call    cs:__imp_RegEnumValueW
0x180075ead  test    eax, eax
0x180075eaf  jz      loc_180075E27
0x180075eb5  lea     rcx, [rsp+2F0h+var_2A8]
0x180075eba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075ebf  lea     rcx, [rsp+2F0h+hKey]
0x180075ec4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180075ec9  mov     rax, rbx
0x180075ecc  mov     rcx, [rbp+1F0h+var_30]
0x180075ed3  xor     rcx, rsp; StackCookie
0x180075ed6  call    __security_check_cookie
0x180075edb  add     rsp, 2D8h
0x180075ee2  pop     rdi
0x180075ee3  pop     rsi
0x180075ee4  pop     rbx
0x180075ee5  pop     rbp
0x180075ee6  retn
```
