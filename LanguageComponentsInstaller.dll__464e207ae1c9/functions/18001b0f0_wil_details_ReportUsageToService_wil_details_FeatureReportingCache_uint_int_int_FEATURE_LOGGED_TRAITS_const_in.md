# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001b0f0`
- end: `0x18001b210`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `288`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001777c`
- `0x18001afa4`
- `0x18001b04c`

## callees

- `0x18001b0f0`
- `0x18001b218`
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
  char v9; // [rsp+30h] [rbp-38h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF

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
0x18001b0f0  mov     rax, rsp
0x18001b0f3  push    rbx
0x18001b0f4  push    rsi
0x18001b0f5  push    rdi
0x18001b0f6  sub     rsp, 50h
0x18001b0fa  mov     rsi, [rsp+68h+arg_20]
0x18001b102  mov     edi, edx
0x18001b104  mov     edx, [rax+38h]
0x18001b107  mov     r10, rcx
0x18001b10a  test    edx, edx
0x18001b10c  jz      loc_18001B208
0x18001b112  mov     ebx, [rsp+68h+arg_28]
0x18001b119  mov     ecx, edx
0x18001b11b  sub     ecx, 1
0x18001b11e  jz      short loc_18001B19D
0x18001b120  sub     ecx, 1
0x18001b123  jz      short loc_18001B18F
0x18001b125  sub     ecx, 1
0x18001b128  jz      short loc_18001B181
0x18001b12a  sub     ecx, 1
0x18001b12d  jz      short loc_18001B173
0x18001b12f  sub     ecx, 1
0x18001b132  jz      short loc_18001B165
0x18001b134  cmp     ecx, 1
0x18001b137  jz      short loc_18001B157
0x18001b139  sub     dl, 64h ; 'd'
0x18001b13c  cmp     dl, 31h ; '1'
0x18001b13f  ja      short loc_18001B1AA
0x18001b141  mov     eax, ebx
0x18001b143  neg     eax
0x18001b145  movzx   eax, dl
0x18001b148  sbb     ecx, ecx
0x18001b14a  and     ecx, 0FFFFFFCEh
0x18001b14d  add     ecx, 96h
0x18001b153  add     ecx, eax
0x18001b155  jmp     short loc_18001B1AF
0x18001b157  mov     eax, ebx
0x18001b159  neg     eax
0x18001b15b  sbb     ecx, ecx
0x18001b15d  and     ecx, 0FFFFFFFEh
0x18001b160  add     ecx, 0Bh
0x18001b163  jmp     short loc_18001B1AF
0x18001b165  mov     eax, ebx
0x18001b167  neg     eax
0x18001b169  sbb     ecx, ecx
0x18001b16b  and     ecx, 0FFFFFFFEh
0x18001b16e  add     ecx, 0Ah
0x18001b171  jmp     short loc_18001B1AF
0x18001b173  mov     eax, ebx
0x18001b175  neg     eax
0x18001b177  sbb     ecx, ecx
0x18001b179  and     ecx, 0FFFFFFFCh
0x18001b17c  add     ecx, 7
0x18001b17f  jmp     short loc_18001B1AF
0x18001b181  mov     eax, ebx
0x18001b183  neg     eax
0x18001b185  sbb     ecx, ecx
0x18001b187  and     ecx, 0FFFFFFFCh
0x18001b18a  add     ecx, 6
0x18001b18d  jmp     short loc_18001B1AF
0x18001b18f  mov     eax, ebx
0x18001b191  neg     eax
0x18001b193  sbb     ecx, ecx
0x18001b195  and     ecx, 0FFFFFFFCh
0x18001b198  add     ecx, 5
0x18001b19b  jmp     short loc_18001B1AF
0x18001b19d  mov     eax, ebx
0x18001b19f  neg     eax
0x18001b1a1  sbb     ecx, ecx
0x18001b1a3  not     ecx
0x18001b1a5  and     ecx, 4
0x18001b1a8  jmp     short loc_18001B1AF
0x18001b1aa  mov     ecx, 0FFh
0x18001b1af  mov     al, [rsi+4]
0x18001b1b2  mov     edx, edi
0x18001b1b4  mov     byte ptr [rsp+68h+var_30], al
0x18001b1b8  mov     dword ptr [rsp+68h+var_48], ecx
0x18001b1bc  mov     rcx, r10
0x18001b1bf  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001b1c4  test    eax, eax
0x18001b1c6  jz      short loc_18001B208
0x18001b1c8  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001b1cf  test    rax, rax
0x18001b1d2  jz      short loc_18001B208
0x18001b1d4  mov     [rsp+68h+var_30], 1
0x18001b1dd  lea     rcx, [rsp+68h+arg_30]
0x18001b1e5  mov     [rsp+68h+var_38], 0
0x18001b1ea  mov     r9d, ebx
0x18001b1ed  mov     [rsp+68h+var_40], 0
0x18001b1f6  xor     r8d, r8d
0x18001b1f9  mov     [rsp+68h+var_48], rcx
0x18001b1fe  mov     rdx, rsi
0x18001b201  mov     ecx, edi
0x18001b203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b208  add     rsp, 50h
0x18001b20c  pop     rdi
0x18001b20d  pop     rsi
0x18001b20e  pop     rbx
0x18001b20f  retn
```
