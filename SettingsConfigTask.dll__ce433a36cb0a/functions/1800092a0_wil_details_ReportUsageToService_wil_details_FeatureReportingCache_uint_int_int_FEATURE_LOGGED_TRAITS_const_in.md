# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800092a0`
- end: `0x1800093d0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `36`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180009100`
- `0x180009198`
- `0x18000921c`
- `0x18001a734`
- `0x18001a7bc`
- `0x18001a844`
- `0x18001a8cc`
- `0x18001a964`
- `0x18001a9e8`
- `0x18001aa74`
- `0x18001ab00`
- `0x18001ab8c`
- `0x18001ac18`
- `0x18001acb0`
- `0x18001ad3c`
- `0x18001adc8`
- `0x18001ae54`
- `0x18001aee0`
- `0x18001af6c`
- `0x18001aff8`
- `0x18001b084`
- `0x18001b110`
- `0x18001b198`
- `0x18001b21c`
- `0x18001b2a0`
- `0x18001b32c`
- `0x18001b3b0`
- `0x18001b434`
- `0x18001b4b8`
- `0x18001b53c`
- `0x18001b5c4`
- `0x18001b64c`
- `0x18001b6d4`
- `0x18001b760`
- `0x18001b7e4`
- `0x18001b86c`

## callees

- `0x1800092a0`
- `0x1800093d8`
- `0x180024010`

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
0x1800092a0  mov     rax, rsp
0x1800092a3  push    rbx
0x1800092a4  push    rbp
0x1800092a5  push    rsi
0x1800092a6  push    rdi
0x1800092a7  sub     rsp, 58h
0x1800092ab  mov     r11d, [rax+38h]
0x1800092af  mov     esi, edx
0x1800092b1  mov     rbp, rcx
0x1800092b4  test    r11d, r11d
0x1800092b7  jz      loc_1800093C7
0x1800092bd  mov     ebx, [rsp+78h+arg_28]
0x1800092c4  mov     r10d, r11d
0x1800092c7  sub     r10d, 1
0x1800092cb  jz      loc_180009356
0x1800092d1  sub     r10d, 1
0x1800092d5  jz      short loc_180009348
0x1800092d7  sub     r10d, 1
0x1800092db  jz      short loc_18000933A
0x1800092dd  sub     r10d, 1
0x1800092e1  jz      short loc_18000932C
0x1800092e3  sub     r10d, 1
0x1800092e7  jz      short loc_18000931E
0x1800092e9  cmp     r10d, 1
0x1800092ed  jz      short loc_180009310
0x1800092ef  sub     r11b, 64h ; 'd'
0x1800092f3  cmp     r11b, 31h ; '1'
0x1800092f7  ja      short loc_180009363
0x1800092f9  mov     eax, ebx
0x1800092fb  neg     eax
0x1800092fd  movzx   eax, r11b
0x180009301  sbb     ecx, ecx
0x180009303  and     ecx, 0FFFFFFCEh
0x180009306  add     ecx, 96h
0x18000930c  add     ecx, eax
0x18000930e  jmp     short loc_180009368
0x180009310  mov     eax, ebx
0x180009312  neg     eax
0x180009314  sbb     ecx, ecx
0x180009316  and     ecx, 0FFFFFFFEh
0x180009319  add     ecx, 0Bh
0x18000931c  jmp     short loc_180009368
0x18000931e  mov     eax, ebx
0x180009320  neg     eax
0x180009322  sbb     ecx, ecx
0x180009324  and     ecx, 0FFFFFFFEh
0x180009327  add     ecx, 0Ah
0x18000932a  jmp     short loc_180009368
0x18000932c  mov     eax, ebx
0x18000932e  neg     eax
0x180009330  sbb     ecx, ecx
0x180009332  and     ecx, 0FFFFFFFCh
0x180009335  add     ecx, 7
0x180009338  jmp     short loc_180009368
0x18000933a  mov     eax, ebx
0x18000933c  neg     eax
0x18000933e  sbb     ecx, ecx
0x180009340  and     ecx, 0FFFFFFFCh
0x180009343  add     ecx, 6
0x180009346  jmp     short loc_180009368
0x180009348  mov     eax, ebx
0x18000934a  neg     eax
0x18000934c  sbb     ecx, ecx
0x18000934e  and     ecx, 0FFFFFFFCh
0x180009351  add     ecx, 5
0x180009354  jmp     short loc_180009368
0x180009356  mov     eax, ebx
0x180009358  neg     eax
0x18000935a  sbb     ecx, ecx
0x18000935c  not     ecx
0x18000935e  and     ecx, 4
0x180009361  jmp     short loc_180009368
0x180009363  mov     ecx, 0FFh
0x180009368  mov     rdi, [rsp+78h+arg_20]
0x180009370  mov     al, [rdi+4]
0x180009373  mov     byte ptr [rsp+78h+var_40], al
0x180009377  mov     dword ptr [rsp+78h+var_58], ecx
0x18000937b  mov     rcx, rbp
0x18000937e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180009383  test    eax, eax
0x180009385  jz      short loc_1800093C7
0x180009387  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000938e  test    rax, rax
0x180009391  jz      short loc_1800093C7
0x180009393  mov     [rsp+78h+var_40], 1
0x18000939c  lea     rcx, [rsp+78h+arg_30]
0x1800093a4  mov     [rsp+78h+var_48], 0
0x1800093a9  mov     r9d, ebx
0x1800093ac  mov     [rsp+78h+var_50], 0
0x1800093b5  xor     r8d, r8d
0x1800093b8  mov     [rsp+78h+var_58], rcx
0x1800093bd  mov     rdx, rdi
0x1800093c0  mov     ecx, esi
0x1800093c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093c7  add     rsp, 58h
0x1800093cb  pop     rdi
0x1800093cc  pop     rsi
0x1800093cd  pop     rbp
0x1800093ce  pop     rbx
0x1800093cf  retn
```
