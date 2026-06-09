# XT1_WriteCIDDict

- ea: `0x18004e4fc`
- end: `0x18004ea15`
- name: `XT1_WriteCIDDict`
- size: `1305`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned int, unsigned __int16)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180048608`

## callees

- `0x180001f20`
- `0x18004adf0`
- `0x18004b690`
- `0x18004b6d0`
- `0x18004ba24`
- `0x18004bb5c`
- `0x18004c400`
- `0x18004cc34`
- `0x18004cccc`
- `0x18004cdd4`
- `0x18004dcf8`
- `0x18004e4fc`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall XT1_WriteCIDDict(__int64 a1, unsigned __int16 a2, unsigned int a3, unsigned __int16 a4)
{
  unsigned int v5; // edi
  __int64 v7; // rdx
  unsigned int v8; // eax
  int v9; // eax
  char v10; // al
  unsigned int v11; // r8d
  int v12; // r9d
  int v14; // [rsp+28h] [rbp-460h]
  int v15; // [rsp+28h] [rbp-460h]
  int v16; // [rsp+28h] [rbp-460h]
  int v17; // [rsp+30h] [rbp-458h]
  int v18; // [rsp+30h] [rbp-458h]
  int v19; // [rsp+30h] [rbp-458h]
  _BYTE v20[1024]; // [rsp+40h] [rbp-448h] BYREF

  v5 = a4;
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v20, 1024, "dup %d\r\n", a2);
  PutString(a1, (__int64)v20);
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"%ADOBeginFontDict");
  PutString(a1, (__int64)"\r\n");
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(
    v20,
    1024,
    "%ld dict\r\nbegin",
    (*(_DWORD *)(a1 + 1124) != 0)
  + (*(_DWORD *)(a1 + 828) != 0)
  + (*(_DWORD *)(a1 + 488) != 0 ? 25 : 10)
  + (*(_DWORD *)(a1 + 672) != 0)
  + (*(_DWORD *)(a1 + 1032) != 0)
  + (*(_DWORD *)(a1 + 1140) != 0)
  + (unsigned int)(*(_DWORD *)(a1 + 1512) != 0));
  PutString(a1, (__int64)v20);
  PutString(a1, (__int64)"\r\n");
  if ( *(_DWORD *)(a1 + 7740) )
  {
    PutString(a1, (__int64)"/FontName /");
    PutStringID(a1, *(_WORD *)(a1 + 7744));
    PutString(a1, (__int64)" def");
    PutString(a1, (__int64)"\r\n");
  }
  WriteLongNumberLine(a1, (__int64)"FontType", *(unsigned __int8 *)(a1 + 7988), 1);
  WriteFontMatrix(a1, v7, a1 + 832, *(_DWORD *)(a1 + 828));
  WriteNumberLine(a1, (__int64)"PaintType", *(_DWORD *)(a1 + 1128), *(_DWORD *)(a1 + 1124), 0);
  PutString(a1, (__int64)"\r\n%ADOBeginPrivateDict");
  PutString(a1, (__int64)"\r\n");
  v8 = PrivateDictCount(a1);
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v20, 1024, "/Private %ld dict dup\r\nbegin", v8);
  PutString(a1, (__int64)v20);
  PutString(a1, (__int64)"\r\n");
  PutString(a1, (__int64)"/MinFeature {16 16} def");
  PutString(a1, (__int64)"\r\n");
  v9 = *(_DWORD *)(a1 + 1500);
  if ( v9 == 2 )
  {
    v10 = *(_BYTE *)(a1 + 7988);
    if ( v10 == 1 )
    {
      v11 = *(__int16 *)(a1 + 7976);
      v12 = 1;
LABEL_11:
      WriteLongNumberLine(a1, (__int64)"lenIV", v11, v12);
      goto LABEL_12;
    }
    if ( v10 == 2 )
    {
      v12 = 1;
      v11 = -1;
      goto LABEL_11;
    }
  }
  else if ( v9 == 1 && *(_BYTE *)(a1 + 7988) == 1 )
  {
    v12 = *(_DWORD *)(a1 + 1116);
    v11 = *(_DWORD *)(a1 + 1120);
    goto LABEL_11;
  }
LABEL_12:
  WriteLongNumberLine(a1, (__int64)"LanguageGroup", *(_DWORD *)(a1 + 1136), *(_DWORD *)(a1 + 1132));
  if ( *(_DWORD *)(a1 + 1132) && *(_DWORD *)(a1 + 1136) == 1 )
    PutString(a1, (__int64)"/RndStemUp false def\r\n");
  if ( *(_DWORD *)(a1 + 1500) == 2 && *(_BYTE *)(a1 + 7988) == 2 )
  {
    WriteNumberLine(a1, (__int64)"defaultWidthX", *(_DWORD *)(a1 + 808), *(_DWORD *)(a1 + 804), 0);
    WriteNumberLine(a1, (__int64)"nominalWidthX", *(_DWORD *)(a1 + 816), *(_DWORD *)(a1 + 812), 0);
  }
  if ( !*(_DWORD *)(a1 + 1908) )
    PutString(a1, (__int64)"/BlueValues [ ] def\r\n");
  WriteBlendArrayLine(a1, (__int64)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 1, 1, 1u);
  WriteBlendArrayLine(a1, (__int64)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 1, 1, 1u);
  WriteBlendLine(a1, (__int64)"BlueScale", (unsigned int *)(a1 + 6544), *(_DWORD *)(a1 + 6540), 1, v14, v17, 1u);
  WriteBlendLine(a1, (__int64)"BlueShift", (unsigned int *)(a1 + 6612), *(_DWORD *)(a1 + 6608), 1, v15, v18, 0);
  WriteBlendLine(a1, (__int64)"BlueFuzz", (unsigned int *)(a1 + 6680), *(_DWORD *)(a1 + 6676), 1, v16, v19, 0);
  WriteStemSnap((_DWORD *)a1, 1);
  PutString(
    a1,
    (__int64)"\r\n"
             "/OtherSubrs [ {} {} {} { systemdict /internaldict known not\r\n"
             "{ pop 3 } { 1183615869 systemdict /internaldict get exec dup\r\n"
             "/startlock known { /startlock get exec }\r\n"
             "{ dup /strtlck known { /strtlck get exec } { pop 3 } ifelse } ifelse } ifelse } bind\r\n"
             "{} {} {} {} {} {} {} {} {}\r\n"
             "{ 2 {cvi { { pop 0 lt { exit } if } loop } repeat } repeat } bind\r\n"
             "{} {} {} {} {} {} {} {} {} {} {} {} {} {} {} ] def");
  PutString(a1, (__int64)"\r\n");
  WriteErode((_DWORD *)a1, 1);
  PutString(a1, (__int64)"\r\n/password 5839 def\r\n");
  PutString(a1, (__int64)"\r\n");
  if ( (_WORD)v5 )
  {
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v20, 1024, "/SubrMapOffset %d def", a3);
    PutString(a1, (__int64)v20);
    PutString(a1, (__int64)"\r\n");
    PutString(a1, (__int64)"/SDBytes 4 def");
    PutString(a1, (__int64)"\r\n");
    (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v20, 1024, "/SubrCount %d def", v5);
    PutString(a1, (__int64)v20);
    PutString(a1, (__int64)"\r\n");
  }
  PutString(a1, (__int64)"end def\r\n%ADOEndPrivateDict\r\n\r\ncurrentdict\r\nend\r\n%ADOEndFontDict\r\n\r\nput");
  return PutString(a1, (__int64)"\r\n");
}

```

## disassembly

```asm
0x18004e4fc  push    rbx
0x18004e4fe  push    rbp
0x18004e4ff  push    rsi
0x18004e500  push    rdi
0x18004e501  push    r12
0x18004e503  push    r14
0x18004e505  push    r15
0x18004e507  sub     rsp, 450h
0x18004e50e  mov     rax, cs:__security_cookie
0x18004e515  xor     rax, rsp
0x18004e518  mov     [rsp+488h+var_48], rax
0x18004e520  mov     rbx, rcx
0x18004e523  movzx   edi, r9w
0x18004e527  mov     esi, r8d
0x18004e52a  movzx   r9d, dx
0x18004e52e  mov     r12d, 400h
0x18004e534  lea     r8, aDupD_0; "dup %d\r\n"
0x18004e53b  mov     edx, r12d
0x18004e53e  lea     rcx, [rsp+488h+var_448]
0x18004e543  mov     rax, [rbx+168h]
0x18004e54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e54f  lea     rdx, [rsp+488h+var_448]
0x18004e554  mov     rcx, rbx
0x18004e557  call    PutString
0x18004e55c  lea     r15, asc_180064FCC; "\r\n"
0x18004e563  mov     rcx, rbx
0x18004e566  mov     rdx, r15
0x18004e569  call    PutString
0x18004e56e  lea     rdx, aAdobeginfontdi; "%ADOBeginFontDict"
0x18004e575  mov     rcx, rbx
0x18004e578  call    PutString
0x18004e57d  mov     rdx, r15
0x18004e580  mov     rcx, rbx
0x18004e583  call    PutString
0x18004e588  xor     r14d, r14d
0x18004e58b  lea     r8, aLdDictBegin; "%ld dict\r\nbegin"
0x18004e592  cmp     [rbx+5E8h], r14d
0x18004e599  mov     eax, r14d
0x18004e59c  mov     r9d, r14d
0x18004e59f  mov     edx, r12d
0x18004e5a2  setnz   r9b
0x18004e5a6  cmp     [rbx+474h], r14d
0x18004e5ad  setnz   al
0x18004e5b0  add     r9d, eax
0x18004e5b3  mov     eax, r14d
0x18004e5b6  cmp     [rbx+408h], r14d
0x18004e5bd  setnz   al
0x18004e5c0  add     r9d, eax
0x18004e5c3  mov     eax, r14d
0x18004e5c6  cmp     [rbx+2A0h], r14d
0x18004e5cd  setnz   al
0x18004e5d0  add     r9d, eax
0x18004e5d3  mov     eax, [rbx+1E8h]
0x18004e5d9  neg     eax
0x18004e5db  mov     eax, r14d
0x18004e5de  sbb     ecx, ecx
0x18004e5e0  and     ecx, 0Fh
0x18004e5e3  add     ecx, 0Ah
0x18004e5e6  add     r9d, ecx
0x18004e5e9  lea     rcx, [rsp+488h+var_448]
0x18004e5ee  cmp     [rbx+33Ch], r14d
0x18004e5f5  setnz   al
0x18004e5f8  add     r9d, eax
0x18004e5fb  mov     eax, r14d
0x18004e5fe  cmp     [rbx+464h], r14d
0x18004e605  setnz   al
0x18004e608  add     r9d, eax
0x18004e60b  mov     rax, [rbx+168h]
0x18004e612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e617  lea     rdx, [rsp+488h+var_448]
0x18004e61c  mov     rcx, rbx
0x18004e61f  call    PutString
0x18004e624  mov     rdx, r15
0x18004e627  mov     rcx, rbx
0x18004e62a  call    PutString
0x18004e62f  cmp     [rbx+1E3Ch], r14d
0x18004e636  jz      short loc_18004E670
0x18004e638  lea     rdx, aFontname; "/FontName /"
0x18004e63f  mov     rcx, rbx
0x18004e642  call    PutString
0x18004e647  movzx   edx, word ptr [rbx+1E40h]
0x18004e64e  mov     rcx, rbx
0x18004e651  call    PutStringID
0x18004e656  lea     rdx, aDef_4; " def"
0x18004e65d  mov     rcx, rbx
0x18004e660  call    PutString
0x18004e665  mov     rdx, r15
0x18004e668  mov     rcx, rbx
0x18004e66b  call    PutString
0x18004e670  movzx   r8d, byte ptr [rbx+1F34h]
0x18004e678  lea     rdx, aFonttype; "FontType"
0x18004e67f  mov     ebp, 1
0x18004e684  mov     rcx, rbx
0x18004e687  mov     r9d, ebp
0x18004e68a  call    WriteLongNumberLine
0x18004e68f  mov     r9d, [rbx+33Ch]
0x18004e696  lea     r8, [rbx+340h]
0x18004e69d  mov     rcx, rbx
0x18004e6a0  call    WriteFontMatrix
0x18004e6a5  mov     r9d, [rbx+464h]
0x18004e6ac  lea     rdx, aPainttype; "PaintType"
0x18004e6b3  mov     r8d, [rbx+468h]
0x18004e6ba  mov     rcx, rbx
0x18004e6bd  mov     [rsp+488h+var_468], r14d
0x18004e6c2  call    WriteNumberLine
0x18004e6c7  lea     rdx, aAdobeginprivat; "\r\n%ADOBeginPrivateDict"
0x18004e6ce  mov     rcx, rbx
0x18004e6d1  call    PutString
0x18004e6d6  mov     rdx, r15
0x18004e6d9  mov     rcx, rbx
0x18004e6dc  call    PutString
0x18004e6e1  mov     rcx, rbx
0x18004e6e4  call    PrivateDictCount
0x18004e6e9  mov     r9d, eax
0x18004e6ec  lea     r8, aPrivateLdDictD; "/Private %ld dict dup\r\nbegin"
0x18004e6f3  mov     rax, [rbx+168h]
0x18004e6fa  lea     rcx, [rsp+488h+var_448]
0x18004e6ff  mov     rdx, r12
0x18004e702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e707  lea     rdx, [rsp+488h+var_448]
0x18004e70c  mov     rcx, rbx
0x18004e70f  call    PutString
0x18004e714  mov     rdx, r15
0x18004e717  mov     rcx, rbx
0x18004e71a  call    PutString
0x18004e71f  lea     rdx, aMinfeature1616; "/MinFeature {16 16} def"
0x18004e726  mov     rcx, rbx
0x18004e729  call    PutString
0x18004e72e  mov     rdx, r15
0x18004e731  mov     rcx, rbx
0x18004e734  call    PutString
0x18004e739  mov     eax, [rbx+5DCh]
0x18004e73f  cmp     eax, 2
0x18004e742  jnz     short loc_18004E769
0x18004e744  mov     al, [rbx+1F34h]
0x18004e74a  cmp     al, bpl
0x18004e74d  jnz     short loc_18004E75C
0x18004e74f  movsx   r8d, word ptr [rbx+1F28h]
0x18004e757  mov     r9d, ebp
0x18004e75a  jmp     short loc_18004E784
0x18004e75c  cmp     al, 2
0x18004e75e  jnz     short loc_18004E793
0x18004e760  mov     r9d, ebp
0x18004e763  or      r8d, 0FFFFFFFFh
0x18004e767  jmp     short loc_18004E784
0x18004e769  cmp     eax, ebp
0x18004e76b  jnz     short loc_18004E793
0x18004e76d  cmp     [rbx+1F34h], bpl
0x18004e774  jnz     short loc_18004E793
0x18004e776  mov     r9d, [rbx+45Ch]
0x18004e77d  mov     r8d, [rbx+460h]
0x18004e784  lea     rdx, aLeniv; "lenIV"
0x18004e78b  mov     rcx, rbx
0x18004e78e  call    WriteLongNumberLine
0x18004e793  mov     r9d, [rbx+46Ch]
0x18004e79a  lea     rdx, aLanguagegroup; "LanguageGroup"
0x18004e7a1  mov     r8d, [rbx+470h]
0x18004e7a8  mov     rcx, rbx
0x18004e7ab  call    WriteLongNumberLine
0x18004e7b0  cmp     [rbx+46Ch], r14d
0x18004e7b7  jz      short loc_18004E7D0
0x18004e7b9  cmp     [rbx+470h], ebp
0x18004e7bf  jnz     short loc_18004E7D0
0x18004e7c1  lea     rdx, aRndstemupFalse; "/RndStemUp false def\r\n"
0x18004e7c8  mov     rcx, rbx
0x18004e7cb  call    PutString
0x18004e7d0  cmp     dword ptr [rbx+5DCh], 2
0x18004e7d7  jnz     short loc_18004E826
0x18004e7d9  cmp     byte ptr [rbx+1F34h], 2
0x18004e7e0  jnz     short loc_18004E826
0x18004e7e2  mov     r9d, [rbx+324h]
0x18004e7e9  lea     rdx, aDefaultwidthx; "defaultWidthX"
0x18004e7f0  mov     r8d, [rbx+328h]
0x18004e7f7  mov     rcx, rbx
0x18004e7fa  mov     [rsp+488h+var_468], r14d
0x18004e7ff  call    WriteNumberLine
0x18004e804  mov     r9d, [rbx+32Ch]
0x18004e80b  lea     rdx, aNominalwidthx; "nominalWidthX"
0x18004e812  mov     r8d, [rbx+330h]
0x18004e819  mov     rcx, rbx
0x18004e81c  mov     [rsp+488h+var_468], r14d
0x18004e821  call    WriteNumberLine
0x18004e826  cmp     [rbx+774h], r14d
0x18004e82d  jnz     short loc_18004E83E
0x18004e82f  lea     rdx, aBluevaluesDef_0; "/BlueValues [ ] def\r\n"
0x18004e836  mov     rcx, rbx
0x18004e839  call    PutString
0x18004e83e  mov     r9d, [rbx+774h]
0x18004e845  lea     r8, [rbx+778h]
0x18004e84c  mov     [rsp+488h+var_458], ebp
0x18004e850  lea     rdx, aBluevalues; "BlueValues"
0x18004e857  mov     [rsp+488h+var_460], ebp
0x18004e85b  mov     rcx, rbx
0x18004e85e  mov     [rsp+488h+var_468], ebp
0x18004e862  call    WriteBlendArrayLine
0x18004e867  mov     r9d, [rbx+0AF8h]
0x18004e86e  lea     r8, [rbx+0AFCh]
0x18004e875  mov     [rsp+488h+var_458], ebp
0x18004e879  lea     rdx, aOtherblues; "OtherBlues"
0x18004e880  mov     [rsp+488h+var_460], ebp
0x18004e884  mov     rcx, rbx
0x18004e887  mov     [rsp+488h+var_468], ebp
0x18004e88b  call    WriteBlendArrayLine
0x18004e890  mov     r9d, [rbx+198Ch]
0x18004e897  lea     r8, [rbx+1990h]
0x18004e89e  lea     rdx, aBluescale; "BlueScale"
0x18004e8a5  mov     [rsp+488h+var_450], ebp
0x18004e8a9  mov     rcx, rbx
0x18004e8ac  mov     [rsp+488h+var_468], ebp
0x18004e8b0  call    WriteBlendLine
0x18004e8b5  mov     r9d, [rbx+19D0h]
0x18004e8bc  lea     r8, [rbx+19D4h]
0x18004e8c3  lea     rdx, aBlueshift; "BlueShift"
0x18004e8ca  mov     [rsp+488h+var_450], r14d
0x18004e8cf  mov     rcx, rbx
0x18004e8d2  mov     [rsp+488h+var_468], ebp
0x18004e8d6  call    WriteBlendLine
0x18004e8db  mov     r9d, [rbx+1A14h]
0x18004e8e2  lea     r8, [rbx+1A18h]
0x18004e8e9  lea     rdx, aBluefuzz; "BlueFuzz"
0x18004e8f0  mov     [rsp+488h+var_450], r14d
0x18004e8f5  mov     rcx, rbx
0x18004e8f8  mov     [rsp+488h+var_468], ebp
0x18004e8fc  call    WriteBlendLine
0x18004e901  mov     edx, ebp
0x18004e903  mov     rcx, rbx
0x18004e906  call    WriteStemSnap
0x18004e90b  lea     rdx, aOthersubrsSyst; "\r\n/OtherSubrs [ {} {} {} { systemdict"...
0x18004e912  mov     rcx, rbx
0x18004e915  call    PutString
0x18004e91a  mov     rdx, r15
0x18004e91d  mov     rcx, rbx
0x18004e920  call    PutString
0x18004e925  mov     edx, ebp
0x18004e927  mov     rcx, rbx
0x18004e92a  call    WriteErode
0x18004e92f  lea     rdx, aPassword5839De; "\r\n/password 5839 def\r\n"
0x18004e936  mov     rcx, rbx
0x18004e939  call    PutString
0x18004e93e  mov     rdx, r15
0x18004e941  mov     rcx, rbx
0x18004e944  call    PutString
0x18004e949  test    di, di
0x18004e94c  jz      loc_18004E9D8
0x18004e952  mov     rax, [rbx+168h]
0x18004e959  lea     r8, aSubrmapoffsetD; "/SubrMapOffset %d def"
0x18004e960  mov     r9d, esi
0x18004e963  lea     rcx, [rsp+488h+var_448]
0x18004e968  mov     rdx, r12
0x18004e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e970  lea     rdx, [rsp+488h+var_448]
0x18004e975  mov     rcx, rbx
0x18004e978  call    PutString
0x18004e97d  mov     rdx, r15
0x18004e980  mov     rcx, rbx
0x18004e983  call    PutString
0x18004e988  lea     rdx, aSdbytes4Def; "/SDBytes 4 def"
0x18004e98f  mov     rcx, rbx
0x18004e992  call    PutString
0x18004e997  mov     rdx, r15
0x18004e99a  mov     rcx, rbx
0x18004e99d  call    PutString
0x18004e9a2  mov     rax, [rbx+168h]
0x18004e9a9  lea     r8, aSubrcountDDef; "/SubrCount %d def"
0x18004e9b0  mov     r9d, edi
0x18004e9b3  lea     rcx, [rsp+488h+var_448]
0x18004e9b8  mov     rdx, r12
0x18004e9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9c0  lea     rdx, [rsp+488h+var_448]
0x18004e9c5  mov     rcx, rbx
0x18004e9c8  call    PutString
0x18004e9cd  mov     rdx, r15
0x18004e9d0  mov     rcx, rbx
0x18004e9d3  call    PutString
0x18004e9d8  lea     rdx, aEndDefAdoendpr; "end def\r\n%ADOEndPrivateDict\r\n\r\ncu"...
0x18004e9df  mov     rcx, rbx
0x18004e9e2  call    PutString
0x18004e9e7  mov     rdx, r15
0x18004e9ea  mov     rcx, rbx
0x18004e9ed  call    PutString
0x18004e9f2  mov     rcx, [rsp+488h+var_48]
0x18004e9fa  xor     rcx, rsp; StackCookie
0x18004e9fd  call    __security_check_cookie
0x18004ea02  add     rsp, 450h
0x18004ea09  pop     r15
0x18004ea0b  pop     r14
0x18004ea0d  pop     r12
0x18004ea0f  pop     rdi
0x18004ea10  pop     rsi
0x18004ea11  pop     rbp
0x18004ea12  pop     rbx
0x18004ea13  retn
```
