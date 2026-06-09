# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140001c58`
- end: `0x140001cce`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1400015c0`

## callees

- `0x140001c58`
- `0x140001cd4`
- `0x140002038`
- `0x140002710`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2 & 1;
  v4 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v5,
                                                                                                     v6,
                                                                                                     v4);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(42995998, &Feature_UserPresenceThrottling_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140001c58  mov     [rsp+arg_10], r8d
0x140001c5d  push    rbx
0x140001c5e  sub     rsp, 50h
0x140001c62  mov     ebx, edx
0x140001c64  mov     r9, rdx
0x140001c67  and     ebx, 1
0x140001c6a  mov     ecx, r8d
0x140001c6d  mov     edx, ebx
0x140001c6f  call    wil_details_MapReportingKind
0x140001c74  mov     r8d, eax
0x140001c77  mov     rdx, r9
0x140001c7a  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140001c7f  test    eax, eax
0x140001c81  jz      short loc_140001CC7
0x140001c83  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140001c8a  test    rax, rax
0x140001c8d  jz      short loc_140001CC7
0x140001c8f  mov     rdx, cs:off_140006B80
0x140001c96  lea     rcx, [rsp+58h+arg_10]
0x140001c9b  mov     [rsp+58h+var_20], 1
0x140001ca4  mov     r9d, ebx
0x140001ca7  mov     [rsp+58h+var_28], 0
0x140001cac  xor     r8d, r8d
0x140001caf  mov     [rsp+58h+var_30], 0
0x140001cb8  mov     [rsp+58h+var_38], rcx
0x140001cbd  mov     ecx, 290111Eh
0x140001cc2  call    _guard_dispatch_icall
0x140001cc7  add     rsp, 50h
0x140001ccb  pop     rbx
0x140001ccc  retn
```
