# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001e8d8`
- end: `0x18001ea08`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001e840`
- `0x180025990`
- `0x180025ad8`
- `0x180026338`
- `0x1800263d4`

## callees

- `0x18001e8d8`
- `0x18001ea10`
- `0x18002b010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  char v9; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v9 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e8d8  mov     rax, rsp
0x18001e8db  push    rbx
0x18001e8dc  push    rbp
0x18001e8dd  push    rsi
0x18001e8de  push    rdi
0x18001e8df  sub     rsp, 58h
0x18001e8e3  mov     r11d, [rax+38h]
0x18001e8e7  mov     esi, edx
0x18001e8e9  mov     rbp, rcx
0x18001e8ec  test    r11d, r11d
0x18001e8ef  jz      loc_18001E9FF
0x18001e8f5  mov     ebx, [rsp+78h+arg_28]
0x18001e8fc  mov     r10d, r11d
0x18001e8ff  sub     r10d, 1
0x18001e903  jz      loc_18001E98E
0x18001e909  sub     r10d, 1
0x18001e90d  jz      short loc_18001E980
0x18001e90f  sub     r10d, 1
0x18001e913  jz      short loc_18001E972
0x18001e915  sub     r10d, 1
0x18001e919  jz      short loc_18001E964
0x18001e91b  sub     r10d, 1
0x18001e91f  jz      short loc_18001E956
0x18001e921  cmp     r10d, 1
0x18001e925  jz      short loc_18001E948
0x18001e927  sub     r11b, 64h ; 'd'
0x18001e92b  cmp     r11b, 31h ; '1'
0x18001e92f  ja      short loc_18001E99B
0x18001e931  mov     eax, ebx
0x18001e933  neg     eax
0x18001e935  movzx   eax, r11b
0x18001e939  sbb     ecx, ecx
0x18001e93b  and     ecx, 0FFFFFFCEh
0x18001e93e  add     ecx, 96h
0x18001e944  add     ecx, eax
0x18001e946  jmp     short loc_18001E9A0
0x18001e948  mov     eax, ebx
0x18001e94a  neg     eax
0x18001e94c  sbb     ecx, ecx
0x18001e94e  and     ecx, 0FFFFFFFEh
0x18001e951  add     ecx, 0Bh
0x18001e954  jmp     short loc_18001E9A0
0x18001e956  mov     eax, ebx
0x18001e958  neg     eax
0x18001e95a  sbb     ecx, ecx
0x18001e95c  and     ecx, 0FFFFFFFEh
0x18001e95f  add     ecx, 0Ah
0x18001e962  jmp     short loc_18001E9A0
0x18001e964  mov     eax, ebx
0x18001e966  neg     eax
0x18001e968  sbb     ecx, ecx
0x18001e96a  and     ecx, 0FFFFFFFCh
0x18001e96d  add     ecx, 7
0x18001e970  jmp     short loc_18001E9A0
0x18001e972  mov     eax, ebx
0x18001e974  neg     eax
0x18001e976  sbb     ecx, ecx
0x18001e978  and     ecx, 0FFFFFFFCh
0x18001e97b  add     ecx, 6
0x18001e97e  jmp     short loc_18001E9A0
0x18001e980  mov     eax, ebx
0x18001e982  neg     eax
0x18001e984  sbb     ecx, ecx
0x18001e986  and     ecx, 0FFFFFFFCh
0x18001e989  add     ecx, 5
0x18001e98c  jmp     short loc_18001E9A0
0x18001e98e  mov     eax, ebx
0x18001e990  neg     eax
0x18001e992  sbb     ecx, ecx
0x18001e994  not     ecx
0x18001e996  and     ecx, 4
0x18001e999  jmp     short loc_18001E9A0
0x18001e99b  mov     ecx, 0FFh
0x18001e9a0  mov     rdi, [rsp+78h+arg_20]
0x18001e9a8  mov     al, [rdi+4]
0x18001e9ab  mov     byte ptr [rsp+78h+var_40], al
0x18001e9af  mov     dword ptr [rsp+78h+var_58], ecx
0x18001e9b3  mov     rcx, rbp
0x18001e9b6  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001e9bb  test    eax, eax
0x18001e9bd  jz      short loc_18001E9FF
0x18001e9bf  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001e9c6  test    rax, rax
0x18001e9c9  jz      short loc_18001E9FF
0x18001e9cb  mov     [rsp+78h+var_40], 1
0x18001e9d4  lea     rcx, [rsp+78h+arg_30]
0x18001e9dc  mov     [rsp+78h+var_48], 0
0x18001e9e1  mov     r9d, ebx
0x18001e9e4  mov     [rsp+78h+var_50], 0
0x18001e9ed  xor     r8d, r8d
0x18001e9f0  mov     [rsp+78h+var_58], rcx
0x18001e9f5  mov     rdx, rdi
0x18001e9f8  mov     ecx, esi
0x18001e9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ff  add     rsp, 58h
0x18001ea03  pop     rdi
0x18001ea04  pop     rsi
0x18001ea05  pop     rbp
0x18001ea06  pop     rbx
0x18001ea07  retn
```
