# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000870c`
- end: `0x140008831`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140008bd0`

## callees

- `0x14000870c`
- `0x140008838`
- `0x140047e90`

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
0x14000870c  mov     [rsp+arg_0], rbx
0x140008711  mov     [rsp+arg_10], r8d
0x140008716  push    rdi
0x140008717  sub     rsp, 50h
0x14000871b  mov     ebx, edx
0x14000871d  mov     r10d, r8d
0x140008720  and     ebx, 1
0x140008723  mov     rdi, rcx
0x140008726  mov     r9d, r8d
0x140008729  test    r8d, r8d
0x14000872c  jz      loc_1400087D7
0x140008732  sub     r9d, 1
0x140008736  jz      loc_1400087CA
0x14000873c  sub     r9d, 1
0x140008740  jz      short loc_1400087BB
0x140008742  sub     r9d, 1
0x140008746  jz      short loc_1400087AC
0x140008748  sub     r9d, 1
0x14000874c  jz      short loc_14000879D
0x14000874e  sub     r9d, 1
0x140008752  jz      short loc_14000878E
0x140008754  cmp     r9d, 1
0x140008758  jz      short loc_14000877F
0x14000875a  sub     r10b, 64h ; 'd'
0x14000875e  cmp     r10b, 31h ; '1'
0x140008762  ja      short loc_1400087D7
0x140008764  mov     eax, ebx
0x140008766  neg     eax
0x140008768  movzx   eax, r10b
0x14000876c  sbb     r8d, r8d
0x14000876f  and     r8d, 0FFFFFFCEh
0x140008773  add     r8d, 96h
0x14000877a  add     r8d, eax
0x14000877d  jmp     short loc_1400087DD
0x14000877f  mov     eax, ebx
0x140008781  xor     eax, 1
0x140008784  lea     r8d, ds:9[rax*2]
0x14000878c  jmp     short loc_1400087DD
0x14000878e  mov     eax, ebx
0x140008790  xor     eax, 1
0x140008793  lea     r8d, ds:8[rax*2]
0x14000879b  jmp     short loc_1400087DD
0x14000879d  mov     eax, ebx
0x14000879f  xor     eax, 1
0x1400087a2  lea     r8d, ds:3[rax*4]
0x1400087aa  jmp     short loc_1400087DD
0x1400087ac  mov     eax, ebx
0x1400087ae  xor     eax, 1
0x1400087b1  lea     r8d, ds:2[rax*4]
0x1400087b9  jmp     short loc_1400087DD
0x1400087bb  mov     eax, ebx
0x1400087bd  xor     eax, 1
0x1400087c0  lea     r8d, ds:1[rax*4]
0x1400087c8  jmp     short loc_1400087DD
0x1400087ca  mov     r8d, ebx
0x1400087cd  xor     r8d, 1
0x1400087d1  shl     r8d, 2
0x1400087d5  jmp     short loc_1400087DD
0x1400087d7  mov     r8d, 0FFh
0x1400087dd  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x1400087e2  test    eax, eax
0x1400087e4  jz      short loc_140008825
0x1400087e6  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400087ed  test    rax, rax
0x1400087f0  jz      short loc_140008825
0x1400087f2  mov     rdx, [rdi+10h]
0x1400087f6  lea     rcx, [rsp+58h+arg_10]
0x1400087fb  mov     [rsp+58h+var_20], 1
0x140008804  mov     r9d, ebx
0x140008807  mov     [rsp+58h+var_28], 0
0x14000880c  xor     r8d, r8d
0x14000880f  mov     [rsp+58h+var_30], 0
0x140008818  mov     [rsp+58h+var_38], rcx
0x14000881d  mov     ecx, [rdi+18h]
0x140008820  call    _guard_dispatch_icall
0x140008825  mov     rbx, [rsp+58h+arg_0]
0x14000882a  add     rsp, 50h
0x14000882e  pop     rdi
0x14000882f  retn
```
