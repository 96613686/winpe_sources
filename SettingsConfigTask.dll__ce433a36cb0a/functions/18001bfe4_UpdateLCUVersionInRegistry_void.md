# UpdateLCUVersionInRegistry(void)

- ea: `0x18001bfe4`
- end: `0x18001c149`
- name: `?UpdateLCUVersionInRegistry@@YAXXZ`
- size: `357`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x1800021d0`
- `0x180002cd4`
- `0x18000d5b8`
- `0x18001ba64`
- `0x18001bfe4`
- `0x18001c8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c03d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c03d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001c0bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001c0bc`

## string_xrefs

- `0x18001c069`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`
- `0x18001c094`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`
- `0x18001c120`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
void UpdateLCUVersionInRegistry(void)
{
  LSTATUS ValueW; // eax
  const unsigned __int16 *v1; // rdx
  HKEY v2; // rcx
  unsigned __int64 v3; // r9
  bool v4; // sf
  int v5; // eax
  const unsigned __int16 *v6; // rdx
  HKEY v7; // rcx
  int v8; // eax
  int pdwType; // [rsp+20h] [rbp-89h]
  int pdwTypea; // [rsp+20h] [rbp-89h]
  DWORD pcbData; // [rsp+50h] [rbp-59h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int16 pvData[32]; // [rsp+70h] [rbp-39h] BYREF
  wchar_t Buffer[32]; // [rsp+B0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pcbData = 64;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
             L"LCUVer",
             2u,
             0,
             pvData,
             &pcbData);
  v3 = (unsigned int)ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    v4 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    v3 = (unsigned __int16)ValueW | 0x80070000;
  }
  v4 = (v3 & 0x80000000) != 0LL;
LABEL_5:
  if ( v4 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
      (const char *)v3,
      pdwType);
  }
  else
  {
    v5 = SHRegSetString(v2, v1, L"LastLCUVersion", pvData);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
        (const char *)(unsigned int)v5,
        pdwType);
    SettingsDownloadTelemetry::InitialTask_UpdatedNewOSBuildVersion<unsigned short (&)[32]>(pvData);
  }
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  pdwTypea = SystemTime.wMonth;
  swprintf_s(Buffer, 0x20u, L"%04d-%02d-%02d %02d:%02d:%02d", SystemTime.wYear);
  v8 = SHRegSetString(v7, v6, L"LastLCUTimestamp", Buffer);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
      (const char *)(unsigned int)v8,
      pdwTypea);
}

```

## disassembly

```asm
0x18001bfe4  push    rbp
0x18001bfe6  lea     rbp, [rsp-57h]
0x18001bfeb  sub     rsp, 100h
0x18001bff2  mov     rax, cs:__security_cookie
0x18001bff9  xor     rax, rsp
0x18001bffc  mov     [rbp+57h+var_10], rax
0x18001c000  lea     rax, [rbp+57h+var_B0]
0x18001c004  mov     [rbp+57h+var_B0], 40h ; '@'
0x18001c00b  mov     [rsp+100h+pcbData], rax; pcbData
0x18001c010  lea     r8, aLcuver; "LCUVer"
0x18001c017  lea     rax, [rbp+57h+var_90]
0x18001c01b  mov     r9d, 2; dwFlags
0x18001c021  mov     [rsp+100h+pvData], rax; pvData
0x18001c026  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001c02d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c034  mov     [rsp+100h+pdwType], 0; int
0x18001c03d  call    cs:__imp_RegGetValueW
0x18001c043  mov     r9d, eax
0x18001c046  test    eax, eax
0x18001c048  jz      short loc_18001C060
0x18001c04a  xor     eax, eax
0x18001c04c  mov     [rbp+57h+var_90], ax
0x18001c050  test    r9d, r9d
0x18001c053  jle     short loc_18001C063
0x18001c055  movzx   r9d, r9w
0x18001c059  or      r9d, 80070000h; char *
0x18001c060  test    r9d, r9d
0x18001c063  jns     short loc_18001C07C
0x18001c065  mov     rcx, [rbp+5Fh]; this
0x18001c069  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001c070  mov     edx, 51h ; 'Q'; void *
0x18001c075  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c07a  jmp     short loc_18001C0B1
0x18001c07c  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x18001c080  lea     r8, aLastlcuversion; "LastLCUVersion"
0x18001c087  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001c08c  test    eax, eax
0x18001c08e  jns     short loc_18001C0A8
0x18001c090  mov     rcx, [rbp+5Fh]; this
0x18001c094  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001c09b  mov     r9d, eax; char *
0x18001c09e  mov     edx, 55h ; 'U'; void *
0x18001c0a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c0a8  lea     rcx, [rbp+57h+var_90]
0x18001c0ac  call    ??$InitialTask_UpdatedNewOSBuildVersion@AEAY0CA@G@SettingsDownloadTelemetry@@SAXAEAY0CA@G@Z; SettingsDownloadTelemetry::InitialTask_UpdatedNewOSBuildVersion<ushort (&)[32]>(ushort (&)[32])
0x18001c0b1  xorps   xmm0, xmm0
0x18001c0b4  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001c0b8  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001c0bc  call    cs:__imp_GetLocalTime
0x18001c0c2  movzx   ecx, [rbp+57h+SystemTime.wMinute]
0x18001c0c6  movzx   edx, [rbp+57h+SystemTime.wHour]
0x18001c0ca  movzx   r8d, [rbp+57h+SystemTime.wDay]
0x18001c0cf  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x18001c0d3  movzx   r10d, [rbp+57h+SystemTime.wMonth]
0x18001c0d8  movzx   r9d, [rbp+57h+SystemTime.wYear]
0x18001c0dd  mov     [rsp+100h+var_C0], eax
0x18001c0e1  mov     [rsp+100h+var_C8], ecx
0x18001c0e5  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001c0e9  mov     dword ptr [rsp+100h+pcbData], edx
0x18001c0ed  mov     edx, 20h ; ' '; BufferCount
0x18001c0f2  mov     dword ptr [rsp+100h+pvData], r8d
0x18001c0f7  lea     r8, a04d02d02d02d02; "%04d-%02d-%02d %02d:%02d:%02d"
0x18001c0fe  mov     dword ptr [rsp+100h+pdwType], r10d; int
0x18001c103  call    swprintf_s
0x18001c108  lea     r9, [rbp+57h+Buffer]; unsigned __int16 *
0x18001c10c  lea     r8, aLastlcutimesta; "LastLCUTimestamp"
0x18001c113  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18001c118  test    eax, eax
0x18001c11a  jns     short loc_18001C134
0x18001c11c  mov     rcx, [rbp+5Fh]; this
0x18001c120  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001c127  mov     r9d, eax; char *
0x18001c12a  mov     edx, 66h ; 'f'; void *
0x18001c12f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c134  mov     rcx, [rbp+57h+var_10]
0x18001c138  xor     rcx, rsp; StackCookie
0x18001c13b  call    __security_check_cookie
0x18001c140  add     rsp, 100h
0x18001c147  pop     rbp
0x18001c148  retn
```
