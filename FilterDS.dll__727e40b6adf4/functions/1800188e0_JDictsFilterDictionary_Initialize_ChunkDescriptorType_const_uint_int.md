# JDictsFilterDictionary::Initialize(_ChunkDescriptorType const *,uint,int)

- ea: `0x1800188e0`
- end: `0x180018cee`
- name: `?Initialize@JDictsFilterDictionary@@UEAAJPEBU_ChunkDescriptorType@@IH@Z`
- size: `1038`
- prototype: `__int64 __fastcall(JDictsFilterDictionary *this, const struct _ChunkDescriptorType *, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180005ca4`
- `0x1800188e0`
- `0x1800199a4`
- `0x18001b550`
- `0x18001bbc0`
- `0x18001d338`
- `0x18001ea28`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall JDictsFilterDictionary::Initialize(
        JDictsFilterDictionary *this,
        const struct _ChunkDescriptorType *a2,
        unsigned int a3,
        int a4)
{
  int Instance; // ebx
  __int64 v9; // rdx
  unsigned int v11; // ebp
  unsigned __int64 v12; // r8
  __int64 v13; // r10
  unsigned __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rcx
  const struct _ChunkDescriptorType *v17; // r12
  struct IJDictsIndexer **v18; // rdi
  __int64 v19; // rcx
  struct IJDictsIndexer *v20; // rcx
  struct IJDictsIndexedData **v21; // rbx
  __int64 v22; // rcx
  struct IJDictsIndexedData *v23; // rcx
  JDictsLogicalDictionaryBase *v24; // rcx
  int v25; // esi
  struct IJDictsIndexer **v26; // rdi
  __int64 v27; // rcx
  struct IJDictsIndexer *v28; // rcx
  struct IJDictsIndexedData **v29; // rbx
  __int64 v30; // rcx
  struct IJDictsIndexedData *v31; // rcx
  JDictsLogicalDictionaryBase *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  unsigned int v35; // ebp
  __int64 v36; // rdx
  __int64 v37; // r12
  struct IJDictsIndexer **v38; // r14
  __int64 v39; // rcx
  struct IJDictsIndexedData **v40; // rsi
  __int64 v41; // rcx
  JDictsLogicalDictionaryBase *v42; // rcx
  int v43; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Instance = (*(__int64 (__fastcall **)(JDictsFilterDictionary *))(*(_QWORD *)this + 32LL))(this);
  if ( Instance < 0 )
  {
    v9 = 91;
    goto LABEL_3;
  }
  if ( a3 < 3 )
    return 2147500037LL;
  v11 = 0;
  v12 = 0xDA6EA39BA8435C9DuLL;
  v13 = DicType_FilterDWORDIDX;
  v14 = 0xF7F40544B2372288uLL;
  v15 = DicType_FilterWordIDX;
  do
  {
    v16 = 540LL * v11;
    v17 = (const struct _ChunkDescriptorType *)((char *)a2 + v16);
    if ( v13 == *(_QWORD *)((char *)a2 + v16 + 524) && *(_QWORD *)((char *)a2 + v16 + 532) == 0xDA6EA39BA8435C9DuLL )
    {
      v18 = (struct IJDictsIndexer **)((char *)this + 192);
      v19 = *((_QWORD *)this + 24);
      if ( v19 )
      {
        *v18 = 0;
        (*(void (__fastcall **)(__int64, unsigned __int64, unsigned __int64, __int64))(*(_QWORD *)v19 + 16LL))(
          v19,
          0xF7F40544B2372288uLL,
          0xDA6EA39BA8435C9DuLL,
          v15);
      }
      v20 = *v18;
      if ( *v18 )
      {
        *v18 = 0;
        (*(void (__fastcall **)(struct IJDictsIndexer *, unsigned __int64, unsigned __int64, __int64))(*(_QWORD *)v20 + 16LL))(
          v20,
          v14,
          v12,
          v15);
      }
      Instance = JDictsIndexerSatori::CreateInstance((struct IJDictsIndexer **)this + 24);
      if ( Instance < 0 )
      {
        v9 = 104;
        goto LABEL_3;
      }
      v21 = (struct IJDictsIndexedData **)((char *)this + 176);
      v22 = *((_QWORD *)this + 22);
      if ( v22 )
      {
        *v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      v23 = *v21;
      if ( *v21 )
      {
        *v21 = 0;
        (*(void (__fastcall **)(struct IJDictsIndexedData *))(*(_QWORD *)v23 + 16LL))(v23);
      }
      v25 = JDictsDataForDWORD::CreateInstance((struct IJDictsDataForDWORD **)this + 22);
      if ( v25 < 0 )
      {
        v34 = 107;
LABEL_39:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsfilterdictionary.cpp",
          (const char *)(unsigned int)v25,
          v43);
        return (unsigned int)v25;
      }
      Instance = JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(v24, v17, *v21, *v18, a4);
      if ( Instance < 0 )
      {
        v9 = 109;
        goto LABEL_3;
      }
LABEL_34:
      v15 = DicType_FilterWordIDX;
      v14 = 0xF7F40544B2372288uLL;
      v13 = DicType_FilterDWORDIDX;
      v12 = 0xDA6EA39BA8435C9DuLL;
      goto LABEL_35;
    }
    if ( v15 == *(_QWORD *)((char *)a2 + v16 + 524) && *(_QWORD *)((char *)a2 + v16 + 532) == 0xF7F40544B2372288uLL )
    {
      v26 = (struct IJDictsIndexer **)((char *)this + 200);
      v27 = *((_QWORD *)this + 25);
      if ( v27 )
      {
        *v26 = 0;
        (*(void (__fastcall **)(__int64, unsigned __int64, unsigned __int64))(*(_QWORD *)v27 + 16LL))(
          v27,
          0xF7F40544B2372288uLL,
          0xDA6EA39BA8435C9DuLL);
      }
      v28 = *v26;
      if ( *v26 )
      {
        *v26 = 0;
        (*(void (__fastcall **)(struct IJDictsIndexer *, unsigned __int64, unsigned __int64))(*(_QWORD *)v28 + 16LL))(
          v28,
          v14,
          v12);
      }
      Instance = JDictsIndexerSatori::CreateInstance((struct IJDictsIndexer **)this + 25);
      if ( Instance < 0 )
      {
        v9 = 115;
        goto LABEL_3;
      }
      v29 = (struct IJDictsIndexedData **)((char *)this + 184);
      v30 = *((_QWORD *)this + 23);
      if ( v30 )
      {
        *v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = *v29;
      if ( *v29 )
      {
        *v29 = 0;
        (*(void (__fastcall **)(struct IJDictsIndexedData *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v25 = JDictsDataBlocksForString::CreateInstance((struct IJDictsDataBlocksForString **)this + 23);
      if ( v25 < 0 )
      {
        v34 = 118;
        goto LABEL_39;
      }
      Instance = JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(v32, v17, *v29, *v26, a4);
      if ( Instance < 0 )
      {
        v9 = 120;
        goto LABEL_3;
      }
      goto LABEL_34;
    }
LABEL_35:
    ++v11;
  }
  while ( v11 < a3 );
  Instance = JDictsHeader::Terminate((JDictsFilterDictionary *)((char *)this + 8));
  if ( Instance < 0 )
  {
    v33 = 38;
    goto LABEL_60;
  }
  v35 = 0;
  v36 = DictType_Header;
  while ( 2 )
  {
    v37 = 540LL * v35;
    if ( v36 != *(_QWORD *)((char *)a2 + v37 + 524) || *(_QWORD *)((char *)a2 + v37 + 532) != 0xFE19B531B766728BuLL )
    {
LABEL_55:
      if ( ++v35 >= a3 )
      {
        *((_DWORD *)this + 5) = a4 == 0;
        *((_DWORD *)this + 10) = 1;
        *((_DWORD *)this + 11) = a4 == 0;
        return 0;
      }
      continue;
    }
    break;
  }
  v38 = (struct IJDictsIndexer **)((char *)this + 24);
  v39 = *((_QWORD *)this + 3);
  if ( v39 )
  {
    *v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  Instance = JDictsIndexerSatori::CreateInstance((struct IJDictsIndexer **)this + 3);
  if ( Instance >= 0 )
  {
    v40 = (struct IJDictsIndexedData **)((char *)this + 32);
    v41 = *((_QWORD *)this + 4);
    if ( v41 )
    {
      *v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    Instance = JDictsDataForDWORD::CreateInstance((struct IJDictsDataForDWORD **)this + 4);
    if ( Instance < 0 )
    {
      v33 = 46;
      goto LABEL_60;
    }
    Instance = JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(
                 v42,
                 (const struct _ChunkDescriptorType *)((char *)a2 + v37),
                 *v40,
                 *v38,
                 a4);
    if ( Instance < 0 )
    {
      v33 = 47;
      goto LABEL_60;
    }
    *((_DWORD *)this + 4) = 1;
    v36 = DictType_Header;
    goto LABEL_55;
  }
  v33 = 45;
LABEL_60:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v33,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsheader.cpp",
    (const char *)(unsigned int)Instance,
    v43);
  v9 = 124;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsfilterdictionary.cpp",
    (const char *)(unsigned int)Instance,
    v43);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800188e0  mov     [rsp+arg_8], rbx
0x1800188e5  mov     [rsp+arg_18], r9d
0x1800188ea  mov     [rsp+arg_10], r8d
0x1800188ef  push    rbp
0x1800188f0  push    rsi
0x1800188f1  push    rdi
0x1800188f2  push    r12
0x1800188f4  push    r13
0x1800188f6  push    r14
0x1800188f8  push    r15
0x1800188fa  sub     rsp, 30h
0x1800188fe  mov     r14d, r9d
0x180018901  mov     ebp, r8d
0x180018904  mov     r13, rdx
0x180018907  mov     r15, rcx
0x18001890a  mov     rax, [rcx]
0x18001890d  mov     rax, [rax+20h]
0x180018911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018916  mov     ebx, eax
0x180018918  xor     esi, esi
0x18001891a  test    eax, eax
0x18001891c  jns     short loc_18001893C
0x18001891e  lea     edx, [rsi+5Bh]; void *
0x180018921  lea     r8, aMincoreTextinp_22; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180018928  mov     r9d, ebx; char *
0x18001892b  mov     rcx, [rsp+68h]; this
0x180018930  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018935  mov     eax, ebx
0x180018937  jmp     loc_180018CA8
0x18001893c  cmp     ebp, 3
0x18001893f  jnb     short loc_18001894B
0x180018941  mov     eax, 80004005h
0x180018946  jmp     loc_180018CA8
0x18001894b  mov     ebp, esi
0x18001894d  mov     r8, cs:qword_180028F60
0x180018954  mov     r10, cs:DicType_FilterDWORDIDX
0x18001895b  mov     rdx, cs:qword_180028F50
0x180018962  mov     r9, cs:DicType_FilterWordIDX
0x180018969  mov     eax, ebp
0x18001896b  imul    rcx, rax, 21Ch
0x180018972  lea     r12, [rcx+r13]
0x180018976  cmp     r10, [rcx+r13+20Ch]
0x18001897e  jnz     loc_180018A4B
0x180018984  cmp     r8, [rcx+r13+214h]
0x18001898c  jnz     loc_180018A4B
0x180018992  lea     rdi, [r15+0C0h]
0x180018999  mov     rcx, [rdi]
0x18001899c  test    rcx, rcx
0x18001899f  jz      short loc_1800189B1
0x1800189a1  mov     [rdi], rsi
0x1800189a4  mov     rax, [rcx]
0x1800189a7  mov     rax, [rax+10h]
0x1800189ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b0  nop
0x1800189b1  mov     rcx, [rdi]
0x1800189b4  test    rcx, rcx
0x1800189b7  jz      short loc_1800189C9
0x1800189b9  mov     [rdi], rsi
0x1800189bc  mov     rax, [rcx]
0x1800189bf  mov     rax, [rax+10h]
0x1800189c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c8  nop
0x1800189c9  mov     rcx, rdi; struct IJDictsIndexer **
0x1800189cc  call    ?CreateInstance@JDictsIndexerSatori@@SAJPEAPEAUIJDictsIndexer@@@Z; JDictsIndexerSatori::CreateInstance(IJDictsIndexer * *)
0x1800189d1  mov     ebx, eax
0x1800189d3  test    eax, eax
0x1800189d5  js      loc_180018B7D
0x1800189db  lea     rbx, [r15+0B0h]
0x1800189e2  mov     rcx, [rbx]
0x1800189e5  test    rcx, rcx
0x1800189e8  jz      short loc_1800189FA
0x1800189ea  mov     [rbx], rsi
0x1800189ed  mov     rax, [rcx]
0x1800189f0  mov     rax, [rax+10h]
0x1800189f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189f9  nop
0x1800189fa  mov     rcx, [rbx]
0x1800189fd  test    rcx, rcx
0x180018a00  jz      short loc_180018A12
0x180018a02  mov     [rbx], rsi
0x180018a05  mov     rax, [rcx]
0x180018a08  mov     rax, [rax+10h]
0x180018a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a11  nop
0x180018a12  mov     rcx, rbx; struct IJDictsDataForDWORD **
0x180018a15  call    ?CreateInstance@JDictsDataForDWORD@@SAJPEAPEAUIJDictsDataForDWORD@@@Z; JDictsDataForDWORD::CreateInstance(IJDictsDataForDWORD * *)
0x180018a1a  mov     esi, eax
0x180018a1c  test    eax, eax
0x180018a1e  js      loc_180018B5D
0x180018a24  mov     [rsp+68h+var_48], r14d; int
0x180018a29  mov     r9, [rdi]; struct IJDictsIndexer *
0x180018a2c  mov     r8, [rbx]; struct IJDictsIndexedData *
0x180018a2f  mov     rdx, r12; struct _ChunkDescriptorType *
0x180018a32  call    ?InitializeIndexedDataAndIndexer@JDictsLogicalDictionaryBase@@IEAAJAEBU_ChunkDescriptorType@@PEAUIJDictsIndexedData@@PEAUIJDictsIndexer@@H@Z; JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(_ChunkDescriptorType const &,IJDictsIndexedData *,IJDictsIndexer *,int)
0x180018a37  mov     ebx, eax
0x180018a39  xor     esi, esi
0x180018a3b  test    eax, eax
0x180018a3d  jns     loc_180018B14
0x180018a43  lea     edx, [rsi+6Dh]
0x180018a46  jmp     loc_180018921
0x180018a4b  cmp     r9, [rcx+r13+20Ch]
0x180018a53  jnz     loc_180018B30
0x180018a59  cmp     rdx, [rcx+r13+214h]
0x180018a61  jnz     loc_180018B30
0x180018a67  lea     rdi, [r15+0C8h]
0x180018a6e  mov     rcx, [rdi]
0x180018a71  test    rcx, rcx
0x180018a74  jz      short loc_180018A86
0x180018a76  mov     [rdi], rsi
0x180018a79  mov     rax, [rcx]
0x180018a7c  mov     rax, [rax+10h]
0x180018a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a85  nop
0x180018a86  mov     rcx, [rdi]
0x180018a89  test    rcx, rcx
0x180018a8c  jz      short loc_180018A9E
0x180018a8e  mov     [rdi], rsi
0x180018a91  mov     rax, [rcx]
0x180018a94  mov     rax, [rax+10h]
0x180018a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a9d  nop
0x180018a9e  mov     rcx, rdi; struct IJDictsIndexer **
0x180018aa1  call    ?CreateInstance@JDictsIndexerSatori@@SAJPEAPEAUIJDictsIndexer@@@Z; JDictsIndexerSatori::CreateInstance(IJDictsIndexer * *)
0x180018aa6  mov     ebx, eax
0x180018aa8  test    eax, eax
0x180018aaa  js      loc_180018B98
0x180018ab0  lea     rbx, [r15+0B8h]
0x180018ab7  mov     rcx, [rbx]
0x180018aba  test    rcx, rcx
0x180018abd  jz      short loc_180018ACF
0x180018abf  mov     [rbx], rsi
0x180018ac2  mov     rax, [rcx]
0x180018ac5  mov     rax, [rax+10h]
0x180018ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ace  nop
0x180018acf  mov     rcx, [rbx]
0x180018ad2  test    rcx, rcx
0x180018ad5  jz      short loc_180018AE7
0x180018ad7  mov     [rbx], rsi
0x180018ada  mov     rax, [rcx]
0x180018add  mov     rax, [rax+10h]
0x180018ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae6  nop
0x180018ae7  mov     rcx, rbx; struct IJDictsDataBlocksForString **
0x180018aea  call    ?CreateInstance@JDictsDataBlocksForString@@SAJPEAPEAUIJDictsDataBlocksForString@@@Z; JDictsDataBlocksForString::CreateInstance(IJDictsDataBlocksForString * *)
0x180018aef  mov     esi, eax
0x180018af1  test    eax, eax
0x180018af3  js      loc_180018B91
0x180018af9  mov     [rsp+68h+var_48], r14d; int
0x180018afe  mov     r9, [rdi]; struct IJDictsIndexer *
0x180018b01  mov     r8, [rbx]; struct IJDictsIndexedData *
0x180018b04  mov     rdx, r12; struct _ChunkDescriptorType *
0x180018b07  call    ?InitializeIndexedDataAndIndexer@JDictsLogicalDictionaryBase@@IEAAJAEBU_ChunkDescriptorType@@PEAUIJDictsIndexedData@@PEAUIJDictsIndexer@@H@Z; JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(_ChunkDescriptorType const &,IJDictsIndexedData *,IJDictsIndexer *,int)
0x180018b0c  mov     ebx, eax
0x180018b0e  xor     esi, esi
0x180018b10  test    eax, eax
0x180018b12  js      short loc_180018B87
0x180018b14  mov     r9, cs:DicType_FilterWordIDX
0x180018b1b  mov     rdx, cs:qword_180028F50
0x180018b22  mov     r10, cs:DicType_FilterDWORDIDX
0x180018b29  mov     r8, cs:qword_180028F60
0x180018b30  inc     ebp
0x180018b32  cmp     ebp, [rsp+68h+arg_10]
0x180018b39  jb      loc_180018969
0x180018b3f  mov     rax, [rsp+68h]
0x180018b44  lea     rcx, [r15+8]; this
0x180018b48  call    ?Terminate@JDictsHeader@@QEAAJXZ; JDictsHeader::Terminate(void)
0x180018b4d  mov     ebx, eax
0x180018b4f  test    eax, eax
0x180018b51  jns     short loc_180018BA2
0x180018b53  mov     edx, 26h ; '&'
0x180018b58  jmp     loc_180018CD0
0x180018b5d  mov     edx, 6Bh ; 'k'; void *
0x180018b62  lea     r8, aMincoreTextinp_22; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180018b69  mov     r9d, esi; char *
0x180018b6c  mov     rcx, [rsp+68h]; this
0x180018b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b76  mov     eax, esi
0x180018b78  jmp     loc_180018CA8
0x180018b7d  mov     edx, 68h ; 'h'
0x180018b82  jmp     loc_180018921
0x180018b87  mov     edx, 78h ; 'x'
0x180018b8c  jmp     loc_180018921
0x180018b91  mov     edx, 76h ; 'v'
0x180018b96  jmp     short loc_180018B62
0x180018b98  mov     edx, 73h ; 's'
0x180018b9d  jmp     loc_180018921
0x180018ba2  mov     ebp, esi
0x180018ba4  mov     rcx, cs:qword_180028FA0
0x180018bab  mov     rdx, cs:DictType_Header
0x180018bb2  mov     eax, ebp
0x180018bb4  imul    r12, rax, 21Ch
0x180018bbb  cmp     rdx, [r12+r13+20Ch]
0x180018bc3  jnz     loc_180018C6F
0x180018bc9  cmp     rcx, [r12+r13+214h]
0x180018bd1  jnz     loc_180018C6F
0x180018bd7  lea     r14, [r15+18h]
0x180018bdb  mov     rcx, [r14]
0x180018bde  test    rcx, rcx
0x180018be1  jz      short loc_180018BF3
0x180018be3  mov     [r14], rsi
0x180018be6  mov     rax, [rcx]
0x180018be9  mov     rax, [rax+10h]
0x180018bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bf2  nop
0x180018bf3  mov     rcx, r14; struct IJDictsIndexer **
0x180018bf6  call    ?CreateInstance@JDictsIndexerSatori@@SAJPEAPEAUIJDictsIndexer@@@Z; JDictsIndexerSatori::CreateInstance(IJDictsIndexer * *)
0x180018bfb  mov     ebx, eax
0x180018bfd  test    eax, eax
0x180018bff  js      loc_180018CCB
0x180018c05  lea     rsi, [r15+20h]
0x180018c09  mov     rcx, [rsi]
0x180018c0c  test    rcx, rcx
0x180018c0f  jz      short loc_180018C25
0x180018c11  mov     qword ptr [rsi], 0
0x180018c18  mov     rax, [rcx]
0x180018c1b  mov     rax, [rax+10h]
0x180018c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c24  nop
0x180018c25  mov     rcx, rsi; struct IJDictsDataForDWORD **
0x180018c28  call    ?CreateInstance@JDictsDataForDWORD@@SAJPEAPEAUIJDictsDataForDWORD@@@Z; JDictsDataForDWORD::CreateInstance(IJDictsDataForDWORD * *)
0x180018c2d  mov     ebx, eax
0x180018c2f  test    eax, eax
0x180018c31  js      loc_180018CC4
0x180018c37  lea     rdx, [r12+r13]; struct _ChunkDescriptorType *
0x180018c3b  mov     eax, [rsp+68h+arg_18]
0x180018c42  mov     [rsp+68h+var_48], eax; int
0x180018c46  mov     r9, [r14]; struct IJDictsIndexer *
0x180018c49  mov     r8, [rsi]; struct IJDictsIndexedData *
0x180018c4c  call    ?InitializeIndexedDataAndIndexer@JDictsLogicalDictionaryBase@@IEAAJAEBU_ChunkDescriptorType@@PEAUIJDictsIndexedData@@PEAUIJDictsIndexer@@H@Z; JDictsLogicalDictionaryBase::InitializeIndexedDataAndIndexer(_ChunkDescriptorType const &,IJDictsIndexedData *,IJDictsIndexer *,int)
0x180018c51  mov     ebx, eax
0x180018c53  xor     esi, esi
0x180018c55  test    eax, eax
0x180018c57  js      short loc_180018CBD
0x180018c59  mov     dword ptr [r15+10h], 1
0x180018c61  mov     rcx, cs:qword_180028FA0
0x180018c68  mov     rdx, cs:DictType_Header
0x180018c6f  inc     ebp
0x180018c71  cmp     ebp, [rsp+68h+arg_10]
0x180018c78  jb      loc_180018BB2
0x180018c7e  mov     eax, esi
0x180018c80  mov     r14d, [rsp+68h+arg_18]
0x180018c88  test    r14d, r14d
0x180018c8b  setz    al
0x180018c8e  mov     [r15+14h], eax
0x180018c92  mov     dword ptr [r15+28h], 1
0x180018c9a  mov     eax, esi
0x180018c9c  test    r14d, r14d
0x180018c9f  setz    al
0x180018ca2  mov     [r15+2Ch], eax
0x180018ca6  xor     eax, eax
0x180018ca8  mov     rbx, [rsp+68h+arg_8]
0x180018cad  add     rsp, 30h
0x180018cb1  pop     r15
0x180018cb3  pop     r14
0x180018cb5  pop     r13
0x180018cb7  pop     r12
0x180018cb9  pop     rdi
0x180018cba  pop     rsi
0x180018cbb  pop     rbp
0x180018cbc  retn
0x180018cbd  mov     edx, 2Fh ; '/'
0x180018cc2  jmp     short loc_180018CD0
0x180018cc4  mov     edx, 2Eh ; '.'
0x180018cc9  jmp     short loc_180018CD0
0x180018ccb  mov     edx, 2Dh ; '-'; void *
0x180018cd0  mov     r9d, ebx; char *
0x180018cd3  lea     r8, aMincoreTextinp_1; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180018cda  mov     rcx, [rsp+68h]; this
0x180018cdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ce4  mov     edx, 7Ch ; '|'
0x180018ce9  jmp     loc_180018921
```
