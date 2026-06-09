# Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(void *,_GUID const *,int)

- ea: `0x180025bd0`
- end: `0x180025e1d`
- name: `?BthpRemoveLocalDeviceInstance@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@H@Z`
- size: `589`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Services::BthServ *__hidden this, void *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800234fc`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800086d8`
- `0x180016664`
- `0x180019d04`
- `0x180025bd0`
- `0x18002fb84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025d44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025d5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025cbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025d0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025cbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025d0e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025c90`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180025c90`

## string_xrefs

- `0x180025bfb`: `System\CurrentControlSet\Services\BTHPORT\Parameters\LocalServices\`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3)
{
  unsigned int v3; // edi
  unsigned int v4; // ebx
  __int64 v5; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  BYTE Data[4]; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v11; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[68]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v14[88]; // [rsp+128h] [rbp+28h] BYREF
  WCHAR v15[64]; // [rsp+180h] [rbp+80h] BYREF

  v3 = (unsigned int)a3;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters\\LocalServices\\");
  hKey = 0;
  *(_DWORD *)Data = 0;
  memset_0(v14, 0, 0x4Eu);
  if ( StringFromGUID2(&SerialPortServiceClass_UUID, &SubKey[67], 39) != 39 )
    return 87;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( !v4 )
  {
    if ( (int)StringCchPrintfW(v15, 0x20u, L"%u", v3) >= 0 )
    {
      v11 = 0;
      v4 = RegOpenKeyExW(hKey, v15, 0, 0x20019u, &v11);
      if ( !v4 )
      {
        cbData = 4;
        v4 = RegQueryValueExW(v11, L"PnpInstance", 0, 0, Data, &cbData);
        RegCloseKey(v11);
      }
    }
    RegCloseKey(hKey);
    if ( !v4 )
    {
      LODWORD(lpcbData) = 4096;
      LODWORD(phkResult) = 0;
      if ( (int)StringCbPrintfW(
                  v15,
                  0x7Cu,
                  L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}#000000000000_%08x",
                  4353,
                  phkResult,
                  lpcbData,
                  128,
                  0,
                  0,
                  128,
                  95,
                  155,
                  52,
                  251,
                  *(_DWORD *)Data) >= 0 )
      {
        if ( (int)BthDevnodeSearchAndUninstallEnumerator(v5, v15) < 0 )
          return (unsigned int)BthServClientUninstallDevice(0, v15);
        return v4;
      }
      return 87;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180025bd0  mov     [rsp-8+arg_0], rbx
0x180025bd5  mov     [rsp-8+arg_8], rdi
0x180025bda  push    rbp
0x180025bdb  lea     rbp, [rsp-110h]
0x180025be3  sub     rsp, 210h
0x180025bea  mov     rax, cs:__security_cookie
0x180025bf1  xor     rax, rsp
0x180025bf4  mov     [rbp+110h+var_10], rax
0x180025bfb  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\BT"...
0x180025c02  lea     rcx, [rbp+110h+var_E8]; void *
0x180025c06  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+10h; "urrentControlSet\\Services\\BTHPORT\\Pa"...
0x180025c0d  xor     edx, edx; Val
0x180025c0f  mov     rax, qword ptr cs:aSystemCurrentc_1+80h; "es\\"
0x180025c16  mov     edi, r8d
0x180025c19  movups  xmmword ptr [rbp+110h+SubKey], xmm0
0x180025c1d  mov     [rbp+110h+hKey], 0
0x180025c25  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+20h; "ntrolSet\\Services\\BTHPORT\\Parameters"...
0x180025c2c  lea     r8d, [rdx+4Eh]; Size
0x180025c30  movups  [rbp+110h+var_160], xmm1
0x180025c34  mov     dword ptr [rbp+110h+Data], 0
0x180025c3b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+30h; "\\Services\\BTHPORT\\Parameters\\LocalS"...
0x180025c42  movups  [rbp+110h+var_150], xmm0
0x180025c46  mov     qword ptr [rbp+110h+sz], rax
0x180025c4a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+40h; "s\\BTHPORT\\Parameters\\LocalServices\\"
0x180025c51  movups  [rbp+110h+var_140], xmm1
0x180025c55  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+50h; "T\\Parameters\\LocalServices\\"
0x180025c5c  movups  [rbp+110h+var_130], xmm0
0x180025c60  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_1+60h; "ters\\LocalServices\\"
0x180025c67  movups  [rbp+110h+var_120], xmm1
0x180025c6b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_1+70h; "alServices\\"
0x180025c72  movups  [rbp+110h+var_110], xmm0
0x180025c76  movups  [rbp+110h+var_100], xmm1
0x180025c7a  call    memset_0
0x180025c7f  mov     r8d, 27h ; '''; cchMax
0x180025c85  lea     rdx, [rbp+110h+sz+6]; lpsz
0x180025c89  lea     rcx, SerialPortServiceClass_UUID; rguid
0x180025c90  call    cs:__imp_StringFromGUID2
0x180025c96  cmp     eax, 27h ; '''
0x180025c99  jnz     loc_180025DF2
0x180025c9f  lea     rax, [rbp+110h+hKey]
0x180025ca3  mov     r9d, 20019h; samDesired
0x180025ca9  xor     r8d, r8d; ulOptions
0x180025cac  mov     [rsp+210h+phkResult], rax; phkResult
0x180025cb1  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x180025cb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025cbc  call    cs:__imp_RegOpenKeyExW
0x180025cc2  mov     ebx, eax
0x180025cc4  test    eax, eax
0x180025cc6  jnz     loc_180025DF7
0x180025ccc  mov     r9d, edi
0x180025ccf  lea     r8, aU; "%u"
0x180025cd6  lea     edx, [rax+20h]; unsigned __int64
0x180025cd9  lea     rcx, [rbp+110h+var_90]; unsigned __int16 *
0x180025ce0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025ce5  test    eax, eax
0x180025ce7  js      short loc_180025D56
0x180025ce9  mov     rcx, [rbp+110h+hKey]; hKey
0x180025ced  lea     rax, [rbp+110h+var_188]
0x180025cf1  mov     r9d, 20019h; samDesired
0x180025cf7  mov     [rsp+210h+phkResult], rax; phkResult
0x180025cfc  xor     r8d, r8d; ulOptions
0x180025cff  mov     [rbp+110h+var_188], 0
0x180025d07  lea     rdx, [rbp+110h+var_90]; lpSubKey
0x180025d0e  call    cs:__imp_RegOpenKeyExW
0x180025d14  mov     ebx, eax
0x180025d16  test    eax, eax
0x180025d18  jnz     short loc_180025D56
0x180025d1a  mov     rcx, [rbp+110h+var_188]; hKey
0x180025d1e  lea     rax, [rbp+110h+cbData]
0x180025d22  mov     [rsp+210h+lpcbData], rax; lpcbData
0x180025d27  lea     rdx, aPnpinstance; "PnpInstance"
0x180025d2e  lea     rax, [rbp+110h+Data]
0x180025d32  mov     [rbp+110h+cbData], 4
0x180025d39  xor     r9d, r9d; lpType
0x180025d3c  mov     [rsp+210h+phkResult], rax; lpData
0x180025d41  xor     r8d, r8d; lpReserved
0x180025d44  call    cs:__imp_RegQueryValueExW
0x180025d4a  mov     rcx, [rbp+110h+var_188]; hKey
0x180025d4e  mov     ebx, eax
0x180025d50  call    cs:__imp_RegCloseKey
0x180025d56  mov     rcx, [rbp+110h+hKey]; hKey
0x180025d5a  call    cs:__imp_RegCloseKey
0x180025d60  test    ebx, ebx
0x180025d62  jnz     loc_180025DF7
0x180025d68  mov     eax, dword ptr [rbp+110h+Data]
0x180025d6b  lea     r8, a08lx04x04x02x0_0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180025d72  mov     [rsp+210h+var_1A0], eax
0x180025d76  lea     edx, [rbx+7Ch]; unsigned __int64
0x180025d79  mov     [rsp+210h+var_1A8], 0FBh
0x180025d81  lea     rcx, [rbp+110h+var_90]; unsigned __int16 *
0x180025d88  mov     [rsp+210h+var_1B0], 34h ; '4'
0x180025d90  mov     eax, 80h
0x180025d95  mov     [rsp+210h+var_1B8], 9Bh
0x180025d9d  mov     r9d, 1101h
0x180025da3  mov     [rsp+210h+var_1C0], 5Fh ; '_'
0x180025dab  mov     [rsp+210h+var_1C8], eax
0x180025daf  mov     [rsp+210h+var_1D0], ebx
0x180025db3  mov     [rsp+210h+var_1D8], ebx
0x180025db7  mov     [rsp+210h+var_1E0], eax
0x180025dbb  mov     dword ptr [rsp+210h+lpcbData], 1000h
0x180025dc3  mov     dword ptr [rsp+210h+phkResult], ebx
0x180025dc7  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025dcc  test    eax, eax
0x180025dce  js      short loc_180025DF2
0x180025dd0  lea     rdx, [rbp+110h+var_90]
0x180025dd7  call    BthDevnodeSearchAndUninstallEnumerator
0x180025ddc  test    eax, eax
0x180025dde  jns     short loc_180025DF7
0x180025de0  lea     rdx, [rbp+110h+var_90]; unsigned __int16 *
0x180025de7  xor     ecx, ecx; void *
0x180025de9  call    ?BthServClientUninstallDevice@@YAJPEAXPEAG@Z; BthServClientUninstallDevice(void *,ushort *)
0x180025dee  mov     ebx, eax
0x180025df0  jmp     short loc_180025DF7
0x180025df2  mov     ebx, 57h ; 'W'
0x180025df7  mov     eax, ebx
0x180025df9  mov     rcx, [rbp+110h+var_10]
0x180025e00  xor     rcx, rsp; StackCookie
0x180025e03  call    __security_check_cookie
0x180025e08  lea     r11, [rsp+210h+var_s0]
0x180025e10  mov     rbx, [r11+10h]
0x180025e14  mov     rdi, [r11+18h]
0x180025e18  mov     rsp, r11
0x180025e1b  pop     rbp
0x180025e1c  retn
```
