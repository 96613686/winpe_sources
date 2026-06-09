# tip2::tip_test<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::start_and_watch_errors(void)

- ea: `0x140017e98`
- end: `0x140017f5a`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e7ec`

## callees

- `0x14000b524`
- `0x14000d83c`
- `0x14000da20`
- `0x14000e004`
- `0x140013d50`
- `0x14001659c`
- `0x1400172d0`
- `0x140017c9c`
- `0x140017e98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017ed0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140017ed0`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>>::start_and_watch_errors(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>(&v12);
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
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 280));
  return a2;
}

```

## disassembly

```asm
0x140017e98  mov     [rsp+arg_8], rbx
0x140017e9d  push    rdi
0x140017e9e  sub     rsp, 30h
0x140017ea2  mov     rbx, rcx
0x140017ea5  mov     rdi, rdx
0x140017ea8  mov     rcx, [rcx]
0x140017eab  test    rcx, rcx
0x140017eae  jz      short loc_140017EC5
0x140017eb0  add     rcx, 8
0x140017eb4  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x140017eb9  test    al, al
0x140017ebb  jz      short loc_140017EC5
0x140017ebd  mov     rcx, rbx
0x140017ec0  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::reset(void)
0x140017ec5  cmp     qword ptr [rbx], 0
0x140017ec9  jnz     short loc_140017F06
0x140017ecb  mov     ecx, 120h; cb
0x140017ed0  call    cs:__imp_CoTaskMemAlloc
0x140017ed6  test    rax, rax
0x140017ed9  jz      short loc_140017F54
0x140017edb  mov     rcx, rax
0x140017ede  call    ??0?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>(void)
0x140017ee3  mov     rcx, [rbx]; pv
0x140017ee6  mov     [rsp+38h+arg_0], 0
0x140017eef  mov     [rbx], rax
0x140017ef2  test    rcx, rcx
0x140017ef5  jz      short loc_140017EFC
0x140017ef7  call    ?Release@?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>::Release(void)
0x140017efc  lea     rcx, [rsp+38h+arg_0]
0x140017f01  call    ??1?$com_ptr_t@V?$merged_data@U_tip_BatchedChunkImageTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BatchedChunkImageTipTest,_tip_BatchedChunkImageTipTest>,wil::err_returncode_policy>(void)
0x140017f06  mov     rcx, [rbx]
0x140017f09  lea     rdx, [rsp+38h+var_18]
0x140017f0e  add     rcx, 8
0x140017f12  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x140017f17  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::`vftable'
0x140017f1e  mov     r9b, 1; bool
0x140017f21  lea     rcx, [rdi+8]; this
0x140017f25  mov     [rdi], rax
0x140017f28  xor     r8d, r8d; struct wil::CallContextInfo *
0x140017f2b  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x140017f2e  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x140017f33  mov     rax, [rbx]
0x140017f36  mov     [rdi+38h], rax
0x140017f3a  test    rax, rax
0x140017f3d  jz      short loc_140017F46
0x140017f3f  lock inc dword ptr [rax+118h]
0x140017f46  mov     rbx, [rsp+38h+arg_8]
0x140017f4b  mov     rax, rdi
0x140017f4e  add     rsp, 30h
0x140017f52  pop     rdi
0x140017f53  retn
0x140017f54  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
