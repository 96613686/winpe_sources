# RegistryKey::TrySetNumber(wchar_t const *,uint)

- ea: `0x1800b8a48`
- end: `0x1800b8a82`
- name: `?TrySetNumber@RegistryKey@@QEBA_NPEB_WI@Z`
- size: `58`
- prototype: `bool __fastcall(RegistryKey *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800b13a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b8a72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b8a72`

## string_xrefs

- `0x1800b8a60`: `FileCacheSize`

## pseudocode

```c
bool __fastcall RegistryKey::TrySetNumber(HKEY *this, const wchar_t *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, L"FileCacheSize", 0, 4u, (const BYTE *)&v4, 4u) == 0;
}

```

## disassembly

```asm
0x1800b8a48  mov     r11, rsp
0x1800b8a4b  mov     [r11+18h], r8d
0x1800b8a4f  sub     rsp, 38h
0x1800b8a53  mov     rcx, [rcx]; hKey
0x1800b8a56  lea     rax, [r11+18h]
0x1800b8a5a  mov     r9d, 4; dwType
0x1800b8a60  lea     rdx, ?CacheSizeValueName@FileCache@@2QB_WB; "FileCacheSize"
0x1800b8a67  mov     [r11-10h], r9d
0x1800b8a6b  xor     r8d, r8d; Reserved
0x1800b8a6e  mov     [r11-18h], rax
0x1800b8a72  call    cs:__imp_RegSetValueExW
0x1800b8a78  test    eax, eax
0x1800b8a7a  setz    al
0x1800b8a7d  add     rsp, 38h
0x1800b8a81  retn
```
