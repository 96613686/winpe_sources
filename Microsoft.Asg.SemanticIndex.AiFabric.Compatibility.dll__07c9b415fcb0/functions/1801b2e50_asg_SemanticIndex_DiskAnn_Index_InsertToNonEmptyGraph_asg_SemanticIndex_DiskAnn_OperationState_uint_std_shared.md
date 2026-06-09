# asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,std::optional<uint>)

- ea: `0x1801b2e50`
- end: `0x1801b33eb`
- name: `?InsertToNonEmptyGraph@Index@DiskAnn@SemanticIndex@asg@@AEAA?AUInsertedNode@234@AEAVOperationState@234@IV?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@std@@V?$optional@I@8@@Z`
- size: `1435`
- prototype: `__int64 __usercall@<rax>(asg::SemanticIndex::DiskAnn::Index *this@<rcx>, __int64, char)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1801b2590`
- `0x1801bab40`

## callees

- `0x1800040f0`
- `0x180006600`
- `0x18000cc40`
- `0x180078ed0`
- `0x1801add80`
- `0x1801b0fb0`
- `0x1801b14e0`
- `0x1801b2c20`
- `0x1801b2e50`
- `0x1801cee00`
- `0x1801cf860`
- `0x1801f7110`
- `0x1801f97e0`

## string_xrefs

- `0x1801b3319`: `struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >,class std::optional<unsigned int>)`
- `0x1801b334c`: `struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >,class std::optional<unsigned int>)`
- `0x1801b33a6`: `struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >,class std::optional<unsigned int>)`
- `0x1801b33d6`: `struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >,class std::optional<unsigned int>)`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned int *__fastcall asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyGraph(
        asg::SemanticIndex::DiskAnn::Index *this,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6)
{
  __int64 v8; // rdi
  int v9; // eax
  char v10; // r15
  unsigned __int64 v11; // rbx
  __int64 v12; // rax
  __int64 GraphNodeFromDb; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 *p_pExceptionObject; // rax
  struct asg::SemanticRegistry::IVectorData *v17; // rcx
  __int64 v18; // rdx
  volatile signed __int32 *v19; // rsi
  volatile signed __int32 *v20; // r14
  volatile signed __int32 *v21; // r14
  volatile signed __int32 *v22; // r14
  unsigned int v23; // r14d
  unsigned int *v24; // rsi
  volatile signed __int32 *v25; // rbx
  const char *v26; // r8
  const char *v27; // rcx
  unsigned int *v28; // rdx
  __int64 v29; // rax
  unsigned int *v30; // rax
  volatile signed __int32 *v31; // rbx
  volatile signed __int32 *v32; // rbx
  unsigned int v34; // [rsp+30h] [rbp-D0h]
  unsigned __int128 v35; // [rsp+40h] [rbp-C0h] BYREF
  const char *v36; // [rsp+50h] [rbp-B0h]
  unsigned int *v37; // [rsp+60h] [rbp-A0h]
  struct asg::SemanticRegistry::IVectorData *v38[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 pExceptionObject; // [rsp+80h] [rbp-80h] BYREF
  const char *v40; // [rsp+88h] [rbp-78h]
  const char *v41; // [rsp+90h] [rbp-70h]
  __int128 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+B0h] [rbp-50h] BYREF
  volatile signed __int32 *v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  char v46; // [rsp+D0h] [rbp-30h] BYREF
  volatile signed __int32 *v47; // [rsp+D8h] [rbp-28h]
  _QWORD *v48; // [rsp+E0h] [rbp-20h]
  unsigned int *v49; // [rsp+E8h] [rbp-18h] BYREF
  const char *v50; // [rsp+F0h] [rbp-10h]
  const char *v51; // [rsp+F8h] [rbp-8h]
  char v52; // [rsp+100h] [rbp+0h]
  char v53; // [rsp+101h] [rbp+1h]

  *(_QWORD *)&v42 = a3;
  v37 = a2;
  v48 = a5;
  LODWORD(v38[0]) = 0;
  if ( *(_DWORD *)(a3 + 64) != *((_DWORD *)this + 22) )
  {
    *(_QWORD *)&v35 = 0x9000000AALL;
    *((_QWORD *)&v35 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v36 = "struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyG"
          "raph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::Semant"
          "icRegistry::IVectorData const >,class std::optional<unsigned int>)";
    asg::details::AsgAssertFail(&v35);
  }
  v8 = *a5;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 16LL))(*a5);
  v10 = 4;
  if ( v9 )
  {
    if ( v9 == 1 )
      v11 = 4;
    else
      v11 = 0;
  }
  else
  {
    v11 = 1;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8) / v11 != *((_QWORD *)this + 10) )
  {
    *(_QWORD *)&v35 = 0x9000000ABLL;
    *((_QWORD *)&v35 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v36 = "struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmptyG"
          "raph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::Semant"
          "icRegistry::IVectorData const >,class std::optional<unsigned int>)";
    asg::details::AsgAssertFail(&v35);
  }
  *(_OWORD *)v38 = 0;
  v12 = a5[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  v38[0] = *(struct asg::SemanticRegistry::IVectorData **)a5;
  v38[1] = *((struct asg::SemanticRegistry::IVectorData **)a5 + 1);
  asg::SemanticIndex::DiskAnn::Index::FindNewNodeNeighborIds(this, (__int64)v38, a6);
  if ( v52 )
  {
    if ( ((v50 - (const char *)v49) & 0xFFFFFFFFFFFFFFFCuLL) != 4 )
    {
      *(_QWORD *)&v35 = 0xD000000B2LL;
      *((_QWORD *)&v35 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
      v36 = "struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmpt"
            "yGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::Se"
            "manticRegistry::IVectorData const >,class std::optional<unsigned int>)";
      asg::details::AsgAssertFail(&v35);
    }
    v34 = *v49;
    if ( BYTE4(a6) )
    {
      v45 = 0;
      if ( v53 )
      {
        GraphNodeFromDb = asg::SemanticIndex::DiskAnn::Index::GetGraphNodeFromDb(this, &v35, a3, (unsigned int)a6);
        LODWORD(v38[0]) = 1;
        v14 = *(_QWORD *)GraphNodeFromDb;
        if ( *(_BYTE *)(*(_QWORD *)GraphNodeFromDb + 64LL) == 1 )
        {
          std::logic_error::logic_error(
            (std::logic_error *)&pExceptionObject,
            "Cannot get the embedding of a 'Cleared' node.");
          throw (std::logic_error *)&pExceptionObject;
        }
        v15 = *(_QWORD *)(v14 + 32);
        if ( v15 )
          _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
        v40 = *(const char **)(v14 + 32);
        p_pExceptionObject = &pExceptionObject;
        v10 = 11;
        v17 = *(struct asg::SemanticRegistry::IVectorData **)(v14 + 24);
        v18 = 0;
      }
      else
      {
        v18 = 0;
        v47 = 0;
        p_pExceptionObject = (__int64 *)&v46;
        v17 = 0;
      }
      v38[0] = v17;
      *(_QWORD *)&v45 = v17;
      v19 = (volatile signed __int32 *)p_pExceptionObject[1];
      *((_QWORD *)&v45 + 1) = v19;
      *p_pExceptionObject = 0;
      p_pExceptionObject[1] = 0;
      if ( (v10 & 4) != 0 )
      {
        v10 &= ~4u;
        v20 = v47;
        if ( v47 )
        {
          if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD))v20)(v20, 0);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
      }
      if ( (v10 & 2) != 0 )
      {
        v10 &= ~2u;
        v21 = (volatile signed __int32 *)v40;
        if ( v40 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v21)(v21, v18);
            if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
          }
        }
      }
      if ( (v10 & 1) != 0 )
      {
        v22 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
        if ( *((_QWORD *)&v35 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v22)(v22, v18);
            if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
          }
        }
      }
      if ( !BYTE4(a6) )
        std::_Throw_bad_optional_access();
      v23 = v34;
      asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(
        *((asg::SemanticIndex::DiskAnn::GraphStore **)this + 13),
        *(struct asg::Sqlite::DbTransaction **)(v42 + 72),
        a6,
        v34,
        v38[0]);
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
    }
    else
    {
      asg::SemanticIndex::DiskAnn::GraphStore::IncrementDuplicateReferenceCount(
        *((asg::SemanticIndex::DiskAnn::GraphStore **)this + 13),
        *(struct asg::Sqlite::DbTransaction **)(a3 + 72),
        *v49,
        1u);
      v23 = v34;
    }
    v24 = v37;
    *v37 = v23;
    *((_BYTE *)v24 + 4) = v53;
    std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(&v49);
    v25 = (volatile signed __int32 *)a5[1];
    if ( v25 )
    {
      if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
  }
  else
  {
    v26 = v51;
    v51 = 0;
    v27 = v50;
    v50 = 0;
    v28 = v49;
    v49 = 0;
    v35 = __PAIR128__((unsigned __int64)v27, (unsigned __int64)v28);
    v36 = v26;
    if ( !((v27 - (const char *)v28) >> 2) )
    {
      pExceptionObject = 0x9000000CBLL;
      v40 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
      v41 = "struct asg::SemanticIndex::DiskAnn::InsertedNode __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToNonEmpt"
            "yGraph(class asg::SemanticIndex::DiskAnn::OperationState &,unsigned int,class std::shared_ptr<struct asg::Se"
            "manticRegistry::IVectorData const >,class std::optional<unsigned int>)";
      asg::details::AsgAssertFail(&pExceptionObject);
    }
    v36 = 0;
    v35 = 0u;
    pExceptionObject = (__int64)v28;
    v40 = v27;
    v41 = v26;
    v42 = 0;
    v29 = a5[1];
    if ( v29 )
      _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
    v42 = *(_OWORD *)a5;
    asg::SemanticIndex::DiskAnn::Index::InsertToGraph(
      (_DWORD)this,
      (unsigned int)&v43,
      a3,
      (unsigned int)&v42,
      (__int64)&pExceptionObject,
      a6);
    asg::SemanticIndex::DiskAnn::Index::AddReverseLink(this, a3, *(unsigned int *)(v43 + 16), v43 + 40);
    v30 = v37;
    *v37 = *(_DWORD *)(v43 + 16);
    *((_BYTE *)v30 + 4) = 0;
    v31 = v44;
    if ( v44 )
    {
      if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    std::vector<enum asg::SemanticRegistry::ModelClass>::_Tidy(&v49);
    v32 = (volatile signed __int32 *)a5[1];
    if ( v32 )
    {
      if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    return v37;
  }
  return v24;
}

```

## disassembly

```asm
0x1801b2e50  push    rbp
0x1801b2e52  push    rbx
0x1801b2e53  push    rsi
0x1801b2e54  push    rdi
0x1801b2e55  push    r12
0x1801b2e57  push    r13
0x1801b2e59  push    r14
0x1801b2e5b  push    r15
0x1801b2e5d  lea     rbp, [rsp-18h]
0x1801b2e62  sub     rsp, 118h
0x1801b2e69  mov     rax, cs:__security_cookie
0x1801b2e70  xor     rax, rsp
0x1801b2e73  mov     [rbp+50h+var_48], rax
0x1801b2e77  mov     [rsp+150h+var_120], r9d
0x1801b2e7c  mov     r14, r8
0x1801b2e7f  mov     qword ptr [rbp+50h+var_B0], r8
0x1801b2e83  mov     [rsp+150h+var_F0], rdx
0x1801b2e88  mov     r13, rcx
0x1801b2e8b  mov     r12, [rbp+50h+arg_20]
0x1801b2e92  mov     [rbp+50h+var_70], r12
0x1801b2e96  mov     dword ptr [rsp+150h+var_E8], 0
0x1801b2e9e  mov     eax, [rcx+58h]
0x1801b2ea1  cmp     [r8+40h], eax
0x1801b2ea5  jnz     loc_1801B3330
0x1801b2eab  mov     rdi, [r12]
0x1801b2eaf  mov     rax, [rdi]
0x1801b2eb2  mov     rcx, rdi
0x1801b2eb5  call    qword ptr [rax+10h]
0x1801b2eb8  mov     r15d, 4
0x1801b2ebe  test    eax, eax
0x1801b2ec0  jz      short loc_1801B2ED0
0x1801b2ec2  cmp     eax, 1
0x1801b2ec5  jz      short loc_1801B2ECB
0x1801b2ec7  xor     ebx, ebx
0x1801b2ec9  jmp     short loc_1801B2ED5
0x1801b2ecb  mov     rbx, r15
0x1801b2ece  jmp     short loc_1801B2ED5
0x1801b2ed0  mov     ebx, 1
0x1801b2ed5  mov     rax, [rdi]
0x1801b2ed8  mov     rcx, rdi
0x1801b2edb  call    qword ptr [rax+8]
0x1801b2ede  xor     edx, edx
0x1801b2ee0  div     rbx
0x1801b2ee3  cmp     rax, [r13+50h]
0x1801b2ee7  jnz     loc_1801B32FD
0x1801b2eed  mov     rbx, qword ptr [rbp+50h+arg_28]
0x1801b2ef4  mov     rsi, rbx
0x1801b2ef7  shr     rsi, 20h
0x1801b2efb  xorps   xmm0, xmm0
0x1801b2efe  movdqu  xmmword ptr [rsp+150h+var_E8], xmm0
0x1801b2f04  mov     rax, [r12+8]
0x1801b2f09  test    rax, rax
0x1801b2f0c  jz      short loc_1801B2F12
0x1801b2f0e  lock inc dword ptr [rax+8]
0x1801b2f12  mov     rax, [r12]
0x1801b2f16  mov     [rsp+150h+var_E8], rax
0x1801b2f1b  mov     rax, [r12+8]
0x1801b2f20  mov     [rsp+150h+var_E8+8], rax
0x1801b2f25  mov     qword ptr [rsp+150h+var_128], rbx; char
0x1801b2f2a  lea     rax, [rsp+150h+var_E8]
0x1801b2f2f  mov     [rsp+150h+var_130], rax; __int64
0x1801b2f34  mov     r9d, [rsp+150h+var_120]
0x1801b2f39  mov     r8, r14
0x1801b2f3c  lea     rdx, [rbp+50h+var_68]
0x1801b2f40  mov     rcx, r13; this
0x1801b2f43  call    ?FindNewNodeNeighborIds@Index@DiskAnn@SemanticIndex@asg@@AEBA?AUNewNodeNeighborResult@1234@AEAVOperationState@234@IV?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@std@@V?$optional@I@8@@Z; asg::SemanticIndex::DiskAnn::Index::FindNewNodeNeighborIds(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,std::optional<uint>)
0x1801b2f48  nop
0x1801b2f49  cmp     [rbp+50h+var_50], 0
0x1801b2f4d  jz      loc_1801B3193
0x1801b2f53  mov     rax, [rbp+50h+var_60]
0x1801b2f57  mov     rcx, [rbp+50h+var_68]
0x1801b2f5b  sub     rax, rcx
0x1801b2f5e  and     rax, 0FFFFFFFFFFFFFFFCh
0x1801b2f62  cmp     rax, 4
0x1801b2f66  jnz     loc_1801B338A
0x1801b2f6c  mov     eax, [rcx]
0x1801b2f6e  mov     [rsp+150h+var_120], eax
0x1801b2f72  mov     edi, 0FFFFFFFFh
0x1801b2f77  test    sil, sil
0x1801b2f7a  jz      loc_1801B311D
0x1801b2f80  xorps   xmm0, xmm0
0x1801b2f83  movups  [rbp+50h+var_90], xmm0
0x1801b2f87  cmp     [rbp+50h+var_4F], 0
0x1801b2f8b  jz      short loc_1801B2FDD
0x1801b2f8d  mov     r9d, ebx
0x1801b2f90  mov     r8, r14
0x1801b2f93  lea     rdx, [rsp+150h+var_110]
0x1801b2f98  mov     rcx, r13
0x1801b2f9b  call    ?GetGraphNodeFromDb@Index@DiskAnn@SemanticIndex@asg@@AEBA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@I@Z; asg::SemanticIndex::DiskAnn::Index::GetGraphNodeFromDb(asg::SemanticIndex::DiskAnn::OperationState &,uint)
0x1801b2fa0  nop
0x1801b2fa1  mov     dword ptr [rsp+150h+var_E8], 1
0x1801b2fa9  mov     rcx, [rax]
0x1801b2fac  cmp     byte ptr [rcx+40h], 1
0x1801b2fb0  jz      loc_1801B3363
0x1801b2fb6  mov     rax, [rcx+20h]
0x1801b2fba  test    rax, rax
0x1801b2fbd  jz      short loc_1801B2FC3
0x1801b2fbf  lock inc dword ptr [rax+8]
0x1801b2fc3  mov     rax, [rcx+20h]
0x1801b2fc7  mov     [rbp+50h+var_C8], rax
0x1801b2fcb  lea     rax, [rbp+50h+pExceptionObject]
0x1801b2fcf  mov     r15d, 0Bh
0x1801b2fd5  mov     rcx, [rcx+18h]
0x1801b2fd9  xor     edx, edx
0x1801b2fdb  jmp     short loc_1801B2FE9
0x1801b2fdd  xor     edx, edx
0x1801b2fdf  mov     [rbp+50h+var_78], rdx
0x1801b2fe3  lea     rax, [rbp+50h+var_80]
0x1801b2fe7  mov     ecx, edx
0x1801b2fe9  mov     [rsp+150h+var_E8], rcx
0x1801b2fee  mov     qword ptr [rbp+50h+var_90], rcx
0x1801b2ff2  mov     rsi, [rax+8]
0x1801b2ff6  mov     qword ptr [rbp+50h+var_90+8], rsi
0x1801b2ffa  mov     [rax], rdx
0x1801b2ffd  mov     [rax+8], rdx
0x1801b3001  test    r15b, 4
0x1801b3005  jz      short loc_1801B303F
0x1801b3007  and     r15d, 0FFFFFFFBh
0x1801b300b  mov     r14, [rbp+50h+var_78]
0x1801b300f  test    r14, r14
0x1801b3012  jz      short loc_1801B303F
0x1801b3014  mov     eax, edi
0x1801b3016  lock xadd [r14+8], eax
0x1801b301c  cmp     eax, 1
0x1801b301f  jnz     short loc_1801B303F
0x1801b3021  mov     rax, [r14]
0x1801b3024  mov     rcx, r14
0x1801b3027  call    qword ptr [rax]
0x1801b3029  mov     eax, edi
0x1801b302b  lock xadd [r14+0Ch], eax
0x1801b3031  cmp     eax, 1
0x1801b3034  jnz     short loc_1801B303F
0x1801b3036  mov     rax, [r14]
0x1801b3039  mov     rcx, r14
0x1801b303c  call    qword ptr [rax+8]
0x1801b303f  test    r15b, 2
0x1801b3043  jz      short loc_1801B307E
0x1801b3045  and     r15d, 0FFFFFFFDh
0x1801b3049  mov     r14, [rbp+50h+var_C8]
0x1801b304d  test    r14, r14
0x1801b3050  jz      short loc_1801B307E
0x1801b3052  mov     eax, edi
0x1801b3054  lock xadd [r14+8], eax
0x1801b305a  cmp     eax, 1
0x1801b305d  jnz     short loc_1801B307E
0x1801b305f  mov     rax, [r14]
0x1801b3062  mov     rcx, r14
0x1801b3065  call    qword ptr [rax]
0x1801b3067  mov     eax, edi
0x1801b3069  lock xadd [r14+0Ch], eax
0x1801b306f  cmp     eax, 1
0x1801b3072  jnz     short loc_1801B307E
0x1801b3074  mov     rax, [r14]
0x1801b3077  mov     rcx, r14
0x1801b307a  call    qword ptr [rax+8]
0x1801b307d  nop
0x1801b307e  test    r15b, 1
0x1801b3082  jz      short loc_1801B30B9
0x1801b3084  mov     r14, qword ptr [rsp+150h+var_110+8]
0x1801b3089  test    r14, r14
0x1801b308c  jz      short loc_1801B30B9
0x1801b308e  mov     eax, edi
0x1801b3090  lock xadd [r14+8], eax
0x1801b3096  cmp     eax, 1
0x1801b3099  jnz     short loc_1801B30B9
0x1801b309b  mov     rax, [r14]
0x1801b309e  mov     rcx, r14
0x1801b30a1  call    qword ptr [rax]
0x1801b30a3  mov     eax, edi
0x1801b30a5  lock xadd [r14+0Ch], eax
0x1801b30ab  cmp     eax, 1
0x1801b30ae  jnz     short loc_1801B30B9
0x1801b30b0  mov     rax, [r14]
0x1801b30b3  mov     rcx, r14
0x1801b30b6  call    qword ptr [rax+8]
0x1801b30b9  cmp     byte ptr [rbp+8Ch], 0
0x1801b30c0  jz      loc_1801B3384
0x1801b30c6  mov     rax, [rsp+150h+var_E8]
0x1801b30cb  mov     [rsp+150h+var_130], rax; struct asg::SemanticRegistry::IVectorData *
0x1801b30d0  mov     r14d, [rsp+150h+var_120]
0x1801b30d5  mov     r9d, r14d; unsigned int
0x1801b30d8  mov     r8d, ebx; unsigned int
0x1801b30db  mov     rdx, qword ptr [rbp+50h+var_B0]
0x1801b30df  mov     rdx, [rdx+48h]; struct asg::Sqlite::DbTransaction *
0x1801b30e3  mov     rcx, [r13+68h]; this
0x1801b30e7  call    ?MergeExistingNodes@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@IIPEBUIVectorData@SemanticRegistry@4@@Z; asg::SemanticIndex::DiskAnn::GraphStore::MergeExistingNodes(asg::Sqlite::DbTransaction &,uint,uint,asg::SemanticRegistry::IVectorData const *)
0x1801b30ec  nop
0x1801b30ed  test    rsi, rsi
0x1801b30f0  jz      short loc_1801B3138
0x1801b30f2  mov     eax, edi
0x1801b30f4  lock xadd [rsi+8], eax
0x1801b30f9  cmp     eax, 1
0x1801b30fc  jnz     short loc_1801B3138
0x1801b30fe  mov     rax, [rsi]
0x1801b3101  mov     rcx, rsi
0x1801b3104  call    qword ptr [rax]
0x1801b3106  mov     eax, edi
0x1801b3108  lock xadd [rsi+0Ch], eax
0x1801b310d  cmp     eax, 1
0x1801b3110  jnz     short loc_1801B3138
0x1801b3112  mov     rax, [rsi]
0x1801b3115  mov     rcx, rsi
0x1801b3118  call    qword ptr [rax+8]
0x1801b311b  jmp     short loc_1801B3138
0x1801b311d  mov     r9d, 1; unsigned __int64
0x1801b3123  mov     r8d, eax; unsigned int
0x1801b3126  mov     rdx, [r14+48h]; struct asg::Sqlite::DbTransaction *
0x1801b312a  mov     rcx, [r13+68h]; this
0x1801b312e  call    ?IncrementDuplicateReferenceCount@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@I_K@Z; asg::SemanticIndex::DiskAnn::GraphStore::IncrementDuplicateReferenceCount(asg::Sqlite::DbTransaction &,uint,unsigned __int64)
0x1801b3133  mov     r14d, [rsp+150h+var_120]
0x1801b3138  mov     rsi, [rsp+150h+var_F0]
0x1801b313d  mov     [rsi], r14d
0x1801b3140  movzx   eax, [rbp+50h+var_4F]
0x1801b3144  mov     [rsi+4], al
0x1801b3147  lea     rcx, [rbp+50h+var_68]
0x1801b314b  call    ?_Tidy@?$vector@W4ModelClass@SemanticRegistry@asg@@V?$allocator@W4ModelClass@SemanticRegistry@asg@@@std@@@std@@AEAAXXZ; std::vector<asg::SemanticRegistry::ModelClass>::_Tidy(void)
0x1801b3150  nop
0x1801b3151  mov     rbx, [r12+8]
0x1801b3156  test    rbx, rbx
0x1801b3159  jz      loc_1801B32DA
0x1801b315f  mov     eax, edi
0x1801b3161  lock xadd [rbx+8], eax
0x1801b3166  cmp     eax, 1
0x1801b3169  jnz     loc_1801B32DA
0x1801b316f  mov     rax, [rbx]
0x1801b3172  mov     rcx, rbx
0x1801b3175  call    qword ptr [rax]
0x1801b3177  lock xadd [rbx+0Ch], edi
0x1801b317c  cmp     edi, 1
0x1801b317f  jnz     loc_1801B32DA
0x1801b3185  mov     rax, [rbx]
0x1801b3188  mov     rcx, rbx
0x1801b318b  call    qword ptr [rax+8]
0x1801b318e  jmp     loc_1801B32DA
0x1801b3193  xorps   xmm0, xmm0
0x1801b3196  movups  [rsp+150h+var_110], xmm0
0x1801b319b  mov     r8, [rbp+50h+var_58]
0x1801b319f  xor     r9d, r9d
0x1801b31a2  mov     [rbp+50h+var_58], r9
0x1801b31a6  mov     rcx, [rbp+50h+var_60]
0x1801b31aa  mov     [rbp+50h+var_60], r9
0x1801b31ae  mov     rdx, [rbp+50h+var_68]
0x1801b31b2  mov     [rbp+50h+var_68], r9
0x1801b31b6  mov     qword ptr [rsp+150h+var_110], rdx
0x1801b31bb  mov     qword ptr [rsp+150h+var_110+8], rcx
0x1801b31c0  mov     [rsp+150h+var_100], r8
0x1801b31c5  mov     rax, rcx
0x1801b31c8  sub     rax, rdx
0x1801b31cb  sar     rax, 2
0x1801b31cf  test    rax, rax
0x1801b31d2  jz      loc_1801B33BD
0x1801b31d8  mov     [rsp+150h+var_100], r9
0x1801b31dd  mov     qword ptr [rsp+150h+var_110+8], r9
0x1801b31e2  mov     qword ptr [rsp+150h+var_110], r9
0x1801b31e7  mov     [rbp+50h+pExceptionObject], rdx
0x1801b31eb  mov     [rbp+50h+var_C8], rcx
0x1801b31ef  mov     [rbp+50h+var_C0], r8
0x1801b31f3  movdqu  [rbp+50h+var_B0], xmm0
0x1801b31f8  mov     rax, [r12+8]
0x1801b31fd  test    rax, rax
0x1801b3200  jz      short loc_1801B3206
0x1801b3202  lock inc dword ptr [rax+8]
0x1801b3206  mov     rax, [r12]
0x1801b320a  mov     qword ptr [rbp+50h+var_B0], rax
0x1801b320e  mov     rax, [r12+8]
0x1801b3213  mov     qword ptr [rbp+50h+var_B0+8], rax
0x1801b3217  mov     qword ptr [rsp+150h+var_128], rbx
0x1801b321c  lea     rax, [rbp+50h+pExceptionObject]
0x1801b3220  mov     [rsp+150h+var_130], rax
0x1801b3225  lea     r9, [rbp+50h+var_B0]
0x1801b3229  mov     r8, r14
0x1801b322c  lea     rdx, [rbp+50h+var_A0]
0x1801b3230  mov     rcx, r13
0x1801b3233  call    ?InsertToGraph@Index@DiskAnn@SemanticIndex@asg@@AEAA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@V?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@6@V?$vector@IV?$allocator@I@std@@@6@V?$optional@I@6@@Z; asg::SemanticIndex::DiskAnn::Index::InsertToGraph(asg::SemanticIndex::DiskAnn::OperationState &,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,std::vector<uint>,std::optional<uint>)
0x1801b3238  nop
0x1801b3239  mov     r8, [rbp+50h+var_A0]
0x1801b323d  lea     r9, [r8+28h]
0x1801b3241  mov     r8d, [r8+10h]
0x1801b3245  mov     rdx, r14
0x1801b3248  mov     rcx, r13
0x1801b324b  call    ?AddReverseLink@Index@DiskAnn@SemanticIndex@asg@@AEAAXAEAVOperationState@234@IAEBV?$vector@IV?$allocator@I@std@@@std@@@Z; asg::SemanticIndex::DiskAnn::Index::AddReverseLink(asg::SemanticIndex::DiskAnn::OperationState &,uint,std::vector<uint> const &)
0x1801b3250  mov     rax, [rbp+50h+var_A0]
0x1801b3254  mov     ecx, [rax+10h]
0x1801b3257  mov     rax, [rsp+150h+var_F0]
0x1801b325c  mov     [rax], ecx
0x1801b325e  mov     byte ptr [rax+4], 0
0x1801b3262  mov     edi, 0FFFFFFFFh
0x1801b3267  mov     rbx, [rbp+50h+var_98]
0x1801b326b  test    rbx, rbx
0x1801b326e  jz      short loc_1801B329A
0x1801b3270  mov     eax, edi
0x1801b3272  lock xadd [rbx+8], eax
0x1801b3277  cmp     eax, 1
0x1801b327a  jnz     short loc_1801B329A
0x1801b327c  mov     rax, [rbx]
0x1801b327f  mov     rcx, rbx
0x1801b3282  call    qword ptr [rax]
0x1801b3284  mov     eax, edi
0x1801b3286  lock xadd [rbx+0Ch], eax
0x1801b328b  cmp     eax, 1
  ... truncated ...
```
