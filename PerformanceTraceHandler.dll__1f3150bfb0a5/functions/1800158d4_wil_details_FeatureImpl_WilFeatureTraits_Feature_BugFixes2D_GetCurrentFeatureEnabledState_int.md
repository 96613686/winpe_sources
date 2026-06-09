# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800158d4`
- end: `0x180015993`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes2D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800149ac`

## callees

- `0x18000cfc0`
- `0x1800158d4`
- `0x180017d20`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes2D>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x398081F, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
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
0x1800158d4  push    rbx
0x1800158d6  push    rbp
0x1800158d7  push    rsi
0x1800158d8  push    rdi
0x1800158d9  sub     rsp, 28h
0x1800158dd  mov     ecx, 398081Fh; this
0x1800158e2  mov     rbx, rdx
0x1800158e5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800158ea  mov     edx, eax
0x1800158ec  mov     qword ptr [rbx], 0
0x1800158f3  and     edx, 0FFFFFF3Fh
0x1800158f9  mov     ecx, eax
0x1800158fb  and     eax, 80h
0x180015900  mov     r8d, edx
0x180015903  and     r8d, 3
0x180015907  mov     ebp, 40h ; '@'
0x18001590c  shl     r8d, 2
0x180015910  and     ecx, ebp
0x180015912  or      r8d, ecx
0x180015915  shl     r8d, 2
0x180015919  or      r8d, eax
0x18001591c  shl     r8d, 3
0x180015920  test    edx, edx
0x180015922  jnz     short loc_180015928
0x180015924  mov     eax, ebp
0x180015926  jmp     short loc_180015930
0x180015928  xor     eax, eax
0x18001592a  cmp     edx, 2
0x18001592d  cmovz   eax, ebp
0x180015930  or      r8d, eax
0x180015933  mov     edi, 1
0x180015938  mov     [rbx], r8d
0x18001593b  bt      r8d, 0Ah
0x180015940  jnb     short loc_180015950
0x180015942  cmp     r8d, 800h
0x180015949  jb      short loc_180015950
0x18001594b  mov     sil, dil
0x18001594e  jmp     short loc_18001595A
0x180015950  xor     sil, sil
0x180015953  xor     al, al
0x180015955  test    bpl, r8b
0x180015958  jz      short loc_180015973
0x18001595a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x180015961  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x180015966  test    sil, sil
0x180015969  jz      short loc_180015973
0x18001596b  test    al, al
0x18001596d  jnz     short loc_180015973
0x18001596f  btr     dword ptr [rbx], 0Ah
0x180015973  mov     ecx, [rbx]
0x180015975  test    bpl, cl
0x180015978  jz      short loc_18001597E
0x18001597a  test    al, al
0x18001597c  jnz     short loc_180015980
0x18001597e  xor     edi, edi
0x180015980  and     ecx, 0FFFFFFFEh
0x180015983  mov     rax, rbx
0x180015986  or      ecx, edi
0x180015988  mov     [rbx], ecx
0x18001598a  add     rsp, 28h
0x18001598e  pop     rdi
0x18001598f  pop     rsi
0x180015990  pop     rbp
0x180015991  pop     rbx
0x180015992  retn
```
