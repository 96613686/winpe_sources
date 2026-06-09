# tip2::tip_test<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::start_and_watch_errors(void)

- ea: `0x1400463b0`
- end: `0x140046472`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400436b0`

## callees

- `0x14000b524`
- `0x14000da20`
- `0x14001659c`
- `0x140017c9c`
- `0x1400436e8`
- `0x140043974`
- `0x140044c04`
- `0x140046234`
- `0x1400463b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400463e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400463e8`

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
  void *v12; // [rsp+40h] [rbp+8h] BYREF

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
0x1400463b0  mov     [rsp+arg_8], rbx
0x1400463b5  push    rdi
0x1400463b6  sub     rsp, 30h
0x1400463ba  mov     rbx, rcx
0x1400463bd  mov     rdi, rdx
0x1400463c0  mov     rcx, [rcx]
0x1400463c3  test    rcx, rcx
0x1400463c6  jz      short loc_1400463DD
0x1400463c8  add     rcx, 8
0x1400463cc  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x1400463d1  test    al, al
0x1400463d3  jz      short loc_1400463DD
0x1400463d5  mov     rcx, rbx
0x1400463d8  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::reset(void)
0x1400463dd  cmp     qword ptr [rbx], 0
0x1400463e1  jnz     short loc_140046424
0x1400463e3  mov     ecx, 130h; cb
0x1400463e8  call    cs:__imp_CoTaskMemAlloc
0x1400463ee  test    rax, rax
0x1400463f1  jnz     short loc_1400463F9
0x1400463f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400463f9  mov     rcx, rax
0x1400463fc  call    ??0?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>(void)
0x140046401  mov     rcx, [rbx]; pv
0x140046404  mov     [rsp+38h+arg_0], 0
0x14004640d  mov     [rbx], rax
0x140046410  test    rcx, rcx
0x140046413  jz      short loc_14004641A
0x140046415  call    ?Release@?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>::Release(void)
0x14004641a  lea     rcx, [rsp+38h+arg_0]
0x14004641f  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>,wil::err_returncode_policy>(void)
0x140046424  mov     rcx, [rbx]
0x140046427  lea     rdx, [rsp+38h+var_18]
0x14004642c  add     rcx, 8
0x140046430  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x140046435  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::`vftable'
0x14004643c  mov     r9b, 1; bool
0x14004643f  lea     rcx, [rdi+8]; this
0x140046443  mov     [rdi], rax
0x140046446  xor     r8d, r8d; struct wil::CallContextInfo *
0x140046449  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x14004644c  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x140046451  mov     rax, [rbx]
0x140046454  mov     [rdi+38h], rax
0x140046458  test    rax, rax
0x14004645b  jz      short loc_140046464
0x14004645d  lock inc dword ptr [rax+128h]
0x140046464  mov     rbx, [rsp+38h+arg_8]
0x140046469  mov     rax, rdi
0x14004646c  add     rsp, 30h
0x140046470  pop     rdi
0x140046471  retn
```
