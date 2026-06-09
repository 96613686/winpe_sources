# DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)

- ea: `0x18000ae04`
- end: `0x18000aea6`
- name: `?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ`
- size: `162`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `14`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b0d0`
- `0x18000c6e0`
- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`
- `0x18000ed18`
- `0x18000fad4`
- `0x18000fbe0`
- `0x180010b10`
- `0x180010ca4`
- `0x180010e44`
- `0x180013e50`
- `0x18001445c`
- `0x180014e28`

## callees

- `0x1800020c0`
- `0x180008fb0`
- `0x18000ac9c`
- `0x18000acd8`
- `0x18000ae04`
- `0x18000afcc`
- `0x1800164c0`

## pseudocode

```c
void DeviceConfigurationTelemetry::WriteDbgTraceError(char *a1, unsigned __int16 *a2, ...)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  DeviceConfigurationTelemetry *v5; // rcx
  unsigned __int16 v6[4096]; // [rsp+30h] [rbp-2018h] BYREF
  va_list va; // [rsp+2060h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( DeviceConfigurationTelemetry::IsEnabled((__int64)a1)
    && StringCchVPrintfW(v6, 0x1000u, a2, va) >= 0
    && DeviceConfigurationTelemetry::IsEnabled(v3) )
  {
    wil::details::static_lazy<DeviceConfigurationTelemetry>::get(
      v4,
      (void (__cdecl *)())_lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_);
    DeviceConfigurationTelemetry::LogDbgTraceError_(v5, a1, v6);
  }
}

```

## disassembly

```asm
0x18000ae04  mov     [rsp+arg_8], rdx
0x18000ae09  mov     qword ptr [rsp+arg_10], r8
0x18000ae0e  mov     [rsp+arg_18], r9
0x18000ae13  push    rbx
0x18000ae14  mov     eax, 2040h
0x18000ae19  call    _alloca_probe
0x18000ae1e  sub     rsp, rax
0x18000ae21  mov     rax, cs:__security_cookie
0x18000ae28  xor     rax, rsp
0x18000ae2b  mov     [rsp+2048h+var_18], rax
0x18000ae33  mov     rbx, rcx
0x18000ae36  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000ae3b  test    al, al
0x18000ae3d  jz      short loc_18000AE8D
0x18000ae3f  mov     r8, [rsp+2048h+arg_8]; unsigned __int16 *
0x18000ae47  lea     r9, [rsp+2048h+arg_10]; char *
0x18000ae4f  mov     edx, 1000h; unsigned __int64
0x18000ae54  mov     [rsp+2048h+var_2028], 0
0x18000ae5d  lea     rcx, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000ae62  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000ae67  test    eax, eax
0x18000ae69  js      short loc_18000AE8D
0x18000ae6b  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000ae70  test    al, al
0x18000ae72  jz      short loc_18000AE8D
0x18000ae74  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0266e7cb468ca894dc8f9195a1f762c1_@@CA@XZ; _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_(void)
0x18000ae7b  call    ?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))
0x18000ae80  lea     r8, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000ae85  mov     rdx, rbx; char *
0x18000ae88  call    ?LogDbgTraceError_@DeviceConfigurationTelemetry@@QEAAXPEBDPEBG@Z; DeviceConfigurationTelemetry::LogDbgTraceError_(char const *,ushort const *)
0x18000ae8d  mov     rcx, [rsp+2048h+var_18]
0x18000ae95  xor     rcx, rsp; StackCookie
0x18000ae98  call    __security_check_cookie
0x18000ae9d  add     rsp, 2040h
0x18000aea4  pop     rbx
0x18000aea5  retn
```
