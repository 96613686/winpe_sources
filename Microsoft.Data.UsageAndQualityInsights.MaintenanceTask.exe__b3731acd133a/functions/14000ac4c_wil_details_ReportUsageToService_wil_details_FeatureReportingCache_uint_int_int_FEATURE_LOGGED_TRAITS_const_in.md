# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000ac4c`
- end: `0x14000ad7c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000a944`
- `0x14000af6c`
- `0x14000b00c`

## callees

- `0x14000ac4c`
- `0x14000ad84`
- `0x14000c010`

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
0x14000ac4c  mov     rax, rsp
0x14000ac4f  push    rbx
0x14000ac50  push    rbp
0x14000ac51  push    rsi
0x14000ac52  push    rdi
0x14000ac53  sub     rsp, 58h
0x14000ac57  mov     r11d, [rax+38h]
0x14000ac5b  mov     esi, edx
0x14000ac5d  mov     rbp, rcx
0x14000ac60  test    r11d, r11d
0x14000ac63  jz      loc_14000AD73
0x14000ac69  mov     ebx, [rsp+78h+arg_28]
0x14000ac70  mov     r10d, r11d
0x14000ac73  sub     r10d, 1
0x14000ac77  jz      loc_14000AD02
0x14000ac7d  sub     r10d, 1
0x14000ac81  jz      short loc_14000ACF4
0x14000ac83  sub     r10d, 1
0x14000ac87  jz      short loc_14000ACE6
0x14000ac89  sub     r10d, 1
0x14000ac8d  jz      short loc_14000ACD8
0x14000ac8f  sub     r10d, 1
0x14000ac93  jz      short loc_14000ACCA
0x14000ac95  cmp     r10d, 1
0x14000ac99  jz      short loc_14000ACBC
0x14000ac9b  sub     r11b, 64h ; 'd'
0x14000ac9f  cmp     r11b, 31h ; '1'
0x14000aca3  ja      short loc_14000AD0F
0x14000aca5  mov     eax, ebx
0x14000aca7  neg     eax
0x14000aca9  movzx   eax, r11b
0x14000acad  sbb     ecx, ecx
0x14000acaf  and     ecx, 0FFFFFFCEh
0x14000acb2  add     ecx, 96h
0x14000acb8  add     ecx, eax
0x14000acba  jmp     short loc_14000AD14
0x14000acbc  mov     eax, ebx
0x14000acbe  neg     eax
0x14000acc0  sbb     ecx, ecx
0x14000acc2  and     ecx, 0FFFFFFFEh
0x14000acc5  add     ecx, 0Bh
0x14000acc8  jmp     short loc_14000AD14
0x14000acca  mov     eax, ebx
0x14000accc  neg     eax
0x14000acce  sbb     ecx, ecx
0x14000acd0  and     ecx, 0FFFFFFFEh
0x14000acd3  add     ecx, 0Ah
0x14000acd6  jmp     short loc_14000AD14
0x14000acd8  mov     eax, ebx
0x14000acda  neg     eax
0x14000acdc  sbb     ecx, ecx
0x14000acde  and     ecx, 0FFFFFFFCh
0x14000ace1  add     ecx, 7
0x14000ace4  jmp     short loc_14000AD14
0x14000ace6  mov     eax, ebx
0x14000ace8  neg     eax
0x14000acea  sbb     ecx, ecx
0x14000acec  and     ecx, 0FFFFFFFCh
0x14000acef  add     ecx, 6
0x14000acf2  jmp     short loc_14000AD14
0x14000acf4  mov     eax, ebx
0x14000acf6  neg     eax
0x14000acf8  sbb     ecx, ecx
0x14000acfa  and     ecx, 0FFFFFFFCh
0x14000acfd  add     ecx, 5
0x14000ad00  jmp     short loc_14000AD14
0x14000ad02  mov     eax, ebx
0x14000ad04  neg     eax
0x14000ad06  sbb     ecx, ecx
0x14000ad08  not     ecx
0x14000ad0a  and     ecx, 4
0x14000ad0d  jmp     short loc_14000AD14
0x14000ad0f  mov     ecx, 0FFh
0x14000ad14  mov     rdi, [rsp+78h+arg_20]
0x14000ad1c  mov     al, [rdi+4]
0x14000ad1f  mov     byte ptr [rsp+78h+var_40], al
0x14000ad23  mov     dword ptr [rsp+78h+var_58], ecx
0x14000ad27  mov     rcx, rbp
0x14000ad2a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000ad2f  test    eax, eax
0x14000ad31  jz      short loc_14000AD73
0x14000ad33  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000ad3a  test    rax, rax
0x14000ad3d  jz      short loc_14000AD73
0x14000ad3f  mov     [rsp+78h+var_40], 1
0x14000ad48  lea     rcx, [rsp+78h+arg_30]
0x14000ad50  mov     [rsp+78h+var_48], 0
0x14000ad55  mov     r9d, ebx
0x14000ad58  mov     [rsp+78h+var_50], 0
0x14000ad61  xor     r8d, r8d
0x14000ad64  mov     [rsp+78h+var_58], rcx
0x14000ad69  mov     rdx, rdi
0x14000ad6c  mov     ecx, esi
0x14000ad6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad73  add     rsp, 58h
0x14000ad77  pop     rdi
0x14000ad78  pop     rsi
0x14000ad79  pop     rbp
0x14000ad7a  pop     rbx
0x14000ad7b  retn
```
