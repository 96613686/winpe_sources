# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180037590`
- end: `0x18003765e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036e3c`

## callees

- `0x180037590`
- `0x180039d8c`
- `0x18003a28c`
- `0x18003bc40`

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
0x180037590  mov     [rsp+arg_0], rbx
0x180037595  mov     [rsp+arg_8], rsi
0x18003759a  push    rdi
0x18003759b  sub     rsp, 20h
0x18003759f  mov     ecx, 3667CA7h; this
0x1800375a4  mov     rbx, rdx
0x1800375a7  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800375ac  mov     edx, eax
0x1800375ae  mov     qword ptr [rbx], 0
0x1800375b5  and     edx, 0FFFFFF3Fh
0x1800375bb  mov     ecx, eax
0x1800375bd  and     eax, 80h
0x1800375c2  mov     r8d, edx
0x1800375c5  and     r8d, 3
0x1800375c9  mov     esi, 40h ; '@'
0x1800375ce  shl     r8d, 2
0x1800375d2  and     ecx, esi
0x1800375d4  or      r8d, ecx
0x1800375d7  shl     r8d, 2
0x1800375db  or      r8d, eax
0x1800375de  shl     r8d, 3
0x1800375e2  test    edx, edx
0x1800375e4  jnz     short loc_1800375EC
0x1800375e6  mov     ecx, esi
0x1800375e8  mov     edx, esi
0x1800375ea  jmp     short loc_1800375F6
0x1800375ec  xor     ecx, ecx
0x1800375ee  cmp     edx, 2
0x1800375f1  cmovz   ecx, esi
0x1800375f4  mov     edx, ecx
0x1800375f6  mov     eax, r8d
0x1800375f9  mov     edi, 1
0x1800375fe  or      eax, edx
0x180037600  or      r8d, ecx
0x180037603  mov     [rbx], eax
0x180037605  bt      r8d, 0Ah
0x18003760a  jnb     short loc_180037615
0x18003760c  cmp     r8d, 800h
0x180037613  jnb     short loc_18003761C
0x180037615  xor     cl, cl
0x180037617  test    sil, r8b
0x18003761a  jz      short loc_180037637
0x18003761c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValLabTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest> `wil::Feature<__WilFeatureTraits_Feature_ValLabTest>::GetImpl(void)'::`2'::impl
0x180037623  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037628  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetImpl(void)'::`2'::impl
0x18003762f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037634  mov     cl, dil
0x180037637  mov     eax, [rbx]
0x180037639  test    sil, al
0x18003763c  jz      short loc_180037642
0x18003763e  test    cl, cl
0x180037640  jnz     short loc_180037644
0x180037642  xor     edi, edi
0x180037644  mov     rsi, [rsp+28h+arg_8]
0x180037649  and     eax, 0FFFFFFFEh
0x18003764c  or      eax, edi
0x18003764e  mov     [rbx], eax
0x180037650  mov     rax, rbx
0x180037653  mov     rbx, [rsp+28h+arg_0]
0x180037658  add     rsp, 20h
0x18003765c  pop     rdi
0x18003765d  retn
```
