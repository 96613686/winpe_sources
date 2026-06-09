# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c490`
- end: `0x14000c500`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MsiHashMismatchFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `112`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b79c`

## callees

- `0x14000c490`
- `0x140011454`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MsiHashMismatchFix>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x1FBD065, 0, a3, a4);
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
0x14000c490  push    rbx
0x14000c492  sub     rsp, 20h
0x14000c496  mov     rbx, rdx
0x14000c499  mov     ecx, 1FBD065h; this
0x14000c49e  xor     edx, edx; unsigned int
0x14000c4a0  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c4a5  mov     r9d, eax
0x14000c4a8  mov     qword ptr [rbx], 0
0x14000c4af  and     r9d, 0FFFFFF3Fh
0x14000c4b6  mov     ecx, eax
0x14000c4b8  and     eax, 80h
0x14000c4bd  mov     r8d, r9d
0x14000c4c0  and     r8d, 3
0x14000c4c4  mov     edx, 40h ; '@'
0x14000c4c9  shl     r8d, 2
0x14000c4cd  and     ecx, edx
0x14000c4cf  or      r8d, ecx
0x14000c4d2  shl     r8d, 2
0x14000c4d6  or      r8d, eax
0x14000c4d9  shl     r8d, 3
0x14000c4dd  test    r9d, r9d
0x14000c4e0  jz      short loc_14000C4ED
0x14000c4e2  xor     eax, eax
0x14000c4e4  cmp     r9d, 2
0x14000c4e8  cmovz   eax, edx
0x14000c4eb  mov     edx, eax
0x14000c4ed  or      r8d, edx
0x14000c4f0  mov     rax, rbx
0x14000c4f3  or      r8d, 1
0x14000c4f7  mov     [rbx], r8d
0x14000c4fa  add     rsp, 20h
0x14000c4fe  pop     rbx
0x14000c4ff  retn
```
