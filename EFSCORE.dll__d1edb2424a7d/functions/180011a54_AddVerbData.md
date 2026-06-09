# AddVerbData

- ea: `0x180011a54`
- end: `0x180012223`
- name: `AddVerbData`
- size: `1999`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, unsigned __int16 *, const WCHAR *, __int64, BYTE, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010e14`

## callees

- `0x18001115c`
- `0x180011a54`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012047`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012153`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011e8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011fc4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012047`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012153`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800121e4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011be0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800120d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011be0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800120d7`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800121a7`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800121a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011b41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121fb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011ccd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180011ccd`

## string_xrefs

- `0x180011d28`: `CommandStateHandler`
- `0x180012031`: `UpdateType`
- `0x1800120ac`: `command`

## pseudocode

```c
__int64 __fastcall AddVerbData(
        HKEY a1,
        const WCHAR *a2,
        unsigned __int16 *a3,
        const WCHAR *a4,
        __int64 a5,
        BYTE a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        int a9)
{
  int v9; // esi
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // r13
  int v14; // ebx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  char v18; // si
  int v19; // eax
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  char phkResult; // [rsp+20h] [rbp-81h]
  HKEY v32; // [rsp+50h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-49h] BYREF
  HKEY v34; // [rsp+60h] [rbp-41h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-39h] BYREF
  BYTE v36[4]; // [rsp+70h] [rbp-31h] BYREF
  BYTE v37[4]; // [rsp+74h] [rbp-2Dh] BYREF
  LPOLESTR lpsz; // [rsp+78h] [rbp-29h] BYREF
  IID rclsid; // [rsp+80h] [rbp-21h] BYREF

  v9 = a9;
  v11 = a7;
  v12 = a8;
  *(_DWORD *)Data = 0x2000;
  hKey = 0;
  v32 = 0;
  v34 = 0;
  *(_DWORD *)v37 = a9;
  *(_DWORD *)v36 = 0;
  lpsz = 0;
  rclsid.Data1 = 1533875281;
  *(_DWORD *)&rclsid.Data2 = 1131590113;
  *(_DWORD *)rclsid.Data4 = -444009072;
  *(_DWORD *)&rclsid.Data4[4] = -1176849343;
  if ( !a1 )
  {
    phkResult = 29;
LABEL_3:
    v14 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 41, phkResult);
    goto LABEL_49;
  }
  if ( !a4 )
  {
    phkResult = 30;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    phkResult = 31;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    phkResult = 32;
    goto LABEL_3;
  }
  v14 = RegOpenKeyExW(a1, a2, 0, 7u, &hKey);
  fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 40);
  if ( v14 > 0 )
    v14 = (unsigned __int16)v14 | 0x80070000;
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v14,
              41,
              40) >= 0 )
  {
    v14 = RegCreateKeyExW(hKey, a4, 0, 0, 0, 7u, 0, &v32, 0);
    fnEfsLogTrace1Strings(v16, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 52);
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v14,
                41,
                52) >= 0 )
    {
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          phkResult = 85;
          goto LABEL_3;
        }
        if ( !a3 )
        {
          phkResult = 73;
          goto LABEL_3;
        }
        v18 = 80;
        fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 80);
        v19 = AddRegistryValue(v32, L"EnterpriseId", a3);
      }
      else
      {
        fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 61);
        v14 = StringFromCLSID(&rclsid, &lpsz);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v14,
                    41,
                    61) < 0 )
          goto LABEL_49;
        v18 = 65;
        fnEfsLogTrace1Strings(v20, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 65);
        v19 = AddRegistryValue(v32, L"CommandStateHandler", lpsz);
      }
      v14 = v19;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v19,
                  41,
                  v18) >= 0 )
      {
        v14 = RegSetValueExW(v32, L"AttributeMask", 0, 4u, Data, 4u);
        fnEfsLogTrace1Strings(v21, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 94);
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v14,
                    41,
                    94) >= 0 )
        {
          v14 = RegSetValueExW(v32, L"AttributeValue", 0, 4u, &a6, 4u);
          fnEfsLogTrace1Strings(v22, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 102);
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v14,
                      41,
                      102) >= 0 )
          {
            v14 = RegSetValueExW(v32, L"ImpliedSelectionModel", 0, 4u, v36, 4u);
            fnEfsLogTrace1Strings(v23, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 110);
            if ( v14 > 0 )
              v14 = (unsigned __int16)v14 | 0x80070000;
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v14,
                        41,
                        110) >= 0 )
            {
              fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 117);
              v14 = AddRegistryValue(v32, L"MUIVerb", v11);
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          v14,
                          41,
                          117) >= 0 )
              {
                fnEfsLogTrace1Strings(v25, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 123);
                v14 = AddRegistryValue(v32, L"Icon", v12);
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            v14,
                            41,
                            123) >= 0 )
                {
                  v14 = RegSetValueExW(v32, L"ShowAsDisabledIfHidden", 0, 1u, 0, 0);
                  fnEfsLogTrace1Strings(v26, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 131);
                  if ( v14 > 0 )
                    v14 = (unsigned __int16)v14 | 0x80070000;
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              v14,
                              41,
                              131) >= 0 )
                  {
                    v14 = RegSetValueExW(v32, L"UpdateType", 0, 4u, v37, 4u);
                    fnEfsLogTrace1Strings(
                      v27,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&sourceString,
                      41,
                      139);
                    if ( v14 > 0 )
                      v14 = (unsigned __int16)v14 | 0x80070000;
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                v14,
                                41,
                                139) >= 0 )
                    {
                      v14 = RegCreateKeyExW(v32, L"command", 0, 0, 0, 7u, 0, &v34, 0);
                      fnEfsLogTrace1Strings(
                        v28,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        41,
                        151);
                      if ( v14 > 0 )
                        v14 = (unsigned __int16)v14 | 0x80070000;
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v14,
                                  41,
                                  151) >= 0 )
                      {
                        v14 = RegSetValueExW(
                                v34,
                                L"DelegateExecute",
                                0,
                                1u,
                                L"{5B6D1451-B1E1-4372-90F5-88E541B4DAB9}",
                                0x4Eu);
                        fnEfsLogTrace1Strings(
                          v29,
                          (unsigned int)EFS_TRACE_START_EVENT,
                          (unsigned int)&sourceString,
                          41,
                          160);
                        if ( v14 > 0 )
                          v14 = (unsigned __int16)v14 | 0x80070000;
                        if ( (int)fnEfsLogTrace1String1Dword(
                                    g_hPublisher,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                    (unsigned int)&sourceString,
                                    v14,
                                    41,
                                    160) >= 0 )
                          RegFlushKey(hKey);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_49:
  if ( v34 )
  {
    RegCloseKey(v34);
    v34 = 0;
  }
  if ( v32 )
  {
    RegCloseKey(v32);
    v32 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180011a54  push    rbp
0x180011a56  push    rbx
0x180011a57  push    rsi
0x180011a58  push    rdi
0x180011a59  push    r12
0x180011a5b  push    r13
0x180011a5d  push    r14
0x180011a5f  push    r15
0x180011a61  lea     rbp, [rsp-7]
0x180011a66  sub     rsp, 0A8h
0x180011a6d  mov     rax, cs:__security_cookie
0x180011a74  xor     rax, rsp
0x180011a77  mov     [rbp+3Fh+var_50], rax
0x180011a7b  mov     esi, [rbp+3Fh+arg_40]
0x180011a81  mov     r15, r8
0x180011a84  mov     r12, [rbp+3Fh+arg_30]
0x180011a88  xor     r8d, r8d; ulOptions
0x180011a8b  mov     r13, [rbp+3Fh+arg_38]
0x180011a92  mov     r14, r9
0x180011a95  mov     dword ptr [rbp+3Fh+Data], 2000h
0x180011a9c  mov     [rbp+3Fh+hKey], r8
0x180011aa0  mov     [rbp+3Fh+var_90], r8
0x180011aa4  mov     [rbp+3Fh+var_80], r8
0x180011aa8  mov     dword ptr [rbp+3Fh+var_6C], esi
0x180011aab  mov     dword ptr [rbp+3Fh+var_70], r8d
0x180011aaf  mov     [rbp+3Fh+lpsz], r8
0x180011ab3  mov     [rbp+3Fh+rclsid.Data1], 5B6D1451h
0x180011aba  mov     dword ptr [rbp+3Fh+rclsid.Data2], 4372B1E1h
0x180011ac1  mov     dword ptr [rbp+3Fh+rclsid.Data4], 0E588F590h
0x180011ac8  mov     dword ptr [rbp+3Fh+rclsid.Data4+4], 0B9DAB441h
0x180011acf  test    rcx, rcx
0x180011ad2  jnz     short loc_180011B05
0x180011ad4  mov     dword ptr [rsp+0E0h+phkResult], 11Dh
0x180011adc  mov     r9d, 29h ; ')'
0x180011ae2  mov     rcx, cs:g_hPublisher
0x180011ae9  lea     rdx, EFS_TRACE_ERROR
0x180011af0  mov     r8d, 80070057h
0x180011af6  mov     ebx, 80070057h
0x180011afb  call    fnEfsLogTrace1
0x180011b00  jmp     loc_1800121AD
0x180011b05  test    r14, r14
0x180011b08  jnz     short loc_180011B14
0x180011b0a  mov     dword ptr [rsp+0E0h+phkResult], 11Eh
0x180011b12  jmp     short loc_180011ADC
0x180011b14  test    r12, r12
0x180011b17  jnz     short loc_180011B23
0x180011b19  mov     dword ptr [rsp+0E0h+phkResult], 11Fh
0x180011b21  jmp     short loc_180011ADC
0x180011b23  test    r13, r13
0x180011b26  jnz     short loc_180011B32
0x180011b28  mov     dword ptr [rsp+0E0h+phkResult], 120h
0x180011b30  jmp     short loc_180011ADC
0x180011b32  lea     rax, [rbp+3Fh+hKey]
0x180011b36  mov     r9d, 7; samDesired
0x180011b3c  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180011b41  call    cs:__imp_RegOpenKeyExW
0x180011b47  mov     edi, 29h ; ')'
0x180011b4c  mov     dword ptr [rsp+0E0h+phkResult], 128h
0x180011b54  mov     r9d, edi
0x180011b57  lea     r8, sourceString
0x180011b5e  lea     rdx, EFS_TRACE_START_EVENT
0x180011b65  mov     ebx, eax
0x180011b67  call    fnEfsLogTrace1Strings
0x180011b6c  test    ebx, ebx
0x180011b6e  jle     short loc_180011B79
0x180011b70  movzx   ebx, bx
0x180011b73  or      ebx, 80070000h
0x180011b79  mov     rcx, cs:g_hPublisher
0x180011b80  lea     r9, sourceString
0x180011b87  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], 128h
0x180011b8f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180011b96  mov     [rsp+0E0h+samDesired], edi
0x180011b9a  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180011ba1  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180011ba5  call    fnEfsLogTrace1String1Dword
0x180011baa  xor     ecx, ecx
0x180011bac  test    eax, eax
0x180011bae  js      loc_1800121AD
0x180011bb4  mov     [rsp+0E0h+lpdwDisposition], rcx; lpdwDisposition
0x180011bb9  lea     rax, [rbp+3Fh+var_90]
0x180011bbd  mov     [rsp+0E0h+var_A8], rax; phkResult
0x180011bc2  xor     r9d, r9d; lpClass
0x180011bc5  mov     [rsp+0E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180011bca  xor     r8d, r8d; Reserved
0x180011bcd  mov     [rsp+0E0h+samDesired], 7; samDesired
0x180011bd5  mov     rdx, r14; lpSubKey
0x180011bd8  mov     dword ptr [rsp+0E0h+phkResult], ecx; dwOptions
0x180011bdc  mov     rcx, [rbp+3Fh+hKey]; hKey
0x180011be0  call    cs:__imp_RegCreateKeyExW
0x180011be6  lea     r14, sourceString
0x180011bed  mov     dword ptr [rsp+0E0h+phkResult], 134h
0x180011bf5  mov     r8, r14
0x180011bf8  lea     rdx, EFS_TRACE_START_EVENT
0x180011bff  mov     r9d, edi
0x180011c02  mov     ebx, eax
0x180011c04  call    fnEfsLogTrace1Strings
0x180011c09  test    ebx, ebx
0x180011c0b  jle     short loc_180011C16
0x180011c0d  movzx   ebx, bx
0x180011c10  or      ebx, 80070000h
0x180011c16  mov     rcx, cs:g_hPublisher
0x180011c1d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180011c24  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], 134h
0x180011c2c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180011c33  mov     [rsp+0E0h+samDesired], edi
0x180011c37  mov     r9, r14
0x180011c3a  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180011c3e  call    fnEfsLogTrace1String1Dword
0x180011c43  test    eax, eax
0x180011c45  js      loc_1800121AD
0x180011c4b  mov     r9d, edi
0x180011c4e  test    esi, esi
0x180011c50  jz      short loc_180011CAD
0x180011c52  cmp     esi, 1
0x180011c55  jz      short loc_180011C64
0x180011c57  mov     dword ptr [rsp+0E0h+phkResult], 155h
0x180011c5f  jmp     loc_180011AE2
0x180011c64  test    r15, r15
0x180011c67  jnz     short loc_180011C76
0x180011c69  mov     dword ptr [rsp+0E0h+phkResult], 149h
0x180011c71  jmp     loc_180011AE2
0x180011c76  mov     esi, 150h
0x180011c7b  lea     rdx, EFS_TRACE_START_EVENT
0x180011c82  mov     r8, r14
0x180011c85  mov     dword ptr [rsp+0E0h+phkResult], esi
0x180011c89  call    fnEfsLogTrace1Strings
0x180011c8e  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011c92  lea     rdx, aEnterpriseid; "EnterpriseId"
0x180011c99  mov     r8, r15; unsigned __int16 *
0x180011c9c  call    AddRegistryValue
0x180011ca1  lea     r15, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180011ca8  jmp     loc_180011D38
0x180011cad  mov     esi, 13Dh
0x180011cb2  lea     rdx, EFS_TRACE_START_EVENT
0x180011cb9  mov     r8, r14
0x180011cbc  mov     dword ptr [rsp+0E0h+phkResult], esi
0x180011cc0  call    fnEfsLogTrace1Strings
0x180011cc5  lea     rdx, [rbp+3Fh+lpsz]; lplpsz
0x180011cc9  lea     rcx, [rbp+3Fh+rclsid]; rclsid
0x180011ccd  call    cs:__imp_StringFromCLSID
0x180011cd3  mov     rcx, cs:g_hPublisher
0x180011cda  lea     r15, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180011ce1  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], esi
0x180011ce5  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180011cec  mov     r8, r15
0x180011cef  mov     [rsp+0E0h+samDesired], edi
0x180011cf3  mov     r9, r14
0x180011cf6  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180011cfa  mov     ebx, eax
0x180011cfc  call    fnEfsLogTrace1String1Dword
0x180011d01  test    eax, eax
0x180011d03  js      loc_1800121AD
0x180011d09  mov     esi, 141h
0x180011d0e  lea     rdx, EFS_TRACE_START_EVENT
0x180011d15  mov     r9d, edi
0x180011d18  mov     dword ptr [rsp+0E0h+phkResult], esi
0x180011d1c  mov     r8, r14
0x180011d1f  call    fnEfsLogTrace1Strings
0x180011d24  mov     r8, [rbp+3Fh+lpsz]; unsigned __int16 *
0x180011d28  lea     rdx, aCommandstateha; "CommandStateHandler"
0x180011d2f  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011d33  call    AddRegistryValue
0x180011d38  mov     rcx, cs:g_hPublisher
0x180011d3f  mov     r9, r14
0x180011d42  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], esi
0x180011d46  mov     r8, r15
0x180011d49  lea     rsi, EFS_TRACE_COMPLETE_EVENT
0x180011d50  mov     [rsp+0E0h+samDesired], edi
0x180011d54  mov     rdx, rsi
0x180011d57  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180011d5b  mov     ebx, eax
0x180011d5d  call    fnEfsLogTrace1String1Dword
0x180011d62  test    eax, eax
0x180011d64  js      loc_1800121AD
0x180011d6a  mov     ecx, 4
0x180011d6f  lea     rax, [rbp+3Fh+Data]
0x180011d73  mov     [rsp+0E0h+samDesired], ecx; cbData
0x180011d77  lea     rdx, aAttributemask; "AttributeMask"
0x180011d7e  mov     r9d, ecx; dwType
0x180011d81  mov     [rsp+0E0h+phkResult], rax; lpData
0x180011d86  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011d8a  xor     r8d, r8d; Reserved
0x180011d8d  call    cs:__imp_RegSetValueExW
0x180011d93  mov     r9d, edi
0x180011d96  mov     dword ptr [rsp+0E0h+phkResult], 15Eh
0x180011d9e  mov     r8, r14
0x180011da1  lea     rdx, EFS_TRACE_START_EVENT
0x180011da8  mov     ebx, eax
0x180011daa  call    fnEfsLogTrace1Strings
0x180011daf  test    ebx, ebx
0x180011db1  jle     short loc_180011DBC
0x180011db3  movzx   ebx, bx
0x180011db6  or      ebx, 80070000h
0x180011dbc  mov     rcx, cs:g_hPublisher
0x180011dc3  mov     r9, r14
0x180011dc6  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], 15Eh
0x180011dce  mov     r8, r15
0x180011dd1  mov     [rsp+0E0h+samDesired], edi
0x180011dd5  mov     rdx, rsi
0x180011dd8  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180011ddc  call    fnEfsLogTrace1String1Dword
0x180011de1  test    eax, eax
0x180011de3  js      loc_1800121AD
0x180011de9  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011ded  lea     rax, [rbp+3Fh+arg_28]
0x180011df1  mov     r9d, 4; dwType
0x180011df7  lea     rdx, aAttributevalue; "AttributeValue"
0x180011dfe  mov     [rsp+0E0h+samDesired], r9d; cbData
0x180011e03  xor     r8d, r8d; Reserved
0x180011e06  mov     [rsp+0E0h+phkResult], rax; lpData
0x180011e0b  call    cs:__imp_RegSetValueExW
0x180011e11  mov     r9d, edi
0x180011e14  mov     dword ptr [rsp+0E0h+phkResult], 166h
0x180011e1c  mov     r8, r14
0x180011e1f  lea     rdx, EFS_TRACE_START_EVENT
0x180011e26  mov     ebx, eax
0x180011e28  call    fnEfsLogTrace1Strings
0x180011e2d  test    ebx, ebx
0x180011e2f  jle     short loc_180011E3A
0x180011e31  movzx   ebx, bx
0x180011e34  or      ebx, 80070000h
0x180011e3a  mov     rcx, cs:g_hPublisher
0x180011e41  mov     r9, r14
0x180011e44  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], 166h
0x180011e4c  mov     r8, r15
0x180011e4f  mov     [rsp+0E0h+samDesired], edi
0x180011e53  mov     rdx, rsi
0x180011e56  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180011e5a  call    fnEfsLogTrace1String1Dword
0x180011e5f  test    eax, eax
0x180011e61  js      loc_1800121AD
0x180011e67  mov     ecx, 4
0x180011e6c  lea     rax, [rbp+3Fh+var_70]
0x180011e70  mov     [rsp+0E0h+samDesired], ecx; cbData
0x180011e74  lea     rdx, aImpliedselecti; "ImpliedSelectionModel"
0x180011e7b  mov     r9d, ecx; dwType
0x180011e7e  mov     [rsp+0E0h+phkResult], rax; lpData
0x180011e83  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011e87  xor     r8d, r8d; Reserved
0x180011e8a  call    cs:__imp_RegSetValueExW
0x180011e90  mov     r9d, edi
0x180011e93  mov     dword ptr [rsp+0E0h+phkResult], 16Eh
0x180011e9b  mov     r8, r14
0x180011e9e  lea     rdx, EFS_TRACE_START_EVENT
0x180011ea5  mov     ebx, eax
0x180011ea7  call    fnEfsLogTrace1Strings
0x180011eac  test    ebx, ebx
0x180011eae  jle     short loc_180011EB9
0x180011eb0  movzx   ebx, bx
0x180011eb3  or      ebx, 80070000h
0x180011eb9  mov     rcx, cs:g_hPublisher
0x180011ec0  mov     r9, r14
0x180011ec3  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], 16Eh
0x180011ecb  mov     r8, r15
0x180011ece  mov     [rsp+0E0h+samDesired], edi
0x180011ed2  mov     rdx, rsi
0x180011ed5  mov     dword ptr [rsp+0E0h+phkResult], ebx
0x180011ed9  call    fnEfsLogTrace1String1Dword
0x180011ede  test    eax, eax
0x180011ee0  js      loc_1800121AD
0x180011ee6  mov     esi, 175h
0x180011eeb  lea     rdx, EFS_TRACE_START_EVENT
0x180011ef2  mov     r9d, edi
0x180011ef5  mov     dword ptr [rsp+0E0h+phkResult], esi
0x180011ef9  mov     r8, r14
0x180011efc  call    fnEfsLogTrace1Strings
0x180011f01  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011f05  lea     rdx, aMuiverb; "MUIVerb"
0x180011f0c  mov     r8, r12; unsigned __int16 *
0x180011f0f  call    AddRegistryValue
0x180011f14  mov     rcx, cs:g_hPublisher
0x180011f1b  lea     r12, EFS_TRACE_COMPLETE_EVENT
0x180011f22  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], esi
0x180011f26  mov     rdx, r12
0x180011f29  mov     [rsp+0E0h+samDesired], edi
0x180011f2d  mov     r9, r14
0x180011f30  mov     r8, r15
0x180011f33  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180011f37  mov     ebx, eax
0x180011f39  call    fnEfsLogTrace1String1Dword
0x180011f3e  test    eax, eax
0x180011f40  js      loc_1800121AD
0x180011f46  mov     esi, 17Bh
0x180011f4b  lea     rdx, EFS_TRACE_START_EVENT
0x180011f52  mov     r9d, edi
0x180011f55  mov     dword ptr [rsp+0E0h+phkResult], esi
0x180011f59  mov     r8, r14
0x180011f5c  call    fnEfsLogTrace1Strings
0x180011f61  mov     rcx, [rbp+3Fh+var_90]; hKey
0x180011f65  lea     rdx, aIcon; "Icon"
0x180011f6c  mov     r8, r13; unsigned __int16 *
0x180011f6f  call    AddRegistryValue
0x180011f74  mov     rcx, cs:g_hPublisher
0x180011f7b  mov     r9, r14
0x180011f7e  mov     dword ptr [rsp+0E0h+lpSecurityAttributes], esi
0x180011f82  mov     r8, r15
0x180011f85  mov     [rsp+0E0h+samDesired], edi
0x180011f89  mov     rdx, r12
0x180011f8c  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180011f90  mov     ebx, eax
  ... truncated ...
```
