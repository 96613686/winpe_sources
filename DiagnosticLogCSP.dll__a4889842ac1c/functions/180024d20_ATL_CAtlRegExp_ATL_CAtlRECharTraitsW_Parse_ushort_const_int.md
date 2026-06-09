# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180024d20`
- end: `0x180024ee4`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `452`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001e388`
- `0x1800274b4`

## callees

- `0x180010db8`
- `0x180021d98`
- `0x180024d20`
- `0x180024eec`
- `0x180025c98`
- `0x18002697c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180024d9b`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180024d9b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024d49`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024e96`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024d49`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180024e96`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180024d6b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180024d6b`

## string_xrefs

- `0x180024d80`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  void *v4; // rcx
  ATL::Checked *v5; // rax
  wchar_t *v6; // rdi
  errno_t v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rsi
  wchar_t *v10; // rax
  unsigned __int64 v12; // [rsp+20h] [rbp-18h]
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
  v5 = (ATL::Checked *)malloc(0x6Au);
  v6 = (wchar_t *)v5;
  if ( !v5 )
    return 1;
  ATL::Checked::memcpy_s(
    v5,
    (void *)0x6A,
    (unsigned __int64)L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})",
    (const void *)0x6A,
    v12);
  v7 = _wcslwr_s(v6, 0x35u);
  if ( v7 )
  {
    if ( v7 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v7 == 22 || v7 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v7 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v13 = v6;
  v8 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v9 = v8;
  if ( v8 < 0 )
    return 1;
  if ( *v13 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) >= 0 )
    {
      v10 = v13;
      goto LABEL_15;
    }
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) < 0 )
    return 1;
  v10 = ++v13;
LABEL_15:
  LOBYTE(v14) = 1;
  if ( *v10 && (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(a1, &v13, &v14) >= 0 )
  {
    LOBYTE(v14) = 1;
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v13, &v14);
  }
  if ( !*a1 )
  {
    if ( v9 >= *((_QWORD *)a1 + 2) )
      ATL::AtlThrowImpl(-2147024809);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v9 + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
      return 1;
  }
  if ( v6 != (wchar_t *)L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v6);
  return *a1;
}

```

## disassembly

```asm
0x180024d20  mov     rax, rsp
0x180024d23  mov     [rax+8], rbx
0x180024d27  mov     [rax+20h], rbp
0x180024d2b  mov     [rax+18h], r8d
0x180024d2f  mov     [rax+10h], rdx
0x180024d33  push    rsi
0x180024d34  push    rdi
0x180024d35  push    r14; unsigned __int64
0x180024d37  sub     rsp, 20h
0x180024d3b  mov     rbx, rcx
0x180024d3e  mov     rcx, [rcx+8]; Block
0x180024d42  xor     ebp, ebp
0x180024d44  test    rcx, rcx
0x180024d47  jz      short loc_180024D53
0x180024d49  call    cs:__imp_free
0x180024d4f  mov     [rbx+8], rbp
0x180024d53  mov     [rbx+10h], rbp
0x180024d57  mov     [rbx+18h], rbp
0x180024d5b  mov     [rbx+28h], rbp
0x180024d5f  mov     [rbx], ebp
0x180024d61  mov     [rbx+30h], ebp
0x180024d64  mov     esi, 6Ah ; 'j'
0x180024d69  mov     ecx, esi; Size
0x180024d6b  call    cs:__imp_malloc
0x180024d71  mov     rdi, rax
0x180024d74  test    rax, rax
0x180024d77  jz      loc_180024EA0
0x180024d7d  mov     r9d, esi; void *
0x180024d80  lea     r14, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180024d87  mov     r8, r14; unsigned __int64
0x180024d8a  mov     edx, esi; void *
0x180024d8c  mov     rcx, rax; this
0x180024d8f  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180024d94  nop
0x180024d95  lea     edx, [rsi-35h]; SizeInWords
0x180024d98  mov     rcx, rdi; String
0x180024d9b  call    cs:__imp__wcslwr_s
0x180024da1  test    eax, eax
0x180024da3  jz      short loc_180024DC9
0x180024da5  cmp     eax, 0Ch
0x180024da8  jz      loc_180024ED9
0x180024dae  cmp     eax, 16h
0x180024db1  jz      loc_180024ECE
0x180024db7  cmp     eax, 22h ; '"'
0x180024dba  jz      loc_180024ECE
0x180024dc0  cmp     eax, 50h ; 'P'
0x180024dc3  jnz     loc_180024EC3
0x180024dc9  mov     [rsp+38h+arg_8], rdi
0x180024dce  mov     edx, 10h
0x180024dd3  mov     rcx, rbx
0x180024dd6  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024ddb  movsxd  rsi, eax
0x180024dde  test    eax, eax
0x180024de0  js      loc_180024EA0
0x180024de6  mov     rcx, [rsp+38h+arg_8]
0x180024deb  cmp     word ptr [rcx], 5Eh ; '^'
0x180024def  mov     rcx, rbx
0x180024df2  jnz     short loc_180024E16
0x180024df4  mov     edx, 1Ch
0x180024df9  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024dfe  test    eax, eax
0x180024e00  js      loc_180024EA0
0x180024e06  mov     rax, [rsp+38h+arg_8]
0x180024e0b  add     rax, 2
0x180024e0f  mov     [rsp+38h+arg_8], rax
0x180024e14  jmp     short loc_180024E29
0x180024e16  mov     edx, 1Dh
0x180024e1b  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024e20  test    eax, eax
0x180024e22  js      short loc_180024EA0
0x180024e24  mov     rax, [rsp+38h+arg_8]
0x180024e29  mov     byte ptr [rsp+38h+arg_10], 1
0x180024e2e  cmp     [rax], bp
0x180024e31  jz      short loc_180024E60
0x180024e33  lea     r8, [rsp+38h+arg_10]
0x180024e38  lea     rdx, [rsp+38h+arg_8]
0x180024e3d  mov     rcx, rbx
0x180024e40  call    ?ParseAltE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(ushort const * *,bool &)
0x180024e45  test    eax, eax
0x180024e47  js      short loc_180024E60
0x180024e49  mov     byte ptr [rsp+38h+arg_10], 1
0x180024e4e  lea     r8, [rsp+38h+arg_10]
0x180024e53  lea     rdx, [rsp+38h+arg_8]
0x180024e58  mov     rcx, rbx
0x180024e5b  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180024e60  cmp     [rbx], ebp
0x180024e62  jnz     short loc_180024E8E
0x180024e64  mov     rcx, rsi
0x180024e67  cmp     rsi, [rbx+10h]
0x180024e6b  jnb     short loc_180024EB8
0x180024e6d  add     rcx, rcx
0x180024e70  mov     rax, [rbx+8]
0x180024e74  mov     qword ptr [rax+rcx*8+8], 2
0x180024e7d  mov     edx, 1Eh
0x180024e82  mov     rcx, rbx
0x180024e85  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180024e8a  test    eax, eax
0x180024e8c  js      short loc_180024EA0
0x180024e8e  cmp     rdi, r14
0x180024e91  jz      short loc_180024E9C
0x180024e93  mov     rcx, rdi; Block
0x180024e96  call    cs:__imp_free
0x180024e9c  mov     eax, [rbx]
0x180024e9e  jmp     short loc_180024EA5
0x180024ea0  mov     eax, 1
0x180024ea5  mov     rbx, [rsp+38h+arg_0]
0x180024eaa  mov     rbp, [rsp+38h+arg_18]
0x180024eaf  add     rsp, 20h
0x180024eb3  pop     r14
0x180024eb5  pop     rdi
0x180024eb6  pop     rsi
0x180024eb7  retn
0x180024eb8  mov     ecx, 80070057h; int
0x180024ebd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ec3  mov     ecx, 80004005h; int
0x180024ec8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ece  mov     ecx, 80070057h; int
0x180024ed3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180024ed9  mov     ecx, 8007000Eh; int
0x180024ede  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
