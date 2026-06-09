# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x140005e70`
- end: `0x140006014`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `420`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140005714`

## callees

- `0x1400050f8`
- `0x1400057f4`
- `0x140005e70`
- `0x140009590`
- `0x140012010`

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
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  wil::details *v14; // rcx
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(v11, &v18);
      v13 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_140019850, 57048226, (v13 >> 10) & 1, (v13 >> 11) & 1, &v17, 1, 0);
    v15 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_1400198B0, 45036792, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x140005e70  mov     [rsp-18h+arg_10], rbx
0x140005e75  mov     [rsp-18h+arg_0], rcx
0x140005e7a  push    rbp
0x140005e7b  push    rdi
0x140005e7c  push    r14
0x140005e7e  mov     rbp, rsp
0x140005e81  sub     rsp, 40h
0x140005e85  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x140005e8c  mov     rdi, rdx
0x140005e8f  test    rax, rax
0x140005e92  jz      short loc_140005EA7
0x140005e94  mov     edx, 3
0x140005e99  mov     ecx, 3667CA7h
0x140005e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ea3  mov     edx, eax
0x140005ea5  jmp     short loc_140005EB5
0x140005ea7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x140005eae  test    rax, rax
0x140005eb1  jnz     short loc_140005E94
0x140005eb3  xor     edx, edx
0x140005eb5  mov     r8d, edx
0x140005eb8  mov     qword ptr [rdi], 0
0x140005ebf  and     r8d, 0FFFFFF3Fh
0x140005ec6  mov     eax, edx
0x140005ec8  and     edx, 80h
0x140005ece  mov     ecx, r8d
0x140005ed1  and     ecx, 3
0x140005ed4  mov     r14d, 40h ; '@'
0x140005eda  shl     ecx, 2
0x140005edd  and     eax, r14d
0x140005ee0  or      ecx, eax
0x140005ee2  shl     ecx, 2
0x140005ee5  or      ecx, edx
0x140005ee7  shl     ecx, 3
0x140005eea  test    r8d, r8d
0x140005eed  jnz     short loc_140005EF7
0x140005eef  mov     edx, r14d
0x140005ef2  mov     r8d, r14d
0x140005ef5  jmp     short loc_140005F04
0x140005ef7  xor     edx, edx
0x140005ef9  cmp     r8d, 2
0x140005efd  cmovz   edx, r14d
0x140005f01  mov     r8d, edx
0x140005f04  mov     eax, ecx
0x140005f06  mov     ebx, 1
0x140005f0b  or      eax, r8d
0x140005f0e  or      ecx, edx
0x140005f10  mov     [rdi], eax
0x140005f12  bt      ecx, 0Ah
0x140005f16  jnb     short loc_140005F20
0x140005f18  cmp     ecx, 800h
0x140005f1e  jnb     short loc_140005F2B
0x140005f20  xor     dl, dl
0x140005f22  test    r14b, cl
0x140005f25  jz      loc_140005FEF
0x140005f2b  mov     rax, cs:Feature_ValLabTest__descriptor
0x140005f32  mov     r8d, [rax]
0x140005f35  test    r8b, 4
0x140005f39  jnz     short loc_140005F4E
0x140005f3b  lea     rdx, [rbp+arg_8]
0x140005f3f  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x140005f44  mov     rcx, [rax]
0x140005f47  mov     [rbp+arg_8], rcx
0x140005f4b  mov     r8d, ecx
0x140005f4e  xor     eax, eax
0x140005f50  mov     word ptr [rbp+arg_0+4], 3
0x140005f56  mov     r9d, r8d
0x140005f59  mov     [rsp+40h+var_10], eax
0x140005f5d  mov     dword ptr [rbp+arg_0], eax
0x140005f60  lea     rcx, qword_140019850
0x140005f67  shr     r9d, 0Bh
0x140005f6b  lea     rax, [rbp+arg_0]
0x140005f6f  shr     r8d, 0Ah
0x140005f73  and     r9d, ebx
0x140005f76  and     r8d, ebx
0x140005f79  mov     [rsp+40h+var_18], ebx
0x140005f7d  mov     edx, 3667CA2h
0x140005f82  mov     [rsp+40h+var_20], rax
0x140005f87  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140005f8c  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x140005f93  mov     r8d, [rax]
0x140005f96  test    r8b, 4
0x140005f9a  jnz     short loc_140005FAF
0x140005f9c  lea     rdx, [rbp+arg_8]
0x140005fa0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x140005fa5  mov     rcx, [rax]
0x140005fa8  mov     [rbp+arg_8], rcx
0x140005fac  mov     r8d, ecx
0x140005faf  xor     eax, eax
0x140005fb1  mov     word ptr [rbp+arg_0+4], 3
0x140005fb7  mov     r9d, r8d
0x140005fba  mov     [rsp+40h+var_10], eax
0x140005fbe  mov     dword ptr [rbp+arg_0], eax
0x140005fc1  lea     rcx, qword_1400198B0
0x140005fc8  shr     r9d, 0Bh
0x140005fcc  lea     rax, [rbp+arg_0]
0x140005fd0  shr     r8d, 0Ah
0x140005fd4  and     r9d, ebx
0x140005fd7  and     r8d, ebx
0x140005fda  mov     [rsp+40h+var_18], ebx
0x140005fde  mov     edx, 2AF34F8h
0x140005fe3  mov     [rsp+40h+var_20], rax
0x140005fe8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x140005fed  mov     dl, bl
0x140005fef  mov     eax, [rdi]
0x140005ff1  test    r14b, al
0x140005ff4  jz      short loc_140005FFA
0x140005ff6  test    dl, dl
0x140005ff8  jnz     short loc_140005FFC
0x140005ffa  xor     ebx, ebx
0x140005ffc  and     eax, 0FFFFFFFEh
0x140005fff  or      eax, ebx
0x140006001  mov     rbx, [rsp+40h+arg_10]
0x140006006  mov     [rdi], eax
0x140006008  mov     rax, rdi
0x14000600b  add     rsp, 40h
0x14000600f  pop     r14
0x140006011  pop     rdi
0x140006012  pop     rbp
0x140006013  retn
```
