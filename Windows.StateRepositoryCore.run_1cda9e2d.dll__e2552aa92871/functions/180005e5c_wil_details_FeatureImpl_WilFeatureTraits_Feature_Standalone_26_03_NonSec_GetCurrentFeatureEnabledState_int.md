# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005e5c`
- end: `0x180005eca`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800051d4`

## callees

- `0x180005e5c`
- `0x18000a544`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37E2881, (unsigned int)a2, a3, a4);
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
0x180005e5c  push    rbx
0x180005e5e  sub     rsp, 20h
0x180005e62  mov     ecx, 37E2881h; this
0x180005e67  mov     rbx, rdx
0x180005e6a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005e6f  mov     r9d, eax
0x180005e72  mov     qword ptr [rbx], 0
0x180005e79  and     r9d, 0FFFFFF3Fh
0x180005e80  mov     ecx, eax
0x180005e82  and     eax, 80h
0x180005e87  mov     r8d, r9d
0x180005e8a  and     r8d, 3
0x180005e8e  mov     edx, 40h ; '@'
0x180005e93  shl     r8d, 2
0x180005e97  and     ecx, edx
0x180005e99  or      r8d, ecx
0x180005e9c  shl     r8d, 2
0x180005ea0  or      r8d, eax
0x180005ea3  shl     r8d, 3
0x180005ea7  test    r9d, r9d
0x180005eaa  jz      short loc_180005EB7
0x180005eac  xor     eax, eax
0x180005eae  cmp     r9d, 2
0x180005eb2  cmovz   eax, edx
0x180005eb5  mov     edx, eax
0x180005eb7  or      r8d, edx
0x180005eba  mov     rax, rbx
0x180005ebd  or      r8d, 1
0x180005ec1  mov     [rbx], r8d
0x180005ec4  add     rsp, 20h
0x180005ec8  pop     rbx
0x180005ec9  retn
```
