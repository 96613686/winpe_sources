# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000dc68`
- end: `0x18000dd98`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008b40`
- `0x180008c88`
- `0x180008dd0`
- `0x180008f18`
- `0x180009060`
- `0x1800091a8`
- `0x1800092f0`
- `0x180011704`
- `0x1800117a0`
- `0x180011840`
- `0x1800118e0`
- `0x180011980`
- `0x180011a20`
- `0x180011ac0`

## callees

- `0x18000dc68`
- `0x18000dda0`
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
0x18000dc68  mov     rax, rsp
0x18000dc6b  push    rbx
0x18000dc6c  push    rbp
0x18000dc6d  push    rsi
0x18000dc6e  push    rdi
0x18000dc6f  sub     rsp, 58h
0x18000dc73  mov     r11d, [rax+38h]
0x18000dc77  mov     esi, edx
0x18000dc79  mov     rbp, rcx
0x18000dc7c  test    r11d, r11d
0x18000dc7f  jz      loc_18000DD8F
0x18000dc85  mov     ebx, [rsp+78h+arg_28]
0x18000dc8c  mov     r10d, r11d
0x18000dc8f  sub     r10d, 1
0x18000dc93  jz      loc_18000DD1E
0x18000dc99  sub     r10d, 1
0x18000dc9d  jz      short loc_18000DD10
0x18000dc9f  sub     r10d, 1
0x18000dca3  jz      short loc_18000DD02
0x18000dca5  sub     r10d, 1
0x18000dca9  jz      short loc_18000DCF4
0x18000dcab  sub     r10d, 1
0x18000dcaf  jz      short loc_18000DCE6
0x18000dcb1  cmp     r10d, 1
0x18000dcb5  jz      short loc_18000DCD8
0x18000dcb7  sub     r11b, 64h ; 'd'
0x18000dcbb  cmp     r11b, 31h ; '1'
0x18000dcbf  ja      short loc_18000DD2B
0x18000dcc1  mov     eax, ebx
0x18000dcc3  neg     eax
0x18000dcc5  movzx   eax, r11b
0x18000dcc9  sbb     ecx, ecx
0x18000dccb  and     ecx, 0FFFFFFCEh
0x18000dcce  add     ecx, 96h
0x18000dcd4  add     ecx, eax
0x18000dcd6  jmp     short loc_18000DD30
0x18000dcd8  mov     eax, ebx
0x18000dcda  neg     eax
0x18000dcdc  sbb     ecx, ecx
0x18000dcde  and     ecx, 0FFFFFFFEh
0x18000dce1  add     ecx, 0Bh
0x18000dce4  jmp     short loc_18000DD30
0x18000dce6  mov     eax, ebx
0x18000dce8  neg     eax
0x18000dcea  sbb     ecx, ecx
0x18000dcec  and     ecx, 0FFFFFFFEh
0x18000dcef  add     ecx, 0Ah
0x18000dcf2  jmp     short loc_18000DD30
0x18000dcf4  mov     eax, ebx
0x18000dcf6  neg     eax
0x18000dcf8  sbb     ecx, ecx
0x18000dcfa  and     ecx, 0FFFFFFFCh
0x18000dcfd  add     ecx, 7
0x18000dd00  jmp     short loc_18000DD30
0x18000dd02  mov     eax, ebx
0x18000dd04  neg     eax
0x18000dd06  sbb     ecx, ecx
0x18000dd08  and     ecx, 0FFFFFFFCh
0x18000dd0b  add     ecx, 6
0x18000dd0e  jmp     short loc_18000DD30
0x18000dd10  mov     eax, ebx
0x18000dd12  neg     eax
0x18000dd14  sbb     ecx, ecx
0x18000dd16  and     ecx, 0FFFFFFFCh
0x18000dd19  add     ecx, 5
0x18000dd1c  jmp     short loc_18000DD30
0x18000dd1e  mov     eax, ebx
0x18000dd20  neg     eax
0x18000dd22  sbb     ecx, ecx
0x18000dd24  not     ecx
0x18000dd26  and     ecx, 4
0x18000dd29  jmp     short loc_18000DD30
0x18000dd2b  mov     ecx, 0FFh
0x18000dd30  mov     rdi, [rsp+78h+arg_20]
0x18000dd38  mov     al, [rdi+4]
0x18000dd3b  mov     byte ptr [rsp+78h+var_40], al
0x18000dd3f  mov     dword ptr [rsp+78h+var_58], ecx
0x18000dd43  mov     rcx, rbp
0x18000dd46  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000dd4b  test    eax, eax
0x18000dd4d  jz      short loc_18000DD8F
0x18000dd4f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000dd56  test    rax, rax
0x18000dd59  jz      short loc_18000DD8F
0x18000dd5b  mov     [rsp+78h+var_40], 1
0x18000dd64  lea     rcx, [rsp+78h+arg_30]
0x18000dd6c  mov     [rsp+78h+var_48], 0
0x18000dd71  mov     r9d, ebx
0x18000dd74  mov     [rsp+78h+var_50], 0
0x18000dd7d  xor     r8d, r8d
0x18000dd80  mov     [rsp+78h+var_58], rcx
0x18000dd85  mov     rdx, rdi
0x18000dd88  mov     ecx, esi
0x18000dd8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd8f  add     rsp, 58h
0x18000dd93  pop     rdi
0x18000dd94  pop     rsi
0x18000dd95  pop     rbp
0x18000dd96  pop     rbx
0x18000dd97  retn
```
