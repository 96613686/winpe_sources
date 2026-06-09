# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015a64`
- end: `0x180015b23`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixesQ3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014b6c`

## callees

- `0x18000cfc0`
- `0x180015a64`
- `0x180017d98`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixesQ3>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3862E9D, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl);
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
0x180015a64  push    rbx
0x180015a66  push    rbp
0x180015a67  push    rsi
0x180015a68  push    rdi
0x180015a69  sub     rsp, 28h
0x180015a6d  mov     ecx, 3862E9Dh; this
0x180015a72  mov     rbx, rdx
0x180015a75  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015a7a  mov     edx, eax
0x180015a7c  mov     qword ptr [rbx], 0
0x180015a83  and     edx, 0FFFFFF3Fh
0x180015a89  mov     ecx, eax
0x180015a8b  and     eax, 80h
0x180015a90  mov     r8d, edx
0x180015a93  and     r8d, 3
0x180015a97  mov     ebp, 40h ; '@'
0x180015a9c  shl     r8d, 2
0x180015aa0  and     ecx, ebp
0x180015aa2  or      r8d, ecx
0x180015aa5  shl     r8d, 2
0x180015aa9  or      r8d, eax
0x180015aac  shl     r8d, 3
0x180015ab0  test    edx, edx
0x180015ab2  jnz     short loc_180015AB8
0x180015ab4  mov     eax, ebp
0x180015ab6  jmp     short loc_180015AC0
0x180015ab8  xor     eax, eax
0x180015aba  cmp     edx, 2
0x180015abd  cmovz   eax, ebp
0x180015ac0  or      r8d, eax
0x180015ac3  mov     edi, 1
0x180015ac8  mov     [rbx], r8d
0x180015acb  bt      r8d, 0Ah
0x180015ad0  jnb     short loc_180015AE0
0x180015ad2  cmp     r8d, 800h
0x180015ad9  jb      short loc_180015AE0
0x180015adb  mov     sil, dil
0x180015ade  jmp     short loc_180015AEA
0x180015ae0  xor     sil, sil
0x180015ae3  xor     al, al
0x180015ae5  test    bpl, r8b
0x180015ae8  jz      short loc_180015B03
0x180015aea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180015af1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180015af6  test    sil, sil
0x180015af9  jz      short loc_180015B03
0x180015afb  test    al, al
0x180015afd  jnz     short loc_180015B03
0x180015aff  btr     dword ptr [rbx], 0Ah
0x180015b03  mov     ecx, [rbx]
0x180015b05  test    bpl, cl
0x180015b08  jz      short loc_180015B0E
0x180015b0a  test    al, al
0x180015b0c  jnz     short loc_180015B10
0x180015b0e  xor     edi, edi
0x180015b10  and     ecx, 0FFFFFFFEh
0x180015b13  mov     rax, rbx
0x180015b16  or      ecx, edi
0x180015b18  mov     [rbx], ecx
0x180015b1a  add     rsp, 28h
0x180015b1e  pop     rdi
0x180015b1f  pop     rsi
0x180015b20  pop     rbp
0x180015b21  pop     rbx
0x180015b22  retn
```
