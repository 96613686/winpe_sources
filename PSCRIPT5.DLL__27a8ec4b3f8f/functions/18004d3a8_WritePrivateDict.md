# WritePrivateDict

- ea: `0x18004d3a8`
- end: `0x18004db6d`
- name: `WritePrivateDict`
- size: `1989`
- prototype: `int __fastcall(__int64, int, unsigned int *, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x18004f3fc`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180049f64`
- `0x18004adf0`
- `0x18004b690`
- `0x18004b6d0`
- `0x18004b8d8`
- `0x18004ba24`
- `0x18004badc`
- `0x18004bb5c`
- `0x18004bd74`
- `0x18004c400`
- `0x18004cccc`
- `0x18004cdd4`
- `0x18004d128`
- `0x18004d3a8`
- `0x18004dcf8`
- `0x18004de80`
- `0x180050274`
- `0x180050b04`
- `0x18005f010`

## string_xrefs

- `0x18004d442`: `/-|{string currentfile exch readhexstring pop}executeonly def\n`
- `0x18004d452`: `/-|{string currentfile exch readstring pop}executeonly def\n`

## pseudocode

```c
int __fastcall WritePrivateDict(__int64 a1, int a2, unsigned int *a3, __int64 a4, _DWORD *a5)
{
  char v9; // bl
  unsigned int v10; // eax
  const char *v11; // rdx
  int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // r8d
  int v17; // r9d
  __int64 v18; // rax
  unsigned int v19; // ebx
  unsigned __int16 v20; // dx
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
  PutString(a1, (__int64)v37);
  if ( !*(_DWORD *)(a1 + 7980)
    || (v11 = "/-|{string currentfile exch readhexstring pop}executeonly def\r\n", *(_DWORD *)(a1 + 7984)) )
  {
    v11 = "/-|{string currentfile exch readstring pop}executeonly def\r\n";
  }
  PutString(a1, (__int64)v11);
  PutString(a1, (__int64)"/|-{def}executeonly def\r\n");
  PutString(a1, (__int64)"/|{put}executeonly def\r\n");
  if ( !StreamKeyPointData(a1, 2) )
    WriteLongNumberLine(a1, (__int64)"UniqueID", *(_DWORD *)(a1 + 676), *(_DWORD *)(a1 + 672));
  if ( !*(_DWORD *)(a1 + 1908) )
    PutString(a1, (__int64)"/BlueValues [ ] |-\r\n");
  WriteBlendArrayLine(a1, (__int64)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 1, 1, 1u);
  WriteBlendArrayLine(a1, (__int64)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 1, 1, 1u);
  WriteBlendArrayLine(a1, (__int64)"FamilyBlues", a1 + 3456, *(_DWORD *)(a1 + 3452), 1, 1, 1u);
  WriteBlendArrayLine(a1, (__int64)"FamilyOtherBlues", a1 + 4356, *(_DWORD *)(a1 + 4352), 1, 1, 1u);
  WriteStemSnap((_DWORD *)a1, 1);
  WriteBlendLine(a1, (__int64)"BlueScale", (unsigned int *)(a1 + 6544), *(_DWORD *)(a1 + 6540), 1, v23, v28, 1u);
  WriteBlendLine(a1, (__int64)"BlueShift", (unsigned int *)(a1 + 6612), *(_DWORD *)(a1 + 6608), 1, v24, v29, 0);
  WriteBlendLine(a1, (__int64)"BlueFuzz", (unsigned int *)(a1 + 6680), *(_DWORD *)(a1 + 6676), 1, v25, v30, 0);
  WriteBlendBooleanLine(
    a1,
    (__int64)"ForceBold",
    (_DWORD *)(a1 + 6748),
    *(_DWORD *)(a1 + 6744),
    1,
    *(_DWORD *)(a1 + 6816));
  WriteNumberLine(a1, (__int64)"ForceBoldThreshold", *(_DWORD *)(a1 + 6816), *(_DWORD *)(a1 + 6812), 0);
  if ( *(_DWORD *)(a1 + 1132) && *(_DWORD *)(a1 + 1136) == 1 )
    PutString(a1, (__int64)"/RndStemUp false def\r\n");
  WriteLongNumberLine(a1, (__int64)"LanguageGroup", *(_DWORD *)(a1 + 1136), *(_DWORD *)(a1 + 1132));
  WriteNumberLine(a1, (__int64)"ExpansionFactor", *(_DWORD *)(a1 + 1104), *(_DWORD *)(a1 + 1100), 1u);
  WriteNumberLine(a1, (__int64)"initialRandomSeed", *(_DWORD *)(a1 + 1112), *(_DWORD *)(a1 + 1108), 0);
  if ( v9 == 2 )
  {
    WriteNumberLine(a1, (__int64)"defaultWidthX", *(_DWORD *)(a1 + 808), *(_DWORD *)(a1 + 804), 0);
    WriteNumberLine(a1, (__int64)"nominalWidthX", *(_DWORD *)(a1 + 816), *(_DWORD *)(a1 + 812), 0);
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
      WriteLongNumberLine(a1, (__int64)"subroutineNumberBias", v14, 1);
    }
  }
  v15 = *(_DWORD *)(a1 + 1500);
  if ( v15 == 2 )
  {
    v16 = *(__int16 *)(a1 + 7976);
    v17 = 1;
LABEL_24:
    WriteLongNumberLine(a1, (__int64)"lenIV", v16, v17);
    goto LABEL_25;
  }
  if ( v15 == 1 && *(_BYTE *)(a1 + 7988) == 1 )
  {
    v17 = *(_DWORD *)(a1 + 1116);
    v16 = *(_DWORD *)(a1 + 1120);
    goto LABEL_24;
  }
LABEL_25:
  if ( *(int *)(a1 + 488) > 0 )
  {
    v18 = 6820;
    if ( v9 != 2 )
      v18 = 14328;
    v19 = *(_DWORD *)(v18 + a1);
    WriteLongNumberLine(a1, (__int64)"NDV", v19, 1);
    WriteLongNumberLine(a1, (__int64)"CDV", v19 + 1, 1);
    if ( *(_BYTE *)(a1 + 7988) == 1 )
    {
      v20 = *(_WORD *)(a1 + 558);
      v34 = 0;
      v33 = 0;
      XCF_LookUpString(a1, v20, &v34, &v33);
      CharStrToSubr(a1, v34);
      XCF_LookUpString(a1, *(_WORD *)(a1 + 556), &v34, &v33);
      CharStrToSubr(a1, v34);
      NewT1Subr(a1);
    }
  }
  WriteLongNumberLine(a1, (__int64)"lenBuildCharArray", *(_DWORD *)(a1 + 1212), *(_DWORD *)(a1 + 1208));
  if ( *(_DWORD *)(a1 + 1208) )
    PutString(a1, (__int64)"/BuildCharArray lenBuildCharArray array def\r\n");
  PutString(a1, (__int64)"/MinFeature {16 16} def\r\n");
  PutString(a1, (__int64)"/password 5839 def\r\n");
  WriteErode((_DWORD *)a1, 1);
  if ( *(_DWORD *)(a1 + 488) )
  {
    PutString(a1, (__int64)"3 index /Blend get /Private get begin\r\n");
    WriteBlendArrayLine(a1, (__int64)"BlueValues", a1 + 1912, *(_DWORD *)(a1 + 1908), 0, 1, 1u);
    WriteBlendArrayLine(a1, (__int64)"OtherBlues", a1 + 2812, *(_DWORD *)(a1 + 2808), 0, 1, 1u);
    WriteBlendLine(a1, (__int64)"BlueScale", (unsigned int *)(a1 + 6544), *(_DWORD *)(a1 + 6540), 0, v26, v31, 1u);
    WriteBlendLine(a1, (__int64)"BlueShift", (unsigned int *)(a1 + 6612), *(_DWORD *)(a1 + 6608), 0, v27, v32, 0);
    WriteBlendArrayLine(a1, (__int64)"FamilyBlues", a1 + 3456, *(_DWORD *)(a1 + 3452), 0, 1, 1u);
    WriteBlendArrayLine(a1, (__int64)"FamilyOtherBlues", a1 + 4356, *(_DWORD *)(a1 + 4352), 0, 1, 1u);
    WriteBlendBooleanLine(
      a1,
      (__int64)"ForceBold",
      (_DWORD *)(a1 + 6748),
      *(_DWORD *)(a1 + 6744),
      0,
      *(_DWORD *)(a1 + 6816));
    WriteStemSnap((_DWORD *)a1, 0);
    WriteErode((_DWORD *)a1, 0);
    PutString(a1, (__int64)"end\r\n");
  }
  if ( *(_DWORD *)(a1 + 788) )
  {
    PutStringID(a1, *(_WORD *)(a1 + 792));
    PutString(a1, (__int64)"\r\n");
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
  PutString(a1, (__int64)v35);
  if ( a2 != -1 )
    WriteCharstrings(a1, 0, 1, (unsigned int *)&qword_1800765F8, 0, a5);
  return WriteCharstrings(a1, 0, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18004d3a8  mov     [rsp-8+arg_8], rbx
0x18004d3ad  push    rbp
0x18004d3ae  push    rsi
0x18004d3af  push    rdi
0x18004d3b0  push    r12
0x18004d3b2  push    r13
0x18004d3b4  push    r14
0x18004d3b6  push    r15
0x18004d3b8  lea     rbp, [rsp-3A0h]
0x18004d3c0  sub     rsp, 4A0h
0x18004d3c7  mov     rax, cs:__security_cookie
0x18004d3ce  xor     rax, rsp
0x18004d3d1  mov     [rbp+3D0h+var_40], rax
0x18004d3d8  mov     rsi, [rbp+3D0h+arg_20]
0x18004d3df  mov     r15, r8
0x18004d3e2  mov     r14d, edx
0x18004d3e5  mov     rdi, rcx
0x18004d3e8  mov     r13d, 400h
0x18004d3ee  lea     rcx, [rbp+3D0h+var_440]; void *
0x18004d3f2  mov     r8d, r13d; Size
0x18004d3f5  xor     edx, edx; Val
0x18004d3f7  mov     r12, r9
0x18004d3fa  call    memset_0
0x18004d3ff  mov     bl, [rdi+1F34h]
0x18004d405  mov     rcx, rdi
0x18004d408  call    PrivateDictCount
0x18004d40d  mov     r9d, eax
0x18004d410  lea     r8, aDupPrivateLdDi; "dup /Private %ld dict dup begin\r\n"
0x18004d417  mov     rax, [rdi+168h]
0x18004d41e  lea     rcx, [rbp+3D0h+var_440]
0x18004d422  mov     edx, r13d
0x18004d425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d42a  lea     rdx, [rbp+3D0h+var_440]
0x18004d42e  mov     rcx, rdi
0x18004d431  call    PutString
0x18004d436  xor     r13d, r13d
0x18004d439  cmp     [rdi+1F2Ch], r13d
0x18004d440  jz      short loc_18004D452
0x18004d442  lea     rdx, aStringCurrentf; "/-|{string currentfile exch readhexstri"...
0x18004d449  cmp     [rdi+1F30h], r13d
0x18004d450  jz      short loc_18004D459
0x18004d452  lea     rdx, aStringCurrentf_0; "/-|{string currentfile exch readstring "...
0x18004d459  mov     rcx, rdi
0x18004d45c  call    PutString
0x18004d461  lea     rdx, aDefExecuteonly; "/|-{def}executeonly def\r\n"
0x18004d468  mov     rcx, rdi
0x18004d46b  call    PutString
0x18004d470  lea     rdx, aPutExecuteonly; "/|{put}executeonly def\r\n"
0x18004d477  mov     rcx, rdi
0x18004d47a  call    PutString
0x18004d47f  mov     edx, 2
0x18004d484  mov     rcx, rdi
0x18004d487  call    StreamKeyPointData
0x18004d48c  test    al, al
0x18004d48e  jnz     short loc_18004D4AD
0x18004d490  mov     r9d, [rdi+2A0h]
0x18004d497  lea     rdx, aUniqueid; "UniqueID"
0x18004d49e  mov     r8d, [rdi+2A4h]
0x18004d4a5  mov     rcx, rdi
0x18004d4a8  call    WriteLongNumberLine
0x18004d4ad  cmp     [rdi+774h], r13d
0x18004d4b4  jnz     short loc_18004D4C5
0x18004d4b6  lea     rdx, aBluevalues_0; "/BlueValues [ ] |-\r\n"
0x18004d4bd  mov     rcx, rdi
0x18004d4c0  call    PutString
0x18004d4c5  mov     r9d, [rdi+774h]
0x18004d4cc  lea     r13, [rdi+778h]
0x18004d4d3  mov     eax, 1
0x18004d4d8  lea     rdx, aBluevalues; "BlueValues"
0x18004d4df  mov     [rsp+4D0h+var_4A0], eax
0x18004d4e3  mov     r8, r13
0x18004d4e6  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004d4ea  mov     rcx, rdi
0x18004d4ed  mov     dword ptr [rsp+4D0h+var_4B0], eax
0x18004d4f1  call    WriteBlendArrayLine
0x18004d4f6  mov     r9d, [rdi+0AF8h]
0x18004d4fd  lea     r8, [rdi+0AFCh]
0x18004d504  mov     ecx, 1
0x18004d509  lea     rdx, aOtherblues; "OtherBlues"
0x18004d510  mov     [rsp+4D0h+var_4A0], ecx
0x18004d514  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004d518  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004d51c  mov     rcx, rdi
0x18004d51f  call    WriteBlendArrayLine
0x18004d524  mov     r9d, [rdi+0D7Ch]
0x18004d52b  lea     r8, [rdi+0D80h]
0x18004d532  mov     ecx, 1
0x18004d537  lea     rdx, aFamilyblues; "FamilyBlues"
0x18004d53e  mov     [rsp+4D0h+var_4A0], ecx
0x18004d542  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004d546  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004d54a  mov     rcx, rdi
0x18004d54d  call    WriteBlendArrayLine
0x18004d552  mov     r9d, [rdi+1100h]
0x18004d559  lea     r8, [rdi+1104h]
0x18004d560  mov     ecx, 1
0x18004d565  lea     rdx, aFamilyotherblu; "FamilyOtherBlues"
0x18004d56c  mov     [rsp+4D0h+var_4A0], ecx
0x18004d570  mov     dword ptr [rsp+4D0h+var_4A8], ecx
0x18004d574  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004d578  mov     rcx, rdi
0x18004d57b  call    WriteBlendArrayLine
0x18004d580  mov     edx, 1
0x18004d585  mov     rcx, rdi
0x18004d588  call    WriteStemSnap
0x18004d58d  mov     r9d, [rdi+198Ch]
0x18004d594  lea     r8, [rdi+1990h]
0x18004d59b  mov     ecx, 1
0x18004d5a0  lea     rdx, aBluescale; "BlueScale"
0x18004d5a7  mov     [rsp+4D0h+var_498], ecx
0x18004d5ab  mov     dword ptr [rsp+4D0h+var_4B0], ecx
0x18004d5af  mov     rcx, rdi
0x18004d5b2  call    WriteBlendLine
0x18004d5b7  mov     r9d, [rdi+19D0h]
0x18004d5be  lea     r8, [rdi+19D4h]
0x18004d5c5  lea     rdx, aBlueshift; "BlueShift"
0x18004d5cc  mov     [rsp+4D0h+var_498], 0
0x18004d5d4  mov     rcx, rdi
0x18004d5d7  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004d5df  call    WriteBlendLine
0x18004d5e4  mov     r9d, [rdi+1A14h]
0x18004d5eb  lea     r8, [rdi+1A18h]
0x18004d5f2  lea     rdx, aBluefuzz; "BlueFuzz"
0x18004d5f9  mov     [rsp+4D0h+var_498], 0
0x18004d601  mov     rcx, rdi
0x18004d604  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004d60c  call    WriteBlendLine
0x18004d611  mov     eax, [rdi+1AA0h]
0x18004d617  lea     r8, [rdi+1A5Ch]
0x18004d61e  mov     r9d, [rdi+1A58h]
0x18004d625  lea     rdx, aForcebold; "ForceBold"
0x18004d62c  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004d630  mov     rcx, rdi
0x18004d633  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004d63b  call    WriteBlendBooleanLine
0x18004d640  mov     r9d, [rdi+1A9Ch]
0x18004d647  lea     rdx, aForceboldthres; "ForceBoldThreshold"
0x18004d64e  mov     r8d, [rdi+1AA0h]
0x18004d655  mov     rcx, rdi
0x18004d658  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004d660  call    WriteNumberLine
0x18004d665  cmp     dword ptr [rdi+46Ch], 0
0x18004d66c  jz      short loc_18004D686
0x18004d66e  cmp     dword ptr [rdi+470h], 1
0x18004d675  jnz     short loc_18004D686
0x18004d677  lea     rdx, aRndstemupFalse; "/RndStemUp false def\r\n"
0x18004d67e  mov     rcx, rdi
0x18004d681  call    PutString
0x18004d686  mov     r9d, [rdi+46Ch]
0x18004d68d  lea     rdx, aLanguagegroup; "LanguageGroup"
0x18004d694  mov     r8d, [rdi+470h]
0x18004d69b  mov     rcx, rdi
0x18004d69e  call    WriteLongNumberLine
0x18004d6a3  mov     r9d, [rdi+44Ch]
0x18004d6aa  lea     rdx, aExpansionfacto; "ExpansionFactor"
0x18004d6b1  mov     r8d, [rdi+450h]
0x18004d6b8  mov     rcx, rdi
0x18004d6bb  mov     dword ptr [rsp+4D0h+var_4B0], 1
0x18004d6c3  call    WriteNumberLine
0x18004d6c8  mov     r9d, [rdi+454h]
0x18004d6cf  lea     rdx, aInitialrandoms; "initialRandomSeed"
0x18004d6d6  mov     r8d, [rdi+458h]
0x18004d6dd  mov     rcx, rdi
0x18004d6e0  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004d6e8  call    WriteNumberLine
0x18004d6ed  cmp     bl, 2
0x18004d6f0  jnz     loc_18004D79A
0x18004d6f6  mov     r9d, [rdi+324h]
0x18004d6fd  lea     rdx, aDefaultwidthx; "defaultWidthX"
0x18004d704  mov     r8d, [rdi+328h]
0x18004d70b  mov     rcx, rdi
0x18004d70e  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004d716  call    WriteNumberLine
0x18004d71b  mov     r9d, [rdi+32Ch]
0x18004d722  lea     rdx, aNominalwidthx; "nominalWidthX"
0x18004d729  mov     r8d, [rdi+330h]
0x18004d730  mov     rcx, rdi
0x18004d733  mov     dword ptr [rsp+4D0h+var_4B0], 0
0x18004d73b  call    WriteNumberLine
0x18004d740  mov     eax, [rdi+1AA4h]
0x18004d746  test    eax, eax
0x18004d748  jz      short loc_18004D79A
0x18004d74a  cmp     dword ptr [rdi+1E8h], 0
0x18004d751  jz      short loc_18004D77D
0x18004d753  add     eax, 2
0x18004d756  cmp     eax, 4D8h
0x18004d75b  jnb     short loc_18004D765
0x18004d75d  mov     r8d, 6Bh ; 'k'
0x18004d763  jmp     short loc_18004D785
0x18004d765  cmp     eax, 846Ch
0x18004d76a  sbb     r8d, r8d
0x18004d76d  and     r8d, 0FFFF846Bh
0x18004d774  add     r8d, 8000h
0x18004d77b  jmp     short loc_18004D785
0x18004d77d  movzx   r8d, word ptr [rdi+1AB4h]
0x18004d785  mov     r9d, 1
0x18004d78b  lea     rdx, aSubroutinenumb; "subroutineNumberBias"
0x18004d792  mov     rcx, rdi
0x18004d795  call    WriteLongNumberLine
0x18004d79a  mov     eax, [rdi+5DCh]
0x18004d7a0  cmp     eax, 2
0x18004d7a3  jnz     short loc_18004D7B3
0x18004d7a5  movsx   r8d, word ptr [rdi+1F28h]
0x18004d7ad  lea     r9d, [rax-1]
0x18004d7b1  jmp     short loc_18004D7CE
0x18004d7b3  cmp     eax, 1
0x18004d7b6  jnz     short loc_18004D7DD
0x18004d7b8  cmp     [rdi+1F34h], al
0x18004d7be  jnz     short loc_18004D7DD
0x18004d7c0  mov     r9d, [rdi+45Ch]
0x18004d7c7  mov     r8d, [rdi+460h]
0x18004d7ce  lea     rdx, aLeniv; "lenIV"
0x18004d7d5  mov     rcx, rdi
0x18004d7d8  call    WriteLongNumberLine
0x18004d7dd  cmp     dword ptr [rdi+1E8h], 0
0x18004d7e4  jle     loc_18004D899
0x18004d7ea  cmp     bl, 2
0x18004d7ed  lea     rdx, aNdv; "NDV"
0x18004d7f4  mov     ecx, 37F8h
0x18004d7f9  mov     eax, 1AA4h
0x18004d7fe  cmovnz  eax, ecx
0x18004d801  mov     r9d, 1
0x18004d807  mov     rcx, rdi
0x18004d80a  mov     ebx, [rax+rdi]
0x18004d80d  mov     r8d, ebx
0x18004d810  call    WriteLongNumberLine
0x18004d815  lea     r8d, [rbx+1]
0x18004d819  mov     r9d, 1
0x18004d81f  lea     rdx, aCdv; "CDV"
0x18004d826  mov     rcx, rdi
0x18004d829  call    WriteLongNumberLine
0x18004d82e  xor     ebx, ebx
0x18004d830  cmp     byte ptr [rdi+1F34h], 1
0x18004d837  jnz     short loc_18004D89B
0x18004d839  movzx   edx, word ptr [rdi+22Eh]
0x18004d840  lea     r9, [rsp+4D0h+var_490]
0x18004d845  lea     r8, [rsp+4D0h+var_488]
0x18004d84a  mov     [rsp+4D0h+var_488], rbx
0x18004d84f  mov     rcx, rdi
0x18004d852  mov     [rsp+4D0h+var_490], bx
0x18004d857  call    XCF_LookUpString
0x18004d85c  mov     rdx, [rsp+4D0h+var_488]
0x18004d861  mov     rcx, rdi
0x18004d864  call    CharStrToSubr
0x18004d869  movzx   edx, word ptr [rdi+22Ch]
0x18004d870  lea     r9, [rsp+4D0h+var_490]
0x18004d875  lea     r8, [rsp+4D0h+var_488]
0x18004d87a  mov     rcx, rdi
0x18004d87d  call    XCF_LookUpString
0x18004d882  mov     rdx, [rsp+4D0h+var_488]
0x18004d887  mov     rcx, rdi
0x18004d88a  call    CharStrToSubr
0x18004d88f  mov     rcx, rdi
0x18004d892  call    NewT1Subr
0x18004d897  jmp     short loc_18004D89B
0x18004d899  xor     ebx, ebx
0x18004d89b  mov     r9d, [rdi+4B8h]
0x18004d8a2  lea     rdx, aLenbuildcharar; "lenBuildCharArray"
0x18004d8a9  mov     r8d, [rdi+4BCh]
0x18004d8b0  mov     rcx, rdi
0x18004d8b3  call    WriteLongNumberLine
0x18004d8b8  cmp     [rdi+4B8h], ebx
0x18004d8be  jz      short loc_18004D8CF
0x18004d8c0  lea     rdx, aBuildchararray; "/BuildCharArray lenBuildCharArray array"...
0x18004d8c7  mov     rcx, rdi
0x18004d8ca  call    PutString
0x18004d8cf  lea     rdx, aMinfeature1616_0; "/MinFeature {16 16} def\r\n"
0x18004d8d6  mov     rcx, rdi
0x18004d8d9  call    PutString
0x18004d8de  lea     rdx, aPassword5839De_0; "/password 5839 def\r\n"
0x18004d8e5  mov     rcx, rdi
0x18004d8e8  call    PutString
0x18004d8ed  mov     edx, 1
0x18004d8f2  mov     rcx, rdi
0x18004d8f5  call    WriteErode
0x18004d8fa  cmp     [rdi+1E8h], ebx
0x18004d900  jz      loc_18004DA61
0x18004d906  lea     rdx, a3IndexBlendGet; "3 index /Blend get /Private get begin\r"...
0x18004d90d  mov     rcx, rdi
0x18004d910  call    PutString
0x18004d915  mov     r9d, [rdi+774h]
0x18004d91c  lea     rdx, aBluevalues; "BlueValues"
0x18004d923  mov     eax, 1
0x18004d928  mov     r8, r13
0x18004d92b  mov     [rsp+4D0h+var_4A0], eax
0x18004d92f  mov     rcx, rdi
0x18004d932  mov     dword ptr [rsp+4D0h+var_4A8], eax
0x18004d936  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18004d93a  call    WriteBlendArrayLine
0x18004d93f  mov     r9d, [rdi+0AF8h]
0x18004d946  lea     r8, [rdi+0AFCh]
0x18004d94d  mov     r13d, 1
0x18004d953  lea     rdx, aOtherblues; "OtherBlues"
0x18004d95a  mov     [rsp+4D0h+var_4A0], r13d
0x18004d95f  mov     rcx, rdi
0x18004d962  mov     dword ptr [rsp+4D0h+var_4A8], r13d
0x18004d967  mov     dword ptr [rsp+4D0h+var_4B0], ebx
0x18004d96b  call    WriteBlendArrayLine
0x18004d970  mov     r9d, [rdi+198Ch]
0x18004d977  lea     r8, [rdi+1990h]
  ... truncated ...
```
