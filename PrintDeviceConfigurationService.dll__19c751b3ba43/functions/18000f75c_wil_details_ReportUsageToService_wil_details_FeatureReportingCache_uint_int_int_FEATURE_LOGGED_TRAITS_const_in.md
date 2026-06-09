# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000f75c`
- end: `0x18000f88c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f6c4`
- `0x180012388`
- `0x180012420`

## callees

- `0x18000f75c`
- `0x18000f894`
- `0x180018010`

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
0x18000f75c  mov     rax, rsp
0x18000f75f  push    rbx
0x18000f760  push    rbp
0x18000f761  push    rsi
0x18000f762  push    rdi
0x18000f763  sub     rsp, 58h
0x18000f767  mov     r11d, [rax+38h]
0x18000f76b  mov     esi, edx
0x18000f76d  mov     rbp, rcx
0x18000f770  test    r11d, r11d
0x18000f773  jz      loc_18000F883
0x18000f779  mov     ebx, [rsp+78h+arg_28]
0x18000f780  mov     r10d, r11d
0x18000f783  sub     r10d, 1
0x18000f787  jz      loc_18000F812
0x18000f78d  sub     r10d, 1
0x18000f791  jz      short loc_18000F804
0x18000f793  sub     r10d, 1
0x18000f797  jz      short loc_18000F7F6
0x18000f799  sub     r10d, 1
0x18000f79d  jz      short loc_18000F7E8
0x18000f79f  sub     r10d, 1
0x18000f7a3  jz      short loc_18000F7DA
0x18000f7a5  cmp     r10d, 1
0x18000f7a9  jz      short loc_18000F7CC
0x18000f7ab  sub     r11b, 64h ; 'd'
0x18000f7af  cmp     r11b, 31h ; '1'
0x18000f7b3  ja      short loc_18000F81F
0x18000f7b5  mov     eax, ebx
0x18000f7b7  neg     eax
0x18000f7b9  movzx   eax, r11b
0x18000f7bd  sbb     ecx, ecx
0x18000f7bf  and     ecx, 0FFFFFFCEh
0x18000f7c2  add     ecx, 96h
0x18000f7c8  add     ecx, eax
0x18000f7ca  jmp     short loc_18000F824
0x18000f7cc  mov     eax, ebx
0x18000f7ce  neg     eax
0x18000f7d0  sbb     ecx, ecx
0x18000f7d2  and     ecx, 0FFFFFFFEh
0x18000f7d5  add     ecx, 0Bh
0x18000f7d8  jmp     short loc_18000F824
0x18000f7da  mov     eax, ebx
0x18000f7dc  neg     eax
0x18000f7de  sbb     ecx, ecx
0x18000f7e0  and     ecx, 0FFFFFFFEh
0x18000f7e3  add     ecx, 0Ah
0x18000f7e6  jmp     short loc_18000F824
0x18000f7e8  mov     eax, ebx
0x18000f7ea  neg     eax
0x18000f7ec  sbb     ecx, ecx
0x18000f7ee  and     ecx, 0FFFFFFFCh
0x18000f7f1  add     ecx, 7
0x18000f7f4  jmp     short loc_18000F824
0x18000f7f6  mov     eax, ebx
0x18000f7f8  neg     eax
0x18000f7fa  sbb     ecx, ecx
0x18000f7fc  and     ecx, 0FFFFFFFCh
0x18000f7ff  add     ecx, 6
0x18000f802  jmp     short loc_18000F824
0x18000f804  mov     eax, ebx
0x18000f806  neg     eax
0x18000f808  sbb     ecx, ecx
0x18000f80a  and     ecx, 0FFFFFFFCh
0x18000f80d  add     ecx, 5
0x18000f810  jmp     short loc_18000F824
0x18000f812  mov     eax, ebx
0x18000f814  neg     eax
0x18000f816  sbb     ecx, ecx
0x18000f818  not     ecx
0x18000f81a  and     ecx, 4
0x18000f81d  jmp     short loc_18000F824
0x18000f81f  mov     ecx, 0FFh
0x18000f824  mov     rdi, [rsp+78h+arg_20]
0x18000f82c  mov     al, [rdi+4]
0x18000f82f  mov     byte ptr [rsp+78h+var_40], al
0x18000f833  mov     dword ptr [rsp+78h+var_58], ecx
0x18000f837  mov     rcx, rbp
0x18000f83a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000f83f  test    eax, eax
0x18000f841  jz      short loc_18000F883
0x18000f843  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000f84a  test    rax, rax
0x18000f84d  jz      short loc_18000F883
0x18000f84f  mov     [rsp+78h+var_40], 1
0x18000f858  lea     rcx, [rsp+78h+arg_30]
0x18000f860  mov     [rsp+78h+var_48], 0
0x18000f865  mov     r9d, ebx
0x18000f868  mov     [rsp+78h+var_50], 0
0x18000f871  xor     r8d, r8d
0x18000f874  mov     [rsp+78h+var_58], rcx
0x18000f879  mov     rdx, rdi
0x18000f87c  mov     ecx, esi
0x18000f87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f883  add     rsp, 58h
0x18000f887  pop     rdi
0x18000f888  pop     rsi
0x18000f889  pop     rbp
0x18000f88a  pop     rbx
0x18000f88b  retn
```
