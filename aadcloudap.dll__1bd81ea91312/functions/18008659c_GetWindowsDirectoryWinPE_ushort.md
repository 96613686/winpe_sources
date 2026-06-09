# GetWindowsDirectoryWinPE(ushort * *)

- ea: `0x18008659c`
- end: `0x18008666f`
- name: `?GetWindowsDirectoryWinPE@@YAKPEAPEAG@Z`
- size: `211`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086824`

## callees

- `0x18008659c`
- `0x180086cdc`
- `0x1800871b4`
- `0x18008aa28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800865d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800865d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086649`

## string_xrefs

- `0x180086622`: `RegReadStringValue`
- `0x1800865ec`: `%s: Cannot open registry key %s. Error code: 0x%08x.`
- `0x180086633`: `GetWindowsDirectoryWinPE`

## pseudocode

```c
__int64 __fastcall GetWindowsDirectoryWinPE(unsigned __int16 **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int StringValue; // eax
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
                    2u,
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
0x18008659c  mov     r11, rsp
0x18008659f  mov     [r11+10h], rbx
0x1800865a3  push    rdi
0x1800865a4  sub     rsp, 30h
0x1800865a8  mov     rdi, rcx
0x1800865ab  mov     qword ptr [rcx], 0
0x1800865b2  lea     rax, [r11+8]
0x1800865b6  mov     qword ptr [r11+8], 0
0x1800865be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800865c5  mov     [r11-18h], rax
0x1800865c9  mov     r9d, 20019h; samDesired
0x1800865cf  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\RecoveryEnvironmen"...
0x1800865d6  xor     r8d, r8d; ulOptions
0x1800865d9  call    cs:__imp_RegOpenKeyExW
0x1800865df  mov     ebx, eax
0x1800865e1  test    eax, eax
0x1800865e3  jz      short loc_1800865F5
0x1800865e5  lea     r8, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x1800865ec  lea     rcx, aSCannotOpenReg_2; "%s: Cannot open registry key %s. Error "...
0x1800865f3  jmp     short loc_180086630
0x1800865f5  mov     rcx, [rsp+38h+hKey]; hkey
0x1800865fa  lea     r9, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft"...
0x180086601  mov     [rsp+38h+var_10], rdi; unsigned __int16 **
0x180086606  lea     r8, aTargetos; "TargetOS"
0x18008660d  xor     edx, edx; lpSubKey
0x18008660f  mov     [rsp+38h+dwFlags], 2; dwFlags
0x180086617  call    ?RegReadStringValue@@YAKPEAUHKEY__@@PEBG11KPEAPEAG@Z; RegReadStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ushort * *)
0x18008661c  mov     ebx, eax
0x18008661e  test    eax, eax
0x180086620  jz      short loc_18008663F
0x180086622  lea     r8, aRegreadstringv; "RegReadStringValue"
0x180086629  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180086630  mov     r9d, eax
0x180086633  lea     rdx, aGetwindowsdire; "GetWindowsDirectoryWinPE"
0x18008663a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008663f  mov     rcx, [rsp+38h+hKey]; hKey
0x180086644  test    rcx, rcx
0x180086647  jz      short loc_18008664F
0x180086649  call    cs:__imp_RegCloseKey
0x18008664f  test    ebx, ebx
0x180086651  jz      short loc_180086662
0x180086653  mov     rcx, [rdi]; void *
0x180086656  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008665b  mov     qword ptr [rdi], 0
0x180086662  mov     eax, ebx
0x180086664  mov     rbx, [rsp+38h+arg_8]
0x180086669  add     rsp, 30h
0x18008666d  pop     rdi
0x18008666e  retn
```
