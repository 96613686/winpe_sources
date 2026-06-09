# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008ffc`
- end: `0x18000906a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c98`

## callees

- `0x180008ffc`
- `0x18000b0a4`

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
0x180008ffc  push    rbx
0x180008ffe  sub     rsp, 20h
0x180009002  mov     ecx, 3667CA2h; this
0x180009007  mov     rbx, rdx
0x18000900a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000900f  mov     r9d, eax
0x180009012  mov     qword ptr [rbx], 0
0x180009019  and     r9d, 0FFFFFF3Fh
0x180009020  mov     ecx, eax
0x180009022  and     eax, 80h
0x180009027  mov     r8d, r9d
0x18000902a  and     r8d, 3
0x18000902e  mov     edx, 40h ; '@'
0x180009033  shl     r8d, 2
0x180009037  and     ecx, edx
0x180009039  or      r8d, ecx
0x18000903c  shl     r8d, 2
0x180009040  or      r8d, eax
0x180009043  shl     r8d, 3
0x180009047  test    r9d, r9d
0x18000904a  jz      short loc_180009057
0x18000904c  xor     eax, eax
0x18000904e  cmp     r9d, 2
0x180009052  cmovz   eax, edx
0x180009055  mov     edx, eax
0x180009057  or      r8d, edx
0x18000905a  mov     rax, rbx
0x18000905d  or      r8d, 1
0x180009061  mov     [rbx], r8d
0x180009064  add     rsp, 20h
0x180009068  pop     rbx
0x180009069  retn
```
