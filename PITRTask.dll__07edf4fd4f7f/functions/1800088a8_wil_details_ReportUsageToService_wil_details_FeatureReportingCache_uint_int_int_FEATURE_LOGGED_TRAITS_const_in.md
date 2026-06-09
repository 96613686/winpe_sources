# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800088a8`
- end: `0x1800089d6`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `302`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005ba0`
- `0x180005d04`
- `0x180005e88`
- `0x180008698`
- `0x18000874c`
- `0x1800087f4`

## callees

- `0x1800088a8`
- `0x1800089dc`
- `0x180012010`

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
  char v9; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2);
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
0x1800088a8  mov     rax, rsp
0x1800088ab  mov     [rax+18h], rbx
0x1800088af  mov     [rax+20h], rsi
0x1800088b3  push    rdi
0x1800088b4  sub     rsp, 50h
0x1800088b8  mov     rsi, [rsp+58h+arg_20]
0x1800088c0  mov     edi, edx
0x1800088c2  mov     edx, [rax+38h]
0x1800088c5  mov     r10, rcx
0x1800088c8  test    edx, edx
0x1800088ca  jz      loc_1800089C6
0x1800088d0  mov     ebx, [rsp+58h+arg_28]
0x1800088d7  mov     ecx, edx
0x1800088d9  sub     ecx, 1
0x1800088dc  jz      short loc_18000895B
0x1800088de  sub     ecx, 1
0x1800088e1  jz      short loc_18000894D
0x1800088e3  sub     ecx, 1
0x1800088e6  jz      short loc_18000893F
0x1800088e8  sub     ecx, 1
0x1800088eb  jz      short loc_180008931
0x1800088ed  sub     ecx, 1
0x1800088f0  jz      short loc_180008923
0x1800088f2  cmp     ecx, 1
0x1800088f5  jz      short loc_180008915
0x1800088f7  sub     dl, 64h ; 'd'
0x1800088fa  cmp     dl, 31h ; '1'
0x1800088fd  ja      short loc_180008968
0x1800088ff  mov     eax, ebx
0x180008901  neg     eax
0x180008903  movzx   eax, dl
0x180008906  sbb     ecx, ecx
0x180008908  and     ecx, 0FFFFFFCEh
0x18000890b  add     ecx, 96h
0x180008911  add     ecx, eax
0x180008913  jmp     short loc_18000896D
0x180008915  mov     eax, ebx
0x180008917  neg     eax
0x180008919  sbb     ecx, ecx
0x18000891b  and     ecx, 0FFFFFFFEh
0x18000891e  add     ecx, 0Bh
0x180008921  jmp     short loc_18000896D
0x180008923  mov     eax, ebx
0x180008925  neg     eax
0x180008927  sbb     ecx, ecx
0x180008929  and     ecx, 0FFFFFFFEh
0x18000892c  add     ecx, 0Ah
0x18000892f  jmp     short loc_18000896D
0x180008931  mov     eax, ebx
0x180008933  neg     eax
0x180008935  sbb     ecx, ecx
0x180008937  and     ecx, 0FFFFFFFCh
0x18000893a  add     ecx, 7
0x18000893d  jmp     short loc_18000896D
0x18000893f  mov     eax, ebx
0x180008941  neg     eax
0x180008943  sbb     ecx, ecx
0x180008945  and     ecx, 0FFFFFFFCh
0x180008948  add     ecx, 6
0x18000894b  jmp     short loc_18000896D
0x18000894d  mov     eax, ebx
0x18000894f  neg     eax
0x180008951  sbb     ecx, ecx
0x180008953  and     ecx, 0FFFFFFFCh
0x180008956  add     ecx, 5
0x180008959  jmp     short loc_18000896D
0x18000895b  mov     eax, ebx
0x18000895d  neg     eax
0x18000895f  sbb     ecx, ecx
0x180008961  not     ecx
0x180008963  and     ecx, 4
0x180008966  jmp     short loc_18000896D
0x180008968  mov     ecx, 0FFh
0x18000896d  mov     al, [rsi+4]
0x180008970  mov     edx, edi
0x180008972  mov     byte ptr [rsp+58h+var_20], al
0x180008976  mov     dword ptr [rsp+58h+var_38], ecx
0x18000897a  mov     rcx, r10
0x18000897d  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180008982  test    eax, eax
0x180008984  jz      short loc_1800089C6
0x180008986  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000898d  test    rax, rax
0x180008990  jz      short loc_1800089C6
0x180008992  mov     [rsp+58h+var_20], 1
0x18000899b  lea     rcx, [rsp+58h+arg_30]
0x1800089a3  mov     [rsp+58h+var_28], 0
0x1800089a8  mov     r9d, ebx
0x1800089ab  mov     [rsp+58h+var_30], 0
0x1800089b4  xor     r8d, r8d
0x1800089b7  mov     [rsp+58h+var_38], rcx
0x1800089bc  mov     rdx, rsi
0x1800089bf  mov     ecx, edi
0x1800089c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c6  mov     rbx, [rsp+58h+arg_10]
0x1800089cb  mov     rsi, [rsp+58h+arg_18]
0x1800089d0  add     rsp, 50h
0x1800089d4  pop     rdi
0x1800089d5  retn
```
