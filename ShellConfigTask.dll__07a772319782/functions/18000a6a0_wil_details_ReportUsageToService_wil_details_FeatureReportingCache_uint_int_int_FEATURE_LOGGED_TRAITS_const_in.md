# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000a6a0`
- end: `0x18000a7d8`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `312`
- prototype: ``
- caller_count: `46`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a608`
- `0x180018800`
- `0x1800189d4`
- `0x180018b1c`
- `0x180018d84`
- `0x180018ebc`
- `0x18001902c`
- `0x1800192a8`
- `0x1800193f0`
- `0x180019534`
- `0x18001969c`
- `0x1800197e4`
- `0x180019a3c`
- `0x180019bac`
- `0x180019d1c`
- `0x180019e8c`
- `0x18001a244`
- `0x18001de24`
- `0x18001debc`
- `0x18001df54`
- `0x18001dfec`
- `0x18001e084`
- `0x180020784`
- `0x180020820`
- `0x18002093c`
- `0x1800209dc`
- `0x180020a7c`
- `0x180020b1c`
- `0x180020bbc`
- `0x180020c5c`
- `0x180020dfc`
- `0x180020e9c`
- `0x180020fbc`
- `0x18002105c`
- `0x1800210fc`
- `0x18002119c`
- `0x18002123c`
- `0x18002135c`
- `0x1800213fc`
- `0x180021498`
- `0x180021534`
- `0x1800215d0`
- `0x18002166c`
- `0x18002170c`
- `0x18002a0b4`
- `0x18002e27c`

## callees

- `0x18000a6a0`
- `0x18000a7e0`
- `0x180033010`

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
0x18000a6a0  mov     rax, rsp
0x18000a6a3  push    rbx
0x18000a6a4  push    rbp
0x18000a6a5  push    rsi
0x18000a6a6  push    rdi
0x18000a6a7  sub     rsp, 58h
0x18000a6ab  mov     r11d, [rax+38h]
0x18000a6af  mov     esi, edx
0x18000a6b1  mov     rbp, rcx
0x18000a6b4  test    r11d, r11d
0x18000a6b7  jz      loc_18000A7CF
0x18000a6bd  mov     ebx, [rsp+78h+arg_28]
0x18000a6c4  mov     r10d, r11d
0x18000a6c7  sub     r10d, 1
0x18000a6cb  jz      loc_18000A756
0x18000a6d1  sub     r10d, 1
0x18000a6d5  jz      short loc_18000A748
0x18000a6d7  sub     r10d, 1
0x18000a6db  jz      short loc_18000A73A
0x18000a6dd  sub     r10d, 1
0x18000a6e1  jz      short loc_18000A72C
0x18000a6e3  sub     r10d, 1
0x18000a6e7  jz      short loc_18000A71E
0x18000a6e9  cmp     r10d, 1
0x18000a6ed  jz      short loc_18000A710
0x18000a6ef  sub     r11b, 64h ; 'd'
0x18000a6f3  cmp     r11b, 31h ; '1'
0x18000a6f7  ja      short loc_18000A763
0x18000a6f9  mov     eax, ebx
0x18000a6fb  neg     eax
0x18000a6fd  movzx   eax, r11b
0x18000a701  sbb     ecx, ecx
0x18000a703  and     ecx, 0FFFFFFCEh
0x18000a706  add     ecx, 96h
0x18000a70c  add     ecx, eax
0x18000a70e  jmp     short loc_18000A768
0x18000a710  mov     eax, ebx
0x18000a712  neg     eax
0x18000a714  sbb     ecx, ecx
0x18000a716  and     ecx, 0FFFFFFFEh
0x18000a719  add     ecx, 0Bh
0x18000a71c  jmp     short loc_18000A768
0x18000a71e  mov     eax, ebx
0x18000a720  neg     eax
0x18000a722  sbb     ecx, ecx
0x18000a724  and     ecx, 0FFFFFFFEh
0x18000a727  add     ecx, 0Ah
0x18000a72a  jmp     short loc_18000A768
0x18000a72c  mov     eax, ebx
0x18000a72e  neg     eax
0x18000a730  sbb     ecx, ecx
0x18000a732  and     ecx, 0FFFFFFFCh
0x18000a735  add     ecx, 7
0x18000a738  jmp     short loc_18000A768
0x18000a73a  mov     eax, ebx
0x18000a73c  neg     eax
0x18000a73e  sbb     ecx, ecx
0x18000a740  and     ecx, 0FFFFFFFCh
0x18000a743  add     ecx, 6
0x18000a746  jmp     short loc_18000A768
0x18000a748  mov     eax, ebx
0x18000a74a  neg     eax
0x18000a74c  sbb     ecx, ecx
0x18000a74e  and     ecx, 0FFFFFFFCh
0x18000a751  add     ecx, 5
0x18000a754  jmp     short loc_18000A768
0x18000a756  mov     eax, ebx
0x18000a758  neg     eax
0x18000a75a  sbb     ecx, ecx
0x18000a75c  not     ecx
0x18000a75e  and     ecx, 4
0x18000a761  jmp     short loc_18000A768
0x18000a763  mov     ecx, 0FFh
0x18000a768  mov     rdi, [rsp+78h+arg_20]
0x18000a770  mov     al, [rdi+4]
0x18000a773  mov     byte ptr [rsp+78h+var_40], al
0x18000a777  mov     dword ptr [rsp+78h+var_50], 0
0x18000a77f  mov     dword ptr [rsp+78h+var_58], ecx
0x18000a783  mov     rcx, rbp
0x18000a786  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000a78b  test    eax, eax
0x18000a78d  jz      short loc_18000A7CF
0x18000a78f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000a796  test    rax, rax
0x18000a799  jz      short loc_18000A7CF
0x18000a79b  mov     [rsp+78h+var_40], 1
0x18000a7a4  lea     rcx, [rsp+78h+arg_30]
0x18000a7ac  mov     [rsp+78h+var_48], 0
0x18000a7b1  mov     r9d, ebx
0x18000a7b4  mov     [rsp+78h+var_50], 0
0x18000a7bd  xor     r8d, r8d
0x18000a7c0  mov     [rsp+78h+var_58], rcx
0x18000a7c5  mov     rdx, rdi
0x18000a7c8  mov     ecx, esi
0x18000a7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7cf  add     rsp, 58h
0x18000a7d3  pop     rdi
0x18000a7d4  pop     rsi
0x18000a7d5  pop     rbp
0x18000a7d6  pop     rbx
0x18000a7d7  retn
```
