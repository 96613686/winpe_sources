# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000cc60`
- end: `0x18000cd90`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `17`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000c39c`
- `0x18000cb4c`
- `0x18000cbd4`
- `0x180012704`
- `0x180015b2c`
- `0x180015c7c`
- `0x180015dcc`
- `0x180015f1c`
- `0x18001606c`
- `0x180017224`
- `0x1800172b0`
- `0x18001733c`
- `0x1800173c8`
- `0x180017450`
- `0x1800174d8`
- `0x180017560`
- `0x1800175e8`

## callees

- `0x18000cc60`
- `0x18000cd98`
- `0x18001c010`

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
0x18000cc60  mov     rax, rsp
0x18000cc63  push    rbx
0x18000cc64  push    rbp
0x18000cc65  push    rsi
0x18000cc66  push    rdi
0x18000cc67  sub     rsp, 58h
0x18000cc6b  mov     r11d, [rax+38h]
0x18000cc6f  mov     esi, edx
0x18000cc71  mov     rbp, rcx
0x18000cc74  test    r11d, r11d
0x18000cc77  jz      loc_18000CD87
0x18000cc7d  mov     ebx, [rsp+78h+arg_28]
0x18000cc84  mov     r10d, r11d
0x18000cc87  sub     r10d, 1
0x18000cc8b  jz      loc_18000CD16
0x18000cc91  sub     r10d, 1
0x18000cc95  jz      short loc_18000CD08
0x18000cc97  sub     r10d, 1
0x18000cc9b  jz      short loc_18000CCFA
0x18000cc9d  sub     r10d, 1
0x18000cca1  jz      short loc_18000CCEC
0x18000cca3  sub     r10d, 1
0x18000cca7  jz      short loc_18000CCDE
0x18000cca9  cmp     r10d, 1
0x18000ccad  jz      short loc_18000CCD0
0x18000ccaf  sub     r11b, 64h ; 'd'
0x18000ccb3  cmp     r11b, 31h ; '1'
0x18000ccb7  ja      short loc_18000CD23
0x18000ccb9  mov     eax, ebx
0x18000ccbb  neg     eax
0x18000ccbd  movzx   eax, r11b
0x18000ccc1  sbb     ecx, ecx
0x18000ccc3  and     ecx, 0FFFFFFCEh
0x18000ccc6  add     ecx, 96h
0x18000cccc  add     ecx, eax
0x18000ccce  jmp     short loc_18000CD28
0x18000ccd0  mov     eax, ebx
0x18000ccd2  neg     eax
0x18000ccd4  sbb     ecx, ecx
0x18000ccd6  and     ecx, 0FFFFFFFEh
0x18000ccd9  add     ecx, 0Bh
0x18000ccdc  jmp     short loc_18000CD28
0x18000ccde  mov     eax, ebx
0x18000cce0  neg     eax
0x18000cce2  sbb     ecx, ecx
0x18000cce4  and     ecx, 0FFFFFFFEh
0x18000cce7  add     ecx, 0Ah
0x18000ccea  jmp     short loc_18000CD28
0x18000ccec  mov     eax, ebx
0x18000ccee  neg     eax
0x18000ccf0  sbb     ecx, ecx
0x18000ccf2  and     ecx, 0FFFFFFFCh
0x18000ccf5  add     ecx, 7
0x18000ccf8  jmp     short loc_18000CD28
0x18000ccfa  mov     eax, ebx
0x18000ccfc  neg     eax
0x18000ccfe  sbb     ecx, ecx
0x18000cd00  and     ecx, 0FFFFFFFCh
0x18000cd03  add     ecx, 6
0x18000cd06  jmp     short loc_18000CD28
0x18000cd08  mov     eax, ebx
0x18000cd0a  neg     eax
0x18000cd0c  sbb     ecx, ecx
0x18000cd0e  and     ecx, 0FFFFFFFCh
0x18000cd11  add     ecx, 5
0x18000cd14  jmp     short loc_18000CD28
0x18000cd16  mov     eax, ebx
0x18000cd18  neg     eax
0x18000cd1a  sbb     ecx, ecx
0x18000cd1c  not     ecx
0x18000cd1e  and     ecx, 4
0x18000cd21  jmp     short loc_18000CD28
0x18000cd23  mov     ecx, 0FFh
0x18000cd28  mov     rdi, [rsp+78h+arg_20]
0x18000cd30  mov     al, [rdi+4]
0x18000cd33  mov     byte ptr [rsp+78h+var_40], al
0x18000cd37  mov     dword ptr [rsp+78h+var_58], ecx
0x18000cd3b  mov     rcx, rbp
0x18000cd3e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000cd43  test    eax, eax
0x18000cd45  jz      short loc_18000CD87
0x18000cd47  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000cd4e  test    rax, rax
0x18000cd51  jz      short loc_18000CD87
0x18000cd53  mov     [rsp+78h+var_40], 1
0x18000cd5c  lea     rcx, [rsp+78h+arg_30]
0x18000cd64  mov     [rsp+78h+var_48], 0
0x18000cd69  mov     r9d, ebx
0x18000cd6c  mov     [rsp+78h+var_50], 0
0x18000cd75  xor     r8d, r8d
0x18000cd78  mov     [rsp+78h+var_58], rcx
0x18000cd7d  mov     rdx, rdi
0x18000cd80  mov     ecx, esi
0x18000cd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd87  add     rsp, 58h
0x18000cd8b  pop     rdi
0x18000cd8c  pop     rsi
0x18000cd8d  pop     rbp
0x18000cd8e  pop     rbx
0x18000cd8f  retn
```
