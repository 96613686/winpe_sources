# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::EtwCollectionRecommendedSettings(SessionConfiguration const &)

- ea: `0x180019210`
- end: `0x180019427`
- name: `??0EtwCollectionRecommendedSettings@StandardCollector@DiagnosticsHub@Microsoft@@IEAA@AEBUSessionConfiguration@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings *__hidden this, const struct SessionConfiguration *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a850`

## callees

- `0x18001662c`
- `0x180019210`
- `0x18003d864`
- `0x180049b50`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001927b`
- `KERNEL32!InitializeCriticalSection` at `0x18001927b`
- `ADVAPI32!RegCloseKey` at `0x180019403`
- `ADVAPI32!RegCloseKey` at `0x180019403`
- `ADVAPI32!RegQueryValueExW` at `0x1800192d9`
- `ADVAPI32!RegQueryValueExW` at `0x180019343`
- `ADVAPI32!RegQueryValueExW` at `0x1800193b7`
- `ADVAPI32!RegQueryValueExW` at `0x1800192d9`
- `ADVAPI32!RegQueryValueExW` at `0x180019343`
- `ADVAPI32!RegQueryValueExW` at `0x1800193b7`

## string_xrefs

- `0x180019305`: `Setting ETW buffer size to %dKB from registry for ETW session with provider.`
- `0x18001930c`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\EtwCollectionRecommendedSettings.cpp`
- `0x180019380`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\EtwCollectionRecommendedSettings.cpp`
- `0x1800193eb`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\EtwCollectionRecommendedSettings.cpp`
- `0x180019379`: `Setting ETW minimum buffers to %d from registry for ETW session with provider.`
- `0x1800193e4`: `Setting ETW maximum buffers to %d from registry for ETW session with provider.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings *__fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::EtwCollectionRecommendedSettings(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings *this,
        const struct SessionConfiguration *a2)
{
  char *v3; // rcx
  HKEY v4; // rdx
  int v5; // r9d
  unsigned int v6; // r9d
  int v7; // r9d
  HKEY hKey[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v10; // [rsp+40h] [rbp-30h]
  Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings *v11; // [rsp+48h] [rbp-28h]
  DWORD cbData; // [rsp+50h] [rbp-20h] BYREF
  DWORD Type; // [rsp+54h] [rbp-1Ch] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-18h] BYREF
  BYTE lpData[4]; // [rsp+5Ch] [rbp-14h] BYREF
  BYTE v16[8]; // [rsp+60h] [rbp-10h] BYREF

  v11 = this;
  *(_QWORD *)this = &Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::`vftable';
  *((_DWORD *)this + 2) = 1024;
  *((_DWORD *)this + 3) = 10;
  *((_DWORD *)this + 4) = 30;
  *((_BYTE *)this + 20) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 16) = 0;
  *((_BYTE *)this + 34) = 0;
  v3 = (char *)this + 40;
  *(_OWORD *)v3 = 0;
  *((_OWORD *)v3 + 1) = 0;
  *((_QWORD *)v3 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3);
  hKey[0] = 0;
  hKey[1] = 0;
  v10 = 0;
  if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v4, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub") )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"VsStandardCollector.EtwBufferSize", 0, &Type, Data, &cbData) && Type == 4 )
    {
      v5 = *(_DWORD *)Data;
      if ( *(_DWORD *)Data )
      {
        *((_BYTE *)this + 32) = 1;
        *((_DWORD *)this + 2) = v5;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRecommendedSettings.cpp",
          L"Setting ETW buffer size to %dKB from registry for ETW session with provider.");
      }
    }
    Type = 4;
    if ( !RegQueryValueExW(hKey[0], L"VsStandardCollector.EtwMinBuffers", 0, &cbData, lpData, &Type) && cbData == 4 )
    {
      v6 = *(_DWORD *)lpData;
      if ( *(_DWORD *)lpData )
      {
        *((_BYTE *)this + 33) = 1;
        *((_DWORD *)this + 3) = v6;
        if ( *((_DWORD *)this + 4) < v6 )
          *((_DWORD *)this + 4) = v6;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRecommendedSettings.cpp",
          L"Setting ETW minimum buffers to %d from registry for ETW session with provider.");
      }
    }
    Type = 4;
    if ( !RegQueryValueExW(hKey[0], L"VsStandardCollector.EtwMaxBuffers", 0, &cbData, v16, &Type) && cbData == 4 )
    {
      v7 = *(_DWORD *)v16;
      if ( *(_DWORD *)v16 >= *((_DWORD *)this + 3) )
      {
        *((_BYTE *)this + 34) = 1;
        *((_DWORD *)this + 4) = v7;
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 56),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRecommendedSettings.cpp",
          L"Setting ETW maximum buffers to %d from registry for ETW session with provider.");
      }
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return this;
}

```

## disassembly

```asm
0x180019210  mov     [rsp-8+arg_8], rbx
0x180019215  push    rbp
0x180019216  mov     rbp, rsp
0x180019219  sub     rsp, 70h
0x18001921d  mov     rax, cs:__security_cookie
0x180019224  xor     rax, rsp
0x180019227  mov     [rbp+var_8], rax
0x18001922b  mov     rbx, rcx
0x18001922e  mov     [rbp+var_28], rcx
0x180019232  lea     rax, ??_7EtwCollectionRecommendedSettings@StandardCollector@DiagnosticsHub@Microsoft@@6B@; const Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRecommendedSettings::`vftable'
0x180019239  mov     [rcx], rax
0x18001923c  mov     dword ptr [rcx+8], 400h
0x180019243  mov     dword ptr [rcx+0Ch], 0Ah
0x18001924a  mov     dword ptr [rcx+10h], 1Eh
0x180019251  mov     byte ptr [rcx+14h], 0
0x180019255  mov     qword ptr [rcx+18h], 0
0x18001925d  mov     word ptr [rcx+20h], 0
0x180019263  mov     byte ptr [rcx+22h], 0
0x180019267  add     rcx, 28h ; '('; lpCriticalSection
0x18001926b  xorps   xmm0, xmm0
0x18001926e  xor     eax, eax
0x180019270  movups  xmmword ptr [rcx], xmm0
0x180019273  movups  xmmword ptr [rcx+10h], xmm0
0x180019277  mov     [rcx+20h], rax
0x18001927b  call    cs:__imp_InitializeCriticalSection
0x180019281  nop
0x180019282  xorps   xmm0, xmm0
0x180019285  xor     eax, eax
0x180019287  movups  xmmword ptr [rbp+hKey], xmm0
0x18001928b  mov     [rbp+hKey], rax
0x18001928f  mov     dword ptr [rbp+hKey+8], eax
0x180019292  mov     [rbp+var_30], rax
0x180019296  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x18001929d  lea     rcx, [rbp+hKey]; this
0x1800192a1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800192a6  test    eax, eax
0x1800192a8  jnz     loc_1800193F8
0x1800192ae  mov     [rbp+cbData], 4
0x1800192b5  lea     rax, [rbp+cbData]
0x1800192b9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800192be  lea     rax, [rbp+Data]
0x1800192c2  mov     [rsp+70h+lpData], rax; lpData
0x1800192c7  lea     r9, [rbp+Type]; lpType
0x1800192cb  xor     r8d, r8d; lpReserved
0x1800192ce  lea     rdx, aVsstandardcoll_1; "VsStandardCollector.EtwBufferSize"
0x1800192d5  mov     rcx, [rbp+hKey]; hKey
0x1800192d9  call    cs:__imp_RegQueryValueExW
0x1800192df  test    eax, eax
0x1800192e1  jnz     short loc_180019318
0x1800192e3  cmp     [rbp+Type], 4
0x1800192e7  jnz     short loc_180019318
0x1800192e9  mov     r9d, dword ptr [rbp+Data]
0x1800192ed  test    r9d, r9d
0x1800192f0  jz      short loc_180019318
0x1800192f2  mov     byte ptr [rbx+20h], 1
0x1800192f6  mov     [rbx+8], r9d
0x1800192fa  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180019301  add     rcx, 38h ; '8'; this
0x180019305  lea     r8, aSettingEtwBuff; "Setting ETW buffer size to %dKB from re"...
0x18001930c  lea     rdx, aDAWork1SSource_15; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180019313  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180019318  mov     [rbp+Type], 4
0x18001931f  lea     rax, [rbp+Type]
0x180019323  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180019328  lea     rax, [rbp+var_14]
0x18001932c  mov     [rsp+70h+lpData], rax; lpData
0x180019331  lea     r9, [rbp+cbData]; lpType
0x180019335  xor     r8d, r8d; lpReserved
0x180019338  lea     rdx, aVsstandardcoll_0; "VsStandardCollector.EtwMinBuffers"
0x18001933f  mov     rcx, [rbp+hKey]; hKey
0x180019343  call    cs:__imp_RegQueryValueExW
0x180019349  test    eax, eax
0x18001934b  jnz     short loc_18001938C
0x18001934d  cmp     [rbp+cbData], 4
0x180019351  jnz     short loc_18001938C
0x180019353  mov     r9d, dword ptr [rbp+var_14]
0x180019357  test    r9d, r9d
0x18001935a  jz      short loc_18001938C
0x18001935c  mov     byte ptr [rbx+21h], 1
0x180019360  mov     [rbx+0Ch], r9d
0x180019364  cmp     [rbx+10h], r9d
0x180019368  jnb     short loc_18001936E
0x18001936a  mov     [rbx+10h], r9d
0x18001936e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180019375  add     rcx, 38h ; '8'; this
0x180019379  lea     r8, aSettingEtwMini; "Setting ETW minimum buffers to %d from "...
0x180019380  lea     rdx, aDAWork1SSource_15; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180019387  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001938c  mov     [rbp+Type], 4
0x180019393  lea     rax, [rbp+Type]
0x180019397  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001939c  lea     rax, [rbp+var_10]
0x1800193a0  mov     [rsp+70h+lpData], rax; lpData
0x1800193a5  lea     r9, [rbp+cbData]; lpType
0x1800193a9  xor     r8d, r8d; lpReserved
0x1800193ac  lea     rdx, aVsstandardcoll; "VsStandardCollector.EtwMaxBuffers"
0x1800193b3  mov     rcx, [rbp+hKey]; hKey
0x1800193b7  call    cs:__imp_RegQueryValueExW
0x1800193bd  test    eax, eax
0x1800193bf  jnz     short loc_1800193F8
0x1800193c1  cmp     [rbp+cbData], 4
0x1800193c5  jnz     short loc_1800193F8
0x1800193c7  mov     r9d, dword ptr [rbp+var_10]
0x1800193cb  cmp     r9d, [rbx+0Ch]
0x1800193cf  jb      short loc_1800193F8
0x1800193d1  mov     byte ptr [rbx+22h], 1
0x1800193d5  mov     [rbx+10h], r9d
0x1800193d9  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800193e0  add     rcx, 38h ; '8'; this
0x1800193e4  lea     r8, aSettingEtwMaxi; "Setting ETW maximum buffers to %d from "...
0x1800193eb  lea     rdx, aDAWork1SSource_15; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800193f2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800193f7  nop
0x1800193f8  cmp     [rbp+hKey], 0
0x1800193fd  jz      short loc_18001940A
0x1800193ff  mov     rcx, [rbp+hKey]; hKey
0x180019403  call    cs:__imp_RegCloseKey
0x180019409  nop
0x18001940a  mov     rax, rbx
0x18001940d  mov     rcx, [rbp+var_8]
0x180019411  xor     rcx, rsp; StackCookie
0x180019414  call    __security_check_cookie
0x180019419  mov     rbx, [rsp+70h+arg_8]
0x180019421  add     rsp, 70h
0x180019425  pop     rbp
0x180019426  retn
```
