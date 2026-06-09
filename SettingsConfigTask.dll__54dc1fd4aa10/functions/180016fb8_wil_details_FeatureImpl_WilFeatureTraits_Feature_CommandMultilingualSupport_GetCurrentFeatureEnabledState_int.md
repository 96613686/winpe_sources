# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180016fb8`
- end: `0x180017096`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014e84`

## callees

- `0x18000aa64`
- `0x180016fb8`
- `0x18001b434`
- `0x18001cbe0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  int v10; // ecx
  __int16 v11; // r8
  int v12; // edi
  char v13; // si
  char v14; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38544ED, 3u, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 )
  {
    if ( v6 == 2 )
      v8 = 64;
    v10 = v9 | v8;
  }
  else
  {
    v10 = v9;
  }
  v11 = v8 | v9;
  *(_DWORD *)a2 = v10;
  v12 = 1;
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_15;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53427769>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
    v14 = 1;
  }
  else
  {
    v14 = 0;
  }
  if ( v13 && !v14 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_15:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v14 )
    v12 = 0;
  *(_DWORD *)a2 = v12 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180016fb8  push    rbx
0x180016fba  push    rbp
0x180016fbb  push    rsi
0x180016fbc  push    rdi
0x180016fbd  sub     rsp, 28h
0x180016fc1  mov     rbx, rdx
0x180016fc4  mov     ecx, 38544EDh; this
0x180016fc9  mov     edx, 3; unsigned int
0x180016fce  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180016fd3  mov     edx, eax
0x180016fd5  mov     qword ptr [rbx], 0
0x180016fdc  mov     ecx, eax
0x180016fde  and     edx, 0FFFFFF3Fh
0x180016fe4  and     eax, 80h
0x180016fe9  mov     r8d, edx
0x180016fec  and     r8d, 3
0x180016ff0  mov     ebp, 40h ; '@'
0x180016ff5  shl     r8d, 2
0x180016ff9  and     ecx, ebp
0x180016ffb  or      r8d, ecx
0x180016ffe  shl     r8d, 2
0x180017002  or      r8d, eax
0x180017005  xor     eax, eax
0x180017007  shl     r8d, 3
0x18001700b  test    edx, edx
0x18001700d  jnz     short loc_180017014
0x18001700f  mov     ecx, r8d
0x180017012  jmp     short loc_18001701F
0x180017014  cmp     edx, 2
0x180017017  cmovz   eax, ebp
0x18001701a  mov     ecx, eax
0x18001701c  or      ecx, r8d
0x18001701f  or      r8d, eax
0x180017022  mov     [rbx], ecx
0x180017024  mov     ecx, 0C00h
0x180017029  mov     eax, r8d
0x18001702c  and     eax, ecx
0x18001702e  mov     edi, 1
0x180017033  cmp     eax, ecx
0x180017035  jnz     short loc_18001703C
0x180017037  mov     sil, dil
0x18001703a  jmp     short loc_180017046
0x18001703c  xor     sil, sil
0x18001703f  xor     cl, cl
0x180017041  test    bpl, r8b
0x180017044  jz      short loc_180017076
0x180017046  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53427769@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769> `wil::Feature<__WilFeatureTraits_Feature_53427769>::GetImpl(void)'::`2'::impl
0x18001704d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53427769@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53427769>::__private_IsEnabled(wil::ReportingKind)
0x180017052  test    al, al
0x180017054  jz      short loc_180017067
0x180017056  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x18001705d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017062  mov     cl, dil
0x180017065  jmp     short loc_180017069
0x180017067  xor     cl, cl
0x180017069  test    sil, sil
0x18001706c  jz      short loc_180017076
0x18001706e  test    cl, cl
0x180017070  jnz     short loc_180017076
0x180017072  btr     dword ptr [rbx], 0Ah
0x180017076  mov     eax, [rbx]
0x180017078  test    bpl, al
0x18001707b  jz      short loc_180017081
0x18001707d  test    cl, cl
0x18001707f  jnz     short loc_180017083
0x180017081  xor     edi, edi
0x180017083  and     eax, 0FFFFFFFEh
0x180017086  or      eax, edi
0x180017088  mov     [rbx], eax
0x18001708a  mov     rax, rbx
0x18001708d  add     rsp, 28h
0x180017091  pop     rdi
0x180017092  pop     rsi
0x180017093  pop     rbp
0x180017094  pop     rbx
0x180017095  retn
```
