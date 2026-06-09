# tip2::tip_test<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::start_and_watch_errors(void)

- ea: `0x14005f598`
- end: `0x14005f65a`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@2@XZ`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14005eb00`

## callees

- `0x14000db48`
- `0x140032fa0`
- `0x14005b668`
- `0x14005ba44`
- `0x14005c924`
- `0x14005cb30`
- `0x14005dd94`
- `0x14005f37c`
- `0x14005f598`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005f5d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005f5d0`

## pseudocode

```c
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::start_and_watch_errors(
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
    wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::reset(a1);
  if ( !*a1 )
  {
    v5 = CoTaskMemAlloc(0x120u);
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>(v5);
    v8 = (void *)*a1;
    v12 = 0;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::Release(v8);
    wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>(&v12);
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
0x14005f598  mov     [rsp+arg_8], rbx
0x14005f59d  push    rdi
0x14005f59e  sub     rsp, 30h
0x14005f5a2  mov     rbx, rcx
0x14005f5a5  mov     rdi, rdx
0x14005f5a8  mov     rcx, [rcx]
0x14005f5ab  test    rcx, rcx
0x14005f5ae  jz      short loc_14005F5C5
0x14005f5b0  add     rcx, 8
0x14005f5b4  call    ?has_ever_started@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::has_ever_started(void)
0x14005f5b9  test    al, al
0x14005f5bb  jz      short loc_14005F5C5
0x14005f5bd  mov     rcx, rbx
0x14005f5c0  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::reset(void)
0x14005f5c5  cmp     qword ptr [rbx], 0
0x14005f5c9  jnz     short loc_14005F606
0x14005f5cb  mov     ecx, 120h; cb
0x14005f5d0  call    cs:__imp_CoTaskMemAlloc
0x14005f5d6  test    rax, rax
0x14005f5d9  jz      short loc_14005F654
0x14005f5db  mov     rcx, rax
0x14005f5de  call    ??0?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>(void)
0x14005f5e3  mov     rcx, [rbx]; pv
0x14005f5e6  mov     [rsp+38h+arg_0], 0
0x14005f5ef  mov     [rbx], rax
0x14005f5f2  test    rcx, rcx
0x14005f5f5  jz      short loc_14005F5FC
0x14005f5f7  call    ?Release@?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>::Release(void)
0x14005f5fc  lea     rcx, [rsp+38h+arg_0]
0x14005f601  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>(void)
0x14005f606  mov     rcx, [rbx]
0x14005f609  lea     rdx, [rsp+38h+var_18]
0x14005f60e  add     rcx, 8
0x14005f612  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x14005f617  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_PixelFilterGetImageInfoTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_PixelFilterGetImageInfoTest,_tip_PixelFilterGetImageInfoTest>>::`vftable'
0x14005f61e  mov     r9b, 1; bool
0x14005f621  lea     rcx, [rdi+8]; this
0x14005f625  mov     [rdi], rax
0x14005f628  xor     r8d, r8d; struct wil::CallContextInfo *
0x14005f62b  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x14005f62e  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x14005f633  mov     rax, [rbx]
0x14005f636  mov     [rdi+38h], rax
0x14005f63a  test    rax, rax
0x14005f63d  jz      short loc_14005F646
0x14005f63f  lock inc dword ptr [rax+118h]
0x14005f646  mov     rbx, [rsp+38h+arg_8]
0x14005f64b  mov     rax, rdi
0x14005f64e  add     rsp, 30h
0x14005f652  pop     rdi
0x14005f653  retn
0x14005f654  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
