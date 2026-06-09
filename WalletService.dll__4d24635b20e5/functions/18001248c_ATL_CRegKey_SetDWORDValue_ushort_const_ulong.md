# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x18001248c`
- end: `0x1800124ba`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180011f20`
- `0x180017b88`
- `0x1800265ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800124af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800124af`

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
0x18001248c  mov     r11, rsp
0x18001248f  mov     [r11+18h], r8d
0x180012493  sub     rsp, 38h
0x180012497  mov     rcx, [rcx]; hKey
0x18001249a  lea     rax, [r11+18h]
0x18001249e  mov     r9d, 4; dwType
0x1800124a4  xor     r8d, r8d; Reserved
0x1800124a7  mov     [r11-10h], r9d
0x1800124ab  mov     [r11-18h], rax
0x1800124af  call    cs:__imp_RegSetValueExW
0x1800124b5  add     rsp, 38h
0x1800124b9  retn
```
