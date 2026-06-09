# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180025990`
- end: `0x180025ad2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800255e0`

## callees

- `0x18001e8d8`
- `0x1800257a0`
- `0x180025990`
- `0x18002b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(55324166, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_180059F78,
      0x2F29A04u,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v15,
      1u,
      0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180025990  mov     [rsp+arg_10], rbx
0x180025995  mov     [rsp+arg_18], rsi
0x18002599a  mov     [rsp+arg_0], rcx
0x18002599f  push    rdi
0x1800259a0  sub     rsp, 40h
0x1800259a4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800259ab  mov     rbx, rdx
0x1800259ae  test    rax, rax
0x1800259b1  jz      short loc_1800259C6
0x1800259b3  mov     edx, 3
0x1800259b8  mov     ecx, 34C2E06h
0x1800259bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259c2  mov     edx, eax
0x1800259c4  jmp     short loc_1800259D4
0x1800259c6  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800259cd  test    rax, rax
0x1800259d0  jnz     short loc_1800259B3
0x1800259d2  xor     edx, edx
0x1800259d4  mov     r8d, edx
0x1800259d7  mov     qword ptr [rbx], 0
0x1800259de  and     r8d, 0FFFFFF3Fh
0x1800259e5  mov     eax, edx
0x1800259e7  and     edx, 80h
0x1800259ed  mov     ecx, r8d
0x1800259f0  and     ecx, 3
0x1800259f3  mov     esi, 40h ; '@'
0x1800259f8  shl     ecx, 2
0x1800259fb  and     eax, esi
0x1800259fd  or      ecx, eax
0x1800259ff  shl     ecx, 2
0x180025a02  or      ecx, edx
0x180025a04  shl     ecx, 3
0x180025a07  test    r8d, r8d
0x180025a0a  jnz     short loc_180025A13
0x180025a0c  mov     edx, esi
0x180025a0e  mov     r8d, esi
0x180025a11  jmp     short loc_180025A1F
0x180025a13  xor     edx, edx
0x180025a15  cmp     r8d, 2
0x180025a19  cmovz   edx, esi
0x180025a1c  mov     r8d, edx
0x180025a1f  mov     eax, ecx
0x180025a21  mov     edi, 1
0x180025a26  or      eax, r8d
0x180025a29  or      ecx, edx
0x180025a2b  mov     [rbx], eax
0x180025a2d  bt      ecx, 0Ah
0x180025a31  jnb     short loc_180025A3B
0x180025a33  cmp     ecx, 800h
0x180025a39  jnb     short loc_180025A42
0x180025a3b  xor     dl, dl
0x180025a3d  test    sil, cl
0x180025a40  jz      short loc_180025AAB
0x180025a42  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180025a49  mov     r8d, [rax]
0x180025a4c  test    r8b, 4
0x180025a50  jnz     short loc_180025A67
0x180025a52  lea     rdx, [rsp+48h+arg_8]
0x180025a57  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180025a5c  mov     rcx, [rax]
0x180025a5f  mov     [rsp+48h+arg_8], rcx
0x180025a64  mov     r8d, ecx
0x180025a67  xor     eax, eax
0x180025a69  mov     word ptr [rsp+48h+arg_0+4], 3
0x180025a70  mov     r9d, r8d
0x180025a73  mov     [rsp+48h+var_18], eax
0x180025a77  mov     dword ptr [rsp+48h+arg_0], eax
0x180025a7b  lea     rcx, qword_180059F78
0x180025a82  shr     r9d, 0Bh
0x180025a86  lea     rax, [rsp+48h+arg_0]
0x180025a8b  shr     r8d, 0Ah
0x180025a8f  and     r9d, edi
0x180025a92  and     r8d, edi
0x180025a95  mov     [rsp+48h+var_20], edi
0x180025a99  mov     edx, 2F29A04h
0x180025a9e  mov     [rsp+48h+var_28], rax
0x180025aa3  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180025aa8  mov     dl, dil
0x180025aab  mov     eax, [rbx]
0x180025aad  test    sil, al
0x180025ab0  jz      short loc_180025AB6
0x180025ab2  test    dl, dl
0x180025ab4  jnz     short loc_180025AB8
0x180025ab6  xor     edi, edi
0x180025ab8  mov     rsi, [rsp+48h+arg_18]
0x180025abd  and     eax, 0FFFFFFFEh
0x180025ac0  or      eax, edi
0x180025ac2  mov     [rbx], eax
0x180025ac4  mov     rax, rbx
0x180025ac7  mov     rbx, [rsp+48h+arg_10]
0x180025acc  add     rsp, 40h
0x180025ad0  pop     rdi
0x180025ad1  retn
```
