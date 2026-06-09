# CRegUtils::SetStringValue(ATL::CRegKey &,ushort const *,ushort const *)

- ea: `0x180011624`
- end: `0x18001169e`
- name: `?SetStringValue@CRegUtils@@SAJAEAVCRegKey@ATL@@PEBG1@Z`
- size: `122`
- prototype: `static int(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e158`
- `0x18000e374`
- `0x18000f580`
- `0x18000f6fc`
- `0x180013500`

## callees

- `0x180010db8`
- `0x180011624`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001166d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001166d`

## pseudocode

```c
__int64 __fastcall CRegUtils::SetStringValue(HKEY *a1, const unsigned __int16 *a2, const BYTE *lpData)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  LSTATUS v5; // eax

  if ( a2 )
  {
    if ( !lpData )
      ATL::AtlThrowImpl(-2147467259);
    v3 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&lpData[2 * v4] );
    v5 = RegSetValueExW(*a1, a2, 0, 1u, lpData, 2 * v4 + 2);
    if ( v5 )
    {
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
      else
        return (unsigned int)v5;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180011624  mov     [rsp+arg_0], rbx
0x180011629  push    rdi
0x18001162a  sub     rsp, 30h
0x18001162e  xor     edi, edi
0x180011630  test    rdx, rdx
0x180011633  jnz     short loc_18001163C
0x180011635  mov     ebx, 80070057h
0x18001163a  jmp     short loc_180011686
0x18001163c  test    r8, r8
0x18001163f  jz      short loc_180011693
0x180011641  mov     ebx, edi
0x180011643  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011647  inc     rax
0x18001164a  cmp     [r8+rax*2], di
0x18001164f  jnz     short loc_180011647
0x180011651  mov     rcx, [rcx]; hKey
0x180011654  lea     eax, ds:2[rax*2]
0x18001165b  mov     [rsp+38h+cbData], eax; cbData
0x18001165f  mov     r9d, 1; dwType
0x180011665  mov     [rsp+38h+lpData], r8; lpData
0x18001166a  xor     r8d, r8d; Reserved
0x18001166d  call    cs:__imp_RegSetValueExW
0x180011673  test    eax, eax
0x180011675  jz      short loc_180011686
0x180011677  jg      short loc_18001167D
0x180011679  mov     ebx, eax
0x18001167b  jmp     short loc_180011686
0x18001167d  movzx   ebx, ax
0x180011680  or      ebx, 80070000h
0x180011686  mov     eax, ebx
0x180011688  mov     rbx, [rsp+38h+arg_0]
0x18001168d  add     rsp, 30h
0x180011691  pop     rdi
0x180011692  retn
0x180011693  mov     ecx, 80004005h; int
0x180011698  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
