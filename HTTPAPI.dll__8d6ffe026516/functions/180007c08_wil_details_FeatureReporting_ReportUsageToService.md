# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180007c08`
- end: `0x180007d2c`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008064`

## callees

- `0x180007c08`
- `0x180007d34`
- `0x18000d010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v5 = 4 * (unsigned int)!(a2 & 1);
        goto LABEL_17;
      case 2:
        v5 = 4 * (unsigned int)!(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v5 = 4 * (unsigned int)!(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v5 = 4 * (unsigned int)!(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v5 = 2 * (unsigned int)!(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
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
0x180007c08  mov     [rsp+arg_0], rbx
0x180007c0d  mov     [rsp+arg_10], r8d
0x180007c12  push    rdi
0x180007c13  sub     rsp, 50h
0x180007c17  mov     ebx, edx
0x180007c19  mov     r10d, r8d
0x180007c1c  and     ebx, 1
0x180007c1f  mov     rdi, rcx
0x180007c22  mov     r9d, r8d
0x180007c25  test    r8d, r8d
0x180007c28  jz      loc_180007CD3
0x180007c2e  sub     r9d, 1
0x180007c32  jz      loc_180007CC6
0x180007c38  sub     r9d, 1
0x180007c3c  jz      short loc_180007CB7
0x180007c3e  sub     r9d, 1
0x180007c42  jz      short loc_180007CA8
0x180007c44  sub     r9d, 1
0x180007c48  jz      short loc_180007C99
0x180007c4a  sub     r9d, 1
0x180007c4e  jz      short loc_180007C8A
0x180007c50  cmp     r9d, 1
0x180007c54  jz      short loc_180007C7B
0x180007c56  sub     r10b, 64h ; 'd'
0x180007c5a  cmp     r10b, 31h ; '1'
0x180007c5e  ja      short loc_180007CD3
0x180007c60  mov     eax, ebx
0x180007c62  neg     eax
0x180007c64  movzx   eax, r10b
0x180007c68  sbb     r8d, r8d
0x180007c6b  and     r8d, 0FFFFFFCEh
0x180007c6f  add     r8d, 96h
0x180007c76  add     r8d, eax
0x180007c79  jmp     short loc_180007CD9
0x180007c7b  mov     eax, ebx
0x180007c7d  xor     eax, 1
0x180007c80  lea     r8d, ds:9[rax*2]
0x180007c88  jmp     short loc_180007CD9
0x180007c8a  mov     eax, ebx
0x180007c8c  xor     eax, 1
0x180007c8f  lea     r8d, ds:8[rax*2]
0x180007c97  jmp     short loc_180007CD9
0x180007c99  mov     eax, ebx
0x180007c9b  xor     eax, 1
0x180007c9e  lea     r8d, ds:3[rax*4]
0x180007ca6  jmp     short loc_180007CD9
0x180007ca8  mov     eax, ebx
0x180007caa  xor     eax, 1
0x180007cad  lea     r8d, ds:2[rax*4]
0x180007cb5  jmp     short loc_180007CD9
0x180007cb7  mov     eax, ebx
0x180007cb9  xor     eax, 1
0x180007cbc  lea     r8d, ds:1[rax*4]
0x180007cc4  jmp     short loc_180007CD9
0x180007cc6  mov     r8d, ebx
0x180007cc9  xor     r8d, 1
0x180007ccd  shl     r8d, 2
0x180007cd1  jmp     short loc_180007CD9
0x180007cd3  mov     r8d, 0FFh
0x180007cd9  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180007cde  test    eax, eax
0x180007ce0  jz      short loc_180007D21
0x180007ce2  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180007ce9  test    rax, rax
0x180007cec  jz      short loc_180007D21
0x180007cee  mov     rdx, [rdi+10h]
0x180007cf2  lea     rcx, [rsp+58h+arg_10]
0x180007cf7  mov     [rsp+58h+var_20], 1
0x180007d00  mov     r9d, ebx
0x180007d03  mov     [rsp+58h+var_28], 0
0x180007d08  xor     r8d, r8d
0x180007d0b  mov     [rsp+58h+var_30], 0
0x180007d14  mov     [rsp+58h+var_38], rcx
0x180007d19  mov     ecx, [rdi+18h]
0x180007d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d21  mov     rbx, [rsp+58h+arg_0]
0x180007d26  add     rsp, 50h
0x180007d2a  pop     rdi
0x180007d2b  retn
```
