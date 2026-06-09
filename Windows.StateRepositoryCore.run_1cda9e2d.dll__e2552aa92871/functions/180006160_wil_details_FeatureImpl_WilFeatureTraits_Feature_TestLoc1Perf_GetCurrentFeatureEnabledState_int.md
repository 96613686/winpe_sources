# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006160`
- end: `0x18000623e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005694`

## callees

- `0x180006160`
- `0x180008c20`
- `0x18000a544`
- `0x18000a9ac`

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
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(&`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x180006160  push    rbx
0x180006162  push    rbp
0x180006163  push    rsi
0x180006164  push    rdi
0x180006165  sub     rsp, 28h
0x180006169  mov     ecx, 38419ACh; this
0x18000616e  mov     rbx, rdx
0x180006171  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180006176  mov     edx, eax
0x180006178  mov     qword ptr [rbx], 0
0x18000617f  and     edx, 0FFFFFF3Fh
0x180006185  mov     ecx, eax
0x180006187  and     eax, 80h
0x18000618c  mov     r8d, edx
0x18000618f  and     r8d, 3
0x180006193  mov     ebp, 40h ; '@'
0x180006198  shl     r8d, 2
0x18000619c  and     ecx, ebp
0x18000619e  or      r8d, ecx
0x1800061a1  shl     r8d, 2
0x1800061a5  or      r8d, eax
0x1800061a8  shl     r8d, 3
0x1800061ac  test    edx, edx
0x1800061ae  jnz     short loc_1800061B6
0x1800061b0  mov     ecx, ebp
0x1800061b2  mov     edx, ebp
0x1800061b4  jmp     short loc_1800061C0
0x1800061b6  xor     ecx, ecx
0x1800061b8  cmp     edx, 2
0x1800061bb  cmovz   ecx, ebp
0x1800061be  mov     edx, ecx
0x1800061c0  mov     eax, r8d
0x1800061c3  mov     edi, 1
0x1800061c8  or      eax, edx
0x1800061ca  or      r8d, ecx
0x1800061cd  mov     [rbx], eax
0x1800061cf  bt      r8d, 0Ah
0x1800061d4  jnb     short loc_1800061E4
0x1800061d6  cmp     r8d, 800h
0x1800061dd  jb      short loc_1800061E4
0x1800061df  mov     sil, dil
0x1800061e2  jmp     short loc_1800061EE
0x1800061e4  xor     sil, sil
0x1800061e7  xor     cl, cl
0x1800061e9  test    bpl, r8b
0x1800061ec  jz      short loc_18000621E
0x1800061ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x1800061f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x1800061fa  test    al, al
0x1800061fc  jz      short loc_18000620F
0x1800061fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x180006205  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000620a  mov     cl, dil
0x18000620d  jmp     short loc_180006211
0x18000620f  xor     cl, cl
0x180006211  test    sil, sil
0x180006214  jz      short loc_18000621E
0x180006216  test    cl, cl
0x180006218  jnz     short loc_18000621E
0x18000621a  btr     dword ptr [rbx], 0Ah
0x18000621e  mov     eax, [rbx]
0x180006220  test    bpl, al
0x180006223  jz      short loc_180006229
0x180006225  test    cl, cl
0x180006227  jnz     short loc_18000622B
0x180006229  xor     edi, edi
0x18000622b  and     eax, 0FFFFFFFEh
0x18000622e  or      eax, edi
0x180006230  mov     [rbx], eax
0x180006232  mov     rax, rbx
0x180006235  add     rsp, 28h
0x180006239  pop     rdi
0x18000623a  pop     rsi
0x18000623b  pop     rbp
0x18000623c  pop     rbx
0x18000623d  retn
```
