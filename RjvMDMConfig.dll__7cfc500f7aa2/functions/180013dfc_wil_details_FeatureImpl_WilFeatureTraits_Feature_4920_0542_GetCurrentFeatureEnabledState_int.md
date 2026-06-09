# wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013dfc`
- end: `0x180013ec1`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_4920_0542@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012c0c`

## callees

- `0x180011098`
- `0x180013dfc`
- `0x180015bec`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2EEBD9E, 3u, a3, a4);
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
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x180013dfc  push    rbx
0x180013dfe  push    rbp
0x180013dff  push    rsi
0x180013e00  push    rdi
0x180013e01  sub     rsp, 28h
0x180013e05  mov     rbx, rdx
0x180013e08  mov     ecx, 2EEBD9Eh; this
0x180013e0d  mov     edx, 3; unsigned int
0x180013e12  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180013e17  mov     edx, eax
0x180013e19  mov     qword ptr [rbx], 0
0x180013e20  and     edx, 0FFFFFF3Fh
0x180013e26  mov     ecx, eax
0x180013e28  and     eax, 80h
0x180013e2d  mov     r8d, edx
0x180013e30  and     r8d, 3
0x180013e34  mov     ebp, 40h ; '@'
0x180013e39  shl     r8d, 2
0x180013e3d  and     ecx, ebp
0x180013e3f  or      r8d, ecx
0x180013e42  shl     r8d, 2
0x180013e46  or      r8d, eax
0x180013e49  shl     r8d, 3
0x180013e4d  test    edx, edx
0x180013e4f  jnz     short loc_180013E55
0x180013e51  mov     eax, ebp
0x180013e53  jmp     short loc_180013E5D
0x180013e55  xor     eax, eax
0x180013e57  cmp     edx, 2
0x180013e5a  cmovz   eax, ebp
0x180013e5d  or      r8d, eax
0x180013e60  mov     edi, 1
0x180013e65  mov     [rbx], r8d
0x180013e68  bt      r8d, 0Ah
0x180013e6d  jnb     short loc_180013E7D
0x180013e6f  cmp     r8d, 800h
0x180013e76  jb      short loc_180013E7D
0x180013e78  mov     sil, dil
0x180013e7b  jmp     short loc_180013E87
0x180013e7d  xor     sil, sil
0x180013e80  xor     al, al
0x180013e82  test    bpl, r8b
0x180013e85  jz      short loc_180013EA0
0x180013e87  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180013e8e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180013e93  test    sil, sil
0x180013e96  jz      short loc_180013EA0
0x180013e98  test    al, al
0x180013e9a  jnz     short loc_180013EA0
0x180013e9c  btr     dword ptr [rbx], 0Ah
0x180013ea0  mov     ecx, [rbx]
0x180013ea2  test    bpl, cl
0x180013ea5  jz      short loc_180013EAB
0x180013ea7  test    al, al
0x180013ea9  jnz     short loc_180013EAD
0x180013eab  xor     edi, edi
0x180013ead  and     ecx, 0FFFFFFFEh
0x180013eb0  mov     rax, rbx
0x180013eb3  or      ecx, edi
0x180013eb5  mov     [rbx], ecx
0x180013eb7  add     rsp, 28h
0x180013ebb  pop     rdi
0x180013ebc  pop     rsi
0x180013ebd  pop     rbp
0x180013ebe  pop     rbx
0x180013ebf  retn
```
