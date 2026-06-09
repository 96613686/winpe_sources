# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006328`
- end: `0x1800063f6`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800058f4`

## callees

- `0x180006328`
- `0x180008b18`
- `0x1800090e0`
- `0x18000a544`

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
0x180006328  mov     [rsp+arg_0], rbx
0x18000632d  mov     [rsp+arg_8], rsi
0x180006332  push    rdi
0x180006333  sub     rsp, 20h
0x180006337  mov     ecx, 3667CA7h; this
0x18000633c  mov     rbx, rdx
0x18000633f  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180006344  mov     edx, eax
0x180006346  mov     qword ptr [rbx], 0
0x18000634d  and     edx, 0FFFFFF3Fh
0x180006353  mov     ecx, eax
0x180006355  and     eax, 80h
0x18000635a  mov     r8d, edx
0x18000635d  and     r8d, 3
0x180006361  mov     esi, 40h ; '@'
0x180006366  shl     r8d, 2
0x18000636a  and     ecx, esi
0x18000636c  or      r8d, ecx
0x18000636f  shl     r8d, 2
0x180006373  or      r8d, eax
0x180006376  shl     r8d, 3
0x18000637a  test    edx, edx
0x18000637c  jnz     short loc_180006384
0x18000637e  mov     ecx, esi
0x180006380  mov     edx, esi
0x180006382  jmp     short loc_18000638E
0x180006384  xor     ecx, ecx
0x180006386  cmp     edx, 2
0x180006389  cmovz   ecx, esi
0x18000638c  mov     edx, ecx
0x18000638e  mov     eax, r8d
0x180006391  mov     edi, 1
0x180006396  or      eax, edx
0x180006398  or      r8d, ecx
0x18000639b  mov     [rbx], eax
0x18000639d  bt      r8d, 0Ah
0x1800063a2  jnb     short loc_1800063AD
0x1800063a4  cmp     r8d, 800h
0x1800063ab  jnb     short loc_1800063B4
0x1800063ad  xor     cl, cl
0x1800063af  test    sil, r8b
0x1800063b2  jz      short loc_1800063CF
0x1800063b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x1800063bb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800063c0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x1800063c7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800063cc  mov     cl, dil
0x1800063cf  mov     eax, [rbx]
0x1800063d1  test    sil, al
0x1800063d4  jz      short loc_1800063DA
0x1800063d6  test    cl, cl
0x1800063d8  jnz     short loc_1800063DC
0x1800063da  xor     edi, edi
0x1800063dc  mov     rsi, [rsp+28h+arg_8]
0x1800063e1  and     eax, 0FFFFFFFEh
0x1800063e4  or      eax, edi
0x1800063e6  mov     [rbx], eax
0x1800063e8  mov     rax, rbx
0x1800063eb  mov     rbx, [rsp+28h+arg_0]
0x1800063f0  add     rsp, 20h
0x1800063f4  pop     rdi
0x1800063f5  retn
```
