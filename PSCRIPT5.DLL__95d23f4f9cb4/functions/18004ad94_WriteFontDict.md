# WriteFontDict

- ea: `0x18004ad94`
- end: `0x18004b3a9`
- name: `WriteFontDict`
- size: `1557`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x18004db6c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180049adc`
- `0x180049cb0`
- `0x180049e14`
- `0x180049e54`
- `0x18004a05c`
- `0x18004a1a8`
- `0x18004a260`
- `0x18004a2e0`
- `0x18004aa14`
- `0x18004ad94`
- `0x18004b3b0`
- `0x18004b444`
- `0x18004b4b8`
- `0x18004b54c`
- `0x18004b5c4`
- `0x18004c390`
- `0x18005d010`

## string_xrefs

- `0x18004af52`: `Copyright`

## pseudocode

```c
__int64 __fastcall WriteFontDict(__int64 a1)
{
  int v2; // ecx
  int v3; // eax
  void (__fastcall *v4)(__int64, _DWORD *, __int64); // rax
  __int64 v5; // r8
  int i; // edi
  __int64 v7; // rdx
  int j; // edi
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-468h]
  _DWORD v12[4]; // [rsp+40h] [rbp-448h] BYREF
  char v13[1024]; // [rsp+50h] [rbp-438h] BYREF

  memset_0(v13, 0, sizeof(v13));
  PutString(a1, "%!FontType1\r\n");
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
  v11 = v2;
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(
    v13,
    1024,
    "%ld dict begin\r\n/FontInfo %ld dict dup begin\r\n",
    (*(_DWORD *)(a1 + 672) != 0)
  + (*(_DWORD *)(a1 + 1512) != 0)
  + (*(_DWORD *)(a1 + 1032) != 0)
  + (*(_DWORD *)(a1 + 828) != 0)
  + (*(_DWORD *)(a1 + 1140) != 0)
  + (*(_DWORD *)(a1 + 1124) != 0)
  + (v3 != 0 ? 25 : 10),
    v11);
  PutString(a1, v13);
  WriteSIDLine(a1, "Notice", *(unsigned int *)(a1 + 824), *(unsigned int *)(a1 + 820));
  WriteSIDLine(a1, "Copyright", *(unsigned int *)(a1 + 1492), *(unsigned int *)(a1 + 1488));
  WriteSIDLine(a1, "version", *(unsigned int *)(a1 + 684), *(unsigned int *)(a1 + 680));
  WriteSIDLine(a1, "FullName", *(unsigned int *)(a1 + 692), *(unsigned int *)(a1 + 688));
  WriteSIDLine(a1, "FamilyName", *(unsigned int *)(a1 + 700), *(unsigned int *)(a1 + 696));
  WriteSIDLine(a1, "BaseFontName", *(unsigned int *)(a1 + 708), *(unsigned int *)(a1 + 704));
  WriteNumberListLine(a1, "BaseFontBlend", a1 + 716, *(unsigned int *)(a1 + 712));
  WriteSIDLine(a1, "Weight", *(unsigned int *)(a1 + 784), *(unsigned int *)(a1 + 780));
  WriteBlendLine(a1, (unsigned int)"ItalicAngle", a1 + 1220, *(_DWORD *)(a1 + 1216), 1);
  WriteBlendBooleanLine(a1, (unsigned int)"isFixedPitch", a1 + 1288, *(_DWORD *)(a1 + 1284), 1, 0x8000);
  WriteBlendLine(a1, (unsigned int)"UnderlinePosition", a1 + 1356, *(_DWORD *)(a1 + 1352), 1);
  WriteBlendLine(a1, (unsigned int)"UnderlineThickness", a1 + 1424, *(_DWORD *)(a1 + 1420), 1);
  v4 = *(void (__fastcall **)(__int64, _DWORD *, __int64))(a1 + 440);
  if ( v4 )
  {
    v5 = *(_QWORD *)(a1 + 448);
    v12[0] = 0;
    v4(a1, v12, v5);
    if ( v12[0] != -1 )
      WriteLongNumberLine(a1, "FSType", v12[0], 1);
  }
  if ( *(_DWORD *)(a1 + 488) && *(_DWORD *)(a1 + 616) )
  {
    PutString(a1, "/BlendAxisTypes [");
    for ( i = 0; i < *(_DWORD *)(a1 + 616); ++i )
    {
      PutString(a1, "/");
      PutStringID(a1, *(unsigned __int16 *)(a1 + 4LL * i + 620));
      PutString(a1, " ");
    }
    PutString(a1, "] def\r\n");
  }
  PutString(a1, "end def\r\n");
  PutString(a1, "/FontName /");
  PutFontName(a1);
  PutString(a1, " def\r\n");
  if ( !(unsigned __int8)StreamKeyPointData(a1, 1) )
    WriteEncodingArray(a1);
  WriteNumberLine(a1, (unsigned int)"PaintType", *(_DWORD *)(a1 + 1128), *(_DWORD *)(a1 + 1124), 0);
  WriteLongNumberLine(a1, "FontType", *(unsigned __int8 *)(a1 + 7988), 1);
  WriteNumberListLine(a1, "DesignVector", a1 + 584, *(unsigned int *)(a1 + 580));
  WriteNumberListLine(a1, "NormDesignVector", a1 + 564, *(unsigned int *)(a1 + 560));
  WriteNumberListLine(a1, "WeightVector", a1 + 492, *(unsigned int *)(a1 + 488));
  if ( *(_DWORD *)(a1 + 488) )
  {
    PutString(a1, "/$Blend {");
    for ( j = 1; j < *(_DWORD *)(a1 + 488); ++j )
    {
      PutRoundedFixedNumber(a1, *(unsigned int *)(a1 + 4LL * j + 492));
      PutString(a1, "  mul ");
      if ( j > 1 )
        PutString(a1, "add ");
      if ( j < *(_DWORD *)(a1 + 488) - 1 )
        PutString(a1, "exch ");
    }
    PutString(a1, "add } bind def\r\n");
  }
  WriteFontMatrix(a1, v7, a1 + 832, *(unsigned int *)(a1 + 828));
  WriteBlendArrayLine(a1, (unsigned int)"FontBBox", a1 + 1516, *(_DWORD *)(a1 + 1512), 1, 0, 0);
  if ( !(unsigned __int8)StreamKeyPointData(a1, 2) )
    WriteLongNumberLine(a1, "UniqueID", *(unsigned int *)(a1 + 676), *(unsigned int *)(a1 + 672));
  if ( *(int *)(a1 + 1140) > 0 )
    WriteLongNumberListLine(a1, v9, a1 + 1144);
  WriteBlendLine(a1, (unsigned int)"StrokeWidth", a1 + 1036, *(_DWORD *)(a1 + 1032), 1);
  return PutString(a1, "currentdict end\r\n");
}

```

## disassembly

```asm
0x18004ad94  push    rbx
0x18004ad96  push    rbp
0x18004ad97  push    rsi
0x18004ad98  push    rdi
0x18004ad99  sub     rsp, 468h
0x18004ada0  mov     rax, cs:__security_cookie
0x18004ada7  xor     rax, rsp
0x18004adaa  mov     [rsp+488h+var_38], rax
0x18004adb2  mov     rbx, rcx
0x18004adb5  mov     edi, 400h
0x18004adba  mov     r8d, edi; Size
0x18004adbd  lea     rcx, [rsp+488h+var_438]; void *
0x18004adc2  xor     edx, edx; Val
0x18004adc4  call    memset_0
0x18004adc9  lea     rdx, aFonttype1; "%!FontType1\r\n"
0x18004add0  mov     rcx, rbx
0x18004add3  call    PutString
0x18004add8  xor     esi, esi
0x18004adda  cmp     [rbx+2B8h], esi
0x18004ade0  mov     eax, esi
0x18004ade2  mov     edx, esi
0x18004ade4  setnz   dl
0x18004ade7  cmp     [rbx+4C0h], esi
0x18004aded  setnz   al
0x18004adf0  add     edx, eax
0x18004adf2  mov     eax, esi
0x18004adf4  cmp     [rbx+268h], esi
0x18004adfa  setnz   al
0x18004adfd  add     edx, eax
0x18004adff  mov     eax, esi
0x18004ae01  cmp     [rbx+2B0h], esi
0x18004ae07  setnz   al
0x18004ae0a  add     edx, eax
0x18004ae0c  mov     eax, esi
0x18004ae0e  cmp     [rbx+30Ch], esi
0x18004ae14  setnz   al
0x18004ae17  add     edx, eax
0x18004ae19  mov     eax, esi
0x18004ae1b  cmp     [rbx+58Ch], esi
0x18004ae21  setnz   al
0x18004ae24  add     edx, eax
0x18004ae26  mov     eax, esi
0x18004ae28  cmp     [rbx+2A8h], esi
0x18004ae2e  setnz   al
0x18004ae31  add     edx, eax
0x18004ae33  mov     eax, esi
0x18004ae35  cmp     [rbx+2C8h], esi
0x18004ae3b  setnz   al
0x18004ae3e  add     edx, eax
0x18004ae40  mov     eax, esi
0x18004ae42  cmp     [rbx+548h], esi
0x18004ae48  setnz   al
0x18004ae4b  add     edx, eax
0x18004ae4d  mov     rax, [rbx+1B8h]
0x18004ae54  neg     rax
0x18004ae57  mov     eax, esi
0x18004ae59  sbb     ecx, ecx
0x18004ae5b  neg     ecx
0x18004ae5d  add     ecx, 5
0x18004ae60  add     ecx, edx
0x18004ae62  cmp     [rbx+5D0h], esi
0x18004ae68  setnz   al
0x18004ae6b  add     ecx, eax
0x18004ae6d  mov     eax, esi
0x18004ae6f  cmp     [rbx+334h], esi
0x18004ae75  setnz   al
0x18004ae78  add     ecx, eax
0x18004ae7a  mov     eax, esi
0x18004ae7c  cmp     [rbx+2C0h], esi
0x18004ae82  setnz   al
0x18004ae85  add     ecx, eax
0x18004ae87  mov     eax, esi
0x18004ae89  cmp     [rbx+504h], esi
0x18004ae8f  setnz   al
0x18004ae92  add     ecx, eax
0x18004ae94  mov     eax, [rbx+1E8h]
0x18004ae9a  test    eax, eax
0x18004ae9c  jz      short loc_18004AEA1
0x18004ae9e  add     ecx, 4
0x18004aea1  neg     eax
0x18004aea3  mov     [rsp+488h+var_468], ecx
0x18004aea7  mov     eax, esi
0x18004aea9  lea     r8, aLdDictBeginFon; "%ld dict begin\r\n/FontInfo %ld dict du"...
0x18004aeb0  sbb     r9d, r9d
0x18004aeb3  lea     rcx, [rsp+488h+var_438]
0x18004aeb8  and     r9d, 0Fh
0x18004aebc  mov     rdx, rdi
0x18004aebf  add     r9d, 0Ah
0x18004aec3  cmp     [rbx+464h], esi
0x18004aec9  setnz   al
0x18004aecc  add     r9d, eax
0x18004aecf  mov     eax, esi
0x18004aed1  cmp     [rbx+474h], esi
0x18004aed7  setnz   al
0x18004aeda  add     r9d, eax
0x18004aedd  mov     eax, esi
0x18004aedf  cmp     [rbx+33Ch], esi
0x18004aee5  setnz   al
0x18004aee8  add     r9d, eax
0x18004aeeb  mov     eax, esi
0x18004aeed  cmp     [rbx+408h], esi
0x18004aef3  setnz   al
0x18004aef6  add     r9d, eax
0x18004aef9  mov     eax, esi
0x18004aefb  cmp     [rbx+5E8h], esi
0x18004af01  setnz   al
0x18004af04  add     r9d, eax
0x18004af07  mov     eax, esi
0x18004af09  cmp     [rbx+2A0h], esi
0x18004af0f  setnz   al
0x18004af12  add     r9d, eax
0x18004af15  mov     rax, [rbx+168h]
0x18004af1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af21  lea     rdx, [rsp+488h+var_438]
0x18004af26  mov     rcx, rbx
0x18004af29  call    PutString
0x18004af2e  mov     r9d, [rbx+334h]
0x18004af35  lea     rdx, aNotice; "Notice"
0x18004af3c  mov     r8d, [rbx+338h]
0x18004af43  mov     rcx, rbx
0x18004af46  call    WriteSIDLine
0x18004af4b  mov     r9d, [rbx+5D0h]
0x18004af52  lea     rdx, aCopyright_0; "Copyright"
0x18004af59  mov     r8d, [rbx+5D4h]
0x18004af60  mov     rcx, rbx
0x18004af63  call    WriteSIDLine
0x18004af68  mov     r9d, [rbx+2A8h]
0x18004af6f  lea     rdx, aVersion_0; "version"
0x18004af76  mov     r8d, [rbx+2ACh]
0x18004af7d  mov     rcx, rbx
0x18004af80  call    WriteSIDLine
0x18004af85  mov     r9d, [rbx+2B0h]
0x18004af8c  lea     rdx, aFullname; "FullName"
0x18004af93  mov     r8d, [rbx+2B4h]
0x18004af9a  mov     rcx, rbx
0x18004af9d  call    WriteSIDLine
0x18004afa2  mov     r9d, [rbx+2B8h]
0x18004afa9  lea     rdx, aFamilyname; "FamilyName"
0x18004afb0  mov     r8d, [rbx+2BCh]
0x18004afb7  mov     rcx, rbx
0x18004afba  call    WriteSIDLine
0x18004afbf  mov     r9d, [rbx+2C0h]
0x18004afc6  lea     rdx, aBasefontname; "BaseFontName"
0x18004afcd  mov     r8d, [rbx+2C4h]
0x18004afd4  mov     rcx, rbx
0x18004afd7  call    WriteSIDLine
0x18004afdc  mov     r9d, [rbx+2C8h]
0x18004afe3  lea     r8, [rbx+2CCh]
0x18004afea  lea     rdx, aBasefontblend; "BaseFontBlend"
0x18004aff1  mov     rcx, rbx
0x18004aff4  call    WriteNumberListLine
0x18004aff9  mov     r9d, [rbx+30Ch]
0x18004b000  lea     rdx, aWeight; "Weight"
0x18004b007  mov     r8d, [rbx+310h]
0x18004b00e  mov     rcx, rbx
0x18004b011  call    WriteSIDLine
0x18004b016  mov     ebp, 1
0x18004b01b  mov     [rsp+488h+var_450], esi
0x18004b01f  mov     [rsp+488h+var_468], ebp
0x18004b023  lea     r8, [rbx+4C4h]
0x18004b02a  mov     r9d, [rbx+4C0h]
0x18004b031  lea     rdx, aItalicangle; "ItalicAngle"
0x18004b038  mov     rcx, rbx
0x18004b03b  call    WriteBlendLine
0x18004b040  mov     r9d, [rbx+504h]
0x18004b047  lea     r8, [rbx+508h]
0x18004b04e  lea     rdx, aIsfixedpitch; "isFixedPitch"
0x18004b055  mov     [rsp+488h+var_460], 8000h
0x18004b05d  mov     rcx, rbx
0x18004b060  mov     [rsp+488h+var_468], ebp
0x18004b064  call    WriteBlendBooleanLine
0x18004b069  mov     r9d, [rbx+548h]
0x18004b070  lea     r8, [rbx+54Ch]
0x18004b077  lea     rdx, aUnderlineposit; "UnderlinePosition"
0x18004b07e  mov     [rsp+488h+var_450], esi
0x18004b082  mov     rcx, rbx
0x18004b085  mov     [rsp+488h+var_468], ebp
0x18004b089  call    WriteBlendLine
0x18004b08e  mov     r9d, [rbx+58Ch]
0x18004b095  lea     r8, [rbx+590h]
0x18004b09c  lea     rdx, aUnderlinethick; "UnderlineThickness"
0x18004b0a3  mov     [rsp+488h+var_450], esi
0x18004b0a7  mov     rcx, rbx
0x18004b0aa  mov     [rsp+488h+var_468], ebp
0x18004b0ae  call    WriteBlendLine
0x18004b0b3  mov     rax, [rbx+1B8h]
0x18004b0ba  test    rax, rax
0x18004b0bd  jz      short loc_18004B0F4
0x18004b0bf  mov     r8, [rbx+1C0h]
0x18004b0c6  lea     rdx, [rsp+488h+var_448]
0x18004b0cb  mov     rcx, rbx
0x18004b0ce  mov     [rsp+488h+var_448], esi
0x18004b0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0d7  mov     r8d, [rsp+488h+var_448]
0x18004b0dc  cmp     r8d, 0FFFFFFFFh
0x18004b0e0  jz      short loc_18004B0F4
0x18004b0e2  mov     r9d, ebp
0x18004b0e5  lea     rdx, aFstype; "FSType"
0x18004b0ec  mov     rcx, rbx
0x18004b0ef  call    WriteLongNumberLine
0x18004b0f4  cmp     [rbx+1E8h], esi
0x18004b0fa  jz      short loc_18004B167
0x18004b0fc  cmp     [rbx+268h], esi
0x18004b102  jz      short loc_18004B167
0x18004b104  lea     rdx, aBlendaxistypes; "/BlendAxisTypes ["
0x18004b10b  mov     rcx, rbx
0x18004b10e  call    PutString
0x18004b113  mov     edi, esi
0x18004b115  cmp     [rbx+268h], esi
0x18004b11b  jle     short loc_18004B158
0x18004b11d  lea     rdx, asc_1800647FC; "/"
0x18004b124  mov     rcx, rbx
0x18004b127  call    PutString
0x18004b12c  movsxd  rdx, edi
0x18004b12f  mov     rcx, rbx
0x18004b132  movzx   edx, word ptr [rbx+rdx*4+26Ch]
0x18004b13a  call    PutStringID
0x18004b13f  lea     rdx, asc_180062A20; " "
0x18004b146  mov     rcx, rbx
0x18004b149  call    PutString
0x18004b14e  add     edi, ebp
0x18004b150  cmp     edi, [rbx+268h]
0x18004b156  jl      short loc_18004B11D
0x18004b158  lea     rdx, aDef_5; "] def\r\n"
0x18004b15f  mov     rcx, rbx
0x18004b162  call    PutString
0x18004b167  lea     rdx, aEndDef; "end def\r\n"
0x18004b16e  mov     rcx, rbx
0x18004b171  call    PutString
0x18004b176  lea     rdx, aFontname; "/FontName /"
0x18004b17d  mov     rcx, rbx
0x18004b180  call    PutString
0x18004b185  mov     rcx, rbx
0x18004b188  call    PutFontName
0x18004b18d  lea     rdx, aDef; " def\r\n"
0x18004b194  mov     rcx, rbx
0x18004b197  call    PutString
0x18004b19c  mov     edx, ebp
0x18004b19e  mov     rcx, rbx
0x18004b1a1  call    StreamKeyPointData
0x18004b1a6  test    al, al
0x18004b1a8  jnz     short loc_18004B1B2
0x18004b1aa  mov     rcx, rbx
0x18004b1ad  call    WriteEncodingArray
0x18004b1b2  mov     r9d, [rbx+464h]
0x18004b1b9  lea     rdx, aPainttype; "PaintType"
0x18004b1c0  mov     r8d, [rbx+468h]
0x18004b1c7  mov     rcx, rbx
0x18004b1ca  mov     [rsp+488h+var_468], esi
0x18004b1ce  call    WriteNumberLine
0x18004b1d3  movzx   r8d, byte ptr [rbx+1F34h]
0x18004b1db  lea     rdx, aFonttype; "FontType"
0x18004b1e2  mov     r9d, ebp
0x18004b1e5  mov     rcx, rbx
0x18004b1e8  call    WriteLongNumberLine
0x18004b1ed  mov     r9d, [rbx+244h]
0x18004b1f4  lea     r8, [rbx+248h]
0x18004b1fb  lea     rdx, aDesignvector; "DesignVector"
0x18004b202  mov     rcx, rbx
0x18004b205  call    WriteNumberListLine
0x18004b20a  mov     r9d, [rbx+230h]
0x18004b211  lea     r8, [rbx+234h]
0x18004b218  lea     rdx, aNormdesignvect; "NormDesignVector"
0x18004b21f  mov     rcx, rbx
0x18004b222  call    WriteNumberListLine
0x18004b227  mov     r9d, [rbx+1E8h]
0x18004b22e  lea     r8, [rbx+1ECh]
0x18004b235  lea     rdx, aWeightvector; "WeightVector"
0x18004b23c  mov     rcx, rbx
0x18004b23f  call    WriteNumberListLine
0x18004b244  cmp     [rbx+1E8h], esi
0x18004b24a  jz      loc_18004B2D1
0x18004b250  lea     rdx, aBlend; "/$Blend {"
0x18004b257  mov     rcx, rbx
0x18004b25a  call    PutString
0x18004b25f  mov     edi, ebp
0x18004b261  cmp     [rbx+1E8h], ebp
0x18004b267  jle     short loc_18004B2C2
0x18004b269  movsxd  rdx, edi
0x18004b26c  mov     rcx, rbx
0x18004b26f  mov     edx, [rbx+rdx*4+1ECh]
0x18004b276  call    PutRoundedFixedNumber
0x18004b27b  lea     rdx, aMul; "  mul "
0x18004b282  mov     rcx, rbx
0x18004b285  call    PutString
0x18004b28a  cmp     edi, ebp
0x18004b28c  jle     short loc_18004B29D
0x18004b28e  lea     rdx, aAdd; "add "
0x18004b295  mov     rcx, rbx
0x18004b298  call    PutString
0x18004b29d  mov     eax, [rbx+1E8h]
0x18004b2a3  sub     eax, ebp
0x18004b2a5  cmp     edi, eax
0x18004b2a7  jge     short loc_18004B2B8
0x18004b2a9  lea     rdx, aExch; "exch "
0x18004b2b0  mov     rcx, rbx
0x18004b2b3  call    PutString
0x18004b2b8  add     edi, ebp
0x18004b2ba  cmp     edi, [rbx+1E8h]
0x18004b2c0  jl      short loc_18004B269
  ... truncated ...
```
