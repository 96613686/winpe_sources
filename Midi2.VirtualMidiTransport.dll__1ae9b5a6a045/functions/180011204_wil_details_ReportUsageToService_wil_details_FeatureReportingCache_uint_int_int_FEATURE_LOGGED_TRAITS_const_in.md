# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180011204`
- end: `0x180011334`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180010060`
- `0x1800101d0`
- `0x180010340`
- `0x1800104b0`
- `0x180010620`
- `0x180010790`
- `0x180011a7c`
- `0x180011b1c`
- `0x180011bb8`
- `0x180011c54`
- `0x180011cf0`
- `0x180011d8c`
- `0x180011e28`

## callees

- `0x180011204`
- `0x18001133c`
- `0x180021010`

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
0x180011204  mov     rax, rsp
0x180011207  push    rbx
0x180011208  push    rbp
0x180011209  push    rsi
0x18001120a  push    rdi
0x18001120b  sub     rsp, 58h
0x18001120f  mov     r11d, [rax+38h]
0x180011213  mov     esi, edx
0x180011215  mov     rbp, rcx
0x180011218  test    r11d, r11d
0x18001121b  jz      loc_18001132B
0x180011221  mov     ebx, [rsp+78h+arg_28]
0x180011228  mov     r10d, r11d
0x18001122b  sub     r10d, 1
0x18001122f  jz      loc_1800112BA
0x180011235  sub     r10d, 1
0x180011239  jz      short loc_1800112AC
0x18001123b  sub     r10d, 1
0x18001123f  jz      short loc_18001129E
0x180011241  sub     r10d, 1
0x180011245  jz      short loc_180011290
0x180011247  sub     r10d, 1
0x18001124b  jz      short loc_180011282
0x18001124d  cmp     r10d, 1
0x180011251  jz      short loc_180011274
0x180011253  sub     r11b, 64h ; 'd'
0x180011257  cmp     r11b, 31h ; '1'
0x18001125b  ja      short loc_1800112C7
0x18001125d  mov     eax, ebx
0x18001125f  neg     eax
0x180011261  movzx   eax, r11b
0x180011265  sbb     ecx, ecx
0x180011267  and     ecx, 0FFFFFFCEh
0x18001126a  add     ecx, 96h
0x180011270  add     ecx, eax
0x180011272  jmp     short loc_1800112CC
0x180011274  mov     eax, ebx
0x180011276  neg     eax
0x180011278  sbb     ecx, ecx
0x18001127a  and     ecx, 0FFFFFFFEh
0x18001127d  add     ecx, 0Bh
0x180011280  jmp     short loc_1800112CC
0x180011282  mov     eax, ebx
0x180011284  neg     eax
0x180011286  sbb     ecx, ecx
0x180011288  and     ecx, 0FFFFFFFEh
0x18001128b  add     ecx, 0Ah
0x18001128e  jmp     short loc_1800112CC
0x180011290  mov     eax, ebx
0x180011292  neg     eax
0x180011294  sbb     ecx, ecx
0x180011296  and     ecx, 0FFFFFFFCh
0x180011299  add     ecx, 7
0x18001129c  jmp     short loc_1800112CC
0x18001129e  mov     eax, ebx
0x1800112a0  neg     eax
0x1800112a2  sbb     ecx, ecx
0x1800112a4  and     ecx, 0FFFFFFFCh
0x1800112a7  add     ecx, 6
0x1800112aa  jmp     short loc_1800112CC
0x1800112ac  mov     eax, ebx
0x1800112ae  neg     eax
0x1800112b0  sbb     ecx, ecx
0x1800112b2  and     ecx, 0FFFFFFFCh
0x1800112b5  add     ecx, 5
0x1800112b8  jmp     short loc_1800112CC
0x1800112ba  mov     eax, ebx
0x1800112bc  neg     eax
0x1800112be  sbb     ecx, ecx
0x1800112c0  not     ecx
0x1800112c2  and     ecx, 4
0x1800112c5  jmp     short loc_1800112CC
0x1800112c7  mov     ecx, 0FFh
0x1800112cc  mov     rdi, [rsp+78h+arg_20]
0x1800112d4  mov     al, [rdi+4]
0x1800112d7  mov     byte ptr [rsp+78h+var_40], al
0x1800112db  mov     dword ptr [rsp+78h+var_58], ecx
0x1800112df  mov     rcx, rbp
0x1800112e2  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800112e7  test    eax, eax
0x1800112e9  jz      short loc_18001132B
0x1800112eb  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800112f2  test    rax, rax
0x1800112f5  jz      short loc_18001132B
0x1800112f7  mov     [rsp+78h+var_40], 1
0x180011300  lea     rcx, [rsp+78h+arg_30]
0x180011308  mov     [rsp+78h+var_48], 0
0x18001130d  mov     r9d, ebx
0x180011310  mov     [rsp+78h+var_50], 0
0x180011319  xor     r8d, r8d
0x18001131c  mov     [rsp+78h+var_58], rcx
0x180011321  mov     rdx, rdi
0x180011324  mov     ecx, esi
0x180011326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001132b  add     rsp, 58h
0x18001132f  pop     rdi
0x180011330  pop     rsi
0x180011331  pop     rbp
0x180011332  pop     rbx
0x180011333  retn
```
