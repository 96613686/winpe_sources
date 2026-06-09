# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000ab68`
- end: `0x18000ac98`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `22`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a820`
- `0x180014478`
- `0x1800145c0`
- `0x18001494c`
- `0x180014abc`
- `0x180014c2c`
- `0x180014d9c`
- `0x180014f0c`
- `0x18001507c`
- `0x180015228`
- `0x1800152c0`
- `0x18001535c`
- `0x180015438`
- `0x1800154d8`
- `0x180015574`
- `0x180015610`
- `0x1800156ac`
- `0x180015748`
- `0x1800157e4`
- `0x180018bbc`
- `0x180018ffc`
- `0x1800246d0`

## callees

- `0x18000ab68`
- `0x18000aca0`
- `0x18002a010`

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
0x18000ab68  mov     rax, rsp
0x18000ab6b  push    rbx
0x18000ab6c  push    rbp
0x18000ab6d  push    rsi
0x18000ab6e  push    rdi
0x18000ab6f  sub     rsp, 58h
0x18000ab73  mov     r11d, [rax+38h]
0x18000ab77  mov     esi, edx
0x18000ab79  mov     rbp, rcx
0x18000ab7c  test    r11d, r11d
0x18000ab7f  jz      loc_18000AC8F
0x18000ab85  mov     ebx, [rsp+78h+arg_28]
0x18000ab8c  mov     r10d, r11d
0x18000ab8f  sub     r10d, 1
0x18000ab93  jz      loc_18000AC1E
0x18000ab99  sub     r10d, 1
0x18000ab9d  jz      short loc_18000AC10
0x18000ab9f  sub     r10d, 1
0x18000aba3  jz      short loc_18000AC02
0x18000aba5  sub     r10d, 1
0x18000aba9  jz      short loc_18000ABF4
0x18000abab  sub     r10d, 1
0x18000abaf  jz      short loc_18000ABE6
0x18000abb1  cmp     r10d, 1
0x18000abb5  jz      short loc_18000ABD8
0x18000abb7  sub     r11b, 64h ; 'd'
0x18000abbb  cmp     r11b, 31h ; '1'
0x18000abbf  ja      short loc_18000AC2B
0x18000abc1  mov     eax, ebx
0x18000abc3  neg     eax
0x18000abc5  movzx   eax, r11b
0x18000abc9  sbb     ecx, ecx
0x18000abcb  and     ecx, 0FFFFFFCEh
0x18000abce  add     ecx, 96h
0x18000abd4  add     ecx, eax
0x18000abd6  jmp     short loc_18000AC30
0x18000abd8  mov     eax, ebx
0x18000abda  neg     eax
0x18000abdc  sbb     ecx, ecx
0x18000abde  and     ecx, 0FFFFFFFEh
0x18000abe1  add     ecx, 0Bh
0x18000abe4  jmp     short loc_18000AC30
0x18000abe6  mov     eax, ebx
0x18000abe8  neg     eax
0x18000abea  sbb     ecx, ecx
0x18000abec  and     ecx, 0FFFFFFFEh
0x18000abef  add     ecx, 0Ah
0x18000abf2  jmp     short loc_18000AC30
0x18000abf4  mov     eax, ebx
0x18000abf6  neg     eax
0x18000abf8  sbb     ecx, ecx
0x18000abfa  and     ecx, 0FFFFFFFCh
0x18000abfd  add     ecx, 7
0x18000ac00  jmp     short loc_18000AC30
0x18000ac02  mov     eax, ebx
0x18000ac04  neg     eax
0x18000ac06  sbb     ecx, ecx
0x18000ac08  and     ecx, 0FFFFFFFCh
0x18000ac0b  add     ecx, 6
0x18000ac0e  jmp     short loc_18000AC30
0x18000ac10  mov     eax, ebx
0x18000ac12  neg     eax
0x18000ac14  sbb     ecx, ecx
0x18000ac16  and     ecx, 0FFFFFFFCh
0x18000ac19  add     ecx, 5
0x18000ac1c  jmp     short loc_18000AC30
0x18000ac1e  mov     eax, ebx
0x18000ac20  neg     eax
0x18000ac22  sbb     ecx, ecx
0x18000ac24  not     ecx
0x18000ac26  and     ecx, 4
0x18000ac29  jmp     short loc_18000AC30
0x18000ac2b  mov     ecx, 0FFh
0x18000ac30  mov     rdi, [rsp+78h+arg_20]
0x18000ac38  mov     al, [rdi+4]
0x18000ac3b  mov     byte ptr [rsp+78h+var_40], al
0x18000ac3f  mov     dword ptr [rsp+78h+var_58], ecx
0x18000ac43  mov     rcx, rbp
0x18000ac46  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000ac4b  test    eax, eax
0x18000ac4d  jz      short loc_18000AC8F
0x18000ac4f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000ac56  test    rax, rax
0x18000ac59  jz      short loc_18000AC8F
0x18000ac5b  mov     [rsp+78h+var_40], 1
0x18000ac64  lea     rcx, [rsp+78h+arg_30]
0x18000ac6c  mov     [rsp+78h+var_48], 0
0x18000ac71  mov     r9d, ebx
0x18000ac74  mov     [rsp+78h+var_50], 0
0x18000ac7d  xor     r8d, r8d
0x18000ac80  mov     [rsp+78h+var_58], rcx
0x18000ac85  mov     rdx, rdi
0x18000ac88  mov     ecx, esi
0x18000ac8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac8f  add     rsp, 58h
0x18000ac93  pop     rdi
0x18000ac94  pop     rsi
0x18000ac95  pop     rbp
0x18000ac96  pop     rbx
0x18000ac97  retn
```
