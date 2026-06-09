# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010790`
- end: `0x180010934`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fe00`

## callees

- `0x18000f0e8`
- `0x18000fee0`
- `0x180010790`
- `0x180011204`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+20h] BYREF
  __int64 v18; // [rsp+68h] [rbp+28h] BYREF

  v17 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(57048231, 3);
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
  v11 = v7 | (unsigned int)v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
                         v11,
                         &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18002DD38,
      0x3667CA2u,
      (v13 >> 10) & 1,
      (v13 >> 11) & 1,
      (__int64)&v17,
      1u,
      0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
                         v14,
                         &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18002DD98,
      0x2AF34F8u,
      (v15 >> 10) & 1,
      (v15 >> 11) & 1,
      (__int64)&v17,
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
0x180010790  mov     [rsp-18h+arg_10], rbx
0x180010795  mov     [rsp-18h+arg_0], rcx
0x18001079a  push    rbp
0x18001079b  push    rdi
0x18001079c  push    r14
0x18001079e  mov     rbp, rsp
0x1800107a1  sub     rsp, 40h
0x1800107a5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800107ac  mov     rdi, rdx
0x1800107af  test    rax, rax
0x1800107b2  jz      short loc_1800107C7
0x1800107b4  mov     edx, 3
0x1800107b9  mov     ecx, 3667CA7h
0x1800107be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c3  mov     edx, eax
0x1800107c5  jmp     short loc_1800107D5
0x1800107c7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800107ce  test    rax, rax
0x1800107d1  jnz     short loc_1800107B4
0x1800107d3  xor     edx, edx
0x1800107d5  mov     r8d, edx
0x1800107d8  mov     qword ptr [rdi], 0
0x1800107df  and     r8d, 0FFFFFF3Fh
0x1800107e6  mov     eax, edx
0x1800107e8  and     edx, 80h
0x1800107ee  mov     ecx, r8d
0x1800107f1  and     ecx, 3
0x1800107f4  mov     r14d, 40h ; '@'
0x1800107fa  shl     ecx, 2
0x1800107fd  and     eax, r14d
0x180010800  or      ecx, eax
0x180010802  shl     ecx, 2
0x180010805  or      ecx, edx
0x180010807  shl     ecx, 3
0x18001080a  test    r8d, r8d
0x18001080d  jnz     short loc_180010817
0x18001080f  mov     edx, r14d
0x180010812  mov     r8d, r14d
0x180010815  jmp     short loc_180010824
0x180010817  xor     edx, edx
0x180010819  cmp     r8d, 2
0x18001081d  cmovz   edx, r14d
0x180010821  mov     r8d, edx
0x180010824  mov     eax, ecx
0x180010826  mov     ebx, 1
0x18001082b  or      eax, r8d
0x18001082e  or      ecx, edx
0x180010830  mov     [rdi], eax
0x180010832  bt      ecx, 0Ah
0x180010836  jnb     short loc_180010840
0x180010838  cmp     ecx, 800h
0x18001083e  jnb     short loc_18001084B
0x180010840  xor     dl, dl
0x180010842  test    r14b, cl
0x180010845  jz      loc_18001090F
0x18001084b  mov     rax, cs:Feature_ValLabTest__descriptor
0x180010852  mov     r8d, [rax]
0x180010855  test    r8b, 4
0x180010859  jnz     short loc_18001086E
0x18001085b  lea     rdx, [rbp+arg_8]
0x18001085f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180010864  mov     rcx, [rax]
0x180010867  mov     [rbp+arg_8], rcx
0x18001086b  mov     r8d, ecx
0x18001086e  xor     eax, eax
0x180010870  mov     word ptr [rbp+arg_0+4], 3
0x180010876  mov     r9d, r8d
0x180010879  mov     [rsp+40h+var_10], eax
0x18001087d  mov     dword ptr [rbp+arg_0], eax
0x180010880  lea     rcx, qword_18002DD38
0x180010887  shr     r9d, 0Bh
0x18001088b  lea     rax, [rbp+arg_0]
0x18001088f  shr     r8d, 0Ah
0x180010893  and     r9d, ebx
0x180010896  and     r8d, ebx
0x180010899  mov     [rsp+40h+var_18], ebx
0x18001089d  mov     edx, 3667CA2h
0x1800108a2  mov     [rsp+40h+var_20], rax
0x1800108a7  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800108ac  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800108b3  mov     r8d, [rax]
0x1800108b6  test    r8b, 4
0x1800108ba  jnz     short loc_1800108CF
0x1800108bc  lea     rdx, [rbp+arg_8]
0x1800108c0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800108c5  mov     rcx, [rax]
0x1800108c8  mov     [rbp+arg_8], rcx
0x1800108cc  mov     r8d, ecx
0x1800108cf  xor     eax, eax
0x1800108d1  mov     word ptr [rbp+arg_0+4], 3
0x1800108d7  mov     r9d, r8d
0x1800108da  mov     [rsp+40h+var_10], eax
0x1800108de  mov     dword ptr [rbp+arg_0], eax
0x1800108e1  lea     rcx, qword_18002DD98
0x1800108e8  shr     r9d, 0Bh
0x1800108ec  lea     rax, [rbp+arg_0]
0x1800108f0  shr     r8d, 0Ah
0x1800108f4  and     r9d, ebx
0x1800108f7  and     r8d, ebx
0x1800108fa  mov     [rsp+40h+var_18], ebx
0x1800108fe  mov     edx, 2AF34F8h
0x180010903  mov     [rsp+40h+var_20], rax
0x180010908  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001090d  mov     dl, bl
0x18001090f  mov     eax, [rdi]
0x180010911  test    r14b, al
0x180010914  jz      short loc_18001091A
0x180010916  test    dl, dl
0x180010918  jnz     short loc_18001091C
0x18001091a  xor     ebx, ebx
0x18001091c  and     eax, 0FFFFFFFEh
0x18001091f  or      eax, ebx
0x180010921  mov     rbx, [rsp+40h+arg_10]
0x180010926  mov     [rdi], eax
0x180010928  mov     rax, rdi
0x18001092b  add     rsp, 40h
0x18001092f  pop     r14
0x180010931  pop     rdi
0x180010932  pop     rbp
0x180010933  retn
```
