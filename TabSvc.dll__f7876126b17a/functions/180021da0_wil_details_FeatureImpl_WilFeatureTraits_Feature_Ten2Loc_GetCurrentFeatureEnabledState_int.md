# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180021da0`
- end: `0x180021eed`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `333`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800212f0`

## callees

- `0x180011c30`
- `0x18001a6e4`
- `0x180020e78`
- `0x180021da0`
- `0x180028b14`

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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, 3u, a3, a4);
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
    wil::details::ReportUsageToService(&qword_180041E80, 58599550, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
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
0x180021da0  mov     [rsp+arg_10], rbx
0x180021da5  mov     [rsp+arg_0], rcx
0x180021daa  push    rbp
0x180021dab  push    rsi
0x180021dac  push    rdi
0x180021dad  sub     rsp, 40h
0x180021db1  mov     rbx, rdx
0x180021db4  mov     ecx, 38419CAh; this
0x180021db9  mov     edx, 3; unsigned int
0x180021dbe  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180021dc3  mov     edx, eax
0x180021dc5  mov     qword ptr [rbx], 0
0x180021dcc  and     edx, 0FFFFFF3Fh
0x180021dd2  mov     ecx, eax
0x180021dd4  and     eax, 80h
0x180021dd9  mov     r8d, edx
0x180021ddc  and     r8d, 3
0x180021de0  mov     ebp, 40h ; '@'
0x180021de5  shl     r8d, 2
0x180021de9  and     ecx, ebp
0x180021deb  or      r8d, ecx
0x180021dee  shl     r8d, 2
0x180021df2  or      r8d, eax
0x180021df5  shl     r8d, 3
0x180021df9  test    edx, edx
0x180021dfb  jnz     short loc_180021E03
0x180021dfd  mov     ecx, ebp
0x180021dff  mov     edx, ebp
0x180021e01  jmp     short loc_180021E0D
0x180021e03  xor     ecx, ecx
0x180021e05  cmp     edx, 2
0x180021e08  cmovz   ecx, ebp
0x180021e0b  mov     edx, ecx
0x180021e0d  mov     eax, r8d
0x180021e10  mov     edi, 1
0x180021e15  or      eax, edx
0x180021e17  or      r8d, ecx
0x180021e1a  mov     [rbx], eax
0x180021e1c  bt      r8d, 0Ah
0x180021e21  jnb     short loc_180021E31
0x180021e23  cmp     r8d, 800h
0x180021e2a  jb      short loc_180021E31
0x180021e2c  mov     sil, dil
0x180021e2f  jmp     short loc_180021E3F
0x180021e31  xor     sil, sil
0x180021e34  xor     cl, cl
0x180021e36  test    bpl, r8b
0x180021e39  jz      loc_180021EC9
0x180021e3f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180021e46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180021e4b  test    al, al
0x180021e4d  jz      short loc_180021EBA
0x180021e4f  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180021e56  mov     r8d, [rax]
0x180021e59  test    r8b, 4
0x180021e5d  jnz     short loc_180021E74
0x180021e5f  lea     rdx, [rsp+58h+arg_8]
0x180021e64  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180021e69  mov     rcx, [rax]
0x180021e6c  mov     [rsp+58h+arg_8], rcx
0x180021e71  mov     r8d, ecx
0x180021e74  xor     eax, eax
0x180021e76  mov     word ptr [rsp+58h+arg_0+4], 3
0x180021e7d  mov     r9d, r8d
0x180021e80  mov     [rsp+58h+var_28], eax
0x180021e84  mov     dword ptr [rsp+58h+arg_0], eax
0x180021e88  lea     rcx, qword_180041E80
0x180021e8f  shr     r9d, 0Bh
0x180021e93  lea     rax, [rsp+58h+arg_0]
0x180021e98  shr     r8d, 0Ah
0x180021e9c  and     r9d, edi
0x180021e9f  and     r8d, edi
0x180021ea2  mov     [rsp+58h+var_30], edi
0x180021ea6  mov     edx, 37E287Eh
0x180021eab  mov     [rsp+58h+var_38], rax
0x180021eb0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180021eb5  mov     cl, dil
0x180021eb8  jmp     short loc_180021EBC
0x180021eba  xor     cl, cl
0x180021ebc  test    sil, sil
0x180021ebf  jz      short loc_180021EC9
0x180021ec1  test    cl, cl
0x180021ec3  jnz     short loc_180021EC9
0x180021ec5  btr     dword ptr [rbx], 0Ah
0x180021ec9  mov     eax, [rbx]
0x180021ecb  test    bpl, al
0x180021ece  jz      short loc_180021ED4
0x180021ed0  test    cl, cl
0x180021ed2  jnz     short loc_180021ED6
0x180021ed4  xor     edi, edi
0x180021ed6  and     eax, 0FFFFFFFEh
0x180021ed9  or      eax, edi
0x180021edb  mov     [rbx], eax
0x180021edd  mov     rax, rbx
0x180021ee0  mov     rbx, [rsp+58h+arg_10]
0x180021ee5  add     rsp, 40h
0x180021ee9  pop     rdi
0x180021eea  pop     rsi
0x180021eeb  pop     rbp
0x180021eec  retn
```
