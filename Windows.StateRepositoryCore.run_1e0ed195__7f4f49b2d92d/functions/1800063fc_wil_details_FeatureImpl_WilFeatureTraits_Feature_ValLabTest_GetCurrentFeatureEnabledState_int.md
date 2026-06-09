# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800063fc`
- end: `0x18000646a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005a24`

## callees

- `0x1800063fc`
- `0x18000a544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA2, (unsigned int)a2, a3, a4);
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
0x1800063fc  push    rbx
0x1800063fe  sub     rsp, 20h
0x180006402  mov     ecx, 3667CA2h; this
0x180006407  mov     rbx, rdx
0x18000640a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000640f  mov     r9d, eax
0x180006412  mov     qword ptr [rbx], 0
0x180006419  and     r9d, 0FFFFFF3Fh
0x180006420  mov     ecx, eax
0x180006422  and     eax, 80h
0x180006427  mov     r8d, r9d
0x18000642a  and     r8d, 3
0x18000642e  mov     edx, 40h ; '@'
0x180006433  shl     r8d, 2
0x180006437  and     ecx, edx
0x180006439  or      r8d, ecx
0x18000643c  shl     r8d, 2
0x180006440  or      r8d, eax
0x180006443  shl     r8d, 3
0x180006447  test    r9d, r9d
0x18000644a  jz      short loc_180006457
0x18000644c  xor     eax, eax
0x18000644e  cmp     r9d, 2
0x180006452  cmovz   eax, edx
0x180006455  mov     edx, eax
0x180006457  or      r8d, edx
0x18000645a  mov     rax, rbx
0x18000645d  or      r8d, 1
0x180006461  mov     [rbx], r8d
0x180006464  add     rsp, 20h
0x180006468  pop     rbx
0x180006469  retn
```
