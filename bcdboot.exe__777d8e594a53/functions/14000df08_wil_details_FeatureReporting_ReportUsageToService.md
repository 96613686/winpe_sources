# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000df08`
- end: `0x14000e02c`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000e4b8`

## callees

- `0x14000df08`
- `0x14000e034`
- `0x140027010`

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
0x14000df08  mov     [rsp+arg_0], rbx
0x14000df0d  mov     [rsp+arg_10], r8d
0x14000df12  push    rdi
0x14000df13  sub     rsp, 50h
0x14000df17  mov     ebx, edx
0x14000df19  mov     r10d, r8d
0x14000df1c  and     ebx, 1
0x14000df1f  mov     rdi, rcx
0x14000df22  mov     r9d, r8d
0x14000df25  test    r8d, r8d
0x14000df28  jz      loc_14000DFD3
0x14000df2e  sub     r9d, 1
0x14000df32  jz      loc_14000DFC6
0x14000df38  sub     r9d, 1
0x14000df3c  jz      short loc_14000DFB7
0x14000df3e  sub     r9d, 1
0x14000df42  jz      short loc_14000DFA8
0x14000df44  sub     r9d, 1
0x14000df48  jz      short loc_14000DF99
0x14000df4a  sub     r9d, 1
0x14000df4e  jz      short loc_14000DF8A
0x14000df50  cmp     r9d, 1
0x14000df54  jz      short loc_14000DF7B
0x14000df56  sub     r10b, 64h ; 'd'
0x14000df5a  cmp     r10b, 31h ; '1'
0x14000df5e  ja      short loc_14000DFD3
0x14000df60  mov     eax, ebx
0x14000df62  neg     eax
0x14000df64  movzx   eax, r10b
0x14000df68  sbb     r8d, r8d
0x14000df6b  and     r8d, 0FFFFFFCEh
0x14000df6f  add     r8d, 96h
0x14000df76  add     r8d, eax
0x14000df79  jmp     short loc_14000DFD9
0x14000df7b  mov     eax, ebx
0x14000df7d  xor     eax, 1
0x14000df80  lea     r8d, ds:9[rax*2]
0x14000df88  jmp     short loc_14000DFD9
0x14000df8a  mov     eax, ebx
0x14000df8c  xor     eax, 1
0x14000df8f  lea     r8d, ds:8[rax*2]
0x14000df97  jmp     short loc_14000DFD9
0x14000df99  mov     eax, ebx
0x14000df9b  xor     eax, 1
0x14000df9e  lea     r8d, ds:3[rax*4]
0x14000dfa6  jmp     short loc_14000DFD9
0x14000dfa8  mov     eax, ebx
0x14000dfaa  xor     eax, 1
0x14000dfad  lea     r8d, ds:2[rax*4]
0x14000dfb5  jmp     short loc_14000DFD9
0x14000dfb7  mov     eax, ebx
0x14000dfb9  xor     eax, 1
0x14000dfbc  lea     r8d, ds:1[rax*4]
0x14000dfc4  jmp     short loc_14000DFD9
0x14000dfc6  mov     r8d, ebx
0x14000dfc9  xor     r8d, 1
0x14000dfcd  shl     r8d, 2
0x14000dfd1  jmp     short loc_14000DFD9
0x14000dfd3  mov     r8d, 0FFh
0x14000dfd9  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000dfde  test    eax, eax
0x14000dfe0  jz      short loc_14000E021
0x14000dfe2  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000dfe9  test    rax, rax
0x14000dfec  jz      short loc_14000E021
0x14000dfee  mov     rdx, [rdi+10h]
0x14000dff2  lea     rcx, [rsp+58h+arg_10]
0x14000dff7  mov     [rsp+58h+var_20], 1
0x14000e000  mov     r9d, ebx
0x14000e003  mov     [rsp+58h+var_28], 0
0x14000e008  xor     r8d, r8d
0x14000e00b  mov     [rsp+58h+var_30], 0
0x14000e014  mov     [rsp+58h+var_38], rcx
0x14000e019  mov     ecx, [rdi+18h]
0x14000e01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e021  mov     rbx, [rsp+58h+arg_0]
0x14000e026  add     rsp, 50h
0x14000e02a  pop     rdi
0x14000e02b  retn
```
