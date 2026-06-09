# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005de8`
- end: `0x180005e56`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050a4`

## callees

- `0x180005de8`
- `0x18000a544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E287E, (unsigned int)a2, a3, a4);
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
0x180005de8  push    rbx
0x180005dea  sub     rsp, 20h
0x180005dee  mov     ecx, 37E287Eh; this
0x180005df3  mov     rbx, rdx
0x180005df6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005dfb  mov     r9d, eax
0x180005dfe  mov     qword ptr [rbx], 0
0x180005e05  and     r9d, 0FFFFFF3Fh
0x180005e0c  mov     ecx, eax
0x180005e0e  and     eax, 80h
0x180005e13  mov     r8d, r9d
0x180005e16  and     r8d, 3
0x180005e1a  mov     edx, 40h ; '@'
0x180005e1f  shl     r8d, 2
0x180005e23  and     ecx, edx
0x180005e25  or      r8d, ecx
0x180005e28  shl     r8d, 2
0x180005e2c  or      r8d, eax
0x180005e2f  shl     r8d, 3
0x180005e33  test    r9d, r9d
0x180005e36  jz      short loc_180005E43
0x180005e38  xor     eax, eax
0x180005e3a  cmp     r9d, 2
0x180005e3e  cmovz   eax, edx
0x180005e41  mov     edx, eax
0x180005e43  or      r8d, edx
0x180005e46  mov     rax, rbx
0x180005e49  or      r8d, 1
0x180005e4d  mov     [rbx], r8d
0x180005e50  add     rsp, 20h
0x180005e54  pop     rbx
0x180005e55  retn
```
