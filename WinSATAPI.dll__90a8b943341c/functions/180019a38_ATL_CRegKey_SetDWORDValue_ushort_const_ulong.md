# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x180019a38`
- end: `0x180019a6d`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `53`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180014f74`
- `0x18001f264`
- `0x180021d84`
- `0x18002d4dc`
- `0x18002d76c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a5b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019a5b`

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
0x180019a38  mov     r11, rsp
0x180019a3b  mov     [r11+18h], r8d
0x180019a3f  sub     rsp, 38h
0x180019a43  mov     rcx, [rcx]; hKey
0x180019a46  lea     rax, [r11+18h]
0x180019a4a  mov     r9d, 4; dwType
0x180019a50  xor     r8d, r8d; Reserved
0x180019a53  mov     [r11-10h], r9d
0x180019a57  mov     [r11-18h], rax
0x180019a5b  call    cs:__imp_RegSetValueExW
0x180019a62  nop     dword ptr [rax+rax+00h]
0x180019a67  add     rsp, 38h
0x180019a6b  retn
```
