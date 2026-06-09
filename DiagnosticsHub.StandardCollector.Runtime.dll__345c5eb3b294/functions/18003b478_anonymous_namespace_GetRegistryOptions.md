# _anonymous_namespace_::GetRegistryOptions

- ea: `0x18003b478`
- end: `0x18003b619`
- name: `_anonymous_namespace_::GetRegistryOptions`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b61c`

## callees

- `0x18001662c`
- `0x18003b478`
- `0x18003d864`
- `0x180049b50`

## import_xrefs

- `KERNEL32!GetNativeSystemInfo` at `0x18003b4a5`
- `KERNEL32!GetNativeSystemInfo` at `0x18003b4a5`
- `ADVAPI32!RegCloseKey` at `0x18003b5f3`
- `ADVAPI32!RegCloseKey` at `0x18003b5f3`
- `ADVAPI32!RegQueryValueExW` at `0x18003b515`
- `ADVAPI32!RegQueryValueExW` at `0x18003b5af`
- `ADVAPI32!RegQueryValueExW` at `0x18003b515`
- `ADVAPI32!RegQueryValueExW` at `0x18003b5af`

## string_xrefs

- `0x18003b50a`: `NgenPdbCreationThreadLimit`
- `0x18003b545`: `The value in the regkey NgenPdbCreationThreadLimit %d was greater than the number of cores available, limiting thread count to %d.`
- `0x18003b56c`: `Used the value in the regkey NgenPdbCreationThreadLimit to set the thread limit to %d instead of the default value %d.`
- `0x18003b5d4`: `Ngen PDB caching was disabled by the regkey ForceDisableNGENPdbCaching, disabling pdb caching regardless of whether a symbol cache dir was specified.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall anonymous_namespace_::GetRegistryOptions(DWORD *a1, _BYTE *a2)
{
  HKEY v4; // rdx
  DWORD dwNumberOfProcessors; // edi
  DWORD v6; // eax
  DWORD v7; // edx
  DiagHubCommon::LogStream *v8; // rcx
  LPBYTE lpData; // [rsp+20h] [rbp-29h]
  HKEY hKey[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+40h] [rbp-9h]
  DWORD cbData; // [rsp+48h] [rbp-1h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp+3h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp+7h] BYREF
  BYTE v15[4]; // [rsp+54h] [rbp+Bh] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp+Fh] BYREF

  GetNativeSystemInfo(&SystemInfo);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  v6 = 12;
  if ( (int)SystemInfo.dwNumberOfProcessors < 12 )
    v6 = SystemInfo.dwNumberOfProcessors;
  *a1 = v6;
  *a2 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v11 = 0;
  if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v4, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub") )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"NgenPdbCreationThreadLimit", 0, &Type, Data, &cbData) && Type == 4 )
    {
      v7 = *(_DWORD *)Data;
      v8 = _logger;
      if ( *(_DWORD *)Data <= dwNumberOfProcessors )
      {
        if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
        {
          LODWORD(lpData) = *a1;
          DiagHubCommon::LogStream::Write(
            _logger,
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
            L"Used the value in the regkey NgenPdbCreationThreadLimit to set the thread limit to %d instead of the default value %d.",
            *(unsigned int *)Data,
            lpData);
          v7 = *(_DWORD *)Data;
        }
        *a1 = v7;
      }
      else
      {
        *a1 = dwNumberOfProcessors;
        if ( *(_QWORD *)v8 != *((_QWORD *)v8 + 1) )
        {
          LODWORD(lpData) = dwNumberOfProcessors;
          DiagHubCommon::LogStream::Write(
            v8,
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
            L"The value in the regkey NgenPdbCreationThreadLimit %d was greater than the number of cores available, limiti"
             "ng thread count to %d.",
            v7,
            lpData);
        }
      }
    }
    Type = 4;
    if ( !RegQueryValueExW(hKey[0], L"ForceDisableNGENPdbCaching", 0, &cbData, v15, &Type)
      && cbData == 4
      && *(_DWORD *)v15 == 1 )
    {
      *a2 = 1;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Ngen PDB caching was disabled by the regkey ForceDisableNGENPdbCaching, disabling pdb caching regardless of whet"
         "her a symbol cache dir was specified.");
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
}

```

## disassembly

```asm
0x18003b478  mov     [rsp-8+arg_10], rsi
0x18003b47d  push    rbp
0x18003b47e  push    rdi
0x18003b47f  push    r14
0x18003b481  lea     rbp, [rsp-47h]
0x18003b486  sub     rsp, 90h
0x18003b48d  mov     rax, cs:__security_cookie
0x18003b494  xor     rax, rsp
0x18003b497  mov     [rbp+57h+var_18], rax
0x18003b49b  mov     r14, rdx
0x18003b49e  mov     rsi, rcx
0x18003b4a1  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18003b4a5  call    cs:__imp_GetNativeSystemInfo
0x18003b4ab  mov     edi, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x18003b4ae  mov     eax, 0Ch
0x18003b4b3  cmp     edi, eax
0x18003b4b5  cmovl   eax, edi
0x18003b4b8  mov     [rsi], eax
0x18003b4ba  mov     byte ptr [r14], 0
0x18003b4be  xorps   xmm0, xmm0
0x18003b4c1  xor     eax, eax
0x18003b4c3  movups  xmmword ptr [rbp+57h+hKey], xmm0
0x18003b4c7  mov     [rbp+57h+hKey], rax
0x18003b4cb  mov     dword ptr [rbp+57h+hKey+8], eax
0x18003b4ce  mov     [rbp+57h+var_60], rax
0x18003b4d2  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x18003b4d9  lea     rcx, [rbp+57h+hKey]; this
0x18003b4dd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003b4e2  test    eax, eax
0x18003b4e4  jnz     loc_18003B5E8
0x18003b4ea  mov     [rbp+57h+cbData], 4
0x18003b4f1  lea     rax, [rbp+57h+cbData]
0x18003b4f5  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18003b4fa  lea     rax, [rbp+57h+Data]
0x18003b4fe  mov     [rsp+0A0h+lpData], rax; lpData
0x18003b503  lea     r9, [rbp+57h+Type]; lpType
0x18003b507  xor     r8d, r8d; lpReserved
0x18003b50a  lea     rdx, aNgenpdbcreatio; "NgenPdbCreationThreadLimit"
0x18003b511  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b515  call    cs:__imp_RegQueryValueExW
0x18003b51b  test    eax, eax
0x18003b51d  jnz     short loc_18003B584
0x18003b51f  cmp     [rbp+57h+Type], 4
0x18003b523  jnz     short loc_18003B584
0x18003b525  mov     edx, dword ptr [rbp+57h+Data]
0x18003b528  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18003b52f  cmp     edx, edi
0x18003b531  jbe     short loc_18003B55A
0x18003b533  mov     [rsi], edi
0x18003b535  mov     rax, [rcx+8]
0x18003b539  cmp     [rcx], rax
0x18003b53c  jz      short loc_18003B584
0x18003b53e  mov     dword ptr [rsp+0A0h+lpData], edi
0x18003b542  mov     r9d, edx
0x18003b545  lea     r8, aTheValueInTheR; "The value in the regkey NgenPdbCreation"...
0x18003b54c  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b553  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b558  jmp     short loc_18003B584
0x18003b55a  mov     rax, [rcx+8]
0x18003b55e  cmp     [rcx], rax
0x18003b561  jz      short loc_18003B582
0x18003b563  mov     eax, [rsi]
0x18003b565  mov     dword ptr [rsp+0A0h+lpData], eax
0x18003b569  mov     r9d, edx
0x18003b56c  lea     r8, aUsedTheValueIn; "Used the value in the regkey NgenPdbCre"...
0x18003b573  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b57a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b57f  mov     edx, dword ptr [rbp+57h+Data]
0x18003b582  mov     [rsi], edx
0x18003b584  mov     [rbp+57h+Type], 4
0x18003b58b  lea     rax, [rbp+57h+Type]
0x18003b58f  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18003b594  lea     rax, [rbp+57h+var_4C]
0x18003b598  mov     [rsp+0A0h+lpData], rax; lpData
0x18003b59d  lea     r9, [rbp+57h+cbData]; lpType
0x18003b5a1  xor     r8d, r8d; lpReserved
0x18003b5a4  lea     rdx, aForcedisableng_0; "ForceDisableNGENPdbCaching"
0x18003b5ab  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b5af  call    cs:__imp_RegQueryValueExW
0x18003b5b5  test    eax, eax
0x18003b5b7  jnz     short loc_18003B5E8
0x18003b5b9  cmp     [rbp+57h+cbData], 4
0x18003b5bd  jnz     short loc_18003B5E8
0x18003b5bf  cmp     dword ptr [rbp+57h+var_4C], 1
0x18003b5c3  jnz     short loc_18003B5E8
0x18003b5c5  mov     byte ptr [r14], 1
0x18003b5c9  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003b5d0  add     rcx, 70h ; 'p'; this
0x18003b5d4  lea     r8, aNgenPdbCaching; "Ngen PDB caching was disabled by the re"...
0x18003b5db  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b5e2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b5e7  nop
0x18003b5e8  cmp     [rbp+57h+hKey], 0
0x18003b5ed  jz      short loc_18003B5F9
0x18003b5ef  mov     rcx, [rbp+57h+hKey]; hKey
0x18003b5f3  call    cs:__imp_RegCloseKey
0x18003b5f9  mov     rcx, [rbp+57h+var_18]
0x18003b5fd  xor     rcx, rsp; StackCookie
0x18003b600  call    __security_check_cookie
0x18003b605  mov     rsi, [rsp+0A0h+arg_10]
0x18003b60d  add     rsp, 90h
0x18003b614  pop     r14
0x18003b616  pop     rdi
0x18003b617  pop     rbp
0x18003b618  retn
```
