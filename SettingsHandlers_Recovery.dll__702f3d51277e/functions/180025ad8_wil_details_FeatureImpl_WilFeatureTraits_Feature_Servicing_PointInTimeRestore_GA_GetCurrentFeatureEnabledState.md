# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180025ad8`
- end: `0x180025c3b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x1800256c0`

## callees

- `0x18001e8d8`
- `0x1800257a0`
- `0x180025ad8`
- `0x180026338`
- `0x18002b010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(
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
  char v12; // si
  bool v13; // dl
  unsigned int v14; // r8d
  char IsEnabled; // al
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(60394409, 3);
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
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( ((unsigned __int8)v11 & 0x40) == 0 )
      goto LABEL_19;
  }
  v14 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
  {
    v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
             v11,
             &v18);
    v14 = v18;
  }
  WORD2(v17) = 3;
  LODWORD(v17) = 0;
  wil::details::ReportUsageToService(
    (__int64)&qword_180059F78,
    0x2F29A04u,
    (v14 >> 10) & 1,
    (v14 >> 11) & 1,
    (__int64)&v17,
    1u,
    0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl);
  v13 = IsEnabled != 0;
  if ( v12 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180025ad8  mov     [rsp+arg_10], rbx
0x180025add  mov     [rsp+arg_0], rcx
0x180025ae2  push    rbp
0x180025ae3  push    rsi
0x180025ae4  push    rdi
0x180025ae5  sub     rsp, 40h
0x180025ae9  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180025af0  mov     rbx, rdx
0x180025af3  test    rax, rax
0x180025af6  jz      short loc_180025B0B
0x180025af8  mov     edx, 3
0x180025afd  mov     ecx, 3998BA9h
0x180025b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b07  mov     edx, eax
0x180025b09  jmp     short loc_180025B19
0x180025b0b  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180025b12  test    rax, rax
0x180025b15  jnz     short loc_180025AF8
0x180025b17  xor     edx, edx
0x180025b19  mov     r8d, edx
0x180025b1c  mov     qword ptr [rbx], 0
0x180025b23  and     r8d, 0FFFFFF3Fh
0x180025b2a  mov     eax, edx
0x180025b2c  and     edx, 80h
0x180025b32  mov     ecx, r8d
0x180025b35  and     ecx, 3
0x180025b38  mov     ebp, 40h ; '@'
0x180025b3d  shl     ecx, 2
0x180025b40  and     eax, ebp
0x180025b42  or      ecx, eax
0x180025b44  shl     ecx, 2
0x180025b47  or      ecx, edx
0x180025b49  shl     ecx, 3
0x180025b4c  test    r8d, r8d
0x180025b4f  jnz     short loc_180025B58
0x180025b51  mov     edx, ebp
0x180025b53  mov     r8d, ebp
0x180025b56  jmp     short loc_180025B64
0x180025b58  xor     edx, edx
0x180025b5a  cmp     r8d, 2
0x180025b5e  cmovz   edx, ebp
0x180025b61  mov     r8d, edx
0x180025b64  mov     eax, ecx
0x180025b66  mov     edi, 1
0x180025b6b  or      eax, r8d
0x180025b6e  or      ecx, edx
0x180025b70  mov     [rbx], eax
0x180025b72  bt      ecx, 0Ah
0x180025b76  jnb     short loc_180025B85
0x180025b78  cmp     ecx, 800h
0x180025b7e  jb      short loc_180025B85
0x180025b80  mov     sil, dil
0x180025b83  jmp     short loc_180025B93
0x180025b85  xor     sil, sil
0x180025b88  xor     dl, dl
0x180025b8a  test    bpl, cl
0x180025b8d  jz      loc_180025C17
0x180025b93  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180025b9a  mov     r8d, [rax]
0x180025b9d  test    r8b, 4
0x180025ba1  jnz     short loc_180025BB8
0x180025ba3  lea     rdx, [rsp+58h+arg_8]
0x180025ba8  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180025bad  mov     rcx, [rax]
0x180025bb0  mov     [rsp+58h+arg_8], rcx
0x180025bb5  mov     r8d, ecx
0x180025bb8  xor     eax, eax
0x180025bba  mov     word ptr [rsp+58h+arg_0+4], 3
0x180025bc1  mov     r9d, r8d
0x180025bc4  mov     [rsp+58h+var_28], eax
0x180025bc8  mov     dword ptr [rsp+58h+arg_0], eax
0x180025bcc  lea     rcx, qword_180059F78
0x180025bd3  shr     r9d, 0Bh
0x180025bd7  lea     rax, [rsp+58h+arg_0]
0x180025bdc  shr     r8d, 0Ah
0x180025be0  and     r9d, edi
0x180025be3  and     r8d, edi
0x180025be6  mov     [rsp+58h+var_30], edi
0x180025bea  mov     edx, 2F29A04h
0x180025bef  mov     [rsp+58h+var_38], rax
0x180025bf4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180025bf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x180025c00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(wil::ReportingKind)
0x180025c05  test    al, al
0x180025c07  setnz   dl
0x180025c0a  test    sil, sil
0x180025c0d  jz      short loc_180025C17
0x180025c0f  test    dl, dl
0x180025c11  jnz     short loc_180025C17
0x180025c13  btr     dword ptr [rbx], 0Ah
0x180025c17  mov     eax, [rbx]
0x180025c19  test    bpl, al
0x180025c1c  jz      short loc_180025C22
0x180025c1e  test    dl, dl
0x180025c20  jnz     short loc_180025C24
0x180025c22  xor     edi, edi
0x180025c24  and     eax, 0FFFFFFFEh
0x180025c27  or      eax, edi
0x180025c29  mov     [rbx], eax
0x180025c2b  mov     rax, rbx
0x180025c2e  mov     rbx, [rsp+58h+arg_10]
0x180025c33  add     rsp, 40h
0x180025c37  pop     rdi
0x180025c38  pop     rsi
0x180025c39  pop     rbp
0x180025c3a  retn
```
