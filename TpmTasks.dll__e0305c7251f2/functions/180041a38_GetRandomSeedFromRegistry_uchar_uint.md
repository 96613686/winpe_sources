# GetRandomSeedFromRegistry(uchar *,uint)

- ea: `0x180041a38`
- end: `0x180041b79`
- name: `?GetRandomSeedFromRegistry@@YAJPEAEI@Z`
- size: `321`
- prototype: `__int64 __fastcall(LPBYTE lpData, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180041728`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x180041a38`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180041ab7`
- `ntdll!RtlGetPersistedStateLocation` at `0x180041ab7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041b29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180041b29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041b49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041b49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041aef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041aef`

## string_xrefs

- `0x180041a99`: `System\CurrentControlSet\Services\TPM\ODUID`

## pseudocode

```c
__int64 __fastcall GetRandomSeedFromRegistry(LPBYTE lpData)
{
  int PersistedStateLocation; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS Value; // eax
  int v7[4]; // [rsp+40h] [rbp-258h] BYREF
  DWORD cbData[4]; // [rsp+50h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-228h] BYREF

  cbData[0] = 32;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  memset_0(SubKey, 0, 0x208u);
  v7[0] = 520;
  if ( lpData )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"OfflineDeviceID",
                               0,
                               L"System\\CurrentControlSet\\Services\\TPM\\ODUID",
                               0,
                               SubKey,
                               520,
                               v7);
    v3 = PersistedStateLocation;
    if ( PersistedStateLocation > 0 )
      v3 = (unsigned __int16)PersistedStateLocation | 0x80070000;
    if ( v3 >= 0 )
    {
      v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 3u, &hKey);
      v3 = v4;
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      if ( v3 >= 0 )
      {
        Value = RegQueryValueExW(hKey, L"RandomSeed", 0, 0, lpData, cbData);
        v3 = Value;
        if ( Value > 0 )
          v3 = (unsigned __int16)Value | 0x80070000;
      }
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180041a38  mov     [rsp+arg_8], rbx
0x180041a3d  push    rdi
0x180041a3e  sub     rsp, 290h
0x180041a45  mov     rax, cs:__security_cookie
0x180041a4c  xor     rax, rsp
0x180041a4f  mov     [rsp+298h+var_18], rax
0x180041a57  mov     rdi, rcx
0x180041a5a  mov     [rsp+298h+cbData], 20h ; ' '
0x180041a62  mov     ebx, 208h
0x180041a67  mov     [rsp+298h+hKey], 0FFFFFFFFFFFFFFFFh
0x180041a70  mov     r8d, ebx; Size
0x180041a73  lea     rcx, [rsp+298h+SubKey]; void *
0x180041a78  xor     edx, edx; Val
0x180041a7a  call    memset_0
0x180041a7f  mov     [rsp+298h+var_258], ebx
0x180041a83  test    rdi, rdi
0x180041a86  jz      loc_180041B51
0x180041a8c  lea     rax, [rsp+298h+var_258]
0x180041a91  xor     r9d, r9d
0x180041a94  mov     [rsp+298h+var_268], rax
0x180041a99  lea     r8, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\TP"...
0x180041aa0  lea     rax, [rsp+298h+SubKey]
0x180041aa5  mov     dword ptr [rsp+298h+lpcbData], ebx
0x180041aa9  xor     edx, edx
0x180041aab  mov     [rsp+298h+phkResult], rax
0x180041ab0  lea     rcx, aOfflinedevicei_0; "OfflineDeviceID"
0x180041ab7  call    cs:__imp_RtlGetPersistedStateLocation
0x180041abd  mov     ebx, eax
0x180041abf  test    eax, eax
0x180041ac1  jle     short loc_180041ACC
0x180041ac3  movzx   ebx, ax
0x180041ac6  or      ebx, 80070000h
0x180041acc  test    ebx, ebx
0x180041ace  js      short loc_180041B3E
0x180041ad0  lea     rax, [rsp+298h+hKey]
0x180041ad5  mov     r9d, 3; samDesired
0x180041adb  xor     r8d, r8d; ulOptions
0x180041ade  mov     [rsp+298h+phkResult], rax; phkResult
0x180041ae3  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x180041ae8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180041aef  call    cs:__imp_RegOpenKeyExW
0x180041af5  mov     ebx, eax
0x180041af7  test    eax, eax
0x180041af9  jle     short loc_180041B04
0x180041afb  movzx   ebx, ax
0x180041afe  or      ebx, 80070000h
0x180041b04  test    ebx, ebx
0x180041b06  js      short loc_180041B3E
0x180041b08  mov     rcx, [rsp+298h+hKey]; hKey
0x180041b0d  lea     rax, [rsp+298h+cbData]
0x180041b12  mov     [rsp+298h+lpcbData], rax; lpcbData
0x180041b17  lea     rdx, aRandomseed; "RandomSeed"
0x180041b1e  xor     r9d, r9d; lpType
0x180041b21  mov     [rsp+298h+phkResult], rdi; lpData
0x180041b26  xor     r8d, r8d; lpReserved
0x180041b29  call    cs:__imp_RegQueryValueExW
0x180041b2f  mov     ebx, eax
0x180041b31  test    eax, eax
0x180041b33  jle     short loc_180041B3E
0x180041b35  movzx   ebx, ax
0x180041b38  or      ebx, 80070000h
0x180041b3e  mov     rcx, [rsp+298h+hKey]; hKey
0x180041b43  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180041b47  jz      short loc_180041B56
0x180041b49  call    cs:__imp_RegCloseKey
0x180041b4f  jmp     short loc_180041B56
0x180041b51  mov     ebx, 80070057h
0x180041b56  mov     eax, ebx
0x180041b58  mov     rcx, [rsp+298h+var_18]
0x180041b60  xor     rcx, rsp; StackCookie
0x180041b63  call    __security_check_cookie
0x180041b68  mov     rbx, [rsp+298h+arg_8]
0x180041b70  add     rsp, 290h
0x180041b77  pop     rdi
0x180041b78  retn
```
