# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800144d4`
- end: `0x1800145b8`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800138dc`

## callees

- `0x180011098`
- `0x1800144d4`
- `0x180015500`
- `0x180015b38`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x1800144d4  push    rbx
0x1800144d6  push    rbp
0x1800144d7  push    rsi
0x1800144d8  push    rdi
0x1800144d9  sub     rsp, 28h
0x1800144dd  mov     rbx, rdx
0x1800144e0  mov     ecx, 38419ACh; this
0x1800144e5  mov     edx, 3; unsigned int
0x1800144ea  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800144ef  mov     edx, eax
0x1800144f1  mov     qword ptr [rbx], 0
0x1800144f8  and     edx, 0FFFFFF3Fh
0x1800144fe  mov     ecx, eax
0x180014500  and     eax, 80h
0x180014505  mov     r8d, edx
0x180014508  and     r8d, 3
0x18001450c  mov     ebp, 40h ; '@'
0x180014511  shl     r8d, 2
0x180014515  and     ecx, ebp
0x180014517  or      r8d, ecx
0x18001451a  shl     r8d, 2
0x18001451e  or      r8d, eax
0x180014521  shl     r8d, 3
0x180014525  test    edx, edx
0x180014527  jnz     short loc_18001452F
0x180014529  mov     ecx, ebp
0x18001452b  mov     edx, ebp
0x18001452d  jmp     short loc_180014539
0x18001452f  xor     ecx, ecx
0x180014531  cmp     edx, 2
0x180014534  cmovz   ecx, ebp
0x180014537  mov     edx, ecx
0x180014539  mov     eax, r8d
0x18001453c  mov     edi, 1
0x180014541  or      eax, edx
0x180014543  or      r8d, ecx
0x180014546  mov     [rbx], eax
0x180014548  bt      r8d, 0Ah
0x18001454d  jnb     short loc_18001455D
0x18001454f  cmp     r8d, 800h
0x180014556  jb      short loc_18001455D
0x180014558  mov     sil, dil
0x18001455b  jmp     short loc_180014567
0x18001455d  xor     sil, sil
0x180014560  xor     cl, cl
0x180014562  test    bpl, r8b
0x180014565  jz      short loc_180014597
0x180014567  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001456e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180014573  test    al, al
0x180014575  jz      short loc_180014588
0x180014577  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x18001457e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014583  mov     cl, dil
0x180014586  jmp     short loc_18001458A
0x180014588  xor     cl, cl
0x18001458a  test    sil, sil
0x18001458d  jz      short loc_180014597
0x18001458f  test    cl, cl
0x180014591  jnz     short loc_180014597
0x180014593  btr     dword ptr [rbx], 0Ah
0x180014597  mov     eax, [rbx]
0x180014599  test    bpl, al
0x18001459c  jz      short loc_1800145A2
0x18001459e  test    cl, cl
0x1800145a0  jnz     short loc_1800145A4
0x1800145a2  xor     edi, edi
0x1800145a4  and     eax, 0FFFFFFFEh
0x1800145a7  or      eax, edi
0x1800145a9  mov     [rbx], eax
0x1800145ab  mov     rax, rbx
0x1800145ae  add     rsp, 28h
0x1800145b2  pop     rdi
0x1800145b3  pop     rsi
0x1800145b4  pop     rbp
0x1800145b5  pop     rbx
0x1800145b6  retn
```
