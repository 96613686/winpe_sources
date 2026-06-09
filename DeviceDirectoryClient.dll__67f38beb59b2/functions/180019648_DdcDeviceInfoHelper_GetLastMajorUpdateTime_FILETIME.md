# DdcDeviceInfoHelper::GetLastMajorUpdateTime(_FILETIME *)

- ea: `0x180019648`
- end: `0x180019810`
- name: `?GetLastMajorUpdateTime@DdcDeviceInfoHelper@@CAJPEAU_FILETIME@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct _FILETIME *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800024c0`
- `0x1800050b8`
- `0x180019648`
- `0x18001b844`
- `0x18001b9e0`
- `0x18001bae4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001974a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001974a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019740`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019740`

## string_xrefs

- `0x1800196da`: `SOFTWARE\Microsoft\WindowsUpdate\Orchestrator\Installation\Target`
- `0x1800196d3`: `UpdateTimestamp`
- `0x1800196f2`: `OobeCompleteTime`
- `0x180019721`: `OobeCompleteTime`
- `0x18001978f`: `InstallDate`
- `0x1800196bb`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcDeviceInfoHelper::GetLastMajorUpdateTime(struct _FILETIME *a1, int a2)
{
  unsigned int v3; // ebx
  HKEY v4; // rcx
  HKEY v5; // rcx
  signed int LastError; // eax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rax
  int v10; // edx
  int v11; // ecx
  unsigned int v13; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-2Ch] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-28h] BYREF
  struct _FILETIME FileTime; // [rsp+40h] [rbp-20h] BYREF
  SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  v14 = 16;
  v15 = 0;
  v13 = 0;
  FileTime = 0;
  SystemTime = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        173,
        "CPR(pftTime)");
    return v3;
  }
  if ( DdcRegistry::GetQWORDValue(
         (HKEY)a1,
         L"SOFTWARE\\Microsoft\\WindowsUpdate\\Orchestrator\\Installation\\Target",
         L"UpdateTimestamp",
         &v15) >= 0
    || DdcRegistry::GetQWORDValue(v4, L"SOFTWARE\\Microsoft\\Shell\\OOBE", L"OobeCompleteTime", &v15) >= 0 )
  {
    v9 = v15;
    goto LABEL_19;
  }
  if ( (int)DdcRegistry::GetByteValue(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
              L"OobeCompleteTime",
              (unsigned __int8 *const)&SystemTime,
              &v14) >= 0 )
  {
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v8,
          v7,
          v3,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          189,
          "CBR(SystemTimeToFileTime(&stSystemTime, &ftTime.ftTime))");
      return v3;
    }
    v9 = (__int64)FileTime;
LABEL_19:
    v3 = 0;
    *a1 = (struct _FILETIME)v9;
    return v3;
  }
  if ( (int)DdcRegistry::GetDWORDValue(
              v5,
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
              L"InstallDate",
              (BYTE *)&v13) >= 0 )
  {
    v9 = 10000000 * ((int)v13 + 0x2B6109100LL);
    goto LABEL_19;
  }
  v3 = -2147024894;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v11,
      v10,
      -2147024894,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      203,
      "CHR(HRESULT_FROM_WIN32(2L))");
  return v3;
}

```

## disassembly

```asm
0x180019648  mov     [rsp-8+arg_8], rbx
0x18001964d  mov     [rsp-8+arg_10], rdi
0x180019652  push    rbp
0x180019653  mov     rbp, rsp
0x180019656  sub     rsp, 60h
0x18001965a  mov     rax, cs:__security_cookie
0x180019661  xor     rax, rsp
0x180019664  mov     [rbp+var_8], rax
0x180019668  mov     [rbp+var_2C], 10h
0x18001966f  xorps   xmm0, xmm0
0x180019672  mov     [rbp+var_28], 0
0x18001967a  mov     rdi, rcx
0x18001967d  mov     [rbp+var_30], 0
0x180019684  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18001968c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180019690  test    rcx, rcx
0x180019693  jnz     short loc_1800196CF
0x180019695  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001969c  mov     ebx, 80070057h
0x1800196a1  jz      loc_1800197F0
0x1800196a7  lea     rax, aCprPfttime; "CPR(pftTime)"
0x1800196ae  mov     [rsp+60h+var_38], rax
0x1800196b3  mov     dword ptr [rsp+60h+var_40], 6ADh
0x1800196bb  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800196c2  mov     r8d, ebx
0x1800196c5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800196ca  jmp     loc_1800197F0
0x1800196cf  lea     r9, [rbp+var_28]; unsigned __int64 *
0x1800196d3  lea     r8, aUpdatetimestam; "UpdateTimestamp"
0x1800196da  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\WindowsUpdate\\Orc"...
0x1800196e1  call    ?GetQWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEA_K@Z; DdcRegistry::GetQWORDValue(HKEY__ *,ushort const *,ushort const *,unsigned __int64 &)
0x1800196e6  test    eax, eax
0x1800196e8  jns     loc_1800197E7
0x1800196ee  lea     r9, [rbp+var_28]; unsigned __int64 *
0x1800196f2  lea     r8, aOobecompleteti; "OobeCompleteTime"
0x1800196f9  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Shell\\OOBE"
0x180019700  call    ?GetQWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEA_K@Z; DdcRegistry::GetQWORDValue(HKEY__ *,ushort const *,ushort const *,unsigned __int64 &)
0x180019705  test    eax, eax
0x180019707  jns     loc_1800197E7
0x18001970d  lea     rax, [rbp+var_2C]
0x180019711  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180019718  lea     r9, [rbp+SystemTime]; unsigned __int8 *
0x18001971c  mov     [rsp+60h+var_40], rax; unsigned int *
0x180019721  lea     r8, aOobecompleteti; "OobeCompleteTime"
0x180019728  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001972f  call    ?GetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1QEAEAEAK@Z; DdcRegistry::GetByteValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong &)
0x180019734  test    eax, eax
0x180019736  js      short loc_18001978B
0x180019738  lea     rdx, [rbp+FileTime]; lpFileTime
0x18001973c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180019740  call    cs:__imp_SystemTimeToFileTime
0x180019746  test    eax, eax
0x180019748  jnz     short loc_180019785
0x18001974a  call    cs:__imp_GetLastError
0x180019750  mov     ebx, eax
0x180019752  test    eax, eax
0x180019754  jle     short loc_18001975F
0x180019756  movzx   ebx, ax
0x180019759  or      ebx, 80070000h
0x18001975f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180019766  jz      loc_1800197F0
0x18001976c  lea     rax, aCbrSystemtimet; "CBR(SystemTimeToFileTime(&stSystemTime,"...
0x180019773  mov     [rsp+60h+var_38], rax
0x180019778  mov     dword ptr [rsp+60h+var_40], 6BDh
0x180019780  jmp     loc_1800196BB
0x180019785  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x180019789  jmp     short loc_1800197EB
0x18001978b  lea     r9, [rbp+var_30]; unsigned int *
0x18001978f  lea     r8, aInstalldate; "InstallDate"
0x180019796  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001979d  call    ?GetDWORDValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAK@Z; DdcRegistry::GetDWORDValue(HKEY__ *,ushort const *,ushort const *,ulong &)
0x1800197a2  test    eax, eax
0x1800197a4  js      short loc_1800197C0
0x1800197a6  movsxd  rax, [rbp+var_30]
0x1800197aa  mov     rcx, 2B6109100h
0x1800197b4  add     rax, rcx
0x1800197b7  imul    rax, 989680h
0x1800197be  jmp     short loc_1800197EB
0x1800197c0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800197c7  mov     ebx, 80070002h
0x1800197cc  jz      short loc_1800197F0
0x1800197ce  lea     rax, aChrHresultFrom; "CHR(HRESULT_FROM_WIN32(2L))"
0x1800197d5  mov     [rsp+60h+var_38], rax
0x1800197da  mov     dword ptr [rsp+60h+var_40], 6CBh
0x1800197e2  jmp     loc_1800196BB
0x1800197e7  mov     rax, [rbp+var_28]
0x1800197eb  xor     ebx, ebx
0x1800197ed  mov     [rdi], rax
0x1800197f0  mov     eax, ebx
0x1800197f2  mov     rcx, [rbp+var_8]
0x1800197f6  xor     rcx, rsp; StackCookie
0x1800197f9  call    __security_check_cookie
0x1800197fe  lea     r11, [rsp+60h+var_s0]
0x180019803  mov     rbx, [r11+18h]
0x180019807  mov     rdi, [r11+20h]
0x18001980b  mov     rsp, r11
0x18001980e  pop     rbp
0x18001980f  retn
```
