# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000974c`
- end: `0x18000987c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009a28`
- `0x180013b8c`

## callees

- `0x18000974c`
- `0x180009884`
- `0x180023010`

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
0x18000974c  mov     rax, rsp
0x18000974f  push    rbx
0x180009750  push    rbp
0x180009751  push    rsi
0x180009752  push    rdi
0x180009753  sub     rsp, 58h
0x180009757  mov     r11d, [rax+38h]
0x18000975b  mov     esi, edx
0x18000975d  mov     rbp, rcx
0x180009760  test    r11d, r11d
0x180009763  jz      loc_180009873
0x180009769  mov     ebx, [rsp+78h+arg_28]
0x180009770  mov     r10d, r11d
0x180009773  sub     r10d, 1
0x180009777  jz      loc_180009802
0x18000977d  sub     r10d, 1
0x180009781  jz      short loc_1800097F4
0x180009783  sub     r10d, 1
0x180009787  jz      short loc_1800097E6
0x180009789  sub     r10d, 1
0x18000978d  jz      short loc_1800097D8
0x18000978f  sub     r10d, 1
0x180009793  jz      short loc_1800097CA
0x180009795  cmp     r10d, 1
0x180009799  jz      short loc_1800097BC
0x18000979b  sub     r11b, 64h ; 'd'
0x18000979f  cmp     r11b, 31h ; '1'
0x1800097a3  ja      short loc_18000980F
0x1800097a5  mov     eax, ebx
0x1800097a7  neg     eax
0x1800097a9  movzx   eax, r11b
0x1800097ad  sbb     ecx, ecx
0x1800097af  and     ecx, 0FFFFFFCEh
0x1800097b2  add     ecx, 96h
0x1800097b8  add     ecx, eax
0x1800097ba  jmp     short loc_180009814
0x1800097bc  mov     eax, ebx
0x1800097be  neg     eax
0x1800097c0  sbb     ecx, ecx
0x1800097c2  and     ecx, 0FFFFFFFEh
0x1800097c5  add     ecx, 0Bh
0x1800097c8  jmp     short loc_180009814
0x1800097ca  mov     eax, ebx
0x1800097cc  neg     eax
0x1800097ce  sbb     ecx, ecx
0x1800097d0  and     ecx, 0FFFFFFFEh
0x1800097d3  add     ecx, 0Ah
0x1800097d6  jmp     short loc_180009814
0x1800097d8  mov     eax, ebx
0x1800097da  neg     eax
0x1800097dc  sbb     ecx, ecx
0x1800097de  and     ecx, 0FFFFFFFCh
0x1800097e1  add     ecx, 7
0x1800097e4  jmp     short loc_180009814
0x1800097e6  mov     eax, ebx
0x1800097e8  neg     eax
0x1800097ea  sbb     ecx, ecx
0x1800097ec  and     ecx, 0FFFFFFFCh
0x1800097ef  add     ecx, 6
0x1800097f2  jmp     short loc_180009814
0x1800097f4  mov     eax, ebx
0x1800097f6  neg     eax
0x1800097f8  sbb     ecx, ecx
0x1800097fa  and     ecx, 0FFFFFFFCh
0x1800097fd  add     ecx, 5
0x180009800  jmp     short loc_180009814
0x180009802  mov     eax, ebx
0x180009804  neg     eax
0x180009806  sbb     ecx, ecx
0x180009808  not     ecx
0x18000980a  and     ecx, 4
0x18000980d  jmp     short loc_180009814
0x18000980f  mov     ecx, 0FFh
0x180009814  mov     rdi, [rsp+78h+arg_20]
0x18000981c  mov     al, [rdi+4]
0x18000981f  mov     byte ptr [rsp+78h+var_40], al
0x180009823  mov     dword ptr [rsp+78h+var_58], ecx
0x180009827  mov     rcx, rbp
0x18000982a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000982f  test    eax, eax
0x180009831  jz      short loc_180009873
0x180009833  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000983a  test    rax, rax
0x18000983d  jz      short loc_180009873
0x18000983f  mov     [rsp+78h+var_40], 1
0x180009848  lea     rcx, [rsp+78h+arg_30]
0x180009850  mov     [rsp+78h+var_48], 0
0x180009855  mov     r9d, ebx
0x180009858  mov     [rsp+78h+var_50], 0
0x180009861  xor     r8d, r8d
0x180009864  mov     [rsp+78h+var_58], rcx
0x180009869  mov     rdx, rdi
0x18000986c  mov     ecx, esi
0x18000986e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009873  add     rsp, 58h
0x180009877  pop     rdi
0x180009878  pop     rsi
0x180009879  pop     rbp
0x18000987a  pop     rbx
0x18000987b  retn
```
