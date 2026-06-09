# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001441c`
- end: `0x180014499`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001420c`

## callees

- `0x18001441c`
- `0x1800162fc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // r8d
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x24E34BD, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  result = a2;
  *(_DWORD *)a2 = ((v9 & 0x40) != 0) | v9;
  return result;
}

```

## disassembly

```asm
0x18001441c  push    rbx
0x18001441e  sub     rsp, 20h
0x180014422  mov     ecx, 24E34BDh; this
0x180014427  mov     rbx, rdx
0x18001442a  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001442f  mov     edx, eax
0x180014431  mov     qword ptr [rbx], 0
0x180014438  and     edx, 0FFFFFF3Fh
0x18001443e  mov     ecx, eax
0x180014440  and     eax, 80h
0x180014445  mov     r8d, edx
0x180014448  and     r8d, 3
0x18001444c  mov     r9d, 40h ; '@'
0x180014452  shl     r8d, 2
0x180014456  and     ecx, r9d
0x180014459  or      r8d, ecx
0x18001445c  shl     r8d, 2
0x180014460  or      r8d, eax
0x180014463  shl     r8d, 3
0x180014467  test    edx, edx
0x180014469  jnz     short loc_180014470
0x18001446b  mov     eax, r9d
0x18001446e  jmp     short loc_180014479
0x180014470  xor     eax, eax
0x180014472  cmp     edx, 2
0x180014475  cmovz   eax, r9d
0x180014479  or      r8d, eax
0x18001447c  test    r9b, r8b
0x18001447f  jz      short loc_180014488
0x180014481  mov     eax, 1
0x180014486  jmp     short loc_18001448A
0x180014488  xor     eax, eax
0x18001448a  or      r8d, eax
0x18001448d  mov     rax, rbx
0x180014490  mov     [rbx], r8d
0x180014493  add     rsp, 20h
0x180014497  pop     rbx
0x180014498  retn
```
