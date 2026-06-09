# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800162ec`
- end: `0x18001641c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180018044`
- `0x1800180e4`

## callees

- `0x1800162ec`
- `0x180016424`
- `0x18001e010`

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
0x1800162ec  mov     rax, rsp
0x1800162ef  push    rbx
0x1800162f0  push    rbp
0x1800162f1  push    rsi
0x1800162f2  push    rdi
0x1800162f3  sub     rsp, 58h
0x1800162f7  mov     r11d, [rax+38h]
0x1800162fb  mov     esi, edx
0x1800162fd  mov     rbp, rcx
0x180016300  test    r11d, r11d
0x180016303  jz      loc_180016413
0x180016309  mov     ebx, [rsp+78h+arg_28]
0x180016310  mov     r10d, r11d
0x180016313  sub     r10d, 1
0x180016317  jz      loc_1800163A2
0x18001631d  sub     r10d, 1
0x180016321  jz      short loc_180016394
0x180016323  sub     r10d, 1
0x180016327  jz      short loc_180016386
0x180016329  sub     r10d, 1
0x18001632d  jz      short loc_180016378
0x18001632f  sub     r10d, 1
0x180016333  jz      short loc_18001636A
0x180016335  cmp     r10d, 1
0x180016339  jz      short loc_18001635C
0x18001633b  sub     r11b, 64h ; 'd'
0x18001633f  cmp     r11b, 31h ; '1'
0x180016343  ja      short loc_1800163AF
0x180016345  mov     eax, ebx
0x180016347  neg     eax
0x180016349  movzx   eax, r11b
0x18001634d  sbb     ecx, ecx
0x18001634f  and     ecx, 0FFFFFFCEh
0x180016352  add     ecx, 96h
0x180016358  add     ecx, eax
0x18001635a  jmp     short loc_1800163B4
0x18001635c  mov     eax, ebx
0x18001635e  neg     eax
0x180016360  sbb     ecx, ecx
0x180016362  and     ecx, 0FFFFFFFEh
0x180016365  add     ecx, 0Bh
0x180016368  jmp     short loc_1800163B4
0x18001636a  mov     eax, ebx
0x18001636c  neg     eax
0x18001636e  sbb     ecx, ecx
0x180016370  and     ecx, 0FFFFFFFEh
0x180016373  add     ecx, 0Ah
0x180016376  jmp     short loc_1800163B4
0x180016378  mov     eax, ebx
0x18001637a  neg     eax
0x18001637c  sbb     ecx, ecx
0x18001637e  and     ecx, 0FFFFFFFCh
0x180016381  add     ecx, 7
0x180016384  jmp     short loc_1800163B4
0x180016386  mov     eax, ebx
0x180016388  neg     eax
0x18001638a  sbb     ecx, ecx
0x18001638c  and     ecx, 0FFFFFFFCh
0x18001638f  add     ecx, 6
0x180016392  jmp     short loc_1800163B4
0x180016394  mov     eax, ebx
0x180016396  neg     eax
0x180016398  sbb     ecx, ecx
0x18001639a  and     ecx, 0FFFFFFFCh
0x18001639d  add     ecx, 5
0x1800163a0  jmp     short loc_1800163B4
0x1800163a2  mov     eax, ebx
0x1800163a4  neg     eax
0x1800163a6  sbb     ecx, ecx
0x1800163a8  not     ecx
0x1800163aa  and     ecx, 4
0x1800163ad  jmp     short loc_1800163B4
0x1800163af  mov     ecx, 0FFh
0x1800163b4  mov     rdi, [rsp+78h+arg_20]
0x1800163bc  mov     al, [rdi+4]
0x1800163bf  mov     byte ptr [rsp+78h+var_40], al
0x1800163c3  mov     dword ptr [rsp+78h+var_58], ecx
0x1800163c7  mov     rcx, rbp
0x1800163ca  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800163cf  test    eax, eax
0x1800163d1  jz      short loc_180016413
0x1800163d3  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800163da  test    rax, rax
0x1800163dd  jz      short loc_180016413
0x1800163df  mov     [rsp+78h+var_40], 1
0x1800163e8  lea     rcx, [rsp+78h+arg_30]
0x1800163f0  mov     byte ptr [rsp+78h+var_48], 0
0x1800163f5  mov     r9d, ebx
0x1800163f8  mov     [rsp+78h+var_50], 0
0x180016401  xor     r8d, r8d
0x180016404  mov     [rsp+78h+var_58], rcx
0x180016409  mov     rdx, rdi
0x18001640c  mov     ecx, esi
0x18001640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016413  add     rsp, 58h
0x180016417  pop     rdi
0x180016418  pop     rsi
0x180016419  pop     rbp
0x18001641a  pop     rbx
0x18001641b  retn
```
