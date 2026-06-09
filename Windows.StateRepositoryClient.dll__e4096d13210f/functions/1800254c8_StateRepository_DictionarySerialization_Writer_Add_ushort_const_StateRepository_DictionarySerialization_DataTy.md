# StateRepository::DictionarySerialization::Writer::Add(ushort const *,StateRepository::DictionarySerialization::DataType,unsigned __int64,void const *,unsigned __int64 const *)

- ea: `0x1800254c8`
- end: `0x1800257d1`
- name: `?Add@Writer@DictionarySerialization@StateRepository@@QEAAJPEBGW4DataType@23@_KPEBXPEB_K@Z`
- size: `777`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned __int64, void *, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180024170`
- `0x1800257d8`
- `0x180025b00`

## callees

- `0x1800075e4`
- `0x1800191a4`
- `0x180023e20`
- `0x1800254c8`
- `0x180025cb0`
- `0x180025d20`
- `0x180025e44`
- `0x180027010`

## string_xrefs

- `0x180025506`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x18002558a`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x180025610`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x180025665`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`
- `0x18002579b`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywriter.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::Writer::Add(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 a4,
        void *a5,
        unsigned int *a6)
{
  unsigned int v7; // esi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  void *v13; // r13
  unsigned int *v14; // r14
  __int64 (__fastcall *v15)(__int64, __int64, const unsigned __int16 *, _QWORD); // rax
  __int64 v16; // rdx
  int v17; // esi
  __int64 v18; // rdx
  bool v19; // zf
  unsigned __int64 v20; // r15
  unsigned int v21; // r15d
  __int64 (__fastcall *v22)(__int64, __int64, const unsigned __int16 *, _QWORD); // rax
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // edi
  int v26; // [rsp+20h] [rbp-30h]
  int v27; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int Src; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v30; // [rsp+9Ch] [rbp+4Ch]
  unsigned int v31; // [rsp+A0h] [rbp+50h]

  v31 = a3;
  v7 = a3;
  if ( !a2 )
  {
    v10 = -2147467261;
    v11 = 418;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
      (const char *)v10,
      v26);
    return v10;
  }
  v13 = a5;
  if ( a4 && !a5 )
  {
    v10 = -2147024809;
    v11 = 419;
    goto LABEL_3;
  }
  v14 = a6;
  if ( !*(_BYTE *)(a1 + 56) )
  {
    v15 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, _QWORD))(a1 + 24);
    if ( v15 )
    {
      v16 = *(_QWORD *)(a1 + 32);
      *(_BYTE *)(a1 + 56) = 1;
      Src = 0;
      v26 = a4;
      v17 = v15(a1, v16, a2, a3);
      if ( v17 < 0 )
      {
        v18 = 426;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
          (const char *)(unsigned int)v17,
          v26);
        return (unsigned int)v17;
      }
      v19 = Src == 1;
      *(_BYTE *)(a1 + 56) = 0;
      if ( v19 )
        return 0;
      v7 = v31;
    }
  }
  v20 = StateRepository::DictionarySerialization::Writer::KeySize(a2);
  if ( (_WORD)v20 == 0xFFFF )
  {
    v10 = -2147024809;
    v11 = 438;
    goto LABEL_3;
  }
  if ( a4 > 0x100000 )
  {
    v10 = -2147024809;
    v11 = 441;
    goto LABEL_3;
  }
  Src = StateRepository::DictionarySerialization::Writer::SizeOfPair(v20, v7, a4, v14);
  v30 = v7;
  if ( Src > 0x11000C )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
      (const char *)0x80070057LL,
      v26);
  v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, 8u, &Src);
  if ( v17 < 0 )
  {
    v18 = 446;
    goto LABEL_11;
  }
  if ( v14 )
  {
    Src = *v14;
    if ( a4 % *(_QWORD *)v14 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
        (const char *)0x8000FFFFLL,
        v26);
    v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, 4u, &Src);
    if ( v17 < 0 )
    {
      v18 = 453;
      goto LABEL_11;
    }
  }
  LOWORD(Src) = v20;
  v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, 2u, &Src);
  if ( v17 < 0 )
  {
    v18 = 458;
    goto LABEL_11;
  }
  v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, v20, a2);
  if ( v17 < 0 )
  {
    v18 = 459;
    goto LABEL_11;
  }
  v21 = v31;
  if ( ((1LL << v31) & 1) == 0 )
  {
    if ( ((1LL << v31) & 0x7FFFFF04004LL) != 0 )
    {
      Src = a4;
      v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, 4u, &Src);
      if ( v17 < 0 )
      {
        v18 = 467;
        goto LABEL_11;
      }
    }
    v17 = StateRepository::Blob::Append((StateRepository::Blob *)a1, a4, v13);
    if ( v17 < 0 )
    {
      v18 = 469;
      goto LABEL_11;
    }
  }
  v17 = StateRepository::DictionarySerialization::Writer::UpdateForAddedPair((StateRepository::DictionarySerialization::Writer *)a1);
  if ( v17 < 0 )
  {
    v18 = 473;
    goto LABEL_11;
  }
  if ( !*(_BYTE *)(a1 + 56) )
  {
    v22 = *(__int64 (__fastcall **)(__int64, __int64, const unsigned __int16 *, _QWORD))(a1 + 40);
    if ( v22 )
    {
      v23 = *(_QWORD *)(a1 + 48);
      v27 = a4;
      *(_BYTE *)(a1 + 56) = 1;
      v24 = v22(a1, v23, a2, v21);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywriter.cpp",
          (const char *)(unsigned int)v24,
          v27);
        return v25;
      }
      *(_BYTE *)(a1 + 56) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800254c8  mov     [rsp-38h+arg_0], rbx
0x1800254cd  mov     [rsp-38h+arg_10], r8d
0x1800254d2  push    rbp
0x1800254d3  push    rsi
0x1800254d4  push    rdi
0x1800254d5  push    r12
0x1800254d7  push    r13
0x1800254d9  push    r14
0x1800254db  push    r15
0x1800254dd  mov     rbp, rsp
0x1800254e0  sub     rsp, 50h
0x1800254e4  xor     r15d, r15d
0x1800254e7  mov     rdi, r9
0x1800254ea  mov     esi, r8d
0x1800254ed  mov     r12, rdx
0x1800254f0  mov     rbx, rcx
0x1800254f3  test    rdx, rdx
0x1800254f6  jnz     short loc_18002551C
0x1800254f8  mov     ebx, 80004003h
0x1800254fd  mov     edx, 1A2h; void *
0x180025502  mov     rcx, [rbp+38h]; this
0x180025506  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x18002550d  mov     r9d, ebx; char *
0x180025510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025515  mov     eax, ebx
0x180025517  jmp     loc_1800257B9
0x18002551c  mov     r13, [rbp+arg_20]
0x180025520  test    rdi, rdi
0x180025523  jz      short loc_180025536
0x180025525  test    r13, r13
0x180025528  jnz     short loc_180025536
0x18002552a  mov     ebx, 80070057h
0x18002552f  mov     edx, 1A3h
0x180025534  jmp     short loc_180025502
0x180025536  mov     r14, [rbp+arg_28]
0x18002553a  cmp     [rcx+38h], r15b
0x18002553e  jnz     short loc_1800255B1
0x180025540  mov     rax, [rcx+18h]
0x180025544  test    rax, rax
0x180025547  jz      short loc_1800255B1
0x180025549  mov     rdx, [rbx+20h]
0x18002554d  mov     r9d, r8d
0x180025550  mov     byte ptr [rcx+38h], 1
0x180025554  mov     r8, r12
0x180025557  lea     rcx, [rbp+Src]
0x18002555b  mov     [rbp+Src], r15d
0x18002555f  mov     [rsp+50h+var_18], rcx
0x180025564  mov     rcx, rbx
0x180025567  mov     [rsp+50h+var_20], r14
0x18002556c  mov     [rsp+50h+var_28], r13
0x180025571  mov     qword ptr [rsp+50h+var_30], rdi; int
0x180025576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002557b  mov     esi, eax
0x18002557d  test    eax, eax
0x18002557f  jns     short loc_1800255A0
0x180025581  mov     edx, 1AAh; void *
0x180025586  mov     rcx, [rbp+38h]; this
0x18002558a  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180025591  mov     r9d, esi; char *
0x180025594  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025599  mov     eax, esi
0x18002559b  jmp     loc_1800257B9
0x1800255a0  cmp     [rbp+Src], 1
0x1800255a4  mov     [rbx+38h], r15b
0x1800255a8  jz      loc_1800257B7
0x1800255ae  mov     esi, [rbp+arg_10]
0x1800255b1  mov     rcx, r12; unsigned __int16 *
0x1800255b4  call    ?KeySize@Writer@DictionarySerialization@StateRepository@@SAGPEBG@Z; StateRepository::DictionarySerialization::Writer::KeySize(ushort const *)
0x1800255b9  movzx   r15d, ax
0x1800255bd  mov     eax, 0FFFEh
0x1800255c2  cmp     r15w, ax
0x1800255c6  jbe     short loc_1800255D7
0x1800255c8  mov     ebx, 80070057h
0x1800255cd  mov     edx, 1B6h
0x1800255d2  jmp     loc_180025502
0x1800255d7  cmp     rdi, 100000h
0x1800255de  jbe     short loc_1800255EF
0x1800255e0  mov     ebx, 80070057h
0x1800255e5  mov     edx, 1B9h
0x1800255ea  jmp     loc_180025502
0x1800255ef  mov     rcx, r15
0x1800255f2  mov     r9, r14
0x1800255f5  mov     r8, rdi
0x1800255f8  mov     edx, esi
0x1800255fa  call    ?SizeOfPair@Writer@DictionarySerialization@StateRepository@@SAI_KW4DataType@23@0PEB_K@Z; StateRepository::DictionarySerialization::Writer::SizeOfPair(unsigned __int64,StateRepository::DictionarySerialization::DataType,unsigned __int64,unsigned __int64 const *)
0x1800255ff  mov     [rbp+Src], eax
0x180025602  mov     [rbp+arg_C], esi
0x180025605  cmp     eax, 11000Ch
0x18002560a  jbe     short loc_180025628
0x18002560c  mov     rcx, [rbp+38h]; this
0x180025610  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180025617  mov     r9d, 80070057h; char *
0x18002561d  mov     edx, 1BDh; void *
0x180025622  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180025628  lea     r8, [rbp+Src]; Src
0x18002562c  mov     edx, 8; unsigned __int64
0x180025631  mov     rcx, rbx; this
0x180025634  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025639  mov     esi, eax
0x18002563b  test    eax, eax
0x18002563d  jns     short loc_180025649
0x18002563f  mov     edx, 1BEh
0x180025644  jmp     loc_180025586
0x180025649  test    r14, r14
0x18002564c  jz      short loc_18002569E
0x18002564e  mov     eax, [r14]
0x180025651  xor     edx, edx
0x180025653  mov     [rbp+Src], eax
0x180025656  mov     rax, rdi
0x180025659  div     qword ptr [r14]
0x18002565c  test    rdx, rdx
0x18002565f  jz      short loc_18002567D
0x180025661  mov     rcx, [rbp+38h]; this
0x180025665  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x18002566c  mov     r9d, 8000FFFFh; char *
0x180025672  mov     edx, 1C4h; void *
0x180025677  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002567d  lea     r8, [rbp+Src]; Src
0x180025681  mov     edx, 4; unsigned __int64
0x180025686  mov     rcx, rbx; this
0x180025689  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x18002568e  mov     esi, eax
0x180025690  test    eax, eax
0x180025692  jns     short loc_18002569E
0x180025694  mov     edx, 1C5h
0x180025699  jmp     loc_180025586
0x18002569e  lea     r8, [rbp+Src]; Src
0x1800256a2  mov     word ptr [rbp+Src], r15w
0x1800256a7  mov     edx, 2; unsigned __int64
0x1800256ac  mov     rcx, rbx; this
0x1800256af  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x1800256b4  mov     esi, eax
0x1800256b6  test    eax, eax
0x1800256b8  jns     short loc_1800256C4
0x1800256ba  mov     edx, 1CAh
0x1800256bf  jmp     loc_180025586
0x1800256c4  mov     r8, r12; Src
0x1800256c7  mov     rdx, r15; unsigned __int64
0x1800256ca  mov     rcx, rbx; this
0x1800256cd  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x1800256d2  mov     esi, eax
0x1800256d4  test    eax, eax
0x1800256d6  jns     short loc_1800256E2
0x1800256d8  mov     edx, 1CBh
0x1800256dd  jmp     loc_180025586
0x1800256e2  mov     r15d, [rbp+arg_10]
0x1800256e6  mov     eax, 1
0x1800256eb  mov     ecx, r15d
0x1800256ee  shl     rax, cl
0x1800256f1  test    cs:qword_18002F578, rax
0x1800256f8  jnz     short loc_180025745
0x1800256fa  test    cs:qword_18002F570, rax
0x180025701  jz      short loc_180025727
0x180025703  lea     r8, [rbp+Src]; Src
0x180025707  mov     [rbp+Src], edi
0x18002570a  mov     edx, 4; unsigned __int64
0x18002570f  mov     rcx, rbx; this
0x180025712  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025717  mov     esi, eax
0x180025719  test    eax, eax
0x18002571b  jns     short loc_180025727
0x18002571d  mov     edx, 1D3h
0x180025722  jmp     loc_180025586
0x180025727  mov     r8, r13; Src
0x18002572a  mov     rdx, rdi; unsigned __int64
0x18002572d  mov     rcx, rbx; this
0x180025730  call    ?Append@Blob@StateRepository@@QEAAJ_KPEBX@Z; StateRepository::Blob::Append(unsigned __int64,void const *)
0x180025735  mov     esi, eax
0x180025737  test    eax, eax
0x180025739  jns     short loc_180025745
0x18002573b  mov     edx, 1D5h
0x180025740  jmp     loc_180025586
0x180025745  mov     rcx, rbx; this
0x180025748  call    ?UpdateForAddedPair@Writer@DictionarySerialization@StateRepository@@QEAAJXZ; StateRepository::DictionarySerialization::Writer::UpdateForAddedPair(void)
0x18002574d  mov     esi, eax
0x18002574f  test    eax, eax
0x180025751  jns     short loc_18002575D
0x180025753  mov     edx, 1D9h
0x180025758  jmp     loc_180025586
0x18002575d  cmp     byte ptr [rbx+38h], 0
0x180025761  jnz     short loc_1800257B7
0x180025763  mov     rax, [rbx+28h]
0x180025767  test    rax, rax
0x18002576a  jz      short loc_1800257B7
0x18002576c  mov     rdx, [rbx+30h]
0x180025770  mov     r9d, r15d
0x180025773  mov     [rsp+50h+var_20], r14
0x180025778  mov     r8, r12
0x18002577b  mov     [rsp+50h+var_28], r13
0x180025780  mov     rcx, rbx
0x180025783  mov     qword ptr [rsp+50h+var_30], rdi; int
0x180025788  mov     byte ptr [rbx+38h], 1
0x18002578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025791  mov     edi, eax
0x180025793  test    eax, eax
0x180025795  jns     short loc_1800257B3
0x180025797  mov     rcx, [rbp+38h]; this
0x18002579b  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x1800257a2  mov     r9d, eax; char *
0x1800257a5  mov     edx, 1DFh; void *
0x1800257aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800257af  mov     eax, edi
0x1800257b1  jmp     short loc_1800257B9
0x1800257b3  mov     byte ptr [rbx+38h], 0
0x1800257b7  xor     eax, eax
0x1800257b9  mov     rbx, [rsp+50h+arg_0]
0x1800257c1  add     rsp, 50h
0x1800257c5  pop     r15
0x1800257c7  pop     r14
0x1800257c9  pop     r13
0x1800257cb  pop     r12
0x1800257cd  pop     rdi
0x1800257ce  pop     rsi
0x1800257cf  pop     rbp
0x1800257d0  retn
```
