# Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessInventoryProviderData(HKEY__ *,ushort const *,_iobuf *)

- ea: `0x1400108cc`
- end: `0x140010a97`
- name: `?ProcessInventoryProviderData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@SAXPEAUHKEY__@@PEBGPEAU_iobuf@@@Z`
- size: `459`
- prototype: `void __fastcall(HKEY hKey, LPCWSTR lpSubKey, FILE *Stream)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000de8c`
- `0x14000f4e0`

## callees

- `0x140001ba0`
- `0x1400026d8`
- `0x1400108cc`
- `0x140010aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400109fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010a6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400109fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010a6f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140010a43`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140010a43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010931`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400109c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010931`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400109c4`

## string_xrefs

- `0x1400109d6`: `RegOpenKeyEx failed for (%ls) %d \n`
- `0x14001093e`: `RegOpenKeyEx failed: (%ls) %d \n`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessInventoryProviderData(
        HKEY hKey,
        LPCWSTR lpSubKey,
        FILE *Stream)
{
  unsigned int v6; // eax
  DWORD v7; // esi
  DWORD i; // edx
  HKEY v9; // rbx
  unsigned int v10; // eax
  unsigned int v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKeya = 0;
  fwprintf(Stream, L"Provider name: %ls \n", lpSubKey);
  v6 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
  if ( v6 )
  {
    fwprintf(Stream, L"RegOpenKeyEx failed: (%ls) %d \n", lpSubKey, v6);
  }
  else
  {
    v7 = 0;
    Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(hKeya, Stream);
    for ( i = 0; ; i = v7 )
    {
      cchName = 260;
      v11 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
      if ( v11 == 259 )
        break;
      if ( v11 )
      {
        fwprintf(Stream, L"RegEnumKeyEx failed: %d \n", v11);
        break;
      }
      v9 = hKeya;
      hkey = 0;
      fwprintf(Stream, L"\n\t%ls \n", SubKey);
      v10 = RegOpenKeyExW(v9, SubKey, 0, 0x20019u, &hkey);
      if ( v10 )
        fwprintf(Stream, L"RegOpenKeyEx failed for (%ls) %d \n", SubKey, v10);
      else
        Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(hkey, Stream);
      if ( hkey )
        RegCloseKey(hkey);
      ++v7;
    }
  }
  if ( hKeya )
    RegCloseKey(hKeya);
}

```

## disassembly

```asm
0x1400108cc  mov     [rsp-8+arg_18], rbx
0x1400108d1  push    rbp
0x1400108d2  push    rsi
0x1400108d3  push    rdi
0x1400108d4  lea     rbp, [rsp-180h]
0x1400108dc  sub     rsp, 280h
0x1400108e3  mov     rax, cs:__security_cookie
0x1400108ea  xor     rax, rsp
0x1400108ed  mov     [rbp+190h+var_20], rax
0x1400108f4  mov     rdi, r8
0x1400108f7  mov     [rsp+290h+hKey], 0
0x140010900  mov     r8, rdx
0x140010903  mov     rsi, rdx
0x140010906  mov     rbx, rcx
0x140010909  lea     rdx, aProviderNameLs; "Provider name: %ls \n"
0x140010910  mov     rcx, rdi; Stream
0x140010913  call    fwprintf
0x140010918  lea     rax, [rsp+290h+hKey]
0x14001091d  mov     r9d, 20019h; samDesired
0x140010923  xor     r8d, r8d; ulOptions
0x140010926  mov     [rsp+290h+phkResult], rax; phkResult
0x14001092b  mov     rdx, rsi; lpSubKey
0x14001092e  mov     rcx, rbx; hKey
0x140010931  call    cs:__imp_RegOpenKeyExW
0x140010937  test    eax, eax
0x140010939  jz      short loc_140010955
0x14001093b  mov     r9d, eax
0x14001093e  lea     rdx, aRegopenkeyexFa_1; "RegOpenKeyEx failed: (%ls) %d \n"
0x140010945  mov     r8, rsi
0x140010948  mov     rcx, rdi; Stream
0x14001094b  call    fwprintf
0x140010950  jmp     loc_140010A65
0x140010955  mov     rcx, [rsp+290h+hKey]; hkey
0x14001095a  mov     rdx, rdi; Stream
0x14001095d  xor     esi, esi
0x14001095f  call    ?ProcessKeyData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@CAXPEAUHKEY__@@PEAU_iobuf@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(HKEY__ *,_iobuf *)
0x140010964  mov     [rsp+290h+lpftLastWriteTime], rsi
0x140010969  xor     edx, edx
0x14001096b  mov     [rsp+290h+lpcchClass], rsi
0x140010970  mov     [rsp+290h+lpClass], rsi
0x140010975  mov     [rsp+290h+phkResult], rsi
0x14001097a  jmp     loc_140010A2C
0x14001097f  mov     rcx, rdi; Stream
0x140010982  test    eax, eax
0x140010984  jnz     loc_140010A56
0x14001098a  mov     rbx, [rsp+290h+hKey]
0x14001098f  lea     r8, [rsp+290h+SubKey]
0x140010994  lea     rdx, aLs_0; "\n\t%ls \n"
0x14001099b  mov     [rsp+290h+hkey], 0
0x1400109a4  call    fwprintf
0x1400109a9  lea     rax, [rsp+290h+hkey]
0x1400109ae  mov     r9d, 20019h; samDesired
0x1400109b4  xor     r8d, r8d; ulOptions
0x1400109b7  mov     [rsp+290h+phkResult], rax; phkResult
0x1400109bc  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x1400109c1  mov     rcx, rbx; hKey
0x1400109c4  call    cs:__imp_RegOpenKeyExW
0x1400109ca  test    eax, eax
0x1400109cc  jz      short loc_1400109E7
0x1400109ce  mov     r9d, eax
0x1400109d1  lea     r8, [rsp+290h+SubKey]
0x1400109d6  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed for (%ls) %d \n"
0x1400109dd  mov     rcx, rdi; Stream
0x1400109e0  call    fwprintf
0x1400109e5  jmp     short loc_1400109F4
0x1400109e7  mov     rcx, [rsp+290h+hkey]; hkey
0x1400109ec  mov     rdx, rdi; Stream
0x1400109ef  call    ?ProcessKeyData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@CAXPEAUHKEY__@@PEAU_iobuf@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::ProcessKeyData(HKEY__ *,_iobuf *)
0x1400109f4  mov     rcx, [rsp+290h+hkey]; hKey
0x1400109f9  test    rcx, rcx
0x1400109fc  jz      short loc_140010A04
0x1400109fe  call    cs:__imp_RegCloseKey
0x140010a04  mov     [rsp+290h+lpftLastWriteTime], 0; lpftLastWriteTime
0x140010a0d  inc     esi
0x140010a0f  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x140010a18  mov     edx, esi; dwIndex
0x140010a1a  mov     [rsp+290h+lpClass], 0; lpClass
0x140010a23  mov     [rsp+290h+phkResult], 0; lpReserved
0x140010a2c  mov     rcx, [rsp+290h+hKey]; hKey
0x140010a31  lea     r9, [rsp+290h+cchName]; lpcchName
0x140010a36  lea     r8, [rsp+290h+SubKey]; lpName
0x140010a3b  mov     [rsp+290h+cchName], 104h
0x140010a43  call    cs:__imp_RegEnumKeyExW
0x140010a49  cmp     eax, 103h
0x140010a4e  jnz     loc_14001097F
0x140010a54  jmp     short loc_140010A65
0x140010a56  mov     r8d, eax
0x140010a59  lea     rdx, aRegenumkeyexFa_0; "RegEnumKeyEx failed: %d \n"
0x140010a60  call    fwprintf
0x140010a65  mov     rcx, [rsp+290h+hKey]; hKey
0x140010a6a  test    rcx, rcx
0x140010a6d  jz      short loc_140010A75
0x140010a6f  call    cs:__imp_RegCloseKey
0x140010a75  mov     rcx, [rbp+190h+var_20]
0x140010a7c  xor     rcx, rsp; StackCookie
0x140010a7f  call    __security_check_cookie
0x140010a84  mov     rbx, [rsp+290h+arg_18]
0x140010a8c  add     rsp, 280h
0x140010a93  pop     rdi
0x140010a94  pop     rsi
0x140010a95  pop     rbp
0x140010a96  retn
```
