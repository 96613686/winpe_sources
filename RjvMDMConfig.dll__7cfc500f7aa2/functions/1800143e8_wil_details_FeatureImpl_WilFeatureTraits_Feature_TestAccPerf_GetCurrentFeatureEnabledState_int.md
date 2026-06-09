# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800143e8`
- end: `0x1800144cc`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013794`

## callees

- `0x180011098`
- `0x1800143e8`
- `0x18001547c`
- `0x180015bec`

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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, 3u, a3, a4);
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
0x1800143e8  push    rbx
0x1800143ea  push    rbp
0x1800143eb  push    rsi
0x1800143ec  push    rdi
0x1800143ed  sub     rsp, 28h
0x1800143f1  mov     rbx, rdx
0x1800143f4  mov     ecx, 3667CADh; this
0x1800143f9  mov     edx, 3; unsigned int
0x1800143fe  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014403  mov     edx, eax
0x180014405  mov     qword ptr [rbx], 0
0x18001440c  and     edx, 0FFFFFF3Fh
0x180014412  mov     ecx, eax
0x180014414  and     eax, 80h
0x180014419  mov     r8d, edx
0x18001441c  and     r8d, 3
0x180014420  mov     ebp, 40h ; '@'
0x180014425  shl     r8d, 2
0x180014429  and     ecx, ebp
0x18001442b  or      r8d, ecx
0x18001442e  shl     r8d, 2
0x180014432  or      r8d, eax
0x180014435  shl     r8d, 3
0x180014439  test    edx, edx
0x18001443b  jnz     short loc_180014443
0x18001443d  mov     ecx, ebp
0x18001443f  mov     edx, ebp
0x180014441  jmp     short loc_18001444D
0x180014443  xor     ecx, ecx
0x180014445  cmp     edx, 2
0x180014448  cmovz   ecx, ebp
0x18001444b  mov     edx, ecx
0x18001444d  mov     eax, r8d
0x180014450  mov     edi, 1
0x180014455  or      eax, edx
0x180014457  or      r8d, ecx
0x18001445a  mov     [rbx], eax
0x18001445c  bt      r8d, 0Ah
0x180014461  jnb     short loc_180014471
0x180014463  cmp     r8d, 800h
0x18001446a  jb      short loc_180014471
0x18001446c  mov     sil, dil
0x18001446f  jmp     short loc_18001447B
0x180014471  xor     sil, sil
0x180014474  xor     cl, cl
0x180014476  test    bpl, r8b
0x180014479  jz      short loc_1800144AB
0x18001447b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180014482  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180014487  test    al, al
0x180014489  jz      short loc_18001449C
0x18001448b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x180014492  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014497  mov     cl, dil
0x18001449a  jmp     short loc_18001449E
0x18001449c  xor     cl, cl
0x18001449e  test    sil, sil
0x1800144a1  jz      short loc_1800144AB
0x1800144a3  test    cl, cl
0x1800144a5  jnz     short loc_1800144AB
0x1800144a7  btr     dword ptr [rbx], 0Ah
0x1800144ab  mov     eax, [rbx]
0x1800144ad  test    bpl, al
0x1800144b0  jz      short loc_1800144B6
0x1800144b2  test    cl, cl
0x1800144b4  jnz     short loc_1800144B8
0x1800144b6  xor     edi, edi
0x1800144b8  and     eax, 0FFFFFFFEh
0x1800144bb  or      eax, edi
0x1800144bd  mov     [rbx], eax
0x1800144bf  mov     rax, rbx
0x1800144c2  add     rsp, 28h
0x1800144c6  pop     rdi
0x1800144c7  pop     rsi
0x1800144c8  pop     rbp
0x1800144c9  pop     rbx
0x1800144ca  retn
```
