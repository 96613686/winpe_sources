# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180020aa4`
- end: `0x180020bd4`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001f86c`
- `0x18001f9dc`
- `0x18001fb4c`
- `0x18001fcbc`
- `0x18001fe2c`
- `0x18001ff9c`
- `0x180021328`
- `0x1800213c8`
- `0x180021464`
- `0x180021500`
- `0x18002159c`
- `0x180021638`
- `0x1800216d4`

## callees

- `0x180020aa4`
- `0x180020bdc`
- `0x180032010`

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
0x180020aa4  mov     rax, rsp
0x180020aa7  push    rbx
0x180020aa8  push    rbp
0x180020aa9  push    rsi
0x180020aaa  push    rdi
0x180020aab  sub     rsp, 58h
0x180020aaf  mov     r11d, [rax+38h]
0x180020ab3  mov     esi, edx
0x180020ab5  mov     rbp, rcx
0x180020ab8  test    r11d, r11d
0x180020abb  jz      loc_180020BCB
0x180020ac1  mov     ebx, [rsp+78h+arg_28]
0x180020ac8  mov     r10d, r11d
0x180020acb  sub     r10d, 1
0x180020acf  jz      loc_180020B5A
0x180020ad5  sub     r10d, 1
0x180020ad9  jz      short loc_180020B4C
0x180020adb  sub     r10d, 1
0x180020adf  jz      short loc_180020B3E
0x180020ae1  sub     r10d, 1
0x180020ae5  jz      short loc_180020B30
0x180020ae7  sub     r10d, 1
0x180020aeb  jz      short loc_180020B22
0x180020aed  cmp     r10d, 1
0x180020af1  jz      short loc_180020B14
0x180020af3  sub     r11b, 64h ; 'd'
0x180020af7  cmp     r11b, 31h ; '1'
0x180020afb  ja      short loc_180020B67
0x180020afd  mov     eax, ebx
0x180020aff  neg     eax
0x180020b01  movzx   eax, r11b
0x180020b05  sbb     ecx, ecx
0x180020b07  and     ecx, 0FFFFFFCEh
0x180020b0a  add     ecx, 96h
0x180020b10  add     ecx, eax
0x180020b12  jmp     short loc_180020B6C
0x180020b14  mov     eax, ebx
0x180020b16  neg     eax
0x180020b18  sbb     ecx, ecx
0x180020b1a  and     ecx, 0FFFFFFFEh
0x180020b1d  add     ecx, 0Bh
0x180020b20  jmp     short loc_180020B6C
0x180020b22  mov     eax, ebx
0x180020b24  neg     eax
0x180020b26  sbb     ecx, ecx
0x180020b28  and     ecx, 0FFFFFFFEh
0x180020b2b  add     ecx, 0Ah
0x180020b2e  jmp     short loc_180020B6C
0x180020b30  mov     eax, ebx
0x180020b32  neg     eax
0x180020b34  sbb     ecx, ecx
0x180020b36  and     ecx, 0FFFFFFFCh
0x180020b39  add     ecx, 7
0x180020b3c  jmp     short loc_180020B6C
0x180020b3e  mov     eax, ebx
0x180020b40  neg     eax
0x180020b42  sbb     ecx, ecx
0x180020b44  and     ecx, 0FFFFFFFCh
0x180020b47  add     ecx, 6
0x180020b4a  jmp     short loc_180020B6C
0x180020b4c  mov     eax, ebx
0x180020b4e  neg     eax
0x180020b50  sbb     ecx, ecx
0x180020b52  and     ecx, 0FFFFFFFCh
0x180020b55  add     ecx, 5
0x180020b58  jmp     short loc_180020B6C
0x180020b5a  mov     eax, ebx
0x180020b5c  neg     eax
0x180020b5e  sbb     ecx, ecx
0x180020b60  not     ecx
0x180020b62  and     ecx, 4
0x180020b65  jmp     short loc_180020B6C
0x180020b67  mov     ecx, 0FFh
0x180020b6c  mov     rdi, [rsp+78h+arg_20]
0x180020b74  mov     al, [rdi+4]
0x180020b77  mov     byte ptr [rsp+78h+var_40], al
0x180020b7b  mov     dword ptr [rsp+78h+var_58], ecx
0x180020b7f  mov     rcx, rbp
0x180020b82  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180020b87  test    eax, eax
0x180020b89  jz      short loc_180020BCB
0x180020b8b  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180020b92  test    rax, rax
0x180020b95  jz      short loc_180020BCB
0x180020b97  mov     [rsp+78h+var_40], 1
0x180020ba0  lea     rcx, [rsp+78h+arg_30]
0x180020ba8  mov     [rsp+78h+var_48], 0
0x180020bad  mov     r9d, ebx
0x180020bb0  mov     [rsp+78h+var_50], 0
0x180020bb9  xor     r8d, r8d
0x180020bbc  mov     [rsp+78h+var_58], rcx
0x180020bc1  mov     rdx, rdi
0x180020bc4  mov     ecx, esi
0x180020bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bcb  add     rsp, 58h
0x180020bcf  pop     rdi
0x180020bd0  pop     rsi
0x180020bd1  pop     rbp
0x180020bd2  pop     rbx
0x180020bd3  retn
```
