# ESEDataSource::SetRebuildAllIndexesKey(int)

- ea: `0x18001122c`
- end: `0x180011343`
- name: `?SetRebuildAllIndexesKey@ESEDataSource@@QEAAJH@Z`
- size: `279`
- prototype: `__int64 __fastcall(ESEDataSource *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b674`
- `0x18000ee40`
- `0x180011f70`

## callees

- `0x180003edc`
- `0x1800104b8`
- `0x18001122c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011335`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800112b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011335`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011287`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011287`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800112e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800112e5`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011309`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011309`

## pseudocode

```c
__int64 __fastcall ESEDataSource::SetRebuildAllIndexesKey(ESEDataSource *this, int a2)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // r9
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  int Data; // [rsp+68h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 0xF003Fu, 0, phkResult, 0);
  v5 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v5 = (unsigned __int16)Key | 0x80070000;
    v6 = 258;
LABEL_5:
    Log_HREvent_2(v5, 0, v4, v6);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v8 = RegSetValueExW(hKey, L"RebuildAllIndexes", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = 268;
    goto LABEL_5;
  }
  v9 = RegFlushKey(hKey);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = 271;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001122c  mov     rax, rsp
0x18001122f  mov     [rax+10h], edx
0x180011232  mov     [rax+8], rcx
0x180011236  push    rbx
0x180011237  sub     rsp, 50h
0x18001123b  lea     rcx, [rax+8]
0x18001123f  mov     qword ptr [rax+8], 0
0x180011247  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001124c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180011255  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18001125c  mov     [rsp+58h+phkResult], rax; phkResult
0x180011261  xor     r9d, r9d; lpClass
0x180011264  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001126d  xor     r8d, r8d; Reserved
0x180011270  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180011278  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001127f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180011287  call    cs:__imp_RegCreateKeyExW
0x18001128d  mov     ebx, eax
0x18001128f  test    eax, eax
0x180011291  jz      short loc_1800112C1
0x180011293  jle     short loc_18001129E
0x180011295  movzx   ebx, ax
0x180011298  or      ebx, 80070000h
0x18001129e  mov     r9d, 102h
0x1800112a4  xor     edx, edx
0x1800112a6  mov     ecx, ebx
0x1800112a8  call    Log_HREvent_2
0x1800112ad  mov     rcx, [rsp+58h+hKey]; hKey
0x1800112b2  test    rcx, rcx
0x1800112b5  jz      short loc_1800112BD
0x1800112b7  call    cs:__imp_RegCloseKey
0x1800112bd  mov     eax, ebx
0x1800112bf  jmp     short loc_18001133D
0x1800112c1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800112c6  lea     rax, [rsp+58h+Data]
0x1800112cb  mov     r9d, 4; dwType
0x1800112d1  lea     rdx, aRebuildallinde; "RebuildAllIndexes"
0x1800112d8  mov     [rsp+58h+samDesired], r9d; cbData
0x1800112dd  xor     r8d, r8d; Reserved
0x1800112e0  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800112e5  call    cs:__imp_RegSetValueExW
0x1800112eb  mov     ebx, eax
0x1800112ed  test    eax, eax
0x1800112ef  jz      short loc_180011304
0x1800112f1  jle     short loc_1800112FC
0x1800112f3  movzx   ebx, ax
0x1800112f6  or      ebx, 80070000h
0x1800112fc  mov     r9d, 10Ch
0x180011302  jmp     short loc_1800112A4
0x180011304  mov     rcx, [rsp+58h+hKey]; hKey
0x180011309  call    cs:__imp_RegFlushKey
0x18001130f  mov     ebx, eax
0x180011311  test    eax, eax
0x180011313  jz      short loc_18001132B
0x180011315  jle     short loc_180011320
0x180011317  movzx   ebx, ax
0x18001131a  or      ebx, 80070000h
0x180011320  mov     r9d, 10Fh
0x180011326  jmp     loc_1800112A4
0x18001132b  mov     rcx, [rsp+58h+hKey]; hKey
0x180011330  test    rcx, rcx
0x180011333  jz      short loc_18001133B
0x180011335  call    cs:__imp_RegCloseKey
0x18001133b  xor     eax, eax
0x18001133d  add     rsp, 50h
0x180011341  pop     rbx
0x180011342  retn
```
