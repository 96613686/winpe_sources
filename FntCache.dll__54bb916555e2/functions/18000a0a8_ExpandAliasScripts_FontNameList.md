# ExpandAliasScripts(FontNameList &)

- ea: `0x18000a0a8`
- end: `0x18000a67d`
- name: `?ExpandAliasScripts@@YAXAEAVFontNameList@@@Z`
- size: `1493`
- prototype: `void __fastcall(struct FontNameList *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009d78`

## callees

- `0x180008a20`
- `0x180009c0c`
- `0x180009ccc`
- `0x18000a0a8`
- `0x18000a704`
- `0x18000a7d4`
- `0x18000ac30`
- `0x18000ac60`
- `0x18000aca0`
- `0x18000ace4`
- `0x18000bcc4`
- `0x180028c50`
- `0x18004d664`
- `0x18009d96c`
- `0x18009df80`
- `0x18009e420`
- `0x1800aa650`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a657`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a657`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a2bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a5b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a2bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a5b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall ExpandAliasScripts(struct FontNameList *a1)
{
  int v2; // r15d
  const WCHAR *v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rdi
  struct FontNameList *v6; // r14
  unsigned __int64 v7; // rsi
  unsigned int v8; // r12d
  wchar_t ***v9; // r13
  unsigned __int64 v10; // r9
  __int64 v11; // r15
  void ***v12; // r14
  wchar_t ***v13; // rbx
  wchar_t ***v14; // rdi
  const WCHAR *i; // r8
  unsigned __int64 v16; // rdx
  int v17; // eax
  const WCHAR *v18; // r14
  struct DWrite::RefString::Data *v19; // r13
  struct DWrite::RefString::Data *v20; // r12
  struct DWrite::RefString::Data *v21; // rsi
  int v22; // eax
  struct DWrite::RefString::Data *v23; // rsi
  _QWORD *v24; // rax
  struct DWrite::RefString::Data **v25; // r14
  struct DWrite::RefString::Data **j; // rdi
  struct DWrite::RefString::Data *v27; // r15
  _QWORD *lower; // rax
  __int64 v29; // rcx
  __int128 v30; // xmm6
  __int64 v31; // r8
  struct DWrite::RefString::Data *v32; // rbx
  _QWORD *v33; // rax
  __int64 v34; // rax
  void **v35; // rsi
  struct DWrite::RefString::Data **v36; // r14
  struct DWrite::RefString::Data *v37; // rdi
  struct DWrite::RefString::Data *v38; // rbx
  struct DWrite::RefString::Data **k; // rbx
  void **v40; // rax
  __int64 v41; // rax
  struct DWrite::RefString::Data *v42; // [rsp+38h] [rbp-89h] BYREF
  __int64 v43; // [rsp+40h] [rbp-81h]
  struct DWrite::RefString::Data *v44[2]; // [rsp+48h] [rbp-79h] BYREF
  struct DWrite::RefString::Data **v45; // [rsp+58h] [rbp-69h] BYREF
  __int64 v46; // [rsp+60h] [rbp-61h]
  struct FontNameList *v47; // [rsp+68h] [rbp-59h]
  struct DWrite::RefString::Data *v48; // [rsp+78h] [rbp-49h] BYREF
  int v49; // [rsp+80h] [rbp-41h]
  int v50; // [rsp+84h] [rbp-3Dh]
  __int64 v51; // [rsp+88h] [rbp-39h] BYREF
  int v52; // [rsp+94h] [rbp-2Dh]
  _BYTE v53[32]; // [rsp+A0h] [rbp-21h] BYREF

  v47 = a1;
  std::wstring::wstring(v53);
  v2 = 0;
  v42 = 0;
  v43 = 0;
  std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Alloc_sentinel_and_proxy(&v42);
  v4 = *(_QWORD *)a1;
  v5 = *((_QWORD *)a1 + 1);
  while ( v4 != v5 )
  {
    v18 = (const WCHAR *)(*(_QWORD *)(v4 + 32) + 8LL);
    v19 = v42;
    v20 = (struct DWrite::RefString::Data *)*((_QWORD *)v42 + 1);
    v44[0] = 0;
    v21 = v20;
    for ( i = 0; !*((_BYTE *)v21 + 25); v21 = *(struct DWrite::RefString::Data **)v21 )
    {
      v20 = v21;
      v3 = (const WCHAR *)*((_QWORD *)v21 + 4);
      v10 = -1;
      do
        ++v10;
      while ( v18[v10] );
      v16 = -1;
      do
        ++v16;
      while ( v3[v16] );
      if ( v3 )
      {
        if ( !v18 )
          goto LABEL_37;
        if ( v10 > 0x7FFFFFFF || v16 > 0x7FFFFFFF )
LABEL_84:
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(v3, v16, i, v10);
        v22 = CompareStringOrdinal(v3, v16, v18, v10, 1);
        i = 0;
        if ( v22 - 2 >= 0 )
        {
LABEL_37:
          v2 = 1;
          v19 = v21;
          continue;
        }
      }
      else if ( !v18 )
      {
        goto LABEL_37;
      }
      v2 = 0;
      v21 = (struct DWrite::RefString::Data *)((char *)v21 + 16);
    }
    if ( *((_BYTE *)v19 + 25)
      || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v3, v18, *((_QWORD *)v19 + 4)) )
    {
      if ( v43 == 0x666666666666666LL )
LABEL_80:
        std::_Xlength_error("map/set too long");
      v23 = v42;
      v45 = &v42;
      v46 = 0;
      v24 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
      v24[4] = v18;
      *v24 = v23;
      v24[1] = v23;
      v24[2] = v23;
      *((_WORD *)v24 + 12) = 0;
      v46 = 0;
      v48 = v20;
      v49 = v2;
      v50 = (int)v44[0];
      std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,unsigned int>>>::_Insert_node(
        &v42,
        &v48,
        v24);
    }
    v4 += 40;
    v2 = 0;
  }
  v6 = v47;
  v7 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v47 + 1) - *(_QWORD *)v47) >> 3);
  v8 = 0;
  v9 = &off_18013B050;
  v10 = 2;
  if ( !(_DWORD)v7 )
    goto LABEL_46;
  while ( 2 )
  {
    v11 = *(_QWORD *)v6;
    if ( v8 >= 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v6 + 1) - *(_QWORD *)v6) >> 3) )
    {
      FailAssert(0x35u, (const char *)0xCCCCCCCCCCCCCCCDLL);
      __debugbreak();
    }
    v3 = (const WCHAR *)(5LL * v8);
    v44[0] = (struct DWrite::RefString::Data *)v3;
    v12 = &OSException `RTTI Type Descriptor';
    v13 = &off_18013B050;
    while ( v13 < (wchar_t ***)v12 )
    {
      v14 = &v13[2 * ((((char *)v12 - (char *)v13) >> 4) / 2)];
      i = **v14;
      v10 = -1;
      do
        ++v10;
      while ( i[v10] );
      v16 = *(_QWORD *)(v11 + 8LL * (_QWORD)v3 + 32);
      v3 = (const WCHAR *)(v16 + 8);
      if ( v16 == -8 )
      {
        if ( !i )
        {
LABEL_38:
          v25 = (struct DWrite::RefString::Data **)v14[1];
          for ( j = (struct DWrite::RefString::Data **)(*v14 + 1); j != v25; ++j )
          {
            v27 = *j;
            v44[0] = *j;
            lower = std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(
                      (__int64)&v42,
                      &v51,
                      (const WCHAR **)v44);
            v30 = *(_OWORD *)lower;
            v31 = lower[2];
            if ( *(_BYTE *)(v31 + 25)
              || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v29, v27, *(_QWORD *)(v31 + 32)) )
            {
              if ( v43 == 0x666666666666666LL )
                goto LABEL_80;
              v32 = v42;
              v45 = &v42;
              v46 = 0;
              v33 = std::_Allocate<16,std::_Default_allocate_traits>(0x28u);
              v33[4] = v27;
              *v33 = v32;
              v33[1] = v32;
              v33[2] = v32;
              *((_WORD *)v33 + 12) = 0;
              v46 = 0;
              *(_OWORD *)v44 = v30;
              std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,unsigned int>>>::_Insert_node(
                &v42,
                v44,
                v33);
              v34 = DWrite::RefString::RefString((DWrite::RefString *)&v48, (const wchar_t *)v27);
              FontNameList::AppendItem(v47, v53, v34);
              DWrite::RefString::DecrementRef(v48);
            }
          }
          v10 = 2;
          break;
        }
LABEL_14:
        v12 = (void ***)&v13[2 * ((((char *)v12 - (char *)v13) >> 4) / 2)];
        goto LABEL_15;
      }
      if ( i )
      {
        if ( v10 > 0x7FFFFFFF )
          goto LABEL_84;
        v16 = *(unsigned int *)(v16 + 4);
        if ( (unsigned int)v16 > 0x7FFFFFFF )
          goto LABEL_84;
        v17 = CompareStringOrdinal(v3, v16, i, v10, 1) - 2;
        if ( v17 < 0 )
          goto LABEL_14;
        if ( v17 <= 0 )
          goto LABEL_38;
      }
      v13 = v14 + 2;
LABEL_15:
      v3 = (const WCHAR *)v44[0];
      v10 = 2;
    }
    if ( ++v8 < (unsigned int)v7 )
    {
      v6 = v47;
      continue;
    }
    break;
  }
LABEL_46:
  while ( 2 )
  {
    v35 = (void **)*v9;
    v36 = (struct DWrite::RefString::Data **)v9[1];
    if ( (unsigned __int64)(((char *)v36 - (char *)*v9) >> 3) <= 2 )
      goto LABEL_47;
    v37 = v42;
    v38 = (struct DWrite::RefString::Data *)*((_QWORD *)v42 + 1);
    v52 = 0;
    while ( 2 )
    {
      if ( !*((_BYTE *)v38 + 25) )
      {
        i = (const WCHAR *)*v35;
        v3 = (const WCHAR *)*((_QWORD *)v38 + 4);
        v10 = -1;
        do
          ++v10;
        while ( i[v10] );
        v16 = -1;
        do
          ++v16;
        while ( v3[v16] );
        if ( v3 )
        {
          if ( !i )
            goto LABEL_69;
          if ( v10 > 0x7FFFFFFF || v16 > 0x7FFFFFFF )
            goto LABEL_84;
          if ( CompareStringOrdinal(v3, v16, i, v10, 1) - 2 >= 0 )
            goto LABEL_69;
        }
        else if ( !i )
        {
LABEL_69:
          v37 = v38;
          goto LABEL_51;
        }
        v38 = (struct DWrite::RefString::Data *)((char *)v38 + 16);
LABEL_51:
        v38 = *(struct DWrite::RefString::Data **)v38;
        continue;
      }
      break;
    }
    if ( *((_BYTE *)v37 + 25)
      || (unsigned __int8)FontNameList::StringLessThanIgnoreCase::operator()(v3, *v35, *((_QWORD *)v37 + 4)) )
    {
      v37 = v42;
    }
    if ( v37 == v42 )
    {
      for ( k = (struct DWrite::RefString::Data **)(v35 + 1); k != v36; ++k )
      {
        v48 = *k;
        v40 = (void **)std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::find(
                         &v42,
                         &v45,
                         &v48,
                         v10);
        v3 = (const WCHAR *)v42;
        if ( *v40 == v42 )
          goto LABEL_71;
      }
      v41 = DWrite::RefString::RefString((DWrite::RefString *)v44, (const wchar_t *)*v35);
      FontNameList::AppendItem(v47, v53, v41);
      DWrite::RefString::DecrementRef(v44[0]);
    }
LABEL_71:
    v10 = 2;
LABEL_47:
    v9 += 2;
    if ( v9 != (wchar_t ***)&OSException `RTTI Type Descriptor' )
      continue;
    break;
  }
  std::_Tree_val<std::_Tree_simple_types<wchar_t const *>>::_Erase_tree<std::allocator<std::_Tree_node<wchar_t const *,void *>>>(
    &v42,
    &v42,
    *((_QWORD *)v42 + 1),
    2);
  std::_Deallocate<16>(v42, 0x28u);
  std::wstring::_Tidy_deallocate(v53);
}

```

## disassembly

```asm
0x18000a0a8  mov     rax, rsp
0x18000a0ab  push    rbp
0x18000a0ac  push    rbx
0x18000a0ad  push    rsi
0x18000a0ae  push    rdi
0x18000a0af  push    r12
0x18000a0b1  push    r13
0x18000a0b3  push    r14
0x18000a0b5  push    r15
0x18000a0b7  lea     rbp, [rax-5Fh]
0x18000a0bb  sub     rsp, 0D8h
0x18000a0c2  movaps  xmmword ptr [rax-58h], xmm6
0x18000a0c6  mov     rax, cs:__security_cookie
0x18000a0cd  xor     rax, rsp
0x18000a0d0  mov     qword ptr [rbp+57h+var_58], rax
0x18000a0d4  mov     r14, rcx
0x18000a0d7  mov     [rbp+57h+var_B0], rcx
0x18000a0db  lea     rcx, [rbp+57h+var_78]; void *
0x18000a0df  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000a0e4  nop
0x18000a0e5  xor     r15d, r15d
0x18000a0e8  mov     [rsp+110h+var_E0], r15
0x18000a0ed  mov     [rsp+110h+var_D8], r15
0x18000a0f2  lea     rcx, [rsp+110h+var_E0]
0x18000a0f7  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tset_traits@VRefString@DWrite@@U?$less@VRefString@DWrite@@@std@@V?$allocator@VRefString@DWrite@@@4@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tset_traits<DWrite::RefString,std::less<DWrite::RefString>,std::allocator<DWrite::RefString>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000a0fc  nop
0x18000a0fd  mov     rbx, [r14]
0x18000a100  mov     rdi, [r14+8]
0x18000a104  cmp     rbx, rdi
0x18000a107  jnz     loc_18000A23D
0x18000a10d  mov     r14, [rbp+57h+var_B0]
0x18000a111  mov     rsi, [r14+8]
0x18000a115  sub     rsi, [r14]
0x18000a118  sar     rsi, 3
0x18000a11c  mov     rdx, 0CCCCCCCCCCCCCCCDh; char *
0x18000a126  imul    rsi, rdx
0x18000a12a  mov     r12d, r15d
0x18000a12d  lea     r8, ??_R0?AVOSException@@@8; OSException `RTTI Type Descriptor'
0x18000a134  lea     r13, off_18013B050
0x18000a13b  mov     r9d, 2
0x18000a141  test    esi, esi
0x18000a143  jz      loc_18000A475
0x18000a149  mov     r15, [r14]
0x18000a14c  mov     ecx, r12d
0x18000a14f  mov     rax, [r14+8]
0x18000a153  sub     rax, r15
0x18000a156  sar     rax, 3
0x18000a15a  imul    rax, rdx
0x18000a15e  cmp     rcx, rax
0x18000a161  jnb     loc_18000A65E
0x18000a167  lea     rcx, [rcx+rcx*4]
0x18000a16b  mov     [rbp+57h+var_D0], rcx
0x18000a16f  mov     r14, r8
0x18000a172  mov     rbx, r13
0x18000a175  cmp     rbx, r14
0x18000a178  jnb     loc_18000A217
0x18000a17e  mov     rax, r14
0x18000a181  sub     rax, rbx
0x18000a184  sar     rax, 4
0x18000a188  cqo
0x18000a18a  idiv    r9
0x18000a18d  add     rax, rax
0x18000a190  lea     rdi, [rbx+rax*8]
0x18000a194  mov     rax, [rdi]
0x18000a197  mov     r8, [rax]; lpString2
0x18000a19a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a19e  xor     r10d, r10d
0x18000a1a1  inc     r9; cchCount2
0x18000a1a4  cmp     [r8+r9*2], r10w
0x18000a1a9  jnz     short loc_18000A1A1
0x18000a1ab  mov     rdx, [r15+rcx*8+20h]
0x18000a1b0  lea     rcx, [rdx+8]; lpString1
0x18000a1b4  test    rcx, rcx
0x18000a1b7  jz      loc_18000A642
0x18000a1bd  test    r8, r8
0x18000a1c0  jz      short loc_18000A20B
0x18000a1c2  cmp     r9, 7FFFFFFFh
0x18000a1c9  ja      loc_18000A677
0x18000a1cf  mov     edx, [rdx+4]; cchCount1
0x18000a1d2  cmp     edx, 7FFFFFFFh
0x18000a1d8  ja      loc_18000A677
0x18000a1de  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18000a1e6  call    cs:__imp_CompareStringOrdinal
0x18000a1ec  add     eax, 0FFFFFFFEh
0x18000a1ef  jns     short loc_18000A203
0x18000a1f1  mov     r14, rdi
0x18000a1f4  mov     rcx, [rbp+57h+var_D0]
0x18000a1f8  mov     r9d, 2
0x18000a1fe  jmp     loc_18000A175
0x18000a203  test    eax, eax
0x18000a205  jle     loc_18000A373
0x18000a20b  lea     rbx, [rdi+10h]
0x18000a20f  jmp     short loc_18000A1F4
0x18000a211  mov     r9d, 2
0x18000a217  inc     r12d
0x18000a21a  lea     r8, ??_R0?AVOSException@@@8; OSException `RTTI Type Descriptor'
0x18000a221  cmp     r12d, esi
0x18000a224  jnb     loc_18000A472
0x18000a22a  mov     r14, [rbp+57h+var_B0]
0x18000a22e  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18000a238  jmp     loc_18000A149
0x18000a23d  mov     r14, [rbx+20h]
0x18000a241  add     r14, 8
0x18000a245  mov     r13, [rsp+110h+var_E0]
0x18000a24a  mov     r12, [r13+8]
0x18000a24e  xor     eax, eax
0x18000a250  mov     [rbp+57h+var_D0], rax
0x18000a254  mov     rsi, r12
0x18000a257  xor     r8d, r8d
0x18000a25a  cmp     [r12+19h], r8b
0x18000a25f  jnz     short loc_18000A2DD
0x18000a261  mov     r12, rsi
0x18000a264  mov     rcx, [rsi+20h]; lpString1
0x18000a268  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000a26c  inc     r9; cchCount2
0x18000a26f  cmp     [r14+r9*2], r8w
0x18000a274  jnz     short loc_18000A26C
0x18000a276  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a27a  inc     rdx; cchCount1
0x18000a27d  cmp     [rcx+rdx*2], r8w
0x18000a282  jnz     short loc_18000A27A
0x18000a284  test    rcx, rcx
0x18000a287  jz      loc_18000A634
0x18000a28d  test    r14, r14
0x18000a290  jz      loc_18000A365
0x18000a296  cmp     r9, 7FFFFFFFh
0x18000a29d  ja      loc_18000A677
0x18000a2a3  cmp     rdx, 7FFFFFFFh
0x18000a2aa  ja      loc_18000A677
0x18000a2b0  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18000a2b8  mov     r8, r14; lpString2
0x18000a2bb  call    cs:__imp_CompareStringOrdinal
0x18000a2c1  xor     r8d, r8d
0x18000a2c4  add     eax, 0FFFFFFFEh
0x18000a2c7  jns     loc_18000A365
0x18000a2cd  mov     r15d, r8d
0x18000a2d0  add     rsi, 10h
0x18000a2d4  mov     rsi, [rsi]
0x18000a2d7  cmp     [rsi+19h], r8b
0x18000a2db  jz      short loc_18000A261
0x18000a2dd  cmp     [r13+19h], r8b
0x18000a2e1  jz      loc_18000A456
0x18000a2e7  mov     rax, 666666666666666h
0x18000a2f1  cmp     [rsp+110h+var_D8], rax
0x18000a2f6  jz      loc_18000A650
0x18000a2fc  mov     rsi, [rsp+110h+var_E0]
0x18000a301  lea     rax, [rsp+110h+var_E0]
0x18000a306  mov     [rbp+57h+var_C0], rax
0x18000a30a  mov     [rbp+57h+var_B8], r8
0x18000a30e  mov     [rbp+57h+var_B8], r8
0x18000a312  mov     ecx, 28h ; '('
0x18000a317  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a31c  mov     [rbp+57h+var_B8], rax
0x18000a320  mov     [rax+20h], r14
0x18000a324  mov     [rax], rsi
0x18000a327  mov     [rax+8], rsi
0x18000a32b  mov     [rax+10h], rsi
0x18000a32f  xor     ecx, ecx
0x18000a331  mov     [rax+18h], cx
0x18000a335  mov     [rbp+57h+var_B8], rcx
0x18000a339  mov     [rbp+57h+var_A0], r12
0x18000a33d  mov     [rbp+57h+var_98], r15d
0x18000a341  mov     rcx, [rbp+57h+var_D0]
0x18000a345  mov     [rbp+57h+var_94], ecx
0x18000a348  mov     r8, rax
0x18000a34b  lea     rdx, [rbp+57h+var_A0]
0x18000a34f  lea     rcx, [rsp+110h+var_E0]
0x18000a354  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$BasedStringPtr@VFontStringsRegion@@I@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> *>,std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> * const)
0x18000a359  add     rbx, 28h ; '('
0x18000a35d  xor     r15d, r15d
0x18000a360  jmp     loc_18000A104
0x18000a365  mov     r15d, 1
0x18000a36b  mov     r13, rsi
0x18000a36e  jmp     loc_18000A2D4
0x18000a373  mov     r14, [rdi+8]
0x18000a377  mov     rdi, [rdi]
0x18000a37a  add     rdi, 8
0x18000a37e  cmp     rdi, r14
0x18000a381  jz      loc_18000A211
0x18000a387  xor     ebx, ebx
0x18000a389  mov     r15, [rdi]
0x18000a38c  mov     [rbp+57h+var_D0], r15
0x18000a390  lea     r8, [rbp+57h+var_D0]
0x18000a394  lea     rdx, [rbp+57h+var_90]
0x18000a398  lea     rcx, [rsp+110h+var_E0]
0x18000a39d  call    ??$_Find_lower_bound@PEB_W@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEB_WPEAX@std@@@1@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::_Find_lower_bound<wchar_t const *>(wchar_t const * const &)
0x18000a3a2  movups  xmm6, xmmword ptr [rax]
0x18000a3a5  mov     r8, [rax+10h]
0x18000a3a9  cmp     [r8+19h], bl
0x18000a3ad  jz      loc_18000A61B
0x18000a3b3  mov     rax, 666666666666666h
0x18000a3bd  cmp     [rsp+110h+var_D8], rax
0x18000a3c2  jz      loc_18000A650
0x18000a3c8  mov     rbx, [rsp+110h+var_E0]
0x18000a3cd  lea     rax, [rsp+110h+var_E0]
0x18000a3d2  mov     [rbp+57h+var_C0], rax
0x18000a3d6  xor     ecx, ecx
0x18000a3d8  mov     [rbp+57h+var_B8], rcx
0x18000a3dc  mov     [rbp+57h+var_B8], rcx
0x18000a3e0  mov     ecx, 28h ; '('
0x18000a3e5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a3ea  mov     [rbp+57h+var_B8], rax
0x18000a3ee  mov     [rax+20h], r15
0x18000a3f2  mov     [rax], rbx
0x18000a3f5  mov     [rax+8], rbx
0x18000a3f9  mov     [rax+10h], rbx
0x18000a3fd  xor     ebx, ebx
0x18000a3ff  mov     [rax+18h], bx
0x18000a403  mov     [rbp+57h+var_B8], rbx
0x18000a407  movdqu  xmmword ptr [rbp+57h+var_D0], xmm6
0x18000a40c  mov     r8, rax
0x18000a40f  lea     rdx, [rbp+57h+var_D0]
0x18000a413  lea     rcx, [rsp+110h+var_E0]
0x18000a418  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@V?$BasedStringPtr@VFontStringsRegion@@I@@@std@@@std@@QEAAPEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@V?$BasedStringPtr@VFontStringsRegion@@I@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<BasedStringPtr<FontStringsRegion,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> *>,std::_Tree_node<BasedStringPtr<FontStringsRegion,uint>,void *> * const)
0x18000a41d  mov     rdx, r15; wchar_t *
0x18000a420  lea     rcx, [rbp+57h+var_A0]; this
0x18000a424  call    ??0RefString@DWrite@@QEAA@PEB_W@Z; DWrite::RefString::RefString(wchar_t const *)
0x18000a429  nop
0x18000a42a  mov     r8, rax
0x18000a42d  lea     rdx, [rbp+57h+var_78]
0x18000a431  mov     rcx, [rbp+57h+var_B0]
0x18000a435  call    ?AppendItem@FontNameList@@QEAAXAEBV?$GenericLanguageTag@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@@AEBVRefString@DWrite@@@Z; FontNameList::AppendItem(GenericLanguageTag<std::wstring> const &,DWrite::RefString const &)
0x18000a43a  nop
0x18000a43b  mov     rcx, [rbp+57h+var_A0]; struct DWrite::RefString::Data *
0x18000a43f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18000a444  add     rdi, 8
0x18000a448  cmp     rdi, r14
0x18000a44b  jnz     loc_18000A389
0x18000a451  jmp     loc_18000A211
0x18000a456  mov     r8, [r13+20h]
0x18000a45a  mov     rdx, r14
0x18000a45d  call    ??RStringLessThanIgnoreCase@FontNameList@@QEBA_NPEB_W0@Z; FontNameList::StringLessThanIgnoreCase::operator()(wchar_t const *,wchar_t const *)
0x18000a462  xor     r8d, r8d
0x18000a465  test    al, al
0x18000a467  jnz     loc_18000A2E7
0x18000a46d  jmp     loc_18000A359
0x18000a472  xor     r15d, r15d
0x18000a475  mov     rsi, [r13+0]
0x18000a479  mov     r14, [r13+8]
0x18000a47d  mov     rax, r14
0x18000a480  sub     rax, rsi
0x18000a483  sar     rax, 3
0x18000a487  cmp     rax, r9
0x18000a48a  ja      short loc_18000A4EE
0x18000a48c  add     r13, 10h
0x18000a490  cmp     r13, r8
0x18000a493  jnz     short loc_18000A475
0x18000a495  mov     r8, [rsp+110h+var_E0]
0x18000a49a  mov     r8, [r8+8]
0x18000a49e  lea     rdx, [rsp+110h+var_E0]
0x18000a4a3  lea     rcx, [rsp+110h+var_E0]
0x18000a4a8  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@PEB_WPEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@PEB_W@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@PEB_WPEAX@std@@@1@PEAU?$_Tree_node@PEB_WPEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<wchar_t const *>>::_Erase_tree<std::allocator<std::_Tree_node<wchar_t const *,void *>>>(std::allocator<std::_Tree_node<wchar_t const *,void *>> &,std::_Tree_node<wchar_t const *,void *> *)
0x18000a4ad  mov     edx, 28h ; '('
0x18000a4b2  mov     rcx, [rsp+110h+var_E0]
0x18000a4b7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a4bc  nop
0x18000a4bd  lea     rcx, [rbp+57h+var_78]; void *
0x18000a4c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a4c6  mov     rcx, qword ptr [rbp+57h+var_58]
0x18000a4ca  xor     rcx, rsp; StackCookie
0x18000a4cd  call    __security_check_cookie
0x18000a4d2  movaps  xmm6, [rsp+110h+var_58+8]
0x18000a4da  add     rsp, 0D8h
0x18000a4e1  pop     r15
0x18000a4e3  pop     r14
0x18000a4e5  pop     r13
0x18000a4e7  pop     r12
0x18000a4e9  pop     rdi
0x18000a4ea  pop     rsi
0x18000a4eb  pop     rbx
0x18000a4ec  pop     rbp
0x18000a4ed  retn
0x18000a4ee  mov     rdi, [rsp+110h+var_E0]
0x18000a4f3  mov     rbx, [rdi+8]
0x18000a4f7  xor     eax, eax
0x18000a4f9  mov     [rbp+57h+var_84], eax
0x18000a4fc  jmp     short loc_18000A505
0x18000a4fe  add     rbx, 10h
0x18000a502  mov     rbx, [rbx]
0x18000a505  cmp     [rbx+19h], r15b
0x18000a509  jz      short loc_18000A55F
0x18000a50b  cmp     [rdi+19h], r15b
0x18000a50f  jz      loc_18000A602
0x18000a515  mov     rdi, [rsp+110h+var_E0]
0x18000a51a  cmp     rdi, [rsp+110h+var_E0]
0x18000a51f  jnz     loc_18000A5F0
0x18000a525  lea     rbx, [rsi+8]
0x18000a529  cmp     rbx, r14
0x18000a52c  jz      loc_18000A5C9
0x18000a532  mov     rax, [rbx]
0x18000a535  mov     [rbp+57h+var_A0], rax
0x18000a539  lea     r8, [rbp+57h+var_A0]
0x18000a53d  lea     rdx, [rbp+57h+var_C0]
0x18000a541  lea     rcx, [rsp+110h+var_E0]
0x18000a546  call    ?find@?$_Tree@V?$_Tset_traits@PEB_WUStringLessThanIgnoreCase@FontNameList@@V?$allocator@PEB_W@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEB_W@std@@@std@@@2@AEBQEB_W@Z; std::_Tree<std::_Tset_traits<wchar_t const *,FontNameList::StringLessThanIgnoreCase,std::allocator<wchar_t const *>,0>>::find(wchar_t const * const &)
0x18000a54b  mov     rcx, [rsp+110h+var_E0]
0x18000a550  cmp     [rax], rcx
0x18000a553  jz      loc_18000A5F0
0x18000a559  add     rbx, 8
0x18000a55d  jmp     short loc_18000A529
  ... truncated ...
```
