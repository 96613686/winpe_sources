# asg::SemanticIndex::DbDiskAnnEmbeddingStore::FixUnreachableNodesStep(asg::Sqlite::DbTransaction &,asg::CancellationToken)

- ea: `0x1801be250`
- end: `0x1801be9ab`
- name: `?FixUnreachableNodesStep@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@QEAA_KAEAVDbTransaction@Sqlite@3@UCancellationToken@3@@Z`
- size: `1883`
- prototype: `unsigned __int64 __high(struct asg::Sqlite::DbTransaction *, struct asg::CancellationToken)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180195b00`

## callees

- `0x180006e30`
- `0x180007ba0`
- `0x180008570`
- `0x180018a60`
- `0x18002b520`
- `0x18002c5c0`
- `0x18002db00`
- `0x18007c250`
- `0x18007c5a0`
- `0x180180080`
- `0x18018b440`
- `0x18018d160`
- `0x1801a7580`
- `0x1801bab40`
- `0x1801bcd10`
- `0x1801be250`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7680`
- `0x1801f97e0`
- `0x180206ec0`
- `0x1802421a0`

## string_xrefs

- `0x1801be4ad`: `DELETE FROM %ls WHERE id = :id`
- `0x1801be6a1`: `DELETE FROM %ls WHERE node_id = :id`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
signed __int64 __fastcall asg::SemanticIndex::DbDiskAnnEmbeddingStore::FixUnreachableNodesStep(
        __int64 a1,
        __int64 a2,
        const struct asg::CancellationToken *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  asg::SemanticIndex::DiskAnn::Index *v11; // r14
  unsigned __int64 v12; // rbx
  size_t v13; // rbx
  signed __int64 v14; // rbx
  _QWORD *v15; // r13
  _QWORD *v16; // rbx
  __m128i si128; // xmm7
  __m128i v18; // xmm6
  __int128 v19; // xmm8
  asg::Sqlite::DbTransaction *v20; // rdi
  __int64 v21; // r8
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rdx
  void *v25; // rcx
  _BYTE *v26; // rcx
  __int64 v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  bool v30; // cf
  int v31; // eax
  volatile signed __int32 *v32; // rdi
  asg::Sqlite::DbTransaction *v33; // rdi
  _QWORD *v34; // r8
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rdx
  void *v38; // rcx
  _BYTE *v39; // rcx
  signed __int64 v40; // rdi
  void *v41; // rcx
  volatile signed __int32 *v42; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v47; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v48; // [rsp+58h] [rbp-B0h] BYREF
  __m128i v49; // [rsp+68h] [rbp-A0h]
  _QWORD v50[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+88h] [rbp-80h] BYREF
  __m128i v52; // [rsp+98h] [rbp-70h]
  __int128 v53; // [rsp+B0h] [rbp-58h]
  size_t v54; // [rsp+C0h] [rbp-48h]
  _QWORD v55[4]; // [rsp+C8h] [rbp-40h] BYREF
  _QWORD v56[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v57; // [rsp+F8h] [rbp-10h]
  const struct asg::CancellationToken *v58; // [rsp+108h] [rbp+0h]
  __int128 *v59; // [rsp+110h] [rbp+8h]
  const char *v60; // [rsp+118h] [rbp+10h] BYREF
  __int64 v61; // [rsp+120h] [rbp+18h]
  char v62; // [rsp+160h] [rbp+58h]
  char v63[16]; // [rsp+168h] [rbp+60h] BYREF
  char v64[16]; // [rsp+178h] [rbp+70h] BYREF
  char v65[8]; // [rsp+188h] [rbp+80h] BYREF
  _QWORD *v66; // [rsp+190h] [rbp+88h]
  void *Src[2]; // [rsp+248h] [rbp+140h] BYREF
  __int64 v68; // [rsp+258h] [rbp+150h]
  _OWORD v69[3]; // [rsp+268h] [rbp+160h] BYREF
  __int128 v70; // [rsp+298h] [rbp+190h]
  asg::Sqlite::DbTransaction *v71[2]; // [rsp+2A8h] [rbp+1A0h]

  v58 = a3;
  if ( *(_QWORD *)a3 && *(_BYTE *)(*(_QWORD *)a3 + 120LL) )
  {
    v44 = asg::CancellationToken::CancellationToken((asg::CancellationToken *)v50, a3);
    asg::OperationCanceledException::OperationCanceledException(pExceptionObject, v44);
    throw (asg::OperationCanceledException *)pExceptionObject;
  }
  *(_OWORD *)Src = 0;
  v68 = 0;
  asg::SemanticIndex::DbDiskAnnEmbeddingStore::BatchPopStoredUnreachableNodeIds(a1, Src, a2, 5);
  if ( *(_QWORD *)a3 && *(_BYTE *)(*(_QWORD *)a3 + 120LL) )
  {
    v45 = asg::CancellationToken::CancellationToken((asg::CancellationToken *)v50, a3);
    asg::OperationCanceledException::OperationCanceledException(pExceptionObject, v45);
    throw (asg::OperationCanceledException *)pExceptionObject;
  }
  memset(v69, 0, sizeof(v69));
  v70 = 0;
  *(_OWORD *)v71 = 0;
  asg::SemanticIndex::DiskAnn::OperationState::OperationState(
    v69,
    *(_QWORD *)(a1 + 184) + 16LL,
    a2,
    *(unsigned int *)(a1 + 20),
    0,
    1);
  v9 = *((_QWORD *)a3 + 1);
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v10 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
  v70 = *(_OWORD *)a3;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = *(asg::SemanticIndex::DiskAnn::Index **)(a1 + 184);
  v53 = 0;
  v54 = 0;
  v12 = ((char *)Src[1] - (char *)Src[0]) >> 2;
  if ( v12 )
  {
    if ( v12 > 0x3FFFFFFFFFFFFFFFLL )
      std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
        v7,
        v6,
        v8);
    _mm_lfence();
    v13 = 4 * v12;
    *(_QWORD *)&v53 = std::_Allocate<16,std::_Default_allocate_traits>(v13);
    v54 = v53 + v13;
    v14 = (char *)Src[1] - (char *)Src[0];
    memmove((void *)v53, Src[0], (char *)Src[1] - (char *)Src[0]);
    *((_QWORD *)&v53 + 1) = v53 + 4 * (v14 >> 2);
  }
  asg::SemanticIndex::DiskAnn::Index::TryReinsertNodes<std::vector<unsigned int>>(v11);
  v15 = v66;
  v16 = (_QWORD *)*v66;
  if ( (_QWORD *)*v66 != v66 )
  {
    *(_QWORD *)&v47 = &v60;
    *((_QWORD *)&v47 + 1) = 1;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v18 = _mm_load_si128((const __m128i *)&_xmm);
    v19 = v47;
    do
    {
      v20 = v71[1];
      v60 = ":id";
      v61 = *((unsigned int *)v16 + 4);
      v62 = 1;
      v21 = a1 + 24;
      if ( *(_QWORD *)(a1 + 48) > 7u )
        v21 = *(_QWORD *)(a1 + 24);
      asg::details::_asg_u16format(&v48, L"DELETE FROM %ls WHERE id = :id", v21);
      v22 = &v48;
      if ( v49.m128i_i64[1] > 7uLL )
        v22 = v48;
      v55[0] = v22;
      v55[1] = v49.m128i_i64[0];
      v23 = (_QWORD *)asg::utf16To8(pExceptionObject, v55);
      v24 = v23;
      if ( v23[3] > 0xFu )
        v24 = (_QWORD *)*v23;
      v47 = v19;
      v55[2] = v24;
      v55[3] = v23[2];
      asg::Sqlite::DbTransaction::ExecuteNonQuery(v20);
      if ( v52.m128i_i64[1] > 0xFuLL )
      {
        v25 = (void *)pExceptionObject[0];
        if ( (unsigned __int64)(v52.m128i_i64[1] + 1) >= 0x1000 )
        {
          v25 = *(void **)(pExceptionObject[0] - 8LL);
          if ( (unsigned __int64)(pExceptionObject[0] - (_QWORD)v25 - 8LL) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        _mm_lfence();
        operator delete(v25);
      }
      v52 = v18;
      LOBYTE(pExceptionObject[0]) = 0;
      if ( v49.m128i_i64[1] > 7uLL )
      {
        v26 = v48;
        if ( (unsigned __int64)(2 * v49.m128i_i64[1] + 2) >= 0x1000 )
        {
          v26 = (_BYTE *)*(v48 - 1);
          if ( (unsigned __int64)((char *)v48 - v26 - 8) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        _mm_lfence();
        operator delete(v26);
      }
      v49 = si128;
      LOWORD(v48) = 0;
      `eh vector destructor iterator'(
        &v60,
        0x50u,
        1u,
        std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
      v27 = *(_QWORD *)&v69[0];
      v47 = 0;
      v59 = &v47;
      v46 = *((_DWORD *)v16 + 4);
      std::unordered_map<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>::_Insert_or_assign<unsigned int const &,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>(
        *(_QWORD *)&v69[0] + 16LL,
        v63,
        &v46,
        &v47);
      v28 = std::_Hash<std::_Umap_traits<unsigned int,unsigned int,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,unsigned int>>,0>>::_Try_emplace<unsigned int const &,>(
              v27 + 160,
              (__int64)v64,
              (unsigned __int8 *)&v46);
      v29 = *(_QWORD *)v28;
      LODWORD(v28) = *(_DWORD *)(*(_QWORD *)v28 + 20LL);
      v30 = (unsigned int)v28 < 0xFFFFFFFE;
      v31 = v28 + 1;
      if ( !v30 )
        v31 = -1;
      *(_DWORD *)(v29 + 20) = v31;
      std::_Hash<std::_Umap_traits<unsigned int,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(
        v27 + 80,
        &v46);
      v32 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
          if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
        }
      }
      v33 = v71[1];
      v60 = ":id";
      v61 = *((unsigned int *)v16 + 4);
      v62 = 1;
      v34 = (_QWORD *)(a1 + 120);
      if ( *(_QWORD *)(a1 + 144) > 7u )
        v34 = (_QWORD *)*v34;
      asg::details::_asg_u16format(&v48, L"DELETE FROM %ls WHERE node_id = :id", v34);
      v35 = &v48;
      if ( v49.m128i_i64[1] > 7uLL )
        v35 = v48;
      *(_QWORD *)&v57 = &v60;
      *((_QWORD *)&v57 + 1) = 1;
      v56[0] = v35;
      v56[1] = v49.m128i_i64[0];
      v36 = (_QWORD *)asg::utf16To8(pExceptionObject, v56);
      v37 = v36;
      if ( v36[3] > 0xFu )
        v37 = (_QWORD *)*v36;
      v47 = v57;
      v50[0] = v37;
      v50[1] = v36[2];
      asg::Sqlite::DbTransaction::ExecuteNonQuery(v33);
      if ( v52.m128i_i64[1] > 0xFuLL )
      {
        v38 = (void *)pExceptionObject[0];
        if ( (unsigned __int64)(v52.m128i_i64[1] + 1) >= 0x1000 )
        {
          v38 = *(void **)(pExceptionObject[0] - 8LL);
          if ( (unsigned __int64)(pExceptionObject[0] - (_QWORD)v38 - 8LL) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        _mm_lfence();
        operator delete(v38);
      }
      v52 = v18;
      LOBYTE(pExceptionObject[0]) = 0;
      if ( v49.m128i_i64[1] > 7uLL )
      {
        v39 = v48;
        if ( (unsigned __int64)(2 * v49.m128i_i64[1] + 2) >= 0x1000 )
        {
          v39 = (_BYTE *)*(v48 - 1);
          if ( (unsigned __int64)((char *)v48 - v39 - 8) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        _mm_lfence();
        operator delete(v39);
      }
      v49 = si128;
      LOWORD(v48) = 0;
      `eh vector destructor iterator'(
        &v60,
        0x50u,
        1u,
        std::pair<char8_t const *,asg::Sqlite::DbValue>::~pair<char8_t const *,asg::Sqlite::DbValue>);
      v16 = (_QWORD *)*v16;
    }
    while ( v16 != v15 );
  }
  v40 = ((char *)Src[1] - (char *)Src[0]) >> 2;
  asg::SemanticIndex::DiskAnn::NodeReinsertionResult::~NodeReinsertionResult((asg::SemanticIndex::DiskAnn::NodeReinsertionResult *)v65);
  asg::SemanticIndex::DiskAnn::OperationState::~OperationState((asg::SemanticIndex::DiskAnn::OperationState *)v69);
  v41 = Src[0];
  if ( Src[0] )
  {
    if ( ((v68 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
    {
      _mm_lfence();
      v41 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v41 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v41);
    *(_OWORD *)Src = 0;
    v68 = 0;
  }
  v42 = (volatile signed __int32 *)*((_QWORD *)a3 + 1);
  if ( v42 )
  {
    if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
      if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
    }
  }
  return v40;
}

```

## disassembly

```asm
0x1801be250  mov     rax, rsp
0x1801be253  mov     [rax+20h], rbx
0x1801be257  push    rbp
0x1801be258  push    rsi
0x1801be259  push    rdi
0x1801be25a  push    r12
0x1801be25c  push    r13
0x1801be25e  push    r14
0x1801be260  push    r15
0x1801be262  lea     rbp, [rax-228h]
0x1801be269  sub     rsp, 2F0h
0x1801be270  movaps  xmmword ptr [rax-48h], xmm6
0x1801be274  movaps  xmmword ptr [rax-58h], xmm7
0x1801be278  movaps  xmmword ptr [rax-68h], xmm8
0x1801be27d  mov     rax, cs:__security_cookie
0x1801be284  xor     rax, rsp
0x1801be287  mov     [rbp+220h+var_70], rax
0x1801be28e  mov     r12, r8
0x1801be291  mov     rbx, rdx
0x1801be294  mov     r15, rcx
0x1801be297  mov     [rbp+220h+var_220], r8
0x1801be29b  xor     edi, edi
0x1801be29d  mov     rax, [r8]
0x1801be2a0  test    rax, rax
0x1801be2a3  jz      short loc_1801BE2B2
0x1801be2a5  movzx   eax, byte ptr [rax+78h]
0x1801be2a9  nop
0x1801be2aa  test    al, al
0x1801be2ac  jnz     loc_1801BE8F5
0x1801be2b2  xorps   xmm0, xmm0
0x1801be2b5  xor     eax, eax
0x1801be2b7  movups  xmmword ptr [rbp+220h+Src], xmm0
0x1801be2be  mov     [rbp+220h+var_D0], rax
0x1801be2c5  mov     r9d, 5
0x1801be2cb  mov     r8, rbx
0x1801be2ce  lea     rdx, [rbp+220h+Src]
0x1801be2d5  call    ?BatchPopStoredUnreachableNodeIds@DbDiskAnnEmbeddingStore@SemanticIndex@asg@@AEAA?AV?$vector@IV?$allocator@I@std@@@std@@AEAVDbTransaction@Sqlite@3@_K@Z; asg::SemanticIndex::DbDiskAnnEmbeddingStore::BatchPopStoredUnreachableNodeIds(asg::Sqlite::DbTransaction &,unsigned __int64)
0x1801be2da  nop
0x1801be2db  mov     rax, [r12]
0x1801be2df  test    rax, rax
0x1801be2e2  jz      short loc_1801BE2F1
0x1801be2e4  movzx   eax, byte ptr [rax+78h]
0x1801be2e8  nop
0x1801be2e9  test    al, al
0x1801be2eb  jnz     loc_1801BE91F
0x1801be2f1  xorps   xmm0, xmm0
0x1801be2f4  movups  [rbp+220h+var_C0], xmm0
0x1801be2fb  movups  [rbp+220h+var_B0], xmm0
0x1801be302  movups  [rbp+220h+var_A0], xmm0
0x1801be309  movups  [rbp+220h+var_90], xmm0
0x1801be310  movups  xmmword ptr [rbp+220h+var_80], xmm0
0x1801be317  mov     rdx, [r15+0B8h]
0x1801be31e  add     rdx, 10h
0x1801be322  mov     byte ptr [rsp+320h+var_2F8], 1
0x1801be327  mov     byte ptr [rsp+320h+Reserved], 0
0x1801be32c  mov     r9d, [r15+14h]
0x1801be330  mov     r8, rbx
0x1801be333  lea     rcx, [rbp+220h+var_C0]
0x1801be33a  call    ??0OperationState@DiskAnn@SemanticIndex@asg@@QEAA@AEBUIndexConfig@123@AEAVDbTransaction@Sqlite@3@W4GraphTableVersion@23@_N3@Z; asg::SemanticIndex::DiskAnn::OperationState::OperationState(asg::SemanticIndex::DiskAnn::IndexConfig const &,asg::Sqlite::DbTransaction &,asg::SemanticIndex::GraphTableVersion,bool,bool)
0x1801be33f  nop
0x1801be340  mov     rax, [r12+8]
0x1801be345  test    rax, rax
0x1801be348  jz      short loc_1801BE34E
0x1801be34a  lock inc dword ptr [rax+8]
0x1801be34e  mov     rax, [r12]
0x1801be352  mov     qword ptr [rbp+220h+var_90], rax
0x1801be359  mov     rbx, qword ptr [rbp+220h+var_90+8]
0x1801be360  mov     rax, [r12+8]
0x1801be365  mov     qword ptr [rbp+220h+var_90+8], rax
0x1801be36c  mov     esi, 0FFFFFFFFh
0x1801be371  test    rbx, rbx
0x1801be374  jz      short loc_1801BE39F
0x1801be376  mov     eax, esi
0x1801be378  lock xadd [rbx+8], eax
0x1801be37d  cmp     eax, 1
0x1801be380  jnz     short loc_1801BE39F
0x1801be382  mov     rax, [rbx]
0x1801be385  mov     rcx, rbx
0x1801be388  call    qword ptr [rax]
0x1801be38a  mov     eax, esi
0x1801be38c  lock xadd [rbx+0Ch], eax
0x1801be391  cmp     eax, 1
0x1801be394  jnz     short loc_1801BE39F
0x1801be396  mov     rax, [rbx]
0x1801be399  mov     rcx, rbx
0x1801be39c  call    qword ptr [rax+8]
0x1801be39f  mov     r14, [r15+0B8h]
0x1801be3a6  xorps   xmm0, xmm0
0x1801be3a9  movdqu  [rbp+220h+var_278], xmm0
0x1801be3ae  mov     [rbp+220h+var_268], rdi
0x1801be3b2  mov     rbx, [rbp+220h+Src+8]
0x1801be3b9  sub     rbx, [rbp+220h+Src]
0x1801be3c0  sar     rbx, 2
0x1801be3c4  test    rbx, rbx
0x1801be3c7  jz      short loc_1801BE42A
0x1801be3c9  mov     rax, 3FFFFFFFFFFFFFFFh
0x1801be3d3  cmp     rbx, rax
0x1801be3d6  ja      loc_1801BE949
0x1801be3dc  lfence
0x1801be3df  lea     rbx, ds:0[rbx*4]
0x1801be3e7  mov     rcx, rbx
0x1801be3ea  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801be3ef  mov     rdi, rax
0x1801be3f2  mov     qword ptr [rbp+220h+var_278], rax
0x1801be3f6  mov     qword ptr [rbp+220h+var_278+8], rax
0x1801be3fa  lea     rcx, [rax+rbx]
0x1801be3fe  mov     [rbp+220h+var_268], rcx
0x1801be402  mov     rbx, [rbp+220h+Src+8]
0x1801be409  mov     rdx, [rbp+220h+Src]; Src
0x1801be410  sub     rbx, rdx
0x1801be413  mov     r8, rbx; Size
0x1801be416  mov     rcx, rax; void *
0x1801be419  call    memmove
0x1801be41e  sar     rbx, 2
0x1801be422  lea     rax, [rdi+rbx*4]
0x1801be426  mov     qword ptr [rbp+220h+var_278+8], rax
0x1801be42a  lea     r9, [rbp+220h+var_278]
0x1801be42e  lea     r8, [rbp+220h+var_C0]
0x1801be435  lea     rdx, [rbp+220h+var_1A0]
0x1801be43c  mov     rcx, r14; this
0x1801be43f  call    ??$TryReinsertNodes@V?$vector@IV?$allocator@I@std@@@std@@@Index@DiskAnn@SemanticIndex@asg@@QEAA?AUNodeReinsertionResult@123@AEAVOperationState@123@V?$vector@IV?$allocator@I@std@@@std@@@Z; asg::SemanticIndex::DiskAnn::Index::TryReinsertNodes<std::vector<uint>>(asg::SemanticIndex::DiskAnn::OperationState &,std::vector<uint>)
0x1801be444  nop
0x1801be445  mov     r13, [rbp+220h+var_198]
0x1801be44c  mov     rbx, [r13+0]
0x1801be450  cmp     rbx, r13
0x1801be453  jz      loc_1801BE7E6
0x1801be459  lea     rax, [rbp+220h+var_210]
0x1801be45d  mov     qword ptr [rsp+320h+var_2E8+8], rax
0x1801be462  mov     [rsp+320h+var_2D8], 1
0x1801be46b  movdqa  xmm7, cs:__xmm@00000000000000070000000000000000
0x1801be473  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1801be47b  movups  xmm8, [rsp+320h+var_2E8+8]
0x1801be481  lea     rax, aId_1; ":id"
0x1801be488  mov     rdi, [rbp+220h+var_80+8]
0x1801be48f  mov     [rbp+220h+var_210], rax
0x1801be493  mov     eax, [rbx+10h]
0x1801be496  mov     [rbp+220h+var_208], rax
0x1801be49a  mov     [rbp+220h+var_1C8], 1
0x1801be49e  lea     r8, [r15+18h]
0x1801be4a2  cmp     qword ptr [r15+30h], 7
0x1801be4a7  jbe     short loc_1801BE4AD
0x1801be4a9  mov     r8, [r15+18h]
0x1801be4ad  lea     rdx, aDeleteFromLsWh_4; "DELETE FROM %ls WHERE id = :id"
0x1801be4b4  lea     rcx, [rsp+320h+var_2D0]
0x1801be4b9  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801be4be  nop
0x1801be4bf  lea     rax, [rsp+320h+var_2D0]
0x1801be4c4  cmp     [rsp+320h+var_2B8], 7
0x1801be4ca  cmova   rax, [rsp+320h+var_2D0]
0x1801be4d0  mov     [rbp+220h+var_260], rax
0x1801be4d4  mov     rax, qword ptr [rsp+320h+var_2C8+8]
0x1801be4d9  mov     [rbp+220h+var_258], rax
0x1801be4dd  lea     rdx, [rbp+220h+var_260]
0x1801be4e1  lea     rcx, [rbp+220h+pExceptionObject]
0x1801be4e5  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801be4ea  nop
0x1801be4eb  mov     rdx, rax
0x1801be4ee  cmp     qword ptr [rax+18h], 0Fh
0x1801be4f3  jbe     short loc_1801BE4F8
0x1801be4f5  mov     rdx, [rax]
0x1801be4f8  movaps  [rsp+320h+var_2E8+8], xmm8
0x1801be4fe  mov     [rbp+220h+var_250], rdx
0x1801be502  mov     rax, [rax+10h]
0x1801be506  mov     [rbp+220h+var_248], rax
0x1801be50a  lea     r8, [rsp+320h+var_2E8+8]
0x1801be50f  lea     rdx, [rbp+220h+var_250]
0x1801be513  mov     rcx, rdi; this
0x1801be516  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801be51b  nop
0x1801be51c  mov     rdx, [rbp+220h+var_288]
0x1801be520  cmp     rdx, 0Fh
0x1801be524  jbe     short loc_1801BE55A
0x1801be526  inc     rdx
0x1801be529  mov     rcx, [rbp+220h+pExceptionObject]
0x1801be52d  mov     rax, rcx
0x1801be530  cmp     rdx, 1000h
0x1801be537  jb      short loc_1801BE552
0x1801be539  add     rdx, 27h ; '''
0x1801be53d  mov     rcx, [rcx-8]; Block
0x1801be541  sub     rax, rcx
0x1801be544  sub     rax, 8
0x1801be548  cmp     rax, 1Fh
0x1801be54c  ja      loc_1801BE966
0x1801be552  lfence
0x1801be555  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801be55a  movdqu  xmmword ptr [rbp-70h], xmm6
0x1801be55f  mov     byte ptr [rbp+220h+pExceptionObject], 0
0x1801be563  mov     rdx, [rsp+320h+var_2B8]
0x1801be568  cmp     rdx, 7
0x1801be56c  jbe     short loc_1801BE5A8
0x1801be56e  lea     rdx, ds:2[rdx*2]
0x1801be576  mov     rcx, [rsp+320h+var_2D0]
0x1801be57b  mov     rax, rcx
0x1801be57e  cmp     rdx, 1000h
0x1801be585  jb      short loc_1801BE5A0
0x1801be587  add     rdx, 27h ; '''
0x1801be58b  mov     rcx, [rcx-8]; Block
0x1801be58f  sub     rax, rcx
0x1801be592  sub     rax, 8
0x1801be596  cmp     rax, 1Fh
0x1801be59a  ja      loc_1801BE97D
0x1801be5a0  lfence
0x1801be5a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801be5a8  movdqu  [rsp+320h+var_2C8+8], xmm7
0x1801be5ae  xor     eax, eax
0x1801be5b0  mov     word ptr [rsp+320h+var_2D0], ax
0x1801be5b5  lea     r9, ??1?$pair@PEB_QUDbValue@Sqlite@asg@@@std@@QEAA@XZ; void (*)(void *)
0x1801be5bc  mov     edx, 50h ; 'P'; unsigned __int64
0x1801be5c1  mov     r8d, 1; unsigned __int64
0x1801be5c7  lea     rcx, [rbp+220h+var_210]; void *
0x1801be5cb  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801be5d0  mov     rdi, qword ptr [rbp+220h+var_C0]
0x1801be5d7  xorps   xmm0, xmm0
0x1801be5da  movdqu  [rsp+320h+var_2E8+8], xmm0
0x1801be5e0  lea     rax, [rsp+320h+var_2E8+8]
0x1801be5e5  mov     [rbp+220h+var_218], rax
0x1801be5e9  mov     eax, [rbx+10h]
0x1801be5ec  mov     [rsp+320h+var_2F0], eax
0x1801be5f0  lea     rcx, [rdi+10h]
0x1801be5f4  lea     r9, [rsp+320h+var_2E8+8]
0x1801be5f9  lea     r8, [rsp+320h+var_2F0]
0x1801be5fe  lea     rdx, [rbp+220h+var_1C0]
0x1801be602  call    ??$_Insert_or_assign@AEBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@?$unordered_map@IV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@U?$hash@I@2@U?$equal_to@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@std@@@2@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@std@@@std@@@std@@@std@@_N@1@AEBI$$QEAV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@1@@Z; std::unordered_map<uint,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>::_Insert_or_assign<uint const &,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>(uint const &,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode> &&)
0x1801be607  lea     rcx, [rdi+0A0h]
0x1801be60e  lea     r8, [rsp+320h+var_2F0]
0x1801be613  lea     rdx, [rbp+220h+var_1B0]
0x1801be617  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IIV?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBII@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBII@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,uint,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,uint>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x1801be61c  mov     rcx, [rax]
0x1801be61f  mov     eax, [rcx+14h]
0x1801be622  cmp     eax, 0FFFFFFFEh
0x1801be625  inc     eax
0x1801be627  jb      short loc_1801BE62E
0x1801be629  mov     eax, 0FFFFFFFFh
0x1801be62e  mov     [rcx+14h], eax
0x1801be631  lea     rcx, [rdi+50h]
0x1801be635  lea     rdx, [rsp+320h+var_2F0]
0x1801be63a  call    ?erase@?$_Hash@V?$_Umap_traits@IV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Hash<std::_Umap_traits<uint,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::shared_ptr<asg::SemanticIndex::DiskAnn::GraphNode>>>,0>>::erase(uint const &)
0x1801be63f  nop
0x1801be640  mov     rdi, [rsp+320h+var_2D8]
0x1801be645  test    rdi, rdi
0x1801be648  jz      short loc_1801BE673
0x1801be64a  mov     eax, esi
0x1801be64c  lock xadd [rdi+8], eax
0x1801be651  cmp     eax, 1
0x1801be654  jnz     short loc_1801BE673
0x1801be656  mov     rax, [rdi]
0x1801be659  mov     rcx, rdi
0x1801be65c  call    qword ptr [rax]
0x1801be65e  mov     eax, esi
0x1801be660  lock xadd [rdi+0Ch], eax
0x1801be665  cmp     eax, 1
0x1801be668  jnz     short loc_1801BE673
0x1801be66a  mov     rax, [rdi]
0x1801be66d  mov     rcx, rdi
0x1801be670  call    qword ptr [rax+8]
0x1801be673  mov     rdi, [rbp+220h+var_80+8]
0x1801be67a  lea     rax, aId_1; ":id"
0x1801be681  mov     [rbp+220h+var_210], rax
0x1801be685  mov     eax, [rbx+10h]
0x1801be688  mov     [rbp+220h+var_208], rax
0x1801be68c  mov     [rbp+220h+var_1C8], 1
0x1801be690  lea     r8, [r15+78h]
0x1801be694  cmp     qword ptr [r15+90h], 7
0x1801be69c  jbe     short loc_1801BE6A1
0x1801be69e  mov     r8, [r8]
0x1801be6a1  lea     rdx, aDeleteFromLsWh_0; "DELETE FROM %ls WHERE node_id = :id"
0x1801be6a8  lea     rcx, [rsp+320h+var_2D0]
0x1801be6ad  call    ?_asg_u16format@details@asg@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@PEB_SZZ; asg::details::_asg_u16format(char16_t const *,...)
0x1801be6b2  nop
0x1801be6b3  lea     rax, [rsp+320h+var_2D0]
0x1801be6b8  cmp     [rsp+320h+var_2B8], 7
0x1801be6be  cmova   rax, [rsp+320h+var_2D0]
0x1801be6c4  lea     rcx, [rbp+220h+var_210]
0x1801be6c8  mov     qword ptr [rbp+220h+var_230], rcx
0x1801be6cc  mov     qword ptr [rbp+220h+var_230+8], 1
0x1801be6d4  mov     [rbp+220h+var_240], rax
0x1801be6d8  mov     rax, qword ptr [rsp+320h+var_2C8+8]
0x1801be6dd  mov     [rbp+220h+var_238], rax
0x1801be6e1  lea     rdx, [rbp+220h+var_240]
0x1801be6e5  lea     rcx, [rbp+220h+pExceptionObject]
0x1801be6e9  call    ?utf16To8@asg@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@V?$basic_string_view@_SU?$char_traits@_S@std@@@3@@Z; asg::utf16To8(std::u16string_view)
0x1801be6ee  nop
0x1801be6ef  mov     rdx, rax
0x1801be6f2  cmp     qword ptr [rax+18h], 0Fh
0x1801be6f7  jbe     short loc_1801BE6FC
0x1801be6f9  mov     rdx, [rax]
0x1801be6fc  movups  xmm0, [rbp+220h+var_230]
0x1801be700  movaps  [rsp+320h+var_2E8+8], xmm0
0x1801be705  mov     [rsp+320h+var_2B0], rdx
0x1801be70a  mov     rax, [rax+10h]
0x1801be70e  mov     [rsp+320h+var_2A8], rax
0x1801be713  lea     r8, [rsp+320h+var_2E8+8]
0x1801be718  lea     rdx, [rsp+320h+var_2B0]
0x1801be71d  mov     rcx, rdi; this
0x1801be720  call    ?ExecuteNonQuery@DbTransaction@Sqlite@asg@@QEAAXV?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@UDbParameters@23@@Z; asg::Sqlite::DbTransaction::ExecuteNonQuery(std::u8string_view,asg::Sqlite::DbParameters)
0x1801be725  nop
0x1801be726  mov     rdx, [rbp+220h+var_288]
0x1801be72a  cmp     rdx, 0Fh
0x1801be72e  jbe     short loc_1801BE764
0x1801be730  inc     rdx
  ... truncated ...
```
