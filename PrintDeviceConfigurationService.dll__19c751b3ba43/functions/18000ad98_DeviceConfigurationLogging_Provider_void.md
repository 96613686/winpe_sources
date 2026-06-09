# DeviceConfigurationLogging::Provider(void)

- ea: `0x18000ad98`
- end: `0x18000adb1`
- name: `?Provider@DeviceConfigurationLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aaec`
- `0x18000acd8`
- `0x18000ad38`
- `0x18000bf54`
- `0x18000f510`

## callees

- `0x180009e60`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DeviceConfigurationLogging::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<DeviceConfigurationLogging>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_95f3d6cf0129e92bc2ffc8a01054732b_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x18000ad98  sub     rsp, 28h
0x18000ad9c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_95f3d6cf0129e92bc2ffc8a01054732b_@@CA@XZ; _lambda_95f3d6cf0129e92bc2ffc8a01054732b_::_lambda_invoker_cdecl_(void)
0x18000ada3  call    ?get@?$static_lazy@VDeviceConfigurationLogging@@@details@wil@@QEAAPEAVDeviceConfigurationLogging@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationLogging>::get(void (*)(void))
0x18000ada8  mov     rax, [rax+8]
0x18000adac  add     rsp, 28h
0x18000adb0  retn
```
