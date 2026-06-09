# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x180018f50`
- end: `0x18001901b`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `203`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab5c`

## callees

- `0x1800088f0`
- `0x18000b3c4`
- `0x180018f50`
- `0x180019024`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018f8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018f8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ff5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ff5`

## string_xrefs

- `0x180018fce`: `RegReadStringValue`
- `0x180018fdf`: `GetWindowsDirectoryWinPE`
- `0x180018fa0`: `%s: Cannot open registry key %s. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall GetWindowsDirectoryWinPE(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int StringValue; // eax
  DWORD v6; // [rsp+20h] [rbp-18h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RecoveryEnvironment", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 )
  {
    Logger::TraceError(
      L"%s: Cannot open registry key %s. Error code: 0x%08x.",
      L"GetWindowsDirectoryWinPE",
      L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RecoveryEnvironment",
      v2);
  }
  else
  {
    StringValue = RegReadStringValue(
                    hKey,
                    0,
                    L"TargetOS",
                    L"HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\RecoveryEnvironment",
                    v6,
                    a1);
    v3 = StringValue;
    if ( StringValue )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"GetWindowsDirectoryWinPE",
        L"RegReadStringValue",
        StringValue);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
  {
    SafeFree(*a1);
    *a1 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180018f50  mov     r11, rsp
0x180018f53  mov     [r11+10h], rbx
0x180018f57  push    rdi
0x180018f58  sub     rsp, 30h
0x180018f5c  mov     rdi, rcx
0x180018f5f  mov     qword ptr [rcx], 0
0x180018f66  lea     rax, [r11+8]
0x180018f6a  mov     qword ptr [r11+8], 0
0x180018f72  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018f79  mov     [r11-18h], rax
0x180018f7d  mov     r9d, 20019h; samDesired
0x180018f83  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x180018f8a  xor     r8d, r8d; ulOptions
0x180018f8d  call    cs:__imp_RegOpenKeyExW
0x180018f93  mov     ebx, eax
0x180018f95  test    eax, eax
0x180018f97  jz      short loc_180018FA9
0x180018f99  lea     r8, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180018fa0  lea     rcx, aSCannotOpenReg_1; "%s: Cannot open registry key %s. Error "...
0x180018fa7  jmp     short loc_180018FDC
0x180018fa9  mov     rcx, [rsp+38h+hKey]; hkey
0x180018fae  lea     r9, aHkeyLocalMachi_1; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180018fb5  lea     r8, aTargetos; "TargetOS"
0x180018fbc  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x180018fc1  xor     edx, edx; lpSubKey
0x180018fc3  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x180018fc8  mov     ebx, eax
0x180018fca  test    eax, eax
0x180018fcc  jz      short loc_180018FEB
0x180018fce  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180018fd5  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180018fdc  mov     r9d, eax
0x180018fdf  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x180018fe6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180018feb  mov     rcx, [rsp+38h+hKey]; hKey
0x180018ff0  test    rcx, rcx
0x180018ff3  jz      short loc_180018FFB
0x180018ff5  call    cs:__imp_RegCloseKey
0x180018ffb  test    ebx, ebx
0x180018ffd  jz      short loc_18001900E
0x180018fff  mov     rcx, [rdi]; void *
0x180019002  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180019007  mov     qword ptr [rdi], 0
0x18001900e  mov     eax, ebx
0x180019010  mov     rbx, [rsp+38h+arg_8]
0x180019015  add     rsp, 30h
0x180019019  pop     rdi
0x18001901a  retn
```
