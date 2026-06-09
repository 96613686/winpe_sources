# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180043384`
- end: `0x1800434a9`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180043830`

## callees

- `0x180043384`
- `0x1800434b0`
- `0x18004d010`

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
0x180043384  mov     [rsp+arg_0], rbx
0x180043389  mov     [rsp+arg_10], r8d
0x18004338e  push    rdi
0x18004338f  sub     rsp, 50h
0x180043393  mov     ebx, edx
0x180043395  mov     r10d, r8d
0x180043398  and     ebx, 1
0x18004339b  mov     rdi, rcx
0x18004339e  mov     r9d, r8d
0x1800433a1  test    r8d, r8d
0x1800433a4  jz      loc_18004344F
0x1800433aa  sub     r9d, 1
0x1800433ae  jz      loc_180043442
0x1800433b4  sub     r9d, 1
0x1800433b8  jz      short loc_180043433
0x1800433ba  sub     r9d, 1
0x1800433be  jz      short loc_180043424
0x1800433c0  sub     r9d, 1
0x1800433c4  jz      short loc_180043415
0x1800433c6  sub     r9d, 1
0x1800433ca  jz      short loc_180043406
0x1800433cc  cmp     r9d, 1
0x1800433d0  jz      short loc_1800433F7
0x1800433d2  sub     r10b, 64h ; 'd'
0x1800433d6  cmp     r10b, 31h ; '1'
0x1800433da  ja      short loc_18004344F
0x1800433dc  mov     eax, ebx
0x1800433de  neg     eax
0x1800433e0  movzx   eax, r10b
0x1800433e4  sbb     r8d, r8d
0x1800433e7  and     r8d, 0FFFFFFCEh
0x1800433eb  add     r8d, 96h
0x1800433f2  add     r8d, eax
0x1800433f5  jmp     short loc_180043455
0x1800433f7  mov     eax, ebx
0x1800433f9  xor     eax, 1
0x1800433fc  lea     r8d, ds:9[rax*2]
0x180043404  jmp     short loc_180043455
0x180043406  mov     eax, ebx
0x180043408  xor     eax, 1
0x18004340b  lea     r8d, ds:8[rax*2]
0x180043413  jmp     short loc_180043455
0x180043415  mov     eax, ebx
0x180043417  xor     eax, 1
0x18004341a  lea     r8d, ds:3[rax*4]
0x180043422  jmp     short loc_180043455
0x180043424  mov     eax, ebx
0x180043426  xor     eax, 1
0x180043429  lea     r8d, ds:2[rax*4]
0x180043431  jmp     short loc_180043455
0x180043433  mov     eax, ebx
0x180043435  xor     eax, 1
0x180043438  lea     r8d, ds:1[rax*4]
0x180043440  jmp     short loc_180043455
0x180043442  mov     r8d, ebx
0x180043445  xor     r8d, 1
0x180043449  shl     r8d, 2
0x18004344d  jmp     short loc_180043455
0x18004344f  mov     r8d, 0FFh
0x180043455  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18004345a  test    eax, eax
0x18004345c  jz      short loc_18004349D
0x18004345e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180043465  test    rax, rax
0x180043468  jz      short loc_18004349D
0x18004346a  mov     rdx, [rdi+10h]
0x18004346e  lea     rcx, [rsp+58h+arg_10]
0x180043473  mov     [rsp+58h+var_20], 1
0x18004347c  mov     r9d, ebx
0x18004347f  mov     [rsp+58h+var_28], 0
0x180043484  xor     r8d, r8d
0x180043487  mov     [rsp+58h+var_30], 0
0x180043490  mov     [rsp+58h+var_38], rcx
0x180043495  mov     ecx, [rdi+18h]
0x180043498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004349d  mov     rbx, [rsp+58h+arg_0]
0x1800434a2  add     rsp, 50h
0x1800434a6  pop     rdi
0x1800434a7  retn
```
