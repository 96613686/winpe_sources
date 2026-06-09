# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000f9f0`
- end: `0x18000fb20`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `19`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f13c`
- `0x180010d6c`
- `0x180027788`
- `0x1800278d0`
- `0x180027b4c`
- `0x180027cbc`
- `0x180027e2c`
- `0x180027f9c`
- `0x18002810c`
- `0x18002827c`
- `0x180028504`
- `0x1800285a0`
- `0x18002863c`
- `0x1800286dc`
- `0x180028778`
- `0x180028814`
- `0x1800288b0`
- `0x18002894c`
- `0x1800289e8`

## callees

- `0x18000f9f0`
- `0x18000fb28`
- `0x180037010`

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
0x18000f9f0  mov     rax, rsp
0x18000f9f3  push    rbx
0x18000f9f4  push    rbp
0x18000f9f5  push    rsi
0x18000f9f6  push    rdi
0x18000f9f7  sub     rsp, 58h
0x18000f9fb  mov     r11d, [rax+38h]
0x18000f9ff  mov     esi, edx
0x18000fa01  mov     rbp, rcx
0x18000fa04  test    r11d, r11d
0x18000fa07  jz      loc_18000FB17
0x18000fa0d  mov     ebx, [rsp+78h+arg_28]
0x18000fa14  mov     r10d, r11d
0x18000fa17  sub     r10d, 1
0x18000fa1b  jz      loc_18000FAA6
0x18000fa21  sub     r10d, 1
0x18000fa25  jz      short loc_18000FA98
0x18000fa27  sub     r10d, 1
0x18000fa2b  jz      short loc_18000FA8A
0x18000fa2d  sub     r10d, 1
0x18000fa31  jz      short loc_18000FA7C
0x18000fa33  sub     r10d, 1
0x18000fa37  jz      short loc_18000FA6E
0x18000fa39  cmp     r10d, 1
0x18000fa3d  jz      short loc_18000FA60
0x18000fa3f  sub     r11b, 64h ; 'd'
0x18000fa43  cmp     r11b, 31h ; '1'
0x18000fa47  ja      short loc_18000FAB3
0x18000fa49  mov     eax, ebx
0x18000fa4b  neg     eax
0x18000fa4d  movzx   eax, r11b
0x18000fa51  sbb     ecx, ecx
0x18000fa53  and     ecx, 0FFFFFFCEh
0x18000fa56  add     ecx, 96h
0x18000fa5c  add     ecx, eax
0x18000fa5e  jmp     short loc_18000FAB8
0x18000fa60  mov     eax, ebx
0x18000fa62  neg     eax
0x18000fa64  sbb     ecx, ecx
0x18000fa66  and     ecx, 0FFFFFFFEh
0x18000fa69  add     ecx, 0Bh
0x18000fa6c  jmp     short loc_18000FAB8
0x18000fa6e  mov     eax, ebx
0x18000fa70  neg     eax
0x18000fa72  sbb     ecx, ecx
0x18000fa74  and     ecx, 0FFFFFFFEh
0x18000fa77  add     ecx, 0Ah
0x18000fa7a  jmp     short loc_18000FAB8
0x18000fa7c  mov     eax, ebx
0x18000fa7e  neg     eax
0x18000fa80  sbb     ecx, ecx
0x18000fa82  and     ecx, 0FFFFFFFCh
0x18000fa85  add     ecx, 7
0x18000fa88  jmp     short loc_18000FAB8
0x18000fa8a  mov     eax, ebx
0x18000fa8c  neg     eax
0x18000fa8e  sbb     ecx, ecx
0x18000fa90  and     ecx, 0FFFFFFFCh
0x18000fa93  add     ecx, 6
0x18000fa96  jmp     short loc_18000FAB8
0x18000fa98  mov     eax, ebx
0x18000fa9a  neg     eax
0x18000fa9c  sbb     ecx, ecx
0x18000fa9e  and     ecx, 0FFFFFFFCh
0x18000faa1  add     ecx, 5
0x18000faa4  jmp     short loc_18000FAB8
0x18000faa6  mov     eax, ebx
0x18000faa8  neg     eax
0x18000faaa  sbb     ecx, ecx
0x18000faac  not     ecx
0x18000faae  and     ecx, 4
0x18000fab1  jmp     short loc_18000FAB8
0x18000fab3  mov     ecx, 0FFh
0x18000fab8  mov     rdi, [rsp+78h+arg_20]
0x18000fac0  mov     al, [rdi+4]
0x18000fac3  mov     byte ptr [rsp+78h+var_40], al
0x18000fac7  mov     dword ptr [rsp+78h+var_58], ecx
0x18000facb  mov     rcx, rbp
0x18000face  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000fad3  test    eax, eax
0x18000fad5  jz      short loc_18000FB17
0x18000fad7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fade  test    rax, rax
0x18000fae1  jz      short loc_18000FB17
0x18000fae3  mov     [rsp+78h+var_40], 1
0x18000faec  lea     rcx, [rsp+78h+arg_30]
0x18000faf4  mov     [rsp+78h+var_48], 0
0x18000faf9  mov     r9d, ebx
0x18000fafc  mov     [rsp+78h+var_50], 0
0x18000fb05  xor     r8d, r8d
0x18000fb08  mov     [rsp+78h+var_58], rcx
0x18000fb0d  mov     rdx, rdi
0x18000fb10  mov     ecx, esi
0x18000fb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb17  add     rsp, 58h
0x18000fb1b  pop     rdi
0x18000fb1c  pop     rsi
0x18000fb1d  pop     rbp
0x18000fb1e  pop     rbx
0x18000fb1f  retn
```
