# LexicalAnalyzer::ComputeNextToken(void)

- ea: `0x18000dc40`
- end: `0x18000dfa1`
- name: `?ComputeNextToken@LexicalAnalyzer@@QEAAJXZ`
- size: `865`
- prototype: `__int64 __fastcall(LexicalAnalyzer *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000f138`

## callees

- `0x180001078`
- `0x1800064a8`
- `0x18000a240`
- `0x18000a3a8`
- `0x18000dc40`
- `0x18000dfa8`
- `0x18000e128`
- `0x18000e1c0`
- `0x18000e26c`
- `0x180010f08`
- `0x180010fac`

## pseudocode

```c
__int64 __fastcall LexicalAnalyzer::ComputeNextToken(LexicalAnalyzer *this)
{
  __int16 *v1; // r11
  unsigned int v2; // esi
  unsigned int v3; // edx
  __int16 v5; // r10
  void *v6; // rax
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdi
  int v9; // edi
  char v10; // cl
  unsigned int i; // r8d
  unsigned int j; // eax
  _WORD *v13; // rcx
  _WORD *v14; // r8
  bool v15; // zf
  _WORD *m; // rcx
  char v17; // al
  struct String *v18; // rcx
  const unsigned __int16 *v19; // r8
  int v20; // eax
  unsigned int v21; // ecx
  char v23; // cl
  int k; // r9d
  __int64 v25; // r15
  unsigned __int64 v26; // r8
  const unsigned __int16 *v27; // rdx
  void *v28; // rax
  const unsigned __int16 *v29; // r8
  __int64 v30; // rsi
  __int64 v31; // [rsp+60h] [rbp+40h] BYREF
  int v32; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v33; // [rsp+70h] [rbp+50h] BYREF

  v1 = (__int16 *)*((_QWORD *)this + 4);
  v2 = 58;
  v3 = 0;
  v32 = 58;
  v33 = 0;
  v5 = *v1;
  if ( !*v1 )
  {
    v31 = 0;
    v6 = operator new(0x38u);
    if ( v6 )
    {
      v7 = &qword_180016F98;
      if ( *((_QWORD *)this + 3) )
        v7 = (const unsigned __int16 *)*((_QWORD *)this + 3);
      v8 = Token::Token(v6, &v31, 58, (__int64)(*((_QWORD *)this + 4) - (_QWORD)v7) >> 1);
    }
    else
    {
      v8 = 0;
    }
    InvasivePtr<Node>::Reset((char *)this + 16);
    *((_QWORD *)this + 2) = v8;
    if ( v8 )
    {
      *(_DWORD *)this = 2;
      v9 = 0;
      goto LABEL_60;
    }
LABEL_8:
    v9 = -2147024882;
LABEL_60:
    String::Reset((String *)&v31);
    return (unsigned int)v9;
  }
  v10 = 0;
  LOBYTE(v31) = 0;
  for ( i = 0; i < 5; ++i )
  {
    if ( v5 == word_180019650[4 * i] && v1[1] == word_180019652[4 * i] )
    {
      v2 = dword_180019654[2 * i];
      v3 = 2;
LABEL_21:
      v10 = 1;
      v33 = v3;
      LOBYTE(v31) = 1;
      v32 = v2;
      goto LABEL_22;
    }
  }
  for ( j = 0; j < 0x10; ++j )
  {
    if ( v5 == word_1800195D0[4 * j] )
    {
      v2 = dword_1800195D4[2 * j];
      v3 = 1;
      goto LABEL_21;
    }
  }
LABEL_22:
  if ( v10 )
  {
LABEL_52:
    v25 = v3;
    v26 = v3;
    v27 = (const unsigned __int16 *)*((_QWORD *)this + 4);
    v31 = 0;
    v9 = String::Initialize((String *)&v31, v27, v26);
    if ( v9 < 0 )
      goto LABEL_60;
    v28 = operator new(0x38u);
    if ( v28 )
    {
      v29 = &qword_180016F98;
      if ( *((_QWORD *)this + 3) )
        v29 = (const unsigned __int16 *)*((_QWORD *)this + 3);
      v30 = Token::Token(v28, &v31, v2, (__int64)(*((_QWORD *)this + 4) - (_QWORD)v29) >> 1);
    }
    else
    {
      v30 = 0;
    }
    InvasivePtr<Node>::Reset((char *)this + 16);
    *((_QWORD *)this + 2) = v30;
    if ( v30 )
    {
      *((_QWORD *)this + 4) += 2 * v25;
      *((_QWORD *)this + 4) = LexicalAnalyzer::FindNextNonWhitespaceCharacter(*((const unsigned __int16 **)this + 4));
      *(_DWORD *)this = 1;
      goto LABEL_60;
    }
    goto LABEL_8;
  }
  v9 = LexicalAnalyzer::TryTokenizeAsAmbiguousNonAlphanumeric(this, (enum SymbolType *)&v32, &v33, (bool *)&v31);
  if ( v9 < 0 )
    goto LABEL_50;
  if ( (_BYTE)v31 )
    goto LABEL_49;
  v9 = LexicalAnalyzer::TryTokenizeAsLiteral(this, (enum SymbolType *)&v32, &v33, (bool *)&v31);
  if ( v9 < 0 )
    goto LABEL_50;
  if ( (_BYTE)v31 )
  {
LABEL_49:
    v2 = v32;
    v3 = v33;
    goto LABEL_52;
  }
  v13 = (_WORD *)*((_QWORD *)this + 4);
  LOBYTE(v31) = 0;
  v14 = v13 + 1;
  if ( (unsigned __int16)(*v13 - 48) <= 9u )
  {
    v23 = 0;
    v3 = 1;
    for ( k = 1; ; ++k )
    {
      if ( *v14 == 46 )
      {
        if ( v23 )
          goto LABEL_33;
        v23 = 1;
      }
      else if ( (unsigned __int16)(*v14 - 48) > 9u )
      {
        goto LABEL_33;
      }
      v3 = k + 1;
      ++v14;
    }
  }
  v15 = *v13 == 46;
  LOBYTE(v31) = 0;
  if ( v15 )
  {
    if ( (unsigned __int16)(*v14 - 48) > 9u )
    {
      v2 = 11;
      v3 = (v13[1] == 46) + 1;
    }
    else
    {
      v3 = 2;
      for ( m = v13 + 2; (unsigned __int16)(*m - 48) <= 9u; ++m )
        ++v3;
LABEL_33:
      v2 = 43;
    }
    v17 = 1;
    v9 = 0;
LABEL_51:
    if ( !v17 )
      return (unsigned int)v9;
    goto LABEL_52;
  }
  v9 = LexicalAnalyzer::TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName(
         this,
         (enum SymbolType *)&v32,
         &v33,
         (bool *)&v31);
  if ( v9 < 0 )
  {
LABEL_50:
    v2 = v32;
    v3 = v33;
    v17 = v31;
    goto LABEL_51;
  }
  if ( (_BYTE)v31 )
    goto LABEL_49;
  v18 = (LexicalAnalyzer *)((char *)this + 24);
  v19 = &qword_180016F98;
  if ( *((_QWORD *)this + 3) )
    v19 = *(const unsigned __int16 **)v18;
  v20 = ExceptionHelpers::SetCompilationException(v18, (__int64)(*((_QWORD *)this + 4) - (_QWORD)v19) >> 1, 1u, 0x70u);
  v21 = -2147024809;
  if ( v20 < 0 )
    return (unsigned int)v20;
  return v21;
}

```

## disassembly

```asm
0x18000dc40  mov     [rsp-38h+arg_18], rbx
0x18000dc45  push    rbp
0x18000dc46  push    rsi
0x18000dc47  push    rdi
0x18000dc48  push    r12
0x18000dc4a  push    r13
0x18000dc4c  push    r14
0x18000dc4e  push    r15
0x18000dc50  mov     rbp, rsp
0x18000dc53  sub     rsp, 20h
0x18000dc57  mov     r11, [rcx+20h]
0x18000dc5b  xor     r12d, r12d
0x18000dc5e  mov     esi, 3Ah ; ':'
0x18000dc63  mov     edx, r12d
0x18000dc66  mov     rbx, rcx
0x18000dc69  mov     [rbp+arg_8], esi
0x18000dc6c  mov     [rbp+arg_10], edx
0x18000dc6f  movzx   r10d, word ptr [r11]
0x18000dc73  test    r10w, r10w
0x18000dc77  jnz     short loc_18000DCE5
0x18000dc79  lea     ecx, [rsi-2]; Size
0x18000dc7c  mov     [rbp+arg_0], r12
0x18000dc80  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dc85  test    rax, rax
0x18000dc88  jz      short loc_18000DCB8
0x18000dc8a  cmp     [rbx+18h], r12
0x18000dc8e  lea     r8, qword_180016F98
0x18000dc95  mov     r9, [rbx+20h]
0x18000dc99  lea     rdx, [rbp+arg_0]
0x18000dc9d  cmovnz  r8, [rbx+18h]
0x18000dca2  mov     rcx, rax
0x18000dca5  sub     r9, r8
0x18000dca8  mov     r8d, esi
0x18000dcab  sar     r9, 1
0x18000dcae  call    ??0Token@@QEAA@AEAVString@@W4SymbolType@@K@Z; Token::Token(String &,SymbolType,ulong)
0x18000dcb3  mov     rdi, rax
0x18000dcb6  jmp     short loc_18000DCBB
0x18000dcb8  mov     rdi, r12
0x18000dcbb  lea     rcx, [rbx+10h]
0x18000dcbf  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x18000dcc4  mov     [rbx+10h], rdi
0x18000dcc8  test    rdi, rdi
0x18000dccb  jnz     short loc_18000DCD7
0x18000dccd  mov     edi, 8007000Eh
0x18000dcd2  jmp     loc_18000DF81
0x18000dcd7  mov     dword ptr [rbx], 2
0x18000dcdd  mov     edi, r12d
0x18000dce0  jmp     loc_18000DF81
0x18000dce5  mov     cl, r12b
0x18000dce8  lea     rdi, cs:180000000h
0x18000dcef  mov     byte ptr [rbp+arg_0], cl
0x18000dcf2  mov     r8d, r12d
0x18000dcf5  mov     r13d, 1
0x18000dcfb  cmp     r8d, 5
0x18000dcff  jnb     short loc_18000DD33
0x18000dd01  mov     r9d, r8d
0x18000dd04  cmp     r10w, rva word_180019650[rdi+r9*8]
0x18000dd0d  jnz     short loc_18000DD1F
0x18000dd0f  movzx   eax, rva word_180019652[rdi+r9*8]
0x18000dd18  cmp     [r11+2], ax
0x18000dd1d  jz      short loc_18000DD24
0x18000dd1f  add     r8d, r13d
0x18000dd22  jmp     short loc_18000DCFB
0x18000dd24  mov     esi, rva dword_180019654[rdi+r9*8]
0x18000dd2c  mov     edx, 2
0x18000dd31  jmp     short loc_18000DD59
0x18000dd33  mov     eax, r12d
0x18000dd36  cmp     eax, 10h
0x18000dd39  jnb     short loc_18000DD65
0x18000dd3b  mov     r8d, eax
0x18000dd3e  cmp     r10w, rva word_1800195D0[rdi+r8*8]
0x18000dd47  jz      short loc_18000DD4E
0x18000dd49  add     eax, r13d
0x18000dd4c  jmp     short loc_18000DD36
0x18000dd4e  mov     esi, rva dword_1800195D4[rdi+r8*8]
0x18000dd56  mov     edx, r13d
0x18000dd59  mov     cl, r13b
0x18000dd5c  mov     [rbp+arg_10], edx
0x18000dd5f  mov     byte ptr [rbp+arg_0], cl
0x18000dd62  mov     [rbp+arg_8], esi
0x18000dd65  test    cl, cl
0x18000dd67  jnz     loc_18000DEF6
0x18000dd6d  lea     r9, [rbp+arg_0]; bool *
0x18000dd71  mov     rcx, rbx; this
0x18000dd74  lea     r8, [rbp+arg_10]; unsigned int *
0x18000dd78  lea     rdx, [rbp+arg_8]; enum SymbolType *
0x18000dd7c  call    ?TryTokenizeAsAmbiguousNonAlphanumeric@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z; LexicalAnalyzer::TryTokenizeAsAmbiguousNonAlphanumeric(SymbolType *,ulong *,bool *)
0x18000dd81  mov     edi, eax
0x18000dd83  test    eax, eax
0x18000dd85  js      loc_18000DEE5
0x18000dd8b  cmp     byte ptr [rbp+arg_0], r12b
0x18000dd8f  jnz     loc_18000DEDD
0x18000dd95  lea     r9, [rbp+arg_0]; bool *
0x18000dd99  mov     rcx, rbx; this
0x18000dd9c  lea     r8, [rbp+arg_10]; unsigned int *
0x18000dda0  lea     rdx, [rbp+arg_8]; enum SymbolType *
0x18000dda4  call    ?TryTokenizeAsLiteral@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z; LexicalAnalyzer::TryTokenizeAsLiteral(SymbolType *,ulong *,bool *)
0x18000dda9  mov     edi, eax
0x18000ddab  test    eax, eax
0x18000ddad  js      loc_18000DEE5
0x18000ddb3  cmp     byte ptr [rbp+arg_0], r12b
0x18000ddb7  jnz     loc_18000DEDD
0x18000ddbd  mov     rcx, [rbx+20h]
0x18000ddc1  mov     r10w, 30h ; '0'
0x18000ddc6  mov     r11w, 9
0x18000ddcb  mov     byte ptr [rbp+arg_0], r12b
0x18000ddcf  movzx   eax, word ptr [rcx]
0x18000ddd2  lea     r8, [rcx+2]
0x18000ddd6  sub     ax, r10w
0x18000ddda  cmp     ax, r11w
0x18000ddde  jbe     loc_18000DEA2
0x18000dde4  cmp     word ptr [rcx], 2Eh ; '.'
0x18000dde8  mov     byte ptr [rbp+arg_0], r12b
0x18000ddec  jnz     short loc_18000DE43
0x18000ddee  movzx   eax, word ptr [r8]
0x18000ddf2  sub     ax, r10w
0x18000ddf6  cmp     ax, r11w
0x18000ddfa  ja      short loc_18000DE25
0x18000ddfc  mov     edx, 2
0x18000de01  add     rcx, 4
0x18000de05  movzx   eax, word ptr [rcx]
0x18000de08  mov     r9d, edx
0x18000de0b  sub     ax, r10w
0x18000de0f  cmp     ax, r11w
0x18000de13  ja      short loc_18000DE1E
0x18000de15  lea     edx, [rdx+1]
0x18000de18  add     rcx, 2
0x18000de1c  jmp     short loc_18000DE05
0x18000de1e  mov     esi, 2Bh ; '+'
0x18000de23  jmp     short loc_18000DE38
0x18000de25  cmp     word ptr [r8], 2Eh ; '.'
0x18000de2a  mov     edx, r12d
0x18000de2d  mov     esi, 0Bh
0x18000de32  setz    dl
0x18000de35  add     edx, r13d
0x18000de38  mov     al, r13b
0x18000de3b  mov     edi, r12d
0x18000de3e  jmp     loc_18000DEEE
0x18000de43  lea     r9, [rbp+arg_0]; bool *
0x18000de47  mov     rcx, rbx; this
0x18000de4a  lea     r8, [rbp+arg_10]; unsigned int *
0x18000de4e  lea     rdx, [rbp+arg_8]; enum SymbolType *
0x18000de52  call    ?TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName@LexicalAnalyzer@@QEAAJPEAW4SymbolType@@PEAKPEA_N@Z; LexicalAnalyzer::TryTokenizeAsNCNameOrOperatorNameOrNodeTypeOrFunctionName(SymbolType *,ulong *,bool *)
0x18000de57  mov     edi, eax
0x18000de59  test    eax, eax
0x18000de5b  js      loc_18000DEE5
0x18000de61  cmp     byte ptr [rbp+arg_0], r12b
0x18000de65  jnz     short loc_18000DEDD
0x18000de67  mov     rdx, [rbx+20h]
0x18000de6b  lea     rcx, [rbx+18h]; struct String *
0x18000de6f  cmp     [rcx], r12
0x18000de72  lea     r8, qword_180016F98
0x18000de79  mov     r9d, 70h ; 'p'; unsigned int
0x18000de7f  cmovnz  r8, [rcx]
0x18000de83  sub     rdx, r8
0x18000de86  mov     r8d, r13d; unsigned int
0x18000de89  sar     rdx, 1; unsigned int
0x18000de8c  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x18000de91  test    eax, eax
0x18000de93  mov     ecx, 80070057h
0x18000de98  cmovs   ecx, eax
0x18000de9b  mov     eax, ecx
0x18000de9d  jmp     loc_18000DF8C
0x18000dea2  mov     cl, r12b
0x18000dea5  mov     edx, r13d
0x18000dea8  mov     r9d, r13d
0x18000deab  movzx   eax, word ptr [r8]
0x18000deaf  cmp     ax, 2Eh ; '.'
0x18000deb3  jnz     short loc_18000DEC2
0x18000deb5  test    cl, cl
0x18000deb7  jnz     loc_18000DE1E
0x18000debd  mov     cl, r13b
0x18000dec0  jmp     short loc_18000DED0
0x18000dec2  sub     ax, r10w
0x18000dec6  cmp     ax, r11w
0x18000deca  ja      loc_18000DE1E
0x18000ded0  lea     edx, [r9+1]
0x18000ded4  add     r8, 2
0x18000ded8  mov     r9d, edx
0x18000dedb  jmp     short loc_18000DEAB
0x18000dedd  mov     esi, [rbp+arg_8]
0x18000dee0  mov     edx, [rbp+arg_10]
0x18000dee3  jmp     short loc_18000DEF6
0x18000dee5  mov     esi, [rbp+arg_8]
0x18000dee8  mov     edx, [rbp+arg_10]
0x18000deeb  mov     al, byte ptr [rbp+arg_0]
0x18000deee  test    al, al
0x18000def0  jz      loc_18000DF8A
0x18000def6  mov     r15d, edx
0x18000def9  lea     rcx, [rbp+arg_0]; this
0x18000defd  mov     r8d, edx; unsigned __int64
0x18000df00  mov     rdx, [rbx+20h]; Src
0x18000df04  mov     [rbp+arg_0], r12
0x18000df08  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000df0d  mov     edi, eax
0x18000df0f  test    eax, eax
0x18000df11  js      short loc_18000DF81
0x18000df13  mov     ecx, 38h ; '8'; Size
0x18000df18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000df1d  test    rax, rax
0x18000df20  jz      short loc_18000DF50
0x18000df22  cmp     [rbx+18h], r12
0x18000df26  lea     r8, qword_180016F98
0x18000df2d  mov     r9, [rbx+20h]
0x18000df31  lea     rdx, [rbp+arg_0]
0x18000df35  cmovnz  r8, [rbx+18h]
0x18000df3a  mov     rcx, rax
0x18000df3d  sub     r9, r8
0x18000df40  mov     r8d, esi
0x18000df43  sar     r9, 1
0x18000df46  call    ??0Token@@QEAA@AEAVString@@W4SymbolType@@K@Z; Token::Token(String &,SymbolType,ulong)
0x18000df4b  mov     rsi, rax
0x18000df4e  jmp     short loc_18000DF53
0x18000df50  mov     rsi, r12
0x18000df53  lea     rcx, [rbx+10h]
0x18000df57  call    ?Reset@?$InvasivePtr@VNode@@@@QEAAXXZ; InvasivePtr<Node>::Reset(void)
0x18000df5c  mov     [rbx+10h], rsi
0x18000df60  test    rsi, rsi
0x18000df63  jz      loc_18000DCCD
0x18000df69  lea     rax, [r15+r15]
0x18000df6d  add     [rbx+20h], rax
0x18000df71  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18000df75  call    ?FindNextNonWhitespaceCharacter@LexicalAnalyzer@@SAPEBGPEBG@Z; LexicalAnalyzer::FindNextNonWhitespaceCharacter(ushort const *)
0x18000df7a  mov     [rbx+20h], rax
0x18000df7e  mov     [rbx], r13d
0x18000df81  lea     rcx, [rbp+arg_0]; this
0x18000df85  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000df8a  mov     eax, edi
0x18000df8c  mov     rbx, [rsp+20h+arg_18]
0x18000df91  add     rsp, 20h
0x18000df95  pop     r15
0x18000df97  pop     r14
0x18000df99  pop     r13
0x18000df9b  pop     r12
0x18000df9d  pop     rdi
0x18000df9e  pop     rsi
0x18000df9f  pop     rbp
0x18000dfa0  retn
```
