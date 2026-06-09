# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180030a54`
- end: `0x180030aa0`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `76`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18003415c`
- `0x18003c92c`
- `0x180060f8c`

## callees

- `0x180030a54`
- `0x180044210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030a8a`

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
0x180030a54  sub     rsp, 38h
0x180030a58  xor     r9d, r9d
0x180030a5b  test    r8, r8
0x180030a5e  jz      short loc_180030A95
0x180030a60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030a64  inc     rax
0x180030a67  cmp     [r8+rax*2], r9w
0x180030a6c  jnz     short loc_180030A64
0x180030a6e  mov     rcx, [rcx]; hKey
0x180030a71  lea     eax, ds:2[rax*2]
0x180030a78  mov     [rsp+38h+cbData], eax; cbData
0x180030a7c  mov     r9d, 1; dwType
0x180030a82  mov     [rsp+38h+lpData], r8; lpData
0x180030a87  xor     r8d, r8d; Reserved
0x180030a8a  call    cs:__imp_RegSetValueExW
0x180030a90  add     rsp, 38h
0x180030a94  retn
0x180030a95  mov     ecx, 80004005h; int
0x180030a9a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
