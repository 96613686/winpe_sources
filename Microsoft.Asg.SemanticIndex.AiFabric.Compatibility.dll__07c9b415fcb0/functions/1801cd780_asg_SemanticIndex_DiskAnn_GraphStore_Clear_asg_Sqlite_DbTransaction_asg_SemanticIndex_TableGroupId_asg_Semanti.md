# asg::SemanticIndex::DiskAnn::GraphStore::Clear(asg::Sqlite::DbTransaction &,asg::SemanticIndex::TableGroupId,asg::SemanticIndex::TableNames)

- ea: `0x1801cd780`
- end: `0x1801cdc62`
- name: `?Clear@GraphStore@DiskAnn@SemanticIndex@asg@@SAXAEAVDbTransaction@Sqlite@4@W4TableGroupId@34@UTableNames@34@@Z`
- size: `1250`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x1801afe80`
- `0x1801cd690`

## callees

- `0x180007de0`
- `0x18007c250`
- `0x18007c5a0`
- `0x180180080`
- `0x1801cd780`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7680`
- `0x180206ec0`

## string_xrefs

- `0x1801cd8ef`: `DELETE FROM %ls`
- `0x1801cda21`: `DELETE FROM %ls`
- `0x1801cd7c6`: `DELETE FROM %ls `
- `0x1801cdb4a`: `UPDATE si_diskann_info SET start_node_id = NULL, final_id_to_process_in_consolidation = NULL, last_id_processed_in_consolidation = NULL WHERE table_id = :tableid`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall asg::SemanticIndex::DiskAnn::GraphStore::Clear(asg::Sqlite::DbTransaction *a1, int a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // r8
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  _QWORD *v17; // r8
  _QWORD *v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  __int128 v24; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-89h] BYREF
  __m128i v26; // [rsp+50h] [rbp-79h]
  __int128 v27; // [rsp+60h] [rbp-69h]
  _QWORD v28[2]; // [rsp+70h] [rbp-59h] BYREF
  __m128i si128; // [rsp+80h] [rbp-49h]
  const char *v30; // [rsp+A0h] [rbp-29h] BYREF
  int v31; // [rsp+A8h] [rbp-21h]
  char v32; // [rsp+E8h] [rbp+1Fh]
  _QWORD *v33; // [rsp+F0h] [rbp+27h]

  v3 = a3;
  v33 = a3;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  asg::details::_asg_u16format(v25, L"DELETE FROM %ls ", a3);
  v6 = v25;
  if ( v26.m128i_i64[1] > 7uLL )
    v6 = (_QWORD *)v25[0];
  *(_QWORD *)&v24 = v6;
  *((_QWORD *)&v24 + 1) = v26.m128i_i64[0];
  v7 = (_QWORD *)asg::utf16To8(v28, &v24);
  v8 = v7;
  if ( v7[3] > 0xFu )
    v8 = (_QWORD *)*v7;
  v27 = 0;
  *(_QWORD *)&v24 = v8;
  *((_QWORD *)&v24 + 1) = v7[2];
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v9 = (void *)v28[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v9 = *(void **)(v28[0] - 8LL);
      if ( (unsigned __int64)(v28[0] - (_QWORD)v9 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v9);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v28[0]) = 0;
  if ( v26.m128i_i64[1] > 7uLL )
  {
    v10 = (void *)v25[0];
    if ( (unsigned __int64)(2 * v26.m128i_i64[1] + 2) >= 0x1000 )
    {
      v10 = *(void **)(v25[0] - 8LL);
      if ( (unsigned __int64)(v25[0] - (_QWORD)v10 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v10);
  }
  v26 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25[0]) = 0;
  v11 = v3 + 12;
  if ( v3[15] > 7u )
    v11 = (_QWORD *)v3[12];
  asg::details::_asg_u16format(v25, L"DELETE FROM %ls", v11);
  v12 = v25;
  if ( v26.m128i_i64[1] > 7uLL )
    v12 = (_QWORD *)v25[0];
  *(_QWORD *)&v24 = v12;
  *((_QWORD *)&v24 + 1) = v26.m128i_i64[0];
  v13 = (_QWORD *)asg::utf16To8(v28, &v24);
  v14 = v13;
  if ( v13[3] > 0xFu )
    v14 = (_QWORD *)*v13;
  v27 = 0;
  *(_QWORD *)&v24 = v14;
  *((_QWORD *)&v24 + 1) = v13[2];
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v15 = (void *)v28[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v15 = *(void **)(v28[0] - 8LL);
      if ( (unsigned __int64)(v28[0] - (_QWORD)v15 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v15);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v28[0]) = 0;
  if ( v26.m128i_i64[1] > 7uLL )
  {
    v16 = (void *)v25[0];
    if ( (unsigned __int64)(2 * v26.m128i_i64[1] + 2) >= 0x1000 )
    {
      v16 = *(void **)(v25[0] - 8LL);
      if ( (unsigned __int64)(v25[0] - (_QWORD)v16 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v16);
  }
  v26 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v25[0]) = 0;
  v17 = v3 + 16;
  if ( v3[19] > 7u )
    v17 = (_QWORD *)v3[16];
  asg::details::_asg_u16format(v25, L"DELETE FROM %ls", v17);
  v18 = v25;
  if ( v26.m128i_i64[1] > 7uLL )
    v18 = (_QWORD *)v25[0];
  *(_QWORD *)&v24 = v18;
  *((_QWORD *)&v24 + 1) = v26.m128i_i64[0];
  v19 = (_QWORD *)asg::utf16To8(v28, &v24);
  v20 = v19;
  if ( v19[3] > 0xFu )
    v20 = (_QWORD *)*v19;
  v27 = 0;
  *(_QWORD *)&v24 = v20;
  *((_QWORD *)&v24 + 1) = v19[2];
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  if ( si128.m128i_i64[1] > 0xFuLL )
  {
    v21 = (void *)v28[0];
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v21 = *(void **)(v28[0] - 8LL);
      if ( (unsigned __int64)(v28[0] - (_QWORD)v21 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v21);
  }
  LOBYTE(v28[0]) = 0;
  if ( v26.m128i_i64[1] > 7uLL )
  {
    v22 = (void *)v25[0];
    if ( (unsigned __int64)(2 * v26.m128i_i64[1] + 2) >= 0x1000 )
    {
      v22 = *(void **)(v25[0] - 8LL);
      if ( (unsigned __int64)(v25[0] - (_QWORD)v22 - 8LL) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    _mm_lfence();
    operator delete(v22);
  }
  v30 = ":tableid";
  v31 = a2;
  v32 = 0;
  *(_QWORD *)&v24 = &v30;
  *((_QWORD *)&v24 + 1) = 1;
  v27 = v24;
  *(_QWORD *)&v24 = "UPDATE si_diskann_info SET start_node_id = NULL, final_id_to_process_in_consolidation = NULL, last_i"
                    "d_processed_in_consolidation = NULL WHERE table_id = :tableid";
  *((_QWORD *)&v24 + 1) = 161;
  asg::Sqlite::DbTransaction::ExecuteNonQuery(a1);
  `eh vector destructor iterator'(
    &v30,
    0x50u,
    1u,
    std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
  std::basic_string<char16_t>::_Tidy_deallocate(v3 + 16);
  std::basic_string<char16_t>::_Tidy_deallocate(v3 + 12);
  std::basic_string<char16_t>::_Tidy_deallocate(v3 + 8);
  std::basic_string<char16_t>::_Tidy_deallocate(v3 + 4);
  return std::basic_string<char16_t>::_Tidy_deallocate(v3);
}

```

## disassembly

```asm
0x1801cd780  mov     [rsp-8+arg_8], rbx
0x1801cd785  mov     [rsp-8+arg_18], rsi
0x1801cd78a  push    rbp
0x1801cd78b  push    rdi
0x1801cd78c  push    r12
0x1801cd78e  push    r14
0x1801cd790  push    r15
0x1801cd792  lea     rbp, [rsp-37h]
0x1801cd797  sub     rsp, 100h
0x1801cd79e  mov     rax, cs:__security_cookie
0x1801cd7a5  xor     rax, rsp
0x1801cd7a8  mov     [rbp+57h+var_28], rax
0x1801cd7ac  mov     rbx, r8
0x1801cd7af  mov     r15d, edx
0x1801cd7b2  mov     r14, rcx
0x1801cd7b5  mov     [rbp+57h+var_30], rbx
0x1801cd7b9  xor     r12d, r12d
0x1801cd7bc  cmp     qword ptr [r8+18h], 7
0x1801cd7c1  jbe     short loc_1801CD7C6
0x1801cd7c3  mov     r8, [r8]
0x1801cd7c6  lea     rdx, aDeleteFromLs; "DELETE FROM %ls "
0x1801cd7cd  lea     rcx, [rsp+120h+var_E0]
0x1801cd7d2  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801cd7d7  nop
0x1801cd7d8  lea     rax, [rsp+120h+var_E0]
0x1801cd7dd  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x1801cd7e2  cmova   rax, [rsp+120h+var_E0]
0x1801cd7e8  mov     qword ptr [rsp+120h+var_F0], rax
0x1801cd7ed  mov     rax, qword ptr [rbp+57h+var_D0]
0x1801cd7f1  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cd7f6  lea     rdx, [rsp+120h+var_F0]
0x1801cd7fb  lea     rcx, [rbp+57h+var_B0]
0x1801cd7ff  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801cd804  nop
0x1801cd805  mov     rcx, rax
0x1801cd808  cmp     qword ptr [rax+18h], 0Fh
0x1801cd80d  jbe     short loc_1801CD812
0x1801cd80f  mov     rcx, [rax]
0x1801cd812  xorps   xmm0, xmm0
0x1801cd815  movdqa  [rbp+57h+var_C0], xmm0
0x1801cd81a  mov     qword ptr [rsp+120h+var_F0], rcx
0x1801cd81f  mov     rax, [rax+10h]
0x1801cd823  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cd828  lea     r8, [rbp+57h+var_C0]
0x1801cd82c  lea     rdx, [rsp+120h+var_F0]
0x1801cd831  mov     rcx, r14; this
0x1801cd834  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801cd839  nop
0x1801cd83a  mov     rdx, [rbp+57h+var_98]
0x1801cd83e  cmp     rdx, 0Fh
0x1801cd842  jbe     short loc_1801CD878
0x1801cd844  inc     rdx
0x1801cd847  mov     rcx, [rbp+57h+var_B0]
0x1801cd84b  mov     rax, rcx
0x1801cd84e  cmp     rdx, 1000h
0x1801cd855  jb      short loc_1801CD870
0x1801cd857  add     rdx, 27h ; '''
0x1801cd85b  mov     rcx, [rcx-8]; Block
0x1801cd85f  sub     rax, rcx
0x1801cd862  sub     rax, 8
0x1801cd866  cmp     rax, 1Fh
0x1801cd86a  ja      loc_1801CDBF9
0x1801cd870  lfence
0x1801cd873  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd878  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801cd880  movdqu  xmmword ptr [rbp-49h], xmm0
0x1801cd885  mov     byte ptr [rbp+57h+var_B0], 0
0x1801cd889  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x1801cd88d  cmp     rdx, 7
0x1801cd891  jbe     short loc_1801CD8CD
0x1801cd893  lea     rdx, ds:2[rdx*2]
0x1801cd89b  mov     rcx, [rsp+120h+var_E0]
0x1801cd8a0  mov     rax, rcx
0x1801cd8a3  cmp     rdx, 1000h
0x1801cd8aa  jb      short loc_1801CD8C5
0x1801cd8ac  add     rdx, 27h ; '''
0x1801cd8b0  mov     rcx, [rcx-8]; Block
0x1801cd8b4  sub     rax, rcx
0x1801cd8b7  sub     rax, 8
0x1801cd8bb  cmp     rax, 1Fh
0x1801cd8bf  ja      loc_1801CDC0E
0x1801cd8c5  lfence
0x1801cd8c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd8cd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801cd8d5  movdqu  [rbp+57h+var_D0], xmm0
0x1801cd8da  mov     word ptr [rsp+120h+var_E0], r12w
0x1801cd8e0  lea     r8, [rbx+60h]
0x1801cd8e4  cmp     qword ptr [rbx+78h], 7
0x1801cd8e9  jbe     short loc_1801CD8EF
0x1801cd8eb  mov     r8, [rbx+60h]
0x1801cd8ef  lea     rdx, aDeleteFromLs_0; "DELETE FROM %ls"
0x1801cd8f6  lea     rcx, [rsp+120h+var_E0]
0x1801cd8fb  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801cd900  nop
0x1801cd901  lea     rax, [rsp+120h+var_E0]
0x1801cd906  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x1801cd90b  cmova   rax, [rsp+120h+var_E0]
0x1801cd911  mov     qword ptr [rsp+120h+var_F0], rax
0x1801cd916  mov     rax, qword ptr [rbp+57h+var_D0]
0x1801cd91a  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cd91f  lea     rdx, [rsp+120h+var_F0]
0x1801cd924  lea     rcx, [rbp+57h+var_B0]
0x1801cd928  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801cd92d  nop
0x1801cd92e  mov     rcx, rax
0x1801cd931  cmp     qword ptr [rax+18h], 0Fh
0x1801cd936  jbe     short loc_1801CD93B
0x1801cd938  mov     rcx, [rax]
0x1801cd93b  xorps   xmm0, xmm0
0x1801cd93e  movdqa  [rbp+57h+var_C0], xmm0
0x1801cd943  mov     qword ptr [rsp+120h+var_F0], rcx
0x1801cd948  mov     rax, [rax+10h]
0x1801cd94c  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cd951  lea     r8, [rbp+57h+var_C0]
0x1801cd955  lea     rdx, [rsp+120h+var_F0]
0x1801cd95a  mov     rcx, r14; this
0x1801cd95d  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801cd962  nop
0x1801cd963  mov     rdx, [rbp+57h+var_98]
0x1801cd967  cmp     rdx, 0Fh
0x1801cd96b  jbe     short loc_1801CD9A1
0x1801cd96d  inc     rdx
0x1801cd970  mov     rcx, [rbp+57h+var_B0]
0x1801cd974  mov     rax, rcx
0x1801cd977  cmp     rdx, 1000h
0x1801cd97e  jb      short loc_1801CD999
0x1801cd980  add     rdx, 27h ; '''
0x1801cd984  mov     rcx, [rcx-8]; Block
0x1801cd988  sub     rax, rcx
0x1801cd98b  sub     rax, 8
0x1801cd98f  cmp     rax, 1Fh
0x1801cd993  ja      loc_1801CDC23
0x1801cd999  lfence
0x1801cd99c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd9a1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801cd9a9  movdqu  xmmword ptr [rbp-49h], xmm0
0x1801cd9ae  mov     byte ptr [rbp+57h+var_B0], 0
0x1801cd9b2  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x1801cd9b6  cmp     rdx, 7
0x1801cd9ba  jbe     short loc_1801CD9F6
0x1801cd9bc  lea     rdx, ds:2[rdx*2]
0x1801cd9c4  mov     rcx, [rsp+120h+var_E0]
0x1801cd9c9  mov     rax, rcx
0x1801cd9cc  cmp     rdx, 1000h
0x1801cd9d3  jb      short loc_1801CD9EE
0x1801cd9d5  add     rdx, 27h ; '''
0x1801cd9d9  mov     rcx, [rcx-8]; Block
0x1801cd9dd  sub     rax, rcx
0x1801cd9e0  sub     rax, 8
0x1801cd9e4  cmp     rax, 1Fh
0x1801cd9e8  ja      loc_1801CDC38
0x1801cd9ee  lfence
0x1801cd9f1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cd9f6  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801cd9fe  movdqu  [rbp+57h+var_D0], xmm0
0x1801cda03  mov     word ptr [rsp+120h+var_E0], r12w
0x1801cda09  lea     r8, [rbx+80h]
0x1801cda10  cmp     qword ptr [rbx+98h], 7
0x1801cda18  jbe     short loc_1801CDA21
0x1801cda1a  mov     r8, [rbx+80h]
0x1801cda21  lea     rdx, aDeleteFromLs_0; "DELETE FROM %ls"
0x1801cda28  lea     rcx, [rsp+120h+var_E0]
0x1801cda2d  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801cda32  nop
0x1801cda33  lea     rax, [rsp+120h+var_E0]
0x1801cda38  cmp     qword ptr [rbp+57h+var_D0+8], 7
0x1801cda3d  cmova   rax, [rsp+120h+var_E0]
0x1801cda43  mov     qword ptr [rsp+120h+var_F0], rax
0x1801cda48  mov     rax, qword ptr [rbp+57h+var_D0]
0x1801cda4c  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cda51  lea     rdx, [rsp+120h+var_F0]
0x1801cda56  lea     rcx, [rbp+57h+var_B0]
0x1801cda5a  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801cda5f  nop
0x1801cda60  mov     rcx, rax
0x1801cda63  cmp     qword ptr [rax+18h], 0Fh
0x1801cda68  jbe     short loc_1801CDA6D
0x1801cda6a  mov     rcx, [rax]
0x1801cda6d  xorps   xmm0, xmm0
0x1801cda70  movdqa  [rbp+57h+var_C0], xmm0
0x1801cda75  mov     qword ptr [rsp+120h+var_F0], rcx
0x1801cda7a  mov     rax, [rax+10h]
0x1801cda7e  mov     qword ptr [rsp+120h+var_F0+8], rax
0x1801cda83  lea     r8, [rbp+57h+var_C0]
0x1801cda87  lea     rdx, [rsp+120h+var_F0]
0x1801cda8c  mov     rcx, r14; this
0x1801cda8f  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801cda94  nop
0x1801cda95  mov     rdx, [rbp+57h+var_98]
0x1801cda99  cmp     rdx, 0Fh
0x1801cda9d  jbe     short loc_1801CDAD3
0x1801cda9f  inc     rdx
0x1801cdaa2  mov     rcx, [rbp+57h+var_B0]
0x1801cdaa6  mov     rax, rcx
0x1801cdaa9  cmp     rdx, 1000h
0x1801cdab0  jb      short loc_1801CDACB
0x1801cdab2  add     rdx, 27h ; '''
0x1801cdab6  mov     rcx, [rcx-8]; Block
0x1801cdaba  sub     rax, rcx
0x1801cdabd  sub     rax, 8
0x1801cdac1  cmp     rax, 1Fh
0x1801cdac5  ja      loc_1801CDC4D
0x1801cdacb  lfence
0x1801cdace  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cdad3  mov     byte ptr [rbp+57h+var_B0], 0
0x1801cdad7  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x1801cdadb  cmp     rdx, 7
0x1801cdadf  jbe     short loc_1801CDB1B
0x1801cdae1  lea     rdx, ds:2[rdx*2]
0x1801cdae9  mov     rcx, [rsp+120h+var_E0]
0x1801cdaee  mov     rax, rcx
0x1801cdaf1  cmp     rdx, 1000h
0x1801cdaf8  jb      short loc_1801CDB13
0x1801cdafa  add     rdx, 27h ; '''
0x1801cdafe  mov     rcx, [rcx-8]; Block
0x1801cdb02  sub     rax, rcx
0x1801cdb05  sub     rax, 8
0x1801cdb09  cmp     rax, 1Fh
0x1801cdb0d  ja      loc_1801CDBE4
0x1801cdb13  lfence
0x1801cdb16  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801cdb1b  lea     rax, aTableid_0; ":tableid"
0x1801cdb22  mov     [rbp+57h+var_80], rax
0x1801cdb26  mov     [rbp+57h+var_78], r15d
0x1801cdb2a  mov     [rbp+57h+var_38], 0
0x1801cdb2e  lea     rax, [rbp+57h+var_80]
0x1801cdb32  mov     qword ptr [rsp+120h+var_F0], rax
0x1801cdb37  mov     qword ptr [rsp+120h+var_F0+8], 1
0x1801cdb40  movaps  xmm0, [rsp+120h+var_F0]
0x1801cdb45  movdqa  [rbp+57h+var_C0], xmm0
0x1801cdb4a  lea     rax, aUpdateSiDiskan_1; "UPDATE si_diskann_info SET start_node_i"...
0x1801cdb51  mov     qword ptr [rsp+120h+var_F0], rax
0x1801cdb56  mov     qword ptr [rsp+120h+var_F0+8], 0A1h
0x1801cdb5f  lea     r8, [rbp+57h+var_C0]
0x1801cdb63  lea     rdx, [rsp+120h+var_F0]
0x1801cdb68  mov     rcx, r14; this
0x1801cdb6b  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801cdb70  nop
0x1801cdb71  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x1801cdb78  mov     edx, 50h ; 'P'; unsigned __int64
0x1801cdb7d  mov     r8d, 1; unsigned __int64
0x1801cdb83  lea     rcx, [rbp+57h+var_80]; void *
0x1801cdb87  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801cdb8c  nop
0x1801cdb8d  lea     rcx, [rbx+80h]
0x1801cdb94  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801cdb99  lea     rcx, [rbx+60h]
0x1801cdb9d  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801cdba2  lea     rcx, [rbx+40h]
0x1801cdba6  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801cdbab  lea     rcx, [rbx+20h]
0x1801cdbaf  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801cdbb4  mov     rcx, rbx
0x1801cdbb7  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1801cdbbc  mov     rcx, [rbp+57h+var_28]
0x1801cdbc0  xor     rcx, rsp; StackCookie
0x1801cdbc3  call    __security_check_cookie
0x1801cdbc8  lea     r11, [rsp+120h+var_20]
0x1801cdbd0  mov     rbx, [r11+38h]
0x1801cdbd4  mov     rsi, [r11+48h]
0x1801cdbd8  mov     rsp, r11
0x1801cdbdb  pop     r15
0x1801cdbdd  pop     r14
0x1801cdbdf  pop     r12
0x1801cdbe1  pop     rdi
0x1801cdbe2  pop     rbp
0x1801cdbe3  retn
0x1801cdbe4  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdbe9  xor     r9d, r9d; LineNo
0x1801cdbec  xor     r8d, r8d; FileName
0x1801cdbef  xor     edx, edx; FunctionName
0x1801cdbf1  xor     ecx, ecx; Expression
0x1801cdbf3  call    _invoke_watson
0x1801cdbf9  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdbfe  xor     r9d, r9d; LineNo
0x1801cdc01  xor     r8d, r8d; FileName
0x1801cdc04  xor     edx, edx; FunctionName
0x1801cdc06  xor     ecx, ecx; Expression
0x1801cdc08  call    _invoke_watson
0x1801cdc0e  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdc13  xor     r9d, r9d; LineNo
0x1801cdc16  xor     r8d, r8d; FileName
0x1801cdc19  xor     edx, edx; FunctionName
0x1801cdc1b  xor     ecx, ecx; Expression
0x1801cdc1d  call    _invoke_watson
0x1801cdc23  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdc28  xor     r9d, r9d; LineNo
0x1801cdc2b  xor     r8d, r8d; FileName
0x1801cdc2e  xor     edx, edx; FunctionName
0x1801cdc30  xor     ecx, ecx; Expression
0x1801cdc32  call    _invoke_watson
0x1801cdc38  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdc3d  xor     r9d, r9d; LineNo
0x1801cdc40  xor     r8d, r8d; FileName
0x1801cdc43  xor     edx, edx; FunctionName
0x1801cdc45  xor     ecx, ecx; Expression
0x1801cdc47  call    _invoke_watson
0x1801cdc4d  mov     [rsp+120h+Reserved], r12; Reserved
0x1801cdc52  xor     r9d, r9d; LineNo
0x1801cdc55  xor     r8d, r8d; FileName
  ... truncated ...
```
