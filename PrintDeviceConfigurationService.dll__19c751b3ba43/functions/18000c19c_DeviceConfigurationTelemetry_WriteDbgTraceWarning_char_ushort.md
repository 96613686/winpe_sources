# DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *,ushort *,...)

- ea: `0x18000c19c`
- end: `0x18000c23e`
- name: `?WriteDbgTraceWarning@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ`
- size: `162`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c42c`
- `0x180010b10`
- `0x18001260c`
- `0x18001497c`

## callees

- `0x1800020c0`
- `0x180008fb0`
- `0x18000ac9c`
- `0x18000afcc`
- `0x18000bf54`
- `0x18000c19c`
- `0x1800164c0`

## pseudocode

```c
void DeviceConfigurationTelemetry::WriteDbgTraceWarning(char *a1, unsigned __int16 *a2, ...)
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
    DeviceConfigurationTelemetry::LogDbgTraceWarning_(v5, a1, v6);
  }
}

```

## disassembly

```asm
0x18000c19c  mov     [rsp+arg_8], rdx
0x18000c1a1  mov     qword ptr [rsp+arg_10], r8
0x18000c1a6  mov     [rsp+arg_18], r9
0x18000c1ab  push    rbx
0x18000c1ac  mov     eax, 2040h
0x18000c1b1  call    _alloca_probe
0x18000c1b6  sub     rsp, rax
0x18000c1b9  mov     rax, cs:__security_cookie
0x18000c1c0  xor     rax, rsp
0x18000c1c3  mov     [rsp+2048h+var_18], rax
0x18000c1cb  mov     rbx, rcx
0x18000c1ce  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000c1d3  test    al, al
0x18000c1d5  jz      short loc_18000C225
0x18000c1d7  mov     r8, [rsp+2048h+arg_8]; unsigned __int16 *
0x18000c1df  lea     r9, [rsp+2048h+arg_10]; char *
0x18000c1e7  mov     edx, 1000h; unsigned __int64
0x18000c1ec  mov     [rsp+2048h+var_2028], 0
0x18000c1f5  lea     rcx, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000c1fa  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000c1ff  test    eax, eax
0x18000c201  js      short loc_18000C225
0x18000c203  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000c208  test    al, al
0x18000c20a  jz      short loc_18000C225
0x18000c20c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0266e7cb468ca894dc8f9195a1f762c1_@@CA@XZ; _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_(void)
0x18000c213  call    ?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))
0x18000c218  lea     r8, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000c21d  mov     rdx, rbx; char *
0x18000c220  call    ?LogDbgTraceWarning_@DeviceConfigurationTelemetry@@QEAAXPEBDPEBG@Z; DeviceConfigurationTelemetry::LogDbgTraceWarning_(char const *,ushort const *)
0x18000c225  mov     rcx, [rsp+2048h+var_18]
0x18000c22d  xor     rcx, rsp; StackCookie
0x18000c230  call    __security_check_cookie
0x18000c235  add     rsp, 2040h
0x18000c23c  pop     rbx
0x18000c23d  retn
```
