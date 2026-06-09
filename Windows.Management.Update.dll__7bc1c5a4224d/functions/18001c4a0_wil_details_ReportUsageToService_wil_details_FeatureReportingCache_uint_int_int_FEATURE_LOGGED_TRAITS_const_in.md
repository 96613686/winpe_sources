# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001c4a0`
- end: `0x18001c5d0`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001bdb8`
- `0x18001c8a0`
- `0x18001c940`

## callees

- `0x18001c4a0`
- `0x18001c5d8`
- `0x18002a010`

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
0x18001c4a0  mov     rax, rsp
0x18001c4a3  push    rbx
0x18001c4a4  push    rbp
0x18001c4a5  push    rsi
0x18001c4a6  push    rdi
0x18001c4a7  sub     rsp, 58h
0x18001c4ab  mov     r11d, [rax+38h]
0x18001c4af  mov     esi, edx
0x18001c4b1  mov     rbp, rcx
0x18001c4b4  test    r11d, r11d
0x18001c4b7  jz      loc_18001C5C7
0x18001c4bd  mov     ebx, [rsp+78h+arg_28]
0x18001c4c4  mov     r10d, r11d
0x18001c4c7  sub     r10d, 1
0x18001c4cb  jz      loc_18001C556
0x18001c4d1  sub     r10d, 1
0x18001c4d5  jz      short loc_18001C548
0x18001c4d7  sub     r10d, 1
0x18001c4db  jz      short loc_18001C53A
0x18001c4dd  sub     r10d, 1
0x18001c4e1  jz      short loc_18001C52C
0x18001c4e3  sub     r10d, 1
0x18001c4e7  jz      short loc_18001C51E
0x18001c4e9  cmp     r10d, 1
0x18001c4ed  jz      short loc_18001C510
0x18001c4ef  sub     r11b, 64h ; 'd'
0x18001c4f3  cmp     r11b, 31h ; '1'
0x18001c4f7  ja      short loc_18001C563
0x18001c4f9  mov     eax, ebx
0x18001c4fb  neg     eax
0x18001c4fd  movzx   eax, r11b
0x18001c501  sbb     ecx, ecx
0x18001c503  and     ecx, 0FFFFFFCEh
0x18001c506  add     ecx, 96h
0x18001c50c  add     ecx, eax
0x18001c50e  jmp     short loc_18001C568
0x18001c510  mov     eax, ebx
0x18001c512  neg     eax
0x18001c514  sbb     ecx, ecx
0x18001c516  and     ecx, 0FFFFFFFEh
0x18001c519  add     ecx, 0Bh
0x18001c51c  jmp     short loc_18001C568
0x18001c51e  mov     eax, ebx
0x18001c520  neg     eax
0x18001c522  sbb     ecx, ecx
0x18001c524  and     ecx, 0FFFFFFFEh
0x18001c527  add     ecx, 0Ah
0x18001c52a  jmp     short loc_18001C568
0x18001c52c  mov     eax, ebx
0x18001c52e  neg     eax
0x18001c530  sbb     ecx, ecx
0x18001c532  and     ecx, 0FFFFFFFCh
0x18001c535  add     ecx, 7
0x18001c538  jmp     short loc_18001C568
0x18001c53a  mov     eax, ebx
0x18001c53c  neg     eax
0x18001c53e  sbb     ecx, ecx
0x18001c540  and     ecx, 0FFFFFFFCh
0x18001c543  add     ecx, 6
0x18001c546  jmp     short loc_18001C568
0x18001c548  mov     eax, ebx
0x18001c54a  neg     eax
0x18001c54c  sbb     ecx, ecx
0x18001c54e  and     ecx, 0FFFFFFFCh
0x18001c551  add     ecx, 5
0x18001c554  jmp     short loc_18001C568
0x18001c556  mov     eax, ebx
0x18001c558  neg     eax
0x18001c55a  sbb     ecx, ecx
0x18001c55c  not     ecx
0x18001c55e  and     ecx, 4
0x18001c561  jmp     short loc_18001C568
0x18001c563  mov     ecx, 0FFh
0x18001c568  mov     rdi, [rsp+78h+arg_20]
0x18001c570  mov     al, [rdi+4]
0x18001c573  mov     byte ptr [rsp+78h+var_40], al
0x18001c577  mov     dword ptr [rsp+78h+var_58], ecx
0x18001c57b  mov     rcx, rbp
0x18001c57e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001c583  test    eax, eax
0x18001c585  jz      short loc_18001C5C7
0x18001c587  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001c58e  test    rax, rax
0x18001c591  jz      short loc_18001C5C7
0x18001c593  mov     [rsp+78h+var_40], 1
0x18001c59c  lea     rcx, [rsp+78h+arg_30]
0x18001c5a4  mov     [rsp+78h+var_48], 0
0x18001c5a9  mov     r9d, ebx
0x18001c5ac  mov     [rsp+78h+var_50], 0
0x18001c5b5  xor     r8d, r8d
0x18001c5b8  mov     [rsp+78h+var_58], rcx
0x18001c5bd  mov     rdx, rdi
0x18001c5c0  mov     ecx, esi
0x18001c5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5c7  add     rsp, 58h
0x18001c5cb  pop     rdi
0x18001c5cc  pop     rsi
0x18001c5cd  pop     rbp
0x18001c5ce  pop     rbx
0x18001c5cf  retn
```
