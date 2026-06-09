# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140009590`
- end: `0x1400096c0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140005b90`
- `0x140005d00`
- `0x140005e70`
- `0x14000b5d4`
- `0x14000b674`
- `0x14000b710`
- `0x14000b7ac`

## callees

- `0x140009590`
- `0x1400096c8`
- `0x140012010`

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
0x140009590  mov     rax, rsp
0x140009593  push    rbx
0x140009594  push    rbp
0x140009595  push    rsi
0x140009596  push    rdi
0x140009597  sub     rsp, 58h
0x14000959b  mov     r11d, [rax+38h]
0x14000959f  mov     esi, edx
0x1400095a1  mov     rbp, rcx
0x1400095a4  test    r11d, r11d
0x1400095a7  jz      loc_1400096B7
0x1400095ad  mov     ebx, [rsp+78h+arg_28]
0x1400095b4  mov     r10d, r11d
0x1400095b7  sub     r10d, 1
0x1400095bb  jz      loc_140009646
0x1400095c1  sub     r10d, 1
0x1400095c5  jz      short loc_140009638
0x1400095c7  sub     r10d, 1
0x1400095cb  jz      short loc_14000962A
0x1400095cd  sub     r10d, 1
0x1400095d1  jz      short loc_14000961C
0x1400095d3  sub     r10d, 1
0x1400095d7  jz      short loc_14000960E
0x1400095d9  cmp     r10d, 1
0x1400095dd  jz      short loc_140009600
0x1400095df  sub     r11b, 64h ; 'd'
0x1400095e3  cmp     r11b, 31h ; '1'
0x1400095e7  ja      short loc_140009653
0x1400095e9  mov     eax, ebx
0x1400095eb  neg     eax
0x1400095ed  movzx   eax, r11b
0x1400095f1  sbb     ecx, ecx
0x1400095f3  and     ecx, 0FFFFFFCEh
0x1400095f6  add     ecx, 96h
0x1400095fc  add     ecx, eax
0x1400095fe  jmp     short loc_140009658
0x140009600  mov     eax, ebx
0x140009602  neg     eax
0x140009604  sbb     ecx, ecx
0x140009606  and     ecx, 0FFFFFFFEh
0x140009609  add     ecx, 0Bh
0x14000960c  jmp     short loc_140009658
0x14000960e  mov     eax, ebx
0x140009610  neg     eax
0x140009612  sbb     ecx, ecx
0x140009614  and     ecx, 0FFFFFFFEh
0x140009617  add     ecx, 0Ah
0x14000961a  jmp     short loc_140009658
0x14000961c  mov     eax, ebx
0x14000961e  neg     eax
0x140009620  sbb     ecx, ecx
0x140009622  and     ecx, 0FFFFFFFCh
0x140009625  add     ecx, 7
0x140009628  jmp     short loc_140009658
0x14000962a  mov     eax, ebx
0x14000962c  neg     eax
0x14000962e  sbb     ecx, ecx
0x140009630  and     ecx, 0FFFFFFFCh
0x140009633  add     ecx, 6
0x140009636  jmp     short loc_140009658
0x140009638  mov     eax, ebx
0x14000963a  neg     eax
0x14000963c  sbb     ecx, ecx
0x14000963e  and     ecx, 0FFFFFFFCh
0x140009641  add     ecx, 5
0x140009644  jmp     short loc_140009658
0x140009646  mov     eax, ebx
0x140009648  neg     eax
0x14000964a  sbb     ecx, ecx
0x14000964c  not     ecx
0x14000964e  and     ecx, 4
0x140009651  jmp     short loc_140009658
0x140009653  mov     ecx, 0FFh
0x140009658  mov     rdi, [rsp+78h+arg_20]
0x140009660  mov     al, [rdi+4]
0x140009663  mov     byte ptr [rsp+78h+var_40], al
0x140009667  mov     dword ptr [rsp+78h+var_58], ecx
0x14000966b  mov     rcx, rbp
0x14000966e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140009673  test    eax, eax
0x140009675  jz      short loc_1400096B7
0x140009677  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000967e  test    rax, rax
0x140009681  jz      short loc_1400096B7
0x140009683  mov     [rsp+78h+var_40], 1
0x14000968c  lea     rcx, [rsp+78h+arg_30]
0x140009694  mov     [rsp+78h+var_48], 0
0x140009699  mov     r9d, ebx
0x14000969c  mov     [rsp+78h+var_50], 0
0x1400096a5  xor     r8d, r8d
0x1400096a8  mov     [rsp+78h+var_58], rcx
0x1400096ad  mov     rdx, rdi
0x1400096b0  mov     ecx, esi
0x1400096b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096b7  add     rsp, 58h
0x1400096bb  pop     rdi
0x1400096bc  pop     rsi
0x1400096bd  pop     rbp
0x1400096be  pop     rbx
0x1400096bf  retn
```
