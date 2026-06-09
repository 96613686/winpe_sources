# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000c804`
- end: `0x18000c934`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000bb34`
- `0x18000bca4`
- `0x18000be14`
- `0x18000bf84`
- `0x18000c0f4`
- `0x18000dd78`
- `0x18000de18`
- `0x18000deb4`
- `0x18000df50`
- `0x18000dfec`
- `0x18000e088`

## callees

- `0x18000c804`
- `0x18000c93c`
- `0x18000f010`

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
0x18000c804  mov     rax, rsp
0x18000c807  push    rbx
0x18000c808  push    rbp
0x18000c809  push    rsi
0x18000c80a  push    rdi
0x18000c80b  sub     rsp, 58h
0x18000c80f  mov     r11d, [rax+38h]
0x18000c813  mov     esi, edx
0x18000c815  mov     rbp, rcx
0x18000c818  test    r11d, r11d
0x18000c81b  jz      loc_18000C92B
0x18000c821  mov     ebx, [rsp+78h+arg_28]
0x18000c828  mov     r10d, r11d
0x18000c82b  sub     r10d, 1
0x18000c82f  jz      loc_18000C8BA
0x18000c835  sub     r10d, 1
0x18000c839  jz      short loc_18000C8AC
0x18000c83b  sub     r10d, 1
0x18000c83f  jz      short loc_18000C89E
0x18000c841  sub     r10d, 1
0x18000c845  jz      short loc_18000C890
0x18000c847  sub     r10d, 1
0x18000c84b  jz      short loc_18000C882
0x18000c84d  cmp     r10d, 1
0x18000c851  jz      short loc_18000C874
0x18000c853  sub     r11b, 64h ; 'd'
0x18000c857  cmp     r11b, 31h ; '1'
0x18000c85b  ja      short loc_18000C8C7
0x18000c85d  mov     eax, ebx
0x18000c85f  neg     eax
0x18000c861  movzx   eax, r11b
0x18000c865  sbb     ecx, ecx
0x18000c867  and     ecx, 0FFFFFFCEh
0x18000c86a  add     ecx, 96h
0x18000c870  add     ecx, eax
0x18000c872  jmp     short loc_18000C8CC
0x18000c874  mov     eax, ebx
0x18000c876  neg     eax
0x18000c878  sbb     ecx, ecx
0x18000c87a  and     ecx, 0FFFFFFFEh
0x18000c87d  add     ecx, 0Bh
0x18000c880  jmp     short loc_18000C8CC
0x18000c882  mov     eax, ebx
0x18000c884  neg     eax
0x18000c886  sbb     ecx, ecx
0x18000c888  and     ecx, 0FFFFFFFEh
0x18000c88b  add     ecx, 0Ah
0x18000c88e  jmp     short loc_18000C8CC
0x18000c890  mov     eax, ebx
0x18000c892  neg     eax
0x18000c894  sbb     ecx, ecx
0x18000c896  and     ecx, 0FFFFFFFCh
0x18000c899  add     ecx, 7
0x18000c89c  jmp     short loc_18000C8CC
0x18000c89e  mov     eax, ebx
0x18000c8a0  neg     eax
0x18000c8a2  sbb     ecx, ecx
0x18000c8a4  and     ecx, 0FFFFFFFCh
0x18000c8a7  add     ecx, 6
0x18000c8aa  jmp     short loc_18000C8CC
0x18000c8ac  mov     eax, ebx
0x18000c8ae  neg     eax
0x18000c8b0  sbb     ecx, ecx
0x18000c8b2  and     ecx, 0FFFFFFFCh
0x18000c8b5  add     ecx, 5
0x18000c8b8  jmp     short loc_18000C8CC
0x18000c8ba  mov     eax, ebx
0x18000c8bc  neg     eax
0x18000c8be  sbb     ecx, ecx
0x18000c8c0  not     ecx
0x18000c8c2  and     ecx, 4
0x18000c8c5  jmp     short loc_18000C8CC
0x18000c8c7  mov     ecx, 0FFh
0x18000c8cc  mov     rdi, [rsp+78h+arg_20]
0x18000c8d4  mov     al, [rdi+4]
0x18000c8d7  mov     byte ptr [rsp+78h+var_40], al
0x18000c8db  mov     dword ptr [rsp+78h+var_58], ecx
0x18000c8df  mov     rcx, rbp
0x18000c8e2  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000c8e7  test    eax, eax
0x18000c8e9  jz      short loc_18000C92B
0x18000c8eb  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000c8f2  test    rax, rax
0x18000c8f5  jz      short loc_18000C92B
0x18000c8f7  mov     [rsp+78h+var_40], 1
0x18000c900  lea     rcx, [rsp+78h+arg_30]
0x18000c908  mov     [rsp+78h+var_48], 0
0x18000c90d  mov     r9d, ebx
0x18000c910  mov     [rsp+78h+var_50], 0
0x18000c919  xor     r8d, r8d
0x18000c91c  mov     [rsp+78h+var_58], rcx
0x18000c921  mov     rdx, rdi
0x18000c924  mov     ecx, esi
0x18000c926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c92b  add     rsp, 58h
0x18000c92f  pop     rdi
0x18000c930  pop     rsi
0x18000c931  pop     rbp
0x18000c932  pop     rbx
0x18000c933  retn
```
