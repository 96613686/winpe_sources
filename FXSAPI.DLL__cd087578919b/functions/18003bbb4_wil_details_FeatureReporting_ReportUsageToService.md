# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18003bbb4`
- end: `0x18003bccb`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18003c054`

## callees

- `0x18003bbb4`
- `0x18003bcd4`
- `0x18003e010`

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
0x18003bbb4  mov     [rsp+arg_10], r8d
0x18003bbb9  push    rbx
0x18003bbba  sub     rsp, 50h
0x18003bbbe  mov     ebx, edx
0x18003bbc0  mov     r9d, r8d
0x18003bbc3  and     ebx, 1
0x18003bbc6  mov     ecx, r8d
0x18003bbc9  test    r8d, r8d
0x18003bbcc  jz      loc_18003BC71
0x18003bbd2  sub     ecx, 1
0x18003bbd5  jz      loc_18003BC64
0x18003bbdb  sub     ecx, 1
0x18003bbde  jz      short loc_18003BC55
0x18003bbe0  sub     ecx, 1
0x18003bbe3  jz      short loc_18003BC46
0x18003bbe5  sub     ecx, 1
0x18003bbe8  jz      short loc_18003BC37
0x18003bbea  sub     ecx, 1
0x18003bbed  jz      short loc_18003BC28
0x18003bbef  cmp     ecx, 1
0x18003bbf2  jz      short loc_18003BC19
0x18003bbf4  sub     r9b, 64h ; 'd'
0x18003bbf8  cmp     r9b, 31h ; '1'
0x18003bbfc  ja      short loc_18003BC71
0x18003bbfe  mov     eax, ebx
0x18003bc00  neg     eax
0x18003bc02  movzx   eax, r9b
0x18003bc06  sbb     r8d, r8d
0x18003bc09  and     r8d, 0FFFFFFCEh
0x18003bc0d  add     r8d, 96h
0x18003bc14  add     r8d, eax
0x18003bc17  jmp     short loc_18003BC77
0x18003bc19  mov     eax, ebx
0x18003bc1b  xor     eax, 1
0x18003bc1e  lea     r8d, ds:9[rax*2]
0x18003bc26  jmp     short loc_18003BC77
0x18003bc28  mov     eax, ebx
0x18003bc2a  xor     eax, 1
0x18003bc2d  lea     r8d, ds:8[rax*2]
0x18003bc35  jmp     short loc_18003BC77
0x18003bc37  mov     eax, ebx
0x18003bc39  xor     eax, 1
0x18003bc3c  lea     r8d, ds:3[rax*4]
0x18003bc44  jmp     short loc_18003BC77
0x18003bc46  mov     eax, ebx
0x18003bc48  xor     eax, 1
0x18003bc4b  lea     r8d, ds:2[rax*4]
0x18003bc53  jmp     short loc_18003BC77
0x18003bc55  mov     eax, ebx
0x18003bc57  xor     eax, 1
0x18003bc5a  lea     r8d, ds:1[rax*4]
0x18003bc62  jmp     short loc_18003BC77
0x18003bc64  mov     r8d, ebx
0x18003bc67  xor     r8d, 1
0x18003bc6b  shl     r8d, 2
0x18003bc6f  jmp     short loc_18003BC77
0x18003bc71  mov     r8d, 0FFh
0x18003bc77  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18003bc7c  test    eax, eax
0x18003bc7e  jz      short loc_18003BCC4
0x18003bc80  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18003bc87  test    rax, rax
0x18003bc8a  jz      short loc_18003BCC4
0x18003bc8c  mov     rdx, cs:off_18004A940
0x18003bc93  lea     rcx, [rsp+58h+arg_10]
0x18003bc98  mov     [rsp+58h+var_20], 1
0x18003bca1  mov     r9d, ebx
0x18003bca4  mov     [rsp+58h+var_28], 0
0x18003bca9  xor     r8d, r8d
0x18003bcac  mov     [rsp+58h+var_30], 0
0x18003bcb5  mov     [rsp+58h+var_38], rcx
0x18003bcba  mov     ecx, 3710FA3h
0x18003bcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcc4  add     rsp, 50h
0x18003bcc8  pop     rbx
0x18003bcc9  retn
```
