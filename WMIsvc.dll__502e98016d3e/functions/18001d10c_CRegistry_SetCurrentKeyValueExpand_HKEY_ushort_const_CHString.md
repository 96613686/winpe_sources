# CRegistry::SetCurrentKeyValueExpand(HKEY__ *,ushort const *,CHString &)

- ea: `0x18001d10c`
- end: `0x18001d15d`
- name: `?SetCurrentKeyValueExpand@CRegistry@@QEAAKPEAUHKEY__@@PEBGAEAVCHString@@@Z`
- size: `81`
- prototype: `unsigned int(CRegistry *__hidden this, HKEY, const unsigned __int16 *, struct CHString *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001d0b0`

## callees

- `0x18001d10c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d152`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d152`

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
  v5 = byte_1800323B0;
  if ( *a4 != (const BYTE *)&dword_1800323BC )
    v5 = (char *)(lpData - 12);
  return RegSetValueExW(a2, a3, 0, 2u, lpData, 2 * *((_DWORD *)v5 + 1) + 2);
}

```

## disassembly

```asm
0x18001d10c  sub     rsp, 38h
0x18001d110  mov     rcx, [r9]
0x18001d113  lea     rax, dword_1800323BC
0x18001d11a  cmp     rcx, rax
0x18001d11d  mov     r10, r8
0x18001d120  lea     rax, byte_1800323B0
0x18001d127  mov     r11, rdx
0x18001d12a  jz      short loc_18001D130
0x18001d12c  lea     rax, [rcx-0Ch]
0x18001d130  mov     eax, [rax+4]
0x18001d133  mov     r9d, 2; dwType
0x18001d139  xor     r8d, r8d; Reserved
0x18001d13c  mov     rdx, r10; lpValueName
0x18001d13f  lea     eax, ds:2[rax*2]
0x18001d146  mov     [rsp+38h+cbData], eax; cbData
0x18001d14a  mov     [rsp+38h+lpData], rcx; lpData
0x18001d14f  mov     rcx, r11; hKey
0x18001d152  call    cs:__imp_RegSetValueExW
0x18001d158  add     rsp, 38h
0x18001d15c  retn
```
