# CRegKeyWrapper::SetStringValue(ATL::CRegKey *,ushort const *,ushort const *,ulong)

- ea: `0x180016220`
- end: `0x180016273`
- name: `?SetStringValue@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEBG1K@Z`
- size: `83`
- prototype: `int(CRegKeyWrapper *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000dc74`
- `0x180016220`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016268`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016268`

## pseudocode

```c
LSTATUS __fastcall CRegKeyWrapper::SetStringValue(
        CRegKeyWrapper *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        const BYTE *lpData,
        DWORD dwType)
{
  __int64 v5; // rax

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)&lpData[2 * v5] );
  return RegSetValueExW(*a2, a3, 0, dwType, lpData, 2 * v5 + 2);
}

```

## disassembly

```asm
0x180016220  sub     rsp, 38h
0x180016224  xor     ecx, ecx
0x180016226  mov     r10, r8
0x180016229  mov     r11, rdx
0x18001622c  test    r9, r9
0x18001622f  jnz     short loc_18001623C
0x180016231  mov     ecx, 80004005h; int
0x180016236  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001623c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016240  inc     rax
0x180016243  cmp     [r9+rax*2], cx
0x180016248  jnz     short loc_180016240
0x18001624a  mov     rcx, [r11]; hKey
0x18001624d  lea     eax, ds:2[rax*2]
0x180016254  mov     [rsp+38h+cbData], eax; cbData
0x180016258  xor     r8d, r8d; Reserved
0x18001625b  mov     [rsp+38h+lpData], r9; lpData
0x180016260  mov     rdx, r10; lpValueName
0x180016263  mov     r9d, [rsp+38h+dwType]; dwType
0x180016268  call    cs:__imp_RegSetValueExW
0x18001626e  add     rsp, 38h
0x180016272  retn
```
