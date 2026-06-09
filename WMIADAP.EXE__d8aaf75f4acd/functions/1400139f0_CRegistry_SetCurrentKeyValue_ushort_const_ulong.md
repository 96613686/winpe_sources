# CRegistry::SetCurrentKeyValue(ushort const *,ulong &)

- ea: `0x1400139f0`
- end: `0x140013a16`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAK@Z`
- size: `38`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013a0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013a0b`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  return RegSetValueExW(this[1], a2, 0, 4u, lpData, 4u);
}

```

## disassembly

```asm
0x1400139f0  sub     rsp, 38h
0x1400139f4  mov     rcx, [rcx+8]; hKey
0x1400139f8  mov     r9d, 4; dwType
0x1400139fe  mov     [rsp+38h+cbData], r9d; cbData
0x140013a03  mov     [rsp+38h+lpData], r8; lpData
0x140013a08  xor     r8d, r8d; Reserved
0x140013a0b  call    cs:__imp_RegSetValueExW
0x140013a11  add     rsp, 38h
0x140013a15  retn
```
