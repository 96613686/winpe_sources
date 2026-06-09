# LexicalAnalyzer::TryTokenizeAsAmbiguousNonAlphanumeric(SymbolType *,ulong *,bool *)

- ea: `0x18000e128`
- end: `0x18000e1ba`
- name: `?TryTokenizeAsAmbiguousNonAlphanumeric@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z`
- size: `146`
- prototype: `__int64 __fastcall(LexicalAnalyzer *__hidden this, enum SymbolType *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000dc40`

## callees

- `0x18000a3a8`
- `0x18000e0fc`
- `0x18000e128`

## pseudocode

```c
__int64 __fastcall LexicalAnalyzer::TryTokenizeAsAmbiguousNonAlphanumeric(
        LexicalAnalyzer *this,
        enum SymbolType *a2,
        unsigned int *a3,
        bool *a4)
{
  _WORD *v5; // rdx
  bool ShouldPreferCurrentTokenAsOperatorGivenPreviousToken; // al
  _DWORD *v7; // r10
  _DWORD *v8; // r8
  struct String *v10; // rcx
  const unsigned __int16 *v11; // rax
  int v12; // eax
  unsigned int v13; // ecx

  *a4 = 0;
  v5 = (_WORD *)*((_QWORD *)this + 4);
  if ( *v5 != 33 )
  {
    if ( *v5 != 42 )
      return 0;
    ShouldPreferCurrentTokenAsOperatorGivenPreviousToken = LexicalAnalyzer::ShouldPreferCurrentTokenAsOperatorGivenPreviousToken(*((struct Token **)this + 1));
    *v7 = !ShouldPreferCurrentTokenAsOperatorGivenPreviousToken + 53;
    *v8 = 1;
LABEL_6:
    *a4 = 1;
    return 0;
  }
  if ( v5[1] == 61 )
  {
    *(_DWORD *)a2 = 49;
    *a3 = 2;
    goto LABEL_6;
  }
  v10 = (LexicalAnalyzer *)((char *)this + 24);
  v11 = &qword_180016F98;
  if ( *(_QWORD *)v10 )
    v11 = *(const unsigned __int16 **)v10;
  v12 = ExceptionHelpers::SetCompilationException(v10, v5 - v11, 1u, 0x65u);
  v13 = -2147024809;
  if ( v12 < 0 )
    return (unsigned int)v12;
  return v13;
}

```

## disassembly

```asm
0x18000e128  sub     rsp, 28h
0x18000e12c  mov     r10, rdx
0x18000e12f  mov     byte ptr [r9], 0
0x18000e133  mov     rdx, [rcx+20h]
0x18000e137  movzx   eax, word ptr [rdx]
0x18000e13a  cmp     ax, 21h ; '!'
0x18000e13e  jz      short loc_18000E164
0x18000e140  cmp     ax, 2Ah ; '*'
0x18000e144  jnz     short loc_18000E17D
0x18000e146  mov     rcx, [rcx+8]; struct Token *
0x18000e14a  call    ?ShouldPreferCurrentTokenAsOperatorGivenPreviousToken@LexicalAnalyzer@@SA_NPEAVToken@@@Z; LexicalAnalyzer::ShouldPreferCurrentTokenAsOperatorGivenPreviousToken(Token *)
0x18000e14f  movzx   edx, al
0x18000e152  xor     edx, 1
0x18000e155  add     edx, 35h ; '5'
0x18000e158  mov     [r10], edx
0x18000e15b  mov     dword ptr [r8], 1
0x18000e162  jmp     short loc_18000E179
0x18000e164  cmp     word ptr [rdx+2], 3Dh ; '='
0x18000e169  jnz     short loc_18000E181
0x18000e16b  mov     dword ptr [r10], 31h ; '1'
0x18000e172  mov     dword ptr [r8], 2
0x18000e179  mov     byte ptr [r9], 1
0x18000e17d  xor     eax, eax
0x18000e17f  jmp     short loc_18000E1B5
0x18000e181  add     rcx, 18h; struct String *
0x18000e185  lea     rax, qword_180016F98
0x18000e18c  mov     r9d, 65h ; 'e'; unsigned int
0x18000e192  cmp     qword ptr [rcx], 0
0x18000e196  lea     r8d, [r9-64h]; unsigned int
0x18000e19a  cmovnz  rax, [rcx]
0x18000e19e  sub     rdx, rax
0x18000e1a1  sar     rdx, 1; unsigned int
0x18000e1a4  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000e1a9  test    eax, eax
0x18000e1ab  mov     ecx, 80070057h
0x18000e1b0  cmovs   ecx, eax
0x18000e1b3  mov     eax, ecx
0x18000e1b5  add     rsp, 28h
0x18000e1b9  retn
```
