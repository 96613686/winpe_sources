# XT1_WriteCIDDict

- ea: `0x18004cc6c`
- end: `0x18004d184`
- name: `XT1_WriteCIDDict`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180046ce0`

## callees

- `0x180001ee0`
- `0x18004957c`
- `0x180049e14`
- `0x180049e54`
- `0x18004a1a8`
- `0x18004a2e0`
- `0x18004ab80`
- `0x18004b3b0`
- `0x18004b444`
- `0x18004b54c`
- `0x18004c470`
- `0x18004cc6c`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall XT1_WriteCIDDict(__int64 a1, unsigned __int16 a2, unsigned int a3, unsigned __int16 a4)
{
  double v4; // xmm2_8
  double v5; // xmm3_8
  unsigned int v7; // edi
  __int64 v9; // rdx
  unsigned int v10; // eax
  int v11; // eax
  char v12; // al
  __int64 v13; // r8
  __int64 v14; // r9
  char v16[1024]; // [rsp+40h] [rbp-448h] BYREF

  v7 = a4;
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v16, 1024, "dup %d\r\n", a2);
  PutString(a1, v16);
  PutString(a1, "\r\n");
  PutString(a1, "%ADOBeginFontDict", v4);
  PutString(a1, "\r\n");
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(
    v16,
    1024,
    "%ld dict\r\nbegin",
    (*(_DWORD *)(a1 + 1124) != 0)
  + (*(_DWORD *)(a1 + 828) != 0)
  + (*(_DWORD *)(a1 + 488) != 0 ? 25 : 10)
  + (*(_DWORD *)(a1 + 672) != 0)
  + (*(_DWORD *)(a1 + 1032) != 0)
  + (*(_DWORD *)(a1 + 1140) != 0)
  + (unsigned int)(*(_DWORD *)(a1 + 1512) != 0));
  PutString(a1, v16);
  PutString(a1, "\r\n");
  if ( *(_DWORD *)(a1 + 7740) )
  {
    PutString(a1, "/FontName /");
    PutStringID(a1, *(unsigned __int16 *)(a1 + 7744));
    PutString(a1, " def");
    PutString(a1, "\r\n");
  }
  WriteLongNumberLine(a1, "FontType", *(unsigned __int8 *)(a1 + 7988), 1);
  WriteFontMatrix(a1, v9, a1 + 832, *(unsigned int *)(a1 + 828));
  WriteNumberLine(a1, (unsigned int)"PaintType", *(_DWORD *)(a1 + 1128), *(_DWORD *)(a1 + 1124), 0);
  PutString(a1, "\r\n%ADOBeginPrivateDict", v4);
  PutString(a1, "\r\n");
  v10 = PrivateDictCount(a1);
  (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v16, 1024, "/Private %ld dict dup\r\nbegin", v10);
  PutString(a1, v16);
  PutString(a1, "\r\n");
  PutString(a1, "/MinFeature {16 16} def");
  PutString(a1, "\r\n");
  v11 = *(_DWORD *)(a1 + 1500);
  if ( v11 == 2 )
  {
    v12 = *(_BYTE *)(a1 + 7988);
    if ( v12 == 1 )
    {
      v13 = (unsigned int)*(__int16 *)(a1 + 7976);
      v14 = 1;
LABEL_11:
      WriteLongNumberLine(a1, "lenIV", v13, v14);
      goto LABEL_12;
    }
    if ( v12 == 2 )
    {
      v14 = 1;
      v13 = 0xFFFFFFFFLL;
      goto LABEL_11;
    }
  }
  else if ( v11 == 1 && *(_BYTE *)(a1 + 7988) == 1 )
  {
    v14 = *(unsigned int *)(a1 + 1116);
    v13 = *(unsigned int *)(a1 + 1120);
    goto LABEL_11;
  }
LABEL_12:
  WriteLongNumberLine(a1, "LanguageGroup", *(unsigned int *)(a1 + 1136), *(unsigned int *)(a1 + 1132));
  if ( *(_DWORD *)(a1 + 1132) && *(_DWORD *)(a1 + 1136) == 1 )
    PutString(a1, "/RndStemUp false def\r\n");
  if ( *(_DWORD *)(a1 + 1500) == 2 && *(_BYTE *)(a1 + 7988) == 2 )
  {
    WriteNumberLine(a1, (unsigned int)"defaultWidthX", *(_DWORD *)(a1 + 808), *(_DWORD *)(a1 + 804), 0);
    WriteNumberLine(a1, (unsigned int)"nominalWidthX", *(_DWORD *)(a1 + 816), *(_DWORD *)(a1 + 812), 0);
  }
  if ( !*(_DWORD *)(a1 + 1908) )
    PutString(a1, "/BlueValues [ ] def\r\n");
  WriteBlendArrayLine(a1, (unsigned int)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 1, 1, 1);
  WriteBlendArrayLine(a1, (unsigned int)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 1, 1, 1);
  WriteBlendLine(a1, (unsigned int)"BlueScale", a1 + 6544, *(_DWORD *)(a1 + 6540), 1);
  WriteBlendLine(a1, (unsigned int)"BlueShift", a1 + 6612, *(_DWORD *)(a1 + 6608), 1);
  WriteBlendLine(a1, (unsigned int)"BlueFuzz", a1 + 6680, *(_DWORD *)(a1 + 6676), 1);
  WriteStemSnap(a1, 1);
  PutString(
    a1,
    "\r\n"
    "/OtherSubrs [ {} {} {} { systemdict /internaldict known not\r\n"
    "{ pop 3 } { 1183615869 systemdict /internaldict get exec dup\r\n"
    "/startlock known { /startlock get exec }\r\n"
    "{ dup /strtlck known { /strtlck get exec } { pop 3 } ifelse } ifelse } ifelse } bind\r\n"
    "{} {} {} {} {} {} {} {} {}\r\n"
    "{ 2 {cvi { { pop 0 lt { exit } if } loop } repeat } repeat } bind\r\n"
    "{} {} {} {} {} {} {} {} {} {} {} {} {} {} {} ] def");
  PutString(a1, "\r\n");
  WriteErode(a1, 1);
  PutString(a1, "\r\n/password 5839 def\r\n");
  PutString(a1, "\r\n");
  if ( (_WORD)v7 )
  {
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v16, 1024, "/SubrMapOffset %d def", a3);
    PutString(a1, v16);
    PutString(a1, "\r\n");
    PutString(a1, "/SDBytes 4 def");
    PutString(a1, "\r\n");
    (*(void (**)(char *, __int64, const char *, ...))(a1 + 360))(v16, 1024, "/SubrCount %d def", v7);
    PutString(a1, v16);
    PutString(a1, "\r\n");
  }
  PutString(a1, "end def\r\n%ADOEndPrivateDict\r\n\r\ncurrentdict\r\nend\r\n%ADOEndFontDict\r\n\r\nput", v4, v5);
  return PutString(a1, "\r\n");
}

```

## disassembly

```asm
0x18004cc6c  push    rbx
0x18004cc6e  push    rbp
0x18004cc6f  push    rsi
0x18004cc70  push    rdi
0x18004cc71  push    r12
0x18004cc73  push    r14
0x18004cc75  push    r15
0x18004cc77  sub     rsp, 450h
0x18004cc7e  mov     rax, cs:__security_cookie
0x18004cc85  xor     rax, rsp
0x18004cc88  mov     [rsp+488h+var_48], rax
0x18004cc90  mov     rbx, rcx
0x18004cc93  movzx   edi, r9w
0x18004cc97  mov     esi, r8d
0x18004cc9a  movzx   r9d, dx
0x18004cc9e  mov     r12d, 400h
0x18004cca4  lea     r8, aDupD_0; "dup %d\r\n"
0x18004ccab  mov     edx, r12d
0x18004ccae  lea     rcx, [rsp+488h+var_448]
0x18004ccb3  mov     rax, [rbx+168h]
0x18004ccba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ccbf  lea     rdx, [rsp+488h+var_448]
0x18004ccc4  mov     rcx, rbx
0x18004ccc7  call    PutString
0x18004cccc  lea     r15, asc_180062FDC; "\r\n"
0x18004ccd3  mov     rcx, rbx
0x18004ccd6  mov     rdx, r15
0x18004ccd9  call    PutString
0x18004ccde  lea     rdx, aAdobeginfontdi; "%ADOBeginFontDict"
0x18004cce5  mov     rcx, rbx
0x18004cce8  call    PutString
0x18004cced  mov     rdx, r15
0x18004ccf0  mov     rcx, rbx
0x18004ccf3  call    PutString
0x18004ccf8  xor     r14d, r14d
0x18004ccfb  lea     r8, aLdDictBegin; "%ld dict\r\nbegin"
0x18004cd02  cmp     [rbx+5E8h], r14d
0x18004cd09  mov     eax, r14d
0x18004cd0c  mov     r9d, r14d
0x18004cd0f  mov     edx, r12d
0x18004cd12  setnz   r9b
0x18004cd16  cmp     [rbx+474h], r14d
0x18004cd1d  setnz   al
0x18004cd20  add     r9d, eax
0x18004cd23  mov     eax, r14d
0x18004cd26  cmp     [rbx+408h], r14d
0x18004cd2d  setnz   al
0x18004cd30  add     r9d, eax
0x18004cd33  mov     eax, r14d
0x18004cd36  cmp     [rbx+2A0h], r14d
0x18004cd3d  setnz   al
0x18004cd40  add     r9d, eax
0x18004cd43  mov     eax, [rbx+1E8h]
0x18004cd49  neg     eax
0x18004cd4b  mov     eax, r14d
0x18004cd4e  sbb     ecx, ecx
0x18004cd50  and     ecx, 0Fh
0x18004cd53  add     ecx, 0Ah
0x18004cd56  add     r9d, ecx
0x18004cd59  lea     rcx, [rsp+488h+var_448]
0x18004cd5e  cmp     [rbx+33Ch], r14d
0x18004cd65  setnz   al
0x18004cd68  add     r9d, eax
0x18004cd6b  mov     eax, r14d
0x18004cd6e  cmp     [rbx+464h], r14d
0x18004cd75  setnz   al
0x18004cd78  add     r9d, eax
0x18004cd7b  mov     rax, [rbx+168h]
0x18004cd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd87  lea     rdx, [rsp+488h+var_448]
0x18004cd8c  mov     rcx, rbx
0x18004cd8f  call    PutString
0x18004cd94  mov     rdx, r15
0x18004cd97  mov     rcx, rbx
0x18004cd9a  call    PutString
0x18004cd9f  cmp     [rbx+1E3Ch], r14d
0x18004cda6  jz      short loc_18004CDE0
0x18004cda8  lea     rdx, aFontname; "/FontName /"
0x18004cdaf  mov     rcx, rbx
0x18004cdb2  call    PutString
0x18004cdb7  movzx   edx, word ptr [rbx+1E40h]
0x18004cdbe  mov     rcx, rbx
0x18004cdc1  call    PutStringID
0x18004cdc6  lea     rdx, aDef_4; " def"
0x18004cdcd  mov     rcx, rbx
0x18004cdd0  call    PutString
0x18004cdd5  mov     rdx, r15
0x18004cdd8  mov     rcx, rbx
0x18004cddb  call    PutString
0x18004cde0  movzx   r8d, byte ptr [rbx+1F34h]
0x18004cde8  lea     rdx, aFonttype; "FontType"
0x18004cdef  mov     ebp, 1
0x18004cdf4  mov     rcx, rbx
0x18004cdf7  mov     r9d, ebp
0x18004cdfa  call    WriteLongNumberLine
0x18004cdff  mov     r9d, [rbx+33Ch]
0x18004ce06  lea     r8, [rbx+340h]
0x18004ce0d  mov     rcx, rbx
0x18004ce10  call    WriteFontMatrix
0x18004ce15  mov     r9d, [rbx+464h]
0x18004ce1c  lea     rdx, aPainttype; "PaintType"
0x18004ce23  mov     r8d, [rbx+468h]
0x18004ce2a  mov     rcx, rbx
0x18004ce2d  mov     [rsp+488h+var_468], r14d
0x18004ce32  call    WriteNumberLine
0x18004ce37  lea     rdx, aAdobeginprivat; "\r\n%ADOBeginPrivateDict"
0x18004ce3e  mov     rcx, rbx
0x18004ce41  call    PutString
0x18004ce46  mov     rdx, r15
0x18004ce49  mov     rcx, rbx
0x18004ce4c  call    PutString
0x18004ce51  mov     rcx, rbx
0x18004ce54  call    PrivateDictCount
0x18004ce59  mov     r9d, eax
0x18004ce5c  lea     r8, aPrivateLdDictD; "/Private %ld dict dup\r\nbegin"
0x18004ce63  mov     rax, [rbx+168h]
0x18004ce6a  lea     rcx, [rsp+488h+var_448]
0x18004ce6f  mov     rdx, r12
0x18004ce72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce77  lea     rdx, [rsp+488h+var_448]
0x18004ce7c  mov     rcx, rbx
0x18004ce7f  call    PutString
0x18004ce84  mov     rdx, r15
0x18004ce87  mov     rcx, rbx
0x18004ce8a  call    PutString
0x18004ce8f  lea     rdx, aMinfeature1616; "/MinFeature {16 16} def"
0x18004ce96  mov     rcx, rbx
0x18004ce99  call    PutString
0x18004ce9e  mov     rdx, r15
0x18004cea1  mov     rcx, rbx
0x18004cea4  call    PutString
0x18004cea9  mov     eax, [rbx+5DCh]
0x18004ceaf  cmp     eax, 2
0x18004ceb2  jnz     short loc_18004CED9
0x18004ceb4  mov     al, [rbx+1F34h]
0x18004ceba  cmp     al, bpl
0x18004cebd  jnz     short loc_18004CECC
0x18004cebf  movsx   r8d, word ptr [rbx+1F28h]
0x18004cec7  mov     r9d, ebp
0x18004ceca  jmp     short loc_18004CEF4
0x18004cecc  cmp     al, 2
0x18004cece  jnz     short loc_18004CF03
0x18004ced0  mov     r9d, ebp
0x18004ced3  or      r8d, 0FFFFFFFFh
0x18004ced7  jmp     short loc_18004CEF4
0x18004ced9  cmp     eax, ebp
0x18004cedb  jnz     short loc_18004CF03
0x18004cedd  cmp     [rbx+1F34h], bpl
0x18004cee4  jnz     short loc_18004CF03
0x18004cee6  mov     r9d, [rbx+45Ch]
0x18004ceed  mov     r8d, [rbx+460h]
0x18004cef4  lea     rdx, aLeniv; "lenIV"
0x18004cefb  mov     rcx, rbx
0x18004cefe  call    WriteLongNumberLine
0x18004cf03  mov     r9d, [rbx+46Ch]
0x18004cf0a  lea     rdx, aLanguagegroup; "LanguageGroup"
0x18004cf11  mov     r8d, [rbx+470h]
0x18004cf18  mov     rcx, rbx
0x18004cf1b  call    WriteLongNumberLine
0x18004cf20  cmp     [rbx+46Ch], r14d
0x18004cf27  jz      short loc_18004CF40
0x18004cf29  cmp     [rbx+470h], ebp
0x18004cf2f  jnz     short loc_18004CF40
0x18004cf31  lea     rdx, aRndstemupFalse; "/RndStemUp false def\r\n"
0x18004cf38  mov     rcx, rbx
0x18004cf3b  call    PutString
0x18004cf40  cmp     dword ptr [rbx+5DCh], 2
0x18004cf47  jnz     short loc_18004CF96
0x18004cf49  cmp     byte ptr [rbx+1F34h], 2
0x18004cf50  jnz     short loc_18004CF96
0x18004cf52  mov     r9d, [rbx+324h]
0x18004cf59  lea     rdx, aDefaultwidthx; "defaultWidthX"
0x18004cf60  mov     r8d, [rbx+328h]
0x18004cf67  mov     rcx, rbx
0x18004cf6a  mov     [rsp+488h+var_468], r14d
0x18004cf6f  call    WriteNumberLine
0x18004cf74  mov     r9d, [rbx+32Ch]
0x18004cf7b  lea     rdx, aNominalwidthx; "nominalWidthX"
0x18004cf82  mov     r8d, [rbx+330h]
0x18004cf89  mov     rcx, rbx
0x18004cf8c  mov     [rsp+488h+var_468], r14d
0x18004cf91  call    WriteNumberLine
0x18004cf96  cmp     [rbx+774h], r14d
0x18004cf9d  jnz     short loc_18004CFAE
0x18004cf9f  lea     rdx, aBluevaluesDef_0; "/BlueValues [ ] def\r\n"
0x18004cfa6  mov     rcx, rbx
0x18004cfa9  call    PutString
0x18004cfae  mov     r9d, [rbx+774h]
0x18004cfb5  lea     r8, [rbx+778h]
0x18004cfbc  mov     [rsp+488h+var_458], ebp
0x18004cfc0  lea     rdx, aBluevalues; "BlueValues"
0x18004cfc7  mov     [rsp+488h+var_460], ebp
0x18004cfcb  mov     rcx, rbx
0x18004cfce  mov     [rsp+488h+var_468], ebp
0x18004cfd2  call    WriteBlendArrayLine
0x18004cfd7  mov     r9d, [rbx+0AF8h]
0x18004cfde  lea     r8, [rbx+0AFCh]
0x18004cfe5  mov     [rsp+488h+var_458], ebp
0x18004cfe9  lea     rdx, aOtherblues; "OtherBlues"
0x18004cff0  mov     [rsp+488h+var_460], ebp
0x18004cff4  mov     rcx, rbx
0x18004cff7  mov     [rsp+488h+var_468], ebp
0x18004cffb  call    WriteBlendArrayLine
0x18004d000  mov     r9d, [rbx+198Ch]
0x18004d007  lea     r8, [rbx+1990h]
0x18004d00e  lea     rdx, aBluescale; "BlueScale"
0x18004d015  mov     [rsp+488h+var_450], ebp
0x18004d019  mov     rcx, rbx
0x18004d01c  mov     [rsp+488h+var_468], ebp
0x18004d020  call    WriteBlendLine
0x18004d025  mov     r9d, [rbx+19D0h]
0x18004d02c  lea     r8, [rbx+19D4h]
0x18004d033  lea     rdx, aBlueshift; "BlueShift"
0x18004d03a  mov     [rsp+488h+var_450], r14d
0x18004d03f  mov     rcx, rbx
0x18004d042  mov     [rsp+488h+var_468], ebp
0x18004d046  call    WriteBlendLine
0x18004d04b  mov     r9d, [rbx+1A14h]
0x18004d052  lea     r8, [rbx+1A18h]
0x18004d059  lea     rdx, aBluefuzz; "BlueFuzz"
0x18004d060  mov     [rsp+488h+var_450], r14d
0x18004d065  mov     rcx, rbx
0x18004d068  mov     [rsp+488h+var_468], ebp
0x18004d06c  call    WriteBlendLine
0x18004d071  mov     edx, ebp
0x18004d073  mov     rcx, rbx
0x18004d076  call    WriteStemSnap
0x18004d07b  lea     rdx, aOthersubrsSyst; "\r\n/OtherSubrs [ {} {} {} { systemdict"...
0x18004d082  mov     rcx, rbx
0x18004d085  call    PutString
0x18004d08a  mov     rdx, r15
0x18004d08d  mov     rcx, rbx
0x18004d090  call    PutString
0x18004d095  mov     edx, ebp
0x18004d097  mov     rcx, rbx
0x18004d09a  call    WriteErode
0x18004d09f  lea     rdx, aPassword5839De; "\r\n/password 5839 def\r\n"
0x18004d0a6  mov     rcx, rbx
0x18004d0a9  call    PutString
0x18004d0ae  mov     rdx, r15
0x18004d0b1  mov     rcx, rbx
0x18004d0b4  call    PutString
0x18004d0b9  test    di, di
0x18004d0bc  jz      loc_18004D148
0x18004d0c2  mov     rax, [rbx+168h]
0x18004d0c9  lea     r8, aSubrmapoffsetD; "/SubrMapOffset %d def"
0x18004d0d0  mov     r9d, esi
0x18004d0d3  lea     rcx, [rsp+488h+var_448]
0x18004d0d8  mov     rdx, r12
0x18004d0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0e0  lea     rdx, [rsp+488h+var_448]
0x18004d0e5  mov     rcx, rbx
0x18004d0e8  call    PutString
0x18004d0ed  mov     rdx, r15
0x18004d0f0  mov     rcx, rbx
0x18004d0f3  call    PutString
0x18004d0f8  lea     rdx, aSdbytes4Def; "/SDBytes 4 def"
0x18004d0ff  mov     rcx, rbx
0x18004d102  call    PutString
0x18004d107  mov     rdx, r15
0x18004d10a  mov     rcx, rbx
0x18004d10d  call    PutString
0x18004d112  mov     rax, [rbx+168h]
0x18004d119  lea     r8, aSubrcountDDef; "/SubrCount %d def"
0x18004d120  mov     r9d, edi
0x18004d123  lea     rcx, [rsp+488h+var_448]
0x18004d128  mov     rdx, r12
0x18004d12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d130  lea     rdx, [rsp+488h+var_448]
0x18004d135  mov     rcx, rbx
0x18004d138  call    PutString
0x18004d13d  mov     rdx, r15
0x18004d140  mov     rcx, rbx
0x18004d143  call    PutString
0x18004d148  lea     rdx, aEndDefAdoendpr; "end def\r\n%ADOEndPrivateDict\r\n\r\ncu"...
0x18004d14f  mov     rcx, rbx
0x18004d152  call    PutString
0x18004d157  mov     rdx, r15
0x18004d15a  mov     rcx, rbx
0x18004d15d  call    PutString
0x18004d162  mov     rcx, [rsp+488h+var_48]
0x18004d16a  xor     rcx, rsp; StackCookie
0x18004d16d  call    __security_check_cookie
0x18004d172  add     rsp, 450h
0x18004d179  pop     r15
0x18004d17b  pop     r14
0x18004d17d  pop     r12
0x18004d17f  pop     rdi
0x18004d180  pop     rsi
0x18004d181  pop     rbp
0x18004d182  pop     rbx
0x18004d183  retn
```
