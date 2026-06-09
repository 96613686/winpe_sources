# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x180079504`
- end: `0x1800795cf`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `203`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079670`

## callees

- `0x180079504`
- `0x180079b18`
- `0x180079de0`
- `0x18007d1b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180079541`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800795a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800795a9`

## string_xrefs

- `0x180079582`: `RegReadStringValue`
- `0x180079593`: `GetWindowsDirectoryWinPE`
- `0x180079554`: `%s: Cannot open registry key %s. Error code: 0x%08x.`

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
0x180079504  mov     r11, rsp
0x180079507  mov     [r11+10h], rbx
0x18007950b  push    rdi
0x18007950c  sub     rsp, 30h
0x180079510  mov     rdi, rcx
0x180079513  mov     qword ptr [rcx], 0
0x18007951a  lea     rax, [r11+8]
0x18007951e  mov     qword ptr [r11+8], 0
0x180079526  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007952d  mov     [r11-18h], rax
0x180079531  mov     r9d, 20019h; samDesired
0x180079537  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x18007953e  xor     r8d, r8d; ulOptions
0x180079541  call    cs:__imp_RegOpenKeyExW
0x180079547  mov     ebx, eax
0x180079549  test    eax, eax
0x18007954b  jz      short loc_18007955D
0x18007954d  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180079554  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open registry key %s. Error "...
0x18007955b  jmp     short loc_180079590
0x18007955d  mov     rcx, [rsp+38h+hKey]; hkey
0x180079562  lea     r9, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180079569  lea     r8, aTargetos; "TargetOS"
0x180079570  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x180079575  xor     edx, edx; lpSubKey
0x180079577  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18007957c  mov     ebx, eax
0x18007957e  test    eax, eax
0x180079580  jz      short loc_18007959F
0x180079582  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180079589  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180079590  mov     r9d, eax
0x180079593  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x18007959a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007959f  mov     rcx, [rsp+38h+hKey]; hKey
0x1800795a4  test    rcx, rcx
0x1800795a7  jz      short loc_1800795AF
0x1800795a9  call    cs:__imp_RegCloseKey
0x1800795af  test    ebx, ebx
0x1800795b1  jz      short loc_1800795C2
0x1800795b3  mov     rcx, [rdi]; void *
0x1800795b6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x1800795bb  mov     qword ptr [rdi], 0
0x1800795c2  mov     eax, ebx
0x1800795c4  mov     rbx, [rsp+38h+arg_8]
0x1800795c9  add     rsp, 30h
0x1800795cd  pop     rdi
0x1800795ce  retn
```
