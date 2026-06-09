# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013ec8`
- end: `0x180013fbb`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012d54`

## callees

- `0x180011098`
- `0x180013ec8`
- `0x180015a48`
- `0x180015ac0`
- `0x180015bb0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::GetCurrentFeatureEnabledState(
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
  int v10; // ecx
  __int16 v11; // r8
  int v12; // edi
  char v13; // si
  bool v14; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38988C8, 3u, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3))));
  v8 = 0;
  v9 = 8 * v7;
  if ( v6 )
  {
    if ( v6 == 2 )
      v8 = 64;
    v10 = v9 | v8;
  }
  else
  {
    v10 = v9;
  }
  v11 = v8 | v9;
  *(_DWORD *)a2 = v10;
  v12 = 1;
  if ( (v11 & 0xC00) == 0xC00 )
  {
    v13 = 1;
  }
  else
  {
    v13 = 0;
    v14 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_17;
  }
  v14 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_4920_0542>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59369936>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59369936>::GetImpl'::`2'::impl)
     && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
  if ( v13 && !v14 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_17:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v14 )
    v12 = 0;
  *(_DWORD *)a2 = v12 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180013ec8  push    rbx
0x180013eca  push    rbp
0x180013ecb  push    rsi
0x180013ecc  push    rdi
0x180013ecd  sub     rsp, 28h
0x180013ed1  mov     rbx, rdx
0x180013ed4  mov     ecx, 38988C8h; this
0x180013ed9  mov     edx, 3; unsigned int
0x180013ede  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180013ee3  mov     edx, eax
0x180013ee5  mov     qword ptr [rbx], 0
0x180013eec  mov     ecx, eax
0x180013eee  and     edx, 0FFFFFF3Fh
0x180013ef4  and     eax, 80h
0x180013ef9  mov     r8d, edx
0x180013efc  and     r8d, 3
0x180013f00  mov     ebp, 40h ; '@'
0x180013f05  shl     r8d, 2
0x180013f09  and     ecx, ebp
0x180013f0b  or      r8d, ecx
0x180013f0e  shl     r8d, 2
0x180013f12  or      r8d, eax
0x180013f15  xor     eax, eax
0x180013f17  shl     r8d, 3
0x180013f1b  test    edx, edx
0x180013f1d  jnz     short loc_180013F24
0x180013f1f  mov     ecx, r8d
0x180013f22  jmp     short loc_180013F2F
0x180013f24  cmp     edx, 2
0x180013f27  cmovz   eax, ebp
0x180013f2a  mov     ecx, eax
0x180013f2c  or      ecx, r8d
0x180013f2f  or      r8d, eax
0x180013f32  mov     [rbx], ecx
0x180013f34  mov     ecx, 0C00h
0x180013f39  mov     eax, r8d
0x180013f3c  and     eax, ecx
0x180013f3e  mov     edi, 1
0x180013f43  cmp     eax, ecx
0x180013f45  jnz     short loc_180013F4C
0x180013f47  mov     sil, dil
0x180013f4a  jmp     short loc_180013F56
0x180013f4c  xor     sil, sil
0x180013f4f  xor     cl, cl
0x180013f51  test    bpl, r8b
0x180013f54  jz      short loc_180013F9A
0x180013f56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_4920_0542@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_4920_0542@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542> `wil::Feature<__WilFeatureTraits_Feature_4920_0542>::GetImpl(void)'::`2'::impl
0x180013f5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_4920_0542@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_4920_0542>::__private_IsEnabled(wil::ReportingKind)
0x180013f62  test    al, al
0x180013f64  jz      short loc_180013F8B
0x180013f66  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59369936@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59369936@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59369936> `wil::Feature<__WilFeatureTraits_Feature_59369936>::GetImpl(void)'::`2'::impl
0x180013f6d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59369936@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59369936>::__private_IsEnabled(wil::ReportingKind)
0x180013f72  test    al, al
0x180013f74  jz      short loc_180013F8B
0x180013f76  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180013f7d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x180013f82  test    al, al
0x180013f84  jz      short loc_180013F8B
0x180013f86  mov     cl, dil
0x180013f89  jmp     short loc_180013F8D
0x180013f8b  xor     cl, cl
0x180013f8d  test    sil, sil
0x180013f90  jz      short loc_180013F9A
0x180013f92  test    cl, cl
0x180013f94  jnz     short loc_180013F9A
0x180013f96  btr     dword ptr [rbx], 0Ah
0x180013f9a  mov     eax, [rbx]
0x180013f9c  test    bpl, al
0x180013f9f  jz      short loc_180013FA5
0x180013fa1  test    cl, cl
0x180013fa3  jnz     short loc_180013FA7
0x180013fa5  xor     edi, edi
0x180013fa7  and     eax, 0FFFFFFFEh
0x180013faa  or      eax, edi
0x180013fac  mov     [rbx], eax
0x180013fae  mov     rax, rbx
0x180013fb1  add     rsp, 28h
0x180013fb5  pop     rdi
0x180013fb6  pop     rsi
0x180013fb7  pop     rbp
0x180013fb8  pop     rbx
0x180013fb9  retn
```
