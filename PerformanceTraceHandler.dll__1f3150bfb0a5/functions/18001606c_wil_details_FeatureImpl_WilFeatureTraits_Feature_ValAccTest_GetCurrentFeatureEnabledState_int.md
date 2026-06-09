# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001606c`
- end: `0x1800161f0`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `388`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180015698`

## callees

- `0x18000cc60`
- `0x18000cfc0`
- `0x180014c4c`
- `0x180015778`
- `0x18001606c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
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
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180027D98, 57048226, (v12 >> 10) & 1, (v12 >> 11) & 1, &v16, 1, 0);
    v14 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180027D58, 45036792, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001606c  mov     [rsp-18h+arg_10], rbx
0x180016071  mov     [rsp-18h+arg_0], rcx
0x180016076  push    rbp
0x180016077  push    rdi
0x180016078  push    r14
0x18001607a  mov     rbp, rsp
0x18001607d  sub     rsp, 40h
0x180016081  mov     ecx, 3667CA7h; this
0x180016086  mov     rdi, rdx
0x180016089  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001608e  mov     edx, eax
0x180016090  mov     qword ptr [rdi], 0
0x180016097  and     edx, 0FFFFFF3Fh
0x18001609d  mov     ecx, eax
0x18001609f  and     eax, 80h
0x1800160a4  mov     r8d, edx
0x1800160a7  and     r8d, 3
0x1800160ab  mov     r14d, 40h ; '@'
0x1800160b1  shl     r8d, 2
0x1800160b5  and     ecx, r14d
0x1800160b8  or      r8d, ecx
0x1800160bb  shl     r8d, 2
0x1800160bf  or      r8d, eax
0x1800160c2  shl     r8d, 3
0x1800160c6  test    edx, edx
0x1800160c8  jnz     short loc_1800160D2
0x1800160ca  mov     ecx, r14d
0x1800160cd  mov     edx, r14d
0x1800160d0  jmp     short loc_1800160DD
0x1800160d2  xor     ecx, ecx
0x1800160d4  cmp     edx, 2
0x1800160d7  cmovz   ecx, r14d
0x1800160db  mov     edx, ecx
0x1800160dd  mov     eax, r8d
0x1800160e0  mov     ebx, 1
0x1800160e5  or      eax, edx
0x1800160e7  or      r8d, ecx
0x1800160ea  mov     [rdi], eax
0x1800160ec  bt      r8d, 0Ah
0x1800160f1  jnb     short loc_1800160FC
0x1800160f3  cmp     r8d, 800h
0x1800160fa  jnb     short loc_180016107
0x1800160fc  xor     cl, cl
0x1800160fe  test    r14b, r8b
0x180016101  jz      loc_1800161CB
0x180016107  mov     rax, cs:Feature_ValLabTest__descriptor
0x18001610e  mov     r8d, [rax]
0x180016111  test    r8b, 4
0x180016115  jnz     short loc_18001612A
0x180016117  lea     rdx, [rbp+arg_8]
0x18001611b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180016120  mov     rcx, [rax]
0x180016123  mov     [rbp+arg_8], rcx
0x180016127  mov     r8d, ecx
0x18001612a  xor     eax, eax
0x18001612c  mov     word ptr [rbp+arg_0+4], 3
0x180016132  mov     r9d, r8d
0x180016135  mov     [rsp+40h+var_10], eax
0x180016139  mov     dword ptr [rbp+arg_0], eax
0x18001613c  lea     rcx, qword_180027D98
0x180016143  shr     r9d, 0Bh
0x180016147  lea     rax, [rbp+arg_0]
0x18001614b  shr     r8d, 0Ah
0x18001614f  and     r9d, ebx
0x180016152  and     r8d, ebx
0x180016155  mov     [rsp+40h+var_18], ebx
0x180016159  mov     edx, 3667CA2h
0x18001615e  mov     [rsp+40h+var_20], rax
0x180016163  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180016168  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18001616f  mov     r8d, [rax]
0x180016172  test    r8b, 4
0x180016176  jnz     short loc_18001618B
0x180016178  lea     rdx, [rbp+arg_8]
0x18001617c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x180016181  mov     rcx, [rax]
0x180016184  mov     [rbp+arg_8], rcx
0x180016188  mov     r8d, ecx
0x18001618b  xor     eax, eax
0x18001618d  mov     word ptr [rbp+arg_0+4], 3
0x180016193  mov     r9d, r8d
0x180016196  mov     [rsp+40h+var_10], eax
0x18001619a  mov     dword ptr [rbp+arg_0], eax
0x18001619d  lea     rcx, qword_180027D58
0x1800161a4  shr     r9d, 0Bh
0x1800161a8  lea     rax, [rbp+arg_0]
0x1800161ac  shr     r8d, 0Ah
0x1800161b0  and     r9d, ebx
0x1800161b3  and     r8d, ebx
0x1800161b6  mov     [rsp+40h+var_18], ebx
0x1800161ba  mov     edx, 2AF34F8h
0x1800161bf  mov     [rsp+40h+var_20], rax
0x1800161c4  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800161c9  mov     cl, bl
0x1800161cb  mov     eax, [rdi]
0x1800161cd  test    r14b, al
0x1800161d0  jz      short loc_1800161D6
0x1800161d2  test    cl, cl
0x1800161d4  jnz     short loc_1800161D8
0x1800161d6  xor     ebx, ebx
0x1800161d8  and     eax, 0FFFFFFFEh
0x1800161db  or      eax, ebx
0x1800161dd  mov     rbx, [rsp+40h+arg_10]
0x1800161e2  mov     [rdi], eax
0x1800161e4  mov     rax, rdi
0x1800161e7  add     rsp, 40h
0x1800161eb  pop     r14
0x1800161ed  pop     rdi
0x1800161ee  pop     rbp
0x1800161ef  retn
```
