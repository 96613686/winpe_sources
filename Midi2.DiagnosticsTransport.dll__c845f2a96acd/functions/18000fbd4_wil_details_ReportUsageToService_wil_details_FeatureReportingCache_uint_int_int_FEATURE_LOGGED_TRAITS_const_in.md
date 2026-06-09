# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000fbd4`
- end: `0x18000fd04`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e8f0`
- `0x18000ea60`
- `0x18000ebd0`
- `0x18000ed40`
- `0x18000eeb0`
- `0x18000f020`
- `0x180010078`
- `0x180010118`
- `0x1800101b4`
- `0x180010250`
- `0x1800102ec`
- `0x180010388`
- `0x180010424`

## callees

- `0x18000fbd4`
- `0x18000fd0c`
- `0x180013010`

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
0x18000fbd4  mov     rax, rsp
0x18000fbd7  push    rbx
0x18000fbd8  push    rbp
0x18000fbd9  push    rsi
0x18000fbda  push    rdi
0x18000fbdb  sub     rsp, 58h
0x18000fbdf  mov     r11d, [rax+38h]
0x18000fbe3  mov     esi, edx
0x18000fbe5  mov     rbp, rcx
0x18000fbe8  test    r11d, r11d
0x18000fbeb  jz      loc_18000FCFB
0x18000fbf1  mov     ebx, [rsp+78h+arg_28]
0x18000fbf8  mov     r10d, r11d
0x18000fbfb  sub     r10d, 1
0x18000fbff  jz      loc_18000FC8A
0x18000fc05  sub     r10d, 1
0x18000fc09  jz      short loc_18000FC7C
0x18000fc0b  sub     r10d, 1
0x18000fc0f  jz      short loc_18000FC6E
0x18000fc11  sub     r10d, 1
0x18000fc15  jz      short loc_18000FC60
0x18000fc17  sub     r10d, 1
0x18000fc1b  jz      short loc_18000FC52
0x18000fc1d  cmp     r10d, 1
0x18000fc21  jz      short loc_18000FC44
0x18000fc23  sub     r11b, 64h ; 'd'
0x18000fc27  cmp     r11b, 31h ; '1'
0x18000fc2b  ja      short loc_18000FC97
0x18000fc2d  mov     eax, ebx
0x18000fc2f  neg     eax
0x18000fc31  movzx   eax, r11b
0x18000fc35  sbb     ecx, ecx
0x18000fc37  and     ecx, 0FFFFFFCEh
0x18000fc3a  add     ecx, 96h
0x18000fc40  add     ecx, eax
0x18000fc42  jmp     short loc_18000FC9C
0x18000fc44  mov     eax, ebx
0x18000fc46  neg     eax
0x18000fc48  sbb     ecx, ecx
0x18000fc4a  and     ecx, 0FFFFFFFEh
0x18000fc4d  add     ecx, 0Bh
0x18000fc50  jmp     short loc_18000FC9C
0x18000fc52  mov     eax, ebx
0x18000fc54  neg     eax
0x18000fc56  sbb     ecx, ecx
0x18000fc58  and     ecx, 0FFFFFFFEh
0x18000fc5b  add     ecx, 0Ah
0x18000fc5e  jmp     short loc_18000FC9C
0x18000fc60  mov     eax, ebx
0x18000fc62  neg     eax
0x18000fc64  sbb     ecx, ecx
0x18000fc66  and     ecx, 0FFFFFFFCh
0x18000fc69  add     ecx, 7
0x18000fc6c  jmp     short loc_18000FC9C
0x18000fc6e  mov     eax, ebx
0x18000fc70  neg     eax
0x18000fc72  sbb     ecx, ecx
0x18000fc74  and     ecx, 0FFFFFFFCh
0x18000fc77  add     ecx, 6
0x18000fc7a  jmp     short loc_18000FC9C
0x18000fc7c  mov     eax, ebx
0x18000fc7e  neg     eax
0x18000fc80  sbb     ecx, ecx
0x18000fc82  and     ecx, 0FFFFFFFCh
0x18000fc85  add     ecx, 5
0x18000fc88  jmp     short loc_18000FC9C
0x18000fc8a  mov     eax, ebx
0x18000fc8c  neg     eax
0x18000fc8e  sbb     ecx, ecx
0x18000fc90  not     ecx
0x18000fc92  and     ecx, 4
0x18000fc95  jmp     short loc_18000FC9C
0x18000fc97  mov     ecx, 0FFh
0x18000fc9c  mov     rdi, [rsp+78h+arg_20]
0x18000fca4  mov     al, [rdi+4]
0x18000fca7  mov     byte ptr [rsp+78h+var_40], al
0x18000fcab  mov     dword ptr [rsp+78h+var_58], ecx
0x18000fcaf  mov     rcx, rbp
0x18000fcb2  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000fcb7  test    eax, eax
0x18000fcb9  jz      short loc_18000FCFB
0x18000fcbb  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000fcc2  test    rax, rax
0x18000fcc5  jz      short loc_18000FCFB
0x18000fcc7  mov     [rsp+78h+var_40], 1
0x18000fcd0  lea     rcx, [rsp+78h+arg_30]
0x18000fcd8  mov     [rsp+78h+var_48], 0
0x18000fcdd  mov     r9d, ebx
0x18000fce0  mov     [rsp+78h+var_50], 0
0x18000fce9  xor     r8d, r8d
0x18000fcec  mov     [rsp+78h+var_58], rcx
0x18000fcf1  mov     rdx, rdi
0x18000fcf4  mov     ecx, esi
0x18000fcf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcfb  add     rsp, 58h
0x18000fcff  pop     rdi
0x18000fd00  pop     rsi
0x18000fd01  pop     rbp
0x18000fd02  pop     rbx
0x18000fd03  retn
```
