# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001d680`
- end: `0x18001d7c3`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `323`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001dac0`
- `0x18001db60`
- `0x18001dc00`

## callees

- `0x18001d680`
- `0x18001d7cc`
- `0x18002c010`

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
  char v9; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

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
0x18001d680  mov     rax, rsp
0x18001d683  mov     [rax+8], rbx
0x18001d687  mov     [rax+10h], rbp
0x18001d68b  mov     [rax+18h], rsi
0x18001d68f  push    rdi
0x18001d690  sub     rsp, 50h
0x18001d694  mov     r11d, [rax+38h]
0x18001d698  mov     esi, edx
0x18001d69a  mov     rbp, rcx
0x18001d69d  test    r11d, r11d
0x18001d6a0  jz      loc_18001D7AD
0x18001d6a6  mov     ebx, [rsp+58h+arg_28]
0x18001d6ad  mov     r10d, r11d
0x18001d6b0  sub     r10d, 1
0x18001d6b4  jz      loc_18001D73F
0x18001d6ba  sub     r10d, 1
0x18001d6be  jz      short loc_18001D731
0x18001d6c0  sub     r10d, 1
0x18001d6c4  jz      short loc_18001D723
0x18001d6c6  sub     r10d, 1
0x18001d6ca  jz      short loc_18001D715
0x18001d6cc  sub     r10d, 1
0x18001d6d0  jz      short loc_18001D707
0x18001d6d2  cmp     r10d, 1
0x18001d6d6  jz      short loc_18001D6F9
0x18001d6d8  sub     r11b, 64h ; 'd'
0x18001d6dc  cmp     r11b, 31h ; '1'
0x18001d6e0  ja      short loc_18001D74C
0x18001d6e2  mov     eax, ebx
0x18001d6e4  neg     eax
0x18001d6e6  movzx   eax, r11b
0x18001d6ea  sbb     ecx, ecx
0x18001d6ec  and     ecx, 0FFFFFFCEh
0x18001d6ef  add     ecx, 96h
0x18001d6f5  add     ecx, eax
0x18001d6f7  jmp     short loc_18001D751
0x18001d6f9  mov     eax, ebx
0x18001d6fb  neg     eax
0x18001d6fd  sbb     ecx, ecx
0x18001d6ff  and     ecx, 0FFFFFFFEh
0x18001d702  add     ecx, 0Bh
0x18001d705  jmp     short loc_18001D751
0x18001d707  mov     eax, ebx
0x18001d709  neg     eax
0x18001d70b  sbb     ecx, ecx
0x18001d70d  and     ecx, 0FFFFFFFEh
0x18001d710  add     ecx, 0Ah
0x18001d713  jmp     short loc_18001D751
0x18001d715  mov     eax, ebx
0x18001d717  neg     eax
0x18001d719  sbb     ecx, ecx
0x18001d71b  and     ecx, 0FFFFFFFCh
0x18001d71e  add     ecx, 7
0x18001d721  jmp     short loc_18001D751
0x18001d723  mov     eax, ebx
0x18001d725  neg     eax
0x18001d727  sbb     ecx, ecx
0x18001d729  and     ecx, 0FFFFFFFCh
0x18001d72c  add     ecx, 6
0x18001d72f  jmp     short loc_18001D751
0x18001d731  mov     eax, ebx
0x18001d733  neg     eax
0x18001d735  sbb     ecx, ecx
0x18001d737  and     ecx, 0FFFFFFFCh
0x18001d73a  add     ecx, 5
0x18001d73d  jmp     short loc_18001D751
0x18001d73f  mov     eax, ebx
0x18001d741  neg     eax
0x18001d743  sbb     ecx, ecx
0x18001d745  not     ecx
0x18001d747  and     ecx, 4
0x18001d74a  jmp     short loc_18001D751
0x18001d74c  mov     ecx, 0FFh
0x18001d751  mov     rdi, [rsp+58h+arg_20]
0x18001d759  mov     al, [rdi+4]
0x18001d75c  mov     byte ptr [rsp+58h+var_20], al
0x18001d760  mov     dword ptr [rsp+58h+var_38], ecx
0x18001d764  mov     rcx, rbp
0x18001d767  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001d76c  test    eax, eax
0x18001d76e  jz      short loc_18001D7AD
0x18001d770  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001d777  test    rax, rax
0x18001d77a  jz      short loc_18001D7AD
0x18001d77c  mov     [rsp+58h+var_20], 1
0x18001d785  lea     rcx, [rsp+58h+arg_30]
0x18001d78d  mov     [rsp+58h+var_28], 0
0x18001d792  mov     r9d, ebx
0x18001d795  and     [rsp+58h+var_30], 0
0x18001d79b  xor     r8d, r8d
0x18001d79e  mov     [rsp+58h+var_38], rcx
0x18001d7a3  mov     rdx, rdi
0x18001d7a6  mov     ecx, esi
0x18001d7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ad  mov     rbx, [rsp+58h+arg_0]
0x18001d7b2  mov     rbp, [rsp+58h+arg_8]
0x18001d7b7  mov     rsi, [rsp+58h+arg_10]
0x18001d7bc  add     rsp, 50h
0x18001d7c0  pop     rdi
0x18001d7c1  retn
```
