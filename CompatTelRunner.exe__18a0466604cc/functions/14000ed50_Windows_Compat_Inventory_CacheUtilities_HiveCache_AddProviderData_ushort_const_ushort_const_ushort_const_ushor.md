# Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x14000ed50`
- end: `0x14000edd2`
- name: `?AddProviderData@HiveCache@CacheUtilities@Inventory@Compat@Windows@@UEAAJPEBG000@Z`
- size: `130`
- prototype: `LSTATUS __fastcall(Windows::Compat::Inventory::CacheUtilities::HiveCache *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, BYTE *lpData)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000ed50`
- `0x140010098`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000edb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000edb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000eda5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000eda5`

## pseudocode

```c
LSTATUS __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::AddProviderData(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        BYTE *lpData)
{
  LSTATUS result; // eax
  __int64 v7; // rax
  LSTATUS v8; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  result = Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(this, a2, a3, &hKey);
  if ( result >= 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&lpData[2 * v7] );
    v8 = RegSetValueExW(hKey, a4, 0, 1u, lpData, 2 * v7 + 2);
    RegCloseKey(hKey);
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x14000ed50  mov     [rsp+arg_0], rbx
0x14000ed55  push    rdi
0x14000ed56  sub     rsp, 40h
0x14000ed5a  mov     rbx, r9
0x14000ed5d  xor     edi, edi
0x14000ed5f  lea     r9, [rsp+48h+hKey]; HKEY *
0x14000ed64  mov     [rsp+48h+hKey], rdi
0x14000ed69  call    ?GetItemKey@HiveCache@CacheUtilities@Inventory@Compat@Windows@@AEAAJPEBG0AEAPEAUHKEY__@@@Z; Windows::Compat::Inventory::CacheUtilities::HiveCache::GetItemKey(ushort const *,ushort const *,HKEY__ * &)
0x14000ed6e  test    eax, eax
0x14000ed70  js      short loc_14000EDC7
0x14000ed72  mov     rcx, [rsp+48h+arg_20]
0x14000ed77  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ed7b  inc     rax
0x14000ed7e  cmp     [rcx+rax*2], di
0x14000ed82  jnz     short loc_14000ED7B
0x14000ed84  lea     eax, ds:2[rax*2]
0x14000ed8b  mov     r9d, 1; dwType
0x14000ed91  mov     [rsp+48h+cbData], eax; cbData
0x14000ed95  xor     r8d, r8d; Reserved
0x14000ed98  mov     [rsp+48h+lpData], rcx; lpData
0x14000ed9d  mov     rdx, rbx; lpValueName
0x14000eda0  mov     rcx, [rsp+48h+hKey]; hKey
0x14000eda5  call    cs:__imp_RegSetValueExW
0x14000edab  mov     rcx, [rsp+48h+hKey]; hKey
0x14000edb0  mov     ebx, eax
0x14000edb2  call    cs:__imp_RegCloseKey
0x14000edb8  test    ebx, ebx
0x14000edba  jle     short loc_14000EDC5
0x14000edbc  movzx   ebx, bx
0x14000edbf  or      ebx, 80070000h
0x14000edc5  mov     eax, ebx
0x14000edc7  mov     rbx, [rsp+48h+arg_0]
0x14000edcc  add     rsp, 40h
0x14000edd0  pop     rdi
0x14000edd1  retn
```
