# ESEDataSource::SetRebuildUnicodeIndexesKey(int)

- ea: `0x18001134c`
- end: `0x180011463`
- name: `?SetRebuildUnicodeIndexesKey@ESEDataSource@@QEAAJH@Z`
- size: `279`
- prototype: `__int64 __fastcall(ESEDataSource *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011f70`
- `0x180018630`

## callees

- `0x180003edc`
- `0x1800104b8`
- `0x18001134c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011455`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800113a7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011405`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011405`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011429`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180011429`

## pseudocode

```c
__int64 __fastcall ESEDataSource::SetRebuildUnicodeIndexesKey(ESEDataSource *this, int a2)
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
    v6 = 336;
LABEL_5:
    Log_HREvent_2(v5, 0, v4, v6);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v8 = RegSetValueExW(hKey, L"RebuildUnicodeIndexes", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = 346;
    goto LABEL_5;
  }
  v9 = RegFlushKey(hKey);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = 349;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001134c  mov     rax, rsp
0x18001134f  mov     [rax+10h], edx
0x180011352  mov     [rax+8], rcx
0x180011356  push    rbx
0x180011357  sub     rsp, 50h
0x18001135b  lea     rcx, [rax+8]
0x18001135f  mov     qword ptr [rax+8], 0
0x180011367  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001136c  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180011375  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18001137c  mov     [rsp+58h+phkResult], rax; phkResult
0x180011381  xor     r9d, r9d; lpClass
0x180011384  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001138d  xor     r8d, r8d; Reserved
0x180011390  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180011398  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001139f  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800113a7  call    cs:__imp_RegCreateKeyExW
0x1800113ad  mov     ebx, eax
0x1800113af  test    eax, eax
0x1800113b1  jz      short loc_1800113E1
0x1800113b3  jle     short loc_1800113BE
0x1800113b5  movzx   ebx, ax
0x1800113b8  or      ebx, 80070000h
0x1800113be  mov     r9d, 150h
0x1800113c4  xor     edx, edx
0x1800113c6  mov     ecx, ebx
0x1800113c8  call    Log_HREvent_2
0x1800113cd  mov     rcx, [rsp+58h+hKey]; hKey
0x1800113d2  test    rcx, rcx
0x1800113d5  jz      short loc_1800113DD
0x1800113d7  call    cs:__imp_RegCloseKey
0x1800113dd  mov     eax, ebx
0x1800113df  jmp     short loc_18001145D
0x1800113e1  mov     rcx, [rsp+58h+hKey]; hKey
0x1800113e6  lea     rax, [rsp+58h+Data]
0x1800113eb  mov     r9d, 4; dwType
0x1800113f1  lea     rdx, aRebuildunicode; "RebuildUnicodeIndexes"
0x1800113f8  mov     [rsp+58h+samDesired], r9d; cbData
0x1800113fd  xor     r8d, r8d; Reserved
0x180011400  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180011405  call    cs:__imp_RegSetValueExW
0x18001140b  mov     ebx, eax
0x18001140d  test    eax, eax
0x18001140f  jz      short loc_180011424
0x180011411  jle     short loc_18001141C
0x180011413  movzx   ebx, ax
0x180011416  or      ebx, 80070000h
0x18001141c  mov     r9d, 15Ah
0x180011422  jmp     short loc_1800113C4
0x180011424  mov     rcx, [rsp+58h+hKey]; hKey
0x180011429  call    cs:__imp_RegFlushKey
0x18001142f  mov     ebx, eax
0x180011431  test    eax, eax
0x180011433  jz      short loc_18001144B
0x180011435  jle     short loc_180011440
0x180011437  movzx   ebx, ax
0x18001143a  or      ebx, 80070000h
0x180011440  mov     r9d, 15Dh
0x180011446  jmp     loc_1800113C4
0x18001144b  mov     rcx, [rsp+58h+hKey]; hKey
0x180011450  test    rcx, rcx
0x180011453  jz      short loc_18001145B
0x180011455  call    cs:__imp_RegCloseKey
0x18001145b  xor     eax, eax
0x18001145d  add     rsp, 50h
0x180011461  pop     rbx
0x180011462  retn
```
