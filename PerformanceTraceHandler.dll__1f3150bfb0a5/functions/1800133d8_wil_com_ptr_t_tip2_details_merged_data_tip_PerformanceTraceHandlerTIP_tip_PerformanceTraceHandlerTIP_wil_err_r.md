# wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::reset(void)

- ea: `0x1800133d8`
- end: `0x1800133f8`
- name: `?reset@?$com_ptr_t@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ`
- size: `32`
- prototype: `volatile signed __int32 *__fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010a90`
- `0x180012890`

## callees

- `0x18000cab8`
- `0x1800133d8`

## pseudocode

```c
volatile signed __int32 *__fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>,wil::err_returncode_policy>::reset(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return (volatile signed __int32 *)tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(result);
  return result;
}

```

## disassembly

```asm
0x1800133d8  sub     rsp, 28h
0x1800133dc  mov     rax, [rcx]
0x1800133df  mov     qword ptr [rcx], 0
0x1800133e6  test    rax, rax
0x1800133e9  jz      short loc_1800133F3
0x1800133eb  mov     rcx, rax; pv
0x1800133ee  call    ?Release@?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>::Release(void)
0x1800133f3  add     rsp, 28h
0x1800133f7  retn
```
