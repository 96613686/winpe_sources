# CRegistry::SetCurrentKeyValueExpand(HKEY__ *,ushort const *,CHString &)

- ea: `0x140013aa0`
- end: `0x140013aee`
- name: `?SetCurrentKeyValueExpand@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `78`
- prototype: `LSTATUS __fastcall(CRegistry *this, HKEY, const unsigned __int16 *, const BYTE **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140013a20`

## callees

- `0x140013aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ae3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140013ae3`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValueExpand(
        CRegistry *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const BYTE **a4)
{
  const BYTE *lpData; // rcx
  char *v5; // rax

  lpData = *a4;
  v5 = byte_140024890;
  if ( *a4 != (const BYTE *)afxPchNil )
    v5 = (char *)(lpData - 12);
  return RegSetValueExW(a2, a3, 0, 2u, lpData, 2 * *((_DWORD *)v5 + 1) + 2);
}

```

## disassembly

```asm
0x140013aa0  sub     rsp, 38h
0x140013aa4  mov     rcx, [r9]
0x140013aa7  lea     rax, byte_140024890
0x140013aae  cmp     rcx, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013ab5  mov     r10, r8
0x140013ab8  mov     r11, rdx
0x140013abb  jz      short loc_140013AC1
0x140013abd  lea     rax, [rcx-0Ch]
0x140013ac1  mov     eax, [rax+4]
0x140013ac4  mov     r9d, 2; dwType
0x140013aca  xor     r8d, r8d; Reserved
0x140013acd  mov     rdx, r10; lpValueName
0x140013ad0  lea     eax, ds:2[rax*2]
0x140013ad7  mov     [rsp+38h+cbData], eax; cbData
0x140013adb  mov     [rsp+38h+lpData], rcx; lpData
0x140013ae0  mov     rcx, r11; hKey
0x140013ae3  call    cs:__imp_RegSetValueExW
0x140013ae9  add     rsp, 38h
0x140013aed  retn
```
