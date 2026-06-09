# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005d00`
- end: `0x180005d6e`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e44`

## callees

- `0x180005d00`
- `0x18000a544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2AF34FD, (unsigned int)a2, a3, a4);
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
0x180005d00  push    rbx
0x180005d02  sub     rsp, 20h
0x180005d06  mov     ecx, 2AF34FDh; this
0x180005d0b  mov     rbx, rdx
0x180005d0e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005d13  mov     r9d, eax
0x180005d16  mov     qword ptr [rbx], 0
0x180005d1d  and     r9d, 0FFFFFF3Fh
0x180005d24  mov     ecx, eax
0x180005d26  and     eax, 80h
0x180005d2b  mov     r8d, r9d
0x180005d2e  and     r8d, 3
0x180005d32  mov     edx, 40h ; '@'
0x180005d37  shl     r8d, 2
0x180005d3b  and     ecx, edx
0x180005d3d  or      r8d, ecx
0x180005d40  shl     r8d, 2
0x180005d44  or      r8d, eax
0x180005d47  shl     r8d, 3
0x180005d4b  test    r9d, r9d
0x180005d4e  jz      short loc_180005D5B
0x180005d50  xor     eax, eax
0x180005d52  cmp     r9d, 2
0x180005d56  cmovz   eax, edx
0x180005d59  mov     edx, eax
0x180005d5b  or      r8d, edx
0x180005d5e  mov     rax, rbx
0x180005d61  or      r8d, 1
0x180005d65  mov     [rbx], r8d
0x180005d68  add     rsp, 20h
0x180005d6c  pop     rbx
0x180005d6d  retn
```
