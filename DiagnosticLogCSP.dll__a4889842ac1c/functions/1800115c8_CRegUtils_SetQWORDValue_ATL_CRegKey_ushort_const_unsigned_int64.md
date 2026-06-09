# CRegUtils::SetQWORDValue(ATL::CRegKey &,ushort const *,unsigned __int64)

- ea: `0x1800115c8`
- end: `0x18001161c`
- name: `?SetQWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG_K@Z`
- size: `84`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e374`
- `0x18000e4cc`

## callees

- `0x1800115c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800115fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800115fb`

## pseudocode

```c
__int64 __fastcall CRegUtils::SetQWORDValue(HKEY *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY v3; // rcx
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  const unsigned __int16 *lpData; // [rsp+48h] [rbp+10h] BYREF

  lpData = a2;
  v3 = *a1;
  v4 = 0;
  lpData = a3;
  v5 = RegSetValueExW(v3, L"Keywords", 0, 0xBu, (const BYTE *)&lpData, 8u);
  if ( v5 )
  {
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    else
      return (unsigned int)v5;
  }
  return v4;
}

```

## disassembly

```asm
0x1800115c8  mov     rax, rsp
0x1800115cb  mov     [rax+10h], rdx
0x1800115cf  push    rbx
0x1800115d0  sub     rsp, 30h
0x1800115d4  mov     rcx, [rcx]; hKey
0x1800115d7  xor     ebx, ebx
0x1800115d9  mov     [rax+10h], r8
0x1800115dd  xor     r8d, r8d; Reserved
0x1800115e0  mov     dword ptr [rax-10h], 8
0x1800115e7  lea     rax, [rax+10h]
0x1800115eb  lea     rdx, aKeywords; "Keywords"
0x1800115f2  mov     [rsp+38h+lpData], rax; lpData
0x1800115f7  lea     r9d, [rbx+0Bh]; dwType
0x1800115fb  call    cs:__imp_RegSetValueExW
0x180011601  test    eax, eax
0x180011603  jz      short loc_180011614
0x180011605  jg      short loc_18001160B
0x180011607  mov     ebx, eax
0x180011609  jmp     short loc_180011614
0x18001160b  movzx   ebx, ax
0x18001160e  or      ebx, 80070000h
0x180011614  mov     eax, ebx
0x180011616  add     rsp, 30h
0x18001161a  pop     rbx
0x18001161b  retn
```
