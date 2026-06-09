# CMicrodomBuilder::ProduceStringTable(_LBLOB *)

- ea: `0x180016090`
- end: `0x1800164a0`
- name: `?ProduceStringTable@CMicrodomBuilder@@AEBAJPEAU_LBLOB@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CMicrodomBuilder *__hidden this, struct _LBLOB *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800152ec`

## callees

- `0x1800031e0`
- `0x18001077c`
- `0x180016090`
- `0x18001fd10`
- `0x180022eb0`
- `0x180022f08`
- `0x180099cb0`
- `0x18009a070`

## string_xrefs

- `0x18001614a`: `onecore\base\xml\udom_builder.cpp`
- `0x180016290`: `onecore\base\xml\udom_builder.cpp`
- `0x1800163a6`: `onecore\base\xml\udom_builder.cpp`
- `0x18001640e`: `onecore\base\xml\udom_builder.cpp`
- `0x1800162bc`: `BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)`
- `0x18001642c`: `BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)`

## pseudocode

```c
__int64 __fastcall CMicrodomBuilder::ProduceStringTable(CMicrodomBuilder *this, struct _LBLOB *a2)
{
  _QWORD **v2; // rbx
  _QWORD **v4; // rax
  _QWORD *v5; // rdi
  unsigned __int64 v6; // r13
  size_t v7; // r14
  void *v8; // rax
  __int64 v9; // rsi
  void *v10; // r14
  _QWORD *v12; // r8
  __int64 v13; // r9
  _QWORD *v14; // rax
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  _QWORD *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rax
  unsigned int v22; // ebx
  struct _LBLOB *v23; // rdx
  unsigned __int64 v24; // rbx
  char *v25; // r15
  __int64 v26; // r12
  char *v27; // rdi
  __int64 v28; // rsi
  __int64 v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  unsigned __int64 v32; // rbx
  const char *v33; // rax
  int v34; // eax
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // [rsp+20h] [rbp-38h] BYREF
  const char *v37; // [rsp+28h] [rbp-30h] BYREF
  const char *v38; // [rsp+30h] [rbp-28h]
  __int64 v39; // [rsp+38h] [rbp-20h]
  const char *v40; // [rsp+40h] [rbp-18h]
  struct _LBLOB *v41; // [rsp+48h] [rbp-10h]

  v2 = (_QWORD **)*((_QWORD *)this + 2);
  v4 = &v2[4 * *((_QWORD *)this + 4)];
  v41 = a2;
  if ( v2 >= v4 )
  {
    v2 = 0;
    v5 = 0;
  }
  else
  {
    while ( 1 )
    {
      v5 = *v2;
      if ( *v2 != v2 )
        break;
      v2 += 4;
      if ( v2 >= v4 )
      {
        v5 = 0;
        v2 = 0;
        break;
      }
    }
  }
  v6 = *((_QWORD *)this + 5);
  if ( v6 )
  {
    v7 = saturated_mul(v6, 0x10u);
    v8 = operator new(v7);
    v9 = (__int64)v8;
    if ( v8 )
    {
      memset(v8, 0, v7);
      v10 = (void *)v9;
    }
    else
    {
      v9 = 0;
      v10 = 0;
      v6 = 0;
    }
  }
  else
  {
    v10 = 0;
    v9 = 8;
    v6 = 0;
  }
  if ( !v9 )
  {
    v39 = 454;
    v37 = "onecore\\base\\xml\\udom_builder.cpp";
    v38 = "CMicrodomBuilder::ProduceStringTable";
    v40 = "Pairs.Allocate(m_StringTable.GetEntryCount())";
    RtlReportErrorOrigination(&v37, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    if ( v10 )
      operator delete(v10);
    return 3221225495LL;
  }
  v12 = (_QWORD *)*((_QWORD *)this + 2);
  v13 = 0;
  v14 = v12;
  v15 = (unsigned __int64)&v12[4 * *((_QWORD *)this + 4)];
  if ( (unsigned __int64)v12 < v15 )
  {
    while ( (_QWORD *)*v14 == v14 )
    {
      v14 += 4;
      if ( (unsigned __int64)v14 >= v15 )
        goto LABEL_20;
    }
    v2 = (_QWORD **)v14;
    v5 = (_QWORD *)*v14;
  }
LABEL_20:
  v16 = ((char *)v14 - (char *)v12) >> 5;
LABEL_21:
  while ( v2 )
  {
    v17 = 0;
    if ( v5 != v2 )
      v17 = v5;
    v18 = 2 * v13;
    *((_DWORD *)v10 + 2 * v18) = *((_DWORD *)v17 + 16);
    *((_QWORD *)v10 + v18 + 1) = v17 + 5;
    v5 = (_QWORD *)*v5;
    if ( !v5 || v5 == v2 )
    {
      v19 = *((_QWORD *)this + 2);
      v2 = 0;
      v5 = 0;
      v20 = v19 + 32LL * *((_QWORD *)this + 4);
      v21 = (_QWORD *)(v19 + 32 * (v16 + 1));
      if ( (unsigned __int64)v21 < v20 )
      {
        while ( (_QWORD *)*v21 == v21 )
        {
          v21 += 4;
          if ( (unsigned __int64)v21 >= v20 )
          {
            v16 = ((__int64)v21 - v19) >> 5;
            ++v13;
            goto LABEL_21;
          }
        }
        v2 = (_QWORD **)v21;
        v5 = (_QWORD *)*v21;
      }
      v16 = ((__int64)v21 - v19) >> 5;
    }
    ++v13;
  }
  BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(
    &v36,
    v10,
    (__int64)(16 * v6) >> 4,
    v13);
  v22 = v36;
  if ( (v36 & 0x80000000) != 0LL )
  {
    v39 = 462;
    v37 = "onecore\\base\\xml\\udom_builder.cpp";
    v38 = "CMicrodomBuilder::ProduceStringTable";
    v40 = "BUCL::Rtl::QuickSort(Pairs, CompareStringSlot)";
    RtlReportErrorOrigination(&v37, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v36);
    if ( v10 )
      operator delete(v10);
    return v22;
  }
  v23 = v41;
  v24 = 0;
  v25 = (char *)(*((_QWORD *)v41 + 2) + *(_QWORD *)v41);
  v26 = *((_QWORD *)v41 + 2) + *((_QWORD *)v41 + 1);
  v27 = v25 + 12;
  if ( v6 )
  {
    do
    {
      v28 = 2 * v24;
      v29 = *((_QWORD *)v10 + 2 * v24 + 1);
      if ( (unsigned __int64)(v26 - (_QWORD)v27) <= *(_QWORD *)v29 )
        goto LABEL_62;
      memmove(v27, *(const void **)(v29 + 16), *(_QWORD *)v29);
      ++v24;
      v30 = **((_QWORD **)v10 + v28 + 1);
      v27[v30] = 0;
      v27 += v30 + 1;
    }
    while ( v24 < v6 );
    v23 = v41;
  }
  *(_QWORD *)v23 = &v27[-*((_QWORD *)v23 + 2)];
  v31 = 0;
  v36 = 0;
  if ( v6 > 0xFFFFFFFF )
  {
    HIDWORD(v36) = -1073741675;
  }
  else
  {
    v31 = v6;
    LODWORD(v36) = v6;
    if ( v6 == (unsigned int)v6 )
      HIDWORD(v36) = 0;
    else
      HIDWORD(v36) = -1073741595;
  }
  v32 = HIDWORD(v36);
  *((_DWORD *)v25 + 2) = v31;
  if ( (v32 & 0x80000000) != 0LL )
  {
    v39 = 491;
    v37 = "onecore\\base\\xml\\udom_builder.cpp";
    v38 = "CMicrodomBuilder::ProduceStringTable";
    v33 = "BUCL::Rtl::ConvertInteger(Pairs.Length, pHeader->TotalCount)";
LABEL_55:
    v40 = v33;
    RtlReportErrorOrigination(&v37, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v32);
    if ( v10 )
      operator delete(v10);
    return (unsigned int)v32;
  }
  v34 = 0;
  v35 = v27 - v25;
  v36 = 0;
  if ( v35 > 0xFFFFFFFF )
  {
    HIDWORD(v36) = -1073741675;
  }
  else
  {
    v34 = v35;
    LODWORD(v36) = v35;
    if ( v35 == (unsigned int)v35 )
      HIDWORD(v36) = 0;
    else
      HIDWORD(v36) = -1073741595;
  }
  v32 = HIDWORD(v36);
  *((_DWORD *)v25 + 1) = v34;
  if ( (v32 & 0x80000000) != 0LL )
  {
    v39 = 496;
    v37 = "onecore\\base\\xml\\udom_builder.cpp";
    v38 = "CMicrodomBuilder::ProduceStringTable";
    v33 = "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)pvWriteCursor) - ((ULONG_PTR)pHeader), pHeader->TotalSize)";
    goto LABEL_55;
  }
  *(_DWORD *)v25 = 1884513357;
  if ( *(_QWORD *)v23 > *((_QWORD *)v23 + 1) )
  {
LABEL_62:
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18001649FLL);
  }
  if ( v10 )
    operator delete(v10);
  return 0;
}

```

## disassembly

```asm
0x180016090  push    rbp
0x180016092  push    rbx
0x180016093  push    rsi
0x180016094  push    rdi
0x180016095  push    r13
0x180016097  push    r15
0x180016099  mov     rbp, rsp
0x18001609c  sub     rsp, 58h
0x1800160a0  mov     rbx, [rcx+10h]
0x1800160a4  mov     r15, rcx
0x1800160a7  mov     rax, [rcx+20h]
0x1800160ab  shl     rax, 5
0x1800160af  add     rax, rbx
0x1800160b2  mov     [rbp+var_10], rdx
0x1800160b6  cmp     rbx, rax
0x1800160b9  jnb     short loc_1800160D7
0x1800160bb  nop     dword ptr [rax+rax+00h]
0x1800160c0  mov     rdi, [rbx]
0x1800160c3  cmp     rdi, rbx
0x1800160c6  jnz     short loc_1800160DB
0x1800160c8  add     rbx, 20h ; ' '
0x1800160cc  cmp     rbx, rax
0x1800160cf  jb      short loc_1800160C0
0x1800160d1  xor     edi, edi
0x1800160d3  xor     ebx, ebx
0x1800160d5  jmp     short loc_1800160DB
0x1800160d7  xor     ebx, ebx
0x1800160d9  xor     edi, edi
0x1800160db  mov     r13, [rcx+28h]
0x1800160df  mov     [rsp+58h+var_8], r14
0x1800160e4  test    r13, r13
0x1800160e7  jz      short loc_18001613A
0x1800160e9  mov     eax, 10h
0x1800160ee  mul     r13
0x1800160f1  mov     r14, rax
0x1800160f4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800160fb  cmovb   r14, rax
0x1800160ff  mov     rcx, r14; Size
0x180016102  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016107  mov     rsi, rax
0x18001610a  test    rax, rax
0x18001610d  jz      short loc_18001612A
0x18001610f  mov     r8, r14; Size
0x180016112  xor     edx, edx; Val
0x180016114  mov     rcx, rax; void *
0x180016117  call    memset
0x18001611c  xor     eax, eax
0x18001611e  mov     r14, rsi
0x180016121  test    rsi, rsi
0x180016124  cmovz   r13, rax
0x180016128  jmp     short loc_180016145
0x18001612a  xor     esi, esi
0x18001612c  xor     eax, eax
0x18001612e  test    rsi, rsi
0x180016131  mov     r14d, esi
0x180016134  cmovz   r13, rax
0x180016138  jmp     short loc_180016145
0x18001613a  xor     r14d, r14d
0x18001613d  mov     esi, 8
0x180016142  xor     r13d, r13d
0x180016145  test    rsi, rsi
0x180016148  jnz     short loc_1800161A0
0x18001614a  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180016151  mov     [rbp+var_20], 1C6h
0x180016159  mov     [rbp+var_30], rax
0x18001615d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180016164  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x18001616b  mov     r8d, 0C0000017h
0x180016171  mov     [rbp+var_28], rax
0x180016175  lea     rcx, [rbp+var_30]
0x180016179  lea     rax, aPairsAllocateM; "Pairs.Allocate(m_StringTable.GetEntryCo"...
0x180016180  mov     [rbp+var_18], rax
0x180016184  call    RtlReportErrorOrigination
0x180016189  test    r14, r14
0x18001618c  jz      short loc_180016196
0x18001618e  mov     rcx, r14; Block
0x180016191  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016196  mov     eax, 0C0000017h
0x18001619b  jmp     loc_180016482
0x1800161a0  mov     r8, [r15+10h]
0x1800161a4  xor     r9d, r9d
0x1800161a7  mov     rdx, [r15+20h]
0x1800161ab  mov     rax, r8
0x1800161ae  shl     rdx, 5
0x1800161b2  add     rdx, r8
0x1800161b5  cmp     r8, rdx
0x1800161b8  jnb     short loc_1800161D9
0x1800161ba  nop     word ptr [rax+rax+00h]
0x1800161c0  mov     rcx, [rax]
0x1800161c3  cmp     rcx, rax
0x1800161c6  jnz     short loc_1800161D3
0x1800161c8  add     rax, 20h ; ' '
0x1800161cc  cmp     rax, rdx
0x1800161cf  jb      short loc_1800161C0
0x1800161d1  jmp     short loc_1800161D9
0x1800161d3  mov     rbx, rax
0x1800161d6  mov     rdi, rcx
0x1800161d9  sub     rax, r8
0x1800161dc  sar     rax, 5
0x1800161e0  test    rbx, rbx
0x1800161e3  jz      loc_180016272
0x1800161e9  xor     r8d, r8d
0x1800161ec  mov     rdx, r9
0x1800161ef  cmp     rdi, rbx
0x1800161f2  cmovnz  r8, rdi
0x1800161f6  add     rdx, rdx
0x1800161f9  mov     ecx, [r8+40h]
0x1800161fd  mov     [r14+rdx*8], ecx
0x180016201  lea     rcx, [r8+28h]
0x180016205  mov     [r14+rdx*8+8], rcx
0x18001620a  mov     rdi, [rdi]
0x18001620d  test    rdi, rdi
0x180016210  jz      short loc_180016217
0x180016212  cmp     rdi, rbx
0x180016215  jnz     short loc_18001626A
0x180016217  mov     r8, [r15+10h]
0x18001621b  xor     ebx, ebx
0x18001621d  mov     rdx, [r15+20h]
0x180016221  xor     edi, edi
0x180016223  inc     rax
0x180016226  shl     rdx, 5
0x18001622a  shl     rax, 5
0x18001622e  add     rdx, r8
0x180016231  add     rax, r8
0x180016234  cmp     rax, rdx
0x180016237  jnb     short loc_180016263
0x180016239  nop     dword ptr [rax+00000000h]
0x180016240  mov     rcx, [rax]
0x180016243  cmp     rcx, rax
0x180016246  jnz     short loc_18001625D
0x180016248  add     rax, 20h ; ' '
0x18001624c  cmp     rax, rdx
0x18001624f  jb      short loc_180016240
0x180016251  sub     rax, r8
0x180016254  sar     rax, 5
0x180016258  inc     r9
0x18001625b  jmp     short loc_1800161E0
0x18001625d  mov     rbx, rax
0x180016260  mov     rdi, rcx
0x180016263  sub     rax, r8
0x180016266  sar     rax, 5
0x18001626a  inc     r9
0x18001626d  jmp     loc_1800161E0
0x180016272  mov     r8, r13
0x180016275  lea     rcx, [rbp+var_38]
0x180016279  shl     r8, 4
0x18001627d  mov     rdx, r14
0x180016280  sar     r8, 4
0x180016284  call    ??$QuickSort@VCCallDisposition@Rtl@BUCL@@_KUStringTablePair@CMicrodomBuilder@@P6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@Implementation@3@AEBU45@0@Z@Implementation@BUCL@@YA?AVCCallDisposition@Rtl@1@PEAUStringTablePair@CMicrodomBuilder@@_KP6A?AU?$ComparisonResultKind@VCCallDisposition@Rtl@BUCL@@@01@AEBU45@2@Z@Z; BUCL::Implementation::QuickSort<BUCL::Rtl::CCallDisposition,unsigned __int64,CMicrodomBuilder::StringTablePair,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &)>(CMicrodomBuilder::StringTablePair *,unsigned __int64,BUCL::Implementation::ComparisonResultKind<BUCL::Rtl::CCallDisposition> (*)(CMicrodomBuilder::StringTablePair const &,CMicrodomBuilder::StringTablePair const &))
0x180016289  mov     ebx, dword ptr [rbp+var_38]
0x18001628c  test    ebx, ebx
0x18001628e  jns     short loc_1800162E0
0x180016290  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180016297  mov     [rbp+var_20], 1CEh
0x18001629f  mov     [rbp+var_30], rax
0x1800162a3  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800162aa  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x1800162b1  mov     r8d, ebx
0x1800162b4  mov     [rbp+var_28], rax
0x1800162b8  lea     rcx, [rbp+var_30]
0x1800162bc  lea     rax, aBuclRtlQuickso; "BUCL::Rtl::QuickSort(Pairs, CompareStri"...
0x1800162c3  mov     [rbp+var_18], rax
0x1800162c7  call    RtlReportErrorOrigination
0x1800162cc  test    r14, r14
0x1800162cf  jz      short loc_1800162D9
0x1800162d1  mov     rcx, r14; Block
0x1800162d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800162d9  mov     eax, ebx
0x1800162db  jmp     loc_180016482
0x1800162e0  mov     rdx, [rbp+var_10]
0x1800162e4  xor     ebx, ebx
0x1800162e6  mov     [rsp+58h+arg_10], r12
0x1800162ee  mov     r15, [rdx]
0x1800162f1  add     r15, [rdx+10h]
0x1800162f5  mov     r12, [rdx+8]
0x1800162f9  add     r12, [rdx+10h]
0x1800162fd  lea     rdi, [r15+0Ch]
0x180016301  test    r13, r13
0x180016304  jz      short loc_180016357
0x180016306  nop     word ptr [rax+rax+00000000h]
0x180016310  mov     rsi, rbx
0x180016313  mov     rax, r12
0x180016316  add     rsi, rsi
0x180016319  sub     rax, rdi
0x18001631c  mov     rdx, [r14+rsi*8+8]
0x180016321  mov     r8, [rdx]; Size
0x180016324  cmp     rax, r8
0x180016327  jbe     loc_180016495
0x18001632d  mov     rdx, [rdx+10h]; Src
0x180016331  mov     rcx, rdi; void *
0x180016334  call    memmove
0x180016339  mov     rax, [r14+rsi*8+8]
0x18001633e  inc     rbx
0x180016341  mov     rax, [rax]
0x180016344  mov     byte ptr [rax+rdi], 0
0x180016348  inc     rdi
0x18001634b  add     rdi, rax
0x18001634e  cmp     rbx, r13
0x180016351  jb      short loc_180016310
0x180016353  mov     rdx, [rbp+var_10]
0x180016357  mov     rax, rdi
0x18001635a  mov     r8d, 0FFFFFFFFh
0x180016360  sub     rax, [rdx+10h]
0x180016364  mov     [rdx], rax
0x180016367  xor     eax, eax
0x180016369  mov     [rbp+var_38], rax
0x18001636d  cmp     r13, r8
0x180016370  ja      short loc_18001638F
0x180016372  mov     eax, r13d
0x180016375  mov     dword ptr [rbp+var_38], eax
0x180016378  cmp     r13, rax
0x18001637b  jz      short loc_180016386
0x18001637d  mov     dword ptr [rbp+var_38+4], 0C00000E5h
0x180016384  jmp     short loc_180016396
0x180016386  mov     dword ptr [rbp+var_38+4], 0
0x18001638d  jmp     short loc_180016396
0x18001638f  mov     dword ptr [rbp+var_38+4], 0C0000095h
0x180016396  mov     rbx, [rbp+var_38]
0x18001639a  shr     rbx, 20h
0x18001639e  mov     [r15+8], eax
0x1800163a2  test    ebx, ebx
0x1800163a4  jns     short loc_1800163CD
0x1800163a6  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x1800163ad  mov     [rbp+var_20], 1EBh
0x1800163b5  mov     [rbp+var_30], rax
0x1800163b9  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x1800163c0  mov     [rbp+var_28], rax
0x1800163c4  lea     rax, aBuclRtlConvert; "BUCL::Rtl::ConvertInteger(Pairs.Length,"...
0x1800163cb  jmp     short loc_180016433
0x1800163cd  xor     eax, eax
0x1800163cf  sub     rdi, r15
0x1800163d2  mov     [rbp+var_38], rax
0x1800163d6  cmp     rdi, r8
0x1800163d9  ja      short loc_1800163F7
0x1800163db  mov     eax, edi
0x1800163dd  mov     dword ptr [rbp+var_38], eax
0x1800163e0  cmp     rdi, rax
0x1800163e3  jz      short loc_1800163EE
0x1800163e5  mov     dword ptr [rbp+var_38+4], 0C00000E5h
0x1800163ec  jmp     short loc_1800163FE
0x1800163ee  mov     dword ptr [rbp+var_38+4], 0
0x1800163f5  jmp     short loc_1800163FE
0x1800163f7  mov     dword ptr [rbp+var_38+4], 0C0000095h
0x1800163fe  mov     rbx, [rbp+var_38]
0x180016402  shr     rbx, 20h
0x180016406  mov     [r15+4], eax
0x18001640a  test    ebx, ebx
0x18001640c  jns     short loc_18001645B
0x18001640e  lea     rax, aOnecoreBaseXml_7; "onecore\\base\\xml\\udom_builder.cpp"
0x180016415  mov     [rbp+var_20], 1F0h
0x18001641d  mov     [rbp+var_30], rax
0x180016421  lea     rax, aCmicrodombuild_22; "CMicrodomBuilder::ProduceStringTable"
0x180016428  mov     [rbp+var_28], rax
0x18001642c  lea     rax, aBuclRtlConvert_6; "BUCL::Rtl::ConvertInteger( ((ULONG_PTR)"...
0x180016433  mov     r8d, ebx
0x180016436  mov     [rbp+var_18], rax
0x18001643a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180016441  lea     rcx, [rbp+var_30]
0x180016445  call    RtlReportErrorOrigination
0x18001644a  test    r14, r14
0x18001644d  jz      short loc_180016457
0x18001644f  mov     rcx, r14; Block
0x180016452  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016457  mov     eax, ebx
0x180016459  jmp     short loc_18001647A
0x18001645b  mov     dword ptr [r15], 7053644Dh
0x180016462  mov     rax, [rdx+8]
0x180016466  cmp     [rdx], rax
0x180016469  ja      short loc_180016495
0x18001646b  test    r14, r14
0x18001646e  jz      short loc_180016478
0x180016470  mov     rcx, r14; Block
0x180016473  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016478  xor     eax, eax
0x18001647a  mov     r12, [rsp+58h+arg_10]
0x180016482  mov     r14, [rsp+58h+var_8]
0x180016487  add     rsp, 58h
0x18001648b  pop     r15
0x18001648d  pop     r13
0x18001648f  pop     rdi
0x180016490  pop     rsi
0x180016491  pop     rbx
0x180016492  pop     rbp
0x180016493  retn
0x180016495  mov     ecx, 0C00000E5h; int
0x18001649a  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
