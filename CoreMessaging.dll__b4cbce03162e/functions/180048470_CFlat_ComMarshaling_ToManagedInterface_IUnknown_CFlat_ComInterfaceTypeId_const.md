# CFlat::ComMarshaling::ToManagedInterface(IUnknown *,CFlat::ComInterfaceTypeId const *)

- ea: `0x180048470`
- end: `0x180048652`
- name: `?ToManagedInterface@ComMarshaling@CFlat@@SA?AV?$SmartPtr@VObject@System@@@2@PEAUIUnknown@@PEBUComInterfaceTypeId@2@@Z`
- size: `482`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180048400`
- `0x18006e37c`
- `0x18006e660`
- `0x180090a20`
- `0x1800934ac`
- `0x180093a90`
- `0x180094280`
- `0x180095eb0`
- `0x1800983cc`
- `0x1800ac058`
- `0x1800ac0bc`

## callees

- `0x180001db4`
- `0x1800067f0`
- `0x1800080a8`
- `0x180009750`
- `0x180010ed0`
- `0x180021bfc`
- `0x180025234`
- `0x180048470`
- `0x180048658`
- `0x180048a20`
- `0x180049ca8`
- `0x180049d04`
- `0x18008ae1c`
- `0x18008b758`
- `0x1800a22c4`
- `0x1800a6298`
- `0x1800c7ff0`
- `0x1800c8050`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800484a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800484a3`

## pseudocode

```c
System::Object **__fastcall CFlat::ComMarshaling::ToManagedInterface(
        System::Object **a1,
        struct IUnknown *a2,
        const struct CFlat::ComInterfaceTypeId *a3)
{
  _QWORD *Value; // rdi
  struct IUnknown *v6; // r14
  void *v8; // r15
  struct System::Object *ObjectFromExportAdapter; // r14
  Cn::Engine::Lock *v10; // rcx
  __int64 v11; // rax
  const char16_t *v12; // rcx
  void *v13; // r14
  __int64 v14; // rax
  Cn::Engine::Lock *v15; // rcx
  char v16; // bl
  bool v17; // r14
  System::Object *v18; // [rsp+20h] [rbp-40h] BYREF
  void *v19; // [rsp+28h] [rbp-38h] BYREF
  struct IUnknown *v20; // [rsp+30h] [rbp-30h] BYREF
  __int64 v21; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v22[32]; // [rsp+40h] [rbp-20h] BYREF
  struct IUnknown *v23; // [rsp+98h] [rbp+38h] BYREF
  int v24; // [rsp+A8h] [rbp+48h] BYREF

  v23 = a2;
  if ( !a2 )
  {
    *a1 = 0;
    return a1;
  }
  Value = TlsGetValue(Cn::Context::s_tlsStorage);
  v18 = 0;
  v6 = v23;
  v20 = v23;
  std::_Hash<std::_Umap_traits<void *,CFlat::ComImportAdapter *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,CFlat::Allocator<std::pair<void * const,CFlat::ComImportAdapter *>>,0>>::find(
    Value + 15,
    &v21,
    &v20);
  if ( v21 != Value[16] )
  {
    CFlat::SmartPtr<Microsoft::CoreUI::ExportEndpointHandler>::operator=(&v18, *(_QWORD *)(v21 + 24));
LABEL_4:
    *a1 = v18;
    return a1;
  }
  v8 = CFlat::EntryExit::ValidateCall(Value, v6, 0);
  CFlat::EntryExit::OnBeginCallToNative(Value);
  ObjectFromExportAdapter = CFlat::ComMarshaling::TryGetObjectFromExportAdapter(v23, Value);
  if ( !ObjectFromExportAdapter )
  {
    v19 = 0;
    v24 = 0;
    v11 = lambda_f7e478493cd4c7e6a5c3d3065f952319_::_lambda_f7e478493cd4c7e6a5c3d3065f952319_(v22, &v24, &v23, &v19);
    CFlat::SehSafe::Execute__lambda_817f165e172d7536dd28b0480abcc310___(Value, v11);
    if ( v24 )
      CFlat::Abandonment::Fail(v12);
    v13 = CFlat::EntryExit::ValidateCall(0, v23, 1);
    v14 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v21, &v23);
    CFlat::SehSafe::Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___(Value, v14);
    v15 = (Cn::Engine::Lock *)Value[11];
    if ( v15 )
    {
      Cn::Engine::Lock::Enter(v15);
      Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
    }
    Value[2] = v13;
    v16 = Cn::ImportAdapterCache::GetOrAdd(Value + 15, v19, &v18);
    v17 = CFlat::ComImportAdapter::TryAddNativeInterface$(v18, Value, a3, v23);
    if ( v16 )
      CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(Value, v19);
    if ( !v17 )
      CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(Value, v23);
    goto LABEL_4;
  }
  v10 = (Cn::Engine::Lock *)Value[11];
  if ( v10 )
  {
    Cn::Engine::Lock::Enter(v10);
    Cn::Context::SetCurrentContext((struct Cn::Context *)Value);
  }
  Value[2] = v8;
  CFlat::SmartPtr<System::Action$2<CFlat::SmartPtr<System::Object>,bool>>::SmartPtr<System::Action$2<CFlat::SmartPtr<System::Object>,bool>>(
    a1,
    ObjectFromExportAdapter);
  if ( v18 )
    System::Object::Release$(v18);
  return a1;
}

```

## disassembly

```asm
0x180048470  mov     [rsp-28h+arg_0], rbx
0x180048475  mov     [rsp-28h+arg_10], rsi
0x18004847a  mov     [rsp-28h+arg_8], rdx
0x18004847f  push    rbp
0x180048480  push    rdi
0x180048481  push    r12
0x180048483  push    r14
0x180048485  push    r15
0x180048487  mov     rbp, rsp
0x18004848a  sub     rsp, 60h
0x18004848e  mov     r12, r8
0x180048491  mov     rsi, rcx
0x180048494  test    rdx, rdx
0x180048497  jz      loc_180048632
0x18004849d  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x1800484a3  call    cs:__imp_TlsGetValue
0x1800484a9  mov     rdi, rax
0x1800484ac  mov     [rbp+var_40], 0
0x1800484b4  mov     r14, [rbp+arg_8]
0x1800484b8  mov     [rbp+var_30], r14
0x1800484bc  lea     r8, [rbp+var_30]
0x1800484c0  lea     rdx, [rbp+var_28]
0x1800484c4  lea     rcx, [rax+78h]
0x1800484c8  call    ?find@?$_Hash@V?$_Umap_traits@PEAXPEAVComImportAdapter@CFlat@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@std@@V?$Allocator@U?$pair@QEAXPEAVComImportAdapter@CFlat@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXPEAVComImportAdapter@CFlat@@@std@@@std@@@std@@@2@AEBQEAX@Z; std::_Hash<std::_Umap_traits<void *,CFlat::ComImportAdapter *,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,CFlat::Allocator<std::pair<void * const,CFlat::ComImportAdapter *>>,0>>::find(void * const &)
0x1800484cd  mov     rdx, [rbp+var_28]
0x1800484d1  cmp     rdx, [rdi+80h]
0x1800484d8  jz      short loc_18004850A
0x1800484da  mov     rdx, [rdx+18h]
0x1800484de  lea     rcx, [rbp+var_40]
0x1800484e2  call    ??4?$SmartPtr@VExportEndpointHandler@CoreUI@Microsoft@@@CFlat@@QEAAAEAV01@PEAVExportEndpointHandler@CoreUI@Microsoft@@@Z; CFlat::SmartPtr<Microsoft::CoreUI::ExportEndpointHandler>::operator=(Microsoft::CoreUI::ExportEndpointHandler *)
0x1800484e7  mov     rax, [rbp+var_40]
0x1800484eb  mov     [rsi], rax
0x1800484ee  mov     rax, rsi
0x1800484f1  lea     r11, [rsp+60h+var_s0]
0x1800484f6  mov     rbx, [r11+30h]
0x1800484fa  mov     rsi, [r11+40h]
0x1800484fe  mov     rsp, r11
0x180048501  pop     r15
0x180048503  pop     r14
0x180048505  pop     r12
0x180048507  pop     rdi
0x180048508  pop     rbp
0x180048509  retn
0x18004850a  xor     r8d, r8d; int
0x18004850d  mov     rdx, r14; void *
0x180048510  mov     rcx, rdi; void *
0x180048513  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x180048518  mov     r15, rax
0x18004851b  mov     rcx, rdi; void *
0x18004851e  call    ?OnBeginCallToNative@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnBeginCallToNative(void *)
0x180048523  mov     rdx, rdi; void *
0x180048526  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18004852a  call    ?TryGetObjectFromExportAdapter@ComMarshaling@CFlat@@SAPEAVObject@System@@PEAUIUnknown@@PEAX@Z; CFlat::ComMarshaling::TryGetObjectFromExportAdapter(IUnknown *,void *)
0x18004852f  mov     r14, rax
0x180048532  test    rax, rax
0x180048535  jz      short loc_18004856C
0x180048537  mov     rcx, [rdi+58h]; this
0x18004853b  test    rcx, rcx
0x18004853e  jz      short loc_18004854D
0x180048540  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x180048545  mov     rcx, rdi; lpTlsValue
0x180048548  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x18004854d  mov     [rdi+10h], r15
0x180048551  mov     rdx, r14
0x180048554  mov     rcx, rsi
0x180048557  call    ??0?$SmartPtr@V?$Action$2@V?$SmartPtr@VObject@System@@@CFlat@@_N@System@@@CFlat@@QEAA@PEAV?$Action$2@V?$SmartPtr@VObject@System@@@CFlat@@_N@System@@@Z; CFlat::SmartPtr<System::Action$2<CFlat::SmartPtr<System::Object>,bool>>::SmartPtr<System::Action$2<CFlat::SmartPtr<System::Object>,bool>>(System::Action$2<CFlat::SmartPtr<System::Object>,bool> *)
0x18004855c  mov     rcx, [rbp+var_40]; this
0x180048560  test    rcx, rcx
0x180048563  jz      short loc_1800484EE
0x180048565  call    ?Release$@Object@System@@AEAAXXZ; System::Object::Release$(void)
0x18004856a  jmp     short loc_1800484EE
0x18004856c  mov     [rbp+var_38], 0
0x180048574  mov     [rbp+arg_18], 0
0x18004857b  lea     r9, [rbp+var_38]
0x18004857f  lea     r8, [rbp+arg_8]
0x180048583  lea     rdx, [rbp+arg_18]
0x180048587  lea     rcx, [rbp+var_20]
0x18004858b  call    _lambda_f7e478493cd4c7e6a5c3d3065f952319____lambda_f7e478493cd4c7e6a5c3d3065f952319_
0x180048590  mov     rdx, rax
0x180048593  mov     rcx, rdi
0x180048596  call    CFlat__SehSafe__Execute__lambda_817f165e172d7536dd28b0480abcc310___
0x18004859b  cmp     [rbp+arg_18], 0
0x18004859f  jnz     loc_18004863E
0x1800485a5  mov     r8d, 1; int
0x1800485ab  mov     rdx, [rbp+arg_8]; void *
0x1800485af  xor     ecx, ecx; void *
0x1800485b1  call    ?ValidateCall@EntryExit@CFlat@@SAPEAXPEAX0H@Z; CFlat::EntryExit::ValidateCall(void *,void *,int)
0x1800485b6  mov     r14, rax
0x1800485b9  lea     rdx, [rbp+arg_8]
0x1800485bd  lea     rcx, [rbp+var_28]
0x1800485c1  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800485c6  mov     rdx, rax
0x1800485c9  mov     rcx, rdi
0x1800485cc  call    CFlat__SehSafe__Execute__lambda_707e52aa1c4238b763f1e5fddd3a6954___
0x1800485d1  mov     rcx, [rdi+58h]; this
0x1800485d5  test    rcx, rcx
0x1800485d8  jz      short loc_1800485E7
0x1800485da  call    ?Enter@Lock@Engine@Cn@@QEAAXXZ; Cn::Engine::Lock::Enter(void)
0x1800485df  mov     rcx, rdi; lpTlsValue
0x1800485e2  call    ?SetCurrentContext@Context@Cn@@CAXPEAV12@@Z; Cn::Context::SetCurrentContext(Cn::Context *)
0x1800485e7  mov     [rdi+10h], r14
0x1800485eb  lea     r8, [rbp+var_40]
0x1800485ef  mov     rdx, [rbp+var_38]
0x1800485f3  lea     rcx, [rdi+78h]
0x1800485f7  call    ?GetOrAdd@ImportAdapterCache@Cn@@QEAA_NPEAXAEAV?$SmartPtr@VComImportAdapter@CFlat@@@CFlat@@@Z; Cn::ImportAdapterCache::GetOrAdd(void *,CFlat::SmartPtr<CFlat::ComImportAdapter> &)
0x1800485fc  mov     bl, al
0x1800485fe  mov     r9, [rbp+arg_8]; void *
0x180048602  mov     r8, r12; struct CFlat::ComInterfaceTypeId *
0x180048605  mov     rdx, rdi; void *
0x180048608  mov     rcx, [rbp+var_40]; this
0x18004860c  call    ?TryAddNativeInterface$@ComImportAdapter@CFlat@@QEAA_NPEAXPEBUComInterfaceTypeId@2@0@Z; CFlat::ComImportAdapter::TryAddNativeInterface$(void *,CFlat::ComInterfaceTypeId const *,void *)
0x180048611  mov     r14b, al
0x180048614  test    bl, bl
0x180048616  jnz     short loc_180048644
0x180048618  test    r14b, r14b
0x18004861b  jnz     loc_1800484E7
0x180048621  mov     rdx, [rbp+arg_8]; void *
0x180048625  mov     rcx, rdi; void *
0x180048628  call    ?ReleaseComInterfaceFromCFlatCode@EntryExit@CFlat@@SAXPEAX0@Z; CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(void *,void *)
0x18004862d  jmp     loc_1800484E7
0x180048632  mov     qword ptr [rcx], 0
0x180048639  jmp     loc_1800484EE
0x18004863e  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
0x180048644  mov     rdx, [rbp+var_38]; void *
0x180048648  mov     rcx, rdi; void *
0x18004864b  call    ?ReleaseComInterfaceFromCFlatCode@EntryExit@CFlat@@SAXPEAX0@Z; CFlat::EntryExit::ReleaseComInterfaceFromCFlatCode(void *,void *)
0x180048650  jmp     short loc_180048618
```
