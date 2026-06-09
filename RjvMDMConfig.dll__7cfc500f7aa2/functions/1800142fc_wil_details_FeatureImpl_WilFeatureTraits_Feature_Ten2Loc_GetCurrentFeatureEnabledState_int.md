# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800142fc`
- end: `0x1800143e0`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001364c`

## callees

- `0x180011098`
- `0x1800142fc`
- `0x180015584`
- `0x180015b74`

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
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800142fc  push    rbx
0x1800142fe  push    rbp
0x1800142ff  push    rsi
0x180014300  push    rdi
0x180014301  sub     rsp, 28h
0x180014305  mov     rbx, rdx
0x180014308  mov     ecx, 38419CAh; this
0x18001430d  mov     edx, 3; unsigned int
0x180014312  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014317  mov     edx, eax
0x180014319  mov     qword ptr [rbx], 0
0x180014320  and     edx, 0FFFFFF3Fh
0x180014326  mov     ecx, eax
0x180014328  and     eax, 80h
0x18001432d  mov     r8d, edx
0x180014330  and     r8d, 3
0x180014334  mov     ebp, 40h ; '@'
0x180014339  shl     r8d, 2
0x18001433d  and     ecx, ebp
0x18001433f  or      r8d, ecx
0x180014342  shl     r8d, 2
0x180014346  or      r8d, eax
0x180014349  shl     r8d, 3
0x18001434d  test    edx, edx
0x18001434f  jnz     short loc_180014357
0x180014351  mov     ecx, ebp
0x180014353  mov     edx, ebp
0x180014355  jmp     short loc_180014361
0x180014357  xor     ecx, ecx
0x180014359  cmp     edx, 2
0x18001435c  cmovz   ecx, ebp
0x18001435f  mov     edx, ecx
0x180014361  mov     eax, r8d
0x180014364  mov     edi, 1
0x180014369  or      eax, edx
0x18001436b  or      r8d, ecx
0x18001436e  mov     [rbx], eax
0x180014370  bt      r8d, 0Ah
0x180014375  jnb     short loc_180014385
0x180014377  cmp     r8d, 800h
0x18001437e  jb      short loc_180014385
0x180014380  mov     sil, dil
0x180014383  jmp     short loc_18001438F
0x180014385  xor     sil, sil
0x180014388  xor     cl, cl
0x18001438a  test    bpl, r8b
0x18001438d  jz      short loc_1800143BF
0x18001438f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180014396  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18001439b  test    al, al
0x18001439d  jz      short loc_1800143B0
0x18001439f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x1800143a6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800143ab  mov     cl, dil
0x1800143ae  jmp     short loc_1800143B2
0x1800143b0  xor     cl, cl
0x1800143b2  test    sil, sil
0x1800143b5  jz      short loc_1800143BF
0x1800143b7  test    cl, cl
0x1800143b9  jnz     short loc_1800143BF
0x1800143bb  btr     dword ptr [rbx], 0Ah
0x1800143bf  mov     eax, [rbx]
0x1800143c1  test    bpl, al
0x1800143c4  jz      short loc_1800143CA
0x1800143c6  test    cl, cl
0x1800143c8  jnz     short loc_1800143CC
0x1800143ca  xor     edi, edi
0x1800143cc  and     eax, 0FFFFFFFEh
0x1800143cf  or      eax, edi
0x1800143d1  mov     [rbx], eax
0x1800143d3  mov     rax, rbx
0x1800143d6  add     rsp, 28h
0x1800143da  pop     rdi
0x1800143db  pop     rsi
0x1800143dc  pop     rbp
0x1800143dd  pop     rbx
0x1800143de  retn
```
