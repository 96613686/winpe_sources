# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001ba94`
- end: `0x18001bb02`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b03c`

## callees

- `0x1800162fc`
- `0x18001ba94`

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
0x18001ba94  push    rbx
0x18001ba96  sub     rsp, 20h
0x18001ba9a  mov     ecx, 2AF34F8h; this
0x18001ba9f  mov     rbx, rdx
0x18001baa2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001baa7  mov     r9d, eax
0x18001baaa  mov     qword ptr [rbx], 0
0x18001bab1  and     r9d, 0FFFFFF3Fh
0x18001bab8  mov     ecx, eax
0x18001baba  and     eax, 80h
0x18001babf  mov     r8d, r9d
0x18001bac2  and     r8d, 3
0x18001bac6  mov     edx, 40h ; '@'
0x18001bacb  shl     r8d, 2
0x18001bacf  and     ecx, edx
0x18001bad1  or      r8d, ecx
0x18001bad4  shl     r8d, 2
0x18001bad8  or      r8d, eax
0x18001badb  shl     r8d, 3
0x18001badf  test    r9d, r9d
0x18001bae2  jz      short loc_18001BAEF
0x18001bae4  xor     eax, eax
0x18001bae6  cmp     r9d, 2
0x18001baea  cmovz   eax, edx
0x18001baed  mov     edx, eax
0x18001baef  or      r8d, edx
0x18001baf2  mov     rax, rbx
0x18001baf5  or      r8d, 1
0x18001baf9  mov     [rbx], r8d
0x18001bafc  add     rsp, 20h
0x18001bb00  pop     rbx
0x18001bb01  retn
```
