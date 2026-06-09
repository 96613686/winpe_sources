# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180012608`
- end: `0x180012654`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800124c0`
- `0x180017b88`
- `0x18001c710`

## callees

- `0x18000ddb4`
- `0x180012608`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012649`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180012649`

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
0x180012608  sub     rsp, 38h
0x18001260c  xor     r9d, r9d
0x18001260f  test    r8, r8
0x180012612  jnz     short loc_18001261F
0x180012614  mov     ecx, 80004005h; int
0x180012619  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001261f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012623  inc     rax
0x180012626  cmp     [r8+rax*2], r9w
0x18001262b  jnz     short loc_180012623
0x18001262d  mov     rcx, [rcx]; hKey
0x180012630  lea     eax, ds:2[rax*2]
0x180012637  mov     [rsp+38h+cbData], eax; cbData
0x18001263b  mov     r9d, 1; dwType
0x180012641  mov     [rsp+38h+lpData], r8; lpData
0x180012646  xor     r8d, r8d; Reserved
0x180012649  call    cs:__imp_RegSetValueExW
0x18001264f  add     rsp, 38h
0x180012653  retn
```
