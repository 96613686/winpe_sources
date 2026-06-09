# ReportDeviceDriverUpdateProgress

- ea: `0x14001bbd8`
- end: `0x14001bd76`
- name: `ReportDeviceDriverUpdateProgress`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001ae4c`

## callees

- `0x14001bbd8`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001bccd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001bccd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001bcf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001bd31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001bcf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001bd31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14001bc72`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14001bc72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001bc46`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001bc46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bd4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001bd4f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001bcb9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001bcb9`

## string_xrefs

- `0x14001bc27`: `Software\Microsoft\Windows\CurrentVersion\Device Installer`

## pseudocode

```c
LSTATUS __fastcall ReportDeviceDriverUpdateProgress(int a1, int a2)
{
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+58h] [rbp+17h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp+1Fh] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+27h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+2Fh] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp+37h] BYREF

  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  *(_QWORD *)Data = 0;
  SystemTime = 0;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Device Installer",
             0,
             0x2000000u,
             &hKey);
  if ( !result )
  {
    if ( (a1 || a2) && (a1 != -1 || a2 != -1) )
    {
      result = RegCreateKeyExW(hKey, L"CurrentStatus", 0, 0, 1u, 2u, 0, &phkResult, &dwDisposition);
      if ( !result )
      {
        if ( dwDisposition == 1 )
        {
          GetSystemTime(&SystemTime);
          RegSetValueExW(phkResult, L"StartTime", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
        }
        *(_DWORD *)&Data[4] = a2;
        *(_DWORD *)Data = a1;
        result = RegSetValueExW(phkResult, L"Progress", 0, 0xBu, Data, 8u);
      }
    }
    else
    {
      result = RegDeleteTreeW(hKey, L"CurrentStatus");
    }
  }
  if ( phkResult )
    result = RegCloseKey(phkResult);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x14001bbd8  mov     r11, rsp
0x14001bbdb  mov     [r11+18h], rbx
0x14001bbdf  mov     [r11+20h], rdi
0x14001bbe3  push    rbp
0x14001bbe4  lea     rbp, [r11-5Fh]
0x14001bbe8  sub     rsp, 90h
0x14001bbef  mov     rax, cs:__security_cookie
0x14001bbf6  xor     rax, rsp
0x14001bbf9  mov     [rbp+57h+var_10], rax
0x14001bbfd  mov     edi, edx
0x14001bbff  mov     [rbp+57h+dwDisposition], 0
0x14001bc06  mov     ebx, ecx
0x14001bc08  mov     [rbp+57h+hKey], 0
0x14001bc10  xorps   xmm0, xmm0
0x14001bc13  mov     [rbp+57h+var_30], 0
0x14001bc1b  lea     rax, [rbp+57h+hKey]
0x14001bc1f  mov     qword ptr [rbp+57h+Data], 0
0x14001bc27  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001bc2e  mov     [r11-78h], rax
0x14001bc32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001bc39  mov     r9d, 2000000h; samDesired
0x14001bc3f  xor     r8d, r8d; ulOptions
0x14001bc42  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x14001bc46  call    cs:__imp_RegOpenKeyExW
0x14001bc4c  test    eax, eax
0x14001bc4e  jnz     loc_14001BD37
0x14001bc54  test    ebx, ebx
0x14001bc56  jnz     short loc_14001BC5C
0x14001bc58  test    edi, edi
0x14001bc5a  jz      short loc_14001BC67
0x14001bc5c  or      eax, 0FFFFFFFFh
0x14001bc5f  cmp     ebx, eax
0x14001bc61  jnz     short loc_14001BC7D
0x14001bc63  cmp     edi, eax
0x14001bc65  jnz     short loc_14001BC7D
0x14001bc67  mov     rcx, [rbp+57h+hKey]; hKey
0x14001bc6b  lea     rdx, aCurrentstatus; "CurrentStatus"
0x14001bc72  call    cs:__imp_RegDeleteTreeW
0x14001bc78  jmp     loc_14001BD37
0x14001bc7d  mov     rcx, [rbp+57h+hKey]; hKey
0x14001bc81  lea     rax, [rbp+57h+dwDisposition]
0x14001bc85  mov     [rsp+90h+lpdwDisposition], rax; lpdwDisposition
0x14001bc8a  lea     rdx, aCurrentstatus; "CurrentStatus"
0x14001bc91  lea     rax, [rbp+57h+var_30]
0x14001bc95  xor     r9d, r9d; lpClass
0x14001bc98  mov     [rsp+90h+phkResult], rax; phkResult
0x14001bc9d  xor     r8d, r8d; Reserved
0x14001bca0  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14001bca9  mov     [rsp+90h+samDesired], 2; samDesired
0x14001bcb1  mov     [rsp+90h+dwOptions], 1; dwOptions
0x14001bcb9  call    cs:__imp_RegCreateKeyExW
0x14001bcbf  test    eax, eax
0x14001bcc1  jnz     short loc_14001BD37
0x14001bcc3  cmp     [rbp+57h+dwDisposition], 1
0x14001bcc7  jnz     short loc_14001BCFE
0x14001bcc9  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x14001bccd  call    cs:__imp_GetSystemTime
0x14001bcd3  mov     rcx, [rbp+57h+var_30]; hKey
0x14001bcd7  lea     rax, [rbp+57h+SystemTime]
0x14001bcdb  mov     [rsp+90h+samDesired], 10h; cbData
0x14001bce3  lea     rdx, aStarttime; "StartTime"
0x14001bcea  mov     r9d, 3; dwType
0x14001bcf0  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x14001bcf5  xor     r8d, r8d; Reserved
0x14001bcf8  call    cs:__imp_RegSetValueExW
0x14001bcfe  mov     rcx, [rbp+57h+var_30]; hKey
0x14001bd02  lea     rdx, aProgress; "Progress"
0x14001bd09  mov     dword ptr [rbp+57h+Data+4], edi
0x14001bd0c  mov     r9d, 0Bh; dwType
0x14001bd12  mov     dword ptr [rbp+57h+Data], ebx
0x14001bd15  xor     r8d, r8d; Reserved
0x14001bd18  mov     rax, qword ptr [rbp+57h+Data]
0x14001bd1c  mov     qword ptr [rbp+57h+Data], rax
0x14001bd20  lea     rax, [rbp+57h+Data]
0x14001bd24  mov     [rsp+90h+samDesired], 8; cbData
0x14001bd2c  mov     qword ptr [rsp+90h+dwOptions], rax; lpData
0x14001bd31  call    cs:__imp_RegSetValueExW
0x14001bd37  mov     rcx, [rbp+57h+var_30]; hKey
0x14001bd3b  test    rcx, rcx
0x14001bd3e  jz      short loc_14001BD46
0x14001bd40  call    cs:__imp_RegCloseKey
0x14001bd46  mov     rcx, [rbp+57h+hKey]; hKey
0x14001bd4a  test    rcx, rcx
0x14001bd4d  jz      short loc_14001BD55
0x14001bd4f  call    cs:__imp_RegCloseKey
0x14001bd55  mov     rcx, [rbp+57h+var_10]
0x14001bd59  xor     rcx, rsp; StackCookie
0x14001bd5c  call    __security_check_cookie
0x14001bd61  lea     r11, [rsp+90h+var_s0]
0x14001bd69  mov     rbx, [r11+20h]
0x14001bd6d  mov     rdi, [r11+28h]
0x14001bd71  mov     rsp, r11
0x14001bd74  pop     rbp
0x14001bd75  retn
```
