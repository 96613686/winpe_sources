# asg::SemanticIndex::ApplicationDb::TransformToElementType(asg::Sqlite::DbTransaction &,asg::SemanticIndex::TableGroupId,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::EmbeddingQuantizationParameters const &,asg::SemanticRegistry::EmbeddingInfo const &)

- ea: `0x1801a51d0`
- end: `0x1801a588e`
- name: `?TransformToElementType@ApplicationDb@SemanticIndex@asg@@SAXAEAVDbTransaction@Sqlite@3@W4TableGroupId@23@W4EmbeddingElementType@SemanticRegistry@3@AEBUEmbeddingQuantizationParameters@83@AEBUEmbeddingInfo@83@@Z`
- size: `1726`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18019ddb0`

## callees

- `0x180007830`
- `0x18007c250`
- `0x18007c5a0`
- `0x180180080`
- `0x1801a51d0`
- `0x1801a5a70`
- `0x1801f7160`
- `0x1801f7210`
- `0x1801f7280`
- `0x1801f7660`
- `0x1801f7680`
- `0x180206ec0`

## string_xrefs

- `0x1801a54e1`: `UPDATE %ls SET embedding = %ls(embedding, :scale, :zeroPoint) WHERE embedding IS NOT NULL`
- `0x1801a567b`: `UPDATE %ls SET embedding_altstore = %ls(embedding_altstore, :scale, :zeroPoint) WHERE embedding_altstore IS NOT NULL`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall asg::SemanticIndex::ApplicationDb::TransformToElementType(
        asg::Sqlite::DbTransaction *a1,
        unsigned int a2,
        __int32 a3,
        float *a4,
        __int128 *a5)
{
  int v9; // eax
  _QWORD *v10; // rdi
  _QWORD *v11; // r8
  const wchar_t *v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  _QWORD *v18; // r8
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  int v24; // xmm1_4
  __int128 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v29; // [rsp+60h] [rbp-A0h]
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  const char *v33; // [rsp+B0h] [rbp-50h] BYREF
  double v34; // [rsp+B8h] [rbp-48h]
  char v35; // [rsp+F8h] [rbp-8h]
  const char *v36; // [rsp+100h] [rbp+0h]
  double v37; // [rsp+108h] [rbp+8h]
  char v38; // [rsp+148h] [rbp+48h]

  v9 = *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 52LL);
  if ( a2 )
  {
    v10 = &`asg::SemanticIndex::GreenTableNames'::`2'::greenTables;
    if ( __TSS0__1__GreenTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA > v9 )
    {
      Init_thread_header(&__TSS0__1__GreenTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA);
      if ( __TSS0__1__GreenTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA == -1 )
      {
        `asg::SemanticIndex::GreenTableNames'::`2'::greenTables = 0;
        xmmword_1803DCBD0 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&`asg::SemanticIndex::GreenTableNames'::`2'::greenTables);
        xmmword_1803DCBE0 = 0;
        xmmword_1803DCBF0 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803DCBE0);
        xmmword_1803DCC00 = 0;
        xmmword_1803DCC10 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803DCC00);
        xmmword_1803DCC20 = 0;
        xmmword_1803DCC30 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803DCC20);
        xmmword_1803DCC40 = 0;
        xmmword_1803DCC50 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803DCC40);
        atexit(`asg::SemanticIndex::GreenTableNames'::`2'::`dynamic atexit destructor for 'greenTables'');
        Init_thread_footer(&__TSS0__1__GreenTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA);
      }
    }
    v11 = (_QWORD *)`asg::SemanticIndex::GreenTableNames'::`2'::greenTables;
  }
  else
  {
    v10 = &`asg::SemanticIndex::BlueTableNames'::`2'::blueTables;
    if ( __TSS0__1__BlueTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA > v9 )
    {
      Init_thread_header(&__TSS0__1__BlueTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA);
      if ( __TSS0__1__BlueTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA == -1 )
      {
        `asg::SemanticIndex::BlueTableNames'::`2'::blueTables = 0;
        xmmword_1803E2B70 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&`asg::SemanticIndex::BlueTableNames'::`2'::blueTables);
        xmmword_1803E2B80 = 0;
        xmmword_1803E2B90 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803E2B80);
        xmmword_1803E2BA0 = 0;
        xmmword_1803E2BB0 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803E2BA0);
        xmmword_1803E2BC0 = 0;
        xmmword_1803E2BD0 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803E2BC0);
        xmmword_1803E2BE0 = 0;
        xmmword_1803E2BF0 = 0;
        std::basic_string<char16_t>::_Construct<1,char16_t const *>(&xmmword_1803E2BE0);
        atexit(`asg::SemanticIndex::BlueTableNames'::`2'::`dynamic atexit destructor for 'blueTables'');
        Init_thread_footer(&__TSS0__1__BlueTableNames_SemanticIndex_asg__YAAEBUTableNames_23_XZ_4HA);
      }
    }
    v11 = (_QWORD *)`asg::SemanticIndex::BlueTableNames'::`2'::blueTables;
  }
  v12 = L"DequantizeEmbedding";
  if ( !a3 )
    v12 = L"QuantizeEmbedding";
  v33 = ":scale";
  v34 = *a4;
  v35 = 2;
  v36 = ":zeroPoint";
  v37 = a4[1];
  v38 = 2;
  if ( v10[3] <= 7u )
    v11 = v10;
  asg::details::_asg_u16format(
    v28,
    L"UPDATE %ls SET embedding = %ls(embedding, :scale, :zeroPoint) WHERE embedding IS NOT NULL",
    v11,
    v12);
  v13 = v28;
  if ( v29.m128i_i64[1] > 7uLL )
    v13 = (_QWORD *)v28[0];
  *(_QWORD *)&v26 = &v33;
  *((_QWORD *)&v26 + 1) = 2;
  *(_QWORD *)&v27 = v13;
  *((_QWORD *)&v27 + 1) = v29.m128i_i64[0];
  v14 = (_QWORD *)asg::utf16To8(&v30, &v27);
  v15 = v14;
  if ( v14[3] > 0xFu )
    v15 = (_QWORD *)*v14;
  v27 = v26;
  *(_QWORD *)&v26 = v15;
  *((_QWORD *)&v26 + 1) = v14[2];
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v16 = (void *)v30;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v16 = *(void **)(v30 - 8);
      if ( (unsigned __int64)(v30 - (_QWORD)v16 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v16);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v30) = 0;
  if ( v29.m128i_i64[1] > 7uLL )
  {
    v17 = (void *)v28[0];
    if ( (unsigned __int64)(2 * v29.m128i_i64[1] + 2) >= 0x1000 )
    {
      v17 = *(void **)(v28[0] - 8LL);
      if ( (unsigned __int64)(v28[0] - (_QWORD)v17 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v17);
  }
  v29 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28[0]) = 0;
  `eh vector destructor iterator'(
    &v33,
    0x50u,
    2u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  v33 = ":scale";
  v34 = *a4;
  v35 = 2;
  v36 = ":zeroPoint";
  v37 = a4[1];
  v38 = 2;
  v18 = v10 + 4;
  if ( v10[7] > 7u )
    v18 = (_QWORD *)*v18;
  asg::details::_asg_u16format(
    v28,
    L"UPDATE %ls SET embedding_altstore = %ls(embedding_altstore, :scale, :zeroPoint) WHERE embedding_altstore IS NOT NULL",
    v18,
    v12);
  v19 = v28;
  if ( v29.m128i_i64[1] > 7uLL )
    v19 = (_QWORD *)v28[0];
  *(_QWORD *)&v27 = &v33;
  *((_QWORD *)&v27 + 1) = 2;
  *(_QWORD *)&v26 = v19;
  *((_QWORD *)&v26 + 1) = v29.m128i_i64[0];
  v20 = (_QWORD *)asg::utf16To8(&v30, &v26);
  v21 = v20;
  if ( v20[3] > 0xFu )
    v21 = (_QWORD *)*v20;
  *(_QWORD *)&v26 = v21;
  *((_QWORD *)&v26 + 1) = v20[2];
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v22 = (void *)v30;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v22 = *(void **)(v30 - 8);
      if ( (unsigned __int64)(v30 - (_QWORD)v22 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v22);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v30) = 0;
  if ( v29.m128i_i64[1] > 7uLL )
  {
    v23 = (void *)v28[0];
    if ( (unsigned __int64)(2 * v29.m128i_i64[1] + 2) >= 0x1000 )
    {
      v23 = *(void **)(v28[0] - 8LL);
      if ( (unsigned __int64)(v28[0] - (_QWORD)v23 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v23);
  }
  v29 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v28[0]) = 0;
  `eh vector destructor iterator'(
    &v33,
    0x50u,
    2u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  v30 = *a5;
  si128 = (__m128i)a5[1];
  v32 = a5[2];
  si128.m128i_i32[2] = a3;
  v24 = *((_DWORD *)a4 + 1);
  *(float *)&v32 = *a4;
  DWORD1(v32) = v24;
  if ( !*((_BYTE *)a5 + 40) )
    BYTE8(v32) = 1;
  return asg::SemanticIndex::ApplicationDb::UpdateEmbeddingInfo(a1, a2, &v30);
}

```

## disassembly

```asm
0x1801a51d0  push    rbp
0x1801a51d2  push    rbx
0x1801a51d3  push    rsi
0x1801a51d4  push    rdi
0x1801a51d5  push    r12
0x1801a51d7  push    r13
0x1801a51d9  push    r14
0x1801a51db  push    r15
0x1801a51dd  lea     rbp, [rsp-58h]
0x1801a51e2  sub     rsp, 158h
0x1801a51e9  mov     rbx, r9
0x1801a51ec  mov     r13d, r8d
0x1801a51ef  mov     r14d, edx
0x1801a51f2  mov     rsi, rcx
0x1801a51f5  mov     r12, [rbp+90h+arg_20]
0x1801a51fc  mov     edx, 34h ; '4'
0x1801a5201  mov     ecx, cs:_tls_index
0x1801a5207  mov     rax, gs:58h
0x1801a5210  mov     rax, [rax+rcx*8]
0x1801a5214  mov     eax, [rdx+rax]
0x1801a5217  test    r14d, r14d
0x1801a521a  jnz     loc_1801A5357
0x1801a5220  lea     rdi, ?blueTables@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A; asg::SemanticIndex::TableNames `asg::SemanticIndex::BlueTableNames(void)'::`2'::blueTables
0x1801a5227  cmp     cs:?$TSS0@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA, eax
0x1801a522d  jle     loc_1801A534B
0x1801a5233  lea     rcx, ?$TSS0@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA
0x1801a523a  call    _Init_thread_header
0x1801a523f  cmp     cs:?$TSS0@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA, 0FFFFFFFFh
0x1801a5246  jnz     loc_1801A534B
0x1801a524c  xorps   xmm0, xmm0
0x1801a524f  movups  cs:?blueTables@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A, xmm0; asg::SemanticIndex::TableNames `asg::SemanticIndex::BlueTableNames(void)'::`2'::blueTables
0x1801a5256  xorps   xmm1, xmm1
0x1801a5259  movdqa  cs:xmmword_1803E2B70, xmm1
0x1801a5261  mov     r8d, 15h
0x1801a5267  lea     rdx, aSiDiskannGraph_0; "si_diskann_graph_blue"
0x1801a526e  mov     rcx, rdi
0x1801a5271  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a5276  nop
0x1801a5277  xorps   xmm0, xmm0
0x1801a527a  movups  cs:xmmword_1803E2B80, xmm0
0x1801a5281  xorps   xmm1, xmm1
0x1801a5284  movdqa  cs:xmmword_1803E2B90, xmm1
0x1801a528c  mov     r8d, 1Ah
0x1801a5292  lea     rdx, aSiEmbeddingMet_0; "si_embedding_metadata_blue"
0x1801a5299  lea     rcx, xmmword_1803E2B80
0x1801a52a0  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a52a5  nop
0x1801a52a6  xorps   xmm0, xmm0
0x1801a52a9  movups  cs:xmmword_1803E2BA0, xmm0
0x1801a52b0  xorps   xmm1, xmm1
0x1801a52b3  movdqa  cs:xmmword_1803E2BB0, xmm1
0x1801a52bb  mov     r8d, 1Ah
0x1801a52c1  lea     rdx, aSiDiskannRefer; "si_diskann_references_blue"
0x1801a52c8  lea     rcx, xmmword_1803E2BA0
0x1801a52cf  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a52d4  nop
0x1801a52d5  xorps   xmm0, xmm0
0x1801a52d8  movups  cs:xmmword_1803E2BC0, xmm0
0x1801a52df  xorps   xmm1, xmm1
0x1801a52e2  movdqa  cs:xmmword_1803E2BD0, xmm1
0x1801a52ea  mov     r8d, 17h
0x1801a52f0  lea     rdx, aSiDiskannPurgi_0; "si_diskann_purging_blue"
0x1801a52f7  lea     rcx, xmmword_1803E2BC0
0x1801a52fe  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a5303  nop
0x1801a5304  xorps   xmm0, xmm0
0x1801a5307  movups  cs:xmmword_1803E2BE0, xmm0
0x1801a530e  xorps   xmm1, xmm1
0x1801a5311  movdqa  cs:xmmword_1803E2BF0, xmm1
0x1801a5319  mov     r8d, 21h ; '!'
0x1801a531f  lea     rdx, aSiDiskannUnrea; "si_diskann_unreachable_nodes_blue"
0x1801a5326  lea     rcx, xmmword_1803E2BE0
0x1801a532d  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a5332  nop
0x1801a5333  lea     rcx, ??__FblueTables@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@12@XZ@YAXXZ; void (__cdecl *)()
0x1801a533a  call    atexit
0x1801a533f  lea     rcx, ?$TSS0@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA
0x1801a5346  call    _Init_thread_footer
0x1801a534b  mov     r8, qword ptr cs:?blueTables@?1??BlueTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A; asg::SemanticIndex::TableNames `asg::SemanticIndex::BlueTableNames(void)'::`2'::blueTables
0x1801a5352  jmp     loc_1801A5489
0x1801a5357  lea     rdi, ?greenTables@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A; asg::SemanticIndex::TableNames `asg::SemanticIndex::GreenTableNames(void)'::`2'::greenTables
0x1801a535e  cmp     cs:?$TSS0@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA, eax
0x1801a5364  jle     loc_1801A5482
0x1801a536a  lea     rcx, ?$TSS0@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA
0x1801a5371  call    _Init_thread_header
0x1801a5376  cmp     cs:?$TSS0@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA, 0FFFFFFFFh
0x1801a537d  jnz     loc_1801A5482
0x1801a5383  xorps   xmm0, xmm0
0x1801a5386  movups  cs:?greenTables@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A, xmm0; asg::SemanticIndex::TableNames `asg::SemanticIndex::GreenTableNames(void)'::`2'::greenTables
0x1801a538d  xorps   xmm1, xmm1
0x1801a5390  movdqa  cs:xmmword_1803DCBD0, xmm1
0x1801a5398  mov     r8d, 16h
0x1801a539e  lea     rdx, aSiDiskannGraph; "si_diskann_graph_green"
0x1801a53a5  mov     rcx, rdi
0x1801a53a8  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a53ad  nop
0x1801a53ae  xorps   xmm0, xmm0
0x1801a53b1  movups  cs:xmmword_1803DCBE0, xmm0
0x1801a53b8  xorps   xmm1, xmm1
0x1801a53bb  movdqa  cs:xmmword_1803DCBF0, xmm1
0x1801a53c3  mov     r8d, 1Bh
0x1801a53c9  lea     rdx, aSiEmbeddingMet; "si_embedding_metadata_green"
0x1801a53d0  lea     rcx, xmmword_1803DCBE0
0x1801a53d7  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a53dc  nop
0x1801a53dd  xorps   xmm0, xmm0
0x1801a53e0  movups  cs:xmmword_1803DCC00, xmm0
0x1801a53e7  xorps   xmm1, xmm1
0x1801a53ea  movdqa  cs:xmmword_1803DCC10, xmm1
0x1801a53f2  mov     r8d, 1Bh
0x1801a53f8  lea     rdx, aSiDiskannRefer_0; "si_diskann_references_green"
0x1801a53ff  lea     rcx, xmmword_1803DCC00
0x1801a5406  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a540b  nop
0x1801a540c  xorps   xmm0, xmm0
0x1801a540f  movups  cs:xmmword_1803DCC20, xmm0
0x1801a5416  xorps   xmm1, xmm1
0x1801a5419  movdqa  cs:xmmword_1803DCC30, xmm1
0x1801a5421  mov     r8d, 18h
0x1801a5427  lea     rdx, aSiDiskannPurgi; "si_diskann_purging_green"
0x1801a542e  lea     rcx, xmmword_1803DCC20
0x1801a5435  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a543a  nop
0x1801a543b  xorps   xmm0, xmm0
0x1801a543e  movups  cs:xmmword_1803DCC40, xmm0
0x1801a5445  xorps   xmm1, xmm1
0x1801a5448  movdqa  cs:xmmword_1803DCC50, xmm1
0x1801a5450  mov     r8d, 22h ; '"'
0x1801a5456  lea     rdx, aSiDiskannUnrea_0; "si_diskann_unreachable_nodes_green"
0x1801a545d  lea     rcx, xmmword_1803DCC40
0x1801a5464  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x1801a5469  nop
0x1801a546a  lea     rcx, ??__FgreenTables@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@12@XZ@YAXXZ; void (__cdecl *)()
0x1801a5471  call    atexit
0x1801a5476  lea     rcx, ?$TSS0@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4HA
0x1801a547d  call    _Init_thread_footer
0x1801a5482  mov     r8, qword ptr cs:?greenTables@?1??GreenTableNames@SemanticIndex@asg@@YAAEBUTableNames@23@XZ@4U423@A; asg::SemanticIndex::TableNames `asg::SemanticIndex::GreenTableNames(void)'::`2'::greenTables
0x1801a5489  lea     rax, aQuantizeembedd; "QuantizeEmbedding"
0x1801a5490  lea     r15, aDequantizeembe_0; "DequantizeEmbedding"
0x1801a5497  test    r13d, r13d
0x1801a549a  cmovz   r15, rax
0x1801a549e  lea     rax, aScale_0; ":scale"
0x1801a54a5  mov     [rbp+90h+var_E0], rax
0x1801a54a9  movss   xmm0, dword ptr [rbx]
0x1801a54ad  cvtps2pd xmm0, xmm0
0x1801a54b0  movsd   [rbp+90h+var_D8], xmm0
0x1801a54b5  mov     [rbp+90h+var_98], 2
0x1801a54b9  lea     rax, aZeropoint_0; ":zeroPoint"
0x1801a54c0  mov     [rbp+90h+var_90], rax
0x1801a54c4  movss   xmm0, dword ptr [rbx+4]
0x1801a54c9  cvtps2pd xmm0, xmm0
0x1801a54cc  movsd   [rbp+90h+var_88], xmm0
0x1801a54d1  mov     [rbp+90h+var_48], 2
0x1801a54d5  cmp     qword ptr [rdi+18h], 7
0x1801a54da  cmovbe  r8, rdi
0x1801a54de  mov     r9, r15
0x1801a54e1  lea     rdx, aUpdateLsSetEmb_1; "UPDATE %ls SET embedding = %ls(embeddin"...
0x1801a54e8  lea     rcx, [rsp+190h+var_140]
0x1801a54ed  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801a54f2  nop
0x1801a54f3  lea     rax, [rsp+190h+var_140]
0x1801a54f8  cmp     qword ptr [rsp+190h+var_130+8], 7
0x1801a54fe  cmova   rax, [rsp+190h+var_140]
0x1801a5504  lea     rcx, [rbp+90h+var_E0]
0x1801a5508  mov     qword ptr [rsp+190h+var_160], rcx
0x1801a550d  mov     qword ptr [rsp+190h+var_160+8], 2
0x1801a5516  mov     qword ptr [rsp+190h+var_150], rax
0x1801a551b  mov     rax, qword ptr [rsp+190h+var_130]
0x1801a5520  mov     qword ptr [rsp+190h+var_150+8], rax
0x1801a5525  lea     rdx, [rsp+190h+var_150]
0x1801a552a  lea     rcx, [rsp+190h+var_120]
0x1801a552f  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801a5534  nop
0x1801a5535  mov     rcx, rax
0x1801a5538  cmp     qword ptr [rax+18h], 0Fh
0x1801a553d  jbe     short loc_1801A5542
0x1801a553f  mov     rcx, [rax]
0x1801a5542  movups  xmm0, [rsp+190h+var_160]
0x1801a5547  movaps  [rsp+190h+var_150], xmm0
0x1801a554c  mov     qword ptr [rsp+190h+var_160], rcx
0x1801a5551  mov     rax, [rax+10h]
0x1801a5555  mov     qword ptr [rsp+190h+var_160+8], rax
0x1801a555a  lea     r8, [rsp+190h+var_150]
0x1801a555f  lea     rdx, [rsp+190h+var_160]
0x1801a5564  mov     rcx, rsi; this
0x1801a5567  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801a556c  nop
0x1801a556d  mov     rdx, [rbp+90h+var_108]
0x1801a5571  cmp     rdx, 0Fh
0x1801a5575  jbe     short loc_1801A55AC
0x1801a5577  inc     rdx
0x1801a557a  mov     rcx, qword ptr [rsp+190h+var_120]
0x1801a557f  mov     rax, rcx
0x1801a5582  cmp     rdx, 1000h
0x1801a5589  jb      short loc_1801A55A4
0x1801a558b  add     rdx, 27h ; '''
0x1801a558f  mov     rcx, [rcx-8]; Block
0x1801a5593  sub     rax, rcx
0x1801a5596  sub     rax, 8
0x1801a559a  cmp     rax, 1Fh
0x1801a559e  ja      loc_1801A5849
0x1801a55a4  lfence
0x1801a55a7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a55ac  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801a55b4  movdqu  xmmword ptr [rbp-80h], xmm0
0x1801a55b9  mov     byte ptr [rsp+190h+var_120], 0
0x1801a55be  mov     rdx, qword ptr [rsp+190h+var_130+8]
0x1801a55c3  cmp     rdx, 7
0x1801a55c7  jbe     short loc_1801A5603
0x1801a55c9  lea     rdx, ds:2[rdx*2]
0x1801a55d1  mov     rcx, [rsp+190h+var_140]
0x1801a55d6  mov     rax, rcx
0x1801a55d9  cmp     rdx, 1000h
0x1801a55e0  jb      short loc_1801A55FB
0x1801a55e2  add     rdx, 27h ; '''
0x1801a55e6  mov     rcx, [rcx-8]; Block
0x1801a55ea  sub     rax, rcx
0x1801a55ed  sub     rax, 8
0x1801a55f1  cmp     rax, 1Fh
0x1801a55f5  ja      loc_1801A5860
0x1801a55fb  lfence
0x1801a55fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a5603  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801a560b  movdqu  [rsp+190h+var_130], xmm0
0x1801a5611  xor     eax, eax
0x1801a5613  mov     word ptr [rsp+190h+var_140], ax
0x1801a5618  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x1801a561f  mov     edx, 50h ; 'P'; unsigned __int64
0x1801a5624  mov     r8d, 2; unsigned __int64
0x1801a562a  lea     rcx, [rbp+90h+var_E0]; void *
0x1801a562e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801a5633  lea     rax, aScale_0; ":scale"
0x1801a563a  mov     [rbp+90h+var_E0], rax
0x1801a563e  movss   xmm0, dword ptr [rbx]
0x1801a5642  cvtps2pd xmm0, xmm0
0x1801a5645  movsd   [rbp+90h+var_D8], xmm0
0x1801a564a  mov     [rbp+90h+var_98], 2
0x1801a564e  lea     rax, aZeropoint_0; ":zeroPoint"
0x1801a5655  mov     [rbp+90h+var_90], rax
0x1801a5659  movss   xmm0, dword ptr [rbx+4]
0x1801a565e  cvtps2pd xmm0, xmm0
0x1801a5661  movsd   [rbp+90h+var_88], xmm0
0x1801a5666  mov     [rbp+90h+var_48], 2
0x1801a566a  lea     r8, [rdi+20h]
0x1801a566e  cmp     qword ptr [r8+18h], 7
0x1801a5673  jbe     short loc_1801A5678
0x1801a5675  mov     r8, [r8]
0x1801a5678  mov     r9, r15
0x1801a567b  lea     rdx, aUpdateLsSetEmb; "UPDATE %ls SET embedding_altstore = %ls"...
0x1801a5682  lea     rcx, [rsp+190h+var_140]
0x1801a5687  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801a568c  nop
0x1801a568d  lea     rax, [rsp+190h+var_140]
0x1801a5692  cmp     qword ptr [rsp+190h+var_130+8], 7
0x1801a5698  cmova   rax, [rsp+190h+var_140]
0x1801a569e  lea     rcx, [rbp+90h+var_E0]
0x1801a56a2  mov     qword ptr [rsp+190h+var_150], rcx
0x1801a56a7  mov     qword ptr [rsp+190h+var_150+8], 2
0x1801a56b0  mov     qword ptr [rsp+190h+var_160], rax
0x1801a56b5  mov     rax, qword ptr [rsp+190h+var_130]
0x1801a56ba  mov     qword ptr [rsp+190h+var_160+8], rax
0x1801a56bf  lea     rdx, [rsp+190h+var_160]
0x1801a56c4  lea     rcx, [rsp+190h+var_120]
0x1801a56c9  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801a56ce  nop
0x1801a56cf  mov     rcx, rax
0x1801a56d2  cmp     qword ptr [rax+18h], 0Fh
0x1801a56d7  jbe     short loc_1801A56DC
0x1801a56d9  mov     rcx, [rax]
0x1801a56dc  movups  xmm0, [rsp+190h+var_150]
0x1801a56e1  movaps  [rsp+190h+var_150], xmm0
0x1801a56e6  mov     qword ptr [rsp+190h+var_160], rcx
0x1801a56eb  mov     rax, [rax+10h]
0x1801a56ef  mov     qword ptr [rsp+190h+var_160+8], rax
0x1801a56f4  lea     r8, [rsp+190h+var_150]
0x1801a56f9  lea     rdx, [rsp+190h+var_160]
0x1801a56fe  mov     rcx, rsi; this
0x1801a5701  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801a5706  nop
0x1801a5707  mov     rdx, [rbp+90h+var_108]
0x1801a570b  cmp     rdx, 0Fh
0x1801a570f  jbe     short loc_1801A5746
0x1801a5711  inc     rdx
0x1801a5714  mov     rcx, qword ptr [rsp+190h+var_120]
0x1801a5719  mov     rax, rcx
0x1801a571c  cmp     rdx, 1000h
0x1801a5723  jb      short loc_1801A573E
0x1801a5725  add     rdx, 27h ; '''
0x1801a5729  mov     rcx, [rcx-8]; Block
0x1801a572d  sub     rax, rcx
0x1801a5730  sub     rax, 8
0x1801a5734  cmp     rax, 1Fh
0x1801a5738  ja      loc_1801A5877
0x1801a573e  lfence
0x1801a5741  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801a5746  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801a574e  movdqu  xmmword ptr [rbp-80h], xmm0
0x1801a5753  mov     byte ptr [rsp+190h+var_120], 0
0x1801a5758  mov     rdx, qword ptr [rsp+190h+var_130+8]
0x1801a575d  cmp     rdx, 7
  ... truncated ...
```
