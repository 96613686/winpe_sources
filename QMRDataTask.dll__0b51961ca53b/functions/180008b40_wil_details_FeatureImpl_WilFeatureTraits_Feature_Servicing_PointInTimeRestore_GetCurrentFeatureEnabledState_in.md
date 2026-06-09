# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008b40`
- end: `0x180008c82`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180007df0`

## callees

- `0x18000886c`
- `0x180008b40`
- `0x18000dc68`
- `0x180015010`

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
    wil::details::ReportUsageToService(&qword_180024070, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180008b40  mov     [rsp+arg_10], rbx
0x180008b45  mov     [rsp+arg_18], rsi
0x180008b4a  mov     [rsp+arg_0], rcx
0x180008b4f  push    rdi
0x180008b50  sub     rsp, 40h
0x180008b54  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008b5b  mov     rbx, rdx
0x180008b5e  test    rax, rax
0x180008b61  jz      short loc_180008B76
0x180008b63  mov     edx, 3
0x180008b68  mov     ecx, 34C2E06h
0x180008b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b72  mov     edx, eax
0x180008b74  jmp     short loc_180008B84
0x180008b76  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008b7d  test    rax, rax
0x180008b80  jnz     short loc_180008B63
0x180008b82  xor     edx, edx
0x180008b84  mov     r8d, edx
0x180008b87  mov     qword ptr [rbx], 0
0x180008b8e  and     r8d, 0FFFFFF3Fh
0x180008b95  mov     eax, edx
0x180008b97  and     edx, 80h
0x180008b9d  mov     ecx, r8d
0x180008ba0  and     ecx, 3
0x180008ba3  mov     esi, 40h ; '@'
0x180008ba8  shl     ecx, 2
0x180008bab  and     eax, esi
0x180008bad  or      ecx, eax
0x180008baf  shl     ecx, 2
0x180008bb2  or      ecx, edx
0x180008bb4  shl     ecx, 3
0x180008bb7  test    r8d, r8d
0x180008bba  jnz     short loc_180008BC3
0x180008bbc  mov     edx, esi
0x180008bbe  mov     r8d, esi
0x180008bc1  jmp     short loc_180008BCF
0x180008bc3  xor     edx, edx
0x180008bc5  cmp     r8d, 2
0x180008bc9  cmovz   edx, esi
0x180008bcc  mov     r8d, edx
0x180008bcf  mov     eax, ecx
0x180008bd1  mov     edi, 1
0x180008bd6  or      eax, r8d
0x180008bd9  or      ecx, edx
0x180008bdb  mov     [rbx], eax
0x180008bdd  bt      ecx, 0Ah
0x180008be1  jnb     short loc_180008BEB
0x180008be3  cmp     ecx, 800h
0x180008be9  jnb     short loc_180008BF2
0x180008beb  xor     dl, dl
0x180008bed  test    sil, cl
0x180008bf0  jz      short loc_180008C5B
0x180008bf2  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180008bf9  mov     r8d, [rax]
0x180008bfc  test    r8b, 4
0x180008c00  jnz     short loc_180008C17
0x180008c02  lea     rdx, [rsp+48h+arg_8]
0x180008c07  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180008c0c  mov     rcx, [rax]
0x180008c0f  mov     [rsp+48h+arg_8], rcx
0x180008c14  mov     r8d, ecx
0x180008c17  xor     eax, eax
0x180008c19  mov     word ptr [rsp+48h+arg_0+4], 3
0x180008c20  mov     r9d, r8d
0x180008c23  mov     [rsp+48h+var_18], eax
0x180008c27  mov     dword ptr [rsp+48h+arg_0], eax
0x180008c2b  lea     rcx, qword_180024070
0x180008c32  shr     r9d, 0Bh
0x180008c36  lea     rax, [rsp+48h+arg_0]
0x180008c3b  shr     r8d, 0Ah
0x180008c3f  and     r9d, edi
0x180008c42  and     r8d, edi
0x180008c45  mov     [rsp+48h+var_20], edi
0x180008c49  mov     edx, 2F29A04h
0x180008c4e  mov     [rsp+48h+var_28], rax
0x180008c53  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180008c58  mov     dl, dil
0x180008c5b  mov     eax, [rbx]
0x180008c5d  test    sil, al
0x180008c60  jz      short loc_180008C66
0x180008c62  test    dl, dl
0x180008c64  jnz     short loc_180008C68
0x180008c66  xor     edi, edi
0x180008c68  mov     rsi, [rsp+48h+arg_18]
0x180008c6d  and     eax, 0FFFFFFFEh
0x180008c70  or      eax, edi
0x180008c72  mov     [rbx], eax
0x180008c74  mov     rax, rbx
0x180008c77  mov     rbx, [rsp+48h+arg_10]
0x180008c7c  add     rsp, 40h
0x180008c80  pop     rdi
0x180008c81  retn
```
