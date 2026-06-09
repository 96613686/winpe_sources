# asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(asg::SemanticIndex::DiskAnn::OperationState &,std::shared_ptr<asg::SemanticRegistry::IVectorData const>)

- ea: `0x1801b29e0`
- end: `0x1801b2c1a`
- name: `?InsertToEmptyGraph@Index@DiskAnn@SemanticIndex@asg@@AEAAIAEAVOperationState@234@V?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@std@@@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1801b2590`

## callees

- `0x180078ed0`
- `0x1801b29e0`
- `0x1801b2c20`
- `0x1801d0320`
- `0x1801d0b80`

## string_xrefs

- `0x1801b2ba9`: `unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)`
- `0x1801b2bd7`: `unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)`
- `0x1801b2c05`: `unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn::OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v6; // r15
  int v7; // eax
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  __int128 v17; // [rsp+30h] [rbp-49h] BYREF
  const char *v18; // [rsp+40h] [rbp-39h]
  __int64 v19; // [rsp+50h] [rbp-29h]
  __int128 v20; // [rsp+58h] [rbp-21h] BYREF
  __int128 v21; // [rsp+68h] [rbp-11h] BYREF
  __int128 v22; // [rsp+78h] [rbp-1h] BYREF
  __int64 v23; // [rsp+88h] [rbp+Fh]
  _QWORD *v24; // [rsp+90h] [rbp+17h]

  v24 = a3;
  if ( *((_DWORD *)a2 + 16) != *(_DWORD *)(a1 + 88) )
  {
    *(_QWORD *)&v17 = 0x900000093LL;
    *((_QWORD *)&v17 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v18 = "unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn:"
          ":OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)";
    asg::details::AsgAssertFail(&v17);
  }
  v6 = *a3;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
  if ( v7 )
  {
    if ( v7 == 1 )
      v8 = 4;
    else
      v8 = 0;
  }
  else
  {
    v8 = 1;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6) / v8 != *(_QWORD *)(a1 + 80) )
  {
    *(_QWORD *)&v17 = 0x900000094LL;
    *((_QWORD *)&v17 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v18 = "unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn:"
          ":OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)";
    asg::details::AsgAssertFail(&v17);
  }
  if ( asg::SemanticIndex::DiskAnn::GraphStore::TotalEmbeddingCount(
         *(asg::SemanticIndex::DiskAnn::GraphStore **)(a1 + 104),
         (struct asg::Sqlite::DbTransaction *)a2[9]) )
  {
    *(_QWORD *)&v17 = 0x900000097LL;
    *((_QWORD *)&v17 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\DiskAnn\\Index.cpp";
    v18 = "unsigned int __cdecl asg::SemanticIndex::DiskAnn::Index::InsertToEmptyGraph(class asg::SemanticIndex::DiskAnn:"
          ":OperationState &,class std::shared_ptr<struct asg::SemanticRegistry::IVectorData const >)";
    asg::details::AsgAssertFail(&v17);
  }
  v21 = 0;
  BYTE4(v19) = 0;
  v18 = 0;
  v17 = 0u;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v9 = a3[1];
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v20 = *(_OWORD *)a3;
  asg::SemanticIndex::DiskAnn::Index::InsertToGraph(
    a1,
    (unsigned int)&v21,
    (_DWORD)a2,
    (unsigned int)&v20,
    (__int64)&v22,
    v19);
  v10 = *(_DWORD *)(v21 + 16);
  v11 = a2[4];
  if ( v11 )
    _InterlockedIncrement64((volatile signed __int64 *)(v11 + 40));
  asg::SemanticIndex::DiskAnn::GraphStore::UpdateStartNodeId(
    *(asg::SemanticIndex::DiskAnn::GraphStore **)(a1 + 104),
    (struct asg::Sqlite::DbTransaction *)a2[9],
    v10);
  v12 = *a2;
  LODWORD(v19) = v10;
  BYTE4(v19) = 1;
  *(_QWORD *)(v12 + 4) = v19;
  *(_BYTE *)v12 = 1;
  v13 = *(_DWORD *)(v21 + 16);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
  if ( *((_QWORD *)&v21 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = (volatile signed __int32 *)a3[1];
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1801b29e0  push    rbp
0x1801b29e2  push    rbx
0x1801b29e3  push    rsi
0x1801b29e4  push    rdi
0x1801b29e5  push    r12
0x1801b29e7  push    r14
0x1801b29e9  push    r15
0x1801b29eb  lea     rbp, [rsp-27h]
0x1801b29f0  sub     rsp, 0A0h
0x1801b29f7  mov     rsi, r8
0x1801b29fa  mov     rdi, rdx
0x1801b29fd  mov     r14, rcx
0x1801b2a00  mov     [rbp+57h+var_40], r8
0x1801b2a04  mov     eax, [rcx+58h]
0x1801b2a07  cmp     [rdx+40h], eax
0x1801b2a0a  jnz     loc_1801B2BBE
0x1801b2a10  mov     r15, [r8]
0x1801b2a13  mov     rax, [r15]
0x1801b2a16  mov     rcx, r15
0x1801b2a19  call    qword ptr [rax+10h]
0x1801b2a1c  xor     r12d, r12d
0x1801b2a1f  test    eax, eax
0x1801b2a21  jz      short loc_1801B2A34
0x1801b2a23  cmp     eax, 1
0x1801b2a26  jz      short loc_1801B2A2D
0x1801b2a28  mov     ebx, r12d
0x1801b2a2b  jmp     short loc_1801B2A39
0x1801b2a2d  mov     ebx, 4
0x1801b2a32  jmp     short loc_1801B2A39
0x1801b2a34  mov     ebx, 1
0x1801b2a39  mov     rax, [r15]
0x1801b2a3c  mov     rcx, r15
0x1801b2a3f  call    qword ptr [rax+8]
0x1801b2a42  xor     edx, edx
0x1801b2a44  div     rbx
0x1801b2a47  cmp     rax, [r14+50h]
0x1801b2a4b  jnz     loc_1801B2B90
0x1801b2a51  mov     rdx, [rdi+48h]; struct asg::Sqlite::DbTransaction *
0x1801b2a55  mov     rcx, [r14+68h]; this
0x1801b2a59  call    ?TotalEmbeddingCount@GraphStore@DiskAnn@SemanticIndex@asg@@QEBA_KAEAVDbTransaction@Sqlite@4@@Z; asg::SemanticIndex::DiskAnn::GraphStore::TotalEmbeddingCount(asg::Sqlite::DbTransaction &)
0x1801b2a5e  test    rax, rax
0x1801b2a61  jnz     loc_1801B2BEC
0x1801b2a67  xorps   xmm0, xmm0
0x1801b2a6a  movups  [rbp+57h+var_A0], xmm0
0x1801b2a6e  movups  [rbp+57h+var_68], xmm0
0x1801b2a72  mov     byte ptr [rbp+57h+var_80+4], al
0x1801b2a75  mov     [rbp+57h+var_90], r12
0x1801b2a79  mov     qword ptr [rbp+57h+var_A0+8], r12
0x1801b2a7d  mov     qword ptr [rbp+57h+var_A0], r12
0x1801b2a81  movdqu  [rbp+57h+var_58], xmm0
0x1801b2a86  mov     [rbp+57h+var_48], r12
0x1801b2a8a  movdqu  [rbp+57h+var_78], xmm0
0x1801b2a8f  mov     rax, [rsi+8]
0x1801b2a93  test    rax, rax
0x1801b2a96  jz      short loc_1801B2A9C
0x1801b2a98  lock inc dword ptr [rax+8]
0x1801b2a9c  mov     rax, [rsi]
0x1801b2a9f  mov     qword ptr [rbp+57h+var_78], rax
0x1801b2aa3  mov     rax, [rsi+8]
0x1801b2aa7  mov     qword ptr [rbp+57h+var_78+8], rax
0x1801b2aab  mov     rax, [rbp-29h]
0x1801b2aaf  mov     [rsp+0D0h+var_A8], rax
0x1801b2ab4  lea     rax, [rbp+57h+var_58]
0x1801b2ab8  mov     [rsp+0D0h+var_B0], rax
0x1801b2abd  lea     r9, [rbp+57h+var_78]
0x1801b2ac1  mov     r8, rdi
0x1801b2ac4  lea     rdx, [rbp+57h+var_68]
0x1801b2ac8  mov     rcx, r14
0x1801b2acb  call    ?InsertToGraph@Index@DiskAnn@SemanticIndex@asg@@AEAA?AV?$shared_ptr@UGraphNode@DiskAnn@SemanticIndex@asg@@@std@@AEAVOperationState@234@V?$shared_ptr@$$CBUIVectorData@SemanticRegistry@asg@@@6@V?$vector@IV?$allocator@I@std@@@6@V?$optional@I@6@@Z; asg::SemanticIndex::DiskAnn::Index::InsertToGraph(asg::SemanticIndex::DiskAnn::OperationState &,std::shared_ptr<asg::SemanticRegistry::IVectorData const>,std::vector<uint>,std::optional<uint>)
0x1801b2ad0  nop
0x1801b2ad1  mov     rax, qword ptr [rbp+57h+var_68]
0x1801b2ad5  mov     ebx, [rax+10h]
0x1801b2ad8  mov     rax, [rdi+20h]
0x1801b2adc  test    rax, rax
0x1801b2adf  jz      short loc_1801B2AE6
0x1801b2ae1  lock inc qword ptr [rax+28h]
0x1801b2ae6  mov     r8d, ebx; unsigned int
0x1801b2ae9  mov     rdx, [rdi+48h]; struct asg::Sqlite::DbTransaction *
0x1801b2aed  mov     rcx, [r14+68h]; this
0x1801b2af1  call    ?UpdateStartNodeId@GraphStore@DiskAnn@SemanticIndex@asg@@QEAAXAEAVDbTransaction@Sqlite@4@I@Z; asg::SemanticIndex::DiskAnn::GraphStore::UpdateStartNodeId(asg::Sqlite::DbTransaction &,uint)
0x1801b2af6  mov     rcx, [rdi]
0x1801b2af9  mov     dword ptr [rbp+57h+var_80], ebx
0x1801b2afc  mov     byte ptr [rbp+57h+var_80+4], 1
0x1801b2b00  mov     rax, [rbp+57h+var_80]
0x1801b2b04  mov     [rcx+4], rax
0x1801b2b08  mov     byte ptr [rcx], 1
0x1801b2b0b  mov     rax, qword ptr [rbp+57h+var_68]
0x1801b2b0f  mov     r14d, [rax+10h]
0x1801b2b13  mov     edi, 0FFFFFFFFh
0x1801b2b18  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x1801b2b1c  test    rbx, rbx
0x1801b2b1f  jz      short loc_1801B2B4B
0x1801b2b21  mov     eax, edi
0x1801b2b23  lock xadd [rbx+8], eax
0x1801b2b28  cmp     eax, 1
0x1801b2b2b  jnz     short loc_1801B2B4B
0x1801b2b2d  mov     rax, [rbx]
0x1801b2b30  mov     rcx, rbx
0x1801b2b33  call    qword ptr [rax]
0x1801b2b35  mov     eax, edi
0x1801b2b37  lock xadd [rbx+0Ch], eax
0x1801b2b3c  cmp     eax, 1
0x1801b2b3f  jnz     short loc_1801B2B4B
0x1801b2b41  mov     rax, [rbx]
0x1801b2b44  mov     rcx, rbx
0x1801b2b47  call    qword ptr [rax+8]
0x1801b2b4a  nop
0x1801b2b4b  mov     rbx, [rsi+8]
0x1801b2b4f  test    rbx, rbx
0x1801b2b52  jz      short loc_1801B2B7B
0x1801b2b54  mov     eax, edi
0x1801b2b56  lock xadd [rbx+8], eax
0x1801b2b5b  cmp     eax, 1
0x1801b2b5e  jnz     short loc_1801B2B7B
0x1801b2b60  mov     rax, [rbx]
0x1801b2b63  mov     rcx, rbx
0x1801b2b66  call    qword ptr [rax]
0x1801b2b68  lock xadd [rbx+0Ch], edi
0x1801b2b6d  cmp     edi, 1
0x1801b2b70  jnz     short loc_1801B2B7B
0x1801b2b72  mov     rdx, [rbx]
0x1801b2b75  mov     rcx, rbx
0x1801b2b78  call    qword ptr [rdx+8]
0x1801b2b7b  mov     eax, r14d
0x1801b2b7e  add     rsp, 0A0h
0x1801b2b85  pop     r15
0x1801b2b87  pop     r14
0x1801b2b89  pop     r12
0x1801b2b8b  pop     rdi
0x1801b2b8c  pop     rsi
0x1801b2b8d  pop     rbx
0x1801b2b8e  pop     rbp
0x1801b2b8f  retn
0x1801b2b90  mov     dword ptr [rbp+57h+var_A0], 94h
0x1801b2b97  mov     dword ptr [rbp+57h+var_A0+4], 9
0x1801b2b9e  lea     rax, aCW1SSrcSemanti_12; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801b2ba5  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1801b2ba9  lea     rdx, aUnsignedIntCde; "unsigned int __cdecl asg::SemanticIndex"...
0x1801b2bb0  mov     [rbp+57h+var_90], rdx
0x1801b2bb4  lea     rcx, [rbp+57h+var_A0]
0x1801b2bb8  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x1801b2bbe  mov     dword ptr [rbp+57h+var_A0], 93h
0x1801b2bc5  mov     dword ptr [rbp+57h+var_A0+4], 9
0x1801b2bcc  lea     rax, aCW1SSrcSemanti_12; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801b2bd3  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1801b2bd7  lea     rdx, aUnsignedIntCde; "unsigned int __cdecl asg::SemanticIndex"...
0x1801b2bde  mov     [rbp+57h+var_90], rdx
0x1801b2be2  lea     rcx, [rbp+57h+var_A0]
0x1801b2be6  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x1801b2bec  mov     dword ptr [rbp+57h+var_A0], 97h
0x1801b2bf3  mov     dword ptr [rbp+57h+var_A0+4], 9
0x1801b2bfa  lea     rax, aCW1SSrcSemanti_12; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1801b2c01  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1801b2c05  lea     rdx, aUnsignedIntCde; "unsigned int __cdecl asg::SemanticIndex"...
0x1801b2c0c  mov     [rbp+57h+var_90], rdx
0x1801b2c10  lea     rcx, [rbp+57h+var_A0]
0x1801b2c14  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
```
