# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18000b120`
- end: `0x18000b1dd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `189`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000afd8`

## callees

- `0x1800014b0`
- `0x18000ae54`
- `0x18000b120`
- `0x18000b464`
- `0x180018010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, __int64 a3)
{
  __int16 v3; // bx
  int v5; // edi
  int v6; // ebp
  void (__fastcall *NtDllProcedureAddress)(int *); // rax
  _BYTE v9[24]; // [rsp+30h] [rbp-48h] BYREF
  int v10; // [rsp+48h] [rbp-30h] BYREF
  int v11; // [rsp+4Ch] [rbp-2Ch]

  v3 = a2;
  v5 = a3;
  v6 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v9,
         *(volatile signed __int32 **)(a1 + 8),
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && v5 != 254 )
  {
    v10 = *(_DWORD *)(a1 + 24);
    v11 = (unsigned __int16)v5;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v11) |= 1u;
    NtDllProcedureAddress = (void (__fastcall *)(int *))g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = (void (__fastcall *)(int *))wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      NtDllProcedureAddress(&v10);
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x18000b120  mov     [rsp+arg_18], rbx
0x18000b125  push    rbp
0x18000b126  push    rsi
0x18000b127  push    rdi
0x18000b128  sub     rsp, 60h
0x18000b12c  mov     rax, cs:__security_cookie
0x18000b133  xor     rax, rsp
0x18000b136  mov     [rsp+78h+var_28], rax
0x18000b13b  mov     r9, rdx
0x18000b13e  mov     rbx, rdx
0x18000b141  mov     rdx, [rcx+8]
0x18000b145  mov     rsi, rcx
0x18000b148  shr     r9, 20h
0x18000b14c  lea     rcx, [rsp+78h+var_48]
0x18000b151  mov     edi, r8d
0x18000b154  call    wil_details_FeatureReporting_RecordUsageInCache
0x18000b159  mov     ebp, [rax+10h]
0x18000b15c  bt      ebx, 0Ah
0x18000b160  jnb     short loc_18000B1B9
0x18000b162  cmp     edi, 0FEh
0x18000b168  jz      short loc_18000B1B9
0x18000b16a  mov     eax, [rsi+18h]
0x18000b16d  mov     [rsp+78h+var_30], 0
0x18000b176  mov     dword ptr [rsp+78h+var_30], eax
0x18000b17a  mov     word ptr [rsp+78h+var_30+4], di
0x18000b17f  bt      ebx, 0Bh
0x18000b183  jnb     short loc_18000B18B
0x18000b185  or      word ptr [rsp+78h+var_30+6], 1
0x18000b18b  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b192  test    rax, rax
0x18000b195  jnz     short loc_18000B1AF
0x18000b197  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b19e  call    wil_details_GetNtDllProcedureAddress
0x18000b1a3  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b1aa  test    rax, rax
0x18000b1ad  jz      short loc_18000B1B9
0x18000b1af  lea     rcx, [rsp+78h+var_30]
0x18000b1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1b9  xor     eax, eax
0x18000b1bb  test    ebp, ebp
0x18000b1bd  setz    al
0x18000b1c0  mov     rcx, [rsp+78h+var_28]
0x18000b1c5  xor     rcx, rsp; StackCookie
0x18000b1c8  call    __security_check_cookie
0x18000b1cd  mov     rbx, [rsp+78h+arg_18]
0x18000b1d5  add     rsp, 60h
0x18000b1d9  pop     rdi
0x18000b1da  pop     rsi
0x18000b1db  pop     rbp
0x18000b1dc  retn
```
