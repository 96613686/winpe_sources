# ATL::CRegKey::SetDWORDValue(wchar_t const *,ulong)

- ea: `0x18000d7c0`
- end: `0x18000d7ee`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEB_WK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000b29c`
- `0x180032328`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d7e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d7e3`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const wchar_t *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x18000d7c0  mov     r11, rsp
0x18000d7c3  mov     [r11+18h], r8d
0x18000d7c7  sub     rsp, 38h
0x18000d7cb  mov     rcx, [rcx]; hKey
0x18000d7ce  lea     rax, [r11+18h]
0x18000d7d2  mov     r9d, 4; dwType
0x18000d7d8  xor     r8d, r8d; Reserved
0x18000d7db  mov     [r11-10h], r9d
0x18000d7df  mov     [r11-18h], rax
0x18000d7e3  call    cs:__imp_RegSetValueExW
0x18000d7e9  add     rsp, 38h
0x18000d7ed  retn
```
