# ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x180009020`
- end: `0x180009074`
- name: `?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z`
- size: `84`
- prototype: `LSTATUS __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008ce0`
- `0x18000eac4`
- `0x18000eda0`

## callees

- `0x180009020`
- `0x18000d950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009069`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009069`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData)
{
  __int64 v3; // rax

  if ( !lpData )
    ATL::AtlThrowImpl((int)this);
  v3 = -1;
  while ( *(_WORD *)&lpData[2 * v3++ + 2] != 0 )
    ;
  return RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * v3 + 2);
}

```

## disassembly

```asm
0x180009020  sub     rsp, 38h
0x180009024  test    r8, r8
0x180009027  jnz     short loc_18000902F
0x180009029  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000902f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009036  nop     word ptr [rax+rax+00000000h]
0x180009040  cmp     word ptr [r8+rax*2+2], 0
0x180009047  lea     rax, [rax+1]
0x18000904b  jnz     short loc_180009040
0x18000904d  mov     rcx, [rcx]; hKey
0x180009050  lea     eax, ds:2[rax*2]
0x180009057  mov     [rsp+38h+cbData], eax; cbData
0x18000905b  mov     r9d, 1; dwType
0x180009061  mov     [rsp+38h+lpData], r8; lpData
0x180009066  xor     r8d, r8d; Reserved
0x180009069  call    cs:__imp_RegSetValueExW
0x18000906f  add     rsp, 38h
0x180009073  retn
```
