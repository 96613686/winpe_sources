# asg::SemanticIndex::SemanticIndexStore::Clear(void)

- ea: `0x180190950`
- end: `0x180190d32`
- name: `?Clear@SemanticIndexStore@SemanticIndex@asg@@QEAAXXZ`
- size: `994`
- prototype: `void __fastcall(asg::SemanticIndex::SemanticIndexStore *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025410`
- `0x1800500b0`

## callees

- `0x18007c250`
- `0x18007c5a0`
- `0x18017fa90`
- `0x180180080`
- `0x18018ffd0`
- `0x1801908b0`
- `0x180190950`
- `0x1801a3d10`
- `0x1801a6140`
- `0x1801f7110`
- `0x1801f7160`
- `0x180206ec0`

## string_xrefs

- `0x1801909bd`: `DELETE FROM si_items`
- `0x180190a02`: `DELETE FROM %ls`
- `0x180190b45`: `DELETE FROM %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall asg::SemanticIndex::SemanticIndexStore::Clear(asg::SemanticIndex::DbDiskAnnEmbeddingStore **this)
{
  asg::Sqlite::DbTransaction *v2; // rdi
  const char *v3; // rax
  const char **v4; // rax
  const char *v5; // rdx
  void *v6; // rcx
  void *v7; // rcx
  asg::Sqlite::DbTransaction *v8; // rdi
  const char *v9; // rax
  const char **v10; // rax
  const char *v11; // rdx
  void *v12; // rcx
  void *v13; // rcx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  const char *v17; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+38h] [rbp-B0h]
  _QWORD v19[2]; // [rsp+40h] [rbp-A8h] BYREF
  __m128i v20; // [rsp+50h] [rbp-98h]
  __int128 v21; // [rsp+60h] [rbp-88h]
  _QWORD v22[2]; // [rsp+78h] [rbp-70h] BYREF
  __m128i si128; // [rsp+88h] [rbp-60h]
  const asg::Sqlite::DbException *v24; // [rsp+B8h] [rbp-30h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-28h] BYREF

  try
  {
    v25 = 0;
    asg::SemanticIndex::SemanticIndexStore::BeginWriteTransaction(this, &v25);
    asg::SemanticIndex::DbDiskAnnEmbeddingStore::Clear(this[22], (struct asg::Sqlite::DbTransaction *)v25);
    asg::SemanticIndex::DbDiskAnnEmbeddingStore::Clear(this[24], (struct asg::Sqlite::DbTransaction *)v25);
    v21 = 0;
    v17 = "DELETE FROM si_items";
    v18 = 20;
    asg::Sqlite::DbTransaction::ExecuteNonQuery((asg::Sqlite::DbTransaction *)v25);
    v2 = (asg::Sqlite::DbTransaction *)v25;
    asg::details::_asg_u16format(v19, L"DELETE FROM %ls");
    v3 = (const char *)v19;
    if ( v20.m128i_i64[1] > 7uLL )
      v3 = (const char *)v19[0];
    v17 = v3;
    v18 = v20.m128i_i64[0];
    v4 = (const char **)asg::utf16To8(v22, &v17);
    v5 = (const char *)v4;
    if ( (unsigned __int64)v4[3] > 0xF )
      v5 = *v4;
    v21 = 0;
    v17 = v5;
    v18 = (__int64)v4[2];
    asg::Sqlite::DbTransaction::ExecuteNonQuery(v2);
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v6 = (void *)v22[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v6 = *(void **)(v22[0] - 8LL);
        if ( (unsigned __int64)(v22[0] - (_QWORD)v6 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v6);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v22[0]) = 0;
    if ( v20.m128i_i64[1] > 7uLL )
    {
      v7 = (void *)v19[0];
      if ( (unsigned __int64)(2 * v20.m128i_i64[1] + 2) >= 0x1000 )
      {
        v7 = *(void **)(v19[0] - 8LL);
        if ( (unsigned __int64)(v19[0] - (_QWORD)v7 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v7);
    }
    v20 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v19[0]) = 0;
    v8 = (asg::Sqlite::DbTransaction *)v25;
    asg::details::_asg_u16format(v19, L"DELETE FROM %ls");
    v9 = (const char *)v19;
    if ( v20.m128i_i64[1] > 7uLL )
      v9 = (const char *)v19[0];
    v17 = v9;
    v18 = v20.m128i_i64[0];
    v10 = (const char **)asg::utf16To8(v22, &v17);
    v11 = (const char *)v10;
    if ( (unsigned __int64)v10[3] > 0xF )
      v11 = *v10;
    v21 = 0;
    v17 = v11;
    v18 = (__int64)v10[2];
    asg::Sqlite::DbTransaction::ExecuteNonQuery(v8);
    if ( si128.m128i_i64[1] > 0xFuLL )
    {
      v12 = (void *)v22[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v12 = *(void **)(v22[0] - 8LL);
        if ( (unsigned __int64)(v22[0] - (_QWORD)v12 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v12);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v22[0]) = 0;
    if ( v20.m128i_i64[1] > 7uLL )
    {
      v13 = (void *)v19[0];
      if ( (unsigned __int64)(2 * v20.m128i_i64[1] + 2) >= 0x1000 )
      {
        v13 = *(void **)(v19[0] - 8LL);
        if ( (unsigned __int64)(v19[0] - (_QWORD)v13 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      _mm_lfence();
      operator delete(v13);
    }
    asg::Sqlite::DbTransaction::Commit((asg::Sqlite::DbTransaction *)v25);
    asg::SemanticIndex::ApplicationDb::Vacuum(this[3]);
    asg::SemanticIndex::ApplicationDb::PerformCheckpoint(this[3], 1);
    v14 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
  }
  catch ( const asg::Sqlite::DbException *v24 )
  {
    v15 = asg::SemanticIndex::AsSemanticIndexException(v22, v24);
    std::throw_with_nested<asg::SemanticIndex::SemanticIndexException>(v15);
  }
  catch ( asg::SemanticIndex::DiskAnn::DiskAnnException )
  {
    v16 = asg::SemanticIndex::SemanticIndexException::SemanticIndexException(v22, "DiskAnn operation failed", 9);
    std::throw_with_nested<asg::SemanticIndex::SemanticIndexException>(v16);
  }
}

```

## disassembly

```asm
0x180190950  mov     r11, rsp
0x180190953  mov     [r11+10h], rbx
0x180190957  mov     [r11+18h], rsi
0x18019095b  push    rdi
0x18019095c  sub     rsp, 0E0h
0x180190963  mov     rax, cs:__security_cookie
0x18019096a  xor     rax, rsp
0x18019096d  mov     [rsp+0E8h+var_18], rax
0x180190975  mov     rbx, rcx
0x180190978  xor     esi, esi
0x18019097a  xorps   xmm0, xmm0
0x18019097d  movups  xmmword ptr [r11-28h], xmm0
0x180190982  lea     rdx, [r11-28h]
0x180190986  call    ?BeginWriteTransaction@SemanticIndexStore@SemanticIndex@asg@@QEAA?AV?$shared_ptr@VApplicationDbWriteTransaction@SemanticIndex@asg@@@std@@XZ; asg::SemanticIndex::SemanticIndexStore::BeginWriteTransaction(void)
0x18019098b  nop
0x18019098c  mov     rdx, [rsp+0E8h+var_28]; struct asg::Sqlite::DbTransaction *
0x180190994  mov     rcx, [rbx+0B0h]; this
0x18019099b  call    ?Clear@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@QEBAXAEAVDbTransaction@Sqlite@3@@Z; asg::SemanticIndex::DbDiskAnnEmbeddingStore::Clear(asg::Sqlite::DbTransaction &)
0x1801909a0  mov     rdx, [rsp+0E8h+var_28]; struct asg::Sqlite::DbTransaction *
0x1801909a8  mov     rcx, [rbx+0C0h]; this
0x1801909af  call    ?Clear@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@QEBAXAEAVDbTransaction@Sqlite@3@@Z; asg::SemanticIndex::DbDiskAnnEmbeddingStore::Clear(asg::Sqlite::DbTransaction &)
0x1801909b4  xorps   xmm0, xmm0
0x1801909b7  movdqa  [rsp+0E8h+var_88], xmm0
0x1801909bd  lea     rax, aDeleteFromSiIt_0; "DELETE FROM si_items"
0x1801909c4  mov     [rsp+0E8h+var_B8], rax
0x1801909c9  mov     [rsp+0E8h+var_B0], 14h
0x1801909d2  lea     r8, [rsp+0E8h+var_88]
0x1801909d7  lea     rdx, [rsp+0E8h+var_B8]
0x1801909dc  mov     rcx, [rsp+0E8h+var_28]; this
0x1801909e4  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801909e9  mov     rdi, [rsp+0E8h+var_28]
0x1801909f1  lea     r8, [rbx+108h]
0x1801909f8  cmp     qword ptr [r8+18h], 7
0x1801909fd  jbe     short loc_180190A02
0x1801909ff  mov     r8, [r8]
0x180190a02  lea     rdx, aDeleteFromLs_0; "DELETE FROM %ls"
0x180190a09  lea     rcx, [rsp+0E8h+var_A8]
0x180190a0e  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x180190a13  nop
0x180190a14  lea     rax, [rsp+0E8h+var_A8]
0x180190a19  cmp     qword ptr [rsp+0E8h+var_98+8], 7
0x180190a1f  cmova   rax, [rsp+0E8h+var_A8]
0x180190a25  mov     [rsp+0E8h+var_B8], rax
0x180190a2a  mov     rax, qword ptr [rsp+0E8h+var_98]
0x180190a2f  mov     [rsp+0E8h+var_B0], rax
0x180190a34  lea     rdx, [rsp+0E8h+var_B8]
0x180190a39  lea     rcx, [rsp+0E8h+var_70]
0x180190a3e  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x180190a43  nop
0x180190a44  mov     rdx, rax
0x180190a47  cmp     qword ptr [rax+18h], 0Fh
0x180190a4c  jbe     short loc_180190A51
0x180190a4e  mov     rdx, [rax]
0x180190a51  xorps   xmm0, xmm0
0x180190a54  movdqa  [rsp+0E8h+var_88], xmm0
0x180190a5a  mov     [rsp+0E8h+var_B8], rdx
0x180190a5f  mov     rax, [rax+10h]
0x180190a63  mov     [rsp+0E8h+var_B0], rax
0x180190a68  lea     r8, [rsp+0E8h+var_88]
0x180190a6d  lea     rdx, [rsp+0E8h+var_B8]
0x180190a72  mov     rcx, rdi; this
0x180190a75  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x180190a7a  nop
0x180190a7b  mov     rdx, [rsp+0E8h+var_58]
0x180190a83  cmp     rdx, 0Fh
0x180190a87  jbe     short loc_180190ABE
0x180190a89  inc     rdx
0x180190a8c  mov     rcx, [rsp+0E8h+var_70]
0x180190a91  mov     rax, rcx
0x180190a94  cmp     rdx, 1000h
0x180190a9b  jb      short loc_180190AB6
0x180190a9d  add     rdx, 27h ; '''
0x180190aa1  mov     rcx, [rcx-8]; Block
0x180190aa5  sub     rax, rcx
0x180190aa8  sub     rax, 8
0x180190aac  cmp     rax, 1Fh
0x180190ab0  ja      loc_180190CDD
0x180190ab6  lfence
0x180190ab9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180190abe  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180190ac6  movdqu  xmmword ptr [rsp+88h], xmm0
0x180190acf  mov     byte ptr [rsp+0E8h+var_70], 0
0x180190ad4  mov     rdx, qword ptr [rsp+0E8h+var_98+8]
0x180190ad9  cmp     rdx, 7
0x180190add  jbe     short loc_180190B19
0x180190adf  lea     rdx, ds:2[rdx*2]
0x180190ae7  mov     rcx, [rsp+0E8h+var_A8]
0x180190aec  mov     rax, rcx
0x180190aef  cmp     rdx, 1000h
0x180190af6  jb      short loc_180190B11
0x180190af8  add     rdx, 27h ; '''
0x180190afc  mov     rcx, [rcx-8]; Block
0x180190b00  sub     rax, rcx
0x180190b03  sub     rax, 8
0x180190b07  cmp     rax, 1Fh
0x180190b0b  ja      loc_180190CF2
0x180190b11  lfence
0x180190b14  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180190b19  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180190b21  movdqu  [rsp+0E8h+var_98], xmm0
0x180190b27  mov     word ptr [rsp+0E8h+var_A8], si
0x180190b2c  mov     rdi, [rsp+0E8h+var_28]
0x180190b34  lea     r8, [rbx+1A8h]
0x180190b3b  cmp     qword ptr [r8+18h], 7
0x180190b40  jbe     short loc_180190B45
0x180190b42  mov     r8, [r8]
0x180190b45  lea     rdx, aDeleteFromLs_0; "DELETE FROM %ls"
0x180190b4c  lea     rcx, [rsp+0E8h+var_A8]
0x180190b51  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x180190b56  nop
0x180190b57  lea     rax, [rsp+0E8h+var_A8]
0x180190b5c  cmp     qword ptr [rsp+0E8h+var_98+8], 7
0x180190b62  cmova   rax, [rsp+0E8h+var_A8]
0x180190b68  mov     [rsp+0E8h+var_B8], rax
0x180190b6d  mov     rax, qword ptr [rsp+0E8h+var_98]
0x180190b72  mov     [rsp+0E8h+var_B0], rax
0x180190b77  lea     rdx, [rsp+0E8h+var_B8]
0x180190b7c  lea     rcx, [rsp+0E8h+var_70]
0x180190b81  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x180190b86  nop
0x180190b87  mov     rdx, rax
0x180190b8a  cmp     qword ptr [rax+18h], 0Fh
0x180190b8f  jbe     short loc_180190B94
0x180190b91  mov     rdx, [rax]
0x180190b94  xorps   xmm0, xmm0
0x180190b97  movdqa  [rsp+0E8h+var_88], xmm0
0x180190b9d  mov     [rsp+0E8h+var_B8], rdx
0x180190ba2  mov     rax, [rax+10h]
0x180190ba6  mov     [rsp+0E8h+var_B0], rax
0x180190bab  lea     r8, [rsp+0E8h+var_88]
0x180190bb0  lea     rdx, [rsp+0E8h+var_B8]
0x180190bb5  mov     rcx, rdi; this
0x180190bb8  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x180190bbd  nop
0x180190bbe  mov     rdx, [rsp+0E8h+var_58]
0x180190bc6  cmp     rdx, 0Fh
0x180190bca  jbe     short loc_180190C01
0x180190bcc  inc     rdx
0x180190bcf  mov     rcx, [rsp+0E8h+var_70]
0x180190bd4  mov     rax, rcx
0x180190bd7  cmp     rdx, 1000h
0x180190bde  jb      short loc_180190BF9
0x180190be0  add     rdx, 27h ; '''
0x180190be4  mov     rcx, [rcx-8]; Block
0x180190be8  sub     rax, rcx
0x180190beb  sub     rax, 8
0x180190bef  cmp     rax, 1Fh
0x180190bf3  ja      loc_180190D07
0x180190bf9  lfence
0x180190bfc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180190c01  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180190c09  movdqu  xmmword ptr [rsp+88h], xmm0
0x180190c12  mov     byte ptr [rsp+0E8h+var_70], 0
0x180190c17  mov     rdx, qword ptr [rsp+0E8h+var_98+8]
0x180190c1c  cmp     rdx, 7
0x180190c20  jbe     short loc_180190C5C
0x180190c22  lea     rdx, ds:2[rdx*2]
0x180190c2a  mov     rcx, [rsp+0E8h+var_A8]
0x180190c2f  mov     rax, rcx
0x180190c32  cmp     rdx, 1000h
0x180190c39  jb      short loc_180190C54
0x180190c3b  add     rdx, 27h ; '''
0x180190c3f  mov     rcx, [rcx-8]; Block
0x180190c43  sub     rax, rcx
0x180190c46  sub     rax, 8
0x180190c4a  cmp     rax, 1Fh
0x180190c4e  ja      loc_180190D1C
0x180190c54  lfence
0x180190c57  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180190c5c  mov     rcx, [rsp+0E8h+var_28]; this
0x180190c64  call    ?Commit@DbTransaction@Sqlite@asg@@QEAAXXZ; asg::Sqlite::DbTransaction::Commit(void)
0x180190c69  mov     rcx, [rbx+18h]; this
0x180190c6d  call    ?Vacuum@ApplicationDb@SemanticIndex@asg@@AEAAXXZ; asg::SemanticIndex::ApplicationDb::Vacuum(void)
0x180190c72  mov     dl, 1; bool
0x180190c74  mov     rcx, [rbx+18h]; this
0x180190c78  call    ?PerformCheckpoint@ApplicationDb@SemanticIndex@asg@@QEAAX_N@Z; asg::SemanticIndex::ApplicationDb::PerformCheckpoint(bool)
0x180190c7d  nop
0x180190c7e  mov     rbx, [rsp+0E8h+var_20]
0x180190c86  test    rbx, rbx
0x180190c89  jz      short loc_180190CB8
0x180190c8b  mov     edi, 0FFFFFFFFh
0x180190c90  mov     eax, edi
0x180190c92  lock xadd [rbx+8], eax
0x180190c97  cmp     eax, 1
0x180190c9a  jnz     short loc_180190CB8
0x180190c9c  mov     rax, [rbx]
0x180190c9f  mov     rcx, rbx
0x180190ca2  call    qword ptr [rax]
0x180190ca4  lock xadd [rbx+0Ch], edi
0x180190ca9  cmp     edi, 1
0x180190cac  jnz     short loc_180190CB8
0x180190cae  mov     rax, [rbx]
0x180190cb1  mov     rcx, rbx
0x180190cb4  call    qword ptr [rax+8]
0x180190cb7  nop
0x180190cb8  mov     rcx, [rsp+0E8h+var_18]
0x180190cc0  xor     rcx, rsp; StackCookie
0x180190cc3  call    __security_check_cookie
0x180190cc8  lea     r11, [rsp+0E8h+var_8]
0x180190cd0  mov     rbx, [r11+18h]
0x180190cd4  mov     rsi, [r11+20h]
0x180190cd8  mov     rsp, r11
0x180190cdb  pop     rdi
0x180190cdc  retn
0x180190cdd  mov     [rsp+0E8h+Reserved], rsi; Reserved
0x180190ce2  xor     r9d, r9d; LineNo
0x180190ce5  xor     r8d, r8d; FileName
0x180190ce8  xor     edx, edx; FunctionName
0x180190cea  xor     ecx, ecx; Expression
0x180190cec  call    _invoke_watson
0x180190cf2  mov     [rsp+0E8h+Reserved], rsi; Reserved
0x180190cf7  xor     r9d, r9d; LineNo
0x180190cfa  xor     r8d, r8d; FileName
0x180190cfd  xor     edx, edx; FunctionName
0x180190cff  xor     ecx, ecx; Expression
0x180190d01  call    _invoke_watson
0x180190d07  mov     [rsp+0E8h+Reserved], rsi; Reserved
0x180190d0c  xor     r9d, r9d; LineNo
0x180190d0f  xor     r8d, r8d; FileName
0x180190d12  xor     edx, edx; FunctionName
0x180190d14  xor     ecx, ecx; Expression
0x180190d16  call    _invoke_watson
0x180190d1c  mov     [rsp+0E8h+Reserved], rsi; Reserved
0x180190d21  xor     r9d, r9d; LineNo
0x180190d24  xor     r8d, r8d; FileName
0x180190d27  xor     edx, edx; FunctionName
0x180190d29  xor     ecx, ecx; Expression
0x180190d2b  call    _invoke_watson
```
