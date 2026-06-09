# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000ad14`
- end: `0x18000ae44`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `16`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ac7c`
- `0x18000aff4`
- `0x18000b090`
- `0x18000b81c`
- `0x18000db48`
- `0x18001109c`
- `0x180011dc0`
- `0x180011e60`
- `0x180011f3c`
- `0x180011fdc`
- `0x180017710`
- `0x1800177b0`
- `0x180017890`
- `0x180017930`
- `0x1800179d0`
- `0x180017a70`

## callees

- `0x18000ad14`
- `0x18000ae4c`
- `0x180019010`

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
0x18000ad14  mov     rax, rsp
0x18000ad17  push    rbx
0x18000ad18  push    rbp
0x18000ad19  push    rsi
0x18000ad1a  push    rdi
0x18000ad1b  sub     rsp, 58h
0x18000ad1f  mov     r11d, [rax+38h]
0x18000ad23  mov     esi, edx
0x18000ad25  mov     rbp, rcx
0x18000ad28  test    r11d, r11d
0x18000ad2b  jz      loc_18000AE3B
0x18000ad31  mov     ebx, [rsp+78h+arg_28]
0x18000ad38  mov     r10d, r11d
0x18000ad3b  sub     r10d, 1
0x18000ad3f  jz      loc_18000ADCA
0x18000ad45  sub     r10d, 1
0x18000ad49  jz      short loc_18000ADBC
0x18000ad4b  sub     r10d, 1
0x18000ad4f  jz      short loc_18000ADAE
0x18000ad51  sub     r10d, 1
0x18000ad55  jz      short loc_18000ADA0
0x18000ad57  sub     r10d, 1
0x18000ad5b  jz      short loc_18000AD92
0x18000ad5d  cmp     r10d, 1
0x18000ad61  jz      short loc_18000AD84
0x18000ad63  sub     r11b, 64h ; 'd'
0x18000ad67  cmp     r11b, 31h ; '1'
0x18000ad6b  ja      short loc_18000ADD7
0x18000ad6d  mov     eax, ebx
0x18000ad6f  neg     eax
0x18000ad71  movzx   eax, r11b
0x18000ad75  sbb     ecx, ecx
0x18000ad77  and     ecx, 0FFFFFFCEh
0x18000ad7a  add     ecx, 96h
0x18000ad80  add     ecx, eax
0x18000ad82  jmp     short loc_18000ADDC
0x18000ad84  mov     eax, ebx
0x18000ad86  neg     eax
0x18000ad88  sbb     ecx, ecx
0x18000ad8a  and     ecx, 0FFFFFFFEh
0x18000ad8d  add     ecx, 0Bh
0x18000ad90  jmp     short loc_18000ADDC
0x18000ad92  mov     eax, ebx
0x18000ad94  neg     eax
0x18000ad96  sbb     ecx, ecx
0x18000ad98  and     ecx, 0FFFFFFFEh
0x18000ad9b  add     ecx, 0Ah
0x18000ad9e  jmp     short loc_18000ADDC
0x18000ada0  mov     eax, ebx
0x18000ada2  neg     eax
0x18000ada4  sbb     ecx, ecx
0x18000ada6  and     ecx, 0FFFFFFFCh
0x18000ada9  add     ecx, 7
0x18000adac  jmp     short loc_18000ADDC
0x18000adae  mov     eax, ebx
0x18000adb0  neg     eax
0x18000adb2  sbb     ecx, ecx
0x18000adb4  and     ecx, 0FFFFFFFCh
0x18000adb7  add     ecx, 6
0x18000adba  jmp     short loc_18000ADDC
0x18000adbc  mov     eax, ebx
0x18000adbe  neg     eax
0x18000adc0  sbb     ecx, ecx
0x18000adc2  and     ecx, 0FFFFFFFCh
0x18000adc5  add     ecx, 5
0x18000adc8  jmp     short loc_18000ADDC
0x18000adca  mov     eax, ebx
0x18000adcc  neg     eax
0x18000adce  sbb     ecx, ecx
0x18000add0  not     ecx
0x18000add2  and     ecx, 4
0x18000add5  jmp     short loc_18000ADDC
0x18000add7  mov     ecx, 0FFh
0x18000addc  mov     rdi, [rsp+78h+arg_20]
0x18000ade4  mov     al, [rdi+4]
0x18000ade7  mov     byte ptr [rsp+78h+var_40], al
0x18000adeb  mov     dword ptr [rsp+78h+var_58], ecx
0x18000adef  mov     rcx, rbp
0x18000adf2  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000adf7  test    eax, eax
0x18000adf9  jz      short loc_18000AE3B
0x18000adfb  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000ae02  test    rax, rax
0x18000ae05  jz      short loc_18000AE3B
0x18000ae07  mov     [rsp+78h+var_40], 1
0x18000ae10  lea     rcx, [rsp+78h+arg_30]
0x18000ae18  mov     [rsp+78h+var_48], 0
0x18000ae1d  mov     r9d, ebx
0x18000ae20  mov     [rsp+78h+var_50], 0
0x18000ae29  xor     r8d, r8d
0x18000ae2c  mov     [rsp+78h+var_58], rcx
0x18000ae31  mov     rdx, rdi
0x18000ae34  mov     ecx, esi
0x18000ae36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3b  add     rsp, 58h
0x18000ae3f  pop     rdi
0x18000ae40  pop     rsi
0x18000ae41  pop     rbp
0x18000ae42  pop     rbx
0x18000ae43  retn
```
