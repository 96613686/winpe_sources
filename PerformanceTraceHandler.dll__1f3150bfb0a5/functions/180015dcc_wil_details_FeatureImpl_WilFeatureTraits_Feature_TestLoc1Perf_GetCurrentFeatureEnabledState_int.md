# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015dcc`
- end: `0x180015f14`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `328`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800154d8`

## callees

- `0x18000cc60`
- `0x18000cfc0`
- `0x180014f04`
- `0x180015dcc`
- `0x180017d5c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180027D38, 58599532, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180015dcc  mov     [rsp+arg_10], rbx
0x180015dd1  mov     [rsp+arg_0], rcx
0x180015dd6  push    rbp
0x180015dd7  push    rsi
0x180015dd8  push    rdi
0x180015dd9  sub     rsp, 40h
0x180015ddd  mov     ecx, 38419ACh; this
0x180015de2  mov     rbx, rdx
0x180015de5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015dea  mov     edx, eax
0x180015dec  mov     qword ptr [rbx], 0
0x180015df3  and     edx, 0FFFFFF3Fh
0x180015df9  mov     ecx, eax
0x180015dfb  and     eax, 80h
0x180015e00  mov     r8d, edx
0x180015e03  and     r8d, 3
0x180015e07  mov     ebp, 40h ; '@'
0x180015e0c  shl     r8d, 2
0x180015e10  and     ecx, ebp
0x180015e12  or      r8d, ecx
0x180015e15  shl     r8d, 2
0x180015e19  or      r8d, eax
0x180015e1c  shl     r8d, 3
0x180015e20  test    edx, edx
0x180015e22  jnz     short loc_180015E2A
0x180015e24  mov     ecx, ebp
0x180015e26  mov     edx, ebp
0x180015e28  jmp     short loc_180015E34
0x180015e2a  xor     ecx, ecx
0x180015e2c  cmp     edx, 2
0x180015e2f  cmovz   ecx, ebp
0x180015e32  mov     edx, ecx
0x180015e34  mov     eax, r8d
0x180015e37  mov     edi, 1
0x180015e3c  or      eax, edx
0x180015e3e  or      r8d, ecx
0x180015e41  mov     [rbx], eax
0x180015e43  bt      r8d, 0Ah
0x180015e48  jnb     short loc_180015E58
0x180015e4a  cmp     r8d, 800h
0x180015e51  jb      short loc_180015E58
0x180015e53  mov     sil, dil
0x180015e56  jmp     short loc_180015E66
0x180015e58  xor     sil, sil
0x180015e5b  xor     cl, cl
0x180015e5d  test    bpl, r8b
0x180015e60  jz      loc_180015EF0
0x180015e66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180015e6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180015e72  test    al, al
0x180015e74  jz      short loc_180015EE1
0x180015e76  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180015e7d  mov     r8d, [rax]
0x180015e80  test    r8b, 4
0x180015e84  jnz     short loc_180015E9B
0x180015e86  lea     rdx, [rsp+58h+arg_8]
0x180015e8b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180015e90  mov     rcx, [rax]
0x180015e93  mov     [rsp+58h+arg_8], rcx
0x180015e98  mov     r8d, ecx
0x180015e9b  xor     eax, eax
0x180015e9d  mov     word ptr [rsp+58h+arg_0+4], 3
0x180015ea4  mov     r9d, r8d
0x180015ea7  mov     [rsp+58h+var_28], eax
0x180015eab  mov     dword ptr [rsp+58h+arg_0], eax
0x180015eaf  lea     rcx, qword_180027D38
0x180015eb6  shr     r9d, 0Bh
0x180015eba  lea     rax, [rsp+58h+arg_0]
0x180015ebf  shr     r8d, 0Ah
0x180015ec3  and     r9d, edi
0x180015ec6  and     r8d, edi
0x180015ec9  mov     [rsp+58h+var_30], edi
0x180015ecd  mov     edx, 37E286Ch
0x180015ed2  mov     [rsp+58h+var_38], rax
0x180015ed7  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015edc  mov     cl, dil
0x180015edf  jmp     short loc_180015EE3
0x180015ee1  xor     cl, cl
0x180015ee3  test    sil, sil
0x180015ee6  jz      short loc_180015EF0
0x180015ee8  test    cl, cl
0x180015eea  jnz     short loc_180015EF0
0x180015eec  btr     dword ptr [rbx], 0Ah
0x180015ef0  mov     eax, [rbx]
0x180015ef2  test    bpl, al
0x180015ef5  jz      short loc_180015EFB
0x180015ef7  test    cl, cl
0x180015ef9  jnz     short loc_180015EFD
0x180015efb  xor     edi, edi
0x180015efd  and     eax, 0FFFFFFFEh
0x180015f00  or      eax, edi
0x180015f02  mov     [rbx], eax
0x180015f04  mov     rax, rbx
0x180015f07  mov     rbx, [rsp+58h+arg_10]
0x180015f0c  add     rsp, 40h
0x180015f10  pop     rdi
0x180015f11  pop     rsi
0x180015f12  pop     rbp
0x180015f13  retn
```
