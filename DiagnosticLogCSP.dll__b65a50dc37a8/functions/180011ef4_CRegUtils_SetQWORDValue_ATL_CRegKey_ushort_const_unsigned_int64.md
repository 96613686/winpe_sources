# CRegUtils::SetQWORDValue(ATL::CRegKey &,ushort const *,unsigned __int64)

- ea: `0x180011ef4`
- end: `0x180011f4f`
- name: `?SetQWORDValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ea88`
- `0x18000ebe8`

## callees

- `0x180011ef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011f27`

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
0x180011ef4  mov     rax, rsp
0x180011ef7  mov     [rax+10h], rdx
0x180011efb  push    rbx
0x180011efc  sub     rsp, 30h
0x180011f00  mov     rcx, [rcx]; hKey
0x180011f03  xor     ebx, ebx
0x180011f05  mov     [rax+10h], r8
0x180011f09  xor     r8d, r8d; Reserved
0x180011f0c  mov     dword ptr [rax-10h], 8
0x180011f13  lea     rax, [rax+10h]
0x180011f17  lea     rdx, aKeywords; "Keywords"
0x180011f1e  mov     [rsp+38h+lpData], rax; lpData
0x180011f23  lea     r9d, [rbx+0Bh]; dwType
0x180011f27  call    cs:__imp_RegSetValueExW
0x180011f2e  nop     dword ptr [rax+rax+00h]
0x180011f33  test    eax, eax
0x180011f35  jz      short loc_180011F46
0x180011f37  jg      short loc_180011F3D
0x180011f39  mov     ebx, eax
0x180011f3b  jmp     short loc_180011F46
0x180011f3d  movzx   ebx, ax
0x180011f40  or      ebx, 80070000h
0x180011f46  mov     eax, ebx
0x180011f48  add     rsp, 30h
0x180011f4c  pop     rbx
0x180011f4d  retn
```
