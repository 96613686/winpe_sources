# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008e40`
- end: `0x180008eae`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089f8`

## callees

- `0x180008e40`
- `0x18000b0a4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34F8, (unsigned int)a2, a3, a4);
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
0x180008e40  push    rbx
0x180008e42  sub     rsp, 20h
0x180008e46  mov     ecx, 2AF34F8h; this
0x180008e4b  mov     rbx, rdx
0x180008e4e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008e53  mov     r9d, eax
0x180008e56  mov     qword ptr [rbx], 0
0x180008e5d  and     r9d, 0FFFFFF3Fh
0x180008e64  mov     ecx, eax
0x180008e66  and     eax, 80h
0x180008e6b  mov     r8d, r9d
0x180008e6e  and     r8d, 3
0x180008e72  mov     edx, 40h ; '@'
0x180008e77  shl     r8d, 2
0x180008e7b  and     ecx, edx
0x180008e7d  or      r8d, ecx
0x180008e80  shl     r8d, 2
0x180008e84  or      r8d, eax
0x180008e87  shl     r8d, 3
0x180008e8b  test    r9d, r9d
0x180008e8e  jz      short loc_180008E9B
0x180008e90  xor     eax, eax
0x180008e92  cmp     r9d, 2
0x180008e96  cmovz   eax, edx
0x180008e99  mov     edx, eax
0x180008e9b  or      r8d, edx
0x180008e9e  mov     rax, rbx
0x180008ea1  or      r8d, 1
0x180008ea5  mov     [rbx], r8d
0x180008ea8  add     rsp, 20h
0x180008eac  pop     rbx
0x180008ead  retn
```
