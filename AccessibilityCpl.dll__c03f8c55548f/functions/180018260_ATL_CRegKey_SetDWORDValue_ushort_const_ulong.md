# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x180018260`
- end: `0x18001828e`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `13`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180016800`
- `0x180016d70`
- `0x180016ee4`
- `0x1800178c0`
- `0x18001d62c`
- `0x18001d6dc`
- `0x18001d978`
- `0x18001ddcc`
- `0x18001de80`
- `0x18001df2c`
- `0x180022724`
- `0x1800241b0`
- `0x180025a18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018283`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018283`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetDWORDValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = a3;
  return RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v4, 4u);
}

```

## disassembly

```asm
0x180018260  mov     r11, rsp
0x180018263  mov     [r11+18h], r8d
0x180018267  sub     rsp, 38h
0x18001826b  mov     rcx, [rcx]; hKey
0x18001826e  lea     rax, [r11+18h]
0x180018272  mov     r9d, 4; dwType
0x180018278  xor     r8d, r8d; Reserved
0x18001827b  mov     [r11-10h], r9d
0x18001827f  mov     [r11-18h], rax
0x180018283  call    cs:__imp_RegSetValueExW
0x180018289  add     rsp, 38h
0x18001828d  retn
```
