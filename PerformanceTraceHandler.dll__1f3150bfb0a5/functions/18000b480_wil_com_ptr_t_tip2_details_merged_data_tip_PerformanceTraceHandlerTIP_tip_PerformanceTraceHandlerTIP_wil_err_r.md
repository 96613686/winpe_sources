# wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>(void)

- ea: `0x18000b480`
- end: `0x18000b496`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b5e8`
- `0x180010a90`
- `0x180010ac8`
- `0x18001303c`

## callees

- `0x18000b480`
- `0x18000cab8`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>(
        void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x18000b480  sub     rsp, 28h
0x18000b484  mov     rcx, [rcx]; pv
0x18000b487  test    rcx, rcx
0x18000b48a  jz      short loc_18000B491
0x18000b48c  call    ?Release@?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(void)
0x18000b491  add     rsp, 28h
0x18000b495  retn
```
