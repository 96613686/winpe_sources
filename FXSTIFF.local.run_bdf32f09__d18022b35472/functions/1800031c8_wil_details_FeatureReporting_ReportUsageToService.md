# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x1800031c8`
- end: `0x1800032de`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003674`

## callees

- `0x1800031c8`
- `0x1800032e4`
- `0x180019010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        unsigned __int64 a2,
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57741219, Feature_Print_PlatformStabilizationFixes_2026_Wave1_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800031c8  mov     [rsp+arg_10], r8d
0x1800031cd  push    rbx
0x1800031ce  sub     rsp, 50h
0x1800031d2  mov     ebx, edx
0x1800031d4  mov     r9d, r8d
0x1800031d7  and     ebx, 1
0x1800031da  mov     ecx, r8d
0x1800031dd  test    r8d, r8d
0x1800031e0  jz      loc_180003285
0x1800031e6  sub     ecx, 1
0x1800031e9  jz      loc_180003278
0x1800031ef  sub     ecx, 1
0x1800031f2  jz      short loc_180003269
0x1800031f4  sub     ecx, 1
0x1800031f7  jz      short loc_18000325A
0x1800031f9  sub     ecx, 1
0x1800031fc  jz      short loc_18000324B
0x1800031fe  sub     ecx, 1
0x180003201  jz      short loc_18000323C
0x180003203  cmp     ecx, 1
0x180003206  jz      short loc_18000322D
0x180003208  sub     r9b, 64h ; 'd'
0x18000320c  cmp     r9b, 31h ; '1'
0x180003210  ja      short loc_180003285
0x180003212  mov     eax, ebx
0x180003214  neg     eax
0x180003216  movzx   eax, r9b
0x18000321a  sbb     r8d, r8d
0x18000321d  and     r8d, 0FFFFFFCEh
0x180003221  add     r8d, 96h
0x180003228  add     r8d, eax
0x18000322b  jmp     short loc_18000328B
0x18000322d  mov     eax, ebx
0x18000322f  xor     eax, 1
0x180003232  lea     r8d, ds:9[rax*2]
0x18000323a  jmp     short loc_18000328B
0x18000323c  mov     eax, ebx
0x18000323e  xor     eax, 1
0x180003241  lea     r8d, ds:8[rax*2]
0x180003249  jmp     short loc_18000328B
0x18000324b  mov     eax, ebx
0x18000324d  xor     eax, 1
0x180003250  lea     r8d, ds:3[rax*4]
0x180003258  jmp     short loc_18000328B
0x18000325a  mov     eax, ebx
0x18000325c  xor     eax, 1
0x18000325f  lea     r8d, ds:2[rax*4]
0x180003267  jmp     short loc_18000328B
0x180003269  mov     eax, ebx
0x18000326b  xor     eax, 1
0x18000326e  lea     r8d, ds:1[rax*4]
0x180003276  jmp     short loc_18000328B
0x180003278  mov     r8d, ebx
0x18000327b  xor     r8d, 1
0x18000327f  shl     r8d, 2
0x180003283  jmp     short loc_18000328B
0x180003285  mov     r8d, 0FFh
0x18000328b  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180003290  test    eax, eax
0x180003292  jz      short loc_1800032D8
0x180003294  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000329b  test    rax, rax
0x18000329e  jz      short loc_1800032D8
0x1800032a0  mov     rdx, cs:off_18006EB58
0x1800032a7  lea     rcx, [rsp+58h+arg_10]
0x1800032ac  mov     [rsp+58h+var_20], 1
0x1800032b5  mov     r9d, ebx
0x1800032b8  mov     [rsp+58h+var_28], 0
0x1800032bd  xor     r8d, r8d
0x1800032c0  mov     [rsp+58h+var_30], 0
0x1800032c9  mov     [rsp+58h+var_38], rcx
0x1800032ce  mov     ecx, 3710FA3h
0x1800032d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d8  add     rsp, 50h
0x1800032dc  pop     rbx
0x1800032dd  retn
```
