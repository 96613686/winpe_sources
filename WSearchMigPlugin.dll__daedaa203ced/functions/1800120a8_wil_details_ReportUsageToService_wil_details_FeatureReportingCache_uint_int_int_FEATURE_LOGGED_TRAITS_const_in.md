# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800120a8`
- end: `0x1800121d8`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000f144`
- `0x18000f2b4`
- `0x18000f424`
- `0x18000f594`
- `0x18000f704`
- `0x180013cd4`
- `0x180013d74`
- `0x180013e10`
- `0x180013eac`
- `0x180013f48`
- `0x180013fe4`

## callees

- `0x1800120a8`
- `0x1800121e0`
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
0x1800120a8  mov     rax, rsp
0x1800120ab  push    rbx
0x1800120ac  push    rbp
0x1800120ad  push    rsi
0x1800120ae  push    rdi
0x1800120af  sub     rsp, 58h
0x1800120b3  mov     r11d, [rax+38h]
0x1800120b7  mov     esi, edx
0x1800120b9  mov     rbp, rcx
0x1800120bc  test    r11d, r11d
0x1800120bf  jz      loc_1800121CF
0x1800120c5  mov     ebx, [rsp+78h+arg_28]
0x1800120cc  mov     r10d, r11d
0x1800120cf  sub     r10d, 1
0x1800120d3  jz      loc_18001215E
0x1800120d9  sub     r10d, 1
0x1800120dd  jz      short loc_180012150
0x1800120df  sub     r10d, 1
0x1800120e3  jz      short loc_180012142
0x1800120e5  sub     r10d, 1
0x1800120e9  jz      short loc_180012134
0x1800120eb  sub     r10d, 1
0x1800120ef  jz      short loc_180012126
0x1800120f1  cmp     r10d, 1
0x1800120f5  jz      short loc_180012118
0x1800120f7  sub     r11b, 64h ; 'd'
0x1800120fb  cmp     r11b, 31h ; '1'
0x1800120ff  ja      short loc_18001216B
0x180012101  mov     eax, ebx
0x180012103  neg     eax
0x180012105  movzx   eax, r11b
0x180012109  sbb     ecx, ecx
0x18001210b  and     ecx, 0FFFFFFCEh
0x18001210e  add     ecx, 96h
0x180012114  add     ecx, eax
0x180012116  jmp     short loc_180012170
0x180012118  mov     eax, ebx
0x18001211a  neg     eax
0x18001211c  sbb     ecx, ecx
0x18001211e  and     ecx, 0FFFFFFFEh
0x180012121  add     ecx, 0Bh
0x180012124  jmp     short loc_180012170
0x180012126  mov     eax, ebx
0x180012128  neg     eax
0x18001212a  sbb     ecx, ecx
0x18001212c  and     ecx, 0FFFFFFFEh
0x18001212f  add     ecx, 0Ah
0x180012132  jmp     short loc_180012170
0x180012134  mov     eax, ebx
0x180012136  neg     eax
0x180012138  sbb     ecx, ecx
0x18001213a  and     ecx, 0FFFFFFFCh
0x18001213d  add     ecx, 7
0x180012140  jmp     short loc_180012170
0x180012142  mov     eax, ebx
0x180012144  neg     eax
0x180012146  sbb     ecx, ecx
0x180012148  and     ecx, 0FFFFFFFCh
0x18001214b  add     ecx, 6
0x18001214e  jmp     short loc_180012170
0x180012150  mov     eax, ebx
0x180012152  neg     eax
0x180012154  sbb     ecx, ecx
0x180012156  and     ecx, 0FFFFFFFCh
0x180012159  add     ecx, 5
0x18001215c  jmp     short loc_180012170
0x18001215e  mov     eax, ebx
0x180012160  neg     eax
0x180012162  sbb     ecx, ecx
0x180012164  not     ecx
0x180012166  and     ecx, 4
0x180012169  jmp     short loc_180012170
0x18001216b  mov     ecx, 0FFh
0x180012170  mov     rdi, [rsp+78h+arg_20]
0x180012178  mov     al, [rdi+4]
0x18001217b  mov     byte ptr [rsp+78h+var_40], al
0x18001217f  mov     dword ptr [rsp+78h+var_58], ecx
0x180012183  mov     rcx, rbp
0x180012186  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001218b  test    eax, eax
0x18001218d  jz      short loc_1800121CF
0x18001218f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180012196  test    rax, rax
0x180012199  jz      short loc_1800121CF
0x18001219b  mov     [rsp+78h+var_40], 1
0x1800121a4  lea     rcx, [rsp+78h+arg_30]
0x1800121ac  mov     [rsp+78h+var_48], 0
0x1800121b1  mov     r9d, ebx
0x1800121b4  mov     [rsp+78h+var_50], 0
0x1800121bd  xor     r8d, r8d
0x1800121c0  mov     [rsp+78h+var_58], rcx
0x1800121c5  mov     rdx, rdi
0x1800121c8  mov     ecx, esi
0x1800121ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121cf  add     rsp, 58h
0x1800121d3  pop     rdi
0x1800121d4  pop     rsi
0x1800121d5  pop     rbp
0x1800121d6  pop     rbx
0x1800121d7  retn
```
