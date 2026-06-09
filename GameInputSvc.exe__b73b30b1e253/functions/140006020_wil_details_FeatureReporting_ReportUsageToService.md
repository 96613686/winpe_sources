# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140006020`
- end: `0x140006136`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14000649c`

## callees

- `0x140006020`
- `0x14000613c`
- `0x140008010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  unsigned int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  v4 = a3;
  if ( a3 )
  {
    v4 = a3 - 1;
    if ( a3 == 1 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1);
      goto LABEL_17;
    }
    v4 = a3 - 2;
    if ( a3 == 2 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 1;
      goto LABEL_17;
    }
    v4 = a3 - 3;
    if ( a3 == 3 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 2;
      goto LABEL_17;
    }
    v4 = a3 - 4;
    if ( a3 == 4 )
    {
      v5 = 4 * (unsigned int)!(a2 & 1) + 3;
      goto LABEL_17;
    }
    v4 = a3 - 5;
    if ( a3 == 5 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 8;
      goto LABEL_17;
    }
    if ( a3 == 6 )
    {
      v5 = 2 * (unsigned int)!(a2 & 1) + 9;
      goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v5 = (unsigned __int8)(a3 - 100) + (v3 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v5 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     v4,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57457541, &Feature_Servicing_GameInputSvcRedirectionGuard_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x140006020  mov     [rsp+arg_10], r8d
0x140006025  push    rbx
0x140006026  sub     rsp, 50h
0x14000602a  mov     ebx, edx
0x14000602c  mov     r9d, r8d
0x14000602f  and     ebx, 1
0x140006032  mov     ecx, r8d
0x140006035  test    r8d, r8d
0x140006038  jz      loc_1400060DD
0x14000603e  sub     ecx, 1
0x140006041  jz      loc_1400060D0
0x140006047  sub     ecx, 1
0x14000604a  jz      short loc_1400060C1
0x14000604c  sub     ecx, 1
0x14000604f  jz      short loc_1400060B2
0x140006051  sub     ecx, 1
0x140006054  jz      short loc_1400060A3
0x140006056  sub     ecx, 1
0x140006059  jz      short loc_140006094
0x14000605b  cmp     ecx, 1
0x14000605e  jz      short loc_140006085
0x140006060  sub     r9b, 64h ; 'd'
0x140006064  cmp     r9b, 31h ; '1'
0x140006068  ja      short loc_1400060DD
0x14000606a  mov     eax, ebx
0x14000606c  neg     eax
0x14000606e  movzx   eax, r9b
0x140006072  sbb     r8d, r8d
0x140006075  and     r8d, 0FFFFFFCEh
0x140006079  add     r8d, 96h
0x140006080  add     r8d, eax
0x140006083  jmp     short loc_1400060E3
0x140006085  mov     eax, ebx
0x140006087  xor     eax, 1
0x14000608a  lea     r8d, ds:9[rax*2]
0x140006092  jmp     short loc_1400060E3
0x140006094  mov     eax, ebx
0x140006096  xor     eax, 1
0x140006099  lea     r8d, ds:8[rax*2]
0x1400060a1  jmp     short loc_1400060E3
0x1400060a3  mov     eax, ebx
0x1400060a5  xor     eax, 1
0x1400060a8  lea     r8d, ds:3[rax*4]
0x1400060b0  jmp     short loc_1400060E3
0x1400060b2  mov     eax, ebx
0x1400060b4  xor     eax, 1
0x1400060b7  lea     r8d, ds:2[rax*4]
0x1400060bf  jmp     short loc_1400060E3
0x1400060c1  mov     eax, ebx
0x1400060c3  xor     eax, 1
0x1400060c6  lea     r8d, ds:1[rax*4]
0x1400060ce  jmp     short loc_1400060E3
0x1400060d0  mov     r8d, ebx
0x1400060d3  xor     r8d, 1
0x1400060d7  shl     r8d, 2
0x1400060db  jmp     short loc_1400060E3
0x1400060dd  mov     r8d, 0FFh
0x1400060e3  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1400060e8  test    eax, eax
0x1400060ea  jz      short loc_140006130
0x1400060ec  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400060f3  test    rax, rax
0x1400060f6  jz      short loc_140006130
0x1400060f8  mov     rdx, cs:off_14000C010
0x1400060ff  lea     rcx, [rsp+58h+arg_10]
0x140006104  mov     [rsp+58h+var_20], 1
0x14000610d  mov     r9d, ebx
0x140006110  mov     [rsp+58h+var_28], 0
0x140006115  xor     r8d, r8d
0x140006118  mov     [rsp+58h+var_30], 0
0x140006121  mov     [rsp+58h+var_38], rcx
0x140006126  mov     ecx, 36CBB85h
0x14000612b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006130  add     rsp, 50h
0x140006134  pop     rbx
0x140006135  retn
```
