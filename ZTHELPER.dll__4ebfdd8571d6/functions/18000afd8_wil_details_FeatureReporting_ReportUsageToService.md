# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000afd8`
- end: `0x18000b118`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `320`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a4e0`
- `0x18000b4a8`

## callees

- `0x1800014b0`
- `0x18000afd8`
- `0x18000b120`
- `0x180018010`

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
  int v7; // [rsp+50h] [rbp-18h] BYREF

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
0x18000afd8  mov     [rsp+arg_18], rbx
0x18000afdd  push    rdi
0x18000afde  sub     rsp, 60h
0x18000afe2  mov     rax, cs:__security_cookie
0x18000afe9  xor     rax, rsp
0x18000afec  mov     [rsp+68h+var_10], rax
0x18000aff1  mov     ebx, edx
0x18000aff3  mov     [rsp+68h+var_18], r8d
0x18000aff8  and     ebx, 1
0x18000affb  mov     rdi, rcx
0x18000affe  mov     r9d, r8d
0x18000b001  mov     ecx, r8d
0x18000b004  test    r8d, r8d
0x18000b007  jz      loc_18000B0AC
0x18000b00d  sub     ecx, 1
0x18000b010  jz      loc_18000B09F
0x18000b016  sub     ecx, 1
0x18000b019  jz      short loc_18000B090
0x18000b01b  sub     ecx, 1
0x18000b01e  jz      short loc_18000B081
0x18000b020  sub     ecx, 1
0x18000b023  jz      short loc_18000B072
0x18000b025  sub     ecx, 1
0x18000b028  jz      short loc_18000B063
0x18000b02a  cmp     ecx, 1
0x18000b02d  jz      short loc_18000B054
0x18000b02f  sub     r9b, 64h ; 'd'
0x18000b033  cmp     r9b, 31h ; '1'
0x18000b037  ja      short loc_18000B0AC
0x18000b039  mov     eax, ebx
0x18000b03b  neg     eax
0x18000b03d  movzx   eax, r9b
0x18000b041  sbb     r8d, r8d
0x18000b044  and     r8d, 0FFFFFFCEh
0x18000b048  add     r8d, 96h
0x18000b04f  add     r8d, eax
0x18000b052  jmp     short loc_18000B0B2
0x18000b054  mov     eax, ebx
0x18000b056  xor     eax, 1
0x18000b059  lea     r8d, ds:9[rax*2]
0x18000b061  jmp     short loc_18000B0B2
0x18000b063  mov     eax, ebx
0x18000b065  xor     eax, 1
0x18000b068  lea     r8d, ds:8[rax*2]
0x18000b070  jmp     short loc_18000B0B2
0x18000b072  mov     eax, ebx
0x18000b074  xor     eax, 1
0x18000b077  lea     r8d, ds:3[rax*4]
0x18000b07f  jmp     short loc_18000B0B2
0x18000b081  mov     eax, ebx
0x18000b083  xor     eax, 1
0x18000b086  lea     r8d, ds:2[rax*4]
0x18000b08e  jmp     short loc_18000B0B2
0x18000b090  mov     eax, ebx
0x18000b092  xor     eax, 1
0x18000b095  lea     r8d, ds:1[rax*4]
0x18000b09d  jmp     short loc_18000B0B2
0x18000b09f  mov     r8d, ebx
0x18000b0a2  xor     r8d, 1
0x18000b0a6  shl     r8d, 2
0x18000b0aa  jmp     short loc_18000B0B2
0x18000b0ac  mov     r8d, 0FFh
0x18000b0b2  mov     rcx, rdi
0x18000b0b5  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000b0ba  test    eax, eax
0x18000b0bc  jz      short loc_18000B0FD
0x18000b0be  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000b0c5  test    rax, rax
0x18000b0c8  jz      short loc_18000B0FD
0x18000b0ca  mov     rdx, [rdi+10h]
0x18000b0ce  lea     rcx, [rsp+68h+var_18]
0x18000b0d3  mov     [rsp+68h+var_30], 1
0x18000b0dc  mov     r9d, ebx
0x18000b0df  mov     [rsp+68h+var_38], 0
0x18000b0e4  xor     r8d, r8d
0x18000b0e7  mov     [rsp+68h+var_40], 0
0x18000b0f0  mov     [rsp+68h+var_48], rcx
0x18000b0f5  mov     ecx, [rdi+18h]
0x18000b0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fd  mov     rcx, [rsp+68h+var_10]
0x18000b102  xor     rcx, rsp; StackCookie
0x18000b105  call    __security_check_cookie
0x18000b10a  mov     rbx, [rsp+68h+arg_18]
0x18000b112  add     rsp, 60h
0x18000b116  pop     rdi
0x18000b117  retn
```
