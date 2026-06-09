# PimIMService::WriteTrackedStoresToRegistry(utl::vector<ulong,utl::allocator<ulong>> const &)

- ea: `0x18000b33c`
- end: `0x18000b473`
- name: `?WriteTrackedStoresToRegistry@PimIMService@@QEAAJAEBV?$vector@KV?$allocator@K@utl@@@utl@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004c14`
- `0x1800058d0`

## callees

- `0x180002da8`
- `0x180003edc`
- `0x18000a998`
- `0x18000b33c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b460`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b460`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b39b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000b39b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b434`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b434`

## string_xrefs

- `0x18000b3ba`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::WriteTrackedStoresToRegistry(__int64 a1, _QWORD *a2)
{
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v9; // rcx
  const BYTE *v10; // r9
  LSTATUS v11; // eax
  __int64 cbData; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  cbData = a1;
  hKey = 0;
  phkResult = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(&hKey);
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Poom\\Indexing", 0, 0, 0, 2u, 0, phkResult, 0);
  v5 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v5 = (unsigned __int16)Key | 0x80070000;
    v6 = 1139;
LABEL_5:
    v7 = 0;
LABEL_6:
    Log_HREvent(
      v5,
      v7,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v6);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v9 = a2[1] - *a2;
  LODWORD(cbData) = 0;
  v5 = ULongLongToULong(v9 & 0xFFFFFFFFFFFFFFFCuLL, (unsigned int *)&cbData);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 1142;
    v7 = 1;
    goto LABEL_6;
  }
  v11 = RegSetValueExW(hKey, L"TrackedStores", 0, 3u, v10, cbData);
  v5 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    v6 = 1153;
    goto LABEL_5;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18000b33c  mov     rax, rsp
0x18000b33f  mov     [rax+10h], rbx
0x18000b343  mov     [rax+8], rcx
0x18000b347  push    rdi
0x18000b348  sub     rsp, 50h
0x18000b34c  lea     rcx, [rax+18h]
0x18000b350  mov     qword ptr [rax+18h], 0
0x18000b358  mov     rdi, rdx
0x18000b35b  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18000b360  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x18000b369  lea     rdx, SubKey; "Software\\Microsoft\\Poom\\Indexing"
0x18000b370  mov     [rsp+58h+phkResult], rax; phkResult
0x18000b375  xor     r9d, r9d; lpClass
0x18000b378  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000b381  xor     r8d, r8d; Reserved
0x18000b384  mov     [rsp+58h+samDesired], 2; samDesired
0x18000b38c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000b393  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000b39b  call    cs:__imp_RegCreateKeyExW
0x18000b3a1  mov     ebx, eax
0x18000b3a3  test    eax, eax
0x18000b3a5  jz      short loc_18000B3DF
0x18000b3a7  jle     short loc_18000B3B2
0x18000b3a9  movzx   ebx, ax
0x18000b3ac  or      ebx, 80070000h
0x18000b3b2  mov     r9d, 473h
0x18000b3b8  xor     edx, edx
0x18000b3ba  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b3c1  mov     ecx, ebx
0x18000b3c3  call    Log_HREvent
0x18000b3c8  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b3cd  test    rcx, rcx
0x18000b3d0  jz      short loc_18000B3D8
0x18000b3d2  call    cs:__imp_RegCloseKey
0x18000b3d8  mov     eax, ebx
0x18000b3da  jmp     loc_18000B468
0x18000b3df  mov     r9, [rdi]
0x18000b3e2  lea     rdx, [rsp+58h+cbData]; unsigned int *
0x18000b3e7  mov     rcx, [rdi+8]
0x18000b3eb  sub     rcx, r9
0x18000b3ee  mov     dword ptr [rsp+58h+cbData], 0
0x18000b3f6  and     rcx, 0FFFFFFFFFFFFFFFCh; unsigned __int64
0x18000b3fa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000b3ff  mov     ebx, eax
0x18000b401  test    eax, eax
0x18000b403  jns     short loc_18000B412
0x18000b405  mov     r9d, 476h
0x18000b40b  mov     edx, 1
0x18000b410  jmp     short loc_18000B3BA
0x18000b412  mov     eax, dword ptr [rsp+58h+cbData]
0x18000b416  lea     rdx, aTrackedstores; "TrackedStores"
0x18000b41d  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b422  xor     r8d, r8d; Reserved
0x18000b425  mov     [rsp+58h+samDesired], eax; cbData
0x18000b429  mov     qword ptr [rsp+58h+dwOptions], r9; lpData
0x18000b42e  mov     r9d, 3; dwType
0x18000b434  call    cs:__imp_RegSetValueExW
0x18000b43a  mov     ebx, eax
0x18000b43c  test    eax, eax
0x18000b43e  jz      short loc_18000B456
0x18000b440  jle     short loc_18000B44B
0x18000b442  movzx   ebx, ax
0x18000b445  or      ebx, 80070000h
0x18000b44b  mov     r9d, 481h
0x18000b451  jmp     loc_18000B3B8
0x18000b456  mov     rcx, [rsp+58h+hKey]; hKey
0x18000b45b  test    rcx, rcx
0x18000b45e  jz      short loc_18000B466
0x18000b460  call    cs:__imp_RegCloseKey
0x18000b466  xor     eax, eax
0x18000b468  mov     rbx, [rsp+58h+arg_8]
0x18000b46d  add     rsp, 50h
0x18000b471  pop     rdi
0x18000b472  retn
```
