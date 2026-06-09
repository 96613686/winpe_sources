# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000bad8`
- end: `0x18000bc08`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800083d0`
- `0x18000e904`
- `0x18000e9a0`

## callees

- `0x18000bad8`
- `0x18000bc10`
- `0x180012010`

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
0x18000bad8  mov     rax, rsp
0x18000badb  push    rbx
0x18000badc  push    rbp
0x18000badd  push    rsi
0x18000bade  push    rdi
0x18000badf  sub     rsp, 58h
0x18000bae3  mov     r11d, [rax+38h]
0x18000bae7  mov     esi, edx
0x18000bae9  mov     rbp, rcx
0x18000baec  test    r11d, r11d
0x18000baef  jz      loc_18000BBFF
0x18000baf5  mov     ebx, [rsp+78h+arg_28]
0x18000bafc  mov     r10d, r11d
0x18000baff  sub     r10d, 1
0x18000bb03  jz      loc_18000BB8E
0x18000bb09  sub     r10d, 1
0x18000bb0d  jz      short loc_18000BB80
0x18000bb0f  sub     r10d, 1
0x18000bb13  jz      short loc_18000BB72
0x18000bb15  sub     r10d, 1
0x18000bb19  jz      short loc_18000BB64
0x18000bb1b  sub     r10d, 1
0x18000bb1f  jz      short loc_18000BB56
0x18000bb21  cmp     r10d, 1
0x18000bb25  jz      short loc_18000BB48
0x18000bb27  sub     r11b, 64h ; 'd'
0x18000bb2b  cmp     r11b, 31h ; '1'
0x18000bb2f  ja      short loc_18000BB9B
0x18000bb31  mov     eax, ebx
0x18000bb33  neg     eax
0x18000bb35  movzx   eax, r11b
0x18000bb39  sbb     ecx, ecx
0x18000bb3b  and     ecx, 0FFFFFFCEh
0x18000bb3e  add     ecx, 96h
0x18000bb44  add     ecx, eax
0x18000bb46  jmp     short loc_18000BBA0
0x18000bb48  mov     eax, ebx
0x18000bb4a  neg     eax
0x18000bb4c  sbb     ecx, ecx
0x18000bb4e  and     ecx, 0FFFFFFFEh
0x18000bb51  add     ecx, 0Bh
0x18000bb54  jmp     short loc_18000BBA0
0x18000bb56  mov     eax, ebx
0x18000bb58  neg     eax
0x18000bb5a  sbb     ecx, ecx
0x18000bb5c  and     ecx, 0FFFFFFFEh
0x18000bb5f  add     ecx, 0Ah
0x18000bb62  jmp     short loc_18000BBA0
0x18000bb64  mov     eax, ebx
0x18000bb66  neg     eax
0x18000bb68  sbb     ecx, ecx
0x18000bb6a  and     ecx, 0FFFFFFFCh
0x18000bb6d  add     ecx, 7
0x18000bb70  jmp     short loc_18000BBA0
0x18000bb72  mov     eax, ebx
0x18000bb74  neg     eax
0x18000bb76  sbb     ecx, ecx
0x18000bb78  and     ecx, 0FFFFFFFCh
0x18000bb7b  add     ecx, 6
0x18000bb7e  jmp     short loc_18000BBA0
0x18000bb80  mov     eax, ebx
0x18000bb82  neg     eax
0x18000bb84  sbb     ecx, ecx
0x18000bb86  and     ecx, 0FFFFFFFCh
0x18000bb89  add     ecx, 5
0x18000bb8c  jmp     short loc_18000BBA0
0x18000bb8e  mov     eax, ebx
0x18000bb90  neg     eax
0x18000bb92  sbb     ecx, ecx
0x18000bb94  not     ecx
0x18000bb96  and     ecx, 4
0x18000bb99  jmp     short loc_18000BBA0
0x18000bb9b  mov     ecx, 0FFh
0x18000bba0  mov     rdi, [rsp+78h+arg_20]
0x18000bba8  mov     al, [rdi+4]
0x18000bbab  mov     byte ptr [rsp+78h+var_40], al
0x18000bbaf  mov     dword ptr [rsp+78h+var_58], ecx
0x18000bbb3  mov     rcx, rbp
0x18000bbb6  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000bbbb  test    eax, eax
0x18000bbbd  jz      short loc_18000BBFF
0x18000bbbf  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000bbc6  test    rax, rax
0x18000bbc9  jz      short loc_18000BBFF
0x18000bbcb  mov     [rsp+78h+var_40], 1
0x18000bbd4  lea     rcx, [rsp+78h+arg_30]
0x18000bbdc  mov     [rsp+78h+var_48], 0
0x18000bbe1  mov     r9d, ebx
0x18000bbe4  mov     [rsp+78h+var_50], 0
0x18000bbed  xor     r8d, r8d
0x18000bbf0  mov     [rsp+78h+var_58], rcx
0x18000bbf5  mov     rdx, rdi
0x18000bbf8  mov     ecx, esi
0x18000bbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbff  add     rsp, 58h
0x18000bc03  pop     rdi
0x18000bc04  pop     rsi
0x18000bc05  pop     rbp
0x18000bc06  pop     rbx
0x18000bc07  retn
```
