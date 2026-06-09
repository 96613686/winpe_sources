# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180017010`
- end: `0x180017081`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016f24`

## callees

- `0x180011098`
- `0x180017010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WVD_MultiSession_User_Configuration>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // r9d
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x16967CF, 0, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 64;
  v8 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( v6 == 2 )
      v9 = 64;
    v7 = v9;
  }
  result = a2;
  *(_DWORD *)a2 = v7 | v8 | 1;
  return result;
}

```

## disassembly

```asm
0x180017010  push    rbx
0x180017012  sub     rsp, 20h
0x180017016  mov     rbx, rdx
0x180017019  mov     ecx, 16967CFh; this
0x18001701e  xor     edx, edx; unsigned int
0x180017020  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180017025  mov     r9d, eax
0x180017028  mov     qword ptr [rbx], 0
0x18001702f  and     r9d, 0FFFFFF3Fh
0x180017036  mov     ecx, eax
0x180017038  and     eax, 80h
0x18001703d  mov     r8d, r9d
0x180017040  and     r8d, 3
0x180017044  mov     edx, 40h ; '@'
0x180017049  shl     r8d, 2
0x18001704d  and     ecx, edx
0x18001704f  or      r8d, ecx
0x180017052  shl     r8d, 2
0x180017056  or      r8d, eax
0x180017059  shl     r8d, 3
0x18001705d  test    r9d, r9d
0x180017060  jz      short loc_18001706D
0x180017062  xor     eax, eax
0x180017064  cmp     r9d, 2
0x180017068  cmovz   eax, edx
0x18001706b  mov     edx, eax
0x18001706d  or      r8d, edx
0x180017070  mov     rax, rbx
0x180017073  or      r8d, 1
0x180017077  mov     [rbx], r8d
0x18001707a  add     rsp, 20h
0x18001707e  pop     rbx
0x18001707f  retn
```
