# StateRepository::DictionarySerialization::Writer::AddArrayOfString(ushort const *,StateRepository::DictionarySerialization::DataType,unsigned __int64,ushort * const *)

- ea: `0x1800258d8`
- end: `0x180025af7`
- name: `?AddArrayOfString@Writer@DictionarySerialization@StateRepository@@QEAAJPEBGW4DataType@23@_KPEBQEAG@Z`
- size: `543`
- prototype: `__int64 __fastcall(StateRepository::Blob *, const unsigned __int16 *, int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180024170`

## callees

- `0x1800075e4`
- `0x1800191a4`
- `0x180023e20`
- `0x1800258d8`
- `0x180025cb0`
- `0x180025db4`
- `0x180025e1c`
- `0x180025e44`

## string_xrefs

- `0x180025910`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x1800259be`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x180025ab4`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::Writer::AddArrayOfString(
        StateRepository::Blob *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int64 a4,
        __int64 a5)
{
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v11; // r12
  unsigned __int64 v12; // rbx
  unsigned __int64 i; // r8
  unsigned int v14; // eax
  __int64 v15; // r8
  unsigned __int16 v16; // ax
  unsigned __int64 v17; // r14
  unsigned __int64 j; // rbx
  const unsigned __int16 *v19; // r15
  int v20; // r14d
  __int64 v21; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  unsigned int Src; // [rsp+68h] [rbp+48h] BYREF
  int v25; // [rsp+6Ch] [rbp+4Ch]
  unsigned __int64 v26; // [rsp+70h] [rbp+50h] BYREF

  LODWORD(v26) = a3;
  if ( !a2 )
  {
    v8 = -2147467261;
    v9 = 505;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
    return (unsigned int)v8;
  }
  v11 = a5;
  if ( a4 && !a5 )
  {
    v8 = -2147024809;
    v9 = 506;
    goto LABEL_3;
  }
  v12 = 0;
  LODWORD(v26) = a4;
  for ( i = 0; i < (unsigned int)a4; i = v15 + 1 )
  {
    v14 = StateRepository::DictionarySerialization::Writer::StringSize(*(const unsigned __int16 **)(v11 + 8 * i));
    if ( v14 > 0x100000 )
    {
      v8 = -2147024809;
      v9 = 516;
      goto LABEL_3;
    }
    v12 += v14;
  }
  v16 = StateRepository::DictionarySerialization::Writer::KeySize(a2);
  v17 = v16;
  if ( v16 == 0xFFFF )
  {
    v8 = -2147024809;
    v9 = 522;
    goto LABEL_3;
  }
  Src = StateRepository::DictionarySerialization::Writer::SizeOfPairVariableLengthDataArray(v16, v12, a4);
  v25 = 35;
  if ( Src > 0x11000C )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x20E,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
      (const char *)0x80070057LL,
      savedregs);
  v8 = StateRepository::Blob::Append(a1, 8u, &Src);
  if ( v8 < 0 )
  {
    v9 = 527;
    goto LABEL_3;
  }
  v8 = StateRepository::Blob::Append(a1, 4u, &v26);
  if ( v8 < 0 )
  {
    v9 = 530;
    goto LABEL_3;
  }
  LOWORD(v26) = v17;
  v8 = StateRepository::Blob::Append(a1, 2u, &v26);
  if ( v8 < 0 )
  {
    v9 = 534;
    goto LABEL_3;
  }
  v8 = StateRepository::Blob::Append(a1, v17, a2);
  if ( v8 < 0 )
  {
    v9 = 535;
    goto LABEL_3;
  }
  for ( j = 0; j < a4; ++j )
  {
    v19 = *(const unsigned __int16 **)(v11 + 8 * j);
    LODWORD(v26) = StateRepository::DictionarySerialization::Writer::StringSize(v19);
    v20 = StateRepository::Blob::Append(a1, 4u, &v26);
    if ( v20 < 0 )
    {
      v21 = 542;
      goto LABEL_31;
    }
    v20 = StateRepository::Blob::Append(a1, (unsigned int)v26, v19);
    if ( v20 < 0 )
    {
      v21 = 543;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
        (const char *)(unsigned int)v20,
        savedregs);
      return (unsigned int)v20;
    }
  }
  v8 = StateRepository::DictionarySerialization::Writer::UpdateForAddedPair(a1);
  if ( v8 < 0 )
  {
    v9 = 547;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800258d8  mov     [rsp-38h+arg_0], rbx
0x1800258dd  mov     dword ptr [rsp-38h+arg_10], r8d
0x1800258e2  push    rbp
0x1800258e3  push    rsi
0x1800258e4  push    rdi
0x1800258e5  push    r12
0x1800258e7  push    r13
0x1800258e9  push    r14
0x1800258eb  push    r15; int
0x1800258ed  mov     rbp, rsp
0x1800258f0  sub     rsp, 20h
0x1800258f4  mov     rsi, r9
0x1800258f7  mov     r15, rdx
0x1800258fa  mov     rdi, rcx
0x1800258fd  test    rdx, rdx
0x180025900  jnz     short loc_180025926
0x180025902  mov     ebx, 80004003h
0x180025907  mov     edx, 1F9h; void *
0x18002590c  mov     rcx, [rbp+38h]; this
0x180025910  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180025917  mov     r9d, ebx; char *
0x18002591a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002591f  mov     eax, ebx
0x180025921  jmp     loc_180025AE2
0x180025926  mov     r12, [rbp+arg_20]
0x18002592a  test    rsi, rsi
0x18002592d  jz      short loc_180025940
0x18002592f  test    r12, r12
0x180025932  jnz     short loc_180025940
0x180025934  mov     ebx, 80070057h
0x180025939  mov     edx, 1FAh
0x18002593e  jmp     short loc_18002590C
0x180025940  xor     ebx, ebx
0x180025942  mov     dword ptr [rbp+arg_10], esi
0x180025945  xor     r8d, r8d
0x180025948  mov     eax, esi
0x18002594a  cmp     r8, rax
0x18002594d  jnb     short loc_180025975
0x18002594f  mov     rcx, [r12+r8*8]; unsigned __int16 *
0x180025953  call    ?StringSize@Writer@DictionarySerialization@StateRepository@@SA_KPEBG@Z; StateRepository::DictionarySerialization::Writer::StringSize(ushort const *)
0x180025958  cmp     eax, 100000h
0x18002595d  ja      short loc_180025969
0x18002595f  mov     eax, eax
0x180025961  add     rbx, rax
0x180025964  inc     r8
0x180025967  jmp     short loc_180025948
0x180025969  mov     ebx, 80070057h
0x18002596e  mov     edx, 204h
0x180025973  jmp     short loc_18002590C
0x180025975  mov     rcx, r15; unsigned __int16 *
0x180025978  call    ?KeySize@Writer@DictionarySerialization@StateRepository@@SAGPEBG@Z; StateRepository::DictionarySerialization::Writer::KeySize(ushort const *)
0x18002597d  movzx   r14d, ax
0x180025981  mov     eax, 0FFFEh
0x180025986  cmp     r14w, ax
0x18002598a  jbe     short loc_18002599B
0x18002598c  mov     ebx, 80070057h
0x180025991  mov     edx, 20Ah
0x180025996  jmp     loc_18002590C
0x18002599b  mov     r8, rsi; unsigned __int64
0x18002599e  mov     rdx, rbx; unsigned __int64
0x1800259a1  mov     rcx, r14; unsigned __int64
0x1800259a4  call    ?SizeOfPairVariableLengthDataArray@Writer@DictionarySerialization@StateRepository@@SAI_K00@Z; StateRepository::DictionarySerialization::Writer::SizeOfPairVariableLengthDataArray(unsigned __int64,unsigned __int64,unsigned __int64)
0x1800259a9  mov     [rbp+Src], eax
0x1800259ac  mov     [rbp+arg_C], 23h ; '#'
0x1800259b3  cmp     eax, 11000Ch
0x1800259b8  jbe     short loc_1800259D6
0x1800259ba  mov     rcx, [rbp+38h]; this
0x1800259be  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800259c5  mov     r9d, 80070057h; char *
0x1800259cb  mov     edx, 20Eh; void *
0x1800259d0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800259d6  lea     r8, [rbp+Src]; Src
0x1800259da  mov     edx, 8; unsigned __int64
0x1800259df  mov     rcx, rdi; this
0x1800259e2  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x1800259e7  mov     ebx, eax
0x1800259e9  test    eax, eax
0x1800259eb  jns     short loc_1800259F7
0x1800259ed  mov     edx, 20Fh
0x1800259f2  jmp     loc_18002590C
0x1800259f7  lea     r8, [rbp+arg_10]; Src
0x1800259fb  mov     edx, 4; unsigned __int64
0x180025a00  mov     rcx, rdi; this
0x180025a03  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025a08  mov     ebx, eax
0x180025a0a  test    eax, eax
0x180025a0c  jns     short loc_180025A18
0x180025a0e  mov     edx, 212h
0x180025a13  jmp     loc_18002590C
0x180025a18  lea     r8, [rbp+arg_10]; Src
0x180025a1c  mov     word ptr [rbp+arg_10], r14w
0x180025a21  mov     edx, 2; unsigned __int64
0x180025a26  mov     rcx, rdi; this
0x180025a29  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025a2e  mov     ebx, eax
0x180025a30  test    eax, eax
0x180025a32  jns     short loc_180025A3E
0x180025a34  mov     edx, 216h
0x180025a39  jmp     loc_18002590C
0x180025a3e  mov     r8, r15; Src
0x180025a41  mov     rdx, r14; unsigned __int64
0x180025a44  mov     rcx, rdi; this
0x180025a47  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025a4c  mov     ebx, eax
0x180025a4e  test    eax, eax
0x180025a50  jns     short loc_180025A5C
0x180025a52  mov     edx, 217h
0x180025a57  jmp     loc_18002590C
0x180025a5c  xor     ebx, ebx
0x180025a5e  cmp     rbx, rsi
0x180025a61  jnb     short loc_180025AC8
0x180025a63  mov     r15, [r12+rbx*8]
0x180025a67  mov     rcx, r15; unsigned __int16 *
0x180025a6a  call    ?StringSize@Writer@DictionarySerialization@StateRepository@@SA_KPEBG@Z; StateRepository::DictionarySerialization::Writer::StringSize(ushort const *)
0x180025a6f  mov     edx, 4; unsigned __int64
0x180025a74  mov     dword ptr [rbp+arg_10], eax
0x180025a77  lea     r8, [rbp+arg_10]; Src
0x180025a7b  mov     rcx, rdi; this
0x180025a7e  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025a83  mov     r14d, eax
0x180025a86  test    eax, eax
0x180025a88  js      short loc_180025AAB
0x180025a8a  mov     edx, dword ptr [rbp+arg_10]; unsigned __int64
0x180025a8d  mov     r8, r15; Src
0x180025a90  mov     rcx, rdi; this
0x180025a93  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025a98  mov     r14d, eax
0x180025a9b  test    eax, eax
0x180025a9d  js      short loc_180025AA4
0x180025a9f  inc     rbx
0x180025aa2  jmp     short loc_180025A5E
0x180025aa4  mov     edx, 21Fh
0x180025aa9  jmp     short loc_180025AB0
0x180025aab  mov     edx, 21Eh; void *
0x180025ab0  mov     rcx, [rbp+38h]; this
0x180025ab4  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180025abb  mov     r9d, r14d; char *
0x180025abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025ac3  mov     eax, r14d
0x180025ac6  jmp     short loc_180025AE2
0x180025ac8  mov     rcx, rdi; this
0x180025acb  call    ?UpdateForAddedPair@Writer@DictionarySerialization@StateRepository@@QEAAJXZ; StateRepository::DictionarySerialization::Writer::UpdateForAddedPair(void)
0x180025ad0  mov     ebx, eax
0x180025ad2  test    eax, eax
0x180025ad4  jns     short loc_180025AE0
0x180025ad6  mov     edx, 223h
0x180025adb  jmp     loc_18002590C
0x180025ae0  xor     eax, eax
0x180025ae2  mov     rbx, [rsp+20h+arg_0]
0x180025ae7  add     rsp, 20h
0x180025aeb  pop     r15
0x180025aed  pop     r14
0x180025aef  pop     r13
0x180025af1  pop     r12
0x180025af3  pop     rdi
0x180025af4  pop     rsi
0x180025af5  pop     rbp
0x180025af6  retn
```
