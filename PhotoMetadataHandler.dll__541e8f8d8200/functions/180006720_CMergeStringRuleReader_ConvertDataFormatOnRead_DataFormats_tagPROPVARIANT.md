# CMergeStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x180006720`
- end: `0x18000684d`
- name: `?ConvertDataFormatOnRead@CMergeStringRuleReader@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `301`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006720`
- `0x180006860`
- `0x180007828`
- `0x1800129d8`
- `0x18001eb74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800067d1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006810`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800067d1`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180006810`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006821`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006842`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800067e2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006821`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006842`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800067ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800067ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMergeStringRuleReader::ConvertDataFormatOnRead(__int64 a1, int a2, PROPVARIANT *a3)
{
  int v4; // eax
  HRESULT v5; // ebx
  __int64 v6; // rdi
  int v8; // ecx
  PROPVARIANT pvarDest; // [rsp+20h] [rbp-28h] BYREF

  if ( a2 == 2 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v5 = PropVariantCopy(&pvarDest, a3);
    v6 = 0;
    if ( v5 >= 0 )
    {
      PropVariantClear(a3);
      v5 = ConvertDelimitedString(&pvarDest, L";,", a3);
    }
    goto LABEL_19;
  }
  if ( a2 == 3 )
  {
    memset(&pvarDest, 0, sizeof(pvarDest));
    v5 = PropVariantCopy(&pvarDest, a3);
    v6 = 0;
    if ( v5 >= 0 )
    {
      PropVariantClear(a3);
      v5 = ConvertDIS11HierarchyOnRead(&pvarDest, a3);
    }
LABEL_19:
    PropVariantClear(&pvarDest);
    goto LABEL_6;
  }
  v4 = CStringRuleReader::ConvertDataFormatOnRead(a1, a2, a3);
  v5 = v4;
  v6 = 0;
  if ( v4 < 0 )
  {
    if ( !g_doStackCaptures )
      return (unsigned int)v5;
    v8 = v4;
LABEL_10:
    DoStackCapture(v8);
    return (unsigned int)v5;
  }
LABEL_6:
  if ( a3->vt != 4127 )
  {
    v5 = -2003292271;
    if ( !g_doStackCaptures )
      return (unsigned int)v5;
    v8 = -2003292271;
    goto LABEL_10;
  }
  if ( a3->lVal )
  {
    do
    {
      StrTrimW(*(PWSTR *)&a3->bstrblobVal.pData[8 * v6], L" \r\n\t");
      v6 = (unsigned int)(v6 + 1);
    }
    while ( (unsigned int)v6 < a3->lVal );
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006720  mov     [rsp+arg_0], rbx
0x180006725  mov     [rsp+arg_8], rsi
0x18000672a  push    rdi
0x18000672b  sub     rsp, 40h
0x18000672f  mov     rsi, r8
0x180006732  mov     r8d, edx
0x180006735  sub     r8d, 2
0x180006739  jz      loc_1800067F9
0x18000673f  cmp     r8d, 1
0x180006743  jz      short loc_1800067BA
0x180006745  mov     r8, rsi
0x180006748  call    ?ConvertDataFormatOnRead@CStringRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z; CStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)
0x18000674d  mov     ebx, eax
0x18000674f  xor     edi, edi
0x180006751  test    eax, eax
0x180006753  jns     short loc_180006773
0x180006755  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18000675b  jnz     short loc_18000678E
0x18000675d  test    eax, eax
0x18000675f  jns     short loc_180006773
0x180006761  mov     eax, ebx
0x180006763  mov     rbx, [rsp+48h+arg_0]
0x180006768  mov     rsi, [rsp+48h+arg_8]
0x18000676d  add     rsp, 40h
0x180006771  pop     rdi
0x180006772  retn
0x180006773  mov     eax, 101Fh
0x180006778  cmp     ax, [rsi]
0x18000677b  jz      short loc_180006797
0x18000677d  mov     ebx, 88982F91h
0x180006782  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180006788  jz      short loc_180006761
0x18000678a  mov     ecx, ebx
0x18000678c  jmp     short loc_180006790
0x18000678e  mov     ecx, eax; int
0x180006790  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180006795  jmp     short loc_180006761
0x180006797  cmp     [rsi+8], edi
0x18000679a  jbe     short loc_180006761
0x18000679c  mov     rcx, [rsi+10h]
0x1800067a0  lea     rdx, pszTrimChars; " \r\n\t"
0x1800067a7  mov     rcx, [rcx+rdi*8]; psz
0x1800067ab  call    cs:__imp_StrTrimW
0x1800067b1  inc     edi
0x1800067b3  cmp     edi, [rsi+8]
0x1800067b6  jb      short loc_18000679C
0x1800067b8  jmp     short loc_180006761
0x1800067ba  xorps   xmm0, xmm0
0x1800067bd  xor     eax, eax
0x1800067bf  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x1800067c4  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x1800067c9  mov     rdx, rsi; pvarSrc
0x1800067cc  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x1800067d1  call    cs:__imp_PropVariantCopy
0x1800067d7  mov     ebx, eax
0x1800067d9  xor     edi, edi
0x1800067db  test    eax, eax
0x1800067dd  js      short loc_1800067F7
0x1800067df  mov     rcx, rsi; pvar
0x1800067e2  call    cs:__imp_PropVariantClear
0x1800067e8  mov     rdx, rsi; struct tagPROPVARIANT *
0x1800067eb  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x1800067f0  call    ?ConvertDIS11HierarchyOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertDIS11HierarchyOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x1800067f5  mov     ebx, eax
0x1800067f7  jmp     short loc_18000683D
0x1800067f9  xorps   xmm0, xmm0
0x1800067fc  xor     eax, eax
0x1800067fe  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180006803  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180006808  mov     rdx, rsi; pvarSrc
0x18000680b  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180006810  call    cs:__imp_PropVariantCopy
0x180006816  mov     ebx, eax
0x180006818  xor     edi, edi
0x18000681a  test    eax, eax
0x18000681c  js      short loc_18000683D
0x18000681e  mov     rcx, rsi; pvar
0x180006821  call    cs:__imp_PropVariantClear
0x180006827  mov     r8, rsi; struct tagPROPVARIANT *
0x18000682a  lea     rdx, asc_180091420; ";,"
0x180006831  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x180006836  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x18000683b  mov     ebx, eax
0x18000683d  lea     rcx, [rsp+48h+pvarDest]; pvar
0x180006842  call    cs:__imp_PropVariantClear
0x180006848  jmp     loc_180006773
```
