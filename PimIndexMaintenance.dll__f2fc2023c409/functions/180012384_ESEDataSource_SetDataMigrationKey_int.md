# ESEDataSource::_SetDataMigrationKey(int)

- ea: `0x180012384`
- end: `0x18001249f`
- name: `?_SetDataMigrationKey@ESEDataSource@@AEAAJH@Z`
- size: `283`
- prototype: `__int64 __fastcall(ESEDataSource *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee40`

## callees

- `0x180003edc`
- `0x1800104b8`
- `0x180012384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012491`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012413`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012491`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800123e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800123e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012441`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012441`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180012465`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180012465`

## pseudocode

```c
__int64 __fastcall ESEDataSource::_SetDataMigrationKey(ESEDataSource *this)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  __int64 v5; // r9
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  int Data[6]; // [rsp+50h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  Data[0] = 1;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v4 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v4 = (unsigned __int16)Key | 0x80070000;
    v5 = 498;
LABEL_5:
    Log_HREvent_2(v4, 0, v3, v5);
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  v7 = RegSetValueExW(hKey, L"DataMigration", 0, 4u, (const BYTE *)Data, 4u);
  v4 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    v5 = 508;
    goto LABEL_5;
  }
  v8 = RegFlushKey(hKey);
  v4 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    v5 = 511;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180012384  mov     rax, rsp
0x180012387  mov     [rax+8], rcx
0x18001238b  push    rbx
0x18001238c  sub     rsp, 60h
0x180012390  lea     rcx, [rax+8]
0x180012394  mov     dword ptr [rax-18h], 1
0x18001239b  mov     qword ptr [rax+8], 0
0x1800123a3  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x1800123a8  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x1800123b1  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x1800123b8  mov     [rsp+68h+phkResult], rax; phkResult
0x1800123bd  xor     r9d, r9d; lpClass
0x1800123c0  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800123c9  xor     r8d, r8d; Reserved
0x1800123cc  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x1800123d4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800123db  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800123e3  call    cs:__imp_RegCreateKeyExW
0x1800123e9  mov     ebx, eax
0x1800123eb  test    eax, eax
0x1800123ed  jz      short loc_18001241D
0x1800123ef  jle     short loc_1800123FA
0x1800123f1  movzx   ebx, ax
0x1800123f4  or      ebx, 80070000h
0x1800123fa  mov     r9d, 1F2h
0x180012400  xor     edx, edx
0x180012402  mov     ecx, ebx
0x180012404  call    Log_HREvent_2
0x180012409  mov     rcx, [rsp+68h+hKey]; hKey
0x18001240e  test    rcx, rcx
0x180012411  jz      short loc_180012419
0x180012413  call    cs:__imp_RegCloseKey
0x180012419  mov     eax, ebx
0x18001241b  jmp     short loc_180012499
0x18001241d  mov     rcx, [rsp+68h+hKey]; hKey
0x180012422  lea     rax, [rsp+68h+Data]
0x180012427  mov     r9d, 4; dwType
0x18001242d  lea     rdx, aDatamigration; "DataMigration"
0x180012434  mov     [rsp+68h+samDesired], r9d; cbData
0x180012439  xor     r8d, r8d; Reserved
0x18001243c  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180012441  call    cs:__imp_RegSetValueExW
0x180012447  mov     ebx, eax
0x180012449  test    eax, eax
0x18001244b  jz      short loc_180012460
0x18001244d  jle     short loc_180012458
0x18001244f  movzx   ebx, ax
0x180012452  or      ebx, 80070000h
0x180012458  mov     r9d, 1FCh
0x18001245e  jmp     short loc_180012400
0x180012460  mov     rcx, [rsp+68h+hKey]; hKey
0x180012465  call    cs:__imp_RegFlushKey
0x18001246b  mov     ebx, eax
0x18001246d  test    eax, eax
0x18001246f  jz      short loc_180012487
0x180012471  jle     short loc_18001247C
0x180012473  movzx   ebx, ax
0x180012476  or      ebx, 80070000h
0x18001247c  mov     r9d, 1FFh
0x180012482  jmp     loc_180012400
0x180012487  mov     rcx, [rsp+68h+hKey]; hKey
0x18001248c  test    rcx, rcx
0x18001248f  jz      short loc_180012497
0x180012491  call    cs:__imp_RegCloseKey
0x180012497  xor     eax, eax
0x180012499  add     rsp, 60h
0x18001249d  pop     rbx
0x18001249e  retn
```
