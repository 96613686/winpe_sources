# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005d74`
- end: `0x180005de2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f74`

## callees

- `0x180005d74`
- `0x18000a544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E286C, (unsigned int)a2, a3, a4);
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
0x180005d74  push    rbx
0x180005d76  sub     rsp, 20h
0x180005d7a  mov     ecx, 37E286Ch; this
0x180005d7f  mov     rbx, rdx
0x180005d82  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005d87  mov     r9d, eax
0x180005d8a  mov     qword ptr [rbx], 0
0x180005d91  and     r9d, 0FFFFFF3Fh
0x180005d98  mov     ecx, eax
0x180005d9a  and     eax, 80h
0x180005d9f  mov     r8d, r9d
0x180005da2  and     r8d, 3
0x180005da6  mov     edx, 40h ; '@'
0x180005dab  shl     r8d, 2
0x180005daf  and     ecx, edx
0x180005db1  or      r8d, ecx
0x180005db4  shl     r8d, 2
0x180005db8  or      r8d, eax
0x180005dbb  shl     r8d, 3
0x180005dbf  test    r9d, r9d
0x180005dc2  jz      short loc_180005DCF
0x180005dc4  xor     eax, eax
0x180005dc6  cmp     r9d, 2
0x180005dca  cmovz   eax, edx
0x180005dcd  mov     edx, eax
0x180005dcf  or      r8d, edx
0x180005dd2  mov     rax, rbx
0x180005dd5  or      r8d, 1
0x180005dd9  mov     [rbx], r8d
0x180005ddc  add     rsp, 20h
0x180005de0  pop     rbx
0x180005de1  retn
```
