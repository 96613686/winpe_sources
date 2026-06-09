# ATL::CRegKey::SetDWORDValue(ushort const *,ulong)

- ea: `0x180037100`
- end: `0x18003712e`
- name: `?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180007c40`
- `0x18003415c`
- `0x18003c92c`
- `0x180060d14`
- `0x180060f8c`
- `0x18006253c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037123`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037123`

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
0x180037100  mov     r11, rsp
0x180037103  mov     [r11+18h], r8d
0x180037107  sub     rsp, 38h
0x18003710b  mov     rcx, [rcx]; hKey
0x18003710e  lea     rax, [r11+18h]
0x180037112  mov     r9d, 4; dwType
0x180037118  xor     r8d, r8d; Reserved
0x18003711b  mov     [r11-10h], r9d
0x18003711f  mov     [r11-18h], rax
0x180037123  call    cs:__imp_RegSetValueExW
0x180037129  add     rsp, 38h
0x18003712d  retn
```
