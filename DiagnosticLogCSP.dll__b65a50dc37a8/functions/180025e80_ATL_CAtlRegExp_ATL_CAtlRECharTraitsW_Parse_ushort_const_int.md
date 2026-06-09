# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180025e80`
- end: `0x1800260ab`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001f32c`
- `0x180028664`

## callees

- `0x180006c7c`
- `0x180011648`
- `0x180022cd4`
- `0x180025e80`
- `0x1800260b4`
- `0x180026e64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180025f30`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180025f30`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025ea9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026035`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025ea9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180026035`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025ed1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180025ed1`

## string_xrefs

- `0x180025eec`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  void *v4; // rcx
  wchar_t *v5; // rax
  wchar_t *v6; // rdi
  errno_t v7; // eax
  errno_t v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rsi
  wchar_t *v11; // rax
  wchar_t *v13; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = a3;
  v13 = a2;
  v4 = (void *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)a1 + 1) = 0;
  }
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v5 = (wchar_t *)malloc(0x6Au);
  v6 = v5;
  if ( !v5 )
    return 1;
  v7 = memcpy_s_0(v5, 0x6Au, L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})", 0x6Au);
  if ( v7 )
  {
    if ( v7 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v7 == 22 || v7 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v7 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v8 = _wcslwr_s(v6, 0x35u);
  if ( v8 )
  {
    if ( v8 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v8 == 22 || v8 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v8 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v13 = v6;
  v9 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v10 = v9;
  if ( v9 < 0 )
    return 1;
  if ( *v13 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) >= 0 )
    {
      v11 = v13;
      goto LABEL_20;
    }
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) < 0 )
    return 1;
  v11 = ++v13;
LABEL_20:
  LOBYTE(v14) = 1;
  if ( *v11 && (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(a1, &v13, &v14) >= 0 )
  {
    LOBYTE(v14) = 1;
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v13, &v14);
  }
  if ( !*a1 )
  {
    if ( v10 >= *((_QWORD *)a1 + 2) )
      ATL::AtlThrowImpl(-2147024809);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v10 + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
      return 1;
  }
  if ( v6 != L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v6);
  return *a1;
}

```

## disassembly

```asm
0x180025e80  mov     rax, rsp
0x180025e83  mov     [rax+8], rbx
0x180025e87  mov     [rax+20h], rbp
0x180025e8b  mov     [rax+18h], r8d
0x180025e8f  mov     [rax+10h], rdx
0x180025e93  push    rsi
0x180025e94  push    rdi
0x180025e95  push    r14
0x180025e97  sub     rsp, 20h
0x180025e9b  mov     rbx, rcx
0x180025e9e  mov     rcx, [rcx+8]; Block
0x180025ea2  xor     ebp, ebp
0x180025ea4  test    rcx, rcx
0x180025ea7  jz      short loc_180025EB9
0x180025ea9  call    cs:__imp_free
0x180025eb0  nop     dword ptr [rax+rax+00h]
0x180025eb5  mov     [rbx+8], rbp
0x180025eb9  mov     [rbx+10h], rbp
0x180025ebd  mov     [rbx+18h], rbp
0x180025ec1  mov     [rbx+28h], rbp
0x180025ec5  mov     [rbx], ebp
0x180025ec7  mov     [rbx+30h], ebp
0x180025eca  mov     esi, 6Ah ; 'j'
0x180025ecf  mov     ecx, esi; Size
0x180025ed1  call    cs:__imp_malloc
0x180025ed8  nop     dword ptr [rax+rax+00h]
0x180025edd  mov     rdi, rax
0x180025ee0  test    rax, rax
0x180025ee3  jz      loc_180026045
0x180025ee9  mov     r9d, esi; SourceSize
0x180025eec  lea     r14, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180025ef3  mov     r8, r14; Source
0x180025ef6  mov     edx, esi; DestinationSize
0x180025ef8  mov     rcx, rax; Destination
0x180025efb  call    memcpy_s_0
0x180025f00  test    eax, eax
0x180025f02  jz      short loc_180025F28
0x180025f04  cmp     eax, 0Ch
0x180025f07  jz      loc_18002607F
0x180025f0d  cmp     eax, 16h
0x180025f10  jz      loc_180026074
0x180025f16  cmp     eax, 22h ; '"'
0x180025f19  jz      loc_180026074
0x180025f1f  cmp     eax, 50h ; 'P'
0x180025f22  jnz     loc_180026069
0x180025f28  mov     edx, 35h ; '5'; SizeInWords
0x180025f2d  mov     rcx, rdi; String
0x180025f30  call    cs:__imp__wcslwr_s
0x180025f37  nop     dword ptr [rax+rax+00h]
0x180025f3c  test    eax, eax
0x180025f3e  jz      short loc_180025F64
0x180025f40  cmp     eax, 0Ch
0x180025f43  jz      loc_1800260A0
0x180025f49  cmp     eax, 16h
0x180025f4c  jz      loc_180026095
0x180025f52  cmp     eax, 22h ; '"'
0x180025f55  jz      loc_180026095
0x180025f5b  cmp     eax, 50h ; 'P'
0x180025f5e  jnz     loc_18002608A
0x180025f64  mov     [rsp+38h+arg_8], rdi
0x180025f69  mov     edx, 10h
0x180025f6e  mov     rcx, rbx
0x180025f71  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180025f76  movsxd  rsi, eax
0x180025f79  test    eax, eax
0x180025f7b  js      loc_180026045
0x180025f81  mov     rcx, [rsp+38h+arg_8]
0x180025f86  cmp     word ptr [rcx], 5Eh ; '^'
0x180025f8a  mov     rcx, rbx
0x180025f8d  jnz     short loc_180025FB1
0x180025f8f  mov     edx, 1Ch
0x180025f94  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180025f99  test    eax, eax
0x180025f9b  js      loc_180026045
0x180025fa1  mov     rax, [rsp+38h+arg_8]
0x180025fa6  add     rax, 2
0x180025faa  mov     [rsp+38h+arg_8], rax
0x180025faf  jmp     short loc_180025FC8
0x180025fb1  mov     edx, 1Dh
0x180025fb6  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180025fbb  test    eax, eax
0x180025fbd  js      loc_180026045
0x180025fc3  mov     rax, [rsp+38h+arg_8]
0x180025fc8  mov     byte ptr [rsp+38h+arg_10], 1
0x180025fcd  cmp     [rax], bp
0x180025fd0  jz      short loc_180025FFF
0x180025fd2  lea     r8, [rsp+38h+arg_10]
0x180025fd7  lea     rdx, [rsp+38h+arg_8]
0x180025fdc  mov     rcx, rbx
0x180025fdf  call    ?ParseAltE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(ushort const * *,bool &)
0x180025fe4  test    eax, eax
0x180025fe6  js      short loc_180025FFF
0x180025fe8  mov     byte ptr [rsp+38h+arg_10], 1
0x180025fed  lea     r8, [rsp+38h+arg_10]
0x180025ff2  lea     rdx, [rsp+38h+arg_8]
0x180025ff7  mov     rcx, rbx
0x180025ffa  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180025fff  cmp     [rbx], ebp
0x180026001  jnz     short loc_18002602D
0x180026003  mov     rcx, rsi
0x180026006  cmp     rsi, [rbx+10h]
0x18002600a  jnb     short loc_18002605E
0x18002600c  add     rcx, rcx
0x18002600f  mov     rax, [rbx+8]
0x180026013  mov     qword ptr [rax+rcx*8+8], 2
0x18002601c  mov     edx, 1Eh
0x180026021  mov     rcx, rbx
0x180026024  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180026029  test    eax, eax
0x18002602b  js      short loc_180026045
0x18002602d  cmp     rdi, r14
0x180026030  jz      short loc_180026041
0x180026032  mov     rcx, rdi; Block
0x180026035  call    cs:__imp_free
0x18002603c  nop     dword ptr [rax+rax+00h]
0x180026041  mov     eax, [rbx]
0x180026043  jmp     short loc_18002604A
0x180026045  mov     eax, 1
0x18002604a  mov     rbx, [rsp+38h+arg_0]
0x18002604f  mov     rbp, [rsp+38h+arg_18]
0x180026054  add     rsp, 20h
0x180026058  pop     r14
0x18002605a  pop     rdi
0x18002605b  pop     rsi
0x18002605c  retn
0x18002605e  mov     ecx, 80070057h; int
0x180026063  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180026069  mov     ecx, 80004005h; int
0x18002606e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180026074  mov     ecx, 80070057h; int
0x180026079  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002607f  mov     ecx, 8007000Eh; int
0x180026084  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002608a  mov     ecx, 80004005h; int
0x18002608f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180026095  mov     ecx, 80070057h; int
0x18002609a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800260a0  mov     ecx, 8007000Eh; int
0x1800260a5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
