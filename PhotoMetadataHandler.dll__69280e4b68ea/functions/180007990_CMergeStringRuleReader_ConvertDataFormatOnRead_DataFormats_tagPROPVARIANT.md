# CMergeStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)

- ea: `0x180007990`
- end: `0x180007ae2`
- name: `?ConvertDataFormatOnRead@CMergeStringRuleReader@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `338`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007990`
- `0x180007af0`
- `0x180008b7c`
- `0x1800132dc`
- `0x18001fa00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007a48`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007a93`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007a48`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180007a93`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007a5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007aaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ad1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007a5f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007aaa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ad1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180007a1c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180007a1c`

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
0x180007990  mov     [rsp+arg_0], rbx
0x180007995  mov     [rsp+arg_8], rsi
0x18000799a  push    rdi
0x18000799b  sub     rsp, 40h
0x18000799f  mov     rsi, r8
0x1800079a2  mov     r8d, edx
0x1800079a5  sub     r8d, 2
0x1800079a9  jz      loc_180007A7C
0x1800079af  cmp     r8d, 1
0x1800079b3  jz      short loc_180007A31
0x1800079b5  mov     r8, rsi
0x1800079b8  call    ?ConvertDataFormatOnRead@CStringRuleReader@@UEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z; CStringRuleReader::ConvertDataFormatOnRead(DataFormats,tagPROPVARIANT *)
0x1800079bd  mov     ebx, eax
0x1800079bf  xor     edi, edi
0x1800079c1  test    eax, eax
0x1800079c3  jns     short loc_1800079E4
0x1800079c5  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800079cb  jnz     short loc_1800079FF
0x1800079cd  test    eax, eax
0x1800079cf  jns     short loc_1800079E4
0x1800079d1  mov     eax, ebx
0x1800079d3  mov     rbx, [rsp+48h+arg_0]
0x1800079d8  mov     rsi, [rsp+48h+arg_8]
0x1800079dd  add     rsp, 40h
0x1800079e1  pop     rdi
0x1800079e2  retn
0x1800079e4  mov     eax, 101Fh
0x1800079e9  cmp     ax, [rsi]
0x1800079ec  jz      short loc_180007A08
0x1800079ee  mov     ebx, 88982F91h
0x1800079f3  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800079f9  jz      short loc_1800079D1
0x1800079fb  mov     ecx, ebx
0x1800079fd  jmp     short loc_180007A01
0x1800079ff  mov     ecx, eax; int
0x180007a01  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007a06  jmp     short loc_1800079D1
0x180007a08  cmp     [rsi+8], edi
0x180007a0b  jbe     short loc_1800079D1
0x180007a0d  mov     rcx, [rsi+10h]
0x180007a11  lea     rdx, pszTrimChars; " \r\n\t"
0x180007a18  mov     rcx, [rcx+rdi*8]; psz
0x180007a1c  call    cs:__imp_StrTrimW
0x180007a23  nop     dword ptr [rax+rax+00h]
0x180007a28  inc     edi
0x180007a2a  cmp     edi, [rsi+8]
0x180007a2d  jb      short loc_180007A0D
0x180007a2f  jmp     short loc_1800079D1
0x180007a31  xorps   xmm0, xmm0
0x180007a34  xor     eax, eax
0x180007a36  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180007a3b  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180007a40  mov     rdx, rsi; pvarSrc
0x180007a43  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180007a48  call    cs:__imp_PropVariantCopy
0x180007a4f  nop     dword ptr [rax+rax+00h]
0x180007a54  mov     ebx, eax
0x180007a56  xor     edi, edi
0x180007a58  test    eax, eax
0x180007a5a  js      short loc_180007A7A
0x180007a5c  mov     rcx, rsi; pvar
0x180007a5f  call    cs:__imp_PropVariantClear
0x180007a66  nop     dword ptr [rax+rax+00h]
0x180007a6b  mov     rdx, rsi; struct tagPROPVARIANT *
0x180007a6e  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x180007a73  call    ?ConvertDIS11HierarchyOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z; ConvertDIS11HierarchyOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180007a78  mov     ebx, eax
0x180007a7a  jmp     short loc_180007ACC
0x180007a7c  xorps   xmm0, xmm0
0x180007a7f  xor     eax, eax
0x180007a81  movups  xmmword ptr [rsp+48h+pvarDest], xmm0
0x180007a86  mov     qword ptr [rsp+48h+pvarDest+10h], rax
0x180007a8b  mov     rdx, rsi; pvarSrc
0x180007a8e  lea     rcx, [rsp+48h+pvarDest]; pvarDest
0x180007a93  call    cs:__imp_PropVariantCopy
0x180007a9a  nop     dword ptr [rax+rax+00h]
0x180007a9f  mov     ebx, eax
0x180007aa1  xor     edi, edi
0x180007aa3  test    eax, eax
0x180007aa5  js      short loc_180007ACC
0x180007aa7  mov     rcx, rsi; pvar
0x180007aaa  call    cs:__imp_PropVariantClear
0x180007ab1  nop     dword ptr [rax+rax+00h]
0x180007ab6  mov     r8, rsi; struct tagPROPVARIANT *
0x180007ab9  lea     rdx, asc_1800923E0; ";,"
0x180007ac0  lea     rcx, [rsp+48h+pvarDest]; struct tagPROPVARIANT *
0x180007ac5  call    ?ConvertDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBGPEAU1@@Z; ConvertDelimitedString(tagPROPVARIANT const *,ushort const *,tagPROPVARIANT *)
0x180007aca  mov     ebx, eax
0x180007acc  lea     rcx, [rsp+48h+pvarDest]; pvar
0x180007ad1  call    cs:__imp_PropVariantClear
0x180007ad8  nop     dword ptr [rax+rax+00h]
0x180007add  jmp     loc_1800079E4
```
