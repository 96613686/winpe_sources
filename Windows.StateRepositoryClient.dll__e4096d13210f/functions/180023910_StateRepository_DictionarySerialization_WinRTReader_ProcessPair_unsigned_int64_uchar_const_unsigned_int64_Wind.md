# StateRepository::DictionarySerialization::WinRTReader::ProcessPair(unsigned __int64,uchar const *,unsigned __int64,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,unsigned __int64 *)

- ea: `0x180023910`
- end: `0x180023e19`
- name: `?ProcessPair@WinRTReader@DictionarySerialization@StateRepository@@AEAAJ_KPEBE_KPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEA_K@Z`
- size: `1289`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, __int64, __int64, _QWORD *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180023484`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x18000c2e4`
- `0x18000c408`
- `0x18000c58c`
- `0x1800191a4`
- `0x180021668`
- `0x180021718`
- `0x180023910`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023d46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023d46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023d5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023d5a`

## string_xrefs

- `0x180023968`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023acf`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023d85`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023de5`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180023e01`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::ProcessPair(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned __int64 *a6)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned __int64 v11; // rcx
  int v12; // r15d
  __int64 v13; // rsi
  __int64 v14; // r14
  __int64 v15; // rax
  unsigned int v16; // r13d
  __int64 v17; // rdi
  unsigned __int64 v18; // r11
  int v19; // eax
  __int64 v20; // r11
  unsigned __int64 v21; // rdi
  __int64 v22; // rcx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int PropertyValue; // eax
  __int64 v28; // rdx
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r8
  __int64 v31; // rax
  _QWORD *v32; // r15
  unsigned __int64 v33; // rcx
  __int64 v34; // rbx
  const WCHAR *v35; // r14
  __int64 v36; // rax
  __int64 (__fastcall *v37)(_QWORD *, HSTRING, __int64, char *); // rsi
  int v38; // [rsp+20h] [rbp-69h]
  int v39; // [rsp+20h] [rbp-69h]
  char v40[8]; // [rsp+30h] [rbp-59h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v42; // [rsp+40h] [rbp-49h] BYREF
  int v43; // [rsp+48h] [rbp-41h]
  __int64 v44; // [rsp+50h] [rbp-39h]
  _QWORD *v45; // [rsp+58h] [rbp-31h]
  PCWSTR sourceString; // [rsp+60h] [rbp-29h]
  unsigned __int64 *v47; // [rsp+68h] [rbp-21h]
  HSTRING string; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+4Fh]

  v44 = a1;
  v45 = a5;
  v47 = a6;
  if ( !a2 )
  {
    v8 = 99;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)v9,
      v38);
    return v9;
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    v8 = 100;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v8 = 101;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    v8 = 102;
    goto LABEL_4;
  }
  if ( !a6 )
  {
    v9 = -2147467261;
    v8 = 103;
    goto LABEL_4;
  }
  if ( a4 + 8 >= a2 )
  {
    v9 = -2140733435;
    v8 = 109;
    goto LABEL_4;
  }
  v11 = a4 + (unsigned int)*(_QWORD *)(a4 + a3);
  *(_QWORD *)length = *(_QWORD *)(a4 + a3);
  if ( v11 > a2 )
  {
    v9 = -2140733435;
    v8 = 111;
    goto LABEL_4;
  }
  v12 = length[1];
  v13 = 1LL << SLOBYTE(length[1]);
  v14 = (1LL << SLOBYTE(length[1])) & 0x7FFFF400000LL;
  if ( v14 )
  {
    v15 = a4 + 12;
    if ( a4 + 12 >= a2 )
    {
      v9 = -2140733435;
      v8 = 118;
      goto LABEL_4;
    }
    v16 = *(_DWORD *)(a4 + 8 + a3);
    if ( v16 > 0x100000 )
    {
      v9 = -2140733435;
      v8 = 120;
      goto LABEL_4;
    }
  }
  else
  {
    v16 = 0;
    v15 = a4 + 8;
  }
  v17 = v15 + 2;
  if ( v15 + 2 >= a2 )
  {
    v9 = -2140733435;
    v8 = 126;
    goto LABEL_4;
  }
  v18 = *(unsigned __int16 *)(a3 + v15);
  if ( v18 + v15 > a2 )
  {
    v9 = -2140733435;
    v8 = 128;
    goto LABEL_4;
  }
  if ( (_WORD)v18 == 0xFFFF )
  {
    v9 = -2140733435;
    v8 = 129;
    goto LABEL_4;
  }
  if ( (v18 & 1) != 0 )
  {
    v9 = -2140733435;
    v8 = 133;
    goto LABEL_4;
  }
  *(_QWORD *)length = 0;
  sourceString = (PCWSTR)(v17 + a3);
  v19 = StringCchLengthW((const unsigned __int16 *)(v17 + a3), v18 >> 1, (unsigned __int64 *)length);
  if ( v19 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)(unsigned int)v19,
      v38);
    v8 = 135;
    v9 = -2140733435;
    goto LABEL_4;
  }
  if ( 2LL * *(_QWORD *)length + 2 != v20 )
  {
    v9 = -2140733435;
    v8 = 136;
    goto LABEL_4;
  }
  v21 = v20 + v17;
  LODWORD(v22) = 0;
  if ( v12 == 35 || v12 == 42 )
  {
    if ( v21 > a2 )
    {
      v9 = -2140733435;
      v8 = 144;
      goto LABEL_4;
    }
    v26 = a3 + v21;
    v30 = 0;
    if ( v16 )
    {
      while ( v21 + 4 <= a2 )
      {
        v31 = *(unsigned int *)(a3 + v21);
        v21 += v31 + 4;
        if ( v21 > a2 )
        {
          v9 = -2140733435;
          v8 = 155;
          goto LABEL_4;
        }
        if ( (unsigned int)v31 > 0x100000 )
        {
          v9 = -2140733435;
          v8 = 156;
          goto LABEL_4;
        }
        ++v30;
        LODWORD(v22) = v31 + v22 + 4;
        if ( v30 >= v16 )
          goto LABEL_63;
      }
      v9 = -2140733435;
      v8 = 151;
      goto LABEL_4;
    }
    goto LABEL_63;
  }
  if ( (v13 & 0xFBFFB) == 0 )
  {
    if ( (v13 & 0x7FFFFF04004LL) != 0 )
    {
      v29 = v21 + 4;
      if ( v21 + 4 > a2 )
      {
        v9 = -2140733435;
        v8 = 171;
        goto LABEL_4;
      }
      v22 = *(unsigned int *)(a3 + v21);
      v21 = v22 + v29;
      if ( v22 + v29 > a2 )
      {
        v9 = -2140733435;
        v8 = 175;
        goto LABEL_4;
      }
      if ( (unsigned int)v22 > 0x100000 )
      {
        v9 = -2140733435;
        v8 = 176;
        goto LABEL_4;
      }
      v26 = v29 + a3;
    }
    else
    {
      v26 = 0;
    }
    goto LABEL_63;
  }
  if ( v14 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)0x8000FFFFLL,
      v38);
  if ( v12 > 10 )
  {
    switch ( v12 )
    {
      case 11:
        goto LABEL_47;
      case 12:
        goto LABEL_61;
      case 13:
        goto LABEL_50;
    }
    LODWORD(v22) = 2;
    if ( v12 == 15 )
      goto LABEL_50;
    v23 = v12 - 16;
    if ( v12 != 16 )
      goto LABEL_57;
LABEL_51:
    LODWORD(v22) = 1;
    goto LABEL_48;
  }
  if ( v12 == 10 )
    goto LABEL_50;
  if ( v12 == 1 )
    goto LABEL_51;
  LODWORD(v22) = 2;
  if ( v12 != 3 )
  {
    if ( v12 != 4 && v12 != 5 )
    {
      v23 = v12 - 6;
      if ( v12 == 6 )
      {
LABEL_47:
        LODWORD(v22) = 16;
        goto LABEL_48;
      }
LABEL_57:
      v24 = v23 - 1;
      if ( !v24 )
        goto LABEL_48;
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 != 1 )
        {
          LODWORD(v22) = 0;
          goto LABEL_48;
        }
        goto LABEL_50;
      }
LABEL_61:
      LODWORD(v22) = 4;
      goto LABEL_48;
    }
LABEL_50:
    LODWORD(v22) = 8;
  }
LABEL_48:
  if ( v21 + (unsigned int)v22 > a2 )
  {
    v9 = -2140733435;
    v8 = 165;
    goto LABEL_4;
  }
  v26 = a3 + v21;
  v21 += (unsigned int)v22;
LABEL_63:
  v39 = v26;
  v42 = 0;
  v43 = 0;
  PropertyValue = StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(
                    v44,
                    (unsigned int)v12,
                    v16,
                    (unsigned int)v22);
  v9 = PropertyValue;
  if ( PropertyValue < 0 )
  {
    v28 = 181;
LABEL_91:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)(unsigned int)PropertyValue,
      v39);
    RoVariant::~RoVariant((RoVariant *)&v42);
    return v9;
  }
  v32 = v45;
  v33 = -1;
  v34 = v42;
  v35 = sourceString;
  v40[0] = 0;
  v36 = *v45;
  length[0] = 0;
  v37 = *(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64, char *))(v36 + 80);
  do
    ++v33;
  while ( sourceString[v33] );
  if ( (int)ULongLongToUInt(v33, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(v35, length[0], &hstringHeader, &string);
  PropertyValue = v37(v32, string, v34, v40);
  v9 = PropertyValue;
  if ( PropertyValue < 0 )
  {
    v28 = 185;
    goto LABEL_91;
  }
  if ( v40[0] )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)0x8000FFFFLL,
      v39);
  *v47 = v21;
  RoVariant::~RoVariant((RoVariant *)&v42);
  return 0;
}

```

## disassembly

```asm
0x180023910  mov     [rsp-8+arg_8], rbx
0x180023915  push    rbp
0x180023916  push    rsi
0x180023917  push    rdi
0x180023918  push    r12
0x18002391a  push    r13
0x18002391c  push    r14
0x18002391e  push    r15
0x180023920  lea     rbp, [rsp-17h]
0x180023925  sub     rsp, 0A0h
0x18002392c  mov     rax, cs:__security_cookie
0x180023933  xor     rax, rsp
0x180023936  mov     [rbp+47h+var_40], rax
0x18002393a  mov     rax, [rbp+47h+arg_28]
0x18002393e  mov     r12, r8
0x180023941  xor     r8d, r8d
0x180023944  mov     [rbp+47h+var_80], rcx
0x180023948  mov     rcx, [rbp+47h+arg_20]
0x18002394c  mov     rbx, rdx
0x18002394f  mov     [rbp+47h+var_78], rcx
0x180023953  mov     [rbp+47h+var_68], rax
0x180023957  test    rdx, rdx
0x18002395a  jnz     short loc_18002397E
0x18002395c  lea     edx, [rbx+63h]; void *
0x18002395f  mov     ebx, 80070057h
0x180023964  mov     rcx, [rbp+4Fh]; this
0x180023968  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x18002396f  mov     r9d, ebx; char *
0x180023972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023977  mov     eax, ebx
0x180023979  jmp     loc_180023DBA
0x18002397e  test    r12, r12
0x180023981  jnz     short loc_18002398F
0x180023983  mov     ebx, 80004003h
0x180023988  lea     edx, [r12+64h]
0x18002398d  jmp     short loc_180023964
0x18002398f  test    r9, r9
0x180023992  jnz     short loc_18002399A
0x180023994  lea     edx, [r9+65h]
0x180023998  jmp     short loc_18002395F
0x18002399a  test    rcx, rcx
0x18002399d  jnz     short loc_1800239A9
0x18002399f  mov     ebx, 80004003h
0x1800239a4  lea     edx, [rcx+66h]
0x1800239a7  jmp     short loc_180023964
0x1800239a9  test    rax, rax
0x1800239ac  jnz     short loc_1800239B8
0x1800239ae  mov     ebx, 80004003h
0x1800239b3  lea     edx, [rax+67h]
0x1800239b6  jmp     short loc_180023964
0x1800239b8  lea     rdx, [r9+8]
0x1800239bc  cmp     rdx, rbx
0x1800239bf  jb      short loc_1800239CD
0x1800239c1  mov     ebx, 80670005h
0x1800239c6  mov     edx, 6Dh ; 'm'
0x1800239cb  jmp     short loc_180023964
0x1800239cd  mov     rax, [r9+r12]
0x1800239d1  mov     ecx, eax
0x1800239d3  add     rcx, r9
0x1800239d6  mov     qword ptr [rbp+47h+length], rax
0x1800239da  cmp     rcx, rbx
0x1800239dd  jbe     short loc_1800239EE
0x1800239df  mov     ebx, 80670005h
0x1800239e4  mov     edx, 6Fh ; 'o'
0x1800239e9  jmp     loc_180023964
0x1800239ee  mov     r15d, [rbp+47h+length+4]
0x1800239f2  mov     esi, 1
0x1800239f7  mov     ecx, r15d
0x1800239fa  shl     rsi, cl
0x1800239fd  mov     r14, rsi
0x180023a00  and     r14, cs:qword_18002F560
0x180023a07  jz      short loc_180023A3D
0x180023a09  lea     rax, [rdx+4]
0x180023a0d  cmp     rax, rbx
0x180023a10  jb      short loc_180023A21
0x180023a12  mov     ebx, 80670005h
0x180023a17  mov     edx, 76h ; 'v'
0x180023a1c  jmp     loc_180023964
0x180023a21  mov     r13d, [rdx+r12]
0x180023a25  cmp     r13d, 100000h
0x180023a2c  jbe     short loc_180023A43
0x180023a2e  mov     ebx, 80670005h
0x180023a33  mov     edx, 78h ; 'x'
0x180023a38  jmp     loc_180023964
0x180023a3d  mov     r13d, r8d
0x180023a40  mov     rax, rdx
0x180023a43  lea     rdi, [rax+2]
0x180023a47  cmp     rdi, rbx
0x180023a4a  jb      short loc_180023A5B
0x180023a4c  mov     ebx, 80670005h
0x180023a51  mov     edx, 7Eh ; '~'
0x180023a56  jmp     loc_180023964
0x180023a5b  movzx   r11d, word ptr [r12+rax]
0x180023a60  add     rax, r11
0x180023a63  cmp     rax, rbx
0x180023a66  jbe     short loc_180023A77
0x180023a68  mov     ebx, 80670005h
0x180023a6d  mov     edx, 80h
0x180023a72  jmp     loc_180023964
0x180023a77  mov     eax, 0FFFEh
0x180023a7c  cmp     r11w, ax
0x180023a80  jbe     short loc_180023A91
0x180023a82  mov     ebx, 80670005h
0x180023a87  mov     edx, 81h
0x180023a8c  jmp     loc_180023964
0x180023a91  test    r11b, 1
0x180023a95  jz      short loc_180023AA6
0x180023a97  mov     ebx, 80670005h
0x180023a9c  mov     edx, 85h
0x180023aa1  jmp     loc_180023964
0x180023aa6  lea     rax, [rdi+r12]
0x180023aaa  mov     qword ptr [rbp+47h+length], r8
0x180023aae  mov     rdx, r11
0x180023ab1  mov     [rbp+47h+sourceString], rax
0x180023ab5  shr     rdx, 1; unsigned __int64
0x180023ab8  lea     r8, [rbp+47h+length]; unsigned __int64 *
0x180023abc  mov     rcx, rax; unsigned __int16 *
0x180023abf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180023ac4  xor     r10d, r10d
0x180023ac7  test    eax, eax
0x180023ac9  jns     short loc_180023AF1
0x180023acb  mov     rcx, [rbp+4Fh]; this
0x180023acf  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180023ad6  mov     edi, 87h
0x180023adb  mov     r9d, eax; char *
0x180023ade  mov     edx, edi; void *
0x180023ae0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023ae5  mov     edx, edi
0x180023ae7  mov     ebx, 80670005h
0x180023aec  jmp     loc_180023964
0x180023af1  mov     rax, qword ptr [rbp+47h+length]
0x180023af5  lea     rax, ds:2[rax*2]
0x180023afd  cmp     rax, r11
0x180023b00  jz      short loc_180023B11
0x180023b02  mov     ebx, 80670005h
0x180023b07  mov     edx, 88h
0x180023b0c  jmp     loc_180023964
0x180023b11  add     rdi, r11
0x180023b14  mov     ecx, r10d
0x180023b17  cmp     r15d, 23h ; '#'
0x180023b1b  jz      loc_180023C7B
0x180023b21  cmp     r15d, 2Ah ; '*'
0x180023b25  jz      loc_180023C7B
0x180023b2b  test    cs:qword_18002F568, rsi
0x180023b32  jz      loc_180023C16
0x180023b38  test    r14, r14
0x180023b3b  jnz     loc_180023DFD
0x180023b41  cmp     r15d, 0Ah
0x180023b45  jg      short loc_180023B95
0x180023b47  jz      short loc_180023B87
0x180023b49  mov     edx, r15d
0x180023b4c  sub     edx, 1
0x180023b4f  jz      short loc_180023B8E
0x180023b51  lea     ecx, [r14+2]
0x180023b55  sub     edx, ecx
0x180023b57  jz      short loc_180023B6D
0x180023b59  sub     edx, 1
0x180023b5c  jz      short loc_180023B87
0x180023b5e  sub     edx, 1
0x180023b61  jz      short loc_180023B87
0x180023b63  sub     edx, 1
0x180023b66  jnz     short loc_180023BB5
0x180023b68  mov     ecx, 10h
0x180023b6d  mov     r8d, ecx
0x180023b70  add     r8, rdi
0x180023b73  cmp     r8, rbx
0x180023b76  jbe     short loc_180023BD0
0x180023b78  mov     ebx, 80670005h
0x180023b7d  mov     edx, 0A5h
0x180023b82  jmp     loc_180023964
0x180023b87  mov     ecx, 8
0x180023b8c  jmp     short loc_180023B6D
0x180023b8e  mov     ecx, 1
0x180023b93  jmp     short loc_180023B6D
0x180023b95  mov     edx, r15d
0x180023b98  sub     edx, 0Bh
0x180023b9b  jz      short loc_180023B68
0x180023b9d  sub     edx, 1
0x180023ba0  jz      short loc_180023BC9
0x180023ba2  sub     edx, 1
0x180023ba5  jz      short loc_180023B87
0x180023ba7  mov     ecx, 2
0x180023bac  sub     edx, ecx
0x180023bae  jz      short loc_180023B87
0x180023bb0  sub     edx, 1
0x180023bb3  jz      short loc_180023B8E
0x180023bb5  sub     edx, 1
0x180023bb8  jz      short loc_180023B6D
0x180023bba  sub     edx, 1
0x180023bbd  jz      short loc_180023BC9
0x180023bbf  cmp     edx, 1
0x180023bc2  jz      short loc_180023B87
0x180023bc4  mov     ecx, r10d
0x180023bc7  jmp     short loc_180023B6D
0x180023bc9  mov     ecx, 4
0x180023bce  jmp     short loc_180023B6D
0x180023bd0  lea     rdx, [r12+rdi]
0x180023bd4  mov     rdi, r8
0x180023bd7  lea     rax, [rbp+47h+var_90]
0x180023bdb  mov     r9d, ecx
0x180023bde  mov     rcx, [rbp+47h+var_80]
0x180023be2  mov     r8d, r13d
0x180023be5  mov     [rsp+0D0h+var_A8], rax
0x180023bea  mov     qword ptr [rsp+0D0h+var_B0], rdx; int
0x180023bef  mov     edx, r15d
0x180023bf2  mov     [rbp+47h+var_90], r10
0x180023bf6  mov     [rbp+47h+var_88], r10d
0x180023bfa  call    ?CreatePropertyValue@WinRTReader@DictionarySerialization@StateRepository@@AEAAJW4DataType@23@I_KPEBXAEAVRoVariant@@@Z; StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(StateRepository::DictionarySerialization::DataType,uint,unsigned __int64,void const *,RoVariant &)
0x180023bff  xor     r12d, r12d
0x180023c02  mov     ebx, eax
0x180023c04  test    eax, eax
0x180023c06  jns     loc_180023D01
0x180023c0c  mov     edx, 0B5h
0x180023c11  jmp     loc_180023D81
0x180023c16  test    cs:qword_18002F570, rsi
0x180023c1d  jz      short loc_180023C73
0x180023c1f  lea     rax, [rdi+4]
0x180023c23  cmp     rax, rbx
0x180023c26  jbe     short loc_180023C37
0x180023c28  mov     ebx, 80670005h
0x180023c2d  mov     edx, 0ABh
0x180023c32  jmp     loc_180023964
0x180023c37  mov     ecx, [r12+rdi]
0x180023c3b  lea     rdi, [rcx+rax]
0x180023c3f  cmp     rdi, rbx
0x180023c42  jbe     short loc_180023C53
0x180023c44  mov     ebx, 80670005h
0x180023c49  mov     edx, 0AFh
0x180023c4e  jmp     loc_180023964
0x180023c53  cmp     ecx, 100000h
0x180023c59  jbe     short loc_180023C6A
0x180023c5b  mov     ebx, 80670005h
0x180023c60  mov     edx, 0B0h
0x180023c65  jmp     loc_180023964
0x180023c6a  lea     rdx, [rax+r12]
0x180023c6e  jmp     loc_180023BD7
0x180023c73  mov     rdx, r10
0x180023c76  jmp     loc_180023BD7
0x180023c7b  cmp     rdi, rbx
0x180023c7e  jbe     short loc_180023C8F
0x180023c80  mov     ebx, 80670005h
0x180023c85  mov     edx, 90h
0x180023c8a  jmp     loc_180023964
0x180023c8f  mov     r9d, r13d
0x180023c92  lea     rdx, [r12+rdi]
0x180023c96  mov     r8, r10
0x180023c99  test    r13d, r13d
0x180023c9c  jz      loc_180023BD7
0x180023ca2  lea     rax, [rdi+4]
0x180023ca6  cmp     rax, rbx
0x180023ca9  ja      short loc_180023CF2
0x180023cab  mov     eax, [r12+rdi]
0x180023caf  add     rdi, 4
0x180023cb3  add     rdi, rax
0x180023cb6  cmp     rdi, rbx
0x180023cb9  ja      short loc_180023CE3
0x180023cbb  cmp     eax, 100000h
0x180023cc0  ja      short loc_180023CD4
0x180023cc2  add     ecx, 4
0x180023cc5  inc     r8
0x180023cc8  add     ecx, eax
0x180023cca  cmp     r8, r9
0x180023ccd  jb      short loc_180023CA2
0x180023ccf  jmp     loc_180023BD7
0x180023cd4  mov     ebx, 80670005h
0x180023cd9  mov     edx, 9Ch
0x180023cde  jmp     loc_180023964
0x180023ce3  mov     ebx, 80670005h
0x180023ce8  mov     edx, 9Bh
0x180023ced  jmp     loc_180023964
0x180023cf2  mov     ebx, 80670005h
0x180023cf7  mov     edx, 97h
0x180023cfc  jmp     loc_180023964
0x180023d01  mov     r15, [rbp+47h+var_78]
0x180023d05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023d09  mov     rbx, [rbp+47h+var_90]
0x180023d0d  mov     r14, [rbp+47h+sourceString]
0x180023d11  mov     [rbp+47h+var_A0], r12b
0x180023d15  mov     rax, [r15]
0x180023d18  mov     [rbp+47h+length], r12d
0x180023d1c  mov     rsi, [rax+50h]
0x180023d20  inc     rcx; unsigned __int64
0x180023d23  cmp     [r14+rcx*2], r12w
0x180023d28  jnz     short loc_180023D20
0x180023d2a  lea     rdx, [rbp+47h+length]; unsigned int *
0x180023d2e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180023d33  test    eax, eax
0x180023d35  jns     short loc_180023D4C
0x180023d37  xor     r9d, r9d; lpArguments
0x180023d3a  xor     r8d, r8d; nNumberOfArguments
0x180023d3d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023d42  lea     edx, [r9+1]; dwExceptionFlags
0x180023d46  call    cs:__imp_RaiseException
0x180023d4c  mov     edx, [rbp+47h+length]; length
0x180023d4f  lea     r9, [rbp+47h+string]; string
0x180023d53  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x180023d57  mov     rcx, r14; sourceString
0x180023d5a  call    cs:__imp_WindowsCreateStringReference
0x180023d60  mov     rdx, [rbp+47h+string]
0x180023d64  lea     r9, [rbp+47h+var_A0]
  ... truncated ...
```
