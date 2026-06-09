# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x14000613c`
- end: `0x1400061be`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `130`
- prototype: `_BOOL8 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140006020`

## callees

- `0x140005d48`
- `0x14000613c`

## import_xrefs

- `ntdll!RtlNotifyFeatureUsage` at `0x1400061a1`
- `ntdll!RtlNotifyFeatureUsage` at `0x1400061a1`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, int a3)
{
  __int16 v3; // bx
  int v5; // esi
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v5 = *(_DWORD *)(wil_details_FeatureReporting_RecordUsageInCache(
                     (__int64)v8,
                     (volatile signed __int32 *)&Feature_Servicing_GameInputSvcRedirectionGuard__private_reporting,
                     a3,
                     SHIDWORD(a2))
                 + 16);
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v7 = 57457541;
    WORD2(v7) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v7) |= 1u;
    RtlNotifyFeatureUsage(&v7);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x14000613c  mov     [rsp+arg_0], rbx
0x140006141  mov     [rsp+arg_18], rsi
0x140006146  push    rdi
0x140006147  sub     rsp, 50h
0x14000614b  mov     r9, rdx
0x14000614e  lea     rcx, [rsp+58h+var_20]
0x140006153  mov     rbx, rdx
0x140006156  shr     r9, 20h
0x14000615a  mov     rdx, cs:off_14000C008
0x140006161  mov     edi, r8d
0x140006164  call    wil_details_FeatureReporting_RecordUsageInCache
0x140006169  mov     esi, [rax+10h]
0x14000616c  bt      ebx, 0Ah
0x140006170  jnb     short loc_1400061A7
0x140006172  cmp     edi, 0FEh
0x140006178  jz      short loc_1400061A7
0x14000617a  mov     [rsp+58h+var_28], 0
0x140006183  mov     dword ptr [rsp+58h+var_28], 36CBB85h
0x14000618b  mov     word ptr [rsp+58h+var_28+4], di
0x140006190  bt      ebx, 0Bh
0x140006194  jnb     short loc_14000619C
0x140006196  or      word ptr [rsp+58h+var_28+6], 1
0x14000619c  lea     rcx, [rsp+58h+var_28]
0x1400061a1  call    cs:__imp_RtlNotifyFeatureUsage
0x1400061a7  mov     rbx, [rsp+58h+arg_0]
0x1400061ac  xor     eax, eax
0x1400061ae  test    esi, esi
0x1400061b0  mov     rsi, [rsp+58h+arg_18]
0x1400061b5  setz    al
0x1400061b8  add     rsp, 50h
0x1400061bc  pop     rdi
0x1400061bd  retn
```
