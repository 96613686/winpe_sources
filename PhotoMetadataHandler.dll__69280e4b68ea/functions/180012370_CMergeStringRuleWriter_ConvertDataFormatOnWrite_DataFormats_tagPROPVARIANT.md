# CMergeStringRuleWriter::ConvertDataFormatOnWrite(DataFormats,tagPROPVARIANT *)

- ea: `0x180012370`
- end: `0x1800124ab`
- name: `?ConvertDataFormatOnWrite@CMergeStringRuleWriter@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `315`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180011c50`
- `0x180011d08`
- `0x180012370`
- `0x1800132dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001245e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012491`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001245e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012491`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800123ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800123de`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800123ab`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x1800123de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMergeStringRuleWriter::ConvertDataFormatOnWrite(__int64 a1, unsigned int a2, PROPVARIANT *a3)
{
  unsigned int i; // esi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  PROPVARIANT pvar; // [rsp+20h] [rbp-48h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  if ( a3->vt == 31 )
  {
    StrTrimW(a3->bstrVal, L" \r\n\t");
  }
  else if ( a3->vt == 4127 )
  {
    for ( i = 0; i < a3->lVal; ++i )
      StrTrimW(*(PWSTR *)&a3->bstrblobVal.pData[8 * i], L" \r\n\t");
  }
  if ( a2 == 2 )
  {
    v7 = ConvertVectorToDelimitedString(a3, (unsigned __int16 *)&qword_18008D620, L",", &pvar);
LABEL_13:
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_19;
      v9 = v7;
      goto LABEL_11;
    }
    if ( pvar.vt )
    {
      PropVariantClear(a3);
      *a3 = pvar;
      memset(&pvar, 0, sizeof(pvar));
    }
    goto LABEL_19;
  }
  if ( a2 != 3 )
  {
    v7 = CStringRuleWriter::ConvertDataFormatOnWrite(a1, a2, a3);
    goto LABEL_13;
  }
  v8 = -2003292274;
  if ( g_doStackCaptures )
  {
    v9 = -2003292274;
LABEL_11:
    DoStackCapture(v9);
  }
LABEL_19:
  PropVariantClear(&pvar);
  return v8;
}

```

## disassembly

```asm
0x180012370  push    rbx
0x180012372  push    rbp
0x180012373  push    rsi
0x180012374  push    rdi
0x180012375  push    r14
0x180012377  sub     rsp, 40h
0x18001237b  mov     rdi, r8
0x18001237e  mov     ebx, edx
0x180012380  mov     rbp, rcx
0x180012383  xorps   xmm0, xmm0
0x180012386  xor     eax, eax
0x180012388  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x18001238d  mov     qword ptr [rsp+68h+pvar+10h], rax
0x180012392  mov     eax, 1Fh
0x180012397  xor     r14d, r14d
0x18001239a  cmp     ax, [r8]
0x18001239e  jnz     short loc_1800123B9
0x1800123a0  lea     rdx, pszTrimChars; " \r\n\t"
0x1800123a7  mov     rcx, [r8+8]; psz
0x1800123ab  call    cs:__imp_StrTrimW
0x1800123b2  nop     dword ptr [rax+rax+00h]
0x1800123b7  jmp     short loc_1800123F1
0x1800123b9  mov     eax, 101Fh
0x1800123be  cmp     ax, [r8]
0x1800123c2  jnz     short loc_1800123F1
0x1800123c4  mov     esi, r14d
0x1800123c7  cmp     [r8+8], r14d
0x1800123cb  jbe     short loc_1800123F1
0x1800123cd  mov     eax, esi
0x1800123cf  mov     rcx, [rdi+10h]
0x1800123d3  lea     rdx, pszTrimChars; " \r\n\t"
0x1800123da  mov     rcx, [rcx+rax*8]; psz
0x1800123de  call    cs:__imp_StrTrimW
0x1800123e5  nop     dword ptr [rax+rax+00h]
0x1800123ea  inc     esi
0x1800123ec  cmp     esi, [rdi+8]
0x1800123ef  jb      short loc_1800123CD
0x1800123f1  cmp     ebx, 2
0x1800123f4  jnz     short loc_180012413
0x1800123f6  lea     r9, [rsp+68h+pvar]; pvarDest
0x1800123fb  lea     r8, Delimiter; ","
0x180012402  lea     rdx, qword_18008D620; unsigned __int16 *
0x180012409  mov     rcx, rdi; pvarSrc
0x18001240c  call    ?ConvertVectorToDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBG1PEAU1@@Z; ConvertVectorToDelimitedString(tagPROPVARIANT const *,ushort const *,ushort const *,tagPROPVARIANT *)
0x180012411  jmp     short loc_18001243C
0x180012413  cmp     ebx, 3
0x180012416  jnz     short loc_18001242F
0x180012418  mov     ebx, 88982F8Eh
0x18001241d  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180012424  jz      short loc_18001248C
0x180012426  mov     ecx, ebx; int
0x180012428  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001242d  jmp     short loc_18001248C
0x18001242f  mov     r8, rdi
0x180012432  mov     edx, ebx
0x180012434  mov     rcx, rbp
0x180012437  call    ?ConvertDataFormatOnWrite@CStringRuleWriter@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z; CStringRuleWriter::ConvertDataFormatOnWrite(DataFormats,tagPROPVARIANT *)
0x18001243c  test    eax, eax
0x18001243e  mov     ebx, eax
0x180012440  jns     short loc_180012453
0x180012442  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180012449  jz      short loc_18001244F
0x18001244b  mov     ecx, eax
0x18001244d  jmp     short loc_180012428
0x18001244f  test    eax, eax
0x180012451  js      short loc_18001248C
0x180012453  cmp     word ptr [rsp+68h+pvar], r14w
0x180012459  jz      short loc_18001248C
0x18001245b  mov     rcx, rdi; pvar
0x18001245e  call    cs:__imp_PropVariantClear
0x180012465  nop     dword ptr [rax+rax+00h]
0x18001246a  movups  xmm0, xmmword ptr [rsp+68h+pvar]
0x18001246f  movups  xmmword ptr [rdi], xmm0
0x180012472  movsd   xmm1, qword ptr [rsp+68h+pvar+10h]
0x180012478  movsd   qword ptr [rdi+10h], xmm1
0x18001247d  xorps   xmm0, xmm0
0x180012480  xor     eax, eax
0x180012482  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180012487  mov     qword ptr [rsp+68h+pvar+10h], rax
0x18001248c  lea     rcx, [rsp+68h+pvar]; pvar
0x180012491  call    cs:__imp_PropVariantClear
0x180012498  nop     dword ptr [rax+rax+00h]
0x18001249d  mov     eax, ebx
0x18001249f  add     rsp, 40h
0x1800124a3  pop     r14
0x1800124a5  pop     rdi
0x1800124a6  pop     rsi
0x1800124a7  pop     rbp
0x1800124a8  pop     rbx
0x1800124a9  retn
```
