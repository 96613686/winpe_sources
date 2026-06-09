# CRegistry::SetCurrentKeyValue(HKEY__ *,ushort const *,CHString &)

- ea: `0x18001d058`
- end: `0x18001d0a9`
- name: `?SetCurrentKeyValue@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `81`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d0b0`

## callees

- `0x18001d058`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d09e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d09e`

## pseudocode

```c
LSTATUS __fastcall CRegistry::SetCurrentKeyValue(CRegistry *this, HKEY a2, const unsigned __int16 *a3, const BYTE **a4)
{
  const BYTE *lpData; // rcx
  char *v5; // rax

  lpData = *a4;
  v5 = byte_1800323B0;
  if ( *a4 != (const BYTE *)&dword_1800323BC )
    v5 = (char *)(lpData - 12);
  return RegSetValueExW(a2, a3, 0, 1u, lpData, 2 * *((_DWORD *)v5 + 1) + 2);
}

```

## disassembly

```asm
0x18001d058  sub     rsp, 38h
0x18001d05c  mov     rcx, [r9]
0x18001d05f  lea     rax, dword_1800323BC
0x18001d066  cmp     rcx, rax
0x18001d069  mov     r10, r8
0x18001d06c  lea     rax, byte_1800323B0
0x18001d073  mov     r11, rdx
0x18001d076  jz      short loc_18001D07C
0x18001d078  lea     rax, [rcx-0Ch]
0x18001d07c  mov     eax, [rax+4]
0x18001d07f  mov     r9d, 1; dwType
0x18001d085  xor     r8d, r8d; Reserved
0x18001d088  mov     rdx, r10; lpValueName
0x18001d08b  lea     eax, ds:2[rax*2]
0x18001d092  mov     [rsp+38h+cbData], eax; cbData
0x18001d096  mov     [rsp+38h+lpData], rcx; lpData
0x18001d09b  mov     rcx, r11; hKey
0x18001d09e  call    cs:__imp_RegSetValueExW
0x18001d0a4  add     rsp, 38h
0x18001d0a8  retn
```
