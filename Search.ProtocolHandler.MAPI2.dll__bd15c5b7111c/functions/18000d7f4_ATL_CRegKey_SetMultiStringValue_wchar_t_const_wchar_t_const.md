# ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)

- ea: `0x18000d7f4`
- end: `0x18000d857`
- name: `?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z`
- size: `99`
- prototype: `int(ATL::CRegKey *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b29c`
- `0x180034b8c`

## callees

- `0x18000be4c`
- `0x18000d7f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d84b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000d84b`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetMultiStringValue(HKEY *this, const wchar_t *a2, const BYTE *lpData)
{
  DWORD cbData; // r9d
  const BYTE *v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( !lpData )
    ATL::AtlThrowImpl(-2147467259);
  cbData = 0;
  v6 = lpData;
  do
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
    v8 = (unsigned int)(v7 + 1);
    v6 += 2 * v8;
    cbData += 2 * v8;
  }
  while ( (_DWORD)v8 != 1 );
  return RegSetValueExW(*this, a2, 0, 7u, lpData, cbData);
}

```

## disassembly

```asm
0x18000d7f4  push    rbx
0x18000d7f6  sub     rsp, 30h
0x18000d7fa  xor     ebx, ebx
0x18000d7fc  mov     r10, rdx
0x18000d7ff  mov     r11, rcx
0x18000d802  test    r8, r8
0x18000d805  jnz     short loc_18000D812
0x18000d807  mov     ecx, 80004005h; int
0x18000d80c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d812  mov     r9d, ebx
0x18000d815  mov     rdx, r8
0x18000d818  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d81c  inc     rcx
0x18000d81f  cmp     [rdx+rcx*2], bx
0x18000d823  jnz     short loc_18000D81C
0x18000d825  inc     ecx
0x18000d827  lea     rdx, [rdx+rcx*2]
0x18000d82b  lea     r9d, [r9+rcx*2]
0x18000d82f  cmp     ecx, 1
0x18000d832  jnz     short loc_18000D818
0x18000d834  mov     [rsp+38h+cbData], r9d; cbData
0x18000d839  mov     rdx, r10; lpValueName
0x18000d83c  mov     [rsp+38h+lpData], r8; lpData
0x18000d841  lea     r9d, [rcx+6]; dwType
0x18000d845  mov     rcx, [r11]; hKey
0x18000d848  xor     r8d, r8d; Reserved
0x18000d84b  call    cs:__imp_RegSetValueExW
0x18000d851  add     rsp, 30h
0x18000d855  pop     rbx
0x18000d856  retn
```
