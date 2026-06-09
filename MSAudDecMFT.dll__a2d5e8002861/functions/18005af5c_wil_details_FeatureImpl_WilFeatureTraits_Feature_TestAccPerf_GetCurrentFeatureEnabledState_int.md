# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18005af5c`
- end: `0x18005b0a5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18005a4a8`

## callees

- `0x180048d90`
- `0x18004c07c`
- `0x180059918`
- `0x18005af5c`
- `0x18005ccc4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
  __int64 v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v18 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
                         v14,
                         &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_1800E5DE0,
      0x2AF34FDu,
      (v15 >> 10) & 1,
      (v15 >> 11) & 1,
      (__int64)&v17,
      1u,
      0);
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
0x18005af5c  mov     [rsp+arg_10], rbx
0x18005af61  mov     [rsp+arg_0], rcx
0x18005af66  push    rbp
0x18005af67  push    rsi
0x18005af68  push    rdi
0x18005af69  sub     rsp, 40h
0x18005af6d  mov     ecx, 3667CADh; this
0x18005af72  mov     rbx, rdx
0x18005af75  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18005af7a  mov     edx, eax
0x18005af7c  mov     qword ptr [rbx], 0
0x18005af83  and     edx, 0FFFFFF3Fh
0x18005af89  mov     ecx, eax
0x18005af8b  and     eax, 80h
0x18005af90  mov     r8d, edx
0x18005af93  and     r8d, 3
0x18005af97  mov     ebp, 40h ; '@'
0x18005af9c  shl     r8d, 2
0x18005afa0  and     ecx, ebp
0x18005afa2  or      r8d, ecx
0x18005afa5  shl     r8d, 2
0x18005afa9  or      r8d, eax
0x18005afac  shl     r8d, 3
0x18005afb0  test    edx, edx
0x18005afb2  jnz     short loc_18005AFBA
0x18005afb4  mov     ecx, ebp
0x18005afb6  mov     edx, ebp
0x18005afb8  jmp     short loc_18005AFC4
0x18005afba  xor     ecx, ecx
0x18005afbc  cmp     edx, 2
0x18005afbf  cmovz   ecx, ebp
0x18005afc2  mov     edx, ecx
0x18005afc4  mov     eax, r8d
0x18005afc7  mov     edi, 1
0x18005afcc  or      eax, edx
0x18005afce  or      r8d, ecx
0x18005afd1  mov     [rbx], eax
0x18005afd3  bt      r8d, 0Ah
0x18005afd8  jnb     short loc_18005AFE8
0x18005afda  cmp     r8d, 800h
0x18005afe1  jb      short loc_18005AFE8
0x18005afe3  mov     sil, dil
0x18005afe6  jmp     short loc_18005AFF6
0x18005afe8  xor     sil, sil
0x18005afeb  xor     cl, cl
0x18005afed  test    bpl, r8b
0x18005aff0  jz      loc_18005B080
0x18005aff6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x18005affd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x18005b002  test    al, al
0x18005b004  jz      short loc_18005B071
0x18005b006  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18005b00d  mov     r8d, [rax]
0x18005b010  test    r8b, 4
0x18005b014  jnz     short loc_18005B02B
0x18005b016  lea     rdx, [rsp+58h+arg_8]
0x18005b01b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18005b020  mov     rcx, [rax]
0x18005b023  mov     [rsp+58h+arg_8], rcx
0x18005b028  mov     r8d, ecx
0x18005b02b  xor     eax, eax
0x18005b02d  mov     word ptr [rsp+58h+arg_0+4], 3
0x18005b034  mov     r9d, r8d
0x18005b037  mov     [rsp+58h+var_28], eax
0x18005b03b  mov     dword ptr [rsp+58h+arg_0], eax
0x18005b03f  lea     rcx, qword_1800E5DE0
0x18005b046  shr     r9d, 0Bh
0x18005b04a  lea     rax, [rsp+58h+arg_0]
0x18005b04f  shr     r8d, 0Ah
0x18005b053  and     r9d, edi
0x18005b056  and     r8d, edi
0x18005b059  mov     [rsp+58h+var_30], edi
0x18005b05d  mov     edx, 2AF34FDh
0x18005b062  mov     [rsp+58h+var_38], rax
0x18005b067  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18005b06c  mov     cl, dil
0x18005b06f  jmp     short loc_18005B073
0x18005b071  xor     cl, cl
0x18005b073  test    sil, sil
0x18005b076  jz      short loc_18005B080
0x18005b078  test    cl, cl
0x18005b07a  jnz     short loc_18005B080
0x18005b07c  btr     dword ptr [rbx], 0Ah
0x18005b080  mov     eax, [rbx]
0x18005b082  test    bpl, al
0x18005b085  jz      short loc_18005B08B
0x18005b087  test    cl, cl
0x18005b089  jnz     short loc_18005B08D
0x18005b08b  xor     edi, edi
0x18005b08d  and     eax, 0FFFFFFFEh
0x18005b090  or      eax, edi
0x18005b092  mov     [rbx], eax
0x18005b094  mov     rax, rbx
0x18005b097  mov     rbx, [rsp+58h+arg_10]
0x18005b09c  add     rsp, 40h
0x18005b0a0  pop     rdi
0x18005b0a1  pop     rsi
0x18005b0a2  pop     rbp
0x18005b0a3  retn
```
