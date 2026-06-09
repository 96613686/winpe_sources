# WaasMedic::MiscUtil::IsOobePastThreshold(ulong)

- ea: `0x1800262a8`
- end: `0x18002641d`
- name: `?IsOobePastThreshold@MiscUtil@WaasMedic@@SA_NK@Z`
- size: `373`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a650`

## callees

- `0x1800251a8`
- `0x18002543c`
- `0x1800262a8`
- `0x180028964`
- `0x180030954`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800263c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800263e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800263e5`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026302`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x180026302`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800263b9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800263b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026352`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026392`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026392`

## pseudocode

```c
bool __fastcall WaasMedic::MiscUtil::IsOobePastThreshold(int a1)
{
  SYSTEMTIME *v1; // rsi
  bool v2; // di
  REGSAM v3; // r9d
  LSTATUS v4; // eax
  signed int v5; // ebx
  signed int v6; // eax
  void *v7; // rdx
  signed int LastError; // eax
  unsigned int DaysBetweenFileTimes; // eax
  unsigned int *phkResult; // [rsp+20h] [rbp-58h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-48h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-40h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-38h] BYREF
  int v15; // [rsp+A0h] [rbp+28h] BYREF
  unsigned __int8 *v16; // [rsp+A8h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp+38h] BYREF
  SYSTEMTIME *v18; // [rsp+B8h] [rbp+40h] BYREF

  v15 = a1;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  v2 = 1;
  FileTime = 0;
  LOBYTE(v15) = 0;
  hKey = 0;
  v18 = 0;
  LODWORD(v16) = 0;
  if ( !dword_180098D58 )
  {
    dword_180098D54 = 0;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetNativeSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
      dword_180098D54 = 1;
    dword_180098D58 = 1;
  }
  v3 = 1;
  if ( dword_180098D54 )
    v3 = 257;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats", 0, v3, &hKey);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    v6 = WaasMedic::RegQueryBinaryValue(hKey, (HKEY)&stru_18006C040, (const unsigned __int16 *)&v18, &v16, phkResult);
    v1 = v18;
    v5 = v6;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 >= 0 )
  {
    if ( SystemTimeToFileTime(v1, &FileTime) )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      DaysBetweenFileTimes = WaasMedic::TimeHelper::GetDaysBetweenFileTimes(
                               FileTime,
                               SystemTimeAsFileTime,
                               (bool *)&v15);
      if ( (_BYTE)v15 )
        v2 = DaysBetweenFileTimes >= 0x1E;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"Failed convert SystemTime to FileTime.! hr = 0x%08x", (unsigned int)LastError);
    }
  }
  else
  {
    LogLevelW(2u, L"RegQueryBinaryValue failed for OOBE EndTimeStamp! hr = 0x%08x", (unsigned int)v5);
  }
  WaasMedic::SafeFree((WaasMedic *)v1, v7);
  return v2;
}

```

## disassembly

```asm
0x1800262a8  mov     [rsp-20h+arg_0], ecx
0x1800262ac  push    rbp
0x1800262ad  push    rbx
0x1800262ae  push    rsi
0x1800262af  push    rdi
0x1800262b0  mov     rbp, rsp
0x1800262b3  sub     rsp, 78h
0x1800262b7  xor     esi, esi
0x1800262b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800262c1  cmp     cs:dword_180098D58, esi
0x1800262c7  mov     edi, 1
0x1800262cc  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800262d4  mov     byte ptr [rbp+arg_0], 0
0x1800262d8  mov     [rbp+hKey], 0
0x1800262e0  mov     [rbp+arg_18], rsi
0x1800262e4  mov     dword ptr [rbp+arg_8], esi
0x1800262e7  jnz     short loc_180026326
0x1800262e9  xorps   xmm0, xmm0
0x1800262ec  mov     cs:dword_180098D54, esi
0x1800262f2  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800262f6  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1800262fa  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800262fe  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180026302  call    cs:__imp_GetNativeSystemInfo
0x180026308  lea     eax, [rdi+5]
0x18002630b  cmp     ax, word ptr [rbp+SystemInfo]
0x18002630f  jz      short loc_18002631A
0x180026311  lea     eax, [rdi+8]
0x180026314  cmp     ax, word ptr [rbp+SystemInfo]
0x180026318  jnz     short loc_180026320
0x18002631a  mov     cs:dword_180098D54, edi
0x180026320  mov     cs:dword_180098D58, edi
0x180026326  cmp     cs:dword_180098D54, esi
0x18002632c  mov     r9d, edi
0x18002632f  mov     eax, 101h
0x180026334  cmovnz  r9d, eax; samDesired
0x180026338  lea     rax, [rbp+hKey]
0x18002633c  xor     r8d, r8d; ulOptions
0x18002633f  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026346  mov     [rsp+78h+phkResult], rax; unsigned int *
0x18002634b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026352  call    cs:__imp_RegOpenKeyExW
0x180026358  mov     ebx, eax
0x18002635a  test    eax, eax
0x18002635c  jz      short loc_18002636B
0x18002635e  jle     short loc_180026389
0x180026360  movzx   ebx, ax
0x180026363  or      ebx, 80070000h
0x180026369  jmp     short loc_180026389
0x18002636b  mov     rcx, [rbp+hKey]; hKey
0x18002636f  lea     r9, [rbp+arg_8]; unsigned __int8 **
0x180026373  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x180026377  lea     rdx, stru_18006C040; HKEY
0x18002637e  call    ?RegQueryBinaryValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; WaasMedic::RegQueryBinaryValue(HKEY__ *,ushort const *,uchar * *,ulong *)
0x180026383  mov     rsi, [rbp+arg_18]
0x180026387  mov     ebx, eax
0x180026389  mov     rcx, [rbp+hKey]; hKey
0x18002638d  test    rcx, rcx
0x180026390  jz      short loc_180026398
0x180026392  call    cs:__imp_RegCloseKey
0x180026398  test    ebx, ebx
0x18002639a  jns     short loc_1800263B2
0x18002639c  mov     r8d, ebx
0x18002639f  lea     rdx, aRegquerybinary; "RegQueryBinaryValue failed for OOBE End"...
0x1800263a6  mov     ecx, 2; unsigned __int8
0x1800263ab  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800263b0  jmp     short loc_180026409
0x1800263b2  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800263b6  mov     rcx, rsi; lpSystemTime
0x1800263b9  call    cs:__imp_SystemTimeToFileTime
0x1800263bf  test    eax, eax
0x1800263c1  jnz     short loc_1800263E1
0x1800263c3  call    cs:__imp_GetLastError
0x1800263c9  test    eax, eax
0x1800263cb  jle     short loc_1800263D5
0x1800263cd  movzx   eax, ax
0x1800263d0  or      eax, 80070000h
0x1800263d5  mov     r8d, eax
0x1800263d8  lea     rdx, aFailedConvertS; "Failed convert SystemTime to FileTime.!"...
0x1800263df  jmp     short loc_1800263A6
0x1800263e1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800263e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800263eb  mov     rdx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x1800263ef  lea     r8, [rbp+arg_0]; bool *
0x1800263f3  mov     rcx, qword ptr [rbp+FileTime.dwLowDateTime]; struct _FILETIME
0x1800263f7  call    ?GetDaysBetweenFileTimes@TimeHelper@WaasMedic@@SAKU_FILETIME@@0AEA_N@Z; WaasMedic::TimeHelper::GetDaysBetweenFileTimes(_FILETIME,_FILETIME,bool &)
0x1800263fc  cmp     byte ptr [rbp+arg_0], 0
0x180026400  jz      short loc_180026409
0x180026402  cmp     eax, 1Eh
0x180026405  setnb   dil
0x180026409  mov     rcx, rsi; this
0x18002640c  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180026411  mov     al, dil
0x180026414  add     rsp, 78h
0x180026418  pop     rdi
0x180026419  pop     rsi
0x18002641a  pop     rbx
0x18002641b  pop     rbp
0x18002641c  retn
```
