# LexicalAnalyzer::TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName(SymbolType *,ulong *,bool *)

- ea: `0x18000e26c`
- end: `0x18000e3cb`
- name: `?TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z`
- size: `351`
- prototype: `__int64 __fastcall(LexicalAnalyzer *__hidden this, enum SymbolType *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000dc40`

## callees

- `0x18000a3a8`
- `0x18000dffc`
- `0x18000e080`
- `0x18000e0fc`
- `0x18000e26c`
- `0x180011816`

## pseudocode

```c
__int64 __fastcall LexicalAnalyzer::TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName(
        LexicalAnalyzer *this,
        enum SymbolType *a2,
        unsigned int *a3,
        bool *a4)
{
  unsigned __int16 *v4; // rdi
  unsigned int NCNameLength; // eax
  __int64 v10; // rsi
  int v11; // eax
  struct String *v12; // rcx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  unsigned int v15; // ecx
  bool v17; // zf

  v4 = (unsigned __int16 *)*((_QWORD *)this + 4);
  *a4 = 0;
  NCNameLength = LexicalAnalyzer::GetNCNameLength(v4);
  v10 = NCNameLength;
  if ( !NCNameLength )
    return 0;
  if ( !LexicalAnalyzer::ShouldPreferCurrentTokenAsOperatorGivenPreviousToken(*((struct Token **)this + 1)) )
  {
    if ( !wcsncmp_0(&v4[v10], L"(", 1u) )
    {
      v11 = LexicalAnalyzer::IsNodeTypeString(v4, (unsigned int)v10) ? 33 : 44;
    }
    else
    {
      v17 = wcsncmp_0(&v4[v10], L"::", 2u) == 0;
      v11 = 31;
      if ( !v17 )
        v11 = 55;
    }
    goto LABEL_19;
  }
  if ( !wcsncmp_0(L"and", v4, (unsigned int)v10) )
  {
    v11 = 48;
LABEL_19:
    *(_DWORD *)a2 = v11;
    *a3 = v10;
    *a4 = 1;
    return 0;
  }
  if ( !wcsncmp_0(L"or", v4, (unsigned int)v10) )
  {
    v11 = 47;
    goto LABEL_19;
  }
  if ( !wcsncmp_0(L"mod", v4, (unsigned int)v10) || !wcsncmp_0(L"div", v4, (unsigned int)v10) )
  {
    v11 = 53;
    goto LABEL_19;
  }
  v12 = (LexicalAnalyzer *)((char *)this + 24);
  v13 = &qword_180016F98;
  if ( *((_QWORD *)this + 3) )
    v13 = *(const unsigned __int16 **)v12;
  v14 = ExceptionHelpers::SetCompilationException(v12, v4 - v13, v10, 0x6Du);
  v15 = -2147024809;
  if ( v14 < 0 )
    return (unsigned int)v14;
  return v15;
}

```

## disassembly

```asm
0x18000e26c  push    rbx
0x18000e26e  push    rbp
0x18000e26f  push    rsi
0x18000e270  push    rdi
0x18000e271  push    r14
0x18000e273  push    r15
0x18000e275  sub     rsp, 28h
0x18000e279  mov     rdi, [rcx+20h]
0x18000e27d  mov     rbp, rcx
0x18000e280  mov     rcx, rdi; unsigned __int16 *
0x18000e283  mov     byte ptr [r9], 0
0x18000e287  mov     r14, r9
0x18000e28a  mov     r15, r8
0x18000e28d  mov     rbx, rdx
0x18000e290  call    ?GetNCNameLength@LexicalAnalyzer@@SAKPEBG@Z; LexicalAnalyzer::GetNCNameLength(ushort const *)
0x18000e295  mov     esi, eax
0x18000e297  test    eax, eax
0x18000e299  jz      loc_18000E3BC
0x18000e29f  mov     rcx, [rbp+8]; struct Token *
0x18000e2a3  call    ?ShouldPreferCurrentTokenAsOperatorGivenPreviousToken@LexicalAnalyzer@@SA_NPEAVToken@@@Z; LexicalAnalyzer::ShouldPreferCurrentTokenAsOperatorGivenPreviousToken(Token *)
0x18000e2a8  test    al, al
0x18000e2aa  jz      loc_18000E35D
0x18000e2b0  mov     r8d, esi; MaxCount
0x18000e2b3  lea     rcx, aAnd; "and"
0x18000e2ba  mov     rdx, rdi; String2
0x18000e2bd  call    wcsncmp_0
0x18000e2c2  test    eax, eax
0x18000e2c4  jnz     short loc_18000E2D0
0x18000e2c6  mov     eax, 30h ; '0'
0x18000e2cb  jmp     loc_18000E3B3
0x18000e2d0  mov     r8d, esi; MaxCount
0x18000e2d3  lea     rcx, aOr; "or"
0x18000e2da  mov     rdx, rdi; String2
0x18000e2dd  call    wcsncmp_0
0x18000e2e2  test    eax, eax
0x18000e2e4  jnz     short loc_18000E2F0
0x18000e2e6  mov     eax, 2Fh ; '/'
0x18000e2eb  jmp     loc_18000E3B3
0x18000e2f0  mov     r8d, esi; MaxCount
0x18000e2f3  lea     rcx, aMod; "mod"
0x18000e2fa  mov     rdx, rdi; String2
0x18000e2fd  call    wcsncmp_0
0x18000e302  test    eax, eax
0x18000e304  jz      short loc_18000E31C
0x18000e306  mov     r8d, esi; MaxCount
0x18000e309  lea     rcx, aDiv; "div"
0x18000e310  mov     rdx, rdi; String2
0x18000e313  call    wcsncmp_0
0x18000e318  test    eax, eax
0x18000e31a  jnz     short loc_18000E326
0x18000e31c  mov     eax, 35h ; '5'
0x18000e321  jmp     loc_18000E3B3
0x18000e326  lea     rcx, [rbp+18h]; struct String *
0x18000e32a  mov     r9d, 6Dh ; 'm'; unsigned int
0x18000e330  cmp     qword ptr [rcx], 0
0x18000e334  lea     rax, qword_180016F98
0x18000e33b  mov     r8d, esi; unsigned int
0x18000e33e  cmovnz  rax, [rcx]
0x18000e342  sub     rdi, rax
0x18000e345  sar     rdi, 1
0x18000e348  mov     edx, edi; unsigned int
0x18000e34a  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000e34f  test    eax, eax
0x18000e351  mov     ecx, 80070057h
0x18000e356  cmovs   ecx, eax
0x18000e359  mov     eax, ecx
0x18000e35b  jmp     short loc_18000E3BE
0x18000e35d  lea     rbp, [rdi+rsi*2]
0x18000e361  mov     r8d, 1; MaxCount
0x18000e367  mov     rcx, rbp; String1
0x18000e36a  lea     rdx, asc_180017180; "("
0x18000e371  call    wcsncmp_0
0x18000e376  test    eax, eax
0x18000e378  jnz     short loc_18000E390
0x18000e37a  mov     edx, esi; MaxCount
0x18000e37c  mov     rcx, rdi; String1
0x18000e37f  call    ?IsNodeTypeString@LexicalAnalyzer@@SA_NPEBGK@Z; LexicalAnalyzer::IsNodeTypeString(ushort const *,ulong)
0x18000e384  neg     al
0x18000e386  sbb     eax, eax
0x18000e388  and     eax, 0FFFFFFF5h
0x18000e38b  add     eax, 2Ch ; ','
0x18000e38e  jmp     short loc_18000E3B3
0x18000e390  mov     r8d, 2; MaxCount
0x18000e396  lea     rdx, asc_180017178; "::"
0x18000e39d  mov     rcx, rbp; String1
0x18000e3a0  call    wcsncmp_0
0x18000e3a5  test    eax, eax
0x18000e3a7  mov     eax, 1Fh
0x18000e3ac  jz      short loc_18000E3B3
0x18000e3ae  mov     eax, 37h ; '7'
0x18000e3b3  mov     [rbx], eax
0x18000e3b5  mov     [r15], esi
0x18000e3b8  mov     byte ptr [r14], 1
0x18000e3bc  xor     eax, eax
0x18000e3be  add     rsp, 28h
0x18000e3c2  pop     r15
0x18000e3c4  pop     r14
0x18000e3c6  pop     rdi
0x18000e3c7  pop     rsi
0x18000e3c8  pop     rbp
0x18000e3c9  pop     rbx
0x18000e3ca  retn
```
