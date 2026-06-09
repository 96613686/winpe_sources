# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180008650`
- end: `0x18000877e`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `302`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005430`
- `0x1800085a8`

## callees

- `0x180008650`
- `0x180008784`
- `0x18000d010`

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
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2);
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
0x180008650  mov     rax, rsp
0x180008653  mov     [rax+18h], rbx
0x180008657  mov     [rax+20h], rsi
0x18000865b  push    rdi
0x18000865c  sub     rsp, 50h
0x180008660  mov     rsi, [rsp+58h+arg_20]
0x180008668  mov     edi, edx
0x18000866a  mov     edx, [rax+38h]
0x18000866d  mov     r10, rcx
0x180008670  test    edx, edx
0x180008672  jz      loc_18000876E
0x180008678  mov     ebx, [rsp+58h+arg_28]
0x18000867f  mov     ecx, edx
0x180008681  sub     ecx, 1
0x180008684  jz      short loc_180008703
0x180008686  sub     ecx, 1
0x180008689  jz      short loc_1800086F5
0x18000868b  sub     ecx, 1
0x18000868e  jz      short loc_1800086E7
0x180008690  sub     ecx, 1
0x180008693  jz      short loc_1800086D9
0x180008695  sub     ecx, 1
0x180008698  jz      short loc_1800086CB
0x18000869a  cmp     ecx, 1
0x18000869d  jz      short loc_1800086BD
0x18000869f  sub     dl, 64h ; 'd'
0x1800086a2  cmp     dl, 31h ; '1'
0x1800086a5  ja      short loc_180008710
0x1800086a7  mov     eax, ebx
0x1800086a9  neg     eax
0x1800086ab  movzx   eax, dl
0x1800086ae  sbb     ecx, ecx
0x1800086b0  and     ecx, 0FFFFFFCEh
0x1800086b3  add     ecx, 96h
0x1800086b9  add     ecx, eax
0x1800086bb  jmp     short loc_180008715
0x1800086bd  mov     eax, ebx
0x1800086bf  neg     eax
0x1800086c1  sbb     ecx, ecx
0x1800086c3  and     ecx, 0FFFFFFFEh
0x1800086c6  add     ecx, 0Bh
0x1800086c9  jmp     short loc_180008715
0x1800086cb  mov     eax, ebx
0x1800086cd  neg     eax
0x1800086cf  sbb     ecx, ecx
0x1800086d1  and     ecx, 0FFFFFFFEh
0x1800086d4  add     ecx, 0Ah
0x1800086d7  jmp     short loc_180008715
0x1800086d9  mov     eax, ebx
0x1800086db  neg     eax
0x1800086dd  sbb     ecx, ecx
0x1800086df  and     ecx, 0FFFFFFFCh
0x1800086e2  add     ecx, 7
0x1800086e5  jmp     short loc_180008715
0x1800086e7  mov     eax, ebx
0x1800086e9  neg     eax
0x1800086eb  sbb     ecx, ecx
0x1800086ed  and     ecx, 0FFFFFFFCh
0x1800086f0  add     ecx, 6
0x1800086f3  jmp     short loc_180008715
0x1800086f5  mov     eax, ebx
0x1800086f7  neg     eax
0x1800086f9  sbb     ecx, ecx
0x1800086fb  and     ecx, 0FFFFFFFCh
0x1800086fe  add     ecx, 5
0x180008701  jmp     short loc_180008715
0x180008703  mov     eax, ebx
0x180008705  neg     eax
0x180008707  sbb     ecx, ecx
0x180008709  not     ecx
0x18000870b  and     ecx, 4
0x18000870e  jmp     short loc_180008715
0x180008710  mov     ecx, 0FFh
0x180008715  mov     al, [rsi+4]
0x180008718  mov     edx, edi
0x18000871a  mov     byte ptr [rsp+58h+var_20], al
0x18000871e  mov     dword ptr [rsp+58h+var_38], ecx
0x180008722  mov     rcx, r10
0x180008725  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000872a  test    eax, eax
0x18000872c  jz      short loc_18000876E
0x18000872e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180008735  test    rax, rax
0x180008738  jz      short loc_18000876E
0x18000873a  mov     [rsp+58h+var_20], 1
0x180008743  lea     rcx, [rsp+58h+arg_30]
0x18000874b  mov     [rsp+58h+var_28], 0
0x180008750  mov     r9d, ebx
0x180008753  mov     [rsp+58h+var_30], 0
0x18000875c  xor     r8d, r8d
0x18000875f  mov     [rsp+58h+var_38], rcx
0x180008764  mov     rdx, rsi
0x180008767  mov     ecx, edi
0x180008769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000876e  mov     rbx, [rsp+58h+arg_10]
0x180008773  mov     rsi, [rsp+58h+arg_18]
0x180008778  add     rsp, 50h
0x18000877c  pop     rdi
0x18000877d  retn
```
