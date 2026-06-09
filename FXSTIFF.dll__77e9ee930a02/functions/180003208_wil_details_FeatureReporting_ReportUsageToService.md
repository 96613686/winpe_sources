# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180003208`
- end: `0x18000331f`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800036a8`

## callees

- `0x180003208`
- `0x180003328`
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57741219, &Feature_Print_PlatformStabilizationFixes_2026_Wave1_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180003208  mov     [rsp+arg_10], r8d
0x18000320d  push    rbx
0x18000320e  sub     rsp, 50h
0x180003212  mov     ebx, edx
0x180003214  mov     r9d, r8d
0x180003217  and     ebx, 1
0x18000321a  mov     ecx, r8d
0x18000321d  test    r8d, r8d
0x180003220  jz      loc_1800032C5
0x180003226  sub     ecx, 1
0x180003229  jz      loc_1800032B8
0x18000322f  sub     ecx, 1
0x180003232  jz      short loc_1800032A9
0x180003234  sub     ecx, 1
0x180003237  jz      short loc_18000329A
0x180003239  sub     ecx, 1
0x18000323c  jz      short loc_18000328B
0x18000323e  sub     ecx, 1
0x180003241  jz      short loc_18000327C
0x180003243  cmp     ecx, 1
0x180003246  jz      short loc_18000326D
0x180003248  sub     r9b, 64h ; 'd'
0x18000324c  cmp     r9b, 31h ; '1'
0x180003250  ja      short loc_1800032C5
0x180003252  mov     eax, ebx
0x180003254  neg     eax
0x180003256  movzx   eax, r9b
0x18000325a  sbb     r8d, r8d
0x18000325d  and     r8d, 0FFFFFFCEh
0x180003261  add     r8d, 96h
0x180003268  add     r8d, eax
0x18000326b  jmp     short loc_1800032CB
0x18000326d  mov     eax, ebx
0x18000326f  xor     eax, 1
0x180003272  lea     r8d, ds:9[rax*2]
0x18000327a  jmp     short loc_1800032CB
0x18000327c  mov     eax, ebx
0x18000327e  xor     eax, 1
0x180003281  lea     r8d, ds:8[rax*2]
0x180003289  jmp     short loc_1800032CB
0x18000328b  mov     eax, ebx
0x18000328d  xor     eax, 1
0x180003290  lea     r8d, ds:3[rax*4]
0x180003298  jmp     short loc_1800032CB
0x18000329a  mov     eax, ebx
0x18000329c  xor     eax, 1
0x18000329f  lea     r8d, ds:2[rax*4]
0x1800032a7  jmp     short loc_1800032CB
0x1800032a9  mov     eax, ebx
0x1800032ab  xor     eax, 1
0x1800032ae  lea     r8d, ds:1[rax*4]
0x1800032b6  jmp     short loc_1800032CB
0x1800032b8  mov     r8d, ebx
0x1800032bb  xor     r8d, 1
0x1800032bf  shl     r8d, 2
0x1800032c3  jmp     short loc_1800032CB
0x1800032c5  mov     r8d, 0FFh
0x1800032cb  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800032d0  test    eax, eax
0x1800032d2  jz      short loc_180003318
0x1800032d4  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800032db  test    rax, rax
0x1800032de  jz      short loc_180003318
0x1800032e0  mov     rdx, cs:off_18006EB98
0x1800032e7  lea     rcx, [rsp+58h+arg_10]
0x1800032ec  mov     [rsp+58h+var_20], 1
0x1800032f5  mov     r9d, ebx
0x1800032f8  mov     [rsp+58h+var_28], 0
0x1800032fd  xor     r8d, r8d
0x180003300  mov     [rsp+58h+var_30], 0
0x180003309  mov     [rsp+58h+var_38], rcx
0x18000330e  mov     ecx, 3710FA3h
0x180003313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003318  add     rsp, 50h
0x18000331c  pop     rbx
0x18000331d  retn
```
