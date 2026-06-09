# tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::ensure_data(void)

- ea: `0x18001303c`
- end: `0x180013095`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: `void **__fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010ca4`
- `0x180012890`

## callees

- `0x180009390`
- `0x18000b480`
- `0x18000cab8`
- `0x180010460`
- `0x18001303c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013050`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x128u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x18001303c  push    rbx
0x18001303e  sub     rsp, 20h
0x180013042  cmp     qword ptr [rcx], 0
0x180013046  mov     rbx, rcx
0x180013049  jnz     short loc_18001308C
0x18001304b  mov     ecx, 128h; cb
0x180013050  call    cs:__imp_CoTaskMemAlloc
0x180013056  test    rax, rax
0x180013059  jnz     short loc_180013061
0x18001305b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013061  mov     rcx, rax
0x180013064  call    ??0?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>(void)
0x180013069  mov     rcx, [rbx]; pv
0x18001306c  mov     [rsp+28h+arg_0], 0
0x180013075  mov     [rbx], rax
0x180013078  test    rcx, rcx
0x18001307b  jz      short loc_180013082
0x18001307d  call    ?Release@?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(void)
0x180013082  lea     rcx, [rsp+28h+arg_0]
0x180013087  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>(void)
0x18001308c  mov     rax, rbx
0x18001308f  add     rsp, 20h
0x180013093  pop     rbx
0x180013094  retn
```
