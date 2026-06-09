# tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::ensure_data(void)

- ea: `0x1800a3e88`
- end: `0x1800a3ee1`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a2b64`
- `0x1800a2b8c`
- `0x1800a418c`

## callees

- `0x180012ab4`
- `0x1800a2914`
- `0x1800a2a60`
- `0x1800a351c`
- `0x1800a3e88`

## import_xrefs

- `OLE32!CoTaskMemAlloc` at `0x1800a3e9c`
- `OLE32!CoTaskMemAlloc` at `0x1800a3e9c`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x120u);
    if ( !v2 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x1800a3e88  push    rbx
0x1800a3e8a  sub     rsp, 20h
0x1800a3e8e  cmp     qword ptr [rcx], 0
0x1800a3e92  mov     rbx, rcx
0x1800a3e95  jnz     short loc_1800A3ED2
0x1800a3e97  mov     ecx, 120h; cb
0x1800a3e9c  call    cs:__imp_CoTaskMemAlloc
0x1800a3ea2  test    rax, rax
0x1800a3ea5  jz      short loc_1800A3EDB
0x1800a3ea7  mov     rcx, rax
0x1800a3eaa  call    ??0?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>(void)
0x1800a3eaf  mov     rcx, [rbx]; pv
0x1800a3eb2  mov     [rsp+28h+arg_0], 0
0x1800a3ebb  mov     [rbx], rax
0x1800a3ebe  test    rcx, rcx
0x1800a3ec1  jz      short loc_1800A3EC8
0x1800a3ec3  call    ?Release@?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>::Release(void)
0x1800a3ec8  lea     rcx, [rsp+28h+arg_0]
0x1800a3ecd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>,wil::err_returncode_policy>(void)
0x1800a3ed2  mov     rax, rbx
0x1800a3ed5  add     rsp, 20h
0x1800a3ed9  pop     rbx
0x1800a3eda  retn
0x1800a3edb  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
