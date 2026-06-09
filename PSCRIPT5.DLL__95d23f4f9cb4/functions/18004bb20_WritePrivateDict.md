# WritePrivateDict

- ea: `0x18004bb20`
- end: `0x18004c2e4`
- name: `WritePrivateDict`
- size: `1988`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x18004db6c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x1800486f4`
- `0x18004957c`
- `0x180049e14`
- `0x180049e54`
- `0x18004a05c`
- `0x18004a1a8`
- `0x18004a260`
- `0x18004a2e0`
- `0x18004a4f4`
- `0x18004ab80`
- `0x18004b444`
- `0x18004b54c`
- `0x18004b8a0`
- `0x18004bb20`
- `0x18004c470`
- `0x18004c5f8`
- `0x18004e918`
- `0x18004f198`
- `0x18005d010`

## string_xrefs

- `0x18004bbba`: `/-|{string currentfile exch readhexstring pop}executeonly def\n`
- `0x18004bbca`: `/-|{string currentfile exch readstring pop}executeonly def\n`

## pseudocode

```c
__int64 __fastcall WritePrivateDict(__int64 a1, int a2, int a3, __int64 a4, __int64 a5)
{
  char v9; // bl
  unsigned int v10; // eax
  const char *v11; // rdx
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r9
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+30h] [rbp-D0h]
  int v30; // [rsp+30h] [rbp-D0h]
  int v31; // [rsp+30h] [rbp-D0h]
  int v32; // [rsp+30h] [rbp-D0h]
  __int16 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v35[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v36; // [rsp+80h] [rbp-80h]
  _BYTE v37[1024]; // [rsp+90h] [rbp-70h] BYREF

  memset_0(v37, 0, sizeof(v37));
  v9 = *(_BYTE *)(a1 + 7988);
  v10 = PrivateDictCount(a1);
  (*(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360))(v37, 1024, "dup /Private %ld dict dup begin\r\n", v10);
  PutString(a1, v37);
  if ( !*(_DWORD *)(a1 + 7980)
    || (v11 = "/-|{string currentfile exch readhexstring pop}executeonly def\r\n", *(_DWORD *)(a1 + 7984)) )
  {
    v11 = "/-|{string currentfile exch readstring pop}executeonly def\r\n";
  }
  PutString(a1, v11);
  PutString(a1, "/|-{def}executeonly def\r\n");
  PutString(a1, "/|{put}executeonly def\r\n");
  if ( !(unsigned __int8)StreamKeyPointData(a1, 2) )
    WriteLongNumberLine(a1, "UniqueID", *(unsigned int *)(a1 + 676), *(unsigned int *)(a1 + 672));
  if ( !*(_DWORD *)(a1 + 1908) )
    PutString(a1, "/BlueValues [ ] |-\r\n");
  WriteBlendArrayLine(a1, (unsigned int)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 1, 1, 1);
  WriteBlendArrayLine(a1, (unsigned int)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 1, 1, 1);
  WriteBlendArrayLine(a1, (unsigned int)"FamilyBlues", a1 + 3456, *(_DWORD *)(a1 + 3452), 1, 1, 1);
  WriteBlendArrayLine(a1, (unsigned int)"FamilyOtherBlues", a1 + 4356, *(_DWORD *)(a1 + 4352), 1, 1, 1);
  WriteStemSnap(a1, 1);
  WriteBlendLine(a1, (unsigned int)"BlueScale", a1 + 6544, *(_DWORD *)(a1 + 6540), 1, v23, v28, 1);
  WriteBlendLine(a1, (unsigned int)"BlueShift", a1 + 6612, *(_DWORD *)(a1 + 6608), 1, v24, v29, 0);
  WriteBlendLine(a1, (unsigned int)"BlueFuzz", a1 + 6680, *(_DWORD *)(a1 + 6676), 1, v25, v30, 0);
  WriteBlendBooleanLine(a1, (unsigned int)"ForceBold", a1 + 6748, *(_DWORD *)(a1 + 6744), 1, *(_DWORD *)(a1 + 6816));
  WriteNumberLine(a1, (unsigned int)"ForceBoldThreshold", *(_DWORD *)(a1 + 6816), *(_DWORD *)(a1 + 6812), 0);
  if ( *(_DWORD *)(a1 + 1132) && *(_DWORD *)(a1 + 1136) == 1 )
    PutString(a1, "/RndStemUp false def\r\n");
  WriteLongNumberLine(a1, "LanguageGroup", *(unsigned int *)(a1 + 1136), *(unsigned int *)(a1 + 1132));
  WriteNumberLine(a1, (unsigned int)"ExpansionFactor", *(_DWORD *)(a1 + 1104), *(_DWORD *)(a1 + 1100), 1);
  WriteNumberLine(a1, (unsigned int)"initialRandomSeed", *(_DWORD *)(a1 + 1112), *(_DWORD *)(a1 + 1108), 0);
  if ( v9 == 2 )
  {
    WriteNumberLine(a1, (unsigned int)"defaultWidthX", *(_DWORD *)(a1 + 808), *(_DWORD *)(a1 + 804), 0);
    WriteNumberLine(a1, (unsigned int)"nominalWidthX", *(_DWORD *)(a1 + 816), *(_DWORD *)(a1 + 812), 0);
    v12 = *(_DWORD *)(a1 + 6820);
    if ( v12 )
    {
      if ( *(_DWORD *)(a1 + 488) )
      {
        v13 = v12 + 2;
        if ( v13 >= 0x4D8 )
          v14 = v13 < 0x846C ? 1131 : 0x8000;
        else
          v14 = 107;
      }
      else
      {
        v14 = *(unsigned __int16 *)(a1 + 6836);
      }
      WriteLongNumberLine(a1, "subroutineNumberBias", v14, 1);
    }
  }
  v15 = *(_DWORD *)(a1 + 1500);
  if ( v15 == 2 )
  {
    v16 = (unsigned int)*(__int16 *)(a1 + 7976);
    v17 = 1;
LABEL_24:
    WriteLongNumberLine(a1, "lenIV", v16, v17);
    goto LABEL_25;
  }
  if ( v15 == 1 && *(_BYTE *)(a1 + 7988) == 1 )
  {
    v17 = *(unsigned int *)(a1 + 1116);
    v16 = *(unsigned int *)(a1 + 1120);
    goto LABEL_24;
  }
LABEL_25:
  if ( *(int *)(a1 + 488) > 0 )
  {
    v18 = 6820;
    if ( v9 != 2 )
      v18 = 14328;
    v19 = *(_DWORD *)(v18 + a1);
    WriteLongNumberLine(a1, "NDV", v19, 1);
    WriteLongNumberLine(a1, "CDV", v19 + 1, 1);
    if ( *(_BYTE *)(a1 + 7988) == 1 )
    {
      v20 = *(unsigned __int16 *)(a1 + 558);
      v34 = 0;
      v33 = 0;
      XCF_LookUpString(a1, v20, &v34, &v33);
      CharStrToSubr(a1, v34);
      XCF_LookUpString(a1, *(unsigned __int16 *)(a1 + 556), &v34, &v33);
      CharStrToSubr(a1, v34);
      NewT1Subr(a1);
    }
  }
  WriteLongNumberLine(a1, "lenBuildCharArray", *(unsigned int *)(a1 + 1212), *(unsigned int *)(a1 + 1208));
  if ( *(_DWORD *)(a1 + 1208) )
    PutString(a1, "/BuildCharArray lenBuildCharArray array def\r\n");
  PutString(a1, "/MinFeature {16 16} def\r\n");
  PutString(a1, "/password 5839 def\r\n");
  WriteErode(a1, 1);
  if ( *(_DWORD *)(a1 + 488) )
  {
    PutString(a1, "3 index /Blend get /Private get begin\r\n");
    WriteBlendArrayLine(a1, (unsigned int)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 0, 1, 1);
    WriteBlendArrayLine(a1, (unsigned int)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 0, 1, 1);
    WriteBlendLine(a1, (unsigned int)"BlueScale", a1 + 6544, *(_DWORD *)(a1 + 6540), 0, v26, v31, 1);
    WriteBlendLine(a1, (unsigned int)"BlueShift", a1 + 6612, *(_DWORD *)(a1 + 6608), 0, v27, v32, 0);
    WriteBlendArrayLine(a1, (unsigned int)"FamilyBlues", a1 + 3456, *(_DWORD *)(a1 + 3452), 0, 1, 1);
    WriteBlendArrayLine(a1, (unsigned int)"FamilyOtherBlues", a1 + 4356, *(_DWORD *)(a1 + 4352), 0, 1, 1);
    WriteBlendBooleanLine(a1, (unsigned int)"ForceBold", a1 + 6748, *(_DWORD *)(a1 + 6744), 0, *(_DWORD *)(a1 + 6816));
    WriteStemSnap(a1, 0);
    WriteErode(a1, 0);
    PutString(a1, "end\r\n");
  }
  if ( *(_DWORD *)(a1 + 788) )
  {
    PutStringID(a1, *(unsigned __int16 *)(a1 + 792));
    PutString(a1, "\r\n");
  }
  WriteOtherSubrs(a1, *(_DWORD *)(a1 + 21936), *(_DWORD *)(a1 + 14328) > 5u);
  WriteSubrs(a1, *(_BYTE *)(a1 + 7988) == 2);
  v21 = *(unsigned int *)(a1 + 7908);
  v36 = 0;
  memset(v35, 0, sizeof(v35));
  (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(
    v35,
    50,
    "2 index /CharStrings %lu dict dup begin\r\n",
    v21);
  PutString(a1, v35);
  if ( a2 != -1 )
    WriteCharstrings(a1, 0, 1, (unsigned int)&qword_180074608, 0, a5);
  return WriteCharstrings(a1, 0, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18004bb20  mov     [rsp-8+arg_8], rbx
0x18004bb25  push    rbp
0x18004bb26  push    rsi
0x18004bb27  push    rdi
0x18004bb28  push    r12
0x18004bb2a  push    r13
0x18004bb2c  push    r14
0x18004bb2e  push    r15
0x18004bb30  lea     rbp, [rsp-3A0h]
0x18004bb38  sub     rsp, 4A0h
0x18004bb3f  mov     rax, cs:__security_cookie
0x18004bb46  xor     rax, rsp
0x18004bb49  mov     [rbp+3D0h+var_40], rax
0x18004bb50  mov     rsi, [rbp+3D0h+arg_20]
0x18004bb57  mov     r15, r8
0x18004bb5a  mov     r14d, edx
0x18004bb5d  mov     rdi, rcx
0x18004bb60  mov     r13d, 400h
0x18004bb66  lea     rcx, [rbp+3D0h+var_440]; void *
0x18004bb6a  mov     r8d, r13d; Size
0x18004bb6d  xor     edx, edx; Val
0x18004bb6f  mov     r12, r9
0x18004bb72  call    memset_0
0x18004bb77  mov     bl, [rdi+1F34h]
0x18004bb7d  mov     rcx, rdi
0x18004bb80  call    PrivateDictCount
0x18004bb85  mov     r9d, eax
0x18004bb88  lea     r8, aDupPrivateLdDi; "dup /Private %ld dict dup begin\r\n"
0x18004bb8f  mov     rax, [rdi+168h]
0x18004bb96  lea     rcx, [rbp+3D0h+var_440]
0x18004bb9a  mov     edx, r13d
0x18004bb9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bba2  lea     rdx, [rbp+3D0h+var_440]
0x18004bba6  mov     rcx, rdi
0x18004bba9  call    PutString
0x18004bbae  xor     r13d, r13d
0x18004bbb1  cmp     [rdi+1F2Ch], r13d
0x18004bbb8  jz      short loc_18004BBCA
0x18004bbba  lea     rdx, aStringCurrentf; "/-|{string currentfile exch readhexstri"...
0x18004bbc1  cmp     [rdi+1F30h], r13d
0x18004bbc8  jz      short loc_18004BBD1
0x18004bbca  lea     rdx, aStringCurrentf_0; "/-|{string currentfile exch readstring "...
0x18004bbd1  mov     rcx, rdi
0x18004bbd4  call    PutString
0x18004bbd9  lea     rdx, aDefExecuteonly; "/|-{def}executeonly def\r\n"
0x18004bbe0  mov     rcx, rdi
0x18004bbe3  call    PutString
0x18004bbe8  lea     rdx, aPutExecuteonly; "/|{put}executeonly def\r\n"
0x18004bbef  mov     rcx, rdi
0x18004bbf2  call    PutString
0x18004bbf7  mov     edx, 2
0x18004bbfc  mov     rcx, rdi
0x18004bbff  call    StreamKeyPointData
0x18004bc04  test    al, al
0x18004bc06  jnz     short loc_18004BC25
0x18004bc08  mov     r9d, [rdi+2A0h]
0x18004bc0f  lea     rdx, aUniqueid; "UniqueID"
0x18004bc16  mov     r8d, [rdi+2A4h]
0x18004bc1d  mov     rcx, rdi
0x18004bc20  call    WriteLongNumberLine
0x18004bc25  cmp     [rdi+774h], r13d
0x18004bc2c  jnz     short loc_18004BC3D
0x18004bc2e  lea     rdx, aBluevalues_0; "/BlueValues [ ] |-\r\n"
0x18004bc35  mov     rcx, rdi
0x18004bc38  call    PutString
0x18004bc3d  mov     r9d, [rdi+774h]
0x18004bc44  lea     r13, [rdi+778h]
0x18004bc4b  mov     eax, 1
0x18004bc50  lea     rdx, aBluevalues; "BlueValues"
0x18004bc57  mov     [rsp+4D0h+var_4A0], eax
0x18004bc5b  mov     r8, r13
0x18004bc5e  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004bc62  mov     rcx, rdi
0x18004bc65  mov     dword ptr [rsp+4D0h+var_4B0], eax
0x18004bc69  call    WriteBlendArrayLine
0x18004bc6e  mov     r9d, [rdi+0AF8h]
0x18004bc75  lea     r8, [rdi+0AFCh]
0x18004bc7c  mov     ecx, 1
0x18004bc81  lea     rdx, aOtherblues; "OtherBlues"
0x18004bc88  mov     [rsp+4D0h+var_4A0], ecx
0x18004bc8c  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004bc90  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004bc94  mov     rcx, rdi
0x18004bc97  call    WriteBlendArrayLine
0x18004bc9c  mov     r9d, [rdi+0D7Ch]
0x18004bca3  lea     r8, [rdi+0D80h]
0x18004bcaa  mov     ecx, 1
0x18004bcaf  lea     rdx, aFamilyblues; "FamilyBlues"
0x18004bcb6  mov     [rsp+4D0h+var_4A0], ecx
0x18004bcba  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004bcbe  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004bcc2  mov     rcx, rdi
0x18004bcc5  call    WriteBlendArrayLine
0x18004bcca  mov     r9d, [rdi+1100h]
0x18004bcd1  lea     r8, [rdi+1104h]
0x18004bcd8  mov     ecx, 1
0x18004bcdd  lea     rdx, aFamilyotherblu; "FamilyOtherBlues"
0x18004bce4  mov     [rsp+4D0h+var_4A0], ecx
0x18004bce8  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004bcec  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004bcf0  mov     rcx, rdi
0x18004bcf3  call    WriteBlendArrayLine
0x18004bcf8  mov     edx, 1
0x18004bcfd  mov     rcx, rdi
0x18004bd00  call    WriteStemSnap
0x18004bd05  mov     r9d, [rdi+198Ch]
0x18004bd0c  lea     r8, [rdi+1990h]
0x18004bd13  mov     ecx, 1
0x18004bd18  lea     rdx, aBluescale; "BlueScale"
0x18004bd1f  mov     [rsp+4D0h+var_498], ecx
0x18004bd23  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004bd27  mov     rcx, rdi
0x18004bd2a  call    WriteBlendLine
0x18004bd2f  mov     r9d, [rdi+19D0h]
0x18004bd36  lea     r8, [rdi+19D4h]
0x18004bd3d  lea     rdx, aBlueshift; "BlueShift"
0x18004bd44  mov     [rsp+4D0h+var_498], 0
0x18004bd4c  mov     rcx, rdi
0x18004bd4f  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004bd57  call    WriteBlendLine
0x18004bd5c  mov     r9d, [rdi+1A14h]
0x18004bd63  lea     r8, [rdi+1A18h]
0x18004bd6a  lea     rdx, aBluefuzz; "BlueFuzz"
0x18004bd71  mov     [rsp+4D0h+var_498], 0
0x18004bd79  mov     rcx, rdi
0x18004bd7c  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004bd84  call    WriteBlendLine
0x18004bd89  mov     eax, [rdi+1AA0h]
0x18004bd8f  lea     r8, [rdi+1A5Ch]
0x18004bd96  mov     r9d, [rdi+1A58h]
0x18004bd9d  lea     rdx, aForcebold; "ForceBold"
0x18004bda4  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004bda8  mov     rcx, rdi
0x18004bdab  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004bdb3  call    WriteBlendBooleanLine
0x18004bdb8  mov     r9d, [rdi+1A9Ch]
0x18004bdbf  lea     rdx, aForceboldthres; "ForceBoldThreshold"
0x18004bdc6  mov     r8d, [rdi+1AA0h]
0x18004bdcd  mov     rcx, rdi
0x18004bdd0  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004bdd8  call    WriteNumberLine
0x18004bddd  cmp     dword ptr [rdi+46Ch], 0
0x18004bde4  jz      short loc_18004BDFE
0x18004bde6  cmp     dword ptr [rdi+470h], 1
0x18004bded  jnz     short loc_18004BDFE
0x18004bdef  lea     rdx, aRndstemupFalse; "/RndStemUp false def\r\n"
0x18004bdf6  mov     rcx, rdi
0x18004bdf9  call    PutString
0x18004bdfe  mov     r9d, [rdi+46Ch]
0x18004be05  lea     rdx, aLanguagegroup; "LanguageGroup"
0x18004be0c  mov     r8d, [rdi+470h]
0x18004be13  mov     rcx, rdi
0x18004be16  call    WriteLongNumberLine
0x18004be1b  mov     r9d, [rdi+44Ch]
0x18004be22  lea     rdx, aExpansionfacto; "ExpansionFactor"
0x18004be29  mov     r8d, [rdi+450h]
0x18004be30  mov     rcx, rdi
0x18004be33  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004be3b  call    WriteNumberLine
0x18004be40  mov     r9d, [rdi+454h]
0x18004be47  lea     rdx, aInitialrandoms; "initialRandomSeed"
0x18004be4e  mov     r8d, [rdi+458h]
0x18004be55  mov     rcx, rdi
0x18004be58  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004be60  call    WriteNumberLine
0x18004be65  cmp     bl, 2
0x18004be68  jnz     loc_18004BF12
0x18004be6e  mov     r9d, [rdi+324h]
0x18004be75  lea     rdx, aDefaultwidthx; "defaultWidthX"
0x18004be7c  mov     r8d, [rdi+328h]
0x18004be83  mov     rcx, rdi
0x18004be86  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004be8e  call    WriteNumberLine
0x18004be93  mov     r9d, [rdi+32Ch]
0x18004be9a  lea     rdx, aNominalwidthx; "nominalWidthX"
0x18004bea1  mov     r8d, [rdi+330h]
0x18004bea8  mov     rcx, rdi
0x18004beab  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004beb3  call    WriteNumberLine
0x18004beb8  mov     eax, [rdi+1AA4h]
0x18004bebe  test    eax, eax
0x18004bec0  jz      short loc_18004BF12
0x18004bec2  cmp     dword ptr [rdi+1E8h], 0
0x18004bec9  jz      short loc_18004BEF5
0x18004becb  add     eax, 2
0x18004bece  cmp     eax, 4D8h
0x18004bed3  jnb     short loc_18004BEDD
0x18004bed5  mov     r8d, 6Bh ; 'k'
0x18004bedb  jmp     short loc_18004BEFD
0x18004bedd  cmp     eax, 846Ch
0x18004bee2  sbb     r8d, r8d
0x18004bee5  and     r8d, 0FFFF846Bh
0x18004beec  add     r8d, 8000h
0x18004bef3  jmp     short loc_18004BEFD
0x18004bef5  movzx   r8d, word ptr [rdi+1AB4h]
0x18004befd  mov     r9d, 1
0x18004bf03  lea     rdx, aSubroutinenumb; "subroutineNumberBias"
0x18004bf0a  mov     rcx, rdi
0x18004bf0d  call    WriteLongNumberLine
0x18004bf12  mov     eax, [rdi+5DCh]
0x18004bf18  cmp     eax, 2
0x18004bf1b  jnz     short loc_18004BF2B
0x18004bf1d  movsx   r8d, word ptr [rdi+1F28h]
0x18004bf25  lea     r9d, [rax-1]
0x18004bf29  jmp     short loc_18004BF46
0x18004bf2b  cmp     eax, 1
0x18004bf2e  jnz     short loc_18004BF55
0x18004bf30  cmp     [rdi+1F34h], al
0x18004bf36  jnz     short loc_18004BF55
0x18004bf38  mov     r9d, [rdi+45Ch]
0x18004bf3f  mov     r8d, [rdi+460h]
0x18004bf46  lea     rdx, aLeniv; "lenIV"
0x18004bf4d  mov     rcx, rdi
0x18004bf50  call    WriteLongNumberLine
0x18004bf55  cmp     dword ptr [rdi+1E8h], 0
0x18004bf5c  jle     loc_18004C011
0x18004bf62  cmp     bl, 2
0x18004bf65  lea     rdx, aNdv; "NDV"
0x18004bf6c  mov     ecx, 37F8h
0x18004bf71  mov     eax, 1AA4h
0x18004bf76  cmovnz  eax, ecx
0x18004bf79  mov     r9d, 1
0x18004bf7f  mov     rcx, rdi
0x18004bf82  mov     ebx, [rax+rdi]
0x18004bf85  mov     r8d, ebx
0x18004bf88  call    WriteLongNumberLine
0x18004bf8d  lea     r8d, [rbx+1]
0x18004bf91  mov     r9d, 1
0x18004bf97  lea     rdx, aCdv; "CDV"
0x18004bf9e  mov     rcx, rdi
0x18004bfa1  call    WriteLongNumberLine
0x18004bfa6  xor     ebx, ebx
0x18004bfa8  cmp     byte ptr [rdi+1F34h], 1
0x18004bfaf  jnz     short loc_18004C013
0x18004bfb1  movzx   edx, word ptr [rdi+22Eh]
0x18004bfb8  lea     r9, [rsp+4D0h+var_490]
0x18004bfbd  lea     r8, [rsp+4D0h+var_488]
0x18004bfc2  mov     [rsp+4D0h+var_488], rbx
0x18004bfc7  mov     rcx, rdi
0x18004bfca  mov     [rsp+4D0h+var_490], bx
0x18004bfcf  call    XCF_LookUpString
0x18004bfd4  mov     rdx, [rsp+4D0h+var_488]
0x18004bfd9  mov     rcx, rdi
0x18004bfdc  call    CharStrToSubr
0x18004bfe1  movzx   edx, word ptr [rdi+22Ch]
0x18004bfe8  lea     r9, [rsp+4D0h+var_490]
0x18004bfed  lea     r8, [rsp+4D0h+var_488]
0x18004bff2  mov     rcx, rdi
0x18004bff5  call    XCF_LookUpString
0x18004bffa  mov     rdx, [rsp+4D0h+var_488]
0x18004bfff  mov     rcx, rdi
0x18004c002  call    CharStrToSubr
0x18004c007  mov     rcx, rdi
0x18004c00a  call    NewT1Subr
0x18004c00f  jmp     short loc_18004C013
0x18004c011  xor     ebx, ebx
0x18004c013  mov     r9d, [rdi+4B8h]
0x18004c01a  lea     rdx, aLenbuildcharar; "lenBuildCharArray"
0x18004c021  mov     r8d, [rdi+4BCh]
0x18004c028  mov     rcx, rdi
0x18004c02b  call    WriteLongNumberLine
0x18004c030  cmp     [rdi+4B8h], ebx
0x18004c036  jz      short loc_18004C047
0x18004c038  lea     rdx, aBuildchararray; "/BuildCharArray lenBuildCharArray array"...
0x18004c03f  mov     rcx, rdi
0x18004c042  call    PutString
0x18004c047  lea     rdx, aMinfeature1616_0; "/MinFeature {16 16} def\r\n"
0x18004c04e  mov     rcx, rdi
0x18004c051  call    PutString
0x18004c056  lea     rdx, aPassword5839De_0; "/password 5839 def\r\n"
0x18004c05d  mov     rcx, rdi
0x18004c060  call    PutString
0x18004c065  mov     edx, 1
0x18004c06a  mov     rcx, rdi
0x18004c06d  call    WriteErode
0x18004c072  cmp     [rdi+1E8h], ebx
0x18004c078  jz      loc_18004C1D9
0x18004c07e  lea     rdx, a3IndexBlendGet; "3 index /Blend get /Private get begin\r"...
0x18004c085  mov     rcx, rdi
0x18004c088  call    PutString
0x18004c08d  mov     r9d, [rdi+774h]
0x18004c094  lea     rdx, aBluevalues; "BlueValues"
0x18004c09b  mov     eax, 1
0x18004c0a0  mov     r8, r13
0x18004c0a3  mov     [rsp+4D0h+var_4A0], eax
0x18004c0a7  mov     rcx, rdi
0x18004c0aa  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004c0ae  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18004c0b2  call    WriteBlendArrayLine
0x18004c0b7  mov     r9d, [rdi+0AF8h]
0x18004c0be  lea     r8, [rdi+0AFCh]
0x18004c0c5  mov     r13d, 1
0x18004c0cb  lea     rdx, aOtherblues; "OtherBlues"
0x18004c0d2  mov     [rsp+4D0h+var_4A0], r13d
0x18004c0d7  mov     rcx, rdi
0x18004c0da  mov     dword ptr [rsp+4D0h+var_4A8], r13d
0x18004c0df  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18004c0e3  call    WriteBlendArrayLine
0x18004c0e8  mov     r9d, [rdi+198Ch]
0x18004c0ef  lea     r8, [rdi+1990h]
  ... truncated ...
```
