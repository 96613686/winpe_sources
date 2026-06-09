# std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___

- ea: `0x18000fe3c`
- end: `0x1800102f3`
- name: `std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___`
- size: `1207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x18000fe3c`
- `0x1800104e4`

## callees

- `0x18000ef28`
- `0x18000f82c`
- `0x18000fc38`
- `0x18000fe3c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800100c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001011f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010165`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010200`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010238`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010284`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102cf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800100c2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001011f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010165`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010200`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010238`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010284`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102cf`

## pseudocode

```c
void __fastcall std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        FilterAgent **a1,
        FilterAgent **a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl
  __int64 v6; // rax
  FilterAgent **v7; // rbp
  FilterAgent **v8; // rdi
  FilterAgent **v9; // rsi
  FilterAgent **v10; // r14
  FilterAgent *v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int8 v14; // r8
  __int64 v15; // rax
  unsigned __int8 v16; // dl
  __int64 v17; // rcx
  FilterAgent **v18; // r9
  FilterAgent **v19; // r10
  unsigned __int8 v20; // dl
  __int64 v21; // rcx
  FilterAgent **v22; // rcx
  FilterAgent *v23; // rax
  bool v24; // zf
  unsigned __int8 v25; // dl
  FilterAgent **v26; // rcx
  FilterAgent *v27; // r8
  __int64 v28; // rax
  FilterAgent *v29; // rax
  FilterAgent *v30; // rcx
  FilterAgent **v31; // r8
  FilterAgent **v32; // rdx
  FilterAgent *v33; // rcx
  FilterAgent *v34; // rcx
  FilterAgent *v35; // rcx
  __int64 v36; // rsi
  __int64 v37; // r14
  FilterAgent *v38; // r15
  FilterAgent **v39; // r14
  FilterAgent **v40; // rbp
  FilterAgent *v41; // r15
  FilterAgent *v42; // rsi
  FilterAgent *v43; // rsi
  FilterAgent **i; // rsi
  FilterAgent *v45; // rbx
  FilterAgent **v46; // r14
  FilterAgent **v47; // r15
  FilterAgent *v48; // r13
  FilterAgent *v49; // r12
  FilterAgent *v50; // r14
  FilterAgent **j; // r15
  FilterAgent *v52; // r13
  FilterAgent *v53; // r12
  FilterAgent *v54; // r15
  __int64 v55; // [rsp+20h] [rbp-68h]
  _BYTE v56[88]; // [rsp+30h] [rbp-58h] BYREF
  FilterAgent *v57; // [rsp+90h] [rbp+8h] BYREF

  v4 = a4;
  v6 = a2 - a1;
  v7 = a2;
  v8 = a1;
  if ( v6 <= 32 )
    goto LABEL_58;
  do
  {
    if ( a3 <= 0 )
      break;
    LOBYTE(a4) = v4;
    v9 = &v8[(v7 - v8) / 2];
    std::_Median_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_______lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
      v8,
      v9,
      v7 - 1,
      a4);
    v10 = v9 + 1;
    if ( v8 < v9 )
    {
      v11 = *v9;
      do
      {
        v12 = *((_QWORD *)v11 + 2);
        v13 = (unsigned __int64)(v9 - 1);
        v11 = *(v9 - 1);
        v14 = *(_BYTE *)(v12 + 8);
        v15 = *((_QWORD *)v11 + 2);
        if ( *(_BYTE *)(v15 + 8) < v14 )
          break;
        if ( *(_BYTE *)(v15 + 8) > v14 )
          break;
        --v9;
      }
      while ( (unsigned __int64)v8 < v13 );
    }
    if ( v10 < v7 )
    {
      v16 = *(_BYTE *)(*((_QWORD *)*v9 + 2) + 8LL);
      do
      {
        v17 = *((_QWORD *)*v10 + 2);
        if ( *(_BYTE *)(v17 + 8) < v16 )
          break;
        if ( *(_BYTE *)(v17 + 8) > v16 )
          break;
        ++v10;
      }
      while ( v10 < v7 );
    }
    v18 = v10;
    v19 = v9;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( v18 < v7 )
        {
          v20 = *(_BYTE *)(*((_QWORD *)*v18 + 2) + 8LL);
          v21 = *((_QWORD *)*v9 + 2);
          if ( *(_BYTE *)(v21 + 8) >= v20 )
          {
            if ( *(_BYTE *)(v21 + 8) > v20 )
              break;
            v22 = v10++;
            v23 = *v22;
            *v22 = *v18;
            *v18 = v23;
          }
          ++v18;
        }
        v24 = v19 == v8;
        if ( v19 > v8 )
        {
          do
          {
            v25 = *(_BYTE *)(*((_QWORD *)*v9 + 2) + 8LL);
            v26 = v19 - 1;
            v27 = *(v19 - 1);
            v28 = *((_QWORD *)v27 + 2);
            if ( *(_BYTE *)(v28 + 8) >= v25 )
            {
              if ( *(_BYTE *)(v28 + 8) > v25 )
                break;
              v29 = *--v9;
              *v9 = v27;
              *v26 = v29;
            }
            --v19;
          }
          while ( v8 < v26 );
          v24 = v19 == v8;
        }
        if ( v24 )
          break;
        v31 = --v19;
        if ( v18 != v7 )
        {
          v32 = v18++;
          goto LABEL_35;
        }
        if ( v31 != --v9 )
        {
          v33 = *v31;
          *v31 = *v9;
          *v9 = v33;
        }
        v34 = *v9;
        *v9 = *--v10;
        *v10 = v34;
      }
      if ( v18 == v7 )
        break;
      if ( v10 != v18 )
      {
        v30 = *v9;
        *v9 = *v10;
        *v10 = v30;
      }
      v31 = v18;
      ++v10;
      ++v18;
      v32 = v9++;
LABEL_35:
      v35 = *v32;
      *v32 = *v31;
      *v31 = v35;
    }
    LOBYTE(v18) = v4;
    a3 = a3 / 2 / 2 + a3 / 2;
    if ( (__int64)(((char *)v9 - (char *)v8) & 0xFFFFFFFFFFFFFFF8uLL) >= (__int64)(((char *)v7 - (char *)v10)
                                                                                 & 0xFFFFFFFFFFFFFFF8uLL) )
    {
      std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        v10,
        v7,
        a3,
        v18,
        v55);
      v7 = v9;
    }
    else
    {
      std::_Sort_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        v8,
        v9,
        a3,
        v18,
        v55);
      v8 = v10;
    }
    v6 = v7 - v8;
  }
  while ( v6 > 32 );
  if ( v6 <= 32 )
  {
LABEL_58:
    if ( v6 <= 1 || v8 == v7 )
      return;
    for ( i = v8 + 1; ; ++i )
    {
      if ( i == v7 )
        return;
      v45 = *i;
      v46 = i;
      *i = 0;
      if ( *(_BYTE *)(*((_QWORD *)v45 + 2) + 8LL) < *(_BYTE *)(*((_QWORD *)*v8 + 2) + 8LL) )
        break;
      for ( j = i; ; v46 = j )
      {
        v52 = *--j;
        if ( *(_BYTE *)(*((_QWORD *)v45 + 2) + 8LL) >= *(_BYTE *)(*((_QWORD *)*j + 2) + 8LL) )
          break;
        if ( v46 != j )
        {
          *j = 0;
          v53 = *v46;
          if ( v52 != *v46 )
          {
            if ( v53 )
            {
              FilterAgent::~FilterAgent(*v46);
              operator delete(v53);
            }
            *v46 = v52;
          }
        }
      }
      if ( v46 == (FilterAgent **)v56 )
        goto LABEL_87;
      v54 = *v46;
      if ( v45 != *v46 )
      {
        if ( v54 )
        {
          FilterAgent::~FilterAgent(*v46);
          operator delete(v54);
        }
        *v46 = v45;
      }
LABEL_89:
      ;
    }
    v47 = i + 1;
    if ( i != v8 )
    {
      do
      {
        if ( --v47 != --v46 )
        {
          v48 = *v46;
          *v46 = 0;
          v49 = *v47;
          if ( v48 != *v47 )
          {
            if ( v49 )
            {
              FilterAgent::~FilterAgent(*v47);
              operator delete(v49);
            }
            *v47 = v48;
          }
        }
      }
      while ( v46 != v8 );
    }
    if ( v8 != (FilterAgent **)v56 )
    {
      v50 = *v8;
      if ( v45 != *v8 )
      {
        if ( v50 )
        {
          FilterAgent::~FilterAgent(*v8);
          operator delete(v50);
        }
        *v8 = v45;
      }
      goto LABEL_89;
    }
LABEL_87:
    if ( v45 )
    {
      FilterAgent::~FilterAgent(v45);
      operator delete(v45);
    }
    goto LABEL_89;
  }
  v36 = v7 - v8;
  if ( v36 <= 1 || (v37 = v36 / 2, v36 / 2 <= 0) )
  {
    v39 = v7;
    if ( v36 > 1 )
      goto LABEL_48;
  }
  else
  {
    do
    {
      --v37;
      LOBYTE(v55) = v4;
      v57 = v8[v37];
      v8[v37] = 0;
      std::_Adjust_heap_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        v8,
        v37,
        v7 - v8,
        &v57,
        v55);
      v38 = v57;
      if ( v57 )
      {
        FilterAgent::~FilterAgent(v57);
        operator delete(v38);
      }
    }
    while ( v37 > 0 );
    v39 = v7;
LABEL_48:
    v40 = v7 - 1;
    do
    {
      v57 = *v40;
      *v40 = 0;
      if ( v40 != v8 )
      {
        v41 = *v8;
        *v8 = 0;
        v42 = *v40;
        if ( v41 != *v40 )
        {
          if ( v42 )
          {
            FilterAgent::~FilterAgent(*v40);
            operator delete(v42);
          }
          *v40 = v41;
        }
      }
      LOBYTE(v55) = v4;
      std::_Adjust_heap_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent________int64_std::unique_ptr_FilterAgent_std::default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___(
        v8,
        0,
        ((char *)v39 - (char *)v8 - 8) >> 3,
        &v57,
        v55);
      v43 = v57;
      if ( v57 )
      {
        FilterAgent::~FilterAgent(v57);
        operator delete(v43);
      }
      --v39;
      --v40;
    }
    while ( (__int64)(((char *)v39 - (char *)v8) & 0xFFFFFFFFFFFFFFF8uLL) > 8 );
  }
}

```

## disassembly

```asm
0x18000fe3c  push    rbx
0x18000fe3e  push    rbp
0x18000fe3f  push    rsi
0x18000fe40  push    rdi
0x18000fe41  push    r12
0x18000fe43  push    r13
0x18000fe45  push    r14
0x18000fe47  push    r15
0x18000fe49  sub     rsp, 48h
0x18000fe4d  mov     rax, rdx
0x18000fe50  mov     bl, r9b
0x18000fe53  sub     rax, rcx
0x18000fe56  mov     r15, r8
0x18000fe59  sar     rax, 3
0x18000fe5d  mov     rbp, rdx
0x18000fe60  mov     rdi, rcx
0x18000fe63  cmp     rax, 20h ; ' '
0x18000fe67  jle     loc_18001018C
0x18000fe6d  test    r15, r15
0x18000fe70  jle     loc_18001004C
0x18000fe76  mov     rax, rbp
0x18000fe79  sub     rax, rdi
0x18000fe7c  sar     rax, 3
0x18000fe80  test    rax, rax
0x18000fe83  jns     short loc_18000FE88
0x18000fe85  inc     rax
0x18000fe88  sar     rax, 1
0x18000fe8b  lea     r8, [rbp-8]
0x18000fe8f  mov     r9b, bl
0x18000fe92  mov     rcx, rdi
0x18000fe95  lea     rsi, [rdi+rax*8]
0x18000fe99  mov     rdx, rsi
0x18000fe9c  call    std___Median_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent_______lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x18000fea1  lea     r14, [rsi+8]
0x18000fea5  cmp     rdi, rsi
0x18000fea8  jnb     short loc_18000FED0
0x18000feaa  mov     rcx, [rsi]
0x18000fead  mov     rax, [rcx+10h]
0x18000feb1  lea     rdx, [rsi-8]
0x18000feb5  mov     rcx, [rdx]
0x18000feb8  mov     r8b, [rax+8]
0x18000febc  mov     rax, [rcx+10h]
0x18000fec0  cmp     [rax+8], r8b
0x18000fec4  jb      short loc_18000FED0
0x18000fec6  ja      short loc_18000FED0
0x18000fec8  mov     rsi, rdx
0x18000fecb  cmp     rdi, rdx
0x18000fece  jb      short loc_18000FEAD
0x18000fed0  cmp     r14, rbp
0x18000fed3  jnb     short loc_18000FEF6
0x18000fed5  mov     rax, [rsi]
0x18000fed8  mov     rcx, [rax+10h]
0x18000fedc  mov     dl, [rcx+8]
0x18000fedf  mov     rax, [r14]
0x18000fee2  mov     rcx, [rax+10h]
0x18000fee6  cmp     [rcx+8], dl
0x18000fee9  jb      short loc_18000FEF6
0x18000feeb  ja      short loc_18000FEF6
0x18000feed  add     r14, 8
0x18000fef1  cmp     r14, rbp
0x18000fef4  jb      short loc_18000FEDF
0x18000fef6  mov     r9, r14
0x18000fef9  mov     r10, rsi
0x18000fefc  jmp     short loc_18000FF2A
0x18000fefe  mov     r8, [r9]
0x18000ff01  mov     rax, [r8+10h]
0x18000ff05  mov     dl, [rax+8]
0x18000ff08  mov     rax, [rsi]
0x18000ff0b  mov     rcx, [rax+10h]
0x18000ff0f  cmp     [rcx+8], dl
0x18000ff12  jb      short loc_18000FF26
0x18000ff14  ja      short loc_18000FF2F
0x18000ff16  mov     rcx, r14
0x18000ff19  add     r14, 8
0x18000ff1d  mov     rax, [rcx]
0x18000ff20  mov     [rcx], r8
0x18000ff23  mov     [r9], rax
0x18000ff26  add     r9, 8
0x18000ff2a  cmp     r9, rbp
0x18000ff2d  jb      short loc_18000FEFE
0x18000ff2f  cmp     r10, rdi
0x18000ff32  jbe     short loc_18000FF68
0x18000ff34  mov     rax, [rsi]
0x18000ff37  mov     rcx, [rax+10h]
0x18000ff3b  mov     dl, [rcx+8]
0x18000ff3e  lea     rcx, [r10-8]
0x18000ff42  mov     r8, [rcx]
0x18000ff45  mov     rax, [r8+10h]
0x18000ff49  cmp     [rax+8], dl
0x18000ff4c  jb      short loc_18000FF5D
0x18000ff4e  ja      short loc_18000FF65
0x18000ff50  sub     rsi, 8
0x18000ff54  mov     rax, [rsi]
0x18000ff57  mov     [rsi], r8
0x18000ff5a  mov     [rcx], rax
0x18000ff5d  mov     r10, rcx
0x18000ff60  cmp     rdi, rcx
0x18000ff63  jb      short loc_18000FF34
0x18000ff65  cmp     r10, rdi
0x18000ff68  jnz     short loc_18000FF94
0x18000ff6a  cmp     r9, rbp
0x18000ff6d  jz      short loc_18000FFE2
0x18000ff6f  cmp     r14, r9
0x18000ff72  jz      short loc_18000FF80
0x18000ff74  mov     rax, [r14]
0x18000ff77  mov     rcx, [rsi]
0x18000ff7a  mov     [rsi], rax
0x18000ff7d  mov     [r14], rcx
0x18000ff80  mov     r8, r9
0x18000ff83  add     r14, 8
0x18000ff87  add     r9, 8
0x18000ff8b  mov     rdx, rsi
0x18000ff8e  add     rsi, 8
0x18000ff92  jmp     short loc_18000FFD1
0x18000ff94  lea     r8, [r10-8]
0x18000ff98  mov     r10, r8
0x18000ff9b  cmp     r9, rbp
0x18000ff9e  jnz     short loc_18000FFCA
0x18000ffa0  sub     rsi, 8
0x18000ffa4  cmp     r8, rsi
0x18000ffa7  jz      short loc_18000FFB5
0x18000ffa9  mov     rax, [rsi]
0x18000ffac  mov     rcx, [r8]
0x18000ffaf  mov     [r8], rax
0x18000ffb2  mov     [rsi], rcx
0x18000ffb5  mov     rcx, [rsi]
0x18000ffb8  sub     r14, 8
0x18000ffbc  mov     rax, [r14]
0x18000ffbf  mov     [rsi], rax
0x18000ffc2  mov     [r14], rcx
0x18000ffc5  jmp     loc_18000FF2A
0x18000ffca  mov     rdx, r9
0x18000ffcd  add     r9, 8
0x18000ffd1  mov     rax, [r8]
0x18000ffd4  mov     rcx, [rdx]
0x18000ffd7  mov     [rdx], rax
0x18000ffda  mov     [r8], rcx
0x18000ffdd  jmp     loc_18000FF2A
0x18000ffe2  mov     rax, r15
0x18000ffe5  mov     rcx, rbp
0x18000ffe8  cqo
0x18000ffea  sub     rcx, r14
0x18000ffed  sub     rax, rdx
0x18000fff0  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18000fff4  sar     rax, 1
0x18000fff7  mov     r9b, bl
0x18000fffa  mov     r15, rax
0x18000fffd  cqo
0x18000ffff  sub     rax, rdx
0x180010002  sar     rax, 1
0x180010005  add     r15, rax
0x180010008  mov     rax, rsi
0x18001000b  sub     rax, rdi
0x18001000e  mov     r8, r15
0x180010011  and     rax, 0FFFFFFFFFFFFFFF8h
0x180010015  cmp     rax, rcx
0x180010018  jge     short loc_18001002A
0x18001001a  mov     rdx, rsi
0x18001001d  mov     rcx, rdi
0x180010020  call    std___Sort_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x180010025  mov     rdi, r14
0x180010028  jmp     short loc_180010038
0x18001002a  mov     rdx, rbp
0x18001002d  mov     rcx, r14
0x180010030  call    std___Sort_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64__lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x180010035  mov     rbp, rsi
0x180010038  mov     rax, rbp
0x18001003b  sub     rax, rdi
0x18001003e  sar     rax, 3
0x180010042  cmp     rax, 20h ; ' '
0x180010046  jg      loc_18000FE6D
0x18001004c  cmp     rax, 20h ; ' '
0x180010050  jle     loc_18001018C
0x180010056  mov     rsi, rbp
0x180010059  sub     rsi, rdi
0x18001005c  sar     rsi, 3
0x180010060  cmp     rsi, 1
0x180010064  jle     short loc_1800100D2
0x180010066  mov     rax, rsi
0x180010069  cqo
0x18001006b  sub     rax, rdx
0x18001006e  sar     rax, 1
0x180010071  mov     r14, rax
0x180010074  test    rax, rax
0x180010077  jle     short loc_1800100D2
0x180010079  dec     r14
0x18001007c  mov     [rsp+88h+var_68], bl
0x180010080  lea     r9, [rsp+88h+arg_0]
0x180010088  mov     r8, rsi
0x18001008b  mov     rdx, r14
0x18001008e  mov     rcx, [rdi+r14*8]
0x180010092  mov     [rsp+88h+arg_0], rcx
0x18001009a  mov     rcx, rdi
0x18001009d  mov     qword ptr [rdi+r14*8], 0
0x1800100a5  call    std___Adjust_heap_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x1800100aa  mov     r15, [rsp+88h+arg_0]
0x1800100b2  test    r15, r15
0x1800100b5  jz      short loc_1800100C8
0x1800100b7  mov     rcx, r15; this
0x1800100ba  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x1800100bf  mov     rcx, r15
0x1800100c2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800100c8  test    r14, r14
0x1800100cb  jg      short loc_180010079
0x1800100cd  mov     r14, rbp
0x1800100d0  jmp     short loc_1800100DF
0x1800100d2  mov     r14, rbp
0x1800100d5  cmp     rsi, 1
0x1800100d9  jle     loc_1800102E2
0x1800100df  add     rbp, 0FFFFFFFFFFFFFFF8h
0x1800100e3  mov     rax, [rbp+0]
0x1800100e7  mov     [rsp+88h+arg_0], rax
0x1800100ef  mov     qword ptr [rbp+0], 0
0x1800100f7  cmp     rbp, rdi
0x1800100fa  jz      short loc_180010129
0x1800100fc  mov     r15, [rdi]
0x1800100ff  mov     qword ptr [rdi], 0
0x180010106  mov     rsi, [rbp+0]
0x18001010a  cmp     r15, rsi
0x18001010d  jz      short loc_180010129
0x18001010f  test    rsi, rsi
0x180010112  jz      short loc_180010125
0x180010114  mov     rcx, rsi; this
0x180010117  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18001011c  mov     rcx, rsi
0x18001011f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010125  mov     [rbp+0], r15
0x180010129  mov     r8, r14
0x18001012c  mov     [rsp+88h+var_68], bl
0x180010130  sub     r8, rdi
0x180010133  lea     r9, [rsp+88h+arg_0]
0x18001013b  sub     r8, 8
0x18001013f  xor     edx, edx
0x180010141  sar     r8, 3
0x180010145  mov     rcx, rdi
0x180010148  call    std___Adjust_heap_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent________int64_std__unique_ptr_FilterAgent_std__default_delete_FilterAgent_____lambda_4e00c4f2fc8604fa547e688629cc8b0c___
0x18001014d  mov     rsi, [rsp+88h+arg_0]
0x180010155  test    rsi, rsi
0x180010158  jz      short loc_18001016B
0x18001015a  mov     rcx, rsi; this
0x18001015d  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x180010162  mov     rcx, rsi
0x180010165  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001016b  sub     r14, 8
0x18001016f  sub     rbp, 8
0x180010173  mov     rax, r14
0x180010176  sub     rax, rdi
0x180010179  and     rax, 0FFFFFFFFFFFFFFF8h
0x18001017d  cmp     rax, 8
0x180010181  jg      loc_1800100E3
0x180010187  jmp     loc_1800102E2
0x18001018c  cmp     rax, 1
0x180010190  jle     loc_1800102E2
0x180010196  cmp     rdi, rbp
0x180010199  jz      loc_1800102E2
0x18001019f  lea     rsi, [rdi+8]
0x1800101a3  jmp     loc_1800102D9
0x1800101a8  mov     rbx, [rsi]
0x1800101ab  mov     r14, rsi
0x1800101ae  mov     qword ptr [rsi], 0
0x1800101b5  mov     rax, [rdi]
0x1800101b8  mov     rcx, [rbx+10h]
0x1800101bc  mov     rax, [rax+10h]
0x1800101c0  mov     al, [rax+8]
0x1800101c3  cmp     [rcx+8], al
0x1800101c6  jnb     short loc_180010246
0x1800101c8  lea     r15, [rsi+8]
0x1800101cc  cmp     rsi, rdi
0x1800101cf  jz      short loc_18001020E
0x1800101d1  sub     r14, 8
0x1800101d5  sub     r15, 8
0x1800101d9  cmp     r15, r14
0x1800101dc  jz      short loc_180010209
0x1800101de  mov     r13, [r14]
0x1800101e1  mov     qword ptr [r14], 0
0x1800101e8  mov     r12, [r15]
0x1800101eb  cmp     r13, r12
0x1800101ee  jz      short loc_180010209
0x1800101f0  test    r12, r12
0x1800101f3  jz      short loc_180010206
0x1800101f5  mov     rcx, r12; this
0x1800101f8  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x1800101fd  mov     rcx, r12
0x180010200  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010206  mov     [r15], r13
0x180010209  cmp     r14, rdi
0x18001020c  jnz     short loc_1800101D1
0x18001020e  lea     rax, [rsp+88h+var_58]
0x180010213  cmp     rdi, rax
0x180010216  jz      loc_1800102BF
0x18001021c  mov     r14, [rdi]
0x18001021f  cmp     rbx, r14
0x180010222  jz      loc_1800102D5
0x180010228  test    r14, r14
0x18001022b  jz      short loc_18001023E
0x18001022d  mov     rcx, r14; this
0x180010230  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x180010235  mov     rcx, r14
0x180010238  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001023e  mov     [rdi], rbx
  ... truncated ...
```
