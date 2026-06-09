# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180006244`
- end: `0x180006322`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800057c4`

## callees

- `0x180006244`
- `0x180008d28`
- `0x18000a544`
- `0x18000a970`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419DD, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl'::`2'::impl);
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
0x180006244  push    rbx
0x180006246  push    rbp
0x180006247  push    rsi
0x180006248  push    rdi
0x180006249  sub     rsp, 28h
0x18000624d  mov     ecx, 38419DDh; this
0x180006252  mov     rbx, rdx
0x180006255  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000625a  mov     edx, eax
0x18000625c  mov     qword ptr [rbx], 0
0x180006263  and     edx, 0FFFFFF3Fh
0x180006269  mov     ecx, eax
0x18000626b  and     eax, 80h
0x180006270  mov     r8d, edx
0x180006273  and     r8d, 3
0x180006277  mov     ebp, 40h ; '@'
0x18000627c  shl     r8d, 2
0x180006280  and     ecx, ebp
0x180006282  or      r8d, ecx
0x180006285  shl     r8d, 2
0x180006289  or      r8d, eax
0x18000628c  shl     r8d, 3
0x180006290  test    edx, edx
0x180006292  jnz     short loc_18000629A
0x180006294  mov     ecx, ebp
0x180006296  mov     edx, ebp
0x180006298  jmp     short loc_1800062A4
0x18000629a  xor     ecx, ecx
0x18000629c  cmp     edx, 2
0x18000629f  cmovz   ecx, ebp
0x1800062a2  mov     edx, ecx
0x1800062a4  mov     eax, r8d
0x1800062a7  mov     edi, 1
0x1800062ac  or      eax, edx
0x1800062ae  or      r8d, ecx
0x1800062b1  mov     [rbx], eax
0x1800062b3  bt      r8d, 0Ah
0x1800062b8  jnb     short loc_1800062C8
0x1800062ba  cmp     r8d, 800h
0x1800062c1  jb      short loc_1800062C8
0x1800062c3  mov     sil, dil
0x1800062c6  jmp     short loc_1800062D2
0x1800062c8  xor     sil, sil
0x1800062cb  xor     cl, cl
0x1800062cd  test    bpl, r8b
0x1800062d0  jz      short loc_180006302
0x1800062d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x1800062d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1800062de  test    al, al
0x1800062e0  jz      short loc_1800062F3
0x1800062e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetImpl(void)'::`2'::impl
0x1800062e9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800062ee  mov     cl, dil
0x1800062f1  jmp     short loc_1800062F5
0x1800062f3  xor     cl, cl
0x1800062f5  test    sil, sil
0x1800062f8  jz      short loc_180006302
0x1800062fa  test    cl, cl
0x1800062fc  jnz     short loc_180006302
0x1800062fe  btr     dword ptr [rbx], 0Ah
0x180006302  mov     eax, [rbx]
0x180006304  test    bpl, al
0x180006307  jz      short loc_18000630D
0x180006309  test    cl, cl
0x18000630b  jnz     short loc_18000630F
0x18000630d  xor     edi, edi
0x18000630f  and     eax, 0FFFFFFFEh
0x180006312  or      eax, edi
0x180006314  mov     [rbx], eax
0x180006316  mov     rax, rbx
0x180006319  add     rsp, 28h
0x18000631d  pop     rdi
0x18000631e  pop     rsi
0x18000631f  pop     rbp
0x180006320  pop     rbx
0x180006321  retn
```
