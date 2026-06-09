# TraceOutputSettings::ReadConfiguration_Locked(void)

- ea: `0x180007b60`
- end: `0x1800081f5`
- name: `?ReadConfiguration_Locked@TraceOutputSettings@@CAXXZ`
- size: `1685`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012284`

## callees

- `0x180003cf0`
- `0x180006054`
- `0x180007b60`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e37`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180007c1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007da8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007f77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008042`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008101`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007da8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007f77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008042`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008101`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007bb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007bb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008198`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007cfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008198`

## string_xrefs

- `0x180007bbf`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007c7c`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007cc6`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007d01`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007e58`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007ea9`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007ed9`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007f43`: `TraceOutputSettings::ReadConfiguration_Locked`
- `0x180007bc6`: `com\complus\dtc\shared\trace\src\traceoutputsettings.cpp`
- `0x180007cba`: `Unable to read level for source %S`
- `0x180007d13`: `Unable to open sources key`
- `0x180007d95`: `TraceFilePath`
- `0x180007e7a`: `Using new trace file path: %s`
- `0x180007eb6`: `Unable to duplicate trace path`
- `0x180007ee2`: `Ignoring empty-string trace directory`
- `0x180007f1a`: `Unable to read trace path`
- `0x180007fec`: `Unable to read memory buffer size`
- `0x1800080ab`: `Unable to read debug out enabled`
- `0x18000816a`: `Unable to read Including Image Name in Trace File Name`
- `0x1800081a9`: `Unable to open output key`

## pseudocode

```c
void TraceOutputSettings::ReadConfiguration_Locked(void)
{
  LSTATUS v0; // eax
  __int64 v1; // rdi
  __int64 v2; // rbx
  const CHAR *v3; // rdx
  LSTATUS Value; // ecx
  bool v5; // zf
  DWORD v6; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  LSTATUS v13; // eax
  unsigned int v14; // eax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDataa; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDatab; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDatac; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbDatad; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  DWORD Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _WORD v27[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Sources", 0, 0x101u, &hKey);
  if ( v0 )
  {
    if ( TraceOutputSettings::fInitialized )
    {
      LODWORD(lpcbData) = v0;
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        288,
        L"TraceOutputSettings::ReadConfiguration_Locked",
        lpcbData,
        L"Unable to open sources key");
    }
  }
  else
  {
    v1 = 0;
    v2 = 0;
    do
    {
      v3 = *(const CHAR **)((char *)&TraceSources + v2 + 8);
      Data[2] = 0;
      *(_QWORD *)Data = 0x400000000LL;
      Value = RegQueryValueExA(hKey, v3, 0, &Data[2], (LPBYTE)Data, &Data[1]);
      if ( Value || *(_QWORD *)&Data[1] != 0x400000004LL )
      {
        if ( TraceOutputSettings::fInitialized )
        {
          LODWORD(lpcbData) = Value;
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            277,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            lpcbData,
            L"Unable to read level for source %S",
            *(struct TraceSourceEntry near **)((char *)&TraceSources + v2 + 8));
        }
      }
      else
      {
        v5 = !TraceOutputSettings::fInitialized;
        v6 = Data[0];
        *(_DWORD *)((char *)&TraceSources + v2 + 16) = Data[0];
        if ( !v5 )
        {
          LODWORD(v23) = v6;
          TraceStringInline(
            2,
            3,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            267,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            0,
            L"Now tracing %S at level %d",
            *(struct TraceSourceEntry near **)((char *)&TraceSources + v2 + 8),
            v23);
        }
      }
      ++v1;
      v2 += 24;
    }
    while ( v1 != 22 );
    RegCloseKey(hKey);
  }
  phkResult = 0;
  v7 = RegOpenKeyExW(TraceOutputSettings::hkConfiguration, L"Output", 0, 0x101u, &phkResult);
  if ( !v7 )
  {
    Data[2] = 0;
    *(_QWORD *)Data = 522;
    v8 = RegQueryValueExW(phkResult, L"TraceFilePath", 0, &Data[1], (LPBYTE)v27, Data);
    if ( v8 || Data[1] != 1 )
    {
      if ( TraceOutputSettings::fInitialized )
      {
        LODWORD(lpcbDataa) = v8;
        TraceStringInline(
          2,
          1,
          L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
          370,
          L"TraceOutputSettings::ReadConfiguration_Locked",
          lpcbDataa,
          L"Unable to read trace path");
      }
      goto LABEL_31;
    }
    v27[260] = 0;
    v9 = -1;
    do
      ++v9;
    while ( v27[v9] );
    v10 = v9 + 1;
    if ( v9 + 1 > 1 )
    {
      if ( v27[v10 - 1] != 92 )
        goto LABEL_22;
      if ( v9 > 1 )
      {
        v10 = v9;
LABEL_22:
        v11 = (unsigned __int16 *)LocalAlloc(0, 2 * v10);
        v12 = v11;
        if ( v11 )
        {
          StringCchCopyW(v11, v10, v27);
          EnterCriticalSection(&stru_1800D62A0);
          LocalFree(TraceOutputSettings::TraceFilePath);
          TraceOutputSettings::TraceFilePath = v12;
          LeaveCriticalSection(&stru_1800D62A0);
          if ( TraceOutputSettings::fInitialized )
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              343,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Using new trace file path: %s",
              TraceOutputSettings::TraceFilePath);
        }
        else if ( TraceOutputSettings::fInitialized )
        {
          LODWORD(lpcbDataa) = -2147024882;
          TraceStringInline(
            2,
            1,
            L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
            352,
            L"TraceOutputSettings::ReadConfiguration_Locked",
            lpcbDataa,
            L"Unable to duplicate trace path");
        }
LABEL_31:
        Data[0] = 4;
        v13 = RegQueryValueExW(phkResult, L"MemoryBufferSize", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v13 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(lpcbDatab) = v13;
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              408,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              lpcbDatab,
              L"Unable to read memory buffer size");
          }
        }
        else
        {
          v14 = Data[2];
          if ( Data[2] > 0xFFFFFFF )
          {
            v14 = 0xFFFFFFF;
            Data[2] = 0xFFFFFFF;
          }
          TraceOutputSettings::MemoryBufferSize = v14;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v22) = v14;
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              399,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Memory buffer size is now %d",
              v22);
          }
        }
        Data[0] = 4;
        v15 = RegQueryValueExW(phkResult, L"DebugOutEnabled", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v15 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(lpcbDatac) = v15;
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              439,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              lpcbDatac,
              L"Unable to read debug out enabled");
          }
        }
        else
        {
          TraceOutputSettings::DebugOutEnabled = Data[2] != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v22) = Data[2];
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              430,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Debug out enabled is now %d",
              v22);
          }
        }
        Data[0] = 4;
        v16 = RegQueryValueExW(phkResult, L"ImageNameInTraceFileNameEnabled", 0, &Data[1], (LPBYTE)&Data[2], Data);
        if ( v16 || *(_QWORD *)Data != 0x400000004LL )
        {
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(lpcbDatad) = v16;
            TraceStringInline(
              2,
              1,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              470,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              lpcbDatad,
              L"Unable to read Including Image Name in Trace File Name");
          }
        }
        else
        {
          TraceOutputSettings::ImageNameInTraceFileNameEnabled = Data[2] != 0;
          if ( TraceOutputSettings::fInitialized )
          {
            LODWORD(v22) = Data[2];
            TraceStringInline(
              2,
              3,
              L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
              461,
              L"TraceOutputSettings::ReadConfiguration_Locked",
              0,
              L"Including Image Name in Trace File Name is now %d",
              v22);
          }
        }
        RegCloseKey(phkResult);
        return;
      }
    }
    if ( TraceOutputSettings::fInitialized )
    {
      LODWORD(lpcbDataa) = -2147024809;
      TraceStringInline(
        2,
        1,
        L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
        362,
        L"TraceOutputSettings::ReadConfiguration_Locked",
        lpcbDataa,
        L"Ignoring empty-string trace directory");
    }
    goto LABEL_31;
  }
  if ( TraceOutputSettings::fInitialized )
  {
    LODWORD(lpcbData) = v7;
    TraceStringInline(
      2,
      1,
      L"com\\complus\\dtc\\shared\\trace\\src\\traceoutputsettings.cpp",
      480,
      L"TraceOutputSettings::ReadConfiguration_Locked",
      lpcbData,
      L"Unable to open output key");
  }
}

```

## disassembly

```asm
0x180007b60  push    rbp
0x180007b62  push    rbx
0x180007b63  push    rsi
0x180007b64  push    rdi
0x180007b65  push    r12
0x180007b67  push    r13
0x180007b69  push    r14
0x180007b6b  push    r15
0x180007b6d  lea     rbp, [rsp-198h]
0x180007b75  sub     rsp, 298h
0x180007b7c  mov     rax, cs:__security_cookie
0x180007b83  xor     rax, rsp
0x180007b86  mov     [rbp+1D0h+var_50], rax
0x180007b8d  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180007b94  lea     rax, [rsp+2D0h+hKey]
0x180007b99  xor     esi, esi
0x180007b9b  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180007ba0  mov     r9d, 101h; samDesired
0x180007ba6  mov     [rsp+2D0h+hKey], rsi
0x180007bab  xor     r8d, r8d; ulOptions
0x180007bae  lea     rdx, aSources; "Sources"
0x180007bb5  call    cs:__imp_RegOpenKeyExW
0x180007bbb  lea     r15d, [rsi+4]
0x180007bbf  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007bc6  lea     r12, aComComplusDtcS_6; "com\\complus\\dtc\\shared\\trace\\src\\"...
0x180007bcd  lea     r13d, [rsi+2]
0x180007bd1  lea     r14d, [rsi+1]
0x180007bd5  test    eax, eax
0x180007bd7  jnz     loc_180007D0A
0x180007bdd  mov     edi, esi
0x180007bdf  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180007be6  mov     ebx, esi
0x180007be8  mov     rdx, [rbx+rcx+8]; lpValueName
0x180007bed  lea     rax, [rsp+2D0h+Data+4]
0x180007bf2  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180007bf7  lea     r9, [rsp+2D0h+Data+8]; lpType
0x180007bfc  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180007c01  xor     r8d, r8d; lpReserved
0x180007c04  lea     rax, [rsp+2D0h+Data]
0x180007c09  mov     [rsp+2D0h+Data+8], esi
0x180007c0d  mov     [rsp+2D0h+phkResult], rax; lpData
0x180007c12  mov     [rsp+2D0h+Data], esi
0x180007c16  mov     [rsp+2D0h+Data+4], r15d
0x180007c1b  call    cs:__imp_RegQueryValueExA
0x180007c21  mov     ecx, eax
0x180007c23  test    eax, eax
0x180007c25  jnz     short loc_180007C94
0x180007c27  cmp     [rsp+2D0h+Data+8], r15d
0x180007c2c  jnz     short loc_180007C94
0x180007c2e  cmp     [rsp+2D0h+Data+4], r15d
0x180007c33  jnz     short loc_180007C94
0x180007c35  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007c3c  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180007c43  mov     eax, [rsp+2D0h+Data]
0x180007c47  mov     [rbx+rcx+10h], eax
0x180007c4b  jz      loc_180007CE5
0x180007c51  mov     [rsp+2D0h+var_290], eax
0x180007c55  mov     r9d, 10Bh
0x180007c5b  mov     rax, [rbx+rcx+8]
0x180007c60  mov     r8, r12
0x180007c63  mov     [rsp+2D0h+var_298], rax
0x180007c68  mov     edx, 3
0x180007c6d  lea     rax, aNowTracingSAtL; "Now tracing %S at level %d"
0x180007c74  mov     ecx, r13d
0x180007c77  mov     [rsp+2D0h+var_2A0], rax
0x180007c7c  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007c83  mov     [rsp+2D0h+lpcbData], rsi
0x180007c88  mov     [rsp+2D0h+phkResult], rax
0x180007c8d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007c92  jmp     short loc_180007CDE
0x180007c94  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007c9b  jz      short loc_180007CDE
0x180007c9d  lea     rax, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180007ca4  mov     r9d, 115h
0x180007caa  mov     rax, [rbx+rax+8]
0x180007caf  mov     r8, r12
0x180007cb2  mov     [rsp+2D0h+var_298], rax
0x180007cb7  mov     edx, r14d
0x180007cba  lea     rax, aUnableToReadLe; "Unable to read level for source %S"
0x180007cc1  mov     [rsp+2D0h+var_2A0], rax
0x180007cc6  lea     rax, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007ccd  mov     dword ptr [rsp+2D0h+lpcbData], ecx
0x180007cd1  mov     ecx, r13d
0x180007cd4  mov     [rsp+2D0h+phkResult], rax
0x180007cd9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007cde  lea     rcx, ?TraceSources@@3PAUTraceSourceEntry@@A; TraceSourceEntry near * TraceSources
0x180007ce5  add     rdi, r14
0x180007ce8  add     rbx, 18h
0x180007cec  cmp     rdi, 16h
0x180007cf0  jnz     loc_180007BE8
0x180007cf6  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180007cfb  call    cs:__imp_RegCloseKey
0x180007d01  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007d08  jmp     short loc_180007D3C
0x180007d0a  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007d11  jz      short loc_180007D3C
0x180007d13  lea     rcx, aUnableToOpenSo; "Unable to open sources key"
0x180007d1a  mov     r9d, 120h
0x180007d20  mov     [rsp+2D0h+var_2A0], rcx
0x180007d25  mov     r8, r12
0x180007d28  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180007d2c  mov     ecx, r13d
0x180007d2f  mov     edx, r14d
0x180007d32  mov     [rsp+2D0h+phkResult], rbx
0x180007d37  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007d3c  mov     rcx, cs:?hkConfiguration@TraceOutputSettings@@0PEAUHKEY__@@EA; hKey
0x180007d43  lea     rax, [rsp+2D0h+var_270]
0x180007d48  mov     r9d, 101h; samDesired
0x180007d4e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180007d53  xor     r8d, r8d; ulOptions
0x180007d56  mov     [rsp+2D0h+var_270], rsi
0x180007d5b  lea     rdx, aOutput; "Output"
0x180007d62  call    cs:__imp_RegOpenKeyExW
0x180007d68  test    eax, eax
0x180007d6a  jnz     loc_1800081A0
0x180007d70  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180007d75  lea     rax, [rsp+2D0h+Data]
0x180007d7a  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180007d7f  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180007d84  lea     rax, [rsp+2D0h+var_260]
0x180007d89  mov     [rsp+2D0h+Data+8], esi
0x180007d8d  xor     r8d, r8d; lpReserved
0x180007d90  mov     [rsp+2D0h+phkResult], rax; lpData
0x180007d95  lea     rdx, ValueName; "TraceFilePath"
0x180007d9c  mov     [rsp+2D0h+Data], 20Ah
0x180007da4  mov     [rsp+2D0h+Data+4], esi
0x180007da8  call    cs:__imp_RegQueryValueExW
0x180007dae  test    eax, eax
0x180007db0  jnz     loc_180007F11
0x180007db6  cmp     [rsp+2D0h+Data+4], r14d
0x180007dbb  jnz     loc_180007F11
0x180007dc1  mov     [rbp+1D0h+var_58], si
0x180007dc8  lea     rcx, [rsp+2D0h+var_260]
0x180007dcd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007dd1  inc     rax
0x180007dd4  cmp     [rcx+rax*2], si
0x180007dd8  jnz     short loc_180007DD1
0x180007dda  lea     rbx, [rax+1]
0x180007dde  cmp     rbx, r14
0x180007de1  jbe     loc_180007ED2
0x180007de7  cmp     word ptr [rsp+rbx*2+2D0h+hKey+6], 5Ch ; '\'
0x180007ded  jnz     short loc_180007DFB
0x180007def  cmp     rax, r14
0x180007df2  jbe     loc_180007ED2
0x180007df8  mov     rbx, rax
0x180007dfb  lea     rdx, [rbx+rbx]; uBytes
0x180007dff  xor     ecx, ecx; uFlags
0x180007e01  call    cs:__imp_LocalAlloc
0x180007e07  mov     rdi, rax
0x180007e0a  test    rax, rax
0x180007e0d  jz      loc_180007EA2
0x180007e13  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x180007e18  mov     rdx, rbx; unsigned __int64
0x180007e1b  mov     rcx, rax; unsigned __int16 *
0x180007e1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007e23  lea     rcx, stru_1800D62A0; lpCriticalSection
0x180007e2a  call    cs:__imp_EnterCriticalSection
0x180007e30  mov     rcx, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; hMem
0x180007e37  call    cs:__imp_LocalFree
0x180007e3d  lea     rcx, stru_1800D62A0; lpCriticalSection
0x180007e44  mov     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rdi; ushort * TraceOutputSettings::TraceFilePath
0x180007e4b  call    cs:__imp_LeaveCriticalSection
0x180007e51  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007e58  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007e5f  jz      loc_180007F4A
0x180007e65  mov     rax, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180007e6c  mov     r9d, 157h
0x180007e72  mov     [rsp+2D0h+var_298], rax
0x180007e77  mov     r8, r12
0x180007e7a  lea     rax, aUsingNewTraceF; "Using new trace file path: %s"
0x180007e81  mov     edx, 3
0x180007e86  mov     [rsp+2D0h+var_2A0], rax
0x180007e8b  mov     ecx, r13d
0x180007e8e  mov     [rsp+2D0h+lpcbData], rsi
0x180007e93  mov     [rsp+2D0h+phkResult], rbx
0x180007e98  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007e9d  jmp     loc_180007F4A
0x180007ea2  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007ea9  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007eb0  jz      loc_180007F4A
0x180007eb6  lea     rax, aUnableToDuplic; "Unable to duplicate trace path"
0x180007ebd  mov     r9d, 160h
0x180007ec3  mov     [rsp+2D0h+var_2A0], rax
0x180007ec8  mov     dword ptr [rsp+2D0h+lpcbData], 8007000Eh
0x180007ed0  jmp     short loc_180007EFC
0x180007ed2  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007ed9  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007ee0  jz      short loc_180007F4A
0x180007ee2  lea     rax, aIgnoringEmptyS; "Ignoring empty-string trace directory"
0x180007ee9  mov     r9d, 16Ah
0x180007eef  mov     [rsp+2D0h+var_2A0], rax
0x180007ef4  mov     dword ptr [rsp+2D0h+lpcbData], 80070057h
0x180007efc  mov     r8, r12
0x180007eff  mov     [rsp+2D0h+phkResult], rbx
0x180007f04  mov     edx, r14d
0x180007f07  mov     ecx, r13d
0x180007f0a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007f0f  jmp     short loc_180007F4A
0x180007f11  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007f18  jz      short loc_180007F43
0x180007f1a  lea     rcx, aUnableToReadTr; "Unable to read trace path"
0x180007f21  mov     r9d, 172h
0x180007f27  mov     [rsp+2D0h+var_2A0], rcx
0x180007f2c  mov     r8, r12
0x180007f2f  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180007f33  mov     ecx, r13d
0x180007f36  mov     edx, r14d
0x180007f39  mov     [rsp+2D0h+phkResult], rbx
0x180007f3e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007f43  lea     rbx, aTraceoutputset_1; "TraceOutputSettings::ReadConfiguration_"...
0x180007f4a  mov     rcx, [rsp+2D0h+var_270]; hKey
0x180007f4f  lea     rax, [rsp+2D0h+Data]
0x180007f54  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180007f59  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180007f5e  lea     rax, [rsp+2D0h+Data+8]
0x180007f63  mov     [rsp+2D0h+Data], r15d
0x180007f68  xor     r8d, r8d; lpReserved
0x180007f6b  mov     [rsp+2D0h+phkResult], rax; lpData
0x180007f70  lea     rdx, aMemorybuffersi; "MemoryBufferSize"
0x180007f77  call    cs:__imp_RegQueryValueExW
0x180007f7d  test    eax, eax
0x180007f7f  jnz     short loc_180007FE3
0x180007f81  cmp     [rsp+2D0h+Data+4], r15d
0x180007f86  jnz     short loc_180007FE3
0x180007f88  cmp     [rsp+2D0h+Data], r15d
0x180007f8d  jnz     short loc_180007FE3
0x180007f8f  mov     eax, [rsp+2D0h+Data+8]
0x180007f93  mov     ecx, 0FFFFFFFh
0x180007f98  cmp     eax, ecx
0x180007f9a  jbe     short loc_180007FA2
0x180007f9c  mov     eax, ecx
0x180007f9e  mov     [rsp+2D0h+Data+8], ecx
0x180007fa2  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007fa9  mov     cs:?MemoryBufferSize@TraceOutputSettings@@2KA, eax; ulong TraceOutputSettings::MemoryBufferSize
0x180007faf  jz      short loc_180008015
0x180007fb1  mov     dword ptr [rsp+2D0h+var_298], eax
0x180007fb5  mov     r9d, 18Fh
0x180007fbb  lea     rax, aMemoryBufferSi; "Memory buffer size is now %d"
0x180007fc2  mov     r8, r12
0x180007fc5  mov     [rsp+2D0h+var_2A0], rax
0x180007fca  mov     edx, 3
0x180007fcf  mov     [rsp+2D0h+lpcbData], rsi
0x180007fd4  mov     ecx, r13d
0x180007fd7  mov     [rsp+2D0h+phkResult], rbx
0x180007fdc  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180007fe1  jmp     short loc_180008015
0x180007fe3  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x180007fea  jz      short loc_180008015
0x180007fec  lea     rcx, aUnableToReadMe; "Unable to read memory buffer size"
0x180007ff3  mov     r9d, 198h
0x180007ff9  mov     [rsp+2D0h+var_2A0], rcx
0x180007ffe  mov     r8, r12
0x180008001  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x180008005  mov     ecx, r13d
0x180008008  mov     edx, r14d
0x18000800b  mov     [rsp+2D0h+phkResult], rbx
0x180008010  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180008015  mov     rcx, [rsp+2D0h+var_270]; hKey
0x18000801a  lea     rax, [rsp+2D0h+Data]
0x18000801f  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x180008024  lea     r9, [rsp+2D0h+Data+4]; lpType
0x180008029  lea     rax, [rsp+2D0h+Data+8]
0x18000802e  mov     [rsp+2D0h+Data], r15d
0x180008033  xor     r8d, r8d; lpReserved
0x180008036  mov     [rsp+2D0h+phkResult], rax; lpData
0x18000803b  lea     rdx, aDebugoutenable; "DebugOutEnabled"
0x180008042  call    cs:__imp_RegQueryValueExW
0x180008048  test    eax, eax
0x18000804a  jnz     short loc_1800080A2
0x18000804c  cmp     [rsp+2D0h+Data+4], r15d
0x180008051  jnz     short loc_1800080A2
0x180008053  cmp     [rsp+2D0h+Data], r15d
0x180008058  jnz     short loc_1800080A2
0x18000805a  mov     eax, [rsp+2D0h+Data+8]
0x18000805e  test    eax, eax
0x180008060  setnz   cs:?DebugOutEnabled@TraceOutputSettings@@2_NA; bool TraceOutputSettings::DebugOutEnabled
0x180008067  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x18000806e  jz      short loc_1800080D4
0x180008070  mov     dword ptr [rsp+2D0h+var_298], eax
0x180008074  mov     r9d, 1AEh
0x18000807a  lea     rax, aDebugOutEnable; "Debug out enabled is now %d"
0x180008081  mov     r8, r12
0x180008084  mov     [rsp+2D0h+var_2A0], rax
0x180008089  mov     edx, 3
0x18000808e  mov     [rsp+2D0h+lpcbData], rsi
0x180008093  mov     ecx, r13d
0x180008096  mov     [rsp+2D0h+phkResult], rbx
0x18000809b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800080a0  jmp     short loc_1800080D4
0x1800080a2  cmp     cs:?fInitialized@TraceOutputSettings@@0_NA, sil; bool TraceOutputSettings::fInitialized
0x1800080a9  jz      short loc_1800080D4
0x1800080ab  lea     rcx, aUnableToReadDe; "Unable to read debug out enabled"
0x1800080b2  mov     r9d, 1B7h
0x1800080b8  mov     [rsp+2D0h+var_2A0], rcx
0x1800080bd  mov     r8, r12
0x1800080c0  mov     dword ptr [rsp+2D0h+lpcbData], eax
0x1800080c4  mov     ecx, r13d
0x1800080c7  mov     edx, r14d
0x1800080ca  mov     [rsp+2D0h+phkResult], rbx
0x1800080cf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
  ... truncated ...
```
