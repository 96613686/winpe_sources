# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140004910`
- end: `0x140004991`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140003560`

## callees

- `0x140004910`
- `0x140004998`
- `0x140004d34`
- `0x140013770`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  unsigned __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v4 = a2 & 1;
  v5 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     v6,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v4, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140004910  mov     [rsp+arg_0], rbx
0x140004915  mov     [rsp+arg_10], r8d
0x14000491a  push    rdi
0x14000491b  sub     rsp, 50h
0x14000491f  mov     edi, edx
0x140004921  mov     r9, rdx
0x140004924  mov     rbx, rcx
0x140004927  and     edi, 1
0x14000492a  mov     edx, edi
0x14000492c  mov     ecx, r8d
0x14000492f  call    wil_details_MapReportingKind
0x140004934  mov     r8d, eax
0x140004937  mov     rdx, r9
0x14000493a  mov     rcx, rbx
0x14000493d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140004942  test    eax, eax
0x140004944  jz      short loc_140004985
0x140004946  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000494d  test    rax, rax
0x140004950  jz      short loc_140004985
0x140004952  mov     rdx, [rbx+10h]
0x140004956  lea     rcx, [rsp+58h+arg_10]
0x14000495b  mov     [rsp+58h+var_20], 1
0x140004964  mov     r9d, edi
0x140004967  mov     [rsp+58h+var_28], 0
0x14000496c  xor     r8d, r8d
0x14000496f  mov     [rsp+58h+var_30], 0
0x140004978  mov     [rsp+58h+var_38], rcx
0x14000497d  mov     ecx, [rbx+18h]
0x140004980  call    _guard_dispatch_icall
0x140004985  mov     rbx, [rsp+58h+arg_0]
0x14000498a  add     rsp, 50h
0x14000498e  pop     rdi
0x14000498f  retn
```
