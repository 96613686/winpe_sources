# ESEDataSource::_SetCorruptionKey(int)

- ea: `0x180012264`
- end: `0x18001237b`
- name: `?_SetCorruptionKey@ESEDataSource@@AEAAJH@Z`
- size: `279`
- prototype: `__int64 __fastcall(ESEDataSource *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ee40`
- `0x180011f70`

## callees

- `0x180003edc`
- `0x1800104b8`
- `0x180012264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001236d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800122ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001236d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800122bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800122bf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001231d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001231d`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180012341`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180012341`

## pseudocode

```c
__int64 __fastcall ESEDataSource::_SetCorruptionKey(ESEDataSource *this, int a2)
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
    v6 = 461;
LABEL_5:
    Log_HREvent_2(v5, 0, v4, v6);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v8 = RegSetValueExW(hKey, L"IndexesCorrupt", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v6 = 471;
    goto LABEL_5;
  }
  v9 = RegFlushKey(hKey);
  v5 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = 474;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180012264  mov     rax, rsp
0x180012267  mov     [rax+10h], edx
0x18001226a  mov     [rax+8], rcx
0x18001226e  push    rbx
0x18001226f  sub     rsp, 50h
0x180012273  lea     rcx, [rax+8]
0x180012277  mov     qword ptr [rax+8], 0
0x18001227f  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x180012284  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18001228d  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x180012294  mov     [rsp+58h+phkResult], rax; phkResult
0x180012299  xor     r9d, r9d; lpClass
0x18001229c  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800122a5  xor     r8d, r8d; Reserved
0x1800122a8  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800122b0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800122b7  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800122bf  call    cs:__imp_RegCreateKeyExW
0x1800122c5  mov     ebx, eax
0x1800122c7  test    eax, eax
0x1800122c9  jz      short loc_1800122F9
0x1800122cb  jle     short loc_1800122D6
0x1800122cd  movzx   ebx, ax
0x1800122d0  or      ebx, 80070000h
0x1800122d6  mov     r9d, 1CDh
0x1800122dc  xor     edx, edx
0x1800122de  mov     ecx, ebx
0x1800122e0  call    Log_HREvent_2
0x1800122e5  mov     rcx, [rsp+58h+hKey]; hKey
0x1800122ea  test    rcx, rcx
0x1800122ed  jz      short loc_1800122F5
0x1800122ef  call    cs:__imp_RegCloseKey
0x1800122f5  mov     eax, ebx
0x1800122f7  jmp     short loc_180012375
0x1800122f9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800122fe  lea     rax, [rsp+58h+Data]
0x180012303  mov     r9d, 4; dwType
0x180012309  lea     rdx, aIndexescorrupt; "IndexesCorrupt"
0x180012310  mov     [rsp+58h+samDesired], r9d; cbData
0x180012315  xor     r8d, r8d; Reserved
0x180012318  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18001231d  call    cs:__imp_RegSetValueExW
0x180012323  mov     ebx, eax
0x180012325  test    eax, eax
0x180012327  jz      short loc_18001233C
0x180012329  jle     short loc_180012334
0x18001232b  movzx   ebx, ax
0x18001232e  or      ebx, 80070000h
0x180012334  mov     r9d, 1D7h
0x18001233a  jmp     short loc_1800122DC
0x18001233c  mov     rcx, [rsp+58h+hKey]; hKey
0x180012341  call    cs:__imp_RegFlushKey
0x180012347  mov     ebx, eax
0x180012349  test    eax, eax
0x18001234b  jz      short loc_180012363
0x18001234d  jle     short loc_180012358
0x18001234f  movzx   ebx, ax
0x180012352  or      ebx, 80070000h
0x180012358  mov     r9d, 1DAh
0x18001235e  jmp     loc_1800122DC
0x180012363  mov     rcx, [rsp+58h+hKey]; hKey
0x180012368  test    rcx, rcx
0x18001236b  jz      short loc_180012373
0x18001236d  call    cs:__imp_RegCloseKey
0x180012373  xor     eax, eax
0x180012375  add     rsp, 50h
0x180012379  pop     rbx
0x18001237a  retn
```
