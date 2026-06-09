# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseSKUAttributeValue(ushort const *,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData &)

- ea: `0x1801fce68`
- end: `0x1801fd0db`
- name: `?ParseSKUAttributeValue@SelectionDataParser@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@AEAAJPEBGAEAUSelectionData@2345@@Z`
- size: `627`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *__hidden this, const unsigned __int16 *, struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801fce30`

## callees

- `0x18001aca4`
- `0x1801fce68`
- `0x180221c10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fce9f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fceca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcef3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf30`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcfc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd002`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd028`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd04e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd074`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fce9f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fceca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcef3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf30`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcf9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fcfc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd002`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd028`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd04e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801fd074`

## string_xrefs

- `0x1801fd0b3`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\helpers\selectiondataparser.cpp`
- `0x1801fce95`: `DesktopEnterprise`
- `0x1801fcebe`: `DesktopEnterpriseN`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser::ParseSKUAttributeValue(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *this,
        const unsigned __int16 *a2,
        struct WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionData *a3)
{
  int v5; // eax
  char *v6; // rcx
  int *v7; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::SelectionDataParser *v11; // [rsp+70h] [rbp+38h] BYREF

  v11 = this;
  if ( CompareStringOrdinal(a2, -1, L"DesktopEnterprise", -1, 1) == 2 )
  {
    v5 = 3;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopEnterpriseN", -1, 1) == 2 )
  {
    v5 = 5;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"Desktop", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 2;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 2;
LABEL_28:
    *((_QWORD *)v6 + 1) += 4LL;
LABEL_30:
    *((_BYTE *)a3 + 3) = 1;
    return 0;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopN", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 4;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 4;
    goto LABEL_28;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopCloud", -1, 1) == 2 )
  {
    v5 = 11;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopCloudN", -1, 1) == 2 )
  {
    v5 = 12;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"DesktopARM", -1, 1) == 2 )
  {
    v6 = (char *)a3 + 40;
    LODWORD(v11) = 1;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 == *((int **)a3 + 7) )
      goto LABEL_29;
    *v7 = 1;
    goto LABEL_28;
  }
  if ( CompareStringOrdinal(a2, -1, L"Mobile", -1, 1) == 2 )
  {
    v5 = 8;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"Server", -1, 1) == 2 )
  {
    v5 = 6;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"ServerSolution", -1, 1) == 2 )
  {
    v5 = 7;
    goto LABEL_26;
  }
  if ( CompareStringOrdinal(a2, -1, L"LongTermServicingBranch", -1, 1) == 2 )
  {
    v5 = 10;
LABEL_26:
    v6 = (char *)a3 + 40;
    LODWORD(v11) = v5;
    v7 = (int *)*((_QWORD *)a3 + 6);
    if ( v7 != *((int **)a3 + 7) )
    {
      *v7 = v5;
      goto LABEL_28;
    }
LABEL_29:
    std::vector<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<enum WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(
      v6,
      v7,
      &v11);
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAD,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\helpers\\selectiondataparser.cpp",
    (const char *)0xC00CE225LL,
    bIgnoreCase);
  return 3222069797LL;
}

```

## disassembly

```asm
0x1801fce68  mov     [rsp-30h+arg_0], rcx
0x1801fce6d  push    rbp
0x1801fce6e  push    rbx
0x1801fce6f  push    rsi
0x1801fce70  push    rdi
0x1801fce71  push    r14
0x1801fce73  push    r15
0x1801fce75  mov     rbp, rsp
0x1801fce78  sub     rsp, 38h
0x1801fce7c  mov     rdi, rdx
0x1801fce7f  or      esi, 0FFFFFFFFh
0x1801fce82  mov     rbx, r8
0x1801fce85  mov     r15d, 1
0x1801fce8b  mov     r9d, esi; cchCount2
0x1801fce8e  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fce93  mov     edx, esi; cchCount1
0x1801fce95  lea     r8, aDesktopenterpr; "DesktopEnterprise"
0x1801fce9c  mov     rcx, rdi; lpString1
0x1801fce9f  call    cs:__imp_CompareStringOrdinal
0x1801fcea5  lea     r14d, [r15+1]
0x1801fcea9  cmp     eax, r14d
0x1801fceac  jnz     short loc_1801FCEB6
0x1801fceae  lea     eax, [rsi+4]
0x1801fceb1  jmp     loc_1801FD084
0x1801fceb6  mov     r9d, esi; cchCount2
0x1801fceb9  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcebe  lea     r8, aDesktopenterpr_0; "DesktopEnterpriseN"
0x1801fcec5  mov     edx, esi; cchCount1
0x1801fcec7  mov     rcx, rdi; lpString1
0x1801fceca  call    cs:__imp_CompareStringOrdinal
0x1801fced0  cmp     eax, r14d
0x1801fced3  jnz     short loc_1801FCEDF
0x1801fced5  mov     eax, 5
0x1801fceda  jmp     loc_1801FD084
0x1801fcedf  mov     r9d, esi; cchCount2
0x1801fcee2  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcee7  lea     r8, aDesktop; "Desktop"
0x1801fceee  mov     edx, esi; cchCount1
0x1801fcef0  mov     rcx, rdi; lpString1
0x1801fcef3  call    cs:__imp_CompareStringOrdinal
0x1801fcef9  cmp     eax, r14d
0x1801fcefc  jnz     short loc_1801FCF1C
0x1801fcefe  lea     rcx, [rbx+28h]
0x1801fcf02  mov     dword ptr [rbp+arg_0], r14d
0x1801fcf06  mov     rdx, [rcx+8]
0x1801fcf0a  cmp     rdx, [rcx+10h]
0x1801fcf0e  jz      loc_1801FD09E
0x1801fcf14  mov     [rdx], r14d
0x1801fcf17  jmp     loc_1801FD097
0x1801fcf1c  mov     r9d, esi; cchCount2
0x1801fcf1f  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcf24  lea     r8, aDesktopn; "DesktopN"
0x1801fcf2b  mov     edx, esi; cchCount1
0x1801fcf2d  mov     rcx, rdi; lpString1
0x1801fcf30  call    cs:__imp_CompareStringOrdinal
0x1801fcf36  cmp     eax, r14d
0x1801fcf39  jnz     short loc_1801FCF5F
0x1801fcf3b  lea     rcx, [rbx+28h]
0x1801fcf3f  mov     dword ptr [rbp+arg_0], 4
0x1801fcf46  mov     rdx, [rcx+8]
0x1801fcf4a  cmp     rdx, [rcx+10h]
0x1801fcf4e  jz      loc_1801FD09E
0x1801fcf54  mov     dword ptr [rdx], 4
0x1801fcf5a  jmp     loc_1801FD097
0x1801fcf5f  mov     r9d, esi; cchCount2
0x1801fcf62  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcf67  lea     r8, aDesktopcloud; "DesktopCloud"
0x1801fcf6e  mov     edx, esi; cchCount1
0x1801fcf70  mov     rcx, rdi; lpString1
0x1801fcf73  call    cs:__imp_CompareStringOrdinal
0x1801fcf79  cmp     eax, r14d
0x1801fcf7c  jnz     short loc_1801FCF88
0x1801fcf7e  mov     eax, 0Bh
0x1801fcf83  jmp     loc_1801FD084
0x1801fcf88  mov     r9d, esi; cchCount2
0x1801fcf8b  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcf90  lea     r8, aDesktopcloudn; "DesktopCloudN"
0x1801fcf97  mov     edx, esi; cchCount1
0x1801fcf99  mov     rcx, rdi; lpString1
0x1801fcf9c  call    cs:__imp_CompareStringOrdinal
0x1801fcfa2  cmp     eax, r14d
0x1801fcfa5  jnz     short loc_1801FCFB1
0x1801fcfa7  mov     eax, 0Ch
0x1801fcfac  jmp     loc_1801FD084
0x1801fcfb1  mov     r9d, esi; cchCount2
0x1801fcfb4  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcfb9  lea     r8, aDesktoparm; "DesktopARM"
0x1801fcfc0  mov     edx, esi; cchCount1
0x1801fcfc2  mov     rcx, rdi; lpString1
0x1801fcfc5  call    cs:__imp_CompareStringOrdinal
0x1801fcfcb  cmp     eax, r14d
0x1801fcfce  jnz     short loc_1801FCFEE
0x1801fcfd0  lea     rcx, [rbx+28h]
0x1801fcfd4  mov     dword ptr [rbp+arg_0], r15d
0x1801fcfd8  mov     rdx, [rcx+8]
0x1801fcfdc  cmp     rdx, [rcx+10h]
0x1801fcfe0  jz      loc_1801FD09E
0x1801fcfe6  mov     [rdx], r15d
0x1801fcfe9  jmp     loc_1801FD097
0x1801fcfee  mov     r9d, esi; cchCount2
0x1801fcff1  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fcff6  lea     r8, aMobile; "Mobile"
0x1801fcffd  mov     edx, esi; cchCount1
0x1801fcfff  mov     rcx, rdi; lpString1
0x1801fd002  call    cs:__imp_CompareStringOrdinal
0x1801fd008  cmp     eax, r14d
0x1801fd00b  jnz     short loc_1801FD014
0x1801fd00d  mov     eax, 8
0x1801fd012  jmp     short loc_1801FD084
0x1801fd014  mov     r9d, esi; cchCount2
0x1801fd017  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fd01c  lea     r8, aServer; "Server"
0x1801fd023  mov     edx, esi; cchCount1
0x1801fd025  mov     rcx, rdi; lpString1
0x1801fd028  call    cs:__imp_CompareStringOrdinal
0x1801fd02e  cmp     eax, r14d
0x1801fd031  jnz     short loc_1801FD03A
0x1801fd033  mov     eax, 6
0x1801fd038  jmp     short loc_1801FD084
0x1801fd03a  mov     r9d, esi; cchCount2
0x1801fd03d  mov     [rsp+38h+bIgnoreCase], r15d; bIgnoreCase
0x1801fd042  lea     r8, aServersolution; "ServerSolution"
0x1801fd049  mov     edx, esi; cchCount1
0x1801fd04b  mov     rcx, rdi; lpString1
0x1801fd04e  call    cs:__imp_CompareStringOrdinal
0x1801fd054  cmp     eax, r14d
0x1801fd057  jnz     short loc_1801FD060
0x1801fd059  mov     eax, 7
0x1801fd05e  jmp     short loc_1801FD084
0x1801fd060  mov     r9d, esi; cchCount2
0x1801fd063  mov     [rsp+38h+bIgnoreCase], r15d; int
0x1801fd068  lea     r8, aLongtermservic; "LongTermServicingBranch"
0x1801fd06f  mov     edx, esi; cchCount1
0x1801fd071  mov     rcx, rdi; lpString1
0x1801fd074  call    cs:__imp_CompareStringOrdinal
0x1801fd07a  cmp     eax, r14d
0x1801fd07d  jnz     short loc_1801FD0AF
0x1801fd07f  mov     eax, 0Ah
0x1801fd084  lea     rcx, [rbx+28h]
0x1801fd088  mov     dword ptr [rbp+arg_0], eax
0x1801fd08b  mov     rdx, [rcx+8]
0x1801fd08f  cmp     rdx, [rcx+10h]
0x1801fd093  jz      short loc_1801FD09E
0x1801fd095  mov     [rdx], eax
0x1801fd097  add     qword ptr [rcx+8], 4
0x1801fd09c  jmp     short loc_1801FD0A7
0x1801fd09e  lea     r8, [rbp+arg_0]
0x1801fd0a2  call    ??$_Emplace_reallocate@AEBW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@?$vector@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$allocator@W4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@@std@@AEAAPEAW4CollectionSKU@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAW423456@AEBW423456@@Z; std::vector<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU>::_Emplace_reallocate<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &>(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU * const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionSKU const &)
0x1801fd0a7  mov     [rbx+3], r15b
0x1801fd0ab  xor     eax, eax
0x1801fd0ad  jmp     short loc_1801FD0CE
0x1801fd0af  mov     rcx, [rbp+30h]; this
0x1801fd0b3  lea     r8, aShellcommonShe_64; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801fd0ba  mov     ebx, 0C00CE225h
0x1801fd0bf  mov     edx, 0ADh; void *
0x1801fd0c4  mov     r9d, ebx; char *
0x1801fd0c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801fd0cc  mov     eax, ebx
0x1801fd0ce  add     rsp, 38h
0x1801fd0d2  pop     r15
0x1801fd0d4  pop     r14
0x1801fd0d6  pop     rdi
0x1801fd0d7  pop     rsi
0x1801fd0d8  pop     rbx
0x1801fd0d9  pop     rbp
0x1801fd0da  retn
```
