# tip2::tip_test<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::start_and_watch_errors(void)

- ea: `0x14005f4d0`
- end: `0x14005f592`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005c850`

## callees

- `0x14000db48`
- `0x140032fa0`
- `0x14005b668`
- `0x14005ba44`
- `0x14005c888`
- `0x14005cb14`
- `0x14005dd54`
- `0x14005f354`
- `0x14005f4d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005f508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005f508`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::start_and_watch_errors(
        __int64 *a1,
        __int64 a2)
{
  char *v4; // rcx
  LPVOID v5; // rax
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v9; // rax
  char v11[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (char *)*a1;
  if ( v4 && (unsigned __int8)tip2::details::shared_data<0,0,0>::has_ever_started(v4 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x130u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>(&v12);
  }
  tip2::details::shared_data<0,0,0>::start(*a1 + 8, v11);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)(a2 + 8),
    (struct wil::details::IFailureCallback *)a2,
    0,
    1);
  v9 = *a1;
  *(_QWORD *)(a2 + 56) = *a1;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 296));
  return a2;
}

```

## disassembly

```asm
0x14005f4d0  mov     [rsp+arg_8], rbx
0x14005f4d5  push    rdi
0x14005f4d6  sub     rsp, 30h
0x14005f4da  mov     rbx, rcx
0x14005f4dd  mov     rdi, rdx
0x14005f4e0  mov     rcx, [rcx]
0x14005f4e3  test    rcx, rcx
0x14005f4e6  jz      short loc_14005F4FD
0x14005f4e8  add     rcx, 8
0x14005f4ec  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x14005f4f1  test    al, al
0x14005f4f3  jz      short loc_14005F4FD
0x14005f4f5  mov     rcx, rbx
0x14005f4f8  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::reset(void)
0x14005f4fd  cmp     qword ptr [rbx], 0
0x14005f501  jnz     short loc_14005F544
0x14005f503  mov     ecx, 130h; cb
0x14005f508  call    cs:__imp_CoTaskMemAlloc
0x14005f50e  test    rax, rax
0x14005f511  jnz     short loc_14005F519
0x14005f513  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14005f519  mov     rcx, rax
0x14005f51c  call    ??0?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>(void)
0x14005f521  mov     rcx, [rbx]; pv
0x14005f524  mov     [rsp+38h+arg_0], 0
0x14005f52d  mov     [rbx], rax
0x14005f530  test    rcx, rcx
0x14005f533  jz      short loc_14005F53A
0x14005f535  call    ?Release@?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::Release(void)
0x14005f53a  lea     rcx, [rsp+38h+arg_0]
0x14005f53f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>(void)
0x14005f544  mov     rcx, [rbx]
0x14005f547  lea     rdx, [rsp+38h+var_18]
0x14005f54c  add     rcx, 8
0x14005f550  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x14005f555  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::`vftable'
0x14005f55c  mov     r9b, 1; bool
0x14005f55f  lea     rcx, [rdi+8]; this
0x14005f563  mov     [rdi], rax
0x14005f566  xor     r8d, r8d; struct wil::CallContextInfo *
0x14005f569  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x14005f56c  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x14005f571  mov     rax, [rbx]
0x14005f574  mov     [rdi+38h], rax
0x14005f578  test    rax, rax
0x14005f57b  jz      short loc_14005F584
0x14005f57d  lock inc dword ptr [rax+128h]
0x14005f584  mov     rbx, [rsp+38h+arg_8]
0x14005f589  mov     rax, rdi
0x14005f58c  add     rsp, 30h
0x14005f590  pop     rdi
0x14005f591  retn
```
