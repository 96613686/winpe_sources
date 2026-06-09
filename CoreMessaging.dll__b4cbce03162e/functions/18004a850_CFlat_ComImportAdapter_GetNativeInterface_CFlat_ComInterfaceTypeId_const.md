# CFlat::ComImportAdapter::GetNativeInterface$(CFlat::ComInterfaceTypeId const *)

- ea: `0x18004a850`
- end: `0x18004a971`
- name: `?GetNativeInterface$@ComImportAdapter@CFlat@@QEAAPEAXPEBUComInterfaceTypeId@2@@Z`
- size: `289`
- prototype: `void *__fastcall(CFlat::ComImportAdapter *__hidden this, const struct CFlat::ComInterfaceTypeId *)`
- caller_count: `20`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180008160`
- `0x180008354`
- `0x18001ebcc`
- `0x180020550`
- `0x18004b320`
- `0x18004bd7c`
- `0x180090a8c`
- `0x180090f60`
- `0x180091834`
- `0x180091dfc`
- `0x180094e50`
- `0x18009515c`
- `0x1800958e4`
- `0x180097504`
- `0x180098f40`
- `0x180099e58`
- `0x18009b020`
- `0x18009b2b0`
- `0x18009bfc4`
- `0x18009cbd0`

## callees

- `0x1800067f0`
- `0x1800080a8`
- `0x180009750`
- `0x180021bfc`
- `0x180048a20`
- `0x18004a348`
- `0x18004a850`
- `0x18004aa90`
- `0x1800a6888`
- `0x1800c7e58`
- `0x1800c7eec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a898`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004a898`

## pseudocode

```c
void *__fastcall CFlat::ComImportAdapter::GetNativeInterface$(
        CFlat::ComImportAdapter *this,
        const struct CFlat::ComInterfaceTypeId *a2)
{
  char *v2; // rsi
  void *result; // rax
  _QWORD *Value; // rbx
  void *v6; // r14
  __int64 v7; // rax
  Cn::Engine::Lock *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rcx
  _BYTE v12[32]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+80h] [rbp+30h] BYREF
  const struct CFlat::ComInterfaceTypeId *v14; // [rsp+88h] [rbp+38h] BYREF
  void *v15; // [rsp+90h] [rbp+40h] BYREF
  __int64 v16; // [rsp+98h] [rbp+48h] BYREF

  v14 = a2;
  v2 = (char *)this + 32;
  std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(
    (char *)this + 32,
    &v16,
    &v14);
  if ( v16 != *((_QWORD *)this + 5) )
    return *(void **)(v16 + 24);
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v6 = CFlat::EntryExit::ValidateCall(Value, *((void **)this + 3), 0);
  CFlat::EntryExit::OnBeginCallToNative(Value);
  v15 = 0;
  v13 = 0;
  v7 = lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_::_lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_(
         (unsigned int)v12,
         (unsigned int)&v13,
         (_DWORD)this,
         (unsigned int)&v14,
         (__int64)&v15);
  CFlat::SehSafe::Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___(Value, v7);
  v8 = (Cn::Engine::Lock *)Value[11];
  if ( v8 )
  {
    Cn::Engine::Lock::Enter(v8);
    Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
  }
  Value[2] = v6;
  if ( v13 == -2147467262 )
  {
    v11 = *(_QWORD *)std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
                       v2,
                       v12,
                       &v14);
    result = 0;
    *(_QWORD *)(v11 + 24) = 0;
  }
  else
  {
    v9 = std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(
           v2,
           v12,
           &v14);
    v10 = *(_QWORD *)v9;
    if ( *(_QWORD *)(*(_QWORD *)v9 + 24LL) )
    {
      CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(Value, v15);
    }
    else
    {
      *(_QWORD *)(v10 + 24) = v15;
      CFlat::EntryExit::AddCachedComImportAdapter(Value, v15, this);
    }
    return *(void **)(v10 + 24);
  }
  return result;
}

```

## disassembly

```asm
0x18004a850  mov     [rsp-28h+arg_8], rdx
0x18004a855  push    rbp
0x18004a856  push    rbx
0x18004a857  push    rsi
0x18004a858  push    rdi
0x18004a859  push    r14
0x18004a85b  mov     rbp, rsp
0x18004a85e  sub     rsp, 50h
0x18004a862  lea     rsi, [rcx+20h]
0x18004a866  mov     rdi, rcx
0x18004a869  mov     rcx, rsi
0x18004a86c  lea     r8, [rbp+arg_8]
0x18004a870  lea     rdx, [rbp+arg_18]
0x18004a874  call    ?find@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@std@@@std@@@2@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::find(CFlat::ComInterfaceTypeId const * const &)
0x18004a879  mov     rax, [rbp+arg_18]
0x18004a87d  cmp     rax, [rdi+28h]
0x18004a881  jz      short loc_18004A892
0x18004a883  mov     rax, [rax+18h]
0x18004a887  add     rsp, 50h
0x18004a88b  pop     r14
0x18004a88d  pop     rdi
0x18004a88e  pop     rsi
0x18004a88f  pop     rbx
0x18004a890  pop     rbp
0x18004a891  retn
0x18004a892  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18004a898  call    cs:__imp_TlsGetValue
0x18004a89e  mov     rdx, [rdi+18h]; void *
0x18004a8a2  xor     r8d, r8d; int
0x18004a8a5  mov     rcx, rax; void *
0x18004a8a8  mov     rbx, rax
0x18004a8ab  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x18004a8b0  mov     rcx, rbx; void *
0x18004a8b3  mov     r14, rax
0x18004a8b6  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x18004a8bb  lea     rax, [rbp+arg_10]
0x18004a8bf  mov     [rbp+arg_10], 0
0x18004a8c7  lea     r9, [rbp+arg_8]
0x18004a8cb  mov     [rsp+50h+var_30], rax
0x18004a8d0  mov     r8, rdi
0x18004a8d3  mov     [rbp+arg_0], 0
0x18004a8da  lea     rdx, [rbp+arg_0]
0x18004a8de  lea     rcx, [rbp+var_20]
0x18004a8e2  call    _lambda_9f26dbb50c5457f1a45ef1436d9c8d4d____lambda_9f26dbb50c5457f1a45ef1436d9c8d4d_
0x18004a8e7  mov     rdx, rax
0x18004a8ea  mov     rcx, rbx
0x18004a8ed  call    CFlat__SehSafe__Execute__lambda_9f26dbb50c5457f1a45ef1436d9c8d4d___
0x18004a8f2  mov     rcx, [rbx+58h]; this
0x18004a8f6  test    rcx, rcx
0x18004a8f9  jz      short loc_18004A908
0x18004a8fb  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x18004a900  mov     rcx, rbx; lpTlsValue
0x18004a903  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x18004a908  mov     [rbx+10h], r14
0x18004a90c  lea     r8, [rbp+arg_8]
0x18004a910  cmp     [rbp+arg_0], 80004002h
0x18004a917  lea     rdx, [rbp+var_20]
0x18004a91b  mov     rcx, rsi
0x18004a91e  jz      short loc_18004A94F
0x18004a920  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18004a925  mov     rcx, rbx; void *
0x18004a928  mov     rsi, [rax]
0x18004a92b  cmp     qword ptr [rsi+18h], 0
0x18004a930  jnz     short loc_18004A966
0x18004a932  mov     rax, [rbp+arg_10]
0x18004a936  mov     r8, rdi; struct CFlat::ComImportAdapter *
0x18004a939  mov     [rsi+18h], rax
0x18004a93d  mov     rdx, [rbp+arg_10]; void *
0x18004a941  call    ?AddCachedComImportAdapter@EntryExit@CFlat@@SAXPEAX0PEAVComImportAdapter@2@@Z; CFlat::EntryExit::AddCachedComImportAdapter(void *,void *,CFlat::ComImportAdapter *)
0x18004a946  mov     rax, [rsi+18h]
0x18004a94a  jmp     loc_18004A887
0x18004a94f  call    ??$_Try_emplace@AEBQEBUComInterfaceTypeId@CFlat@@$$V@?$_Hash@V?$_Umap_traits@PEBUComInterfaceTypeId@CFlat@@PEAXV?$_Uhash_compare@PEBUComInterfaceTypeId@CFlat@@U?$hash@PEBUComInterfaceTypeId@CFlat@@@std@@U?$equal_to@PEBUComInterfaceTypeId@CFlat@@@4@@std@@V?$Allocator@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEBUComInterfaceTypeId@CFlat@@PEAX@std@@PEAX@std@@_N@1@AEBQEBUComInterfaceTypeId@CFlat@@@Z; std::_Hash<std::_Umap_traits<CFlat::ComInterfaceTypeId const *,void *,std::_Uhash_compare<CFlat::ComInterfaceTypeId const *,std::hash<CFlat::ComInterfaceTypeId const *>,std::equal_to<CFlat::ComInterfaceTypeId const *>>,CFlat::Allocator<std::pair<CFlat::ComInterfaceTypeId const * const,void *>>,0>>::_Try_emplace<CFlat::ComInterfaceTypeId const * const &,>(CFlat::ComInterfaceTypeId const * const &)
0x18004a954  mov     rcx, [rax]
0x18004a957  xor     eax, eax
0x18004a959  mov     qword ptr [rcx+18h], 0
0x18004a961  jmp     loc_18004A887
0x18004a966  mov     rdx, [rbp+arg_10]; void *
0x18004a96a  call    ?ReleaseComInterfaceFromCFlatCode@EntryExit@CFlat@@SAXPEAX0@Z; CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(void *,void *)
0x18004a96f  jmp     short loc_18004A946
```
