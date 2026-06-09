# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180014da0`
- end: `0x180014ed0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014af4`
- `0x180014d14`

## callees

- `0x180014da0`
- `0x180014ed8`
- `0x180016010`

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
0x180014da0  mov     rax, rsp
0x180014da3  push    rbx
0x180014da4  push    rbp
0x180014da5  push    rsi
0x180014da6  push    rdi
0x180014da7  sub     rsp, 58h
0x180014dab  mov     r11d, [rax+38h]
0x180014daf  mov     esi, edx
0x180014db1  mov     rbp, rcx
0x180014db4  test    r11d, r11d
0x180014db7  jz      loc_180014EC7
0x180014dbd  mov     ebx, [rsp+78h+arg_28]
0x180014dc4  mov     r10d, r11d
0x180014dc7  sub     r10d, 1
0x180014dcb  jz      loc_180014E56
0x180014dd1  sub     r10d, 1
0x180014dd5  jz      short loc_180014E48
0x180014dd7  sub     r10d, 1
0x180014ddb  jz      short loc_180014E3A
0x180014ddd  sub     r10d, 1
0x180014de1  jz      short loc_180014E2C
0x180014de3  sub     r10d, 1
0x180014de7  jz      short loc_180014E1E
0x180014de9  cmp     r10d, 1
0x180014ded  jz      short loc_180014E10
0x180014def  sub     r11b, 64h ; 'd'
0x180014df3  cmp     r11b, 31h ; '1'
0x180014df7  ja      short loc_180014E63
0x180014df9  mov     eax, ebx
0x180014dfb  neg     eax
0x180014dfd  movzx   eax, r11b
0x180014e01  sbb     ecx, ecx
0x180014e03  and     ecx, 0FFFFFFCEh
0x180014e06  add     ecx, 96h
0x180014e0c  add     ecx, eax
0x180014e0e  jmp     short loc_180014E68
0x180014e10  mov     eax, ebx
0x180014e12  neg     eax
0x180014e14  sbb     ecx, ecx
0x180014e16  and     ecx, 0FFFFFFFEh
0x180014e19  add     ecx, 0Bh
0x180014e1c  jmp     short loc_180014E68
0x180014e1e  mov     eax, ebx
0x180014e20  neg     eax
0x180014e22  sbb     ecx, ecx
0x180014e24  and     ecx, 0FFFFFFFEh
0x180014e27  add     ecx, 0Ah
0x180014e2a  jmp     short loc_180014E68
0x180014e2c  mov     eax, ebx
0x180014e2e  neg     eax
0x180014e30  sbb     ecx, ecx
0x180014e32  and     ecx, 0FFFFFFFCh
0x180014e35  add     ecx, 7
0x180014e38  jmp     short loc_180014E68
0x180014e3a  mov     eax, ebx
0x180014e3c  neg     eax
0x180014e3e  sbb     ecx, ecx
0x180014e40  and     ecx, 0FFFFFFFCh
0x180014e43  add     ecx, 6
0x180014e46  jmp     short loc_180014E68
0x180014e48  mov     eax, ebx
0x180014e4a  neg     eax
0x180014e4c  sbb     ecx, ecx
0x180014e4e  and     ecx, 0FFFFFFFCh
0x180014e51  add     ecx, 5
0x180014e54  jmp     short loc_180014E68
0x180014e56  mov     eax, ebx
0x180014e58  neg     eax
0x180014e5a  sbb     ecx, ecx
0x180014e5c  not     ecx
0x180014e5e  and     ecx, 4
0x180014e61  jmp     short loc_180014E68
0x180014e63  mov     ecx, 0FFh
0x180014e68  mov     rdi, [rsp+78h+arg_20]
0x180014e70  mov     al, [rdi+4]
0x180014e73  mov     byte ptr [rsp+78h+var_40], al
0x180014e77  mov     dword ptr [rsp+78h+var_58], ecx
0x180014e7b  mov     rcx, rbp
0x180014e7e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180014e83  test    eax, eax
0x180014e85  jz      short loc_180014EC7
0x180014e87  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180014e8e  test    rax, rax
0x180014e91  jz      short loc_180014EC7
0x180014e93  mov     [rsp+78h+var_40], 1
0x180014e9c  lea     rcx, [rsp+78h+arg_30]
0x180014ea4  mov     byte ptr [rsp+78h+var_48], 0
0x180014ea9  mov     r9d, ebx
0x180014eac  mov     [rsp+78h+var_50], 0
0x180014eb5  xor     r8d, r8d
0x180014eb8  mov     [rsp+78h+var_58], rcx
0x180014ebd  mov     rdx, rdi
0x180014ec0  mov     ecx, esi
0x180014ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ec7  add     rsp, 58h
0x180014ecb  pop     rdi
0x180014ecc  pop     rsi
0x180014ecd  pop     rbp
0x180014ece  pop     rbx
0x180014ecf  retn
```
