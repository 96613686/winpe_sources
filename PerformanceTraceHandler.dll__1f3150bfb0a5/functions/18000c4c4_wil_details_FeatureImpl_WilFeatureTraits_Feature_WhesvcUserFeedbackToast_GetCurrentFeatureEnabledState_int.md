# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000c4c4`
- end: `0x18000c57d`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WhesvcUserFeedbackToast@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `185`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c2bc`

## callees

- `0x18000c4c4`
- `0x18000cfc0`
- `0x18000d064`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WhesvcUserFeedbackToast>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edi
  char v10; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3A019EF, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
    v7 |= v8;
  }
  *(_DWORD *)a2 = v7;
  v9 = 1;
  if ( (v7 & 0xC00) == 0xC00 )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    IsEnabled = 0;
    if ( (v7 & 0x40) == 0 )
      goto LABEL_11;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v10 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_11:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v9 = 0;
  result = a2;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18000c4c4  push    rbx
0x18000c4c6  push    rbp
0x18000c4c7  push    rsi
0x18000c4c8  push    rdi
0x18000c4c9  sub     rsp, 28h
0x18000c4cd  mov     ecx, 3A019EFh; this
0x18000c4d2  mov     rbx, rdx
0x18000c4d5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000c4da  mov     edx, eax
0x18000c4dc  mov     qword ptr [rbx], 0
0x18000c4e3  and     edx, 0FFFFFF3Fh
0x18000c4e9  mov     ecx, eax
0x18000c4eb  and     eax, 80h
0x18000c4f0  mov     r8d, edx
0x18000c4f3  and     r8d, 3
0x18000c4f7  mov     ebp, 40h ; '@'
0x18000c4fc  shl     r8d, 2
0x18000c500  and     ecx, ebp
0x18000c502  or      r8d, ecx
0x18000c505  shl     r8d, 2
0x18000c509  or      r8d, eax
0x18000c50c  shl     r8d, 3
0x18000c510  test    edx, edx
0x18000c512  jz      short loc_18000C51F
0x18000c514  xor     eax, eax
0x18000c516  cmp     edx, 2
0x18000c519  cmovz   eax, ebp
0x18000c51c  or      r8d, eax
0x18000c51f  mov     ecx, 0C00h
0x18000c524  mov     [rbx], r8d
0x18000c527  mov     eax, r8d
0x18000c52a  mov     edi, 1
0x18000c52f  and     eax, ecx
0x18000c531  cmp     eax, ecx
0x18000c533  jnz     short loc_18000C53A
0x18000c535  mov     sil, dil
0x18000c538  jmp     short loc_18000C544
0x18000c53a  xor     sil, sil
0x18000c53d  xor     al, al
0x18000c53f  test    bpl, r8b
0x18000c542  jz      short loc_18000C55D
0x18000c544  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18000c54b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18000c550  test    sil, sil
0x18000c553  jz      short loc_18000C55D
0x18000c555  test    al, al
0x18000c557  jnz     short loc_18000C55D
0x18000c559  btr     dword ptr [rbx], 0Ah
0x18000c55d  mov     ecx, [rbx]
0x18000c55f  test    bpl, cl
0x18000c562  jz      short loc_18000C568
0x18000c564  test    al, al
0x18000c566  jnz     short loc_18000C56A
0x18000c568  xor     edi, edi
0x18000c56a  and     ecx, 0FFFFFFFEh
0x18000c56d  mov     rax, rbx
0x18000c570  or      ecx, edi
0x18000c572  mov     [rbx], ecx
0x18000c574  add     rsp, 28h
0x18000c578  pop     rdi
0x18000c579  pop     rsi
0x18000c57a  pop     rbp
0x18000c57b  pop     rbx
0x18000c57c  retn
```
