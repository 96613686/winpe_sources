# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001180c`
- end: `0x1800118cb`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RetireTHotkey@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001172c`

## callees

- `0x18000cfc0`
- `0x18000d064`
- `0x18001180c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RetireTHotkey>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x36F0790, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl'::`2'::impl);
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
0x18001180c  push    rbx
0x18001180e  push    rbp
0x18001180f  push    rsi
0x180011810  push    rdi
0x180011811  sub     rsp, 28h
0x180011815  mov     ecx, 36F0790h; this
0x18001181a  mov     rbx, rdx
0x18001181d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180011822  mov     edx, eax
0x180011824  mov     qword ptr [rbx], 0
0x18001182b  and     edx, 0FFFFFF3Fh
0x180011831  mov     ecx, eax
0x180011833  and     eax, 80h
0x180011838  mov     r8d, edx
0x18001183b  and     r8d, 3
0x18001183f  mov     ebp, 40h ; '@'
0x180011844  shl     r8d, 2
0x180011848  and     ecx, ebp
0x18001184a  or      r8d, ecx
0x18001184d  shl     r8d, 2
0x180011851  or      r8d, eax
0x180011854  shl     r8d, 3
0x180011858  test    edx, edx
0x18001185a  jnz     short loc_180011860
0x18001185c  mov     eax, ebp
0x18001185e  jmp     short loc_180011868
0x180011860  xor     eax, eax
0x180011862  cmp     edx, 2
0x180011865  cmovz   eax, ebp
0x180011868  or      r8d, eax
0x18001186b  mov     edi, 1
0x180011870  mov     [rbx], r8d
0x180011873  bt      r8d, 0Ah
0x180011878  jnb     short loc_180011888
0x18001187a  cmp     r8d, 800h
0x180011881  jb      short loc_180011888
0x180011883  mov     sil, dil
0x180011886  jmp     short loc_180011892
0x180011888  xor     sil, sil
0x18001188b  xor     al, al
0x18001188d  test    bpl, r8b
0x180011890  jz      short loc_1800118AB
0x180011892  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UxAccOptimization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization> `wil::Feature<__WilFeatureTraits_Feature_UxAccOptimization>::GetImpl(void)'::`2'::impl
0x180011899  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::__private_IsEnabled(wil::ReportingKind)
0x18001189e  test    sil, sil
0x1800118a1  jz      short loc_1800118AB
0x1800118a3  test    al, al
0x1800118a5  jnz     short loc_1800118AB
0x1800118a7  btr     dword ptr [rbx], 0Ah
0x1800118ab  mov     ecx, [rbx]
0x1800118ad  test    bpl, cl
0x1800118b0  jz      short loc_1800118B6
0x1800118b2  test    al, al
0x1800118b4  jnz     short loc_1800118B8
0x1800118b6  xor     edi, edi
0x1800118b8  and     ecx, 0FFFFFFFEh
0x1800118bb  mov     rax, rbx
0x1800118be  or      ecx, edi
0x1800118c0  mov     [rbx], ecx
0x1800118c2  add     rsp, 28h
0x1800118c6  pop     rdi
0x1800118c7  pop     rsi
0x1800118c8  pop     rbp
0x1800118c9  pop     rbx
0x1800118ca  retn
```
