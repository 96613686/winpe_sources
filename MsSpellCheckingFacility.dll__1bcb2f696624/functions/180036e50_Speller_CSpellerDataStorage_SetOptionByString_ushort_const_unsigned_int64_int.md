# Speller::CSpellerDataStorage::SetOptionByString(ushort const *,unsigned __int64,int)

- ea: `0x180036e50`
- end: `0x180037320`
- name: `?SetOptionByString@CSpellerDataStorage@Speller@@QEAAXPEBG_KH@Z`
- size: `1232`
- prototype: `void __fastcall(Speller::CSpellerDataStorage *__hidden this, const unsigned __int16 *, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800481f4`

## callees

- `0x180014150`
- `0x180036908`
- `0x180036e50`
- `0x180062344`

## string_xrefs

- `0x180036ec0`: `MaxCompoundLength`
- `0x180036f10`: `MinCompoundLength`
- `0x180037133`: `LexicalizedCompoundCheck`
- `0x180037066`: `AutoReplace`
- `0x18003715a`: `MaxCompoundCheckPenalty`
- `0x1800371c8`: `DoubleCheckDynamicCompounds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Speller::CSpellerDataStorage::SetOptionByString(
        Speller::CSpellerDataStorage *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4)
{
  __int64 v4; // rsi
  __int64 v7; // r12
  const wchar_t *v8; // r13
  const unsigned __int16 *i; // r15
  unsigned __int16 v10; // bx
  __int16 v11; // di
  __int64 v12; // r12
  const wchar_t *v13; // r13
  const unsigned __int16 *j; // r15
  wchar_t v15; // di
  __int16 v16; // bx
  __int64 v17; // r12
  const wchar_t *v18; // r13
  const unsigned __int16 *k; // r15
  wchar_t v20; // di
  __int16 v21; // bx
  __int64 v22; // r12
  const wchar_t *v23; // r13
  const unsigned __int16 *m; // r15
  unsigned __int16 v25; // bx
  __int16 v26; // di
  void **pExceptionObject; // [rsp+20h] [rbp-98h] BYREF
  int v28; // [rsp+28h] [rbp-90h]
  __int128 v29; // [rsp+30h] [rbp-88h]
  int v30; // [rsp+40h] [rbp-78h]
  int v31; // [rsp+50h] [rbp-68h]
  __int128 v32; // [rsp+58h] [rbp-60h]
  __int64 v33; // [rsp+68h] [rbp-50h]

  v4 = a4;
  v7 = 256;
  v8 = L"Segmentation";
  for ( i = a2; ; ++i )
  {
    if ( !v7 )
    {
LABEL_69:
      *((_BYTE *)this + 613) = (_DWORD)v4 != 0;
      return;
    }
    v10 = *i;
    v11 = CMN_CharLowerW(*v8);
    if ( (unsigned __int16)CMN_CharLowerW(v10) != v11 )
      break;
    if ( !*i )
      goto LABEL_69;
    --v7;
    ++v8;
  }
  v12 = 256;
  v13 = L"MaxCompoundLength";
  for ( j = a2; ; ++j )
  {
    if ( !v12 )
    {
LABEL_68:
      *((_QWORD *)this + 177) = v4;
      return;
    }
    v15 = *v13;
    v16 = CMN_CharLowerW(*j);
    if ( v16 != (unsigned __int16)CMN_CharLowerW(v15) )
      break;
    if ( !*j )
      goto LABEL_68;
    --v12;
    ++v13;
  }
  v17 = 256;
  v18 = L"MinCompoundLength";
  for ( k = a2; ; ++k )
  {
    if ( !v17 )
    {
LABEL_67:
      *((_QWORD *)this + 178) = v4;
      return;
    }
    v20 = *v18;
    v21 = CMN_CharLowerW(*k);
    if ( v21 != (unsigned __int16)CMN_CharLowerW(v20) )
      break;
    if ( !*k )
      goto LABEL_67;
    --v17;
    ++v18;
  }
  v22 = 256;
  v23 = L"MaxSegmentCount";
  for ( m = a2; ; ++m )
  {
    if ( !v22 )
    {
LABEL_66:
      *((_QWORD *)this + 180) = v4;
      return;
    }
    v25 = *m;
    v26 = CMN_CharLowerW(*v23);
    if ( (unsigned __int16)CMN_CharLowerW(v25) != v26 )
      break;
    if ( !*m )
      goto LABEL_66;
    --v22;
    ++v23;
  }
  if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"MinSegmentLength", 256) )
  {
    *((_QWORD *)this + 179) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"LookupNormalization", 256) )
  {
    *((_BYTE *)this + 547) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"RequireFullDialectBitMatch", 256) )
  {
    *((_BYTE *)this + 571) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"UsingDialects", 256) )
  {
    *((_BYTE *)this + 3) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"MaxConsecutivePunct", 256) )
  {
    *((_DWORD *)this + 145) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"AutoReplace", 256) )
  {
    *((_BYTE *)this + 8) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"AllowedRepeatWordBit", 256) )
  {
    *((_DWORD *)this + 146) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"InvariableCaseBit", 256) )
  {
    *((_DWORD *)this + 147) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"ExactMatchSubstitute", 256) )
  {
    *((_BYTE *)this + 601) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"BeforeHyphenOnlyBit", 256) )
  {
    *((_DWORD *)this + 148) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"AfterHyphenOnlyBit", 256) )
  {
    *((_DWORD *)this + 149) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"LexicalizedCompoundCheck", 256) )
  {
    if ( (unsigned int)v4 > 4 )
      LODWORD(v4) = 0;
    *((_DWORD *)this + 351) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"MaxCompoundCheckPenalty", 256) )
  {
    *((_BYTE *)this + 1408) = v4;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"AllowInitCapHyphenForLexEntries", 256) )
  {
    *((_BYTE *)this + 575) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"AddInitCapHyphenSuggestions", 256) )
  {
    *((_BYTE *)this + 576) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"DoubleCheckDynamicCompounds", 256) )
  {
    *((_BYTE *)this + 609) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"BreakOnPrefixes", 256) )
  {
    *((_BYTE *)this + 610) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"CaseSensitiveSegments", 256) )
  {
    *((_BYTE *)this + 611) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"SegmentsMustBeInDialect", 256) )
  {
    *((_BYTE *)this + 612) = (_DWORD)v4 != 0;
  }
  else if ( (unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"SuggestNormalized", 256) )
  {
    *((_BYTE *)this + 546) = (_DWORD)v4 != 0;
  }
  else
  {
    if ( !(unsigned int)CMN_IsStringEqualNoCaseNumW(a2, L"OutOfDialectIsMasking", 256) )
    {
      v28 = -2147467259;
      v29 = 0;
      pExceptionObject = &CNLException::`vftable';
      v30 = -2147467259;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      throw (CNLException *)&pExceptionObject;
    }
    *((_BYTE *)this + 614) = (_DWORD)v4 != 0;
  }
}

```

## disassembly

```asm
0x180036e50  push    rbx
0x180036e52  push    rbp
0x180036e53  push    rsi
0x180036e54  push    rdi
0x180036e55  push    r12
0x180036e57  push    r13
0x180036e59  push    r14
0x180036e5b  push    r15
0x180036e5d  sub     rsp, 78h
0x180036e61  movsxd  rsi, r9d
0x180036e64  mov     r14, rdx
0x180036e67  mov     rbp, rcx
0x180036e6a  mov     r12d, 100h
0x180036e70  lea     r13, aSegmentation; "Segmentation"
0x180036e77  mov     r15, rdx
0x180036e7a  test    r12, r12
0x180036e7d  jz      loc_180037304
0x180036e83  movzx   ebx, word ptr [r15]
0x180036e87  movzx   ecx, word ptr [r13+0]
0x180036e8c  call    CMN_CharLowerW
0x180036e91  movzx   edi, ax
0x180036e94  movzx   ecx, bx
0x180036e97  call    CMN_CharLowerW
0x180036e9c  cmp     ax, di
0x180036e9f  jnz     short loc_180036EBA
0x180036ea1  xor     eax, eax
0x180036ea3  cmp     [r15], ax
0x180036ea7  jz      loc_180037304
0x180036ead  dec     r12
0x180036eb0  add     r13, 2
0x180036eb4  add     r15, 2
0x180036eb8  jmp     short loc_180036E7A
0x180036eba  mov     r12d, 100h
0x180036ec0  lea     r13, aMaxcompoundlen; "MaxCompoundLength"
0x180036ec7  mov     r15, r14
0x180036eca  test    r12, r12
0x180036ecd  jz      loc_1800372FB
0x180036ed3  movzx   edi, word ptr [r13+0]
0x180036ed8  movzx   ecx, word ptr [r15]
0x180036edc  call    CMN_CharLowerW
0x180036ee1  movzx   ebx, ax
0x180036ee4  movzx   ecx, di
0x180036ee7  call    CMN_CharLowerW
0x180036eec  cmp     bx, ax
0x180036eef  jnz     short loc_180036F0A
0x180036ef1  xor     eax, eax
0x180036ef3  cmp     [r15], ax
0x180036ef7  jz      loc_1800372FB
0x180036efd  dec     r12
0x180036f00  add     r13, 2
0x180036f04  add     r15, 2
0x180036f08  jmp     short loc_180036ECA
0x180036f0a  mov     r12d, 100h
0x180036f10  lea     r13, aMincompoundlen; "MinCompoundLength"
0x180036f17  mov     r15, r14
0x180036f1a  test    r12, r12
0x180036f1d  jz      loc_1800372F2
0x180036f23  movzx   edi, word ptr [r13+0]
0x180036f28  movzx   ecx, word ptr [r15]
0x180036f2c  call    CMN_CharLowerW
0x180036f31  movzx   ebx, ax
0x180036f34  movzx   ecx, di
0x180036f37  call    CMN_CharLowerW
0x180036f3c  cmp     bx, ax
0x180036f3f  jnz     short loc_180036F5A
0x180036f41  xor     eax, eax
0x180036f43  cmp     [r15], ax
0x180036f47  jz      loc_1800372F2
0x180036f4d  dec     r12
0x180036f50  add     r13, 2
0x180036f54  add     r15, 2
0x180036f58  jmp     short loc_180036F1A
0x180036f5a  mov     r12d, 100h
0x180036f60  lea     r13, aMaxsegmentcoun; "MaxSegmentCount"
0x180036f67  mov     r15, r14
0x180036f6a  test    r12, r12
0x180036f6d  jz      loc_1800372E9
0x180036f73  movzx   ebx, word ptr [r15]
0x180036f77  movzx   ecx, word ptr [r13+0]
0x180036f7c  call    CMN_CharLowerW
0x180036f81  movzx   edi, ax
0x180036f84  movzx   ecx, bx
0x180036f87  call    CMN_CharLowerW
0x180036f8c  cmp     ax, di
0x180036f8f  jnz     short loc_180036FAA
0x180036f91  xor     eax, eax
0x180036f93  cmp     [r15], ax
0x180036f97  jz      loc_1800372E9
0x180036f9d  dec     r12
0x180036fa0  add     r13, 2
0x180036fa4  add     r15, 2
0x180036fa8  jmp     short loc_180036F6A
0x180036faa  mov     edi, 100h
0x180036faf  mov     r8d, edi
0x180036fb2  lea     rdx, aMinsegmentleng; "MinSegmentLength"
0x180036fb9  mov     rcx, r14
0x180036fbc  call    CMN_IsStringEqualNoCaseNumW
0x180036fc1  xor     ebx, ebx
0x180036fc3  test    eax, eax
0x180036fc5  jz      short loc_180036FD3
0x180036fc7  mov     [rbp+598h], rsi
0x180036fce  jmp     loc_18003730F
0x180036fd3  mov     r8, rdi
0x180036fd6  lea     rdx, aLookupnormaliz; "LookupNormalization"
0x180036fdd  mov     rcx, r14
0x180036fe0  call    CMN_IsStringEqualNoCaseNumW
0x180036fe5  test    eax, eax
0x180036fe7  jz      short loc_180036FF9
0x180036fe9  test    esi, esi
0x180036feb  setnz   al
0x180036fee  mov     [rbp+223h], al
0x180036ff4  jmp     loc_18003730F
0x180036ff9  mov     r8, rdi
0x180036ffc  lea     rdx, aRequirefulldia; "RequireFullDialectBitMatch"
0x180037003  mov     rcx, r14
0x180037006  call    CMN_IsStringEqualNoCaseNumW
0x18003700b  test    eax, eax
0x18003700d  jz      short loc_18003701F
0x18003700f  test    esi, esi
0x180037011  setnz   al
0x180037014  mov     [rbp+23Bh], al
0x18003701a  jmp     loc_18003730F
0x18003701f  mov     r8, rdi
0x180037022  lea     rdx, aUsingdialects; "UsingDialects"
0x180037029  mov     rcx, r14
0x18003702c  call    CMN_IsStringEqualNoCaseNumW
0x180037031  test    eax, eax
0x180037033  jz      short loc_180037042
0x180037035  test    esi, esi
0x180037037  setnz   al
0x18003703a  mov     [rbp+3], al
0x18003703d  jmp     loc_18003730F
0x180037042  mov     r8, rdi
0x180037045  lea     rdx, aMaxconsecutive; "MaxConsecutivePunct"
0x18003704c  mov     rcx, r14
0x18003704f  call    CMN_IsStringEqualNoCaseNumW
0x180037054  test    eax, eax
0x180037056  jz      short loc_180037063
0x180037058  mov     [rbp+244h], esi
0x18003705e  jmp     loc_18003730F
0x180037063  mov     r8, rdi
0x180037066  lea     rdx, aAutoreplace; "AutoReplace"
0x18003706d  mov     rcx, r14
0x180037070  call    CMN_IsStringEqualNoCaseNumW
0x180037075  test    eax, eax
0x180037077  jz      short loc_180037086
0x180037079  test    esi, esi
0x18003707b  setnz   al
0x18003707e  mov     [rbp+8], al
0x180037081  jmp     loc_18003730F
0x180037086  mov     r8, rdi
0x180037089  lea     rdx, aAllowedrepeatw; "AllowedRepeatWordBit"
0x180037090  mov     rcx, r14
0x180037093  call    CMN_IsStringEqualNoCaseNumW
0x180037098  test    eax, eax
0x18003709a  jz      short loc_1800370A7
0x18003709c  mov     [rbp+248h], esi
0x1800370a2  jmp     loc_18003730F
0x1800370a7  mov     r8, rdi
0x1800370aa  lea     rdx, aInvariablecase; "InvariableCaseBit"
0x1800370b1  mov     rcx, r14
0x1800370b4  call    CMN_IsStringEqualNoCaseNumW
0x1800370b9  test    eax, eax
0x1800370bb  jz      short loc_1800370C8
0x1800370bd  mov     [rbp+24Ch], esi
0x1800370c3  jmp     loc_18003730F
0x1800370c8  mov     r8, rdi
0x1800370cb  lea     rdx, aExactmatchsubs; "ExactMatchSubstitute"
0x1800370d2  mov     rcx, r14
0x1800370d5  call    CMN_IsStringEqualNoCaseNumW
0x1800370da  test    eax, eax
0x1800370dc  jz      short loc_1800370EE
0x1800370de  test    esi, esi
0x1800370e0  setnz   al
0x1800370e3  mov     [rbp+259h], al
0x1800370e9  jmp     loc_18003730F
0x1800370ee  mov     r8, rdi
0x1800370f1  lea     rdx, aBeforehyphenon; "BeforeHyphenOnlyBit"
0x1800370f8  mov     rcx, r14
0x1800370fb  call    CMN_IsStringEqualNoCaseNumW
0x180037100  test    eax, eax
0x180037102  jz      short loc_18003710F
0x180037104  mov     [rbp+250h], esi
0x18003710a  jmp     loc_18003730F
0x18003710f  mov     r8, rdi
0x180037112  lea     rdx, aAfterhyphenonl; "AfterHyphenOnlyBit"
0x180037119  mov     rcx, r14
0x18003711c  call    CMN_IsStringEqualNoCaseNumW
0x180037121  test    eax, eax
0x180037123  jz      short loc_180037130
0x180037125  mov     [rbp+254h], esi
0x18003712b  jmp     loc_18003730F
0x180037130  mov     r8, rdi
0x180037133  lea     rdx, aLexicalizedcom; "LexicalizedCompoundCheck"
0x18003713a  mov     rcx, r14
0x18003713d  call    CMN_IsStringEqualNoCaseNumW
0x180037142  test    eax, eax
0x180037144  jz      short loc_180037157
0x180037146  cmp     esi, 4
0x180037149  cmova   esi, ebx
0x18003714c  mov     [rbp+57Ch], esi
0x180037152  jmp     loc_18003730F
0x180037157  mov     r8, rdi
0x18003715a  lea     rdx, aMaxcompoundche; "MaxCompoundCheckPenalty"
0x180037161  mov     rcx, r14
0x180037164  call    CMN_IsStringEqualNoCaseNumW
0x180037169  test    eax, eax
0x18003716b  jz      short loc_180037179
0x18003716d  mov     [rbp+580h], sil
0x180037174  jmp     loc_18003730F
0x180037179  mov     r8, rdi
0x18003717c  lea     rdx, aAllowinitcaphy; "AllowInitCapHyphenForLexEntries"
0x180037183  mov     rcx, r14
0x180037186  call    CMN_IsStringEqualNoCaseNumW
0x18003718b  test    eax, eax
0x18003718d  jz      short loc_18003719F
0x18003718f  test    esi, esi
0x180037191  setnz   al
0x180037194  mov     [rbp+23Fh], al
0x18003719a  jmp     loc_18003730F
0x18003719f  mov     r8, rdi
0x1800371a2  lea     rdx, aAddinitcaphyph; "AddInitCapHyphenSuggestions"
0x1800371a9  mov     rcx, r14
0x1800371ac  call    CMN_IsStringEqualNoCaseNumW
0x1800371b1  test    eax, eax
0x1800371b3  jz      short loc_1800371C5
0x1800371b5  test    esi, esi
0x1800371b7  setnz   al
0x1800371ba  mov     [rbp+240h], al
0x1800371c0  jmp     loc_18003730F
0x1800371c5  mov     r8, rdi
0x1800371c8  lea     rdx, aDoublecheckdyn; "DoubleCheckDynamicCompounds"
0x1800371cf  mov     rcx, r14
0x1800371d2  call    CMN_IsStringEqualNoCaseNumW
0x1800371d7  test    eax, eax
0x1800371d9  jz      short loc_1800371EB
0x1800371db  test    esi, esi
0x1800371dd  setnz   al
0x1800371e0  mov     [rbp+261h], al
0x1800371e6  jmp     loc_18003730F
0x1800371eb  mov     r8, rdi
0x1800371ee  lea     rdx, aBreakonprefixe; "BreakOnPrefixes"
0x1800371f5  mov     rcx, r14
0x1800371f8  call    CMN_IsStringEqualNoCaseNumW
0x1800371fd  test    eax, eax
0x1800371ff  jz      short loc_180037211
0x180037201  test    esi, esi
0x180037203  setnz   al
0x180037206  mov     [rbp+262h], al
0x18003720c  jmp     loc_18003730F
0x180037211  mov     r8, rdi
0x180037214  lea     rdx, aCasesensitives; "CaseSensitiveSegments"
0x18003721b  mov     rcx, r14
0x18003721e  call    CMN_IsStringEqualNoCaseNumW
0x180037223  test    eax, eax
0x180037225  jz      short loc_180037237
0x180037227  test    esi, esi
0x180037229  setnz   al
0x18003722c  mov     [rbp+263h], al
0x180037232  jmp     loc_18003730F
0x180037237  mov     r8, rdi
0x18003723a  lea     rdx, aSegmentsmustbe; "SegmentsMustBeInDialect"
0x180037241  mov     rcx, r14
0x180037244  call    CMN_IsStringEqualNoCaseNumW
0x180037249  test    eax, eax
0x18003724b  jz      short loc_18003725D
0x18003724d  test    esi, esi
0x18003724f  setnz   al
0x180037252  mov     [rbp+264h], al
0x180037258  jmp     loc_18003730F
0x18003725d  mov     r8, rdi
0x180037260  lea     rdx, aSuggestnormali; "SuggestNormalized"
0x180037267  mov     rcx, r14
0x18003726a  call    CMN_IsStringEqualNoCaseNumW
0x18003726f  test    eax, eax
0x180037271  jz      short loc_180037283
0x180037273  test    esi, esi
0x180037275  setnz   al
0x180037278  mov     [rbp+222h], al
0x18003727e  jmp     loc_18003730F
0x180037283  mov     r8, rdi
0x180037286  lea     rdx, aOutofdialectis; "OutOfDialectIsMasking"
0x18003728d  mov     rcx, r14
0x180037290  call    CMN_IsStringEqualNoCaseNumW
0x180037295  test    eax, eax
0x180037297  jz      short loc_1800372A6
0x180037299  test    esi, esi
0x18003729b  setnz   al
0x18003729e  mov     [rbp+266h], al
0x1800372a4  jmp     short loc_18003730F
0x1800372a6  mov     ecx, 80004005h
0x1800372ab  mov     [rsp+0B8h+var_90], ecx
0x1800372af  xorps   xmm0, xmm0
0x1800372b2  movdqu  [rsp+0B8h+var_88], xmm0
0x1800372b8  lea     rax, ??_7CNLException@@6B@; const CNLException::`vftable'
0x1800372bf  mov     [rsp+0B8h+pExceptionObject], rax
0x1800372c4  mov     [rsp+0B8h+var_78], ecx
0x1800372c8  mov     [rsp+0B8h+var_68], ebx
0x1800372cc  movdqu  [rsp+0B8h+var_60], xmm0
0x1800372d2  mov     [rsp+0B8h+var_50], rbx
  ... truncated ...
```
