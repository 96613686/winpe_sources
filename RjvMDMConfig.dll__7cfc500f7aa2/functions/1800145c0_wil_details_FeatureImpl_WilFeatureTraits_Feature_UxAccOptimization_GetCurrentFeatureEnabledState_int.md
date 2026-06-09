# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800145c0`
- end: `0x180014688`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013a24`

## callees

- `0x180011098`
- `0x1800145c0`
- `0x180015608`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, 3u, a3, a4);
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
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl'::`2'::impl);
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
0x1800145c0  mov     [rsp+arg_0], rbx
0x1800145c5  mov     [rsp+arg_8], rsi
0x1800145ca  push    rdi
0x1800145cb  sub     rsp, 20h
0x1800145cf  mov     rbx, rdx
0x1800145d2  mov     ecx, 2E30A37h; this
0x1800145d7  mov     edx, 3; unsigned int
0x1800145dc  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800145e1  mov     edx, eax
0x1800145e3  mov     qword ptr [rbx], 0
0x1800145ea  and     edx, 0FFFFFF3Fh
0x1800145f0  mov     ecx, eax
0x1800145f2  and     eax, 80h
0x1800145f7  mov     r8d, edx
0x1800145fa  and     r8d, 3
0x1800145fe  mov     esi, 40h ; '@'
0x180014603  shl     r8d, 2
0x180014607  and     ecx, esi
0x180014609  or      r8d, ecx
0x18001460c  shl     r8d, 2
0x180014610  or      r8d, eax
0x180014613  shl     r8d, 3
0x180014617  test    edx, edx
0x180014619  jnz     short loc_180014621
0x18001461b  mov     ecx, esi
0x18001461d  mov     edx, esi
0x18001461f  jmp     short loc_18001462B
0x180014621  xor     ecx, ecx
0x180014623  cmp     edx, 2
0x180014626  cmovz   ecx, esi
0x180014629  mov     edx, ecx
0x18001462b  mov     eax, r8d
0x18001462e  mov     edi, 1
0x180014633  or      eax, edx
0x180014635  or      r8d, ecx
0x180014638  mov     [rbx], eax
0x18001463a  bt      r8d, 0Ah
0x18001463f  jnb     short loc_18001464A
0x180014641  cmp     r8d, 800h
0x180014648  jnb     short loc_180014651
0x18001464a  xor     cl, cl
0x18001464c  test    sil, r8b
0x18001464f  jz      short loc_180014660
0x180014651  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_Future@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future> `wil::Feature<__WilFeatureTraits_Feature_Standalone_Future>::GetImpl(void)'::`2'::impl
0x180014658  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001465d  mov     cl, dil
0x180014660  mov     eax, [rbx]
0x180014662  test    sil, al
0x180014665  jz      short loc_18001466B
0x180014667  test    cl, cl
0x180014669  jnz     short loc_18001466D
0x18001466b  xor     edi, edi
0x18001466d  mov     rsi, [rsp+28h+arg_8]
0x180014672  and     eax, 0FFFFFFFEh
0x180014675  or      eax, edi
0x180014677  mov     [rbx], eax
0x180014679  mov     rax, rbx
0x18001467c  mov     rbx, [rsp+28h+arg_0]
0x180014681  add     rsp, 20h
0x180014685  pop     rdi
0x180014686  retn
```
