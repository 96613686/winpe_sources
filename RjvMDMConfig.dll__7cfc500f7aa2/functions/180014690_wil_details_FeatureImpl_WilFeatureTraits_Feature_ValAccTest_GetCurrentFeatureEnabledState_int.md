# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014690`
- end: `0x180014764`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013b6c`

## callees

- `0x180011098`
- `0x180014690`
- `0x1800153f8`
- `0x180015948`

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
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, 3u, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (v12 = 0, (v11 & 0x40) != 0) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl'::`2'::impl);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl'::`2'::impl);
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
0x180014690  mov     [rsp+arg_0], rbx
0x180014695  mov     [rsp+arg_8], rsi
0x18001469a  push    rdi
0x18001469b  sub     rsp, 20h
0x18001469f  mov     rbx, rdx
0x1800146a2  mov     ecx, 3667CA7h; this
0x1800146a7  mov     edx, 3; unsigned int
0x1800146ac  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800146b1  mov     edx, eax
0x1800146b3  mov     qword ptr [rbx], 0
0x1800146ba  and     edx, 0FFFFFF3Fh
0x1800146c0  mov     ecx, eax
0x1800146c2  and     eax, 80h
0x1800146c7  mov     r8d, edx
0x1800146ca  and     r8d, 3
0x1800146ce  mov     esi, 40h ; '@'
0x1800146d3  shl     r8d, 2
0x1800146d7  and     ecx, esi
0x1800146d9  or      r8d, ecx
0x1800146dc  shl     r8d, 2
0x1800146e0  or      r8d, eax
0x1800146e3  shl     r8d, 3
0x1800146e7  test    edx, edx
0x1800146e9  jnz     short loc_1800146F1
0x1800146eb  mov     ecx, esi
0x1800146ed  mov     edx, esi
0x1800146ef  jmp     short loc_1800146FB
0x1800146f1  xor     ecx, ecx
0x1800146f3  cmp     edx, 2
0x1800146f6  cmovz   ecx, esi
0x1800146f9  mov     edx, ecx
0x1800146fb  mov     eax, r8d
0x1800146fe  mov     edi, 1
0x180014703  or      eax, edx
0x180014705  or      r8d, ecx
0x180014708  mov     [rbx], eax
0x18001470a  bt      r8d, 0Ah
0x18001470f  jnb     short loc_18001471A
0x180014711  cmp     r8d, 800h
0x180014718  jnb     short loc_180014721
0x18001471a  xor     cl, cl
0x18001471c  test    sil, r8b
0x18001471f  jz      short loc_18001473C
0x180014721  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x180014728  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001472d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x180014734  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014739  mov     cl, dil
0x18001473c  mov     eax, [rbx]
0x18001473e  test    sil, al
0x180014741  jz      short loc_180014747
0x180014743  test    cl, cl
0x180014745  jnz     short loc_180014749
0x180014747  xor     edi, edi
0x180014749  mov     rsi, [rsp+28h+arg_8]
0x18001474e  and     eax, 0FFFFFFFEh
0x180014751  or      eax, edi
0x180014753  mov     [rbx], eax
0x180014755  mov     rax, rbx
0x180014758  mov     rbx, [rsp+28h+arg_0]
0x18001475d  add     rsp, 20h
0x180014761  pop     rdi
0x180014762  retn
```
