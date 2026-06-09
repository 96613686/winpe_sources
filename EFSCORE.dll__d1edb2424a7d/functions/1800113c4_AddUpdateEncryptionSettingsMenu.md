# AddUpdateEncryptionSettingsMenu

- ea: `0x1800113c4`
- end: `0x180011a4b`
- name: `AddUpdateEncryptionSettingsMenu`
- size: `1671`
- prototype: `__int64(HKEY, const WCHAR *, DWORD, __int64, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010e14`

## callees

- `0x1800113c4`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011505`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001158e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011696`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011722`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001179e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011819`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011895`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011916`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011505`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001158e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011617`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011696`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011722`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001179e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011819`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011895`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011916`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a2a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001146a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800119ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001146a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800119ab`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011a04`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011a04`

## string_xrefs

- `0x18001156a`: `@efscore.dll,-101`
- `0x18001167c`: `ExtendedSubCommandsKey`

## pseudocode

```c
__int64 AddUpdateEncryptionSettingsMenu(HKEY a1, const WCHAR *a2, DWORD a3, __int64 a4, ...)
{
  int v6; // ebx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  BYTE Data[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  int v22; // [rsp+A8h] [rbp+48h] BYREF
  va_list va; // [rsp+B0h] [rbp+50h] BYREF

  va_start(va, a4);
  *(_DWORD *)Data = 0x2000;
  hKey = 0;
  phkResult = 0;
  v22 = 0;
  if ( a1 )
  {
    v6 = RegCreateKeyExW(a1, a2, 0, 0, 0, 7u, 0, &hKey, 0);
    fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 70);
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v6,
                41,
                70) >= 0 )
    {
      v6 = RegSetValueExW(
             hKey,
             L"AppliesTo",
             0,
             1u,
             L"System.StorageProviderId:<>\"network\" AND System.StorageProviderProtectionMode:<>1 AND System.StorageProvi"
              "derProtectionMode:<>2",
             0xFEu);
      fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 81);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v6,
                  41,
                  81) >= 0 )
      {
        v6 = RegSetValueExW(hKey, L"MUIVerb", 0, 1u, L"@efscore.dll,-101", 0x24u);
        fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 89);
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v6,
                    41,
                    89) >= 0 )
        {
          v6 = RegSetValueExW(hKey, L"Position", 0, 1u, L"Bottom", 0xEu);
          fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 97);
          if ( v6 > 0 )
            v6 = (unsigned __int16)v6 | 0x80070000;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v6,
                      41,
                      97) >= 0 )
          {
            v6 = RegSetValueExW(hKey, L"ExtendedSubCommandsKey", 0, 1u, (const BYTE *)a2, a3);
            fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 105);
            if ( v6 > 0 )
              v6 = (unsigned __int16)v6 | 0x80070000;
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v6,
                        41,
                        105) >= 0 )
            {
              v6 = RegSetValueExW(hKey, L"MultiSelectModel", 0, 1u, L"Player", 0xEu);
              fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 113);
              if ( v6 > 0 )
                v6 = (unsigned __int16)v6 | 0x80070000;
              if ( (int)fnEfsLogTrace1String1Dword(
                          g_hPublisher,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                          (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                          (unsigned int)&sourceString,
                          v6,
                          41,
                          113) >= 0 )
              {
                v6 = RegSetValueExW(hKey, L"AttributeMask", 0, 4u, Data, 4u);
                fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 121);
                if ( v6 > 0 )
                  v6 = (unsigned __int16)v6 | 0x80070000;
                if ( (int)fnEfsLogTrace1String1Dword(
                            g_hPublisher,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                            (unsigned int)&sourceString,
                            v6,
                            41,
                            121) >= 0 )
                {
                  v6 = RegSetValueExW(hKey, L"AttributeValue", 0, 4u, (const BYTE *)va, 4u);
                  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 41, 129);
                  if ( v6 > 0 )
                    v6 = (unsigned __int16)v6 | 0x80070000;
                  if ( (int)fnEfsLogTrace1String1Dword(
                              g_hPublisher,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                              (unsigned int)&sourceString,
                              v6,
                              41,
                              129) >= 0 )
                  {
                    v6 = RegSetValueExW(hKey, L"ImpliedSelectionModel", 0, 4u, (const BYTE *)&v22, 4u);
                    fnEfsLogTrace1Strings(
                      v15,
                      (unsigned int)EFS_TRACE_START_EVENT,
                      (unsigned int)&sourceString,
                      41,
                      137);
                    if ( v6 > 0 )
                      v6 = (unsigned __int16)v6 | 0x80070000;
                    if ( (int)fnEfsLogTrace1String1Dword(
                                g_hPublisher,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                (unsigned int)&sourceString,
                                v6,
                                41,
                                137) >= 0 )
                    {
                      v6 = RegSetValueExW(hKey, L"ActivationModel", 0, 1u, L"COM", 8u);
                      fnEfsLogTrace1Strings(
                        v16,
                        (unsigned int)EFS_TRACE_START_EVENT,
                        (unsigned int)&sourceString,
                        41,
                        145);
                      if ( v6 > 0 )
                        v6 = (unsigned __int16)v6 | 0x80070000;
                      if ( (int)fnEfsLogTrace1String1Dword(
                                  g_hPublisher,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                  (unsigned int)&sourceString,
                                  v6,
                                  41,
                                  145) >= 0 )
                      {
                        v6 = RegCreateKeyExW(hKey, L"Shell", 0, 0, 0, 7u, 0, &phkResult, 0);
                        fnEfsLogTrace1Strings(
                          v17,
                          (unsigned int)EFS_TRACE_START_EVENT,
                          (unsigned int)&sourceString,
                          41,
                          157);
                        if ( v6 > 0 )
                          v6 = (unsigned __int16)v6 | 0x80070000;
                        if ( (int)fnEfsLogTrace1String1Dword(
                                    g_hPublisher,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                                    (unsigned int)&sourceString,
                                    v6,
                                    41,
                                    157) >= 0 )
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
  else
  {
    v6 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 41, 58);
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800113c4  mov     rax, rsp
0x1800113c7  mov     [rax+10h], rbx
0x1800113cb  mov     [rax+18h], rsi
0x1800113cf  mov     [rax+20h], r9d
0x1800113d3  push    rbp
0x1800113d4  push    rdi
0x1800113d5  push    r12
0x1800113d7  push    r13
0x1800113d9  push    r14
0x1800113db  mov     rbp, rsp
0x1800113de  sub     rsp, 60h
0x1800113e2  mov     dword ptr [rbp+Data], 2000h
0x1800113e9  mov     r14d, r8d
0x1800113ec  mov     [rbp+hKey], 0
0x1800113f4  mov     rsi, rdx
0x1800113f7  mov     [rbp+var_8], 0
0x1800113ff  mov     [rbp+arg_18], 0
0x180011406  test    rcx, rcx
0x180011409  jnz     short loc_180011439
0x18001140b  lea     r9d, [rcx+29h]
0x18001140f  mov     dword ptr [rax-68h], 3Ah ; ':'
0x180011416  mov     rcx, cs:g_hPublisher
0x18001141d  lea     rdx, EFS_TRACE_ERROR
0x180011424  mov     r8d, 80070057h
0x18001142a  mov     ebx, 80070057h
0x18001142f  call    fnEfsLogTrace1
0x180011434  jmp     loc_180011A0A
0x180011439  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x180011442  lea     rax, [rbp+hKey]
0x180011446  mov     [rsp+60h+phkResult], rax; phkResult
0x18001144b  xor     r9d, r9d; lpClass
0x18001144e  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180011457  xor     r8d, r8d; Reserved
0x18001145a  mov     [rsp+60h+samDesired], 7; samDesired
0x180011462  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18001146a  call    cs:__imp_RegCreateKeyExW
0x180011470  mov     edi, 29h ; ')'
0x180011475  mov     [rsp+60h+dwOptions], 46h ; 'F'
0x18001147d  lea     r12, sourceString
0x180011484  mov     r9d, edi
0x180011487  mov     r8, r12
0x18001148a  lea     rdx, EFS_TRACE_START_EVENT
0x180011491  mov     ebx, eax
0x180011493  call    fnEfsLogTrace1Strings
0x180011498  mov     r13d, 80070000h
0x18001149e  test    ebx, ebx
0x1800114a0  jle     short loc_1800114A8
0x1800114a2  movzx   ebx, bx
0x1800114a5  or      ebx, r13d
0x1800114a8  mov     rcx, cs:g_hPublisher
0x1800114af  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800114b6  mov     dword ptr [rsp+60h+lpSecurityAttributes], 46h ; 'F'
0x1800114be  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800114c5  mov     [rsp+60h+samDesired], edi
0x1800114c9  mov     r9, r12
0x1800114cc  mov     [rsp+60h+dwOptions], ebx
0x1800114d0  call    fnEfsLogTrace1String1Dword
0x1800114d5  test    eax, eax
0x1800114d7  js      loc_180011A0A
0x1800114dd  mov     rcx, [rbp+hKey]; hKey
0x1800114e1  lea     rax, Data; "System.StorageProviderId:<>\"network\" "...
0x1800114e8  mov     [rsp+60h+samDesired], 0FEh; cbData
0x1800114f0  lea     rdx, ValueName; "AppliesTo"
0x1800114f7  mov     r9d, 1; dwType
0x1800114fd  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180011502  xor     r8d, r8d; Reserved
0x180011505  call    cs:__imp_RegSetValueExW
0x18001150b  mov     r9d, edi
0x18001150e  mov     [rsp+60h+dwOptions], 51h ; 'Q'
0x180011516  mov     r8, r12
0x180011519  lea     rdx, EFS_TRACE_START_EVENT
0x180011520  mov     ebx, eax
0x180011522  call    fnEfsLogTrace1Strings
0x180011527  test    ebx, ebx
0x180011529  jle     short loc_180011531
0x18001152b  movzx   ebx, bx
0x18001152e  or      ebx, r13d
0x180011531  mov     rcx, cs:g_hPublisher
0x180011538  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18001153f  mov     dword ptr [rsp+60h+lpSecurityAttributes], 51h ; 'Q'
0x180011547  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18001154e  mov     [rsp+60h+samDesired], edi
0x180011552  mov     r9, r12
0x180011555  mov     [rsp+60h+dwOptions], ebx
0x180011559  call    fnEfsLogTrace1String1Dword
0x18001155e  test    eax, eax
0x180011560  js      loc_180011A0A
0x180011566  mov     rcx, [rbp+hKey]; hKey
0x18001156a  lea     rax, aEfscoreDll101; "@efscore.dll,-101"
0x180011571  mov     [rsp+60h+samDesired], 24h ; '$'; cbData
0x180011579  lea     rdx, aMuiverb; "MUIVerb"
0x180011580  mov     r9d, 1; dwType
0x180011586  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001158b  xor     r8d, r8d; Reserved
0x18001158e  call    cs:__imp_RegSetValueExW
0x180011594  mov     r9d, edi
0x180011597  mov     [rsp+60h+dwOptions], 59h ; 'Y'
0x18001159f  mov     r8, r12
0x1800115a2  lea     rdx, EFS_TRACE_START_EVENT
0x1800115a9  mov     ebx, eax
0x1800115ab  call    fnEfsLogTrace1Strings
0x1800115b0  test    ebx, ebx
0x1800115b2  jle     short loc_1800115BA
0x1800115b4  movzx   ebx, bx
0x1800115b7  or      ebx, r13d
0x1800115ba  mov     rcx, cs:g_hPublisher
0x1800115c1  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800115c8  mov     dword ptr [rsp+60h+lpSecurityAttributes], 59h ; 'Y'
0x1800115d0  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800115d7  mov     [rsp+60h+samDesired], edi
0x1800115db  mov     r9, r12
0x1800115de  mov     [rsp+60h+dwOptions], ebx
0x1800115e2  call    fnEfsLogTrace1String1Dword
0x1800115e7  test    eax, eax
0x1800115e9  js      loc_180011A0A
0x1800115ef  mov     rcx, [rbp+hKey]; hKey
0x1800115f3  lea     rax, aBottom; "Bottom"
0x1800115fa  mov     [rsp+60h+samDesired], 0Eh; cbData
0x180011602  lea     rdx, aPosition; "Position"
0x180011609  mov     r9d, 1; dwType
0x18001160f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180011614  xor     r8d, r8d; Reserved
0x180011617  call    cs:__imp_RegSetValueExW
0x18001161d  mov     r9d, edi
0x180011620  mov     [rsp+60h+dwOptions], 61h ; 'a'
0x180011628  mov     r8, r12
0x18001162b  lea     rdx, EFS_TRACE_START_EVENT
0x180011632  mov     ebx, eax
0x180011634  call    fnEfsLogTrace1Strings
0x180011639  test    ebx, ebx
0x18001163b  jle     short loc_180011643
0x18001163d  movzx   ebx, bx
0x180011640  or      ebx, r13d
0x180011643  mov     rcx, cs:g_hPublisher
0x18001164a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180011651  mov     dword ptr [rsp+60h+lpSecurityAttributes], 61h ; 'a'
0x180011659  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180011660  mov     [rsp+60h+samDesired], edi
0x180011664  mov     r9, r12
0x180011667  mov     [rsp+60h+dwOptions], ebx
0x18001166b  call    fnEfsLogTrace1String1Dword
0x180011670  test    eax, eax
0x180011672  js      loc_180011A0A
0x180011678  mov     rcx, [rbp+hKey]; hKey
0x18001167c  lea     rdx, aExtendedsubcom; "ExtendedSubCommandsKey"
0x180011683  mov     [rsp+60h+samDesired], r14d; cbData
0x180011688  mov     r9d, 1; dwType
0x18001168e  xor     r8d, r8d; Reserved
0x180011691  mov     qword ptr [rsp+60h+dwOptions], rsi; lpData
0x180011696  call    cs:__imp_RegSetValueExW
0x18001169c  mov     esi, 69h ; 'i'
0x1800116a1  lea     rdx, EFS_TRACE_START_EVENT
0x1800116a8  mov     r9d, edi
0x1800116ab  mov     [rsp+60h+dwOptions], esi
0x1800116af  mov     r8, r12
0x1800116b2  mov     ebx, eax
0x1800116b4  call    fnEfsLogTrace1Strings
0x1800116b9  test    ebx, ebx
0x1800116bb  jle     short loc_1800116C3
0x1800116bd  movzx   ebx, bx
0x1800116c0  or      ebx, r13d
0x1800116c3  mov     rcx, cs:g_hPublisher
0x1800116ca  lea     r14, EFS_TRACE_COMPLETE_EVENT
0x1800116d1  mov     dword ptr [rsp+60h+lpSecurityAttributes], esi
0x1800116d5  mov     r9, r12
0x1800116d8  lea     rsi, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800116df  mov     [rsp+60h+samDesired], edi
0x1800116e3  mov     r8, rsi
0x1800116e6  mov     [rsp+60h+dwOptions], ebx
0x1800116ea  mov     rdx, r14
0x1800116ed  call    fnEfsLogTrace1String1Dword
0x1800116f2  test    eax, eax
0x1800116f4  js      loc_180011A0A
0x1800116fa  mov     rcx, [rbp+hKey]; hKey
0x1800116fe  lea     rax, aPlayer; "Player"
0x180011705  mov     [rsp+60h+samDesired], 0Eh; cbData
0x18001170d  lea     rdx, aMultiselectmod; "MultiSelectModel"
0x180011714  mov     r9d, 1; dwType
0x18001171a  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001171f  xor     r8d, r8d; Reserved
0x180011722  call    cs:__imp_RegSetValueExW
0x180011728  mov     r9d, edi
0x18001172b  mov     [rsp+60h+dwOptions], 71h ; 'q'
0x180011733  mov     r8, r12
0x180011736  lea     rdx, EFS_TRACE_START_EVENT
0x18001173d  mov     ebx, eax
0x18001173f  call    fnEfsLogTrace1Strings
0x180011744  test    ebx, ebx
0x180011746  jle     short loc_18001174E
0x180011748  movzx   ebx, bx
0x18001174b  or      ebx, r13d
0x18001174e  mov     rcx, cs:g_hPublisher
0x180011755  mov     r9, r12
0x180011758  mov     dword ptr [rsp+60h+lpSecurityAttributes], 71h ; 'q'
0x180011760  mov     r8, rsi
0x180011763  mov     [rsp+60h+samDesired], edi
0x180011767  mov     rdx, r14
0x18001176a  mov     [rsp+60h+dwOptions], ebx
0x18001176e  call    fnEfsLogTrace1String1Dword
0x180011773  test    eax, eax
0x180011775  js      loc_180011A0A
0x18001177b  mov     ecx, 4
0x180011780  lea     rax, [rbp+Data]
0x180011784  mov     [rsp+60h+samDesired], ecx; cbData
0x180011788  lea     rdx, aAttributemask; "AttributeMask"
0x18001178f  mov     r9d, ecx; dwType
0x180011792  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180011797  mov     rcx, [rbp+hKey]; hKey
0x18001179b  xor     r8d, r8d; Reserved
0x18001179e  call    cs:__imp_RegSetValueExW
0x1800117a4  mov     r9d, edi
0x1800117a7  mov     [rsp+60h+dwOptions], 79h ; 'y'
0x1800117af  mov     r8, r12
0x1800117b2  lea     rdx, EFS_TRACE_START_EVENT
0x1800117b9  mov     ebx, eax
0x1800117bb  call    fnEfsLogTrace1Strings
0x1800117c0  test    ebx, ebx
0x1800117c2  jle     short loc_1800117CA
0x1800117c4  movzx   ebx, bx
0x1800117c7  or      ebx, r13d
0x1800117ca  mov     rcx, cs:g_hPublisher
0x1800117d1  mov     r9, r12
0x1800117d4  mov     dword ptr [rsp+60h+lpSecurityAttributes], 79h ; 'y'
0x1800117dc  mov     r8, rsi
0x1800117df  mov     [rsp+60h+samDesired], edi
0x1800117e3  mov     rdx, r14
0x1800117e6  mov     [rsp+60h+dwOptions], ebx
0x1800117ea  call    fnEfsLogTrace1String1Dword
0x1800117ef  test    eax, eax
0x1800117f1  js      loc_180011A0A
0x1800117f7  mov     rcx, [rbp+hKey]; hKey
0x1800117fb  lea     rax, [rbp+arg_20]
0x1800117ff  mov     r9d, 4; dwType
0x180011805  lea     rdx, aAttributevalue; "AttributeValue"
0x18001180c  mov     [rsp+60h+samDesired], r9d; cbData
0x180011811  xor     r8d, r8d; Reserved
0x180011814  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180011819  call    cs:__imp_RegSetValueExW
0x18001181f  mov     r9d, edi
0x180011822  mov     [rsp+60h+dwOptions], 81h
0x18001182a  mov     r8, r12
0x18001182d  lea     rdx, EFS_TRACE_START_EVENT
0x180011834  mov     ebx, eax
0x180011836  call    fnEfsLogTrace1Strings
0x18001183b  test    ebx, ebx
0x18001183d  jle     short loc_180011845
0x18001183f  movzx   ebx, bx
0x180011842  or      ebx, r13d
0x180011845  mov     rcx, cs:g_hPublisher
0x18001184c  mov     r9, r12
0x18001184f  mov     dword ptr [rsp+60h+lpSecurityAttributes], 81h
0x180011857  mov     r8, rsi
0x18001185a  mov     [rsp+60h+samDesired], edi
0x18001185e  mov     rdx, r14
0x180011861  mov     [rsp+60h+dwOptions], ebx
0x180011865  call    fnEfsLogTrace1String1Dword
0x18001186a  test    eax, eax
0x18001186c  js      loc_180011A0A
0x180011872  mov     ecx, 4
0x180011877  lea     rax, [rbp+arg_18]
0x18001187b  mov     [rsp+60h+samDesired], ecx; cbData
0x18001187f  lea     rdx, aImpliedselecti; "ImpliedSelectionModel"
0x180011886  mov     r9d, ecx; dwType
0x180011889  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18001188e  mov     rcx, [rbp+hKey]; hKey
0x180011892  xor     r8d, r8d; Reserved
0x180011895  call    cs:__imp_RegSetValueExW
0x18001189b  mov     r9d, edi
0x18001189e  mov     [rsp+60h+dwOptions], 89h
0x1800118a6  mov     r8, r12
0x1800118a9  lea     rdx, EFS_TRACE_START_EVENT
0x1800118b0  mov     ebx, eax
0x1800118b2  call    fnEfsLogTrace1Strings
0x1800118b7  test    ebx, ebx
0x1800118b9  jle     short loc_1800118C1
0x1800118bb  movzx   ebx, bx
0x1800118be  or      ebx, r13d
0x1800118c1  mov     rcx, cs:g_hPublisher
0x1800118c8  mov     r9, r12
0x1800118cb  mov     dword ptr [rsp+60h+lpSecurityAttributes], 89h
0x1800118d3  mov     r8, rsi
0x1800118d6  mov     [rsp+60h+samDesired], edi
0x1800118da  mov     rdx, r14
0x1800118dd  mov     [rsp+60h+dwOptions], ebx
0x1800118e1  call    fnEfsLogTrace1String1Dword
0x1800118e6  test    eax, eax
0x1800118e8  js      loc_180011A0A
0x1800118ee  mov     rcx, [rbp+hKey]; hKey
0x1800118f2  lea     rax, aCom; "COM"
0x1800118f9  mov     [rsp+60h+samDesired], 8; cbData
0x180011901  lea     rdx, aActivationmode; "ActivationModel"
0x180011908  mov     r9d, 1; dwType
0x18001190e  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180011913  xor     r8d, r8d; Reserved
0x180011916  call    cs:__imp_RegSetValueExW
0x18001191c  mov     r9d, edi
0x18001191f  mov     [rsp+60h+dwOptions], 91h
0x180011927  mov     r8, r12
0x18001192a  lea     rdx, EFS_TRACE_START_EVENT
0x180011931  mov     ebx, eax
  ... truncated ...
```
