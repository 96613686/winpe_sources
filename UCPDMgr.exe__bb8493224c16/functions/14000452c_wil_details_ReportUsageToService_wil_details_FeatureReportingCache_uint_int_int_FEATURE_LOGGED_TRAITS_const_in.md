# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000452c`
- end: `0x1400045bf`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `147`
- prototype: `__int64 (__fastcall *__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `31`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000602c`
- `0x14000625c`
- `0x14000648c`
- `0x1400066bc`
- `0x1400068ec`
- `0x140006b1c`
- `0x140006d4c`
- `0x140006f7c`
- `0x1400071ac`
- `0x1400073dc`
- `0x14000760c`
- `0x14000783c`
- `0x140007a6c`
- `0x140007c9c`
- `0x140007ecc`
- `0x1400080fc`
- `0x14000832c`
- `0x14000855c`
- `0x14000878c`
- `0x1400089bc`
- `0x140008bec`
- `0x140008e1c`
- `0x14000904c`
- `0x14000927c`
- `0x1400094ac`
- `0x1400096dc`
- `0x14000990c`
- `0x140009b3c`
- `0x140009d6c`
- `0x140009f9c`
- `0x14000a1cc`

## callees

- `0x140004318`
- `0x14000452c`
- `0x14000f4d0`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-38h]
  int v9[6]; // [rsp+50h] [rbp-18h] BYREF

  v9[0] = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000452c  mov     [rsp+arg_10], rbx
0x140004531  push    rdi
0x140004532  sub     rsp, 60h
0x140004536  mov     eax, [rsp+68h+arg_28]
0x14000453d  mov     ebx, edx
0x14000453f  mov     rdi, [rsp+68h+arg_20]
0x140004547  neg     eax
0x140004549  mov     [rsp+68h+var_18], 3
0x140004551  sbb     edx, edx
0x140004553  and     edx, 0FFFFFFFCh
0x140004556  mov     al, [rdi+4]
0x140004559  add     edx, 6
0x14000455c  mov     byte ptr [rsp+68h+var_30], al
0x140004560  mov     dword ptr [rsp+68h+var_48], edx
0x140004564  mov     edx, ebx
0x140004566  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000456b  test    eax, eax
0x14000456d  jz      short loc_1400045B1
0x14000456f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140004576  test    rax, rax
0x140004579  jz      short loc_1400045B1
0x14000457b  mov     r9d, [rsp+68h+arg_28]
0x140004583  lea     rcx, [rsp+68h+var_18]
0x140004588  mov     [rsp+68h+var_30], 1
0x140004591  xor     r8d, r8d
0x140004594  mov     [rsp+68h+var_38], 0
0x140004599  mov     rdx, rdi
0x14000459c  mov     [rsp+68h+var_40], 0
0x1400045a5  mov     [rsp+68h+var_48], rcx
0x1400045aa  mov     ecx, ebx
0x1400045ac  call    _guard_dispatch_icall
0x1400045b1  mov     rbx, [rsp+68h+arg_10]
0x1400045b9  add     rsp, 60h
0x1400045bd  pop     rdi
0x1400045be  retn
```
