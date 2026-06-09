# wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014478`
- end: `0x1800145ba`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_53100197@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012e80`

## callees

- `0x18000ab68`
- `0x180013200`
- `0x180014478`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_53100197>::GetCurrentFeatureEnabledState(
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
    v4 = v2(53100197, 3);
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
    v13 = *(_DWORD *)Feature_ImplVal__descriptor;
    if ( (*(_DWORD *)Feature_ImplVal__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(v11, &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180033808, 54237993, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180014478  mov     [rsp+arg_10], rbx
0x18001447d  mov     [rsp+arg_18], rsi
0x180014482  mov     [rsp+arg_0], rcx
0x180014487  push    rdi
0x180014488  sub     rsp, 40h
0x18001448c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014493  mov     rbx, rdx
0x180014496  test    rax, rax
0x180014499  jz      short loc_1800144AE
0x18001449b  mov     edx, 3
0x1800144a0  mov     ecx, 32A3EA5h
0x1800144a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144aa  mov     edx, eax
0x1800144ac  jmp     short loc_1800144BC
0x1800144ae  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800144b5  test    rax, rax
0x1800144b8  jnz     short loc_18001449B
0x1800144ba  xor     edx, edx
0x1800144bc  mov     r8d, edx
0x1800144bf  mov     qword ptr [rbx], 0
0x1800144c6  and     r8d, 0FFFFFF3Fh
0x1800144cd  mov     eax, edx
0x1800144cf  and     edx, 80h
0x1800144d5  mov     ecx, r8d
0x1800144d8  and     ecx, 3
0x1800144db  mov     esi, 40h ; '@'
0x1800144e0  shl     ecx, 2
0x1800144e3  and     eax, esi
0x1800144e5  or      ecx, eax
0x1800144e7  shl     ecx, 2
0x1800144ea  or      ecx, edx
0x1800144ec  shl     ecx, 3
0x1800144ef  test    r8d, r8d
0x1800144f2  jnz     short loc_1800144FB
0x1800144f4  mov     edx, esi
0x1800144f6  mov     r8d, esi
0x1800144f9  jmp     short loc_180014507
0x1800144fb  xor     edx, edx
0x1800144fd  cmp     r8d, 2
0x180014501  cmovz   edx, esi
0x180014504  mov     r8d, edx
0x180014507  mov     eax, ecx
0x180014509  mov     edi, 1
0x18001450e  or      eax, r8d
0x180014511  or      ecx, edx
0x180014513  mov     [rbx], eax
0x180014515  bt      ecx, 0Ah
0x180014519  jnb     short loc_180014523
0x18001451b  cmp     ecx, 800h
0x180014521  jnb     short loc_18001452A
0x180014523  xor     dl, dl
0x180014525  test    sil, cl
0x180014528  jz      short loc_180014593
0x18001452a  mov     rax, cs:Feature_ImplVal__descriptor
0x180014531  mov     r8d, [rax]
0x180014534  test    r8b, 4
0x180014538  jnz     short loc_18001454F
0x18001453a  lea     rdx, [rsp+48h+arg_8]
0x18001453f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ImplVal@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImplVal>::GetCachedFeatureEnabledState(void)
0x180014544  mov     rcx, [rax]
0x180014547  mov     [rsp+48h+arg_8], rcx
0x18001454c  mov     r8d, ecx
0x18001454f  xor     eax, eax
0x180014551  mov     word ptr [rsp+48h+arg_0+4], 3
0x180014558  mov     r9d, r8d
0x18001455b  mov     [rsp+48h+var_18], eax
0x18001455f  mov     dword ptr [rsp+48h+arg_0], eax
0x180014563  lea     rcx, qword_180033808
0x18001456a  shr     r9d, 0Bh
0x18001456e  lea     rax, [rsp+48h+arg_0]
0x180014573  shr     r8d, 0Ah
0x180014577  and     r9d, edi
0x18001457a  and     r8d, edi
0x18001457d  mov     [rsp+48h+var_20], edi
0x180014581  mov     edx, 33B9B29h
0x180014586  mov     [rsp+48h+var_28], rax
0x18001458b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014590  mov     dl, dil
0x180014593  mov     eax, [rbx]
0x180014595  test    sil, al
0x180014598  jz      short loc_18001459E
0x18001459a  test    dl, dl
0x18001459c  jnz     short loc_1800145A0
0x18001459e  xor     edi, edi
0x1800145a0  mov     rsi, [rsp+48h+arg_18]
0x1800145a5  and     eax, 0FFFFFFFEh
0x1800145a8  or      eax, edi
0x1800145aa  mov     [rbx], eax
0x1800145ac  mov     rax, rbx
0x1800145af  mov     rbx, [rsp+48h+arg_10]
0x1800145b4  add     rsp, 40h
0x1800145b8  pop     rdi
0x1800145b9  retn
```
