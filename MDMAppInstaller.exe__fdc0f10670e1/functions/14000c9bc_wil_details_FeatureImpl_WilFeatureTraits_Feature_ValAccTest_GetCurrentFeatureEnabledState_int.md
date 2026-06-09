# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c9bc`
- end: `0x14000ca8f`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `211`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c148`

## callees

- `0x14000c9bc`
- `0x14000fd08`
- `0x140010138`
- `0x140011454`

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
0x14000c9bc  mov     [rsp+arg_0], rbx
0x14000c9c1  mov     [rsp+arg_8], rsi
0x14000c9c6  push    rdi
0x14000c9c7  sub     rsp, 20h
0x14000c9cb  mov     rbx, rdx
0x14000c9ce  mov     ecx, 3667CA7h; this
0x14000c9d3  mov     edx, 3; unsigned int
0x14000c9d8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c9dd  mov     edx, eax
0x14000c9df  mov     qword ptr [rbx], 0
0x14000c9e6  and     edx, 0FFFFFF3Fh
0x14000c9ec  mov     ecx, eax
0x14000c9ee  and     eax, 80h
0x14000c9f3  mov     r8d, edx
0x14000c9f6  and     r8d, 3
0x14000c9fa  mov     esi, 40h ; '@'
0x14000c9ff  shl     r8d, 2
0x14000ca03  and     ecx, esi
0x14000ca05  or      r8d, ecx
0x14000ca08  shl     r8d, 2
0x14000ca0c  or      r8d, eax
0x14000ca0f  shl     r8d, 3
0x14000ca13  test    edx, edx
0x14000ca15  jnz     short loc_14000CA1D
0x14000ca17  mov     ecx, esi
0x14000ca19  mov     edx, esi
0x14000ca1b  jmp     short loc_14000CA27
0x14000ca1d  xor     ecx, ecx
0x14000ca1f  cmp     edx, 2
0x14000ca22  cmovz   ecx, esi
0x14000ca25  mov     edx, ecx
0x14000ca27  mov     eax, r8d
0x14000ca2a  mov     edi, 1
0x14000ca2f  or      eax, edx
0x14000ca31  or      r8d, ecx
0x14000ca34  mov     [rbx], eax
0x14000ca36  bt      r8d, 0Ah
0x14000ca3b  jnb     short loc_14000CA46
0x14000ca3d  cmp     r8d, 800h
0x14000ca44  jnb     short loc_14000CA4D
0x14000ca46  xor     cl, cl
0x14000ca48  test    sil, r8b
0x14000ca4b  jz      short loc_14000CA68
0x14000ca4d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x14000ca54  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000ca59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x14000ca60  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000ca65  mov     cl, dil
0x14000ca68  mov     eax, [rbx]
0x14000ca6a  test    sil, al
0x14000ca6d  jz      short loc_14000CA73
0x14000ca6f  test    cl, cl
0x14000ca71  jnz     short loc_14000CA75
0x14000ca73  xor     edi, edi
0x14000ca75  mov     rsi, [rsp+28h+arg_8]
0x14000ca7a  and     eax, 0FFFFFFFEh
0x14000ca7d  or      eax, edi
0x14000ca7f  mov     [rbx], eax
0x14000ca81  mov     rax, rbx
0x14000ca84  mov     rbx, [rsp+28h+arg_0]
0x14000ca89  add     rsp, 20h
0x14000ca8d  pop     rdi
0x14000ca8e  retn
```
