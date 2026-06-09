# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bf10`
- end: `0x18001bfde`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b65c`

## callees

- `0x1800162fc`
- `0x18001bf10`
- `0x18001c318`
- `0x18001c748`

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
0x18001bf10  mov     [rsp+arg_0], rbx
0x18001bf15  mov     [rsp+arg_8], rsi
0x18001bf1a  push    rdi
0x18001bf1b  sub     rsp, 20h
0x18001bf1f  mov     ecx, 3667CA7h; this
0x18001bf24  mov     rbx, rdx
0x18001bf27  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bf2c  mov     edx, eax
0x18001bf2e  mov     qword ptr [rbx], 0
0x18001bf35  and     edx, 0FFFFFF3Fh
0x18001bf3b  mov     ecx, eax
0x18001bf3d  and     eax, 80h
0x18001bf42  mov     r8d, edx
0x18001bf45  and     r8d, 3
0x18001bf49  mov     esi, 40h ; '@'
0x18001bf4e  shl     r8d, 2
0x18001bf52  and     ecx, esi
0x18001bf54  or      r8d, ecx
0x18001bf57  shl     r8d, 2
0x18001bf5b  or      r8d, eax
0x18001bf5e  shl     r8d, 3
0x18001bf62  test    edx, edx
0x18001bf64  jnz     short loc_18001BF6C
0x18001bf66  mov     ecx, esi
0x18001bf68  mov     edx, esi
0x18001bf6a  jmp     short loc_18001BF76
0x18001bf6c  xor     ecx, ecx
0x18001bf6e  cmp     edx, 2
0x18001bf71  cmovz   ecx, esi
0x18001bf74  mov     edx, ecx
0x18001bf76  mov     eax, r8d
0x18001bf79  mov     edi, 1
0x18001bf7e  or      eax, edx
0x18001bf80  or      r8d, ecx
0x18001bf83  mov     [rbx], eax
0x18001bf85  bt      r8d, 0Ah
0x18001bf8a  jnb     short loc_18001BF95
0x18001bf8c  cmp     r8d, 800h
0x18001bf93  jnb     short loc_18001BF9C
0x18001bf95  xor     cl, cl
0x18001bf97  test    sil, r8b
0x18001bf9a  jz      short loc_18001BFB7
0x18001bf9c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x18001bfa3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bfa8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x18001bfaf  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001bfb4  mov     cl, dil
0x18001bfb7  mov     eax, [rbx]
0x18001bfb9  test    sil, al
0x18001bfbc  jz      short loc_18001BFC2
0x18001bfbe  test    cl, cl
0x18001bfc0  jnz     short loc_18001BFC4
0x18001bfc2  xor     edi, edi
0x18001bfc4  mov     rsi, [rsp+28h+arg_8]
0x18001bfc9  and     eax, 0FFFFFFFEh
0x18001bfcc  or      eax, edi
0x18001bfce  mov     [rbx], eax
0x18001bfd0  mov     rax, rbx
0x18001bfd3  mov     rbx, [rsp+28h+arg_0]
0x18001bfd8  add     rsp, 20h
0x18001bfdc  pop     rdi
0x18001bfdd  retn
```
