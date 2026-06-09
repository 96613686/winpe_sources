# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x18002415c`
- end: `0x1800241a8`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021a30`
- `0x1800229ec`
- `0x180023bc0`
- `0x18002486c`
- `0x1800250c8`
- `0x1800251dc`
- `0x180025a18`

## callees

- `0x18000546c`
- `0x18002415c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002419d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002419d`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&lpData[2 * v3] );
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x18002415c  sub     rsp, 38h
0x180024160  xor     r9d, r9d
0x180024163  test    r8, r8
0x180024166  jnz     short loc_180024173
0x180024168  mov     ecx, 80004005h; int
0x18002416d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024173  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024177  inc     rax
0x18002417a  cmp     [r8+rax*2], r9w
0x18002417f  jnz     short loc_180024177
0x180024181  mov     rcx, [rcx]; hKey
0x180024184  lea     eax, ds:2[rax*2]
0x18002418b  mov     [rsp+38h+cbData], eax; cbData
0x18002418f  mov     r9d, 1; dwType
0x180024195  mov     [rsp+38h+lpData], r8; lpData
0x18002419a  xor     r8d, r8d; Reserved
0x18002419d  call    cs:__imp_RegSetValueExW
0x1800241a3  add     rsp, 38h
0x1800241a7  retn
```
