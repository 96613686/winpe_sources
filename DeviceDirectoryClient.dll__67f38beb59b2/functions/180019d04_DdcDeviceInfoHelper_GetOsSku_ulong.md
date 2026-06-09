# DdcDeviceInfoHelper::GetOsSku(ulong *)

- ea: `0x180019d04`
- end: `0x180019e5e`
- name: `?GetOsSku@DdcDeviceInfoHelper@@CAJPEAK@Z`
- size: `346`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x180019d04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019dfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019d8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180019d8c`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180019df2`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180019df2`

## string_xrefs

- `0x180019d6b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180019e1a`: `CBR(GetProductInfo(osVersion.dwMajorVersion, osVersion.dwMinorVersion, osVersion.wServicePackMajor, osVersion.wServicePackMinor, &dwSku))`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::GetOsSku(unsigned int *a1)
{
  int v2; // edx
  int v3; // ecx
  unsigned int v4; // ebx
  signed int v5; // eax
  int v6; // edx
  int v7; // ecx
  signed int LastError; // eax
  int v9; // edx
  int v10; // ecx
  DWORD pdwReturnedProductType[4]; // [rsp+30h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-138h] BYREF
  unsigned __int16 v14; // [rsp+154h] [rbp-24h]
  unsigned __int16 v15; // [rsp+156h] [rbp-22h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  pdwReturnedProductType[0] = 0;
  if ( a1 )
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation) )
    {
      if ( GetProductInfo(
             VersionInformation.dwMajorVersion,
             VersionInformation.dwMinorVersion,
             v14,
             v15,
             pdwReturnedProductType) )
      {
        v4 = 0;
        *a1 = pdwReturnedProductType[0];
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v10,
            v9,
            v4,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
            89,
            "CBR(GetProductInfo(osVersion.dwMajorVersion, osVersion.dwMinorVersion, osVersion.wServicePackMajor, osVersio"
            "n.wServicePackMinor, &dwSku))");
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v4,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          84,
          "CBR(GetVersionExW((OSVERSIONINFO *)&osVersion))");
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        81,
        "CPR(pdwSku)");
  }
  return v4;
}

```

## disassembly

```asm
0x180019d04  mov     [rsp+arg_8], rbx
0x180019d09  push    rdi
0x180019d0a  sub     rsp, 170h
0x180019d11  mov     rax, cs:__security_cookie
0x180019d18  xor     rax, rsp
0x180019d1b  mov     [rsp+178h+var_18], rax
0x180019d23  mov     rdi, rcx
0x180019d26  xor     edx, edx; Val
0x180019d28  lea     rcx, [rsp+178h+VersionInformation.dwMajorVersion]; void *
0x180019d2d  mov     r8d, 118h; Size
0x180019d33  call    memset_0
0x180019d38  mov     [rsp+178h+var_148], 0
0x180019d40  test    rdi, rdi
0x180019d43  jnz     short loc_180019D7F
0x180019d45  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019d4c  mov     ebx, 80070057h
0x180019d51  jz      loc_180019E3B
0x180019d57  lea     rax, aCprPdwsku; "CPR(pdwSku)"
0x180019d5e  mov     [rsp+178h+var_150], rax
0x180019d63  mov     dword ptr [rsp+178h+pdwReturnedProductType], 651h
0x180019d6b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180019d72  mov     r8d, ebx
0x180019d75  call    McTemplateU0dsqs_EventWriteTransfer
0x180019d7a  jmp     loc_180019E3B
0x180019d7f  lea     rcx, [rsp+178h+VersionInformation]; lpVersionInformation
0x180019d84  mov     [rsp+178h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180019d8c  call    cs:__imp_GetVersionExW
0x180019d92  test    eax, eax
0x180019d94  jnz     short loc_180019DCE
0x180019d96  call    cs:__imp_GetLastError
0x180019d9c  mov     ebx, eax
0x180019d9e  test    eax, eax
0x180019da0  jle     short loc_180019DAB
0x180019da2  movzx   ebx, ax
0x180019da5  or      ebx, 80070000h
0x180019dab  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019db2  jz      loc_180019E3B
0x180019db8  lea     rax, aCbrGetversione; "CBR(GetVersionExW((OSVERSIONINFO *)&osV"...
0x180019dbf  mov     [rsp+178h+var_150], rax
0x180019dc4  mov     dword ptr [rsp+178h+pdwReturnedProductType], 654h
0x180019dcc  jmp     short loc_180019D6B
0x180019dce  movzx   r9d, [rsp+178h+var_22]; dwSpMinorVersion
0x180019dd7  lea     rax, [rsp+178h+var_148]
0x180019ddc  movzx   r8d, [rsp+178h+var_24]; dwSpMajorVersion
0x180019de5  mov     edx, [rsp+178h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x180019de9  mov     ecx, [rsp+178h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180019ded  mov     [rsp+178h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180019df2  call    cs:__imp_GetProductInfo
0x180019df8  test    eax, eax
0x180019dfa  jnz     short loc_180019E33
0x180019dfc  call    cs:__imp_GetLastError
0x180019e02  mov     ebx, eax
0x180019e04  test    eax, eax
0x180019e06  jle     short loc_180019E11
0x180019e08  movzx   ebx, ax
0x180019e0b  or      ebx, 80070000h
0x180019e11  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019e18  jz      short loc_180019E3B
0x180019e1a  lea     rax, aCbrGetproducti; "CBR(GetProductInfo(osVersion.dwMajorVer"...
0x180019e21  mov     [rsp+178h+var_150], rax
0x180019e26  mov     dword ptr [rsp+178h+pdwReturnedProductType], 659h
0x180019e2e  jmp     loc_180019D6B
0x180019e33  mov     ecx, [rsp+178h+var_148]
0x180019e37  xor     ebx, ebx
0x180019e39  mov     [rdi], ecx
0x180019e3b  mov     eax, ebx
0x180019e3d  mov     rcx, [rsp+178h+var_18]
0x180019e45  xor     rcx, rsp; StackCookie
0x180019e48  call    __security_check_cookie
0x180019e4d  mov     rbx, [rsp+178h+arg_8]
0x180019e55  add     rsp, 170h
0x180019e5c  pop     rdi
0x180019e5d  retn
```
