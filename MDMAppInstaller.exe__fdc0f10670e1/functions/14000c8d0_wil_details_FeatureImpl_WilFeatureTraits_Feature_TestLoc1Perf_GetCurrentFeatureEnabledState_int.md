# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c8d0`
- end: `0x14000c9b3`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c008`

## callees

- `0x14000c8d0`
- `0x14000fe10`
- `0x140011454`
- `0x140011bdc`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x14000c8d0  push    rbx
0x14000c8d2  push    rbp
0x14000c8d3  push    rsi
0x14000c8d4  push    rdi
0x14000c8d5  sub     rsp, 28h
0x14000c8d9  mov     rbx, rdx
0x14000c8dc  mov     ecx, 38419ACh; this
0x14000c8e1  mov     edx, 3; unsigned int
0x14000c8e6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c8eb  mov     edx, eax
0x14000c8ed  mov     qword ptr [rbx], 0
0x14000c8f4  and     edx, 0FFFFFF3Fh
0x14000c8fa  mov     ecx, eax
0x14000c8fc  and     eax, 80h
0x14000c901  mov     r8d, edx
0x14000c904  and     r8d, 3
0x14000c908  mov     ebp, 40h ; '@'
0x14000c90d  shl     r8d, 2
0x14000c911  and     ecx, ebp
0x14000c913  or      r8d, ecx
0x14000c916  shl     r8d, 2
0x14000c91a  or      r8d, eax
0x14000c91d  shl     r8d, 3
0x14000c921  test    edx, edx
0x14000c923  jnz     short loc_14000C92B
0x14000c925  mov     ecx, ebp
0x14000c927  mov     edx, ebp
0x14000c929  jmp     short loc_14000C935
0x14000c92b  xor     ecx, ecx
0x14000c92d  cmp     edx, 2
0x14000c930  cmovz   ecx, ebp
0x14000c933  mov     edx, ecx
0x14000c935  mov     eax, r8d
0x14000c938  mov     edi, 1
0x14000c93d  or      eax, edx
0x14000c93f  or      r8d, ecx
0x14000c942  mov     [rbx], eax
0x14000c944  bt      r8d, 0Ah
0x14000c949  jnb     short loc_14000C959
0x14000c94b  cmp     r8d, 800h
0x14000c952  jb      short loc_14000C959
0x14000c954  mov     sil, dil
0x14000c957  jmp     short loc_14000C963
0x14000c959  xor     sil, sil
0x14000c95c  xor     cl, cl
0x14000c95e  test    bpl, r8b
0x14000c961  jz      short loc_14000C993
0x14000c963  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x14000c96a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x14000c96f  test    al, al
0x14000c971  jz      short loc_14000C984
0x14000c973  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x14000c97a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000c97f  mov     cl, dil
0x14000c982  jmp     short loc_14000C986
0x14000c984  xor     cl, cl
0x14000c986  test    sil, sil
0x14000c989  jz      short loc_14000C993
0x14000c98b  test    cl, cl
0x14000c98d  jnz     short loc_14000C993
0x14000c98f  btr     dword ptr [rbx], 0Ah
0x14000c993  mov     eax, [rbx]
0x14000c995  test    bpl, al
0x14000c998  jz      short loc_14000C99E
0x14000c99a  test    cl, cl
0x14000c99c  jnz     short loc_14000C9A0
0x14000c99e  xor     edi, edi
0x14000c9a0  and     eax, 0FFFFFFFEh
0x14000c9a3  or      eax, edi
0x14000c9a5  mov     [rbx], eax
0x14000c9a7  mov     rax, rbx
0x14000c9aa  add     rsp, 28h
0x14000c9ae  pop     rdi
0x14000c9af  pop     rsi
0x14000c9b0  pop     rbp
0x14000c9b1  pop     rbx
0x14000c9b2  retn
```
