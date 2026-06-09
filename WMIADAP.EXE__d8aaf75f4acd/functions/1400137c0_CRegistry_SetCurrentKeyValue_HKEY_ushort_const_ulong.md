# CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,ulong &)

- ea: `0x1400137c0`
- end: `0x1400137ef`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAK@Z`
- size: `47`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400137e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400137e4`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValue(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const BYTE *lpData)
{
  return RegSetValueExW(a2, a3, 0, 4u, lpData, 4u);
}

```

## disassembly

```asm
0x1400137c0  sub     rsp, 38h
0x1400137c4  mov     ecx, 4
0x1400137c9  mov     rax, r8
0x1400137cc  mov     [rsp+38h+cbData], ecx; cbData
0x1400137d0  mov     r10, rdx
0x1400137d3  mov     [rsp+38h+lpData], r9; lpData
0x1400137d8  xor     r8d, r8d; Reserved
0x1400137db  mov     r9d, ecx; dwType
0x1400137de  mov     rdx, rax; lpValueName
0x1400137e1  mov     rcx, r10; hKey
0x1400137e4  call    cs:__imp_RegSetValueExW
0x1400137ea  add     rsp, 38h
0x1400137ee  retn
```
