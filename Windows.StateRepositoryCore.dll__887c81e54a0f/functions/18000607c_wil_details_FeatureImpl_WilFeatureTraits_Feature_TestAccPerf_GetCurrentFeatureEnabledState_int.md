# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000607c`
- end: `0x18000615a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005564`

## callees

- `0x18000607c`
- `0x180008b9c`
- `0x18000a544`
- `0x18000aa60`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
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
0x18000607c  push    rbx
0x18000607e  push    rbp
0x18000607f  push    rsi
0x180006080  push    rdi
0x180006081  sub     rsp, 28h
0x180006085  mov     ecx, 3667CADh; this
0x18000608a  mov     rbx, rdx
0x18000608d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180006092  mov     edx, eax
0x180006094  mov     qword ptr [rbx], 0
0x18000609b  and     edx, 0FFFFFF3Fh
0x1800060a1  mov     ecx, eax
0x1800060a3  and     eax, 80h
0x1800060a8  mov     r8d, edx
0x1800060ab  and     r8d, 3
0x1800060af  mov     ebp, 40h ; '@'
0x1800060b4  shl     r8d, 2
0x1800060b8  and     ecx, ebp
0x1800060ba  or      r8d, ecx
0x1800060bd  shl     r8d, 2
0x1800060c1  or      r8d, eax
0x1800060c4  shl     r8d, 3
0x1800060c8  test    edx, edx
0x1800060ca  jnz     short loc_1800060D2
0x1800060cc  mov     ecx, ebp
0x1800060ce  mov     edx, ebp
0x1800060d0  jmp     short loc_1800060DC
0x1800060d2  xor     ecx, ecx
0x1800060d4  cmp     edx, 2
0x1800060d7  cmovz   ecx, ebp
0x1800060da  mov     edx, ecx
0x1800060dc  mov     eax, r8d
0x1800060df  mov     edi, 1
0x1800060e4  or      eax, edx
0x1800060e6  or      r8d, ecx
0x1800060e9  mov     [rbx], eax
0x1800060eb  bt      r8d, 0Ah
0x1800060f0  jnb     short loc_180006100
0x1800060f2  cmp     r8d, 800h
0x1800060f9  jb      short loc_180006100
0x1800060fb  mov     sil, dil
0x1800060fe  jmp     short loc_18000610A
0x180006100  xor     sil, sil
0x180006103  xor     cl, cl
0x180006105  test    bpl, r8b
0x180006108  jz      short loc_18000613A
0x18000610a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180006111  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180006116  test    al, al
0x180006118  jz      short loc_18000612B
0x18000611a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x180006121  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180006126  mov     cl, dil
0x180006129  jmp     short loc_18000612D
0x18000612b  xor     cl, cl
0x18000612d  test    sil, sil
0x180006130  jz      short loc_18000613A
0x180006132  test    cl, cl
0x180006134  jnz     short loc_18000613A
0x180006136  btr     dword ptr [rbx], 0Ah
0x18000613a  mov     eax, [rbx]
0x18000613c  test    bpl, al
0x18000613f  jz      short loc_180006145
0x180006141  test    cl, cl
0x180006143  jnz     short loc_180006147
0x180006145  xor     edi, edi
0x180006147  and     eax, 0FFFFFFFEh
0x18000614a  or      eax, edi
0x18000614c  mov     [rbx], eax
0x18000614e  mov     rax, rbx
0x180006151  add     rsp, 28h
0x180006155  pop     rdi
0x180006156  pop     rsi
0x180006157  pop     rbp
0x180006158  pop     rbx
0x180006159  retn
```
