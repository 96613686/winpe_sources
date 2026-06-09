# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x180007d34`
- end: `0x180007d99`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180007c08`

## callees

- `0x1800077d8`
- `0x180007a84`
- `0x180007d34`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebx
  int v6; // esi
  _BYTE v8[56]; // [rsp+30h] [rbp-38h] BYREF

  v3 = a2;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v8,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
    wil_RtlStagingConfig_RecordFeatureUsage(*(unsigned int *)(a1 + 24), a3, (v3 >> 11) & 1);
  return v6 == 0;
}

```

## disassembly

```asm
0x180007d34  mov     [rsp+arg_18], rbx
0x180007d39  push    rbp
0x180007d3a  push    rsi
0x180007d3b  push    rdi
0x180007d3c  sub     rsp, 50h
0x180007d40  mov     r9, rdx
0x180007d43  mov     rbx, rdx
0x180007d46  mov     rdx, [rcx+8]
0x180007d4a  mov     rbp, rcx
0x180007d4d  shr     r9, 20h
0x180007d51  lea     rcx, [rsp+68h+var_38]
0x180007d56  mov     edi, r8d
0x180007d59  call    wil_details_FeatureReporting_RecordUsageInCache
0x180007d5e  mov     esi, [rax+10h]
0x180007d61  bt      ebx, 0Ah
0x180007d65  jnb     short loc_180007D82
0x180007d67  cmp     edi, 0FEh
0x180007d6d  jz      short loc_180007D82
0x180007d6f  mov     ecx, [rbp+18h]
0x180007d72  mov     edx, edi
0x180007d74  shr     ebx, 0Bh
0x180007d77  and     ebx, 1
0x180007d7a  mov     r8d, ebx
0x180007d7d  call    wil_RtlStagingConfig_RecordFeatureUsage
0x180007d82  mov     rbx, [rsp+68h+arg_18]
0x180007d8a  xor     eax, eax
0x180007d8c  test    esi, esi
0x180007d8e  setz    al
0x180007d91  add     rsp, 50h
0x180007d95  pop     rdi
0x180007d96  pop     rsi
0x180007d97  pop     rbp
0x180007d98  retn
```
