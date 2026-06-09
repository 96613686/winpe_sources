# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005c8c`
- end: `0x180005cfa`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004d14`

## callees

- `0x180005c8c`
- `0x18000a544`

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
0x180005c8c  push    rbx
0x180005c8e  sub     rsp, 20h
0x180005c92  mov     ecx, 2AF34F8h; this
0x180005c97  mov     rbx, rdx
0x180005c9a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005c9f  mov     r9d, eax
0x180005ca2  mov     qword ptr [rbx], 0
0x180005ca9  and     r9d, 0FFFFFF3Fh
0x180005cb0  mov     ecx, eax
0x180005cb2  and     eax, 80h
0x180005cb7  mov     r8d, r9d
0x180005cba  and     r8d, 3
0x180005cbe  mov     edx, 40h ; '@'
0x180005cc3  shl     r8d, 2
0x180005cc7  and     ecx, edx
0x180005cc9  or      r8d, ecx
0x180005ccc  shl     r8d, 2
0x180005cd0  or      r8d, eax
0x180005cd3  shl     r8d, 3
0x180005cd7  test    r9d, r9d
0x180005cda  jz      short loc_180005CE7
0x180005cdc  xor     eax, eax
0x180005cde  cmp     r9d, 2
0x180005ce2  cmovz   eax, edx
0x180005ce5  mov     edx, eax
0x180005ce7  or      r8d, edx
0x180005cea  mov     rax, rbx
0x180005ced  or      r8d, 1
0x180005cf1  mov     [rbx], r8d
0x180005cf4  add     rsp, 20h
0x180005cf8  pop     rbx
0x180005cf9  retn
```
