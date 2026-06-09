# CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)

- ea: `0x140013800`
- end: `0x14001384e`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `78`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, const BYTE **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013a20`

## callees

- `0x140013800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013843`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013843`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValue(CRegistry *this, HKEY a2, const unsigned __int16 *a3, const BYTE **a4)
{
  const BYTE *lpData; // rcx
  char *v5; // rax

  lpData = *a4;
  v5 = byte_140024890;
  if ( *a4 != (const BYTE *)afxPchNil )
    v5 = (char *)(lpData - 12);
  return RegSetValueExW(a2, a3, 0, 1u, lpData, 2 * *((_DWORD *)v5 + 1) + 2);
}

```

## disassembly

```asm
0x140013800  sub     rsp, 38h
0x140013804  mov     rcx, [r9]
0x140013807  lea     rax, byte_140024890
0x14001380e  cmp     rcx, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013815  mov     r10, r8
0x140013818  mov     r11, rdx
0x14001381b  jz      short loc_140013821
0x14001381d  lea     rax, [rcx-0Ch]
0x140013821  mov     eax, [rax+4]
0x140013824  mov     r9d, 1; dwType
0x14001382a  xor     r8d, r8d; Reserved
0x14001382d  mov     rdx, r10; lpValueName
0x140013830  lea     eax, ds:2[rax*2]
0x140013837  mov     [rsp+38h+cbData], eax; cbData
0x14001383b  mov     [rsp+38h+lpData], rcx; lpData
0x140013840  mov     rcx, r11; hKey
0x140013843  call    cs:__imp_RegSetValueExW
0x140013849  add     rsp, 38h
0x14001384d  retn
```
