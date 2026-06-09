# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x18000ce70`
- end: `0x18000d07e`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800098d0`
- `0x1800140dc`

## callees

- `0x18000139c`
- `0x18000ce70`
- `0x18000db9c`
- `0x18000dc18`

## import_xrefs

- `msvcrt!malloc` at `0x18000cecd`
- `msvcrt!malloc` at `0x18000cecd`
- `msvcrt!free` at `0x18000ce94`
- `msvcrt!free` at `0x18000d016`
- `msvcrt!free` at `0x18000ce94`
- `msvcrt!free` at `0x18000d016`
- `msvcrt!memcpy_s` at `0x18000cef1`
- `msvcrt!memcpy_s` at `0x18000cef1`
- `msvcrt!_wcslwr_s` at `0x18000cf28`
- `msvcrt!_wcslwr_s` at `0x18000cf28`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2)
{
  void *v3; // rcx
  __int64 v5; // rax
  size_t v6; // rsi
  wchar_t *v7; // rax
  wchar_t *v8; // rdi
  errno_t v10; // eax
  errno_t v11; // eax
  int v12; // eax
  unsigned __int64 v13; // rsi
  wchar_t *v14; // rax
  char v15; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *v16; // [rsp+48h] [rbp+10h] BYREF

  v3 = (void *)*((_QWORD *)a1 + 1);
  if ( v3 )
  {
    free(v3);
    *((_QWORD *)a1 + 1) = 0;
  }
  *((_QWORD *)a1 + 2) = 0;
  v5 = -1;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  do
    ++v5;
  while ( a2[v5] );
  v6 = 2 * (int)v5 + 2;
  v7 = (wchar_t *)malloc(v6);
  v8 = v7;
  if ( !v7 )
    return 1;
  v10 = memcpy_s(v7, v6, a2, v6);
  if ( v10 )
  {
    if ( v10 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v10 == 22 || v10 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v10 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v11 = _wcslwr_s(v8, (int)(v6 >> 1));
  if ( v11 )
  {
    if ( v11 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v11 == 22 || v11 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v11 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v16 = v8;
  v12 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 16);
  v13 = v12;
  if ( v12 < 0 )
    return 1;
  if ( *v16 == 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 28) >= 0 )
    {
      v14 = ++v16;
      goto LABEL_23;
    }
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 29) < 0 )
    return 1;
  v14 = v16;
LABEL_23:
  v15 = 1;
  if ( *v14 )
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v16, &v15);
  if ( !*a1 )
  {
    if ( v13 >= *((_QWORD *)a1 + 2) )
      ATL::AtlThrowImpl(-2147024809);
    *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v13 + 8) = 2;
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(a1, 30) < 0 )
      return 1;
  }
  if ( v8 != a2 )
    free(v8);
  return *a1;
}

```

## disassembly

```asm
0x18000ce70  mov     [rsp+arg_10], rbx
0x18000ce75  mov     [rsp+arg_18], rbp
0x18000ce7a  push    rsi
0x18000ce7b  push    rdi
0x18000ce7c  push    r14
0x18000ce7e  sub     rsp, 20h
0x18000ce82  mov     rbx, rcx
0x18000ce85  xor     r14d, r14d
0x18000ce88  mov     rcx, [rcx+8]; Block
0x18000ce8c  mov     rbp, rdx
0x18000ce8f  test    rcx, rcx
0x18000ce92  jz      short loc_18000CE9E
0x18000ce94  call    cs:__imp_free
0x18000ce9a  mov     [rbx+8], r14
0x18000ce9e  mov     [rbx+10h], r14
0x18000cea2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cea6  mov     [rbx+18h], r14
0x18000ceaa  mov     [rbx+28h], r14
0x18000ceae  mov     [rbx], r14d
0x18000ceb1  mov     [rbx+30h], r14d
0x18000ceb5  inc     rax
0x18000ceb8  cmp     [rbp+rax*2+0], r14w
0x18000cebe  jnz     short loc_18000CEB5
0x18000cec0  lea     eax, ds:2[rax*2]
0x18000cec7  movsxd  rsi, eax
0x18000ceca  mov     rcx, rsi; Size
0x18000cecd  call    cs:__imp_malloc
0x18000ced3  mov     rdi, rax
0x18000ced6  test    rax, rax
0x18000ced9  jnz     short loc_18000CEE5
0x18000cedb  mov     eax, 1
0x18000cee0  jmp     loc_18000D01E
0x18000cee5  mov     r9, rsi; SourceSize
0x18000cee8  mov     r8, rbp; Source
0x18000ceeb  mov     rdx, rsi; DestinationSize
0x18000ceee  mov     rcx, rdi; Destination
0x18000cef1  call    cs:__imp_memcpy_s
0x18000cef7  test    eax, eax
0x18000cef9  jz      short loc_18000CF1F
0x18000cefb  cmp     eax, 0Ch
0x18000cefe  jz      loc_18000D047
0x18000cf04  cmp     eax, 16h
0x18000cf07  jz      loc_18000D03C
0x18000cf0d  cmp     eax, 22h ; '"'
0x18000cf10  jz      loc_18000D03C
0x18000cf16  cmp     eax, 50h ; 'P'
0x18000cf19  jnz     loc_18000D031
0x18000cf1f  shr     rsi, 1
0x18000cf22  mov     rcx, rdi; String
0x18000cf25  movsxd  rdx, esi; SizeInWords
0x18000cf28  call    cs:__imp__wcslwr_s
0x18000cf2e  test    eax, eax
0x18000cf30  jz      short loc_18000CF56
0x18000cf32  cmp     eax, 0Ch
0x18000cf35  jz      loc_18000D068
0x18000cf3b  cmp     eax, 16h
0x18000cf3e  jz      loc_18000D05D
0x18000cf44  cmp     eax, 22h ; '"'
0x18000cf47  jz      loc_18000D05D
0x18000cf4d  cmp     eax, 50h ; 'P'
0x18000cf50  jnz     loc_18000D052
0x18000cf56  mov     edx, 10h
0x18000cf5b  mov     [rsp+38h+arg_8], rdi
0x18000cf60  mov     rcx, rbx
0x18000cf63  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000cf68  movsxd  rsi, eax
0x18000cf6b  test    eax, eax
0x18000cf6d  js      loc_18000CEDB
0x18000cf73  mov     rax, [rsp+38h+arg_8]
0x18000cf78  mov     rcx, rbx
0x18000cf7b  cmp     word ptr [rax], 5Eh ; '^'
0x18000cf7f  jnz     short loc_18000CFA3
0x18000cf81  mov     edx, 1Ch
0x18000cf86  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000cf8b  test    eax, eax
0x18000cf8d  js      loc_18000CEDB
0x18000cf93  mov     rax, [rsp+38h+arg_8]
0x18000cf98  add     rax, 2
0x18000cf9c  mov     [rsp+38h+arg_8], rax
0x18000cfa1  jmp     short loc_18000CFBA
0x18000cfa3  mov     edx, 1Dh
0x18000cfa8  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000cfad  test    eax, eax
0x18000cfaf  js      loc_18000CEDB
0x18000cfb5  mov     rax, [rsp+38h+arg_8]
0x18000cfba  mov     [rsp+38h+arg_0], 1
0x18000cfbf  cmp     [rax], r14w
0x18000cfc3  jz      short loc_18000CFD7
0x18000cfc5  lea     r8, [rsp+38h+arg_0]
0x18000cfca  mov     rcx, rbx
0x18000cfcd  lea     rdx, [rsp+38h+arg_8]
0x18000cfd2  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x18000cfd7  cmp     [rbx], r14d
0x18000cfda  jnz     short loc_18000D00E
0x18000cfdc  mov     rcx, rsi
0x18000cfdf  cmp     rsi, [rbx+10h]
0x18000cfe3  jnb     loc_18000D073
0x18000cfe9  mov     rax, [rbx+8]
0x18000cfed  add     rcx, rcx
0x18000cff0  mov     edx, 1Eh
0x18000cff5  mov     qword ptr [rax+rcx*8+8], 2
0x18000cffe  mov     rcx, rbx
0x18000d001  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x18000d006  test    eax, eax
0x18000d008  js      loc_18000CEDB
0x18000d00e  cmp     rdi, rbp
0x18000d011  jz      short loc_18000D01C
0x18000d013  mov     rcx, rdi; Block
0x18000d016  call    cs:__imp_free
0x18000d01c  mov     eax, [rbx]
0x18000d01e  mov     rbx, [rsp+38h+arg_10]
0x18000d023  mov     rbp, [rsp+38h+arg_18]
0x18000d028  add     rsp, 20h
0x18000d02c  pop     r14
0x18000d02e  pop     rdi
0x18000d02f  pop     rsi
0x18000d030  retn
0x18000d031  mov     ecx, 80004005h; int
0x18000d036  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d03c  mov     ecx, 80070057h; int
0x18000d041  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d047  mov     ecx, 8007000Eh; int
0x18000d04c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d052  mov     ecx, 80004005h; int
0x18000d057  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d05d  mov     ecx, 80070057h; int
0x18000d062  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d068  mov     ecx, 8007000Eh; int
0x18000d06d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d073  mov     ecx, 80070057h; int
0x18000d078  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
