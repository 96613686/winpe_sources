# DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x18000aeac`
- end: `0x18000af4e`
- name: `?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ`
- size: `162`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `22`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000b0d0`
- `0x18000bac8`
- `0x18000c06c`
- `0x18000c42c`
- `0x18000c4a0`
- `0x18000c6e0`
- `0x18000da84`
- `0x18000db34`
- `0x18000dbe4`
- `0x18000ed18`
- `0x18000fad4`
- `0x18000fbe0`
- `0x180010ca4`
- `0x180011174`
- `0x180011c38`
- `0x18001445c`
- `0x18001481c`
- `0x18001497c`
- `0x180014c44`
- `0x180015088`
- `0x1800153bc`
- `0x180016284`

## callees

- `0x1800020c0`
- `0x180008fb0`
- `0x18000ac9c`
- `0x18000ad38`
- `0x18000aeac`
- `0x18000afcc`
- `0x1800164c0`

## pseudocode

```c
void DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
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
    DeviceConfigurationTelemetry::LogDbgTraceInfo_(v5, a1, v6);
  }
}

```

## disassembly

```asm
0x18000aeac  mov     [rsp+arg_8], rdx
0x18000aeb1  mov     qword ptr [rsp+arg_10], r8
0x18000aeb6  mov     [rsp+arg_18], r9
0x18000aebb  push    rbx
0x18000aebc  mov     eax, 2040h
0x18000aec1  call    _alloca_probe
0x18000aec6  sub     rsp, rax
0x18000aec9  mov     rax, cs:__security_cookie
0x18000aed0  xor     rax, rsp
0x18000aed3  mov     [rsp+2048h+var_18], rax
0x18000aedb  mov     rbx, rcx
0x18000aede  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000aee3  test    al, al
0x18000aee5  jz      short loc_18000AF35
0x18000aee7  mov     r8, [rsp+2048h+arg_8]; unsigned __int16 *
0x18000aeef  lea     r9, [rsp+2048h+arg_10]; char *
0x18000aef7  mov     edx, 1000h; unsigned __int64
0x18000aefc  mov     [rsp+2048h+var_2028], 0
0x18000af05  lea     rcx, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000af0a  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000af0f  test    eax, eax
0x18000af11  js      short loc_18000AF35
0x18000af13  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000af18  test    al, al
0x18000af1a  jz      short loc_18000AF35
0x18000af1c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0266e7cb468ca894dc8f9195a1f762c1_@@CA@XZ; _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_(void)
0x18000af23  call    ?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))
0x18000af28  lea     r8, [rsp+2048h+var_2018]; unsigned __int16 *
0x18000af2d  mov     rdx, rbx; char *
0x18000af30  call    ?LogDbgTraceInfo_@DeviceConfigurationTelemetry@@QEAAXPEBDPEBG@Z; DeviceConfigurationTelemetry::LogDbgTraceInfo_(char const *,ushort const *)
0x18000af35  mov     rcx, [rsp+2048h+var_18]
0x18000af3d  xor     rcx, rsp; StackCookie
0x18000af40  call    __security_check_cookie
0x18000af45  add     rsp, 2040h
0x18000af4c  pop     rbx
0x18000af4d  retn
```
