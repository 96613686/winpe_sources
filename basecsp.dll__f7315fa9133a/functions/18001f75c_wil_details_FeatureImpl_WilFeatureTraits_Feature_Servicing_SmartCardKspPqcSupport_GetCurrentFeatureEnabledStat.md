# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001f75c`
- end: `0x18001f81b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001f444`

## callees

- `0x180017994`
- `0x18001f75c`
- `0x18001faa0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  int v5; // edi
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v7; // edx
  int v8; // r8d
  int v9; // eax
  unsigned int v10; // r8d
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  v5 = 1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x39199BF, 1u, a3, a4);
  *a2 = 0;
  v7 = FeatureEnabledState & 0xFFFFFF3F;
  v8 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v9 = 0;
    if ( v7 == 2 )
      v9 = 64;
  }
  else
  {
    v9 = 64;
  }
  v10 = v9 | v8;
  *(_DWORD *)a2 = v10;
  if ( (v10 & 0x400) != 0 && v10 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v10 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v5 = 0;
  result = a2;
  *(_DWORD *)a2 = v5 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18001f75c  push    rbx
0x18001f75e  push    rbp
0x18001f75f  push    rsi
0x18001f760  push    rdi
0x18001f761  sub     rsp, 28h
0x18001f765  mov     rbx, rdx
0x18001f768  mov     edi, 1
0x18001f76d  mov     edx, edi; unsigned int
0x18001f76f  mov     ecx, 39199BFh; this
0x18001f774  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001f779  mov     edx, eax
0x18001f77b  mov     qword ptr [rbx], 0
0x18001f782  and     edx, 0FFFFFF3Fh
0x18001f788  lea     ebp, [rdi+3Fh]
0x18001f78b  mov     ecx, eax
0x18001f78d  mov     r8d, edx
0x18001f790  and     r8d, 3
0x18001f794  and     ecx, ebp
0x18001f796  shl     r8d, 2
0x18001f79a  and     eax, 80h
0x18001f79f  or      r8d, ecx
0x18001f7a2  shl     r8d, 2
0x18001f7a6  or      r8d, eax
0x18001f7a9  shl     r8d, 3
0x18001f7ad  test    edx, edx
0x18001f7af  jnz     short loc_18001F7B5
0x18001f7b1  mov     eax, ebp
0x18001f7b3  jmp     short loc_18001F7BD
0x18001f7b5  xor     eax, eax
0x18001f7b7  cmp     edx, 2
0x18001f7ba  cmovz   eax, ebp
0x18001f7bd  or      r8d, eax
0x18001f7c0  mov     [rbx], r8d
0x18001f7c3  bt      r8d, 0Ah
0x18001f7c8  jnb     short loc_18001F7D8
0x18001f7ca  cmp     r8d, 800h
0x18001f7d1  jb      short loc_18001F7D8
0x18001f7d3  mov     sil, dil
0x18001f7d6  jmp     short loc_18001F7E2
0x18001f7d8  xor     sil, sil
0x18001f7db  xor     al, al
0x18001f7dd  test    bpl, r8b
0x18001f7e0  jz      short loc_18001F7FB
0x18001f7e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x18001f7e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001f7ee  test    sil, sil
0x18001f7f1  jz      short loc_18001F7FB
0x18001f7f3  test    al, al
0x18001f7f5  jnz     short loc_18001F7FB
0x18001f7f7  btr     dword ptr [rbx], 0Ah
0x18001f7fb  mov     ecx, [rbx]
0x18001f7fd  test    bpl, cl
0x18001f800  jz      short loc_18001F806
0x18001f802  test    al, al
0x18001f804  jnz     short loc_18001F808
0x18001f806  xor     edi, edi
0x18001f808  and     ecx, 0FFFFFFFEh
0x18001f80b  mov     rax, rbx
0x18001f80e  or      ecx, edi
0x18001f810  mov     [rbx], ecx
0x18001f812  add     rsp, 28h
0x18001f816  pop     rdi
0x18001f817  pop     rsi
0x18001f818  pop     rbp
0x18001f819  pop     rbx
0x18001f81a  retn
```
