# CRegKeyWrapper::SetDWORDValue(ATL::CRegKey *,ushort const *,ulong)

- ea: `0x180016160`
- end: `0x180016197`
- name: `?SetDWORDValue@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEBGK@Z`
- size: `55`
- prototype: `int(CRegKeyWrapper *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001618c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001618c`

## pseudocode

```c
LSTATUS __fastcall CRegKeyWrapper::SetDWORDValue(CRegKeyWrapper *this, HKEY *a2, const unsigned __int16 *a3, int a4)
{
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  return RegSetValueExW(*a2, a3, 0, 4u, (const BYTE *)&v5, 4u);
}

```

## disassembly

```asm
0x180016160  mov     r11, rsp
0x180016163  sub     rsp, 38h
0x180016167  mov     r10, rdx
0x18001616a  mov     [r11+20h], r9d
0x18001616e  lea     rcx, [r11+20h]
0x180016172  mov     rax, r8
0x180016175  mov     r9d, 4; dwType
0x18001617b  xor     r8d, r8d; Reserved
0x18001617e  mov     [r11-10h], r9d
0x180016182  mov     rdx, rax; lpValueName
0x180016185  mov     [r11-18h], rcx
0x180016189  mov     rcx, [r10]; hKey
0x18001618c  call    cs:__imp_RegSetValueExW
0x180016192  add     rsp, 38h
0x180016196  retn
```
