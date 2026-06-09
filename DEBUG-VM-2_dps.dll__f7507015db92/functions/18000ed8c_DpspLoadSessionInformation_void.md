# DpspLoadSessionInformation(void)

- ea: `0x18000ed8c`
- end: `0x18000f291`
- name: `?DpspLoadSessionInformation@@YAJXZ`
- size: `1285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f940`

## callees

- `0x1800013a0`
- `0x180006d08`
- `0x180008ea0`
- `0x180008f10`
- `0x180009044`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x18000bbd4`
- `0x18000de94`
- `0x18000e334`
- `0x18000e3d4`
- `0x18000e434`
- `0x18000ed8c`
- `0x1800178a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f256`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f256`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f269`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ef53`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ef53`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ee64`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ee64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f0af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f0f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f0af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f0f8`

## string_xrefs

- `0x18000efa2`: `ImagePath`
- `0x18000f092`: `NotifyInstanceCompletion`

## pseudocode

```c
__int64 DpspLoadSessionInformation(void)
{
  WCHAR *v0; // rsi
  _QWORD *v1; // rdi
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  DWORD v5; // r12d
  _QWORD *v6; // rax
  int v7; // eax
  int v8; // r8d
  int v9; // eax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // r15d
  unsigned __int16 *v13; // rax
  unsigned int SessionExecutionContext; // eax
  __int64 SystemSessionHost; // rax
  DWORD cbData; // [rsp+60h] [rbp-49h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-45h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-41h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp-39h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-35h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-31h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-29h] BYREF
  _DWORD v24[3]; // [rsp+84h] [rbp-25h] BYREF
  unsigned __int16 *v25; // [rsp+90h] [rbp-19h]
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp-11h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-9h] BYREF

  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  memset(v24, 0, sizeof(v24));
  v0 = 0;
  *(_DWORD *)Data = 0;
  v1 = 0;
  cbData = 0;
  v25 = 0;
  v27 = 0;
  ftLastWriteTime = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\WDI\\DiagnosticModules",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 || !hKey )
  {
    hKey = 0;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_48:
    if ( v1 )
      DpspFreeSpecificSessionInfo((struct __SESSIONINFO **)&v24[1]);
  }
  else
  {
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_50;
    }
    ++cbMaxSubKeyLen;
    if ( cbMaxSubKeyLen != (2 * cbMaxSubKeyLen) >> 1 )
    {
      v3 = -2147024362;
      goto LABEL_50;
    }
    v0 = (WCHAR *)WdipAlloc(2 * cbMaxSubKeyLen);
    if ( !v0 )
    {
      v3 = -2147024882;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
        (int)L"DpspLoadSessionInformation",
        1692,
        (int)L"Error = %d",
        14);
      goto LABEL_50;
    }
    v3 = 0;
    v5 = 0;
    if ( cSubKeys )
    {
      while ( 1 )
      {
        WdipFree(v25);
        v25 = 0;
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        if ( v1 )
        {
          DpspFreeSpecificSessionInfo((struct __SESSIONINFO **)&v24[1]);
          v1 = 0;
          *(_QWORD *)&v24[1] = 0;
        }
        cchName = cbMaxSubKeyLen;
        if ( RegEnumKeyExW(hKey, v5, v0, &cchName, 0, 0, 0, &ftLastWriteTime)
          || RegOpenKeyExW(hKey, v0, 0, 0x20019u, &phkResult)
          || !phkResult )
        {
          goto LABEL_44;
        }
        if ( (int)WdipRegReadValueAlloc(phkResult, L"ImagePath", (__int64)v24) >= 0 )
        {
          v3 = WdipStringToGuid(v0, &v27);
          if ( v3 >= 0 )
          {
            v6 = (_QWORD *)WdipAlloc(192);
            *(_QWORD *)&v24[1] = v6;
            v1 = v6;
            if ( !v6 )
              goto LABEL_44;
            memset_0(v6, 0, 0xC0u);
            v1[15] = v1 + 14;
            v1[14] = v1 + 14;
            v7 = WdipInitializeCriticalSection(v1 + 8);
            v3 = v7;
            if ( v7 >= 0 )
            {
              cbData = 4;
              if ( !RegQueryValueExW(phkResult, L"NeverUnload", 0, 0, Data, &cbData) )
              {
                v9 = 0;
                if ( *(_DWORD *)Data == 1 )
                  v9 = 2;
                *((_DWORD *)v1 + 38) |= v9;
              }
              cbData = 4;
              if ( !RegQueryValueExW(phkResult, L"NotifyInstanceCompletion", 0, 0, Data, &cbData) )
              {
                v10 = 0;
                if ( *(_DWORD *)Data == 1 )
                  v10 = 32;
                *((_DWORD *)v1 + 38) |= v10;
              }
              cbData = 4;
              if ( RegQueryValueExW(phkResult, L"IsReentrant", 0, 0, Data, &cbData) || *(_DWORD *)Data != 1 )
              {
                *((_DWORD *)v1 + 8) = 1;
                v11 = g_ulQueueSize;
              }
              else
              {
                *((_DWORD *)v1 + 8) = 7;
                v11 = 2 * g_ulQueueSize;
              }
              v12 = v24[0];
              *((_DWORD *)v1 + 10) = v11;
              *((_DWORD *)v1 + 7) = 0;
              *((_DWORD *)v1 + 9) = 0;
              v13 = (unsigned __int16 *)WdipAlloc(v12);
              v1[16] = v13;
              if ( !v13 )
                goto LABEL_44;
              v7 = StringCbCopyW(v13, v12, v25);
              v3 = v7;
              if ( v7 >= 0 )
              {
                *((_DWORD *)v1 + 37) = v12;
                *((_DWORD *)v1 + 14) = DpspGetSessionAudience(phkResult);
                DpspEnumerateSessionResourceInformation(phkResult, (struct __SESSIONINFO *)v1);
                SessionExecutionContext = DpspGetSessionExecutionContext(phkResult);
                SystemSessionHost = DpspGetSystemSessionHost(SessionExecutionContext);
                v1[22] = SystemSessionHost;
                if ( SystemSessionHost )
                {
                  *(_OWORD *)v1 = v27;
                  *(_QWORD *)&v24[1] = 0;
                  v1[2] = (_InterlockedExchangeAdd64(&g_ulConnectionId, 4u) + 4) | 1;
                  *((_DWORD *)v1 + 6) = 0;
                  v1[21] = 0;
                  *((_DWORD *)v1 + 39) = -1;
                  v1[23] = g_pSessionHead;
                  g_pSessionHead = (struct __SESSIONINFO *)v1;
                  v1 = 0;
                  goto LABEL_44;
                }
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
                  (int)L"DpspLoadSessionInformation",
                  1859,
                  (int)L"Error = %d",
                  5);
                goto LABEL_19;
              }
              v8 = 1839;
            }
            else
            {
              v8 = 1765;
            }
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsstate.cpp",
              (int)L"DpspLoadSessionInformation",
              v8,
              (int)L"Error = %d",
              v7);
          }
        }
LABEL_19:
        v3 = 0;
LABEL_44:
        if ( ++v5 >= cSubKeys )
          goto LABEL_48;
      }
    }
  }
LABEL_50:
  WdipFree(v25);
  WdipFree(v0);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ed8c  push    rbp
0x18000ed8e  push    rbx
0x18000ed8f  push    rsi
0x18000ed90  push    rdi
0x18000ed91  push    r12
0x18000ed93  push    r13
0x18000ed95  push    r14
0x18000ed97  push    r15
0x18000ed99  lea     rbp, [rsp-1Fh]
0x18000ed9e  sub     rsp, 0C8h
0x18000eda5  mov     rax, cs:__security_cookie
0x18000edac  xor     rax, rsp
0x18000edaf  mov     [rbp+57h+var_50], rax
0x18000edb3  xor     r13d, r13d
0x18000edb6  lea     rax, [rbp+57h+hKey]
0x18000edba  xorps   xmm0, xmm0
0x18000edbd  mov     [rbp+57h+hKey], r13
0x18000edc1  mov     r9d, 20019h; samDesired
0x18000edc7  mov     [rbp+57h+var_98], r13
0x18000edcb  xor     r8d, r8d; ulOptions
0x18000edce  mov     [rbp+57h+cSubKeys], r13d
0x18000edd2  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\WDI"...
0x18000edd9  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18000eddd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ede4  mov     [rbp+57h+cchName], r13d
0x18000ede8  mov     dword ptr [rbp+57h+var_7C], r13d
0x18000edec  mov     esi, r13d
0x18000edef  mov     dword ptr [rbp+57h+Data], r13d
0x18000edf3  mov     edi, r13d
0x18000edf6  mov     [rbp+57h+cbData], r13d
0x18000edfa  mov     [rbp+57h+var_70], r13
0x18000edfe  mov     qword ptr [rbp+57h+var_7C+4], r13
0x18000ee02  movups  [rbp+57h+var_60], xmm0
0x18000ee06  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r13
0x18000ee0a  mov     [rsp+100h+phkResult], rax; phkResult
0x18000ee0f  call    cs:__imp_RegOpenKeyExW
0x18000ee15  mov     ebx, eax
0x18000ee17  test    eax, eax
0x18000ee19  jnz     loc_18000F21D
0x18000ee1f  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ee23  test    rcx, rcx
0x18000ee26  jz      loc_18000F21D
0x18000ee2c  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18000ee31  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18000ee35  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18000ee3a  xor     r9d, r9d; lpReserved
0x18000ee3d  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18000ee42  xor     r8d, r8d; lpcchClass
0x18000ee45  mov     [rsp+100h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18000ee4a  xor     edx, edx; lpClass
0x18000ee4c  mov     [rsp+100h+lpcValues], r13; lpcValues
0x18000ee51  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000ee56  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000ee5b  lea     rax, [rbp+57h+cSubKeys]
0x18000ee5f  mov     [rsp+100h+phkResult], rax; lpcSubKeys
0x18000ee64  call    cs:__imp_RegQueryInfoKeyW
0x18000ee6a  mov     ebx, eax
0x18000ee6c  test    eax, eax
0x18000ee6e  jz      short loc_18000EE84
0x18000ee70  jle     loc_18000F23C
0x18000ee76  movzx   ebx, ax
0x18000ee79  or      ebx, 80070000h
0x18000ee7f  jmp     loc_18000F23C
0x18000ee84  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18000ee87  inc     ecx
0x18000ee89  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18000ee8c  lea     edx, [rcx+rcx]
0x18000ee8f  mov     eax, edx
0x18000ee91  shr     eax, 1
0x18000ee93  cmp     ecx, eax
0x18000ee95  jz      short loc_18000EEA1
0x18000ee97  mov     ebx, 80070216h
0x18000ee9c  jmp     loc_18000F23C
0x18000eea1  mov     ecx, edx
0x18000eea3  call    WdipAlloc
0x18000eea8  mov     rsi, rax
0x18000eeab  test    rax, rax
0x18000eeae  jnz     short loc_18000EEE2
0x18000eeb0  lea     r9, aErrorD; "Error = %d"
0x18000eeb7  mov     dword ptr [rsp+100h+phkResult], 0Eh; Args
0x18000eebf  mov     r8d, 69Ch; int
0x18000eec5  lea     rdx, aDpsploadsessio; "DpspLoadSessionInformation"
0x18000eecc  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000eed3  mov     ebx, 8007000Eh
0x18000eed8  call    WdipTraceError
0x18000eedd  jmp     loc_18000F23C
0x18000eee2  mov     ebx, r13d
0x18000eee5  mov     r12d, r13d
0x18000eee8  cmp     [rbp+57h+cSubKeys], r13d
0x18000eeec  jbe     loc_18000F23C
0x18000eef2  mov     rcx, [rbp+57h+var_70]
0x18000eef6  call    WdipFree
0x18000eefb  mov     rcx, [rbp+57h+var_98]; hKey
0x18000eeff  mov     [rbp+57h+var_70], r13
0x18000ef03  test    rcx, rcx
0x18000ef06  jz      short loc_18000EF12
0x18000ef08  call    cs:__imp_RegCloseKey
0x18000ef0e  mov     [rbp+57h+var_98], r13
0x18000ef12  test    rdi, rdi
0x18000ef15  jz      short loc_18000EF27
0x18000ef17  lea     rcx, [rbp+57h+var_7C+4]; struct __SESSIONINFO **
0x18000ef1b  call    ?DpspFreeSpecificSessionInfo@@YAXPEAPEAU__SESSIONINFO@@@Z; DpspFreeSpecificSessionInfo(__SESSIONINFO * *)
0x18000ef20  mov     rdi, r13
0x18000ef23  mov     qword ptr [rbp+57h+var_7C+4], r13
0x18000ef27  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18000ef2a  lea     r9, [rbp+57h+cchName]; lpcchName
0x18000ef2e  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ef32  mov     r8, rsi; lpName
0x18000ef35  mov     [rbp+57h+cchName], eax
0x18000ef38  mov     edx, r12d; dwIndex
0x18000ef3b  lea     rax, [rbp+57h+ftLastWriteTime]
0x18000ef3f  mov     [rsp+100h+lpcValues], rax; lpftLastWriteTime
0x18000ef44  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcchClass
0x18000ef49  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpClass
0x18000ef4e  mov     [rsp+100h+phkResult], r13; lpReserved
0x18000ef53  call    cs:__imp_RegEnumKeyExW
0x18000ef59  test    eax, eax
0x18000ef5b  jnz     loc_18000F20E
0x18000ef61  mov     rcx, [rbp+57h+hKey]; hKey
0x18000ef65  lea     rax, [rbp+57h+var_98]
0x18000ef69  mov     r9d, 20019h; samDesired
0x18000ef6f  mov     [rsp+100h+phkResult], rax; phkResult
0x18000ef74  xor     r8d, r8d; ulOptions
0x18000ef77  mov     rdx, rsi; lpSubKey
0x18000ef7a  call    cs:__imp_RegOpenKeyExW
0x18000ef80  test    eax, eax
0x18000ef82  jnz     loc_18000F20E
0x18000ef88  mov     rcx, [rbp+57h+var_98]; hKey
0x18000ef8c  test    rcx, rcx
0x18000ef8f  jz      loc_18000F20E
0x18000ef95  lea     rax, [rbp+57h+var_7C]
0x18000ef99  lea     r9, [rbp+57h+var_70]
0x18000ef9d  mov     [rsp+100h+phkResult], rax; __int64
0x18000efa2  lea     rdx, aImagepath; "ImagePath"
0x18000efa9  call    WdipRegReadValueAlloc
0x18000efae  test    eax, eax
0x18000efb0  jns     short loc_18000EFBA
0x18000efb2  mov     ebx, r13d
0x18000efb5  jmp     loc_18000F20E
0x18000efba  lea     rdx, [rbp+57h+var_60]
0x18000efbe  mov     rcx, rsi
0x18000efc1  call    WdipStringToGuid
0x18000efc6  mov     ebx, eax
0x18000efc8  test    eax, eax
0x18000efca  js      short loc_18000EFB2
0x18000efcc  mov     ecx, 0C0h
0x18000efd1  call    WdipAlloc
0x18000efd6  mov     qword ptr [rbp+57h+var_7C+4], rax
0x18000efda  mov     rdi, rax
0x18000efdd  test    rax, rax
0x18000efe0  jz      loc_18000F20E
0x18000efe6  xor     edx, edx; Val
0x18000efe8  mov     r8d, 0C0h; Size
0x18000efee  mov     rcx, rax; void *
0x18000eff1  call    memset_0
0x18000eff6  lea     rcx, [rdi+70h]
0x18000effa  mov     [rcx+8], rcx
0x18000effe  mov     [rcx], rcx
0x18000f001  lea     rcx, [rdi+40h]
0x18000f005  call    WdipInitializeCriticalSection
0x18000f00a  mov     ebx, eax
0x18000f00c  test    eax, eax
0x18000f00e  jns     short loc_18000F03C
0x18000f010  mov     r8d, 6E5h; int
0x18000f016  movzx   eax, ax
0x18000f019  mov     dword ptr [rsp+100h+phkResult], eax; Args
0x18000f01d  lea     r9, aErrorD; "Error = %d"
0x18000f024  lea     rdx, aDpsploadsessio; "DpspLoadSessionInformation"
0x18000f02b  lea     rcx, aClientcoreBase_8; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000f032  call    WdipTraceError
0x18000f037  jmp     loc_18000EFB2
0x18000f03c  mov     rcx, [rbp+57h+var_98]; hKey
0x18000f040  lea     rax, [rbp+57h+cbData]
0x18000f044  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000f049  lea     rdx, aNeverunload; "NeverUnload"
0x18000f050  lea     rax, [rbp+57h+Data]
0x18000f054  mov     [rbp+57h+cbData], 4
0x18000f05b  xor     r9d, r9d; lpType
0x18000f05e  mov     [rsp+100h+phkResult], rax; lpData
0x18000f063  xor     r8d, r8d; lpReserved
0x18000f066  call    cs:__imp_RegQueryValueExW
0x18000f06c  test    eax, eax
0x18000f06e  jnz     short loc_18000F085
0x18000f070  cmp     dword ptr [rbp+57h+Data], 1
0x18000f074  mov     eax, r13d
0x18000f077  mov     ecx, 2
0x18000f07c  cmovz   eax, ecx
0x18000f07f  or      [rdi+98h], eax
0x18000f085  mov     rcx, [rbp+57h+var_98]; hKey
0x18000f089  lea     rax, [rbp+57h+cbData]
0x18000f08d  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000f092  lea     rdx, aNotifyinstance; "NotifyInstanceCompletion"
0x18000f099  lea     rax, [rbp+57h+Data]
0x18000f09d  mov     [rbp+57h+cbData], 4
0x18000f0a4  xor     r9d, r9d; lpType
0x18000f0a7  mov     [rsp+100h+phkResult], rax; lpData
0x18000f0ac  xor     r8d, r8d; lpReserved
0x18000f0af  call    cs:__imp_RegQueryValueExW
0x18000f0b5  test    eax, eax
0x18000f0b7  jnz     short loc_18000F0CE
0x18000f0b9  cmp     dword ptr [rbp+57h+Data], 1
0x18000f0bd  mov     eax, r13d
0x18000f0c0  mov     ecx, 20h ; ' '
0x18000f0c5  cmovz   eax, ecx
0x18000f0c8  or      [rdi+98h], eax
0x18000f0ce  mov     rcx, [rbp+57h+var_98]; hKey
0x18000f0d2  lea     rax, [rbp+57h+cbData]
0x18000f0d6  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000f0db  lea     rdx, aIsreentrant; "IsReentrant"
0x18000f0e2  lea     rax, [rbp+57h+Data]
0x18000f0e6  mov     [rbp+57h+cbData], 4
0x18000f0ed  xor     r9d, r9d; lpType
0x18000f0f0  mov     [rsp+100h+phkResult], rax; lpData
0x18000f0f5  xor     r8d, r8d; lpReserved
0x18000f0f8  call    cs:__imp_RegQueryValueExW
0x18000f0fe  test    eax, eax
0x18000f100  jnz     short loc_18000F119
0x18000f102  cmp     dword ptr [rbp+57h+Data], 1
0x18000f106  jnz     short loc_18000F119
0x18000f108  mov     dword ptr [rdi+20h], 7
0x18000f10f  mov     eax, cs:?g_ulQueueSize@@3KA; ulong g_ulQueueSize
0x18000f115  add     eax, eax
0x18000f117  jmp     short loc_18000F126
0x18000f119  mov     dword ptr [rdi+20h], 1
0x18000f120  mov     eax, cs:?g_ulQueueSize@@3KA; ulong g_ulQueueSize
0x18000f126  mov     r15d, dword ptr [rbp+57h+var_7C]
0x18000f12a  mov     [rdi+28h], eax
0x18000f12d  mov     ecx, r15d
0x18000f130  mov     [rdi+1Ch], r13d
0x18000f134  mov     [rdi+24h], r13d
0x18000f138  call    WdipAlloc
0x18000f13d  mov     [rdi+80h], rax
0x18000f144  test    rax, rax
0x18000f147  jz      loc_18000F20E
0x18000f14d  mov     r8, [rbp+57h+var_70]; unsigned __int16 *
0x18000f151  mov     edx, r15d; unsigned __int64
0x18000f154  mov     rcx, rax; unsigned __int16 *
0x18000f157  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f15c  mov     ebx, eax
0x18000f15e  test    eax, eax
0x18000f160  jns     short loc_18000F16D
0x18000f162  mov     r8d, 72Fh
0x18000f168  jmp     loc_18000F016
0x18000f16d  mov     [rdi+94h], r15d
0x18000f174  mov     rcx, [rbp+57h+var_98]
0x18000f178  call    ?DpspGetSessionAudience@@YA?AW4WDI_QUEUED_RESOLUTION_AUDIENCE@@PEAUHKEY__@@@Z; DpspGetSessionAudience(HKEY__ *)
0x18000f17d  mov     [rdi+38h], eax
0x18000f180  mov     rdx, rdi; struct __SESSIONINFO *
0x18000f183  mov     rcx, [rbp+57h+var_98]; hKey
0x18000f187  call    ?DpspEnumerateSessionResourceInformation@@YAJPEAUHKEY__@@PEAU__SESSIONINFO@@@Z; DpspEnumerateSessionResourceInformation(HKEY__ *,__SESSIONINFO *)
0x18000f18c  mov     rcx, [rbp+57h+var_98]
0x18000f190  call    ?DpspGetSessionExecutionContext@@YA?AW4HOSTTYPE@@PEAUHKEY__@@@Z; DpspGetSessionExecutionContext(HKEY__ *)
0x18000f195  mov     ecx, eax
0x18000f197  call    DpspGetSystemSessionHost
0x18000f19c  mov     [rdi+0B0h], rax
0x18000f1a3  test    rax, rax
0x18000f1a6  jnz     short loc_18000F1BB
0x18000f1a8  mov     dword ptr [rsp+100h+phkResult], 4005h
0x18000f1b0  mov     r8d, 743h
0x18000f1b6  jmp     loc_18000F01D
0x18000f1bb  movups  xmm0, [rbp+57h+var_60]
0x18000f1bf  mov     eax, 4
0x18000f1c4  movdqu  xmmword ptr [rdi], xmm0
0x18000f1c8  lock xadd cs:g_ulConnectionId, rax
0x18000f1d1  add     rax, 4
0x18000f1d5  mov     qword ptr [rbp+57h+var_7C+4], r13
0x18000f1d9  or      rax, 1
0x18000f1dd  mov     [rdi+10h], rax
0x18000f1e1  mov     [rdi+18h], r13d
0x18000f1e5  mov     [rdi+0A8h], r13
0x18000f1ec  mov     dword ptr [rdi+9Ch], 0FFFFFFFFh
0x18000f1f6  mov     rax, cs:g_pSessionHead
0x18000f1fd  mov     [rdi+0B8h], rax
0x18000f204  mov     cs:g_pSessionHead, rdi
0x18000f20b  mov     rdi, r13
0x18000f20e  inc     r12d
0x18000f211  cmp     r12d, [rbp+57h+cSubKeys]
0x18000f215  jb      loc_18000EEF2
0x18000f21b  jmp     short loc_18000F22E
0x18000f21d  mov     [rbp+57h+hKey], r13
0x18000f221  test    eax, eax
0x18000f223  jle     short loc_18000F22E
0x18000f225  movzx   ebx, ax
0x18000f228  or      ebx, 80070000h
0x18000f22e  test    rdi, rdi
0x18000f231  jz      short loc_18000F23C
0x18000f233  lea     rcx, [rbp+57h+var_7C+4]; struct __SESSIONINFO **
0x18000f237  call    ?DpspFreeSpecificSessionInfo@@YAXPEAPEAU__SESSIONINFO@@@Z; DpspFreeSpecificSessionInfo(__SESSIONINFO * *)
0x18000f23c  mov     rcx, [rbp+57h+var_70]
0x18000f240  call    WdipFree
0x18000f245  mov     rcx, rsi
0x18000f248  call    WdipFree
0x18000f24d  mov     rcx, [rbp+57h+var_98]; hKey
0x18000f251  test    rcx, rcx
0x18000f254  jz      short loc_18000F260
0x18000f256  call    cs:__imp_RegCloseKey
0x18000f25c  mov     [rbp+57h+var_98], r13
0x18000f260  mov     rcx, [rbp+57h+hKey]; hKey
0x18000f264  test    rcx, rcx
0x18000f267  jz      short loc_18000F26F
  ... truncated ...
```
