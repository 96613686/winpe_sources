# WriteFontDict

- ea: `0x18004c618`
- end: `0x18004cc2e`
- name: `WriteFontDict`
- size: `1558`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x18004f3fc`

## callees

- `0x180001f20`
- `0x180002938`
- `0x18004b354`
- `0x18004b52c`
- `0x18004b690`
- `0x18004b6d0`
- `0x18004b8d8`
- `0x18004ba24`
- `0x18004badc`
- `0x18004bb5c`
- `0x18004c294`
- `0x18004c618`
- `0x18004cc34`
- `0x18004cccc`
- `0x18004cd40`
- `0x18004cdd4`
- `0x18004ce4c`
- `0x18004dc18`
- `0x18005f010`

## string_xrefs

- `0x18004c7d6`: `Copyright`

## pseudocode

```c
__int64 __fastcall WriteFontDict(__int64 a1)
{
  int v2; // ecx
  int v3; // eax
  void (__fastcall *v4)(__int64, unsigned int *, __int64); // rax
  __int64 v5; // r8
  int i; // edi
  __int64 v7; // rdx
  int j; // edi
  __int64 v9; // rdx
  int v10; // r9d
  int v12; // [rsp+20h] [rbp-468h]
  int v13; // [rsp+28h] [rbp-460h]
  int v14; // [rsp+28h] [rbp-460h]
  int v15; // [rsp+28h] [rbp-460h]
  int v16; // [rsp+28h] [rbp-460h]
  int v17; // [rsp+30h] [rbp-458h]
  int v18; // [rsp+30h] [rbp-458h]
  int v19; // [rsp+30h] [rbp-458h]
  int v20; // [rsp+30h] [rbp-458h]
  unsigned int v21[4]; // [rsp+40h] [rbp-448h] BYREF
  _BYTE v22[1024]; // [rsp+50h] [rbp-438h] BYREF

  memset_0(v22, 0, sizeof(v22));
  PutString(a1, (__int64)"%!FontType1\r\n");
  v2 = (*(_DWORD *)(a1 + 1284) != 0)
     + (*(_DWORD *)(a1 + 704) != 0)
     + (*(_DWORD *)(a1 + 820) != 0)
     + (*(_DWORD *)(a1 + 1488) != 0)
     + (*(_DWORD *)(a1 + 1352) != 0)
     + (*(_DWORD *)(a1 + 712) != 0)
     + (*(_DWORD *)(a1 + 680) != 0)
     + (*(_DWORD *)(a1 + 1420) != 0)
     + (*(_DWORD *)(a1 + 780) != 0)
     + (*(_DWORD *)(a1 + 688) != 0)
     + (*(_DWORD *)(a1 + 616) != 0)
     + (*(_DWORD *)(a1 + 1216) != 0)
     + (*(_DWORD *)(a1 + 696) != 0)
     + (*(_QWORD *)(a1 + 440) != 0)
     + 5;
  v3 = *(_DWORD *)(a1 + 488);
  if ( v3 )
    v2 += 4;
  v12 = v2;
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(
    v22,
    1024,
    "%ld dict begin\r\n/FontInfo %ld dict dup begin\r\n",
    (*(_DWORD *)(a1 + 672) != 0)
  + (*(_DWORD *)(a1 + 1512) != 0)
  + (*(_DWORD *)(a1 + 1032) != 0)
  + (*(_DWORD *)(a1 + 828) != 0)
  + (*(_DWORD *)(a1 + 1140) != 0)
  + (*(_DWORD *)(a1 + 1124) != 0)
  + (v3 != 0 ? 25 : 10),
    v12);
  PutString(a1, (__int64)v22);
  WriteSIDLine(a1, (__int64)"Notice", *(_DWORD *)(a1 + 824), *(_DWORD *)(a1 + 820));
  WriteSIDLine(a1, (__int64)"Copyright", *(_DWORD *)(a1 + 1492), *(_DWORD *)(a1 + 1488));
  WriteSIDLine(a1, (__int64)"version", *(_DWORD *)(a1 + 684), *(_DWORD *)(a1 + 680));
  WriteSIDLine(a1, (__int64)"FullName", *(_DWORD *)(a1 + 692), *(_DWORD *)(a1 + 688));
  WriteSIDLine(a1, (__int64)"FamilyName", *(_DWORD *)(a1 + 700), *(_DWORD *)(a1 + 696));
  WriteSIDLine(a1, (__int64)"BaseFontName", *(_DWORD *)(a1 + 708), *(_DWORD *)(a1 + 704));
  WriteNumberListLine(a1, (__int64)"BaseFontBlend", a1 + 716, *(_DWORD *)(a1 + 712));
  WriteSIDLine(a1, (__int64)"Weight", *(_DWORD *)(a1 + 784), *(_DWORD *)(a1 + 780));
  WriteBlendLine(a1, (__int64)"ItalicAngle", (unsigned int *)(a1 + 1220), *(_DWORD *)(a1 + 1216), 1, v13, v17, 0);
  WriteBlendBooleanLine(a1, (__int64)"isFixedPitch", (_DWORD *)(a1 + 1288), *(_DWORD *)(a1 + 1284), 1, 0x8000);
  WriteBlendLine(a1, (__int64)"UnderlinePosition", (unsigned int *)(a1 + 1356), *(_DWORD *)(a1 + 1352), 1, v14, v18, 0);
  WriteBlendLine(a1, (__int64)"UnderlineThickness", (unsigned int *)(a1 + 1424), *(_DWORD *)(a1 + 1420), 1, v15, v19, 0);
  v4 = *(void (__fastcall **)(__int64, unsigned int *, __int64))(a1 + 440);
  if ( v4 )
  {
    v5 = *(_QWORD *)(a1 + 448);
    v21[0] = 0;
    v4(a1, v21, v5);
    if ( v21[0] != -1 )
      WriteLongNumberLine(a1, (__int64)"FSType", v21[0], 1);
  }
  if ( *(_DWORD *)(a1 + 488) && *(_DWORD *)(a1 + 616) )
  {
    PutString(a1, (__int64)"/BlendAxisTypes [");
    for ( i = 0; i < *(_DWORD *)(a1 + 616); ++i )
    {
      PutString(a1, (__int64)"/");
      PutStringID(a1, *(_WORD *)(a1 + 4LL * i + 620));
      PutString(a1, (__int64)" ");
    }
    PutString(a1, (__int64)"] def\r\n");
  }
  PutString(a1, (__int64)"end def\r\n");
  PutString(a1, (__int64)"/FontName /");
  PutFontName(a1);
  PutString(a1, (__int64)" def\r\n");
  if ( !StreamKeyPointData(a1, 1) )
    WriteEncodingArray(a1);
  WriteNumberLine(a1, (__int64)"PaintType", *(_DWORD *)(a1 + 1128), *(_DWORD *)(a1 + 1124), 0);
  WriteLongNumberLine(a1, (__int64)"FontType", *(unsigned __int8 *)(a1 + 7988), 1);
  WriteNumberListLine(a1, (__int64)"DesignVector", a1 + 584, *(_DWORD *)(a1 + 580));
  WriteNumberListLine(a1, (__int64)"NormDesignVector", a1 + 564, *(_DWORD *)(a1 + 560));
  WriteNumberListLine(a1, (__int64)"WeightVector", a1 + 492, *(_DWORD *)(a1 + 488));
  if ( *(_DWORD *)(a1 + 488) )
  {
    PutString(a1, (__int64)"/$Blend {");
    for ( j = 1; j < *(_DWORD *)(a1 + 488); ++j )
    {
      PutRoundedFixedNumber(a1, *(_DWORD *)(a1 + 4LL * j + 492));
      PutString(a1, (__int64)"  mul ");
      if ( j > 1 )
        PutString(a1, (__int64)"add ");
      if ( j < *(_DWORD *)(a1 + 488) - 1 )
        PutString(a1, (__int64)"exch ");
    }
    PutString(a1, (__int64)"add } bind def\r\n");
  }
  WriteFontMatrix(a1, v7, a1 + 832, *(_DWORD *)(a1 + 828));
  WriteBlendArrayLine(a1, (__int64)"FontBBox", a1 + 1516, *(_DWORD *)(a1 + 1512), 1, 0, 0);
  if ( !StreamKeyPointData(a1, 2) )
    WriteLongNumberLine(a1, (__int64)"UniqueID", *(_DWORD *)(a1 + 676), *(_DWORD *)(a1 + 672));
  v10 = *(_DWORD *)(a1 + 1140);
  if ( v10 > 0 )
    WriteLongNumberListLine(a1, v9, a1 + 1144, v10);
  WriteBlendLine(a1, (__int64)"StrokeWidth", (unsigned int *)(a1 + 1036), *(_DWORD *)(a1 + 1032), 1, v16, v20, 0);
  return PutString(a1, (__int64)"currentdict end\r\n");
}

```

## disassembly

```asm
0x18004c618  push    rbx
0x18004c61a  push    rbp
0x18004c61b  push    rsi
0x18004c61c  push    rdi
0x18004c61d  sub     rsp, 468h
0x18004c624  mov     rax, cs:__security_cookie
0x18004c62b  xor     rax, rsp
0x18004c62e  mov     [rsp+488h+var_38], rax
0x18004c636  mov     rbx, rcx
0x18004c639  mov     edi, 400h
0x18004c63e  mov     r8d, edi; Size
0x18004c641  lea     rcx, [rsp+488h+var_438]; void *
0x18004c646  xor     edx, edx; Val
0x18004c648  call    memset_0
0x18004c64d  lea     rdx, aFonttype1; "%!FontType1\r\n"
0x18004c654  mov     rcx, rbx
0x18004c657  call    PutString
0x18004c65c  xor     esi, esi
0x18004c65e  cmp     [rbx+2B8h], esi
0x18004c664  mov     eax, esi
0x18004c666  mov     edx, esi
0x18004c668  setnz   dl
0x18004c66b  cmp     [rbx+4C0h], esi
0x18004c671  setnz   al
0x18004c674  add     edx, eax
0x18004c676  mov     eax, esi
0x18004c678  cmp     [rbx+268h], esi
0x18004c67e  setnz   al
0x18004c681  add     edx, eax
0x18004c683  mov     eax, esi
0x18004c685  cmp     [rbx+2B0h], esi
0x18004c68b  setnz   al
0x18004c68e  add     edx, eax
0x18004c690  mov     eax, esi
0x18004c692  cmp     [rbx+30Ch], esi
0x18004c698  setnz   al
0x18004c69b  add     edx, eax
0x18004c69d  mov     eax, esi
0x18004c69f  cmp     [rbx+58Ch], esi
0x18004c6a5  setnz   al
0x18004c6a8  add     edx, eax
0x18004c6aa  mov     eax, esi
0x18004c6ac  cmp     [rbx+2A8h], esi
0x18004c6b2  setnz   al
0x18004c6b5  add     edx, eax
0x18004c6b7  mov     eax, esi
0x18004c6b9  cmp     [rbx+2C8h], esi
0x18004c6bf  setnz   al
0x18004c6c2  add     edx, eax
0x18004c6c4  mov     eax, esi
0x18004c6c6  cmp     [rbx+548h], esi
0x18004c6cc  setnz   al
0x18004c6cf  add     edx, eax
0x18004c6d1  mov     rax, [rbx+1B8h]
0x18004c6d8  neg     rax
0x18004c6db  mov     eax, esi
0x18004c6dd  sbb     ecx, ecx
0x18004c6df  neg     ecx
0x18004c6e1  add     ecx, 5
0x18004c6e4  add     ecx, edx
0x18004c6e6  cmp     [rbx+5D0h], esi
0x18004c6ec  setnz   al
0x18004c6ef  add     ecx, eax
0x18004c6f1  mov     eax, esi
0x18004c6f3  cmp     [rbx+334h], esi
0x18004c6f9  setnz   al
0x18004c6fc  add     ecx, eax
0x18004c6fe  mov     eax, esi
0x18004c700  cmp     [rbx+2C0h], esi
0x18004c706  setnz   al
0x18004c709  add     ecx, eax
0x18004c70b  mov     eax, esi
0x18004c70d  cmp     [rbx+504h], esi
0x18004c713  setnz   al
0x18004c716  add     ecx, eax
0x18004c718  mov     eax, [rbx+1E8h]
0x18004c71e  test    eax, eax
0x18004c720  jz      short loc_18004C725
0x18004c722  add     ecx, 4
0x18004c725  neg     eax
0x18004c727  mov     [rsp+488h+var_468], ecx
0x18004c72b  mov     eax, esi
0x18004c72d  lea     r8, aLdDictBeginFon; "%ld dict begin\r\n/FontInfo %ld dict du"...
0x18004c734  sbb     r9d, r9d
0x18004c737  lea     rcx, [rsp+488h+var_438]
0x18004c73c  and     r9d, 0Fh
0x18004c740  mov     rdx, rdi
0x18004c743  add     r9d, 0Ah
0x18004c747  cmp     [rbx+464h], esi
0x18004c74d  setnz   al
0x18004c750  add     r9d, eax
0x18004c753  mov     eax, esi
0x18004c755  cmp     [rbx+474h], esi
0x18004c75b  setnz   al
0x18004c75e  add     r9d, eax
0x18004c761  mov     eax, esi
0x18004c763  cmp     [rbx+33Ch], esi
0x18004c769  setnz   al
0x18004c76c  add     r9d, eax
0x18004c76f  mov     eax, esi
0x18004c771  cmp     [rbx+408h], esi
0x18004c777  setnz   al
0x18004c77a  add     r9d, eax
0x18004c77d  mov     eax, esi
0x18004c77f  cmp     [rbx+5E8h], esi
0x18004c785  setnz   al
0x18004c788  add     r9d, eax
0x18004c78b  mov     eax, esi
0x18004c78d  cmp     [rbx+2A0h], esi
0x18004c793  setnz   al
0x18004c796  add     r9d, eax
0x18004c799  mov     rax, [rbx+168h]
0x18004c7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7a5  lea     rdx, [rsp+488h+var_438]
0x18004c7aa  mov     rcx, rbx
0x18004c7ad  call    PutString
0x18004c7b2  mov     r9d, [rbx+334h]
0x18004c7b9  lea     rdx, aNotice; "Notice"
0x18004c7c0  mov     r8d, [rbx+338h]
0x18004c7c7  mov     rcx, rbx
0x18004c7ca  call    WriteSIDLine
0x18004c7cf  mov     r9d, [rbx+5D0h]
0x18004c7d6  lea     rdx, aCopyright_0; "Copyright"
0x18004c7dd  mov     r8d, [rbx+5D4h]
0x18004c7e4  mov     rcx, rbx
0x18004c7e7  call    WriteSIDLine
0x18004c7ec  mov     r9d, [rbx+2A8h]
0x18004c7f3  lea     rdx, aVersion_0; "version"
0x18004c7fa  mov     r8d, [rbx+2ACh]
0x18004c801  mov     rcx, rbx
0x18004c804  call    WriteSIDLine
0x18004c809  mov     r9d, [rbx+2B0h]
0x18004c810  lea     rdx, aFullname; "FullName"
0x18004c817  mov     r8d, [rbx+2B4h]
0x18004c81e  mov     rcx, rbx
0x18004c821  call    WriteSIDLine
0x18004c826  mov     r9d, [rbx+2B8h]
0x18004c82d  lea     rdx, aFamilyname; "FamilyName"
0x18004c834  mov     r8d, [rbx+2BCh]
0x18004c83b  mov     rcx, rbx
0x18004c83e  call    WriteSIDLine
0x18004c843  mov     r9d, [rbx+2C0h]
0x18004c84a  lea     rdx, aBasefontname; "BaseFontName"
0x18004c851  mov     r8d, [rbx+2C4h]
0x18004c858  mov     rcx, rbx
0x18004c85b  call    WriteSIDLine
0x18004c860  mov     r9d, [rbx+2C8h]
0x18004c867  lea     r8, [rbx+2CCh]
0x18004c86e  lea     rdx, aBasefontblend; "BaseFontBlend"
0x18004c875  mov     rcx, rbx
0x18004c878  call    WriteNumberListLine
0x18004c87d  mov     r9d, [rbx+30Ch]
0x18004c884  lea     rdx, aWeight; "Weight"
0x18004c88b  mov     r8d, [rbx+310h]
0x18004c892  mov     rcx, rbx
0x18004c895  call    WriteSIDLine
0x18004c89a  mov     ebp, 1
0x18004c89f  mov     [rsp+488h+var_450], esi
0x18004c8a3  mov     [rsp+488h+var_468], ebp
0x18004c8a7  lea     r8, [rbx+4C4h]
0x18004c8ae  mov     r9d, [rbx+4C0h]
0x18004c8b5  lea     rdx, aItalicangle; "ItalicAngle"
0x18004c8bc  mov     rcx, rbx
0x18004c8bf  call    WriteBlendLine
0x18004c8c4  mov     r9d, [rbx+504h]
0x18004c8cb  lea     r8, [rbx+508h]
0x18004c8d2  lea     rdx, aIsfixedpitch; "isFixedPitch"
0x18004c8d9  mov     [rsp+488h+var_460], 8000h
0x18004c8e1  mov     rcx, rbx
0x18004c8e4  mov     [rsp+488h+var_468], ebp
0x18004c8e8  call    WriteBlendBooleanLine
0x18004c8ed  mov     r9d, [rbx+548h]
0x18004c8f4  lea     r8, [rbx+54Ch]
0x18004c8fb  lea     rdx, aUnderlineposit; "UnderlinePosition"
0x18004c902  mov     [rsp+488h+var_450], esi
0x18004c906  mov     rcx, rbx
0x18004c909  mov     [rsp+488h+var_468], ebp
0x18004c90d  call    WriteBlendLine
0x18004c912  mov     r9d, [rbx+58Ch]
0x18004c919  lea     r8, [rbx+590h]
0x18004c920  lea     rdx, aUnderlinethick; "UnderlineThickness"
0x18004c927  mov     [rsp+488h+var_450], esi
0x18004c92b  mov     rcx, rbx
0x18004c92e  mov     [rsp+488h+var_468], ebp
0x18004c932  call    WriteBlendLine
0x18004c937  mov     rax, [rbx+1B8h]
0x18004c93e  test    rax, rax
0x18004c941  jz      short loc_18004C978
0x18004c943  mov     r8, [rbx+1C0h]
0x18004c94a  lea     rdx, [rsp+488h+var_448]
0x18004c94f  mov     rcx, rbx
0x18004c952  mov     [rsp+488h+var_448], esi
0x18004c956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c95b  mov     r8d, [rsp+488h+var_448]
0x18004c960  cmp     r8d, 0FFFFFFFFh
0x18004c964  jz      short loc_18004C978
0x18004c966  mov     r9d, ebp
0x18004c969  lea     rdx, aFstype; "FSType"
0x18004c970  mov     rcx, rbx
0x18004c973  call    WriteLongNumberLine
0x18004c978  cmp     [rbx+1E8h], esi
0x18004c97e  jz      short loc_18004C9EB
0x18004c980  cmp     [rbx+268h], esi
0x18004c986  jz      short loc_18004C9EB
0x18004c988  lea     rdx, aBlendaxistypes; "/BlendAxisTypes ["
0x18004c98f  mov     rcx, rbx
0x18004c992  call    PutString
0x18004c997  mov     edi, esi
0x18004c999  cmp     [rbx+268h], esi
0x18004c99f  jle     short loc_18004C9DC
0x18004c9a1  lea     rdx, asc_1800667DC; "/"
0x18004c9a8  mov     rcx, rbx
0x18004c9ab  call    PutString
0x18004c9b0  movsxd  rdx, edi
0x18004c9b3  mov     rcx, rbx
0x18004c9b6  movzx   edx, word ptr [rbx+rdx*4+26Ch]
0x18004c9be  call    PutStringID
0x18004c9c3  lea     rdx, asc_180064A10; " "
0x18004c9ca  mov     rcx, rbx
0x18004c9cd  call    PutString
0x18004c9d2  add     edi, ebp
0x18004c9d4  cmp     edi, [rbx+268h]
0x18004c9da  jl      short loc_18004C9A1
0x18004c9dc  lea     rdx, aDef_5; "] def\r\n"
0x18004c9e3  mov     rcx, rbx
0x18004c9e6  call    PutString
0x18004c9eb  lea     rdx, aEndDef; "end def\r\n"
0x18004c9f2  mov     rcx, rbx
0x18004c9f5  call    PutString
0x18004c9fa  lea     rdx, aFontname; "/FontName /"
0x18004ca01  mov     rcx, rbx
0x18004ca04  call    PutString
0x18004ca09  mov     rcx, rbx
0x18004ca0c  call    PutFontName
0x18004ca11  lea     rdx, aDef; " def\r\n"
0x18004ca18  mov     rcx, rbx
0x18004ca1b  call    PutString
0x18004ca20  mov     edx, ebp
0x18004ca22  mov     rcx, rbx
0x18004ca25  call    StreamKeyPointData
0x18004ca2a  test    al, al
0x18004ca2c  jnz     short loc_18004CA36
0x18004ca2e  mov     rcx, rbx
0x18004ca31  call    WriteEncodingArray
0x18004ca36  mov     r9d, [rbx+464h]
0x18004ca3d  lea     rdx, aPainttype; "PaintType"
0x18004ca44  mov     r8d, [rbx+468h]
0x18004ca4b  mov     rcx, rbx
0x18004ca4e  mov     [rsp+488h+var_468], esi
0x18004ca52  call    WriteNumberLine
0x18004ca57  movzx   r8d, byte ptr [rbx+1F34h]
0x18004ca5f  lea     rdx, aFonttype; "FontType"
0x18004ca66  mov     r9d, ebp
0x18004ca69  mov     rcx, rbx
0x18004ca6c  call    WriteLongNumberLine
0x18004ca71  mov     r9d, [rbx+244h]
0x18004ca78  lea     r8, [rbx+248h]
0x18004ca7f  lea     rdx, aDesignvector; "DesignVector"
0x18004ca86  mov     rcx, rbx
0x18004ca89  call    WriteNumberListLine
0x18004ca8e  mov     r9d, [rbx+230h]
0x18004ca95  lea     r8, [rbx+234h]
0x18004ca9c  lea     rdx, aNormdesignvect; "NormDesignVector"
0x18004caa3  mov     rcx, rbx
0x18004caa6  call    WriteNumberListLine
0x18004caab  mov     r9d, [rbx+1E8h]
0x18004cab2  lea     r8, [rbx+1ECh]
0x18004cab9  lea     rdx, aWeightvector; "WeightVector"
0x18004cac0  mov     rcx, rbx
0x18004cac3  call    WriteNumberListLine
0x18004cac8  cmp     [rbx+1E8h], esi
0x18004cace  jz      loc_18004CB55
0x18004cad4  lea     rdx, aBlend; "/$Blend {"
0x18004cadb  mov     rcx, rbx
0x18004cade  call    PutString
0x18004cae3  mov     edi, ebp
0x18004cae5  cmp     [rbx+1E8h], ebp
0x18004caeb  jle     short loc_18004CB46
0x18004caed  movsxd  rdx, edi
0x18004caf0  mov     rcx, rbx
0x18004caf3  mov     edx, [rbx+rdx*4+1ECh]
0x18004cafa  call    PutRoundedFixedNumber
0x18004caff  lea     rdx, aMul; "  mul "
0x18004cb06  mov     rcx, rbx
0x18004cb09  call    PutString
0x18004cb0e  cmp     edi, ebp
0x18004cb10  jle     short loc_18004CB21
0x18004cb12  lea     rdx, aAdd; "add "
0x18004cb19  mov     rcx, rbx
0x18004cb1c  call    PutString
0x18004cb21  mov     eax, [rbx+1E8h]
0x18004cb27  sub     eax, ebp
0x18004cb29  cmp     edi, eax
0x18004cb2b  jge     short loc_18004CB3C
0x18004cb2d  lea     rdx, aExch; "exch "
0x18004cb34  mov     rcx, rbx
0x18004cb37  call    PutString
0x18004cb3c  add     edi, ebp
0x18004cb3e  cmp     edi, [rbx+1E8h]
0x18004cb44  jl      short loc_18004CAED
  ... truncated ...
```
