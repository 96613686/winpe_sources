# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800092f0`
- end: `0x180009447`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180008330`

## callees

- `0x18000886c`
- `0x1800092f0`
- `0x18000dc68`
- `0x180011704`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // eax
  int v7; // ecx
  int v8; // edx
  wil::details *v9; // rcx
  int v10; // edi
  char v11; // si
  bool v12; // dl
  unsigned int v13; // r8d
  char IsEnabled; // al
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(55936146, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 0;
  v7 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  v8 = v7;
  if ( v5 )
  {
    if ( v5 == 2 )
      v6 = 64;
    v8 = v6 | v7;
  }
  v9 = (wil::details *)(v6 | (unsigned int)v7);
  *(_DWORD *)a2 = v8;
  v10 = 1;
  if ( ((unsigned __int16)v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
    if ( ((unsigned __int8)v9 & 0x40) == 0 )
      goto LABEL_17;
  }
  v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
  {
    v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
             v9,
             &v17);
    v13 = v17;
  }
  WORD2(v16) = 3;
  LODWORD(v16) = 0;
  wil::details::ReportUsageToService(
    (__int64)&unk_180024070,
    0x2F29A04u,
    (v13 >> 10) & 1,
    (v13 >> 11) & 1,
    (__int64)&v16,
    1u,
    0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl);
  v12 = IsEnabled != 0;
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_17:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v10 = 0;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp+arg_10], rbx
0x1800092f5  mov     [rsp+arg_0], rcx
0x1800092fa  push    rbp
0x1800092fb  push    rsi
0x1800092fc  push    rdi
0x1800092fd  sub     rsp, 40h
0x180009301  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180009308  mov     rbx, rdx
0x18000930b  test    rax, rax
0x18000930e  jz      short loc_180009323
0x180009310  mov     edx, 3
0x180009315  mov     ecx, 3558492h
0x18000931a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000931f  mov     edx, eax
0x180009321  jmp     short loc_180009331
0x180009323  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000932a  test    rax, rax
0x18000932d  jnz     short loc_180009310
0x18000932f  xor     edx, edx
0x180009331  mov     r8d, edx
0x180009334  mov     qword ptr [rbx], 0
0x18000933b  mov     eax, edx
0x18000933d  and     r8d, 0FFFFFF3Fh
0x180009344  and     edx, 80h
0x18000934a  mov     ecx, r8d
0x18000934d  and     ecx, 3
0x180009350  mov     ebp, 40h ; '@'
0x180009355  shl     ecx, 2
0x180009358  and     eax, ebp
0x18000935a  or      ecx, eax
0x18000935c  xor     eax, eax
0x18000935e  shl     ecx, 2
0x180009361  or      ecx, edx
0x180009363  shl     ecx, 3
0x180009366  mov     edx, ecx
0x180009368  test    r8d, r8d
0x18000936b  jz      short loc_180009376
0x18000936d  cmp     r8d, 2
0x180009371  cmovz   eax, ebp
0x180009374  or      edx, eax
0x180009376  or      ecx, eax
0x180009378  mov     [rbx], edx
0x18000937a  mov     edx, 0C00h
0x18000937f  mov     eax, ecx
0x180009381  and     eax, edx
0x180009383  mov     edi, 1
0x180009388  cmp     eax, edx
0x18000938a  jnz     short loc_180009391
0x18000938c  mov     sil, dil
0x18000938f  jmp     short loc_18000939F
0x180009391  xor     sil, sil
0x180009394  xor     dl, dl
0x180009396  test    bpl, cl
0x180009399  jz      loc_180009423
0x18000939f  mov     rax, cs:Feature_Standalone_Future__descriptor
0x1800093a6  mov     r8d, [rax]
0x1800093a9  test    r8b, 4
0x1800093ad  jnz     short loc_1800093C4
0x1800093af  lea     rdx, [rsp+58h+arg_8]
0x1800093b4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x1800093b9  mov     rcx, [rax]
0x1800093bc  mov     [rsp+58h+arg_8], rcx
0x1800093c1  mov     r8d, ecx
0x1800093c4  xor     eax, eax
0x1800093c6  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800093cd  mov     r9d, r8d
0x1800093d0  mov     [rsp+58h+var_28], eax
0x1800093d4  mov     dword ptr [rsp+58h+arg_0], eax
0x1800093d8  lea     rcx, unk_180024070
0x1800093df  shr     r9d, 0Bh
0x1800093e3  lea     rax, [rsp+58h+arg_0]
0x1800093e8  shr     r8d, 0Ah
0x1800093ec  and     r9d, edi
0x1800093ef  and     r8d, edi
0x1800093f2  mov     [rsp+58h+var_30], edi
0x1800093f6  mov     edx, 2F29A04h
0x1800093fb  mov     [rsp+58h+var_38], rax
0x180009400  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009405  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x18000940c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(wil::ReportingKind)
0x180009411  test    al, al
0x180009413  setnz   dl
0x180009416  test    sil, sil
0x180009419  jz      short loc_180009423
0x18000941b  test    dl, dl
0x18000941d  jnz     short loc_180009423
0x18000941f  btr     dword ptr [rbx], 0Ah
0x180009423  mov     eax, [rbx]
0x180009425  test    bpl, al
0x180009428  jz      short loc_18000942E
0x18000942a  test    dl, dl
0x18000942c  jnz     short loc_180009430
0x18000942e  xor     edi, edi
0x180009430  and     eax, 0FFFFFFFEh
0x180009433  or      eax, edi
0x180009435  mov     [rbx], eax
0x180009437  mov     rax, rbx
0x18000943a  mov     rbx, [rsp+58h+arg_10]
0x18000943f  add     rsp, 40h
0x180009443  pop     rdi
0x180009444  pop     rsi
0x180009445  pop     rbp
0x180009446  retn
```
