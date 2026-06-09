# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180027614`
- end: `0x180027738`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180027ad4`

## callees

- `0x180027614`
- `0x180027740`
- `0x18002a010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v5; // r8d
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v5 = 4 * !(a2 & 1);
        goto LABEL_17;
      case 2:
        v5 = 4 * !(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v5 = 4 * !(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v5 = 4 * !(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v5 = 2 * !(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
        v5 = 2 * !(a2 & 1) + 9;
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
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180027614  mov     [rsp+arg_0], rbx
0x180027619  mov     [rsp+arg_10], r8d
0x18002761e  push    rdi
0x18002761f  sub     rsp, 50h
0x180027623  mov     ebx, edx
0x180027625  mov     r10d, r8d
0x180027628  and     ebx, 1
0x18002762b  mov     rdi, rcx
0x18002762e  mov     r9d, r8d
0x180027631  test    r8d, r8d
0x180027634  jz      loc_1800276DF
0x18002763a  sub     r9d, 1
0x18002763e  jz      loc_1800276D2
0x180027644  sub     r9d, 1
0x180027648  jz      short loc_1800276C3
0x18002764a  sub     r9d, 1
0x18002764e  jz      short loc_1800276B4
0x180027650  sub     r9d, 1
0x180027654  jz      short loc_1800276A5
0x180027656  sub     r9d, 1
0x18002765a  jz      short loc_180027696
0x18002765c  cmp     r9d, 1
0x180027660  jz      short loc_180027687
0x180027662  sub     r10b, 64h ; 'd'
0x180027666  cmp     r10b, 31h ; '1'
0x18002766a  ja      short loc_1800276DF
0x18002766c  mov     eax, ebx
0x18002766e  neg     eax
0x180027670  movzx   eax, r10b
0x180027674  sbb     r8d, r8d
0x180027677  and     r8d, 0FFFFFFCEh
0x18002767b  add     r8d, 96h
0x180027682  add     r8d, eax
0x180027685  jmp     short loc_1800276E5
0x180027687  mov     eax, ebx
0x180027689  xor     eax, 1
0x18002768c  lea     r8d, ds:9[rax*2]
0x180027694  jmp     short loc_1800276E5
0x180027696  mov     eax, ebx
0x180027698  xor     eax, 1
0x18002769b  lea     r8d, ds:8[rax*2]
0x1800276a3  jmp     short loc_1800276E5
0x1800276a5  mov     eax, ebx
0x1800276a7  xor     eax, 1
0x1800276aa  lea     r8d, ds:3[rax*4]
0x1800276b2  jmp     short loc_1800276E5
0x1800276b4  mov     eax, ebx
0x1800276b6  xor     eax, 1
0x1800276b9  lea     r8d, ds:2[rax*4]
0x1800276c1  jmp     short loc_1800276E5
0x1800276c3  mov     eax, ebx
0x1800276c5  xor     eax, 1
0x1800276c8  lea     r8d, ds:1[rax*4]
0x1800276d0  jmp     short loc_1800276E5
0x1800276d2  mov     r8d, ebx
0x1800276d5  xor     r8d, 1
0x1800276d9  shl     r8d, 2
0x1800276dd  jmp     short loc_1800276E5
0x1800276df  mov     r8d, 0FFh
0x1800276e5  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1800276ea  test    eax, eax
0x1800276ec  jz      short loc_18002772D
0x1800276ee  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800276f5  test    rax, rax
0x1800276f8  jz      short loc_18002772D
0x1800276fa  mov     rdx, [rdi+10h]
0x1800276fe  lea     rcx, [rsp+58h+arg_10]
0x180027703  mov     [rsp+58h+var_20], 1
0x18002770c  mov     r9d, ebx
0x18002770f  mov     [rsp+58h+var_28], 0
0x180027714  xor     r8d, r8d
0x180027717  mov     [rsp+58h+var_30], 0
0x180027720  mov     [rsp+58h+var_38], rcx
0x180027725  mov     ecx, [rdi+18h]
0x180027728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002772d  mov     rbx, [rsp+58h+arg_0]
0x180027732  add     rsp, 50h
0x180027736  pop     rdi
0x180027737  retn
```
