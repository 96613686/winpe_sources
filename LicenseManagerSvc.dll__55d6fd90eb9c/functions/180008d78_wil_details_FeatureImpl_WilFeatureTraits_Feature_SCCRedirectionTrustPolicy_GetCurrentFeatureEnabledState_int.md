# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008d78`
- end: `0x180008e37`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008918`

## callees

- `0x180008d78`
- `0x18000b0a4`
- `0x18000b310`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SCCRedirectionTrustPolicy>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x387788F, (unsigned int)a2, a3, a4);
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
0x180008d78  push    rbx
0x180008d7a  push    rbp
0x180008d7b  push    rsi
0x180008d7c  push    rdi
0x180008d7d  sub     rsp, 28h
0x180008d81  mov     ecx, 387788Fh; this
0x180008d86  mov     rbx, rdx
0x180008d89  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180008d8e  mov     edx, eax
0x180008d90  mov     qword ptr [rbx], 0
0x180008d97  and     edx, 0FFFFFF3Fh
0x180008d9d  mov     ecx, eax
0x180008d9f  and     eax, 80h
0x180008da4  mov     r8d, edx
0x180008da7  and     r8d, 3
0x180008dab  mov     ebp, 40h ; '@'
0x180008db0  shl     r8d, 2
0x180008db4  and     ecx, ebp
0x180008db6  or      r8d, ecx
0x180008db9  shl     r8d, 2
0x180008dbd  or      r8d, eax
0x180008dc0  shl     r8d, 3
0x180008dc4  test    edx, edx
0x180008dc6  jnz     short loc_180008DCC
0x180008dc8  mov     eax, ebp
0x180008dca  jmp     short loc_180008DD4
0x180008dcc  xor     eax, eax
0x180008dce  cmp     edx, 2
0x180008dd1  cmovz   eax, ebp
0x180008dd4  or      r8d, eax
0x180008dd7  mov     edi, 1
0x180008ddc  mov     [rbx], r8d
0x180008ddf  bt      r8d, 0Ah
0x180008de4  jnb     short loc_180008DF4
0x180008de6  cmp     r8d, 800h
0x180008ded  jb      short loc_180008DF4
0x180008def  mov     sil, dil
0x180008df2  jmp     short loc_180008DFE
0x180008df4  xor     sil, sil
0x180008df7  xor     al, al
0x180008df9  test    bpl, r8b
0x180008dfc  jz      short loc_180008E17
0x180008dfe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x180008e05  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x180008e0a  test    sil, sil
0x180008e0d  jz      short loc_180008E17
0x180008e0f  test    al, al
0x180008e11  jnz     short loc_180008E17
0x180008e13  btr     dword ptr [rbx], 0Ah
0x180008e17  mov     ecx, [rbx]
0x180008e19  test    bpl, cl
0x180008e1c  jz      short loc_180008E22
0x180008e1e  test    al, al
0x180008e20  jnz     short loc_180008E24
0x180008e22  xor     edi, edi
0x180008e24  and     ecx, 0FFFFFFFEh
0x180008e27  mov     rax, rbx
0x180008e2a  or      ecx, edi
0x180008e2c  mov     [rbx], ecx
0x180008e2e  add     rsp, 28h
0x180008e32  pop     rdi
0x180008e33  pop     rsi
0x180008e34  pop     rbp
0x180008e35  pop     rbx
0x180008e36  retn
```
