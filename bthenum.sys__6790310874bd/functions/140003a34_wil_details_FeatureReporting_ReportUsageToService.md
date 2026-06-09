# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140003a34`
- end: `0x140003b4b`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140003f20`

## callees

- `0x140003a34`
- `0x140003b54`
- `0x140007d40`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(56664216, &Feature_56664216_logged_traits, 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x140003a34  mov     [rsp+arg_10], r8d
0x140003a39  push    rbx
0x140003a3a  sub     rsp, 50h
0x140003a3e  mov     ebx, edx
0x140003a40  mov     r9d, r8d
0x140003a43  and     ebx, 1
0x140003a46  mov     ecx, r8d
0x140003a49  test    r8d, r8d
0x140003a4c  jz      loc_140003AF1
0x140003a52  sub     ecx, 1
0x140003a55  jz      loc_140003AE4
0x140003a5b  sub     ecx, 1
0x140003a5e  jz      short loc_140003AD5
0x140003a60  sub     ecx, 1
0x140003a63  jz      short loc_140003AC6
0x140003a65  sub     ecx, 1
0x140003a68  jz      short loc_140003AB7
0x140003a6a  sub     ecx, 1
0x140003a6d  jz      short loc_140003AA8
0x140003a6f  cmp     ecx, 1
0x140003a72  jz      short loc_140003A99
0x140003a74  sub     r9b, 64h ; 'd'
0x140003a78  cmp     r9b, 31h ; '1'
0x140003a7c  ja      short loc_140003AF1
0x140003a7e  mov     eax, ebx
0x140003a80  neg     eax
0x140003a82  movzx   eax, r9b
0x140003a86  sbb     r8d, r8d
0x140003a89  and     r8d, 0FFFFFFCEh
0x140003a8d  add     r8d, 96h
0x140003a94  add     r8d, eax
0x140003a97  jmp     short loc_140003AF7
0x140003a99  mov     eax, ebx
0x140003a9b  xor     eax, 1
0x140003a9e  lea     r8d, ds:9[rax*2]
0x140003aa6  jmp     short loc_140003AF7
0x140003aa8  mov     eax, ebx
0x140003aaa  xor     eax, 1
0x140003aad  lea     r8d, ds:8[rax*2]
0x140003ab5  jmp     short loc_140003AF7
0x140003ab7  mov     eax, ebx
0x140003ab9  xor     eax, 1
0x140003abc  lea     r8d, ds:3[rax*4]
0x140003ac4  jmp     short loc_140003AF7
0x140003ac6  mov     eax, ebx
0x140003ac8  xor     eax, 1
0x140003acb  lea     r8d, ds:2[rax*4]
0x140003ad3  jmp     short loc_140003AF7
0x140003ad5  mov     eax, ebx
0x140003ad7  xor     eax, 1
0x140003ada  lea     r8d, ds:1[rax*4]
0x140003ae2  jmp     short loc_140003AF7
0x140003ae4  mov     r8d, ebx
0x140003ae7  xor     r8d, 1
0x140003aeb  shl     r8d, 2
0x140003aef  jmp     short loc_140003AF7
0x140003af1  mov     r8d, 0FFh
0x140003af7  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140003afc  test    eax, eax
0x140003afe  jz      short loc_140003B44
0x140003b00  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140003b07  test    rax, rax
0x140003b0a  jz      short loc_140003B44
0x140003b0c  mov     rdx, cs:off_140014730
0x140003b13  lea     rcx, [rsp+58h+arg_10]
0x140003b18  mov     [rsp+58h+var_20], 1
0x140003b21  mov     r9d, ebx
0x140003b24  mov     [rsp+58h+var_28], 0
0x140003b29  xor     r8d, r8d
0x140003b2c  mov     [rsp+58h+var_30], 0
0x140003b35  mov     [rsp+58h+var_38], rcx
0x140003b3a  mov     ecx, 360A098h
0x140003b3f  call    _guard_dispatch_icall
0x140003b44  add     rsp, 50h
0x140003b48  pop     rbx
0x140003b49  retn
```
