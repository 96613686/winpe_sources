# CMergeStringRuleWriter::ConvertDataFormatOnWrite(DataFormats,tagPROPVARIANT *)

- ea: `0x180011b20`
- end: `0x180011c42`
- name: `?ConvertDataFormatOnWrite@CMergeStringRuleWriter@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z`
- size: `290`
- prototype: `int __high(enum DataFormats, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180011460`
- `0x18001150c`
- `0x180011b20`
- `0x1800129d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c02`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011c2f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180011b5b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180011b88`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180011b5b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180011b88`

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
    v7 = ConvertVectorToDelimitedString(a3, (unsigned __int16 *)&qword_18008C640, L",", &pvar);
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
0x180011b20  push    rbx
0x180011b22  push    rbp
0x180011b23  push    rsi
0x180011b24  push    rdi
0x180011b25  push    r14
0x180011b27  sub     rsp, 40h
0x180011b2b  mov     rdi, r8
0x180011b2e  mov     ebx, edx
0x180011b30  mov     rbp, rcx
0x180011b33  xorps   xmm0, xmm0
0x180011b36  xor     eax, eax
0x180011b38  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180011b3d  mov     qword ptr [rsp+68h+pvar+10h], rax
0x180011b42  mov     eax, 1Fh
0x180011b47  xor     r14d, r14d
0x180011b4a  cmp     ax, [r8]
0x180011b4e  jnz     short loc_180011B63
0x180011b50  lea     rdx, pszTrimChars; " \r\n\t"
0x180011b57  mov     rcx, [r8+8]; psz
0x180011b5b  call    cs:__imp_StrTrimW
0x180011b61  jmp     short loc_180011B95
0x180011b63  mov     eax, 101Fh
0x180011b68  cmp     ax, [r8]
0x180011b6c  jnz     short loc_180011B95
0x180011b6e  mov     esi, r14d
0x180011b71  cmp     [r8+8], r14d
0x180011b75  jbe     short loc_180011B95
0x180011b77  mov     eax, esi
0x180011b79  mov     rcx, [rdi+10h]
0x180011b7d  lea     rdx, pszTrimChars; " \r\n\t"
0x180011b84  mov     rcx, [rcx+rax*8]; psz
0x180011b88  call    cs:__imp_StrTrimW
0x180011b8e  inc     esi
0x180011b90  cmp     esi, [rdi+8]
0x180011b93  jb      short loc_180011B77
0x180011b95  cmp     ebx, 2
0x180011b98  jnz     short loc_180011BB7
0x180011b9a  lea     r9, [rsp+68h+pvar]; pvarDest
0x180011b9f  lea     r8, Delimiter; ","
0x180011ba6  lea     rdx, qword_18008C640; unsigned __int16 *
0x180011bad  mov     rcx, rdi; pvarSrc
0x180011bb0  call    ?ConvertVectorToDelimitedString@@YAJPEBUtagPROPVARIANT@@PEBG1PEAU1@@Z; ConvertVectorToDelimitedString(tagPROPVARIANT const *,ushort const *,ushort const *,tagPROPVARIANT *)
0x180011bb5  jmp     short loc_180011BE0
0x180011bb7  cmp     ebx, 3
0x180011bba  jnz     short loc_180011BD3
0x180011bbc  mov     ebx, 88982F8Eh
0x180011bc1  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180011bc8  jz      short loc_180011C2A
0x180011bca  mov     ecx, ebx; int
0x180011bcc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011bd1  jmp     short loc_180011C2A
0x180011bd3  mov     r8, rdi
0x180011bd6  mov     edx, ebx
0x180011bd8  mov     rcx, rbp
0x180011bdb  call    ?ConvertDataFormatOnWrite@CStringRuleWriter@@MEAAJW4DataFormats@@PEAUtagPROPVARIANT@@@Z; CStringRuleWriter::ConvertDataFormatOnWrite(DataFormats,tagPROPVARIANT *)
0x180011be0  test    eax, eax
0x180011be2  mov     ebx, eax
0x180011be4  jns     short loc_180011BF7
0x180011be6  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180011bed  jz      short loc_180011BF3
0x180011bef  mov     ecx, eax
0x180011bf1  jmp     short loc_180011BCC
0x180011bf3  test    eax, eax
0x180011bf5  js      short loc_180011C2A
0x180011bf7  cmp     word ptr [rsp+68h+pvar], r14w
0x180011bfd  jz      short loc_180011C2A
0x180011bff  mov     rcx, rdi; pvar
0x180011c02  call    cs:__imp_PropVariantClear
0x180011c08  movups  xmm0, xmmword ptr [rsp+68h+pvar]
0x180011c0d  movups  xmmword ptr [rdi], xmm0
0x180011c10  movsd   xmm1, qword ptr [rsp+68h+pvar+10h]
0x180011c16  movsd   qword ptr [rdi+10h], xmm1
0x180011c1b  xorps   xmm0, xmm0
0x180011c1e  xor     eax, eax
0x180011c20  movups  xmmword ptr [rsp+68h+pvar], xmm0
0x180011c25  mov     qword ptr [rsp+68h+pvar+10h], rax
0x180011c2a  lea     rcx, [rsp+68h+pvar]; pvar
0x180011c2f  call    cs:__imp_PropVariantClear
0x180011c35  mov     eax, ebx
0x180011c37  add     rsp, 40h
0x180011c3b  pop     r14
0x180011c3d  pop     rdi
0x180011c3e  pop     rsi
0x180011c3f  pop     rbp
0x180011c40  pop     rbx
0x180011c41  retn
```
