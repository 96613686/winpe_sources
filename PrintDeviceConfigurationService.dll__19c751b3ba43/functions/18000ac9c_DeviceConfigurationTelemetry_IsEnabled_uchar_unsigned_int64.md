# DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)

- ea: `0x18000ac9c`
- end: `0x18000acd1`
- name: `?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z`
- size: `53`
- prototype: `bool __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ae04`
- `0x18000aeac`
- `0x18000c19c`
- `0x18000ed18`

## callees

- `0x18000172c`
- `0x18000ac9c`
- `0x18000afcc`

## pseudocode

```c
bool __fastcall DeviceConfigurationTelemetry::IsEnabled(__int64 a1)
{
  _DWORD *v1; // rcx

  v1 = (_DWORD *)wil::details::static_lazy<DeviceConfigurationTelemetry>::get(
                   a1,
                   (void (__cdecl *)())_lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_)[1];
  return v1 && *v1 && (unsigned __int8)tlgKeywordOn(v1, 0);
}

```

## disassembly

```asm
0x18000ac9c  sub     rsp, 28h
0x18000aca0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0266e7cb468ca894dc8f9195a1f762c1_@@CA@XZ; _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_(void)
0x18000aca7  call    ?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))
0x18000acac  mov     rcx, [rax+8]
0x18000acb0  test    rcx, rcx
0x18000acb3  jz      short loc_18000ACCA
0x18000acb5  mov     eax, [rcx]
0x18000acb7  test    eax, eax
0x18000acb9  jz      short loc_18000ACCA
0x18000acbb  xor     edx, edx
0x18000acbd  call    _tlgKeywordOn
0x18000acc2  test    al, al
0x18000acc4  jz      short loc_18000ACCA
0x18000acc6  mov     al, 1
0x18000acc8  jmp     short loc_18000ACCC
0x18000acca  xor     al, al
0x18000accc  add     rsp, 28h
0x18000acd0  retn
```
