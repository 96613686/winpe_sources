# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000fb70`
- end: `0x18000fc86`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010104`

## callees

- `0x18000fb70`
- `0x18000fc8c`
- `0x18001c010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57207774, &Feature_57207774_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000fb70  mov     [rsp+arg_10], r8d
0x18000fb75  push    rbx
0x18000fb76  sub     rsp, 50h
0x18000fb7a  mov     ebx, edx
0x18000fb7c  mov     r9d, r8d
0x18000fb7f  and     ebx, 1
0x18000fb82  mov     ecx, r8d
0x18000fb85  test    r8d, r8d
0x18000fb88  jz      loc_18000FC2D
0x18000fb8e  sub     ecx, 1
0x18000fb91  jz      loc_18000FC20
0x18000fb97  sub     ecx, 1
0x18000fb9a  jz      short loc_18000FC11
0x18000fb9c  sub     ecx, 1
0x18000fb9f  jz      short loc_18000FC02
0x18000fba1  sub     ecx, 1
0x18000fba4  jz      short loc_18000FBF3
0x18000fba6  sub     ecx, 1
0x18000fba9  jz      short loc_18000FBE4
0x18000fbab  cmp     ecx, 1
0x18000fbae  jz      short loc_18000FBD5
0x18000fbb0  sub     r9b, 64h ; 'd'
0x18000fbb4  cmp     r9b, 31h ; '1'
0x18000fbb8  ja      short loc_18000FC2D
0x18000fbba  mov     eax, ebx
0x18000fbbc  neg     eax
0x18000fbbe  movzx   eax, r9b
0x18000fbc2  sbb     r8d, r8d
0x18000fbc5  and     r8d, 0FFFFFFCEh
0x18000fbc9  add     r8d, 96h
0x18000fbd0  add     r8d, eax
0x18000fbd3  jmp     short loc_18000FC33
0x18000fbd5  mov     eax, ebx
0x18000fbd7  xor     eax, 1
0x18000fbda  lea     r8d, ds:9[rax*2]
0x18000fbe2  jmp     short loc_18000FC33
0x18000fbe4  mov     eax, ebx
0x18000fbe6  xor     eax, 1
0x18000fbe9  lea     r8d, ds:8[rax*2]
0x18000fbf1  jmp     short loc_18000FC33
0x18000fbf3  mov     eax, ebx
0x18000fbf5  xor     eax, 1
0x18000fbf8  lea     r8d, ds:3[rax*4]
0x18000fc00  jmp     short loc_18000FC33
0x18000fc02  mov     eax, ebx
0x18000fc04  xor     eax, 1
0x18000fc07  lea     r8d, ds:2[rax*4]
0x18000fc0f  jmp     short loc_18000FC33
0x18000fc11  mov     eax, ebx
0x18000fc13  xor     eax, 1
0x18000fc16  lea     r8d, ds:1[rax*4]
0x18000fc1e  jmp     short loc_18000FC33
0x18000fc20  mov     r8d, ebx
0x18000fc23  xor     r8d, 1
0x18000fc27  shl     r8d, 2
0x18000fc2b  jmp     short loc_18000FC33
0x18000fc2d  mov     r8d, 0FFh
0x18000fc33  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000fc38  test    eax, eax
0x18000fc3a  jz      short loc_18000FC80
0x18000fc3c  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fc43  test    rax, rax
0x18000fc46  jz      short loc_18000FC80
0x18000fc48  mov     rdx, cs:off_180025E50
0x18000fc4f  lea     rcx, [rsp+58h+arg_10]
0x18000fc54  mov     [rsp+58h+var_20], 1
0x18000fc5d  mov     r9d, ebx
0x18000fc60  mov     [rsp+58h+var_28], 0
0x18000fc65  xor     r8d, r8d
0x18000fc68  mov     [rsp+58h+var_30], 0
0x18000fc71  mov     [rsp+58h+var_38], rcx
0x18000fc76  mov     ecx, 368EBDEh
0x18000fc7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc80  add     rsp, 50h
0x18000fc84  pop     rbx
0x18000fc85  retn
```
