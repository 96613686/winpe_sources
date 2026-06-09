# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015b2c`
- end: `0x180015c74`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `328`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180015318`

## callees

- `0x18000cc60`
- `0x18000cfc0`
- `0x180015060`
- `0x180015b2c`
- `0x180017d98`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180027D28, 58599550, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180015b2c  mov     [rsp+arg_10], rbx
0x180015b31  mov     [rsp+arg_0], rcx
0x180015b36  push    rbp
0x180015b37  push    rsi
0x180015b38  push    rdi
0x180015b39  sub     rsp, 40h
0x180015b3d  mov     ecx, 38419CAh; this
0x180015b42  mov     rbx, rdx
0x180015b45  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015b4a  mov     edx, eax
0x180015b4c  mov     qword ptr [rbx], 0
0x180015b53  and     edx, 0FFFFFF3Fh
0x180015b59  mov     ecx, eax
0x180015b5b  and     eax, 80h
0x180015b60  mov     r8d, edx
0x180015b63  and     r8d, 3
0x180015b67  mov     ebp, 40h ; '@'
0x180015b6c  shl     r8d, 2
0x180015b70  and     ecx, ebp
0x180015b72  or      r8d, ecx
0x180015b75  shl     r8d, 2
0x180015b79  or      r8d, eax
0x180015b7c  shl     r8d, 3
0x180015b80  test    edx, edx
0x180015b82  jnz     short loc_180015B8A
0x180015b84  mov     ecx, ebp
0x180015b86  mov     edx, ebp
0x180015b88  jmp     short loc_180015B94
0x180015b8a  xor     ecx, ecx
0x180015b8c  cmp     edx, 2
0x180015b8f  cmovz   ecx, ebp
0x180015b92  mov     edx, ecx
0x180015b94  mov     eax, r8d
0x180015b97  mov     edi, 1
0x180015b9c  or      eax, edx
0x180015b9e  or      r8d, ecx
0x180015ba1  mov     [rbx], eax
0x180015ba3  bt      r8d, 0Ah
0x180015ba8  jnb     short loc_180015BB8
0x180015baa  cmp     r8d, 800h
0x180015bb1  jb      short loc_180015BB8
0x180015bb3  mov     sil, dil
0x180015bb6  jmp     short loc_180015BC6
0x180015bb8  xor     sil, sil
0x180015bbb  xor     cl, cl
0x180015bbd  test    bpl, r8b
0x180015bc0  jz      loc_180015C50
0x180015bc6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180015bcd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180015bd2  test    al, al
0x180015bd4  jz      short loc_180015C41
0x180015bd6  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180015bdd  mov     r8d, [rax]
0x180015be0  test    r8b, 4
0x180015be4  jnz     short loc_180015BFB
0x180015be6  lea     rdx, [rsp+58h+arg_8]
0x180015beb  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180015bf0  mov     rcx, [rax]
0x180015bf3  mov     [rsp+58h+arg_8], rcx
0x180015bf8  mov     r8d, ecx
0x180015bfb  xor     eax, eax
0x180015bfd  mov     word ptr [rsp+58h+arg_0+4], 3
0x180015c04  mov     r9d, r8d
0x180015c07  mov     [rsp+58h+var_28], eax
0x180015c0b  mov     dword ptr [rsp+58h+arg_0], eax
0x180015c0f  lea     rcx, qword_180027D28
0x180015c16  shr     r9d, 0Bh
0x180015c1a  lea     rax, [rsp+58h+arg_0]
0x180015c1f  shr     r8d, 0Ah
0x180015c23  and     r9d, edi
0x180015c26  and     r8d, edi
0x180015c29  mov     [rsp+58h+var_30], edi
0x180015c2d  mov     edx, 37E287Eh
0x180015c32  mov     [rsp+58h+var_38], rax
0x180015c37  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015c3c  mov     cl, dil
0x180015c3f  jmp     short loc_180015C43
0x180015c41  xor     cl, cl
0x180015c43  test    sil, sil
0x180015c46  jz      short loc_180015C50
0x180015c48  test    cl, cl
0x180015c4a  jnz     short loc_180015C50
0x180015c4c  btr     dword ptr [rbx], 0Ah
0x180015c50  mov     eax, [rbx]
0x180015c52  test    bpl, al
0x180015c55  jz      short loc_180015C5B
0x180015c57  test    cl, cl
0x180015c59  jnz     short loc_180015C5D
0x180015c5b  xor     edi, edi
0x180015c5d  and     eax, 0FFFFFFFEh
0x180015c60  or      eax, edi
0x180015c62  mov     [rbx], eax
0x180015c64  mov     rax, rbx
0x180015c67  mov     rbx, [rsp+58h+arg_10]
0x180015c6c  add     rsp, 40h
0x180015c70  pop     rdi
0x180015c71  pop     rsi
0x180015c72  pop     rbp
0x180015c73  retn
```
