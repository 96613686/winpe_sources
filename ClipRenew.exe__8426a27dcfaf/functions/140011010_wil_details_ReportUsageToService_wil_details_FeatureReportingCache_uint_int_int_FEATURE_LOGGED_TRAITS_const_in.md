# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140011010`
- end: `0x1400110a6`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `150`
- prototype: `__int64 (__fastcall *__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140011d74`
- `0x140011e0c`
- `0x140011ea4`
- `0x140011f3c`
- `0x140012a38`

## callees

- `0x140011010`
- `0x1400110ac`
- `0x140014010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v9; // [rsp+30h] [rbp-28h]

  a7 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(a1);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v9 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011010  mov     rax, rsp
0x140011013  mov     [rax+8], rbx
0x140011017  push    rdi
0x140011018  sub     rsp, 50h
0x14001101c  mov     rdi, [rsp+58h+arg_20]
0x140011024  mov     ebx, edx
0x140011026  mov     dword ptr [rax+38h], 3
0x14001102d  mov     eax, [rsp+58h+arg_28]
0x140011034  neg     eax
0x140011036  mov     al, [rdi+4]
0x140011039  sbb     r10d, r10d
0x14001103c  mov     byte ptr [rsp+58h+var_20], al
0x140011040  and     r10d, 0FFFFFFFCh
0x140011044  add     r10d, 6
0x140011048  mov     dword ptr [rsp+58h+var_38], r10d
0x14001104d  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140011052  test    eax, eax
0x140011054  jz      short loc_14001109B
0x140011056  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14001105d  test    rax, rax
0x140011060  jz      short loc_14001109B
0x140011062  mov     r9d, [rsp+58h+arg_28]
0x14001106a  lea     rcx, [rsp+58h+arg_30]
0x140011072  mov     [rsp+58h+var_20], 1
0x14001107b  xor     r8d, r8d
0x14001107e  mov     [rsp+58h+var_28], 0
0x140011083  mov     rdx, rdi
0x140011086  mov     [rsp+58h+var_30], 0
0x14001108f  mov     [rsp+58h+var_38], rcx
0x140011094  mov     ecx, ebx
0x140011096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001109b  mov     rbx, [rsp+58h+arg_0]
0x1400110a0  add     rsp, 50h
0x1400110a4  pop     rdi
0x1400110a5  retn
```
