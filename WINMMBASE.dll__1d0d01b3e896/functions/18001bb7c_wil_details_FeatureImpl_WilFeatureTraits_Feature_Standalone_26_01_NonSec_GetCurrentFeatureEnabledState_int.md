# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001bb7c`
- end: `0x18001bbea`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b1fc`

## callees

- `0x1800162fc`
- `0x18001bb7c`

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
0x18001bb7c  push    rbx
0x18001bb7e  sub     rsp, 20h
0x18001bb82  mov     ecx, 37E286Ch; this
0x18001bb87  mov     rbx, rdx
0x18001bb8a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001bb8f  mov     r9d, eax
0x18001bb92  mov     qword ptr [rbx], 0
0x18001bb99  and     r9d, 0FFFFFF3Fh
0x18001bba0  mov     ecx, eax
0x18001bba2  and     eax, 80h
0x18001bba7  mov     r8d, r9d
0x18001bbaa  and     r8d, 3
0x18001bbae  mov     edx, 40h ; '@'
0x18001bbb3  shl     r8d, 2
0x18001bbb7  and     ecx, edx
0x18001bbb9  or      r8d, ecx
0x18001bbbc  shl     r8d, 2
0x18001bbc0  or      r8d, eax
0x18001bbc3  shl     r8d, 3
0x18001bbc7  test    r9d, r9d
0x18001bbca  jz      short loc_18001BBD7
0x18001bbcc  xor     eax, eax
0x18001bbce  cmp     r9d, 2
0x18001bbd2  cmovz   eax, edx
0x18001bbd5  mov     edx, eax
0x18001bbd7  or      r8d, edx
0x18001bbda  mov     rax, rbx
0x18001bbdd  or      r8d, 1
0x18001bbe1  mov     [rbx], r8d
0x18001bbe4  add     rsp, 20h
0x18001bbe8  pop     rbx
0x18001bbe9  retn
```
