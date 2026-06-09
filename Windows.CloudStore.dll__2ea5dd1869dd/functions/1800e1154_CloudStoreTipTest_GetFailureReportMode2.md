# CloudStoreTipTest::GetFailureReportMode2

- ea: `0x1800e1154`
- end: `0x1800e156a`
- name: `CloudStoreTipTest::GetFailureReportMode2`
- size: `1046`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800438a4`
- `0x18008e164`
- `0x18009fbf4`
- `0x1800f5f78`
- `0x18010a170`
- `0x18010d024`
- `0x18011c5d0`
- `0x1801755e4`
- `0x180175970`

## callees

- `0x180025508`
- `0x180091700`
- `0x1800e1154`
- `0x180160154`
- `0x1801608ec`
- `0x180163ac4`
- `0x180163d44`
- `0x180173f24`
- `0x180175d2c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e125f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e1299`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e12c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e13d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e144e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e147e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e14a8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e125f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e1299`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e12c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e13d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e144e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e147e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e14a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CloudStoreTipTest::GetFailureReportMode2(__int64 a1)
{
  __int64 v2; // rbx
  _QWORD *v3; // rax
  int v4; // r15d
  char v5; // r13
  __int64 v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // r12d
  const WCHAR *v9; // rcx
  int v10; // esi
  _QWORD *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rcx
  int *i; // rcx
  const WCHAR *j; // rcx
  __int128 v17; // [rsp+30h] [rbp-99h] BYREF
  __int128 v18; // [rsp+40h] [rbp-89h]
  __int64 v19; // [rsp+50h] [rbp-79h]
  int v20; // [rsp+60h] [rbp-69h] BYREF
  _QWORD *v21; // [rsp+68h] [rbp-61h]
  __int64 v22; // [rsp+70h] [rbp-59h]
  __int64 v23; // [rsp+78h] [rbp-51h] BYREF
  __int128 v24; // [rsp+80h] [rbp-49h]
  __int64 v25; // [rsp+90h] [rbp-39h]
  __int64 v26; // [rsp+98h] [rbp-31h]
  _BYTE v27[8]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v28[16]; // [rsp+A8h] [rbp-21h] BYREF
  _BYTE v29[16]; // [rsp+B8h] [rbp-11h] BYREF
  _BYTE v30[88]; // [rsp+C8h] [rbp-1h] BYREF
  int v31; // [rsp+130h] [rbp+67h] BYREF
  __int64 v32; // [rsp+138h] [rbp+6Fh]
  char v33; // [rsp+140h] [rbp+77h] BYREF
  char v34; // [rsp+148h] [rbp+7Fh] BYREF

  v2 = *(_QWORD *)(a1 + 80);
  if ( !v2 )
    return 1;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v17);
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v3 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
  *v3 = v3;
  v3[1] = v3;
  v21 = v3;
  v23 = 0;
  v24 = 0;
  v25 = 7;
  v26 = 8;
  v20 = 1065353216;
  std::_Hash_vec_std::allocator_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState___________::_Assign_grow(
    &v23,
    16,
    v3);
  v4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 64);
  v7 = v6 + 168LL * *(_QWORD *)(a1 + 80);
  v32 = v7;
  v8 = 3;
  while ( v6 != v7 )
  {
    if ( *(_DWORD *)(v6 + 8) == -2147319765 )
      goto LABEL_48;
    v9 = *(const WCHAR **)(v6 + 24);
    v10 = 0;
    if ( v9 )
    {
      if ( CompareStringOrdinal(v9, -1, L"**!!##!!**NoLogTipIgnore", -1, 0) == 2 )
      {
        v31 = 2;
LABEL_8:
        --v2;
        std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_Emplace_back_internal_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_(
          &v17,
          &v31);
        goto LABEL_31;
      }
      if ( CompareStringOrdinal(*(LPCWCH *)(v6 + 24), -1, L"**!!##!!**NoLogTipForceWarn", -1, 0) == 2 )
      {
        v31 = 1;
        goto LABEL_8;
      }
      if ( CompareStringOrdinal(*(LPCWCH *)(v6 + 24), -1, L"**!!##!!**NoLogTipResume", -1, 0) == 2 )
      {
        --v2;
        if ( !--v19 )
          *((_QWORD *)&v18 + 1) = 0;
        goto LABEL_31;
      }
    }
    if ( v19 )
    {
      --v2;
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v17 + 1)
                                 + 8 * ((v18 - 1) & ((unsigned __int64)(v19 - 1 + *((_QWORD *)&v18 + 1)) >> 2)))
                     + 4 * ((v19 - 1 + *((_QWORD *)&v18 + 1)) & 3)) == 1 )
      {
        v31 = 1;
        std::unordered_map_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::hash_long__std::equal_to_long__std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_____::_Insert_or_assign_long_const___enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_(
          &v20,
          v28,
          v6 + 8,
          &v31);
LABEL_23:
        ++v4;
        goto LABEL_31;
      }
      if ( !v22
        || (v11 = (_QWORD *)std::_Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___::find(
                              &v20,
                              &v33,
                              v6 + 8),
            (_QWORD *)*v11 == v21) )
      {
        v31 = 0;
        std::unordered_map_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::hash_long__std::equal_to_long__std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_____::_Insert_or_assign_long_const___enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_(
          &v20,
          v29,
          v6 + 8,
          &v31);
      }
    }
    else
    {
      if ( v22 )
      {
        v12 = std::_Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___::find(
                &v20,
                &v34,
                v6 + 8);
        if ( *(_QWORD **)v12 != v21 )
        {
          --v2;
          if ( *(_DWORD *)(*(_QWORD *)v12 + 20LL) != 1 )
            goto LABEL_31;
          goto LABEL_23;
        }
      }
      v31 = 1;
      if ( CompareStringOrdinal(*(LPCWCH *)(v6 + 24), -1, L"**!!##!!**NoLogTipPass", -1, 0) == 2 )
      {
        v31 = 0;
LABEL_26:
        if ( !v22
          || (v13 = (_QWORD *)std::_Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___::find(
                                &v20,
                                v27,
                                v6 + 8),
              (_QWORD *)*v13 == v21) )
        {
          --v2;
          if ( v10 == 1 )
            ++v4;
          std::unordered_map_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::hash_long__std::equal_to_long__std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_____::_Insert_or_assign_long_const___enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_(
            &v20,
            v30,
            v6 + 8,
            &v31);
        }
        goto LABEL_31;
      }
      v10 = 1;
      if ( CompareStringOrdinal(*(LPCWCH *)(v6 + 24), -1, L"**!!##!!**NoLogTipAfcTimeout", -1, 0) == 2 )
      {
        v5 = 1;
        goto LABEL_26;
      }
      if ( CompareStringOrdinal(*(LPCWCH *)(v6 + 24), -1, L"**!!##!!**NoLogTipWarn", -1, 0) == 2
        || CompareStringOrdinal(*(LPCWCH *)(v6 + 24), 13, L"**!!##!!**Log", -1, 0) == 2 )
      {
        goto LABEL_26;
      }
      for ( i = (int *)qword_18023C230; i != &dword_18023C24C; ++i )
      {
        if ( (*(_WORD *)(v6 + 10) & 0x1FFF) == *i )
          goto LABEL_26;
      }
      for ( j = (const WCHAR *)qword_18023C250; j != L"**!!##!!**NoLogTipResume"; j += 2 )
      {
        if ( *(_DWORD *)(v6 + 8) == *(_DWORD *)j )
          goto LABEL_26;
      }
    }
LABEL_31:
    v6 += 168;
    v7 = v32;
  }
  if ( v2 )
  {
LABEL_49:
    std::_Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___::__Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___(&v20);
    std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___(&v17);
    return v8;
  }
  if ( v5 )
  {
    v8 = 0;
    goto LABEL_49;
  }
  if ( v4 )
  {
LABEL_48:
    v8 = 2;
    goto LABEL_49;
  }
  std::_Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___::__Hash_std::_Umap_traits_long_enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState_std::_Uhash_compare_long_std::hash_long__std::equal_to_long____std::allocator_std::pair_long_const__enum__CloudStoreTipTest::GetFailureReportMode2_::_2_::ObservedState____0___(&v20);
  std::deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___::_deque_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState_std::allocator_enum__CloudStoreTipTest::GetFailureReportMode_::_2_::ReportModeState___(&v17);
  return 1;
}

```

## disassembly

```asm
0x1800e1154  push    rbp
0x1800e1156  push    rbx
0x1800e1157  push    rsi
0x1800e1158  push    rdi
0x1800e1159  push    r12
0x1800e115b  push    r13
0x1800e115d  push    r14
0x1800e115f  push    r15
0x1800e1161  lea     rbp, [rsp-1Fh]
0x1800e1166  sub     rsp, 0E8h
0x1800e116d  mov     rsi, rcx
0x1800e1170  mov     rbx, [rcx+50h]
0x1800e1174  test    rbx, rbx
0x1800e1177  jz      loc_1800E1551
0x1800e117d  xorps   xmm0, xmm0
0x1800e1180  movdqu  [rsp+120h+var_F0], xmm0
0x1800e1186  xorps   xmm1, xmm1
0x1800e1189  movdqu  [rsp+120h+var_E0], xmm1
0x1800e118f  mov     [rbp+57h+var_D0], 0
0x1800e1197  lea     rcx, [rsp+120h+var_F0]
0x1800e119c  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x1800e11a1  nop
0x1800e11a2  mov     [rbp+57h+var_C0], 0
0x1800e11a9  mov     [rbp+57h+var_B8], 0
0x1800e11b1  mov     [rbp+57h+var_B0], 0
0x1800e11b9  mov     ecx, 18h
0x1800e11be  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800e11c3  mov     [rax], rax
0x1800e11c6  mov     [rax+8], rax
0x1800e11ca  mov     [rbp+57h+var_B8], rax
0x1800e11ce  mov     [rbp+57h+var_A8], 0
0x1800e11d6  xorps   xmm0, xmm0
0x1800e11d9  movdqa  [rbp+57h+var_A0], xmm0
0x1800e11de  mov     [rbp+57h+var_90], 7
0x1800e11e6  mov     [rbp+57h+var_88], 8
0x1800e11ee  mov     [rbp+57h+var_C0], 3F800000h
0x1800e11f5  mov     r8, rax
0x1800e11f8  mov     edx, 10h
0x1800e11fd  lea     rcx, [rbp+57h+var_A8]
0x1800e1201  call    std___Hash_vec_std__allocator_std___List_unchecked_iterator_std___List_val_std___List_simple_types_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState______________Assign_grow
0x1800e1206  nop
0x1800e1207  xor     r15d, r15d
0x1800e120a  xor     r13b, r13b
0x1800e120d  mov     rdi, [rsi+40h]
0x1800e1211  imul    rax, [rsi+50h], 0A8h
0x1800e1219  add     rax, rdi
0x1800e121c  mov     [rbp+57h+arg_8], rax
0x1800e1220  lea     r12d, [r15+3]
0x1800e1224  cmp     rdi, rax
0x1800e1227  jz      loc_1800E150A
0x1800e122d  lea     r14, [rdi+8]
0x1800e1231  cmp     dword ptr [r14], 8002802Bh
0x1800e1238  jz      loc_1800E151E
0x1800e123e  mov     rcx, [rdi+18h]; lpString1
0x1800e1242  xor     esi, esi
0x1800e1244  test    rcx, rcx
0x1800e1247  jz      loc_1800E12EE
0x1800e124d  mov     [rsp+120h+bIgnoreCase], esi; bIgnoreCase
0x1800e1251  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e1255  lea     r8, aNologtipignore; "**!!##!!**NoLogTipIgnore"
0x1800e125c  or      edx, r9d; cchCount1
0x1800e125f  call    cs:__imp_CompareStringOrdinal
0x1800e1265  cmp     eax, 2
0x1800e1268  jnz     short loc_1800E1283
0x1800e126a  mov     [rbp+57h+arg_0], eax
0x1800e126d  dec     rbx
0x1800e1270  lea     rdx, [rbp+57h+arg_0]
0x1800e1274  lea     rcx, [rsp+120h+var_F0]
0x1800e1279  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______Emplace_back_internal_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_
0x1800e127e  jmp     loc_1800E1427
0x1800e1283  mov     [rsp+120h+bIgnoreCase], esi; bIgnoreCase
0x1800e1287  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e128b  lea     r8, aNologtipforcew_0; "**!!##!!**NoLogTipForceWarn"
0x1800e1292  or      edx, r9d; cchCount1
0x1800e1295  mov     rcx, [rdi+18h]; lpString1
0x1800e1299  call    cs:__imp_CompareStringOrdinal
0x1800e129f  cmp     eax, 2
0x1800e12a2  jnz     short loc_1800E12AD
0x1800e12a4  mov     [rbp+57h+arg_0], 1
0x1800e12ab  jmp     short loc_1800E126D
0x1800e12ad  mov     [rsp+120h+bIgnoreCase], esi; bIgnoreCase
0x1800e12b1  or      eax, 0FFFFFFFFh
0x1800e12b4  mov     r9d, eax; cchCount2
0x1800e12b7  lea     r8, aNologtipresume; "**!!##!!**NoLogTipResume"
0x1800e12be  mov     edx, eax; cchCount1
0x1800e12c0  mov     rcx, [rdi+18h]; lpString1
0x1800e12c4  call    cs:__imp_CompareStringOrdinal
0x1800e12ca  cmp     eax, 2
0x1800e12cd  jnz     short loc_1800E12EE
0x1800e12cf  dec     rbx
0x1800e12d2  mov     rax, [rbp+57h+var_D0]
0x1800e12d6  sub     rax, 1
0x1800e12da  mov     [rbp+57h+var_D0], rax
0x1800e12de  jnz     loc_1800E1427
0x1800e12e4  mov     qword ptr [rsp+120h+var_E0+8], rsi
0x1800e12e9  jmp     loc_1800E1427
0x1800e12ee  mov     rcx, [rbp+57h+var_D0]
0x1800e12f2  test    rcx, rcx
0x1800e12f5  jz      loc_1800E138C
0x1800e12fb  dec     rbx
0x1800e12fe  mov     rdx, qword ptr [rsp+120h+var_E0+8]
0x1800e1303  dec     rcx
0x1800e1306  add     rdx, rcx
0x1800e1309  mov     rcx, rdx
0x1800e130c  shr     rcx, 2
0x1800e1310  mov     rax, qword ptr [rsp+120h+var_E0]
0x1800e1315  dec     rax
0x1800e1318  and     rcx, rax
0x1800e131b  and     rdx, r12
0x1800e131e  mov     rax, qword ptr [rsp+120h+var_F0+8]
0x1800e1323  mov     rcx, [rax+rcx*8]
0x1800e1327  cmp     dword ptr [rcx+rdx*4], 1
0x1800e132b  jnz     short loc_1800E134A
0x1800e132d  mov     [rbp+57h+arg_0], 1
0x1800e1334  lea     r9, [rbp+57h+arg_0]
0x1800e1338  mov     r8, r14
0x1800e133b  lea     rdx, [rbp+57h+var_78]
0x1800e133f  lea     rcx, [rbp+57h+var_C0]
0x1800e1343  call    std__unordered_map_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std__hash_long__std__equal_to_long__std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState________Insert_or_assign_long_const___enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_
0x1800e1348  jmp     short loc_1800E13B4
0x1800e134a  cmp     [rbp+57h+var_B0], rsi
0x1800e134e  jz      short loc_1800E1370
0x1800e1350  mov     r8, r14
0x1800e1353  lea     rdx, [rbp+57h+arg_10]
0x1800e1357  lea     rcx, [rbp+57h+var_C0]
0x1800e135b  call    std___Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0_____find
0x1800e1360  mov     rcx, rax
0x1800e1363  mov     rax, [rbp+57h+var_B8]
0x1800e1367  cmp     [rcx], rax
0x1800e136a  jnz     loc_1800E1427
0x1800e1370  mov     [rbp+57h+arg_0], esi
0x1800e1373  lea     r9, [rbp+57h+arg_0]
0x1800e1377  mov     r8, r14
0x1800e137a  lea     rdx, [rbp+57h+var_68]
0x1800e137e  lea     rcx, [rbp+57h+var_C0]
0x1800e1382  call    std__unordered_map_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std__hash_long__std__equal_to_long__std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState________Insert_or_assign_long_const___enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_
0x1800e1387  jmp     loc_1800E1427
0x1800e138c  cmp     [rbp+57h+var_B0], rsi
0x1800e1390  jbe     short loc_1800E13B9
0x1800e1392  mov     r8, r14
0x1800e1395  lea     rdx, [rbp+57h+arg_18]
0x1800e1399  lea     rcx, [rbp+57h+var_C0]
0x1800e139d  call    std___Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0_____find
0x1800e13a2  mov     rcx, [rax]
0x1800e13a5  cmp     rcx, [rbp+57h+var_B8]
0x1800e13a9  jz      short loc_1800E13B9
0x1800e13ab  dec     rbx
0x1800e13ae  cmp     dword ptr [rcx+14h], 1
0x1800e13b2  jnz     short loc_1800E1427
0x1800e13b4  inc     r15d
0x1800e13b7  jmp     short loc_1800E1427
0x1800e13b9  mov     [rbp+57h+arg_0], 1
0x1800e13c0  mov     [rsp+120h+bIgnoreCase], esi; bIgnoreCase
0x1800e13c4  or      eax, 0FFFFFFFFh
0x1800e13c7  mov     r9d, eax; cchCount2
0x1800e13ca  lea     r8, aNologtippass_0; "**!!##!!**NoLogTipPass"
0x1800e13d1  mov     edx, eax; cchCount1
0x1800e13d3  mov     rcx, [rdi+18h]; lpString1
0x1800e13d7  call    cs:__imp_CompareStringOrdinal
0x1800e13dd  cmp     eax, 2
0x1800e13e0  jnz     short loc_1800E1437
0x1800e13e2  mov     [rbp+57h+arg_0], esi
0x1800e13e5  cmp     [rbp+57h+var_B0], 0
0x1800e13ea  jz      short loc_1800E1408
0x1800e13ec  mov     r8, r14
0x1800e13ef  lea     rdx, [rbp+57h+var_80]
0x1800e13f3  lea     rcx, [rbp+57h+var_C0]
0x1800e13f7  call    std___Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0_____find
0x1800e13fc  mov     rcx, rax
0x1800e13ff  mov     rax, [rbp+57h+var_B8]
0x1800e1403  cmp     [rcx], rax
0x1800e1406  jnz     short loc_1800E1427
0x1800e1408  dec     rbx
0x1800e140b  cmp     esi, 1
0x1800e140e  jnz     short loc_1800E1413
0x1800e1410  inc     r15d
0x1800e1413  lea     r9, [rbp+57h+arg_0]
0x1800e1417  mov     r8, r14
0x1800e141a  lea     rdx, [rbp+57h+var_58]
0x1800e141e  lea     rcx, [rbp+57h+var_C0]
0x1800e1422  call    std__unordered_map_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std__hash_long__std__equal_to_long__std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState________Insert_or_assign_long_const___enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_
0x1800e1427  add     rdi, 0A8h
0x1800e142e  mov     rax, [rbp+57h+arg_8]
0x1800e1432  jmp     loc_1800E1224
0x1800e1437  mov     [rsp+120h+bIgnoreCase], esi; bIgnoreCase
0x1800e143b  or      eax, 0FFFFFFFFh
0x1800e143e  mov     r9d, eax; cchCount2
0x1800e1441  lea     r8, aNologtipafctim_2; "**!!##!!**NoLogTipAfcTimeout"
0x1800e1448  mov     edx, eax; cchCount1
0x1800e144a  mov     rcx, [rdi+18h]; lpString1
0x1800e144e  call    cs:__imp_CompareStringOrdinal
0x1800e1454  mov     esi, 1
0x1800e1459  cmp     eax, 2
0x1800e145c  jnz     short loc_1800E1463
0x1800e145e  mov     r13b, sil
0x1800e1461  jmp     short loc_1800E13E5
0x1800e1463  mov     [rsp+120h+bIgnoreCase], 0; bIgnoreCase
0x1800e146b  or      eax, 0FFFFFFFFh
0x1800e146e  mov     r9d, eax; cchCount2
0x1800e1471  lea     r8, aNologtipwarn_0; "**!!##!!**NoLogTipWarn"
0x1800e1478  mov     edx, eax; cchCount1
0x1800e147a  mov     rcx, [rdi+18h]; lpString1
0x1800e147e  call    cs:__imp_CompareStringOrdinal
0x1800e1484  cmp     eax, 2
0x1800e1487  jz      loc_1800E13E5
0x1800e148d  mov     [rsp+120h+bIgnoreCase], 0; bIgnoreCase
0x1800e1495  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e1499  lea     r8, aLog_1; "**!!##!!**Log"
0x1800e14a0  lea     edx, [r9+0Eh]; cchCount1
0x1800e14a4  mov     rcx, [rdi+18h]; lpString1
0x1800e14a8  call    cs:__imp_CompareStringOrdinal
0x1800e14ae  cmp     eax, 2
0x1800e14b1  jz      loc_1800E13E5
0x1800e14b7  lea     rcx, qword_18023C230
0x1800e14be  lea     rax, dword_18023C24C
0x1800e14c5  cmp     rcx, rax
0x1800e14c8  jz      short loc_1800E14E2
0x1800e14ca  movsx   eax, word ptr [r14+2]
0x1800e14cf  and     eax, 1FFFh
0x1800e14d4  cmp     eax, [rcx]
0x1800e14d6  jz      loc_1800E13E5
0x1800e14dc  add     rcx, 4
0x1800e14e0  jmp     short loc_1800E14BE
0x1800e14e2  lea     rcx, qword_18023C250
0x1800e14e9  lea     rax, aNologtipresume; "**!!##!!**NoLogTipResume"
0x1800e14f0  cmp     rcx, rax
0x1800e14f3  jz      loc_1800E1427
0x1800e14f9  mov     eax, [rcx]
0x1800e14fb  cmp     [r14], eax
0x1800e14fe  jz      loc_1800E13E5
0x1800e1504  add     rcx, 4
0x1800e1508  jmp     short loc_1800E14E9
0x1800e150a  test    rbx, rbx
0x1800e150d  jnz     short loc_1800E1524
0x1800e150f  test    r13b, r13b
0x1800e1512  jz      short loc_1800E1519
0x1800e1514  xor     r12d, r12d
0x1800e1517  jmp     short loc_1800E1524
0x1800e1519  test    r15d, r15d
0x1800e151c  jz      short loc_1800E153D
0x1800e151e  mov     r12d, 2
0x1800e1524  lea     rcx, [rbp+57h+var_C0]
0x1800e1528  call    std___Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0_______Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0___
0x1800e152d  nop
0x1800e152e  lea     rcx, [rsp+120h+var_F0]
0x1800e1533  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState___
0x1800e1538  mov     eax, r12d
0x1800e153b  jmp     short loc_1800E1556
0x1800e153d  lea     rcx, [rbp+57h+var_C0]
0x1800e1541  call    std___Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0_______Hash_std___Umap_traits_long_enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState_std___Uhash_compare_long_std__hash_long__std__equal_to_long____std__allocator_std__pair_long_const__enum__CloudStoreTipTest__GetFailureReportMode2____2___ObservedState____0___
0x1800e1546  nop
0x1800e1547  lea     rcx, [rsp+120h+var_F0]
0x1800e154c  call    std__deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState______deque_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState_std__allocator_enum__CloudStoreTipTest__GetFailureReportMode____2___ReportModeState___
0x1800e1551  mov     eax, 1
0x1800e1556  add     rsp, 0E8h
0x1800e155d  pop     r15
0x1800e155f  pop     r14
0x1800e1561  pop     r13
0x1800e1563  pop     r12
0x1800e1565  pop     rdi
0x1800e1566  pop     rsi
0x1800e1567  pop     rbx
0x1800e1568  pop     rbp
0x1800e1569  retn
```
