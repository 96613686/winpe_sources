# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001553c`
- end: `0x18001566c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180012cc0`
- `0x180016224`

## callees

- `0x18001553c`
- `0x180015674`
- `0x18001b010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        struct wil_details_FeatureReportingCache *a1,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  unsigned int v10; // ecx
  __int64 v11; // [rsp+28h] [rbp-50h]
  __int64 v12; // [rsp+30h] [rbp-48h]
  int v13; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v10 = a6 == 0 ? 4 : 0;
        break;
      case 2:
        v10 = a6 != 0 ? 1 : 5;
        break;
      case 3:
        v10 = a6 != 0 ? 2 : 6;
        break;
      case 4:
        v10 = a6 != 0 ? 3 : 7;
        break;
      case 5:
        v10 = a6 != 0 ? 8 : 10;
        break;
      case 6:
        v10 = a6 != 0 ? 9 : 11;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
          v10 = 255;
        else
          v10 = (unsigned __int8)(a7 - 100) + (a6 != 0 ? 100 : 150);
        break;
    }
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2, a3, a4, v10, v11, v12, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v13) = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v13, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001553c  mov     rax, rsp
0x18001553f  push    rbx
0x180015540  push    rbp
0x180015541  push    rsi
0x180015542  push    rdi
0x180015543  sub     rsp, 58h
0x180015547  mov     r11d, [rax+38h]
0x18001554b  mov     esi, edx
0x18001554d  mov     rbp, rcx
0x180015550  test    r11d, r11d
0x180015553  jz      loc_180015663
0x180015559  mov     ebx, [rsp+78h+arg_28]
0x180015560  mov     r10d, r11d
0x180015563  sub     r10d, 1
0x180015567  jz      loc_1800155F2
0x18001556d  sub     r10d, 1
0x180015571  jz      short loc_1800155E4
0x180015573  sub     r10d, 1
0x180015577  jz      short loc_1800155D6
0x180015579  sub     r10d, 1
0x18001557d  jz      short loc_1800155C8
0x18001557f  sub     r10d, 1
0x180015583  jz      short loc_1800155BA
0x180015585  cmp     r10d, 1
0x180015589  jz      short loc_1800155AC
0x18001558b  sub     r11b, 64h ; 'd'
0x18001558f  cmp     r11b, 31h ; '1'
0x180015593  ja      short loc_1800155FF
0x180015595  mov     eax, ebx
0x180015597  neg     eax
0x180015599  movzx   eax, r11b
0x18001559d  sbb     ecx, ecx
0x18001559f  and     ecx, 0FFFFFFCEh
0x1800155a2  add     ecx, 96h
0x1800155a8  add     ecx, eax
0x1800155aa  jmp     short loc_180015604
0x1800155ac  mov     eax, ebx
0x1800155ae  neg     eax
0x1800155b0  sbb     ecx, ecx
0x1800155b2  and     ecx, 0FFFFFFFEh
0x1800155b5  add     ecx, 0Bh
0x1800155b8  jmp     short loc_180015604
0x1800155ba  mov     eax, ebx
0x1800155bc  neg     eax
0x1800155be  sbb     ecx, ecx
0x1800155c0  and     ecx, 0FFFFFFFEh
0x1800155c3  add     ecx, 0Ah
0x1800155c6  jmp     short loc_180015604
0x1800155c8  mov     eax, ebx
0x1800155ca  neg     eax
0x1800155cc  sbb     ecx, ecx
0x1800155ce  and     ecx, 0FFFFFFFCh
0x1800155d1  add     ecx, 7
0x1800155d4  jmp     short loc_180015604
0x1800155d6  mov     eax, ebx
0x1800155d8  neg     eax
0x1800155da  sbb     ecx, ecx
0x1800155dc  and     ecx, 0FFFFFFFCh
0x1800155df  add     ecx, 6
0x1800155e2  jmp     short loc_180015604
0x1800155e4  mov     eax, ebx
0x1800155e6  neg     eax
0x1800155e8  sbb     ecx, ecx
0x1800155ea  and     ecx, 0FFFFFFFCh
0x1800155ed  add     ecx, 5
0x1800155f0  jmp     short loc_180015604
0x1800155f2  mov     eax, ebx
0x1800155f4  neg     eax
0x1800155f6  sbb     ecx, ecx
0x1800155f8  not     ecx
0x1800155fa  and     ecx, 4
0x1800155fd  jmp     short loc_180015604
0x1800155ff  mov     ecx, 0FFh
0x180015604  mov     rdi, [rsp+78h+arg_20]
0x18001560c  mov     al, [rdi+4]
0x18001560f  mov     byte ptr [rsp+78h+var_40], al
0x180015613  mov     dword ptr [rsp+78h+var_58], ecx
0x180015617  mov     rcx, rbp
0x18001561a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001561f  test    eax, eax
0x180015621  jz      short loc_180015663
0x180015623  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001562a  test    rax, rax
0x18001562d  jz      short loc_180015663
0x18001562f  mov     [rsp+78h+var_40], 1
0x180015638  lea     rcx, [rsp+78h+arg_30]
0x180015640  mov     byte ptr [rsp+78h+var_48], 0
0x180015645  mov     r9d, ebx
0x180015648  mov     [rsp+78h+var_50], 0
0x180015651  xor     r8d, r8d
0x180015654  mov     [rsp+78h+var_58], rcx
0x180015659  mov     rdx, rdi
0x18001565c  mov     ecx, esi
0x18001565e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015663  add     rsp, 58h
0x180015667  pop     rdi
0x180015668  pop     rsi
0x180015669  pop     rbp
0x18001566a  pop     rbx
0x18001566b  retn
```
