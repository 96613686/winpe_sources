# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140002678`
- end: `0x140002702`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000223c`
- `0x140002aa8`
- `0x140025ba0`

## callees

- `0x140002678`
- `0x140002708`
- `0x140002b30`
- `0x140006a60`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        char a2,
        unsigned int a3,
        __int64 a4))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v5; // edi
  unsigned int v7; // eax
  __int64 v8; // r10
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v10; // [rsp+30h] [rbp-28h]
  unsigned int v11; // [rsp+70h] [rbp+18h] BYREF

  v11 = a3;
  v5 = a2 & 1;
  v7 = wil_details_MapReportingKind(a3, a2 & 1);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     v8,
                                                                                                     v7);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v10 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v5, &v11, 0, v10, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002678  mov     [rsp+arg_0], rbx
0x14000267d  mov     [rsp+arg_8], rsi
0x140002682  mov     [rsp+arg_10], r8d
0x140002687  push    rdi
0x140002688  sub     rsp, 50h
0x14000268c  mov     edi, edx
0x14000268e  mov     r10, rdx
0x140002691  mov     rbx, rcx
0x140002694  and     edi, 1
0x140002697  mov     edx, edi
0x140002699  mov     ecx, r8d
0x14000269c  mov     rsi, r9
0x14000269f  call    wil_details_MapReportingKind
0x1400026a4  mov     r8d, eax
0x1400026a7  mov     rdx, r10
0x1400026aa  mov     rcx, rbx
0x1400026ad  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1400026b2  test    eax, eax
0x1400026b4  jz      short loc_1400026F1
0x1400026b6  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400026bd  test    rax, rax
0x1400026c0  jz      short loc_1400026F1
0x1400026c2  mov     rdx, [rbx+10h]
0x1400026c6  lea     rcx, [rsp+58h+arg_10]
0x1400026cb  mov     [rsp+58h+var_20], rsi
0x1400026d0  mov     r9d, edi
0x1400026d3  mov     [rsp+58h+var_28], 0
0x1400026d8  xor     r8d, r8d
0x1400026db  mov     [rsp+58h+var_30], 0
0x1400026e4  mov     [rsp+58h+var_38], rcx
0x1400026e9  mov     ecx, [rbx+18h]
0x1400026ec  call    _guard_dispatch_icall
0x1400026f1  mov     rbx, [rsp+58h+arg_0]
0x1400026f6  mov     rsi, [rsp+58h+arg_8]
0x1400026fb  add     rsp, 50h
0x1400026ff  pop     rdi
0x140002700  retn
```
