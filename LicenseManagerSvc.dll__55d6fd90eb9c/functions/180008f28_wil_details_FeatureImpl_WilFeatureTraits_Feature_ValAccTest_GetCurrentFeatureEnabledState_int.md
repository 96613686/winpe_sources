# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008f28`
- end: `0x180008ff6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008bb8`

## callees

- `0x180008f28`
- `0x18000a4b0`
- `0x18000a640`
- `0x18000b0a4`

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
0x180008f28  mov     [rsp+arg_0], rbx
0x180008f2d  mov     [rsp+arg_8], rsi
0x180008f32  push    rdi
0x180008f33  sub     rsp, 20h
0x180008f37  mov     ecx, 3667CA7h; this
0x180008f3c  mov     rbx, rdx
0x180008f3f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008f44  mov     edx, eax
0x180008f46  mov     qword ptr [rbx], 0
0x180008f4d  and     edx, 0FFFFFF3Fh
0x180008f53  mov     ecx, eax
0x180008f55  and     eax, 80h
0x180008f5a  mov     r8d, edx
0x180008f5d  and     r8d, 3
0x180008f61  mov     esi, 40h ; '@'
0x180008f66  shl     r8d, 2
0x180008f6a  and     ecx, esi
0x180008f6c  or      r8d, ecx
0x180008f6f  shl     r8d, 2
0x180008f73  or      r8d, eax
0x180008f76  shl     r8d, 3
0x180008f7a  test    edx, edx
0x180008f7c  jnz     short loc_180008F84
0x180008f7e  mov     ecx, esi
0x180008f80  mov     edx, esi
0x180008f82  jmp     short loc_180008F8E
0x180008f84  xor     ecx, ecx
0x180008f86  cmp     edx, 2
0x180008f89  cmovz   ecx, esi
0x180008f8c  mov     edx, ecx
0x180008f8e  mov     eax, r8d
0x180008f91  mov     edi, 1
0x180008f96  or      eax, edx
0x180008f98  or      r8d, ecx
0x180008f9b  mov     [rbx], eax
0x180008f9d  bt      r8d, 0Ah
0x180008fa2  jnb     short loc_180008FAD
0x180008fa4  cmp     r8d, 800h
0x180008fab  jnb     short loc_180008FB4
0x180008fad  xor     cl, cl
0x180008faf  test    sil, r8b
0x180008fb2  jz      short loc_180008FCF
0x180008fb4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x180008fbb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180008fc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x180008fc7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180008fcc  mov     cl, dil
0x180008fcf  mov     eax, [rbx]
0x180008fd1  test    sil, al
0x180008fd4  jz      short loc_180008FDA
0x180008fd6  test    cl, cl
0x180008fd8  jnz     short loc_180008FDC
0x180008fda  xor     edi, edi
0x180008fdc  mov     rsi, [rsp+28h+arg_8]
0x180008fe1  and     eax, 0FFFFFFFEh
0x180008fe4  or      eax, edi
0x180008fe6  mov     [rbx], eax
0x180008fe8  mov     rax, rbx
0x180008feb  mov     rbx, [rsp+28h+arg_0]
0x180008ff0  add     rsp, 20h
0x180008ff4  pop     rdi
0x180008ff5  retn
```
