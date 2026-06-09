# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140009024`
- end: `0x1400090ba`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `150`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000a7e4`
- `0x14000c68c`
- `0x1400143ac`

## callees

- `0x140009024`
- `0x1400090c0`
- `0x140017010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v9; // [rsp+28h] [rbp-30h]
  __int64 v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+30h] [rbp-28h]

  a7 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     a3,
                                                                                                     a4,
                                                                                                     a6 != 0 ? 2 : 6,
                                                                                                     v9,
                                                                                                     v10,
                                                                                                     *(_BYTE *)(a5 + 4));
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v11) = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v11, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009024  mov     rax, rsp
0x140009027  mov     [rax+8], rbx
0x14000902b  push    rdi
0x14000902c  sub     rsp, 50h
0x140009030  mov     rdi, [rsp+58h+arg_20]
0x140009038  mov     ebx, edx
0x14000903a  mov     dword ptr [rax+38h], 3
0x140009041  mov     eax, [rsp+58h+arg_28]
0x140009048  neg     eax
0x14000904a  mov     al, [rdi+4]
0x14000904d  sbb     r10d, r10d
0x140009050  mov     byte ptr [rsp+58h+var_20], al
0x140009054  and     r10d, 0FFFFFFFCh
0x140009058  add     r10d, 6
0x14000905c  mov     dword ptr [rsp+58h+var_38], r10d
0x140009061  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140009066  test    eax, eax
0x140009068  jz      short loc_1400090AF
0x14000906a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140009071  test    rax, rax
0x140009074  jz      short loc_1400090AF
0x140009076  mov     r9d, [rsp+58h+arg_28]
0x14000907e  lea     rcx, [rsp+58h+arg_30]
0x140009086  mov     [rsp+58h+var_20], 1
0x14000908f  xor     r8d, r8d
0x140009092  mov     byte ptr [rsp+58h+var_28], 0
0x140009097  mov     rdx, rdi
0x14000909a  mov     [rsp+58h+var_30], 0
0x1400090a3  mov     [rsp+58h+var_38], rcx
0x1400090a8  mov     ecx, ebx
0x1400090aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090af  mov     rbx, [rsp+58h+arg_0]
0x1400090b4  add     rsp, 50h
0x1400090b8  pop     rdi
0x1400090b9  retn
```
