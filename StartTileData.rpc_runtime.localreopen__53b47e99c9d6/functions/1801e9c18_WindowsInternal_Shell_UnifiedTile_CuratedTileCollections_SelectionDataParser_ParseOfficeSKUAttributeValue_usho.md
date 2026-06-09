# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseOfficeSKUAttributeValue(ushort const *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData &)

- ea: `0x1801e9c18`
- end: `0x1801e9e07`
- name: `?ParseOfficeSKUAttributeValue@SelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGAEAUSelectionData@2345@@Z`
- size: `495`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *__hidden this, const unsigned __int16 *, struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801e9be0`

## callees

- `0x18001aca4`
- `0x1801e9c18`
- `0x180221c10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9c54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9c97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9cd4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d9a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9c54`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9c97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9cd4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d0f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d38`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801e9d9a`

## string_xrefs

- `0x1801e9dd9`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\selectiondataparser.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseOfficeSKUAttributeValue(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *this,
        const unsigned __int16 *a2,
        struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *a3)
{
  char *v5; // rcx
  int *v6; // rdx
  int v7; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *v11; // [rsp+50h] [rbp+20h] BYREF

  v11 = this;
  if ( CompareStringOrdinal(a2, -1, L"None", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 0;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 0;
LABEL_21:
      *((_QWORD *)v5 + 1) += 4LL;
LABEL_23:
      *((_BYTE *)a3 + 4) = 1;
      return 0;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"DownloadOffice", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 1;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 1;
      goto LABEL_21;
    }
LABEL_22:
    std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(
      v5,
      v6,
      &v11);
    goto LABEL_23;
  }
  if ( CompareStringOrdinal(a2, -1, L"Mobile", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 2;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 2;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop", -1, 1) == 2 )
  {
    v7 = 3;
    goto LABEL_19;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop2016", -1, 1) == 2 )
  {
    v5 = (char *)a3 + 64;
    LODWORD(v11) = 4;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = 4;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopBridge", -1, 1) == 2 )
  {
    v7 = 5;
    goto LABEL_19;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopBridgeSubscription", -1, 1) == 2 )
  {
    v7 = 6;
LABEL_19:
    v5 = (char *)a3 + 64;
    LODWORD(v11) = v7;
    v6 = (int *)*((_QWORD *)a3 + 9);
    if ( v6 != *((int **)a3 + 10) )
    {
      *v6 = v7;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD3,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\selectiondataparser.cpp",
    (const char *)0xC00CE225LL,
    bIgnoreCase);
  return 3222069797LL;
}

```

## disassembly

```asm
0x1801e9c18  mov     rax, rsp
0x1801e9c1b  mov     [rax+10h], rbx
0x1801e9c1f  mov     [rax+18h], rsi
0x1801e9c23  mov     [rax+8], rcx
0x1801e9c27  push    rbp
0x1801e9c28  push    rdi
0x1801e9c29  push    r14
0x1801e9c2b  mov     rbp, rsp
0x1801e9c2e  sub     rsp, 30h
0x1801e9c32  mov     rdi, rdx
0x1801e9c35  or      esi, 0FFFFFFFFh
0x1801e9c38  mov     rbx, r8
0x1801e9c3b  mov     r14d, 1
0x1801e9c41  mov     r9d, esi; cchCount2
0x1801e9c44  mov     [rax-28h], r14d
0x1801e9c48  mov     edx, esi; cchCount1
0x1801e9c4a  lea     r8, aNone_0; "None"
0x1801e9c51  mov     rcx, rdi; lpString1
0x1801e9c54  call    cs:__imp_CompareStringOrdinal
0x1801e9c5a  cmp     eax, 2
0x1801e9c5d  jnz     short loc_1801E9C83
0x1801e9c5f  lea     rcx, [rbx+40h]
0x1801e9c63  mov     dword ptr [rbp+arg_0], 0
0x1801e9c6a  mov     rdx, [rcx+8]
0x1801e9c6e  cmp     rdx, [rcx+10h]
0x1801e9c72  jz      loc_1801E9DC4
0x1801e9c78  mov     dword ptr [rdx], 0
0x1801e9c7e  jmp     loc_1801E9DBD
0x1801e9c83  mov     r9d, esi; cchCount2
0x1801e9c86  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1801e9c8b  lea     r8, aDownloadoffice; "DownloadOffice"
0x1801e9c92  mov     edx, esi; cchCount1
0x1801e9c94  mov     rcx, rdi; lpString1
0x1801e9c97  call    cs:__imp_CompareStringOrdinal
0x1801e9c9d  cmp     eax, 2
0x1801e9ca0  jnz     short loc_1801E9CC0
0x1801e9ca2  lea     rcx, [rbx+40h]
0x1801e9ca6  mov     dword ptr [rbp+arg_0], r14d
0x1801e9caa  mov     rdx, [rcx+8]
0x1801e9cae  cmp     rdx, [rcx+10h]
0x1801e9cb2  jz      loc_1801E9DC4
0x1801e9cb8  mov     [rdx], r14d
0x1801e9cbb  jmp     loc_1801E9DBD
0x1801e9cc0  mov     r9d, esi; cchCount2
0x1801e9cc3  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1801e9cc8  lea     r8, aMobile; "Mobile"
0x1801e9ccf  mov     edx, esi; cchCount1
0x1801e9cd1  mov     rcx, rdi; lpString1
0x1801e9cd4  call    cs:__imp_CompareStringOrdinal
0x1801e9cda  cmp     eax, 2
0x1801e9cdd  jnz     short loc_1801E9CFB
0x1801e9cdf  lea     rcx, [rbx+40h]
0x1801e9ce3  mov     dword ptr [rbp+arg_0], eax
0x1801e9ce6  mov     rdx, [rcx+8]
0x1801e9cea  cmp     rdx, [rcx+10h]
0x1801e9cee  jz      loc_1801E9DC4
0x1801e9cf4  mov     [rdx], eax
0x1801e9cf6  jmp     loc_1801E9DBD
0x1801e9cfb  mov     r9d, esi; cchCount2
0x1801e9cfe  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1801e9d03  lea     r8, aDesktop; "Desktop"
0x1801e9d0a  mov     edx, esi; cchCount1
0x1801e9d0c  mov     rcx, rdi; lpString1
0x1801e9d0f  call    cs:__imp_CompareStringOrdinal
0x1801e9d15  cmp     eax, 2
0x1801e9d18  jnz     short loc_1801E9D24
0x1801e9d1a  mov     eax, 3
0x1801e9d1f  jmp     loc_1801E9DAA
0x1801e9d24  mov     r9d, esi; cchCount2
0x1801e9d27  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1801e9d2c  lea     r8, aDesktop2016; "Desktop2016"
0x1801e9d33  mov     edx, esi; cchCount1
0x1801e9d35  mov     rcx, rdi; lpString1
0x1801e9d38  call    cs:__imp_CompareStringOrdinal
0x1801e9d3e  cmp     eax, 2
0x1801e9d41  jnz     short loc_1801E9D60
0x1801e9d43  lea     rcx, [rbx+40h]
0x1801e9d47  mov     dword ptr [rbp+arg_0], 4
0x1801e9d4e  mov     rdx, [rcx+8]
0x1801e9d52  cmp     rdx, [rcx+10h]
0x1801e9d56  jz      short loc_1801E9DC4
0x1801e9d58  mov     dword ptr [rdx], 4
0x1801e9d5e  jmp     short loc_1801E9DBD
0x1801e9d60  mov     r9d, esi; cchCount2
0x1801e9d63  mov     [rsp+30h+bIgnoreCase], r14d; bIgnoreCase
0x1801e9d68  lea     r8, aDesktopbridge; "DesktopBridge"
0x1801e9d6f  mov     edx, esi; cchCount1
0x1801e9d71  mov     rcx, rdi; lpString1
0x1801e9d74  call    cs:__imp_CompareStringOrdinal
0x1801e9d7a  cmp     eax, 2
0x1801e9d7d  jnz     short loc_1801E9D86
0x1801e9d7f  mov     eax, 5
0x1801e9d84  jmp     short loc_1801E9DAA
0x1801e9d86  mov     r9d, esi; cchCount2
0x1801e9d89  mov     [rsp+30h+bIgnoreCase], r14d; int
0x1801e9d8e  lea     r8, aDesktopbridges; "DesktopBridgeSubscription"
0x1801e9d95  mov     edx, esi; cchCount1
0x1801e9d97  mov     rcx, rdi; lpString1
0x1801e9d9a  call    cs:__imp_CompareStringOrdinal
0x1801e9da0  cmp     eax, 2
0x1801e9da3  jnz     short loc_1801E9DD5
0x1801e9da5  mov     eax, 6
0x1801e9daa  lea     rcx, [rbx+40h]
0x1801e9dae  mov     dword ptr [rbp+arg_0], eax
0x1801e9db1  mov     rdx, [rcx+8]
0x1801e9db5  cmp     rdx, [rcx+10h]
0x1801e9db9  jz      short loc_1801E9DC4
0x1801e9dbb  mov     [rdx], eax
0x1801e9dbd  add     qword ptr [rcx+8], 4
0x1801e9dc2  jmp     short loc_1801E9DCD
0x1801e9dc4  lea     r8, [rbp+arg_0]
0x1801e9dc8  call    ??$_Emplace_reallocate@AEBW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@?$vector@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$allocator@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@AEAAPEAW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAW423456@AEBW423456@@Z; std::vector<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU * const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &)
0x1801e9dcd  mov     [rbx+4], r14b
0x1801e9dd1  xor     eax, eax
0x1801e9dd3  jmp     short loc_1801E9DF4
0x1801e9dd5  mov     rcx, [rbp+18h]; this
0x1801e9dd9  lea     r8, aShellcommonShe_64; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801e9de0  mov     ebx, 0C00CE225h
0x1801e9de5  mov     edx, 0D3h; void *
0x1801e9dea  mov     r9d, ebx; char *
0x1801e9ded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e9df2  mov     eax, ebx
0x1801e9df4  mov     rbx, [rsp+30h+arg_8]
0x1801e9df9  mov     rsi, [rsp+30h+arg_10]
0x1801e9dfe  add     rsp, 30h
0x1801e9e02  pop     r14
0x1801e9e04  pop     rdi
0x1801e9e05  pop     rbp
0x1801e9e06  retn
```
