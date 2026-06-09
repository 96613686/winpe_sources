# CFlat::ComImportAdapter::GetComInterfaceDispatcher$(CFlat::ComInterfaceTypeId const *)

- ea: `0x18001d848`
- end: `0x18001d97e`
- name: `?GetComInterfaceDispatcher$@ComImportAdapter@CFlat@@QEAAPEBXPEBUComInterfaceTypeId@2@@Z`
- size: `310`
- prototype: `const void *__fastcall(CFlat::ComImportAdapter *__hidden this, const struct CFlat::ComInterfaceTypeId *)`
- caller_count: `12`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800077a0`
- `0x18001d7ac`
- `0x18001e270`
- `0x18001ef10`
- `0x1800200b0`
- `0x1800208e0`
- `0x180020e70`
- `0x180021200`
- `0x180021540`
- `0x180040b30`
- `0x18006bcfc`
- `0x18006c8a0`

## callees

- `0x1800067f0`
- `0x1800080a8`
- `0x180009750`
- `0x18001d848`
- `0x180021bfc`
- `0x180048a20`
- `0x18004a348`
- `0x18004aa90`
- `0x1800a6888`
- `0x1800c7e58`
- `0x1800c7eec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001d8a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001d8a4`

## pseudocode

```c
unsigned __int64 __fastcall CFlat::ComImportAdapter::GetComInterfaceDispatcher$(
        void **this,
        const struct CFlat::ComInterfaceTypeId *a2)
{
  char *v2; // rsi
  __int64 v5; // r8
  _QWORD *Value; // rbx
  void *v8; // r15
  __int64 v9; // rax
  Cn::Engine::Lock *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rax
  _BYTE v14[40]; // [rsp+30h] [rbp-28h] BYREF
  int v15; // [rsp+90h] [rbp+38h] BYREF
  const struct CFlat::ComInterfaceTypeId *v16; // [rsp+98h] [rbp+40h] BYREF
  void *v17; // [rsp+A0h] [rbp+48h] BYREF
  _QWORD *v18; // [rsp+A8h] [rbp+50h] BYREF

  v2 = (char *)(this + 4);
  v16 = a2;
  std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(
    this + 4,
    &v18,
    &v16);
  if ( v18 == this[5] )
  {
    Value = TlsGetValue(Cn::Context::s_tlsStorage);
    v8 = CFlat::EntryExit::ValidateCall(Value, this[3], 0);
    CFlat::EntryExit::OnBeginCallToNative(Value);
    v17 = 0;
    v15 = 0;
    v9 = lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_::_lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_(
           (unsigned int)v14,
           (unsigned int)&v15,
           (_DWORD)this,
           (unsigned int)&v16,
           (__int64)&v17);
    CFlat::SehSafe::Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___(Value, v9);
    v10 = (Cn::Engine::Lock *)Value[11];
    if ( v10 )
    {
      Cn::Engine::Lock::Enter(v10);
      Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
    }
    Value[2] = v8;
    if ( v15 == -2147467262 )
    {
      v13 = std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
              v2,
              v14,
              &v16);
      v5 = 0;
      *(_QWORD *)(*(_QWORD *)v13 + 24LL) = 0;
    }
    else
    {
      v11 = std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
              v2,
              v14,
              &v16);
      v12 = *(_QWORD *)v11;
      if ( *(_QWORD *)(*(_QWORD *)v11 + 24LL) )
      {
        CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(Value, v17);
      }
      else
      {
        *(_QWORD *)(v12 + 24) = v17;
        CFlat::EntryExit::AddCachedComImportAdapter(Value, v17, (struct CFlat::ComImportAdapter *)this);
      }
      v5 = *(_QWORD *)(v12 + 24);
    }
  }
  else
  {
    v5 = v18[3];
  }
  return ((unsigned __int64)a2 + 32) & -(__int64)(v5 != 0);
}

```

## disassembly

```asm
0x18001d848  push    rbp
0x18001d84a  push    rbx
0x18001d84b  push    rsi
0x18001d84c  push    rdi
0x18001d84d  push    r14
0x18001d84f  push    r15
0x18001d851  mov     rbp, rsp
0x18001d854  sub     rsp, 58h
0x18001d858  lea     rsi, [rcx+20h]
0x18001d85c  mov     [rbp+arg_8], rdx
0x18001d860  mov     r14, rdx
0x18001d863  lea     r8, [rbp+arg_8]
0x18001d867  mov     rdi, rcx
0x18001d86a  lea     rdx, [rbp+arg_18]
0x18001d86e  mov     rcx, rsi
0x18001d871  call    ?find@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@std@@@std@@@2@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(CFlat::ComInterfaceTypeId const * const &)
0x18001d876  mov     rax, [rbp+arg_18]
0x18001d87a  cmp     rax, [rdi+28h]
0x18001d87e  jz      short loc_18001D89E
0x18001d880  mov     r8, [rax+18h]
0x18001d884  neg     r8
0x18001d887  lea     rcx, [r14+20h]
0x18001d88b  sbb     rax, rax
0x18001d88e  and     rax, rcx
0x18001d891  add     rsp, 58h
0x18001d895  pop     r15
0x18001d897  pop     r14
0x18001d899  pop     rdi
0x18001d89a  pop     rsi
0x18001d89b  pop     rbx
0x18001d89c  pop     rbp
0x18001d89d  retn
0x18001d89e  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001d8a4  call    cs:__imp_TlsGetValue
0x18001d8aa  mov     rdx, [rdi+18h]; void *
0x18001d8ae  xor     r8d, r8d; int
0x18001d8b1  mov     rcx, rax; void *
0x18001d8b4  mov     rbx, rax
0x18001d8b7  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18001d8bc  mov     rcx, rbx; void *
0x18001d8bf  mov     r15, rax
0x18001d8c2  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18001d8c7  lea     rax, [rbp+arg_10]
0x18001d8cb  mov     [rbp+arg_10], 0
0x18001d8d3  lea     r9, [rbp+arg_8]
0x18001d8d7  mov     [rsp+58h+var_38], rax
0x18001d8dc  mov     r8, rdi
0x18001d8df  mov     [rbp+arg_0], 0
0x18001d8e6  lea     rdx, [rbp+arg_0]
0x18001d8ea  lea     rcx, [rbp+var_28]
0x18001d8ee  call    _lambda_9f26dbb50c5457f1a45ef1436d9c8d4d____lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_
0x18001d8f3  mov     rdx, rax
0x18001d8f6  mov     rcx, rbx
0x18001d8f9  call    CFlat__SehSafe__Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___
0x18001d8fe  mov     rcx, [rbx+58h]; this
0x18001d902  test    rcx, rcx
0x18001d905  jz      short loc_18001D914
0x18001d907  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18001d90c  mov     rcx, rbx; lpTlsValue
0x18001d90f  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x18001d914  mov     [rbx+10h], r15
0x18001d918  lea     r8, [rbp+arg_8]
0x18001d91c  cmp     [rbp+arg_0], 80004002h
0x18001d923  lea     rdx, [rbp+var_28]
0x18001d927  mov     rcx, rsi
0x18001d92a  jz      short loc_18001D95B
0x18001d92c  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18001d931  mov     rcx, rbx; void *
0x18001d934  mov     rsi, [rax]
0x18001d937  cmp     qword ptr [rsi+18h], 0
0x18001d93c  jnz     short loc_18001D973
0x18001d93e  mov     rax, [rbp+arg_10]
0x18001d942  mov     r8, rdi; struct CFlat::ComImportAdapter *
0x18001d945  mov     [rsi+18h], rax
0x18001d949  mov     rdx, [rbp+arg_10]; void *
0x18001d94d  call    ?AddCachedComImportAdapter@EntryExit@CFlat@@SAXPEAX0PEAVComImportAdapter@2@@Z; CFlat::EntryExit::AddCachedComImportAdapter(void *,void *,CFlat::ComImportAdapter *)
0x18001d952  mov     r8, [rsi+18h]
0x18001d956  jmp     loc_18001D884
0x18001d95b  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18001d960  xor     r8d, r8d
0x18001d963  mov     rcx, [rax]
0x18001d966  mov     qword ptr [rcx+18h], 0
0x18001d96e  jmp     loc_18001D884
0x18001d973  mov     rdx, [rbp+arg_10]; void *
0x18001d977  call    ?ReleaseComInterfaceFromCFlatCode@EntryExit@CFlat@@SAXPEAX0@Z; CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(void *,void *)
0x18001d97c  jmp     short loc_18001D952
```
