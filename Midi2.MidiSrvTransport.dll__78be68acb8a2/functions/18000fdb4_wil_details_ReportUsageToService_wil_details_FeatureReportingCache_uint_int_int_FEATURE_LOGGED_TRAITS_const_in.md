# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000fdb4`
- end: `0x18000fee4`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000eb34`
- `0x18000eca4`
- `0x18000ee14`
- `0x18000ef84`
- `0x1800111e4`
- `0x180011280`
- `0x18001131c`
- `0x1800113bc`
- `0x180011458`
- `0x1800114f4`
- `0x180011590`

## callees

- `0x18000fdb4`
- `0x18000feec`
- `0x180015010`

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
0x18000fdb4  mov     rax, rsp
0x18000fdb7  push    rbx
0x18000fdb8  push    rbp
0x18000fdb9  push    rsi
0x18000fdba  push    rdi
0x18000fdbb  sub     rsp, 58h
0x18000fdbf  mov     r11d, [rax+38h]
0x18000fdc3  mov     esi, edx
0x18000fdc5  mov     rbp, rcx
0x18000fdc8  test    r11d, r11d
0x18000fdcb  jz      loc_18000FEDB
0x18000fdd1  mov     ebx, [rsp+78h+arg_28]
0x18000fdd8  mov     r10d, r11d
0x18000fddb  sub     r10d, 1
0x18000fddf  jz      loc_18000FE6A
0x18000fde5  sub     r10d, 1
0x18000fde9  jz      short loc_18000FE5C
0x18000fdeb  sub     r10d, 1
0x18000fdef  jz      short loc_18000FE4E
0x18000fdf1  sub     r10d, 1
0x18000fdf5  jz      short loc_18000FE40
0x18000fdf7  sub     r10d, 1
0x18000fdfb  jz      short loc_18000FE32
0x18000fdfd  cmp     r10d, 1
0x18000fe01  jz      short loc_18000FE24
0x18000fe03  sub     r11b, 64h ; 'd'
0x18000fe07  cmp     r11b, 31h ; '1'
0x18000fe0b  ja      short loc_18000FE77
0x18000fe0d  mov     eax, ebx
0x18000fe0f  neg     eax
0x18000fe11  movzx   eax, r11b
0x18000fe15  sbb     ecx, ecx
0x18000fe17  and     ecx, 0FFFFFFCEh
0x18000fe1a  add     ecx, 96h
0x18000fe20  add     ecx, eax
0x18000fe22  jmp     short loc_18000FE7C
0x18000fe24  mov     eax, ebx
0x18000fe26  neg     eax
0x18000fe28  sbb     ecx, ecx
0x18000fe2a  and     ecx, 0FFFFFFFEh
0x18000fe2d  add     ecx, 0Bh
0x18000fe30  jmp     short loc_18000FE7C
0x18000fe32  mov     eax, ebx
0x18000fe34  neg     eax
0x18000fe36  sbb     ecx, ecx
0x18000fe38  and     ecx, 0FFFFFFFEh
0x18000fe3b  add     ecx, 0Ah
0x18000fe3e  jmp     short loc_18000FE7C
0x18000fe40  mov     eax, ebx
0x18000fe42  neg     eax
0x18000fe44  sbb     ecx, ecx
0x18000fe46  and     ecx, 0FFFFFFFCh
0x18000fe49  add     ecx, 7
0x18000fe4c  jmp     short loc_18000FE7C
0x18000fe4e  mov     eax, ebx
0x18000fe50  neg     eax
0x18000fe52  sbb     ecx, ecx
0x18000fe54  and     ecx, 0FFFFFFFCh
0x18000fe57  add     ecx, 6
0x18000fe5a  jmp     short loc_18000FE7C
0x18000fe5c  mov     eax, ebx
0x18000fe5e  neg     eax
0x18000fe60  sbb     ecx, ecx
0x18000fe62  and     ecx, 0FFFFFFFCh
0x18000fe65  add     ecx, 5
0x18000fe68  jmp     short loc_18000FE7C
0x18000fe6a  mov     eax, ebx
0x18000fe6c  neg     eax
0x18000fe6e  sbb     ecx, ecx
0x18000fe70  not     ecx
0x18000fe72  and     ecx, 4
0x18000fe75  jmp     short loc_18000FE7C
0x18000fe77  mov     ecx, 0FFh
0x18000fe7c  mov     rdi, [rsp+78h+arg_20]
0x18000fe84  mov     al, [rdi+4]
0x18000fe87  mov     byte ptr [rsp+78h+var_40], al
0x18000fe8b  mov     dword ptr [rsp+78h+var_58], ecx
0x18000fe8f  mov     rcx, rbp
0x18000fe92  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000fe97  test    eax, eax
0x18000fe99  jz      short loc_18000FEDB
0x18000fe9b  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fea2  test    rax, rax
0x18000fea5  jz      short loc_18000FEDB
0x18000fea7  mov     [rsp+78h+var_40], 1
0x18000feb0  lea     rcx, [rsp+78h+arg_30]
0x18000feb8  mov     [rsp+78h+var_48], 0
0x18000febd  mov     r9d, ebx
0x18000fec0  mov     [rsp+78h+var_50], 0
0x18000fec9  xor     r8d, r8d
0x18000fecc  mov     [rsp+78h+var_58], rcx
0x18000fed1  mov     rdx, rdi
0x18000fed4  mov     ecx, esi
0x18000fed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fedb  add     rsp, 58h
0x18000fedf  pop     rdi
0x18000fee0  pop     rsi
0x18000fee1  pop     rbp
0x18000fee2  pop     rbx
0x18000fee3  retn
```
