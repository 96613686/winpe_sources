# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c3c8`
- end: `0x14000c487`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000b65c`

## callees

- `0x14000c3c8`
- `0x140011454`
- `0x140011ba0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCurrentFeatureEnabledState(
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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x380FE3A, 1u, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
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
0x14000c3c8  push    rbx
0x14000c3ca  push    rbp
0x14000c3cb  push    rsi
0x14000c3cc  push    rdi
0x14000c3cd  sub     rsp, 28h
0x14000c3d1  mov     rbx, rdx
0x14000c3d4  mov     edi, 1
0x14000c3d9  mov     edx, edi; unsigned int
0x14000c3db  mov     ecx, 380FE3Ah; this
0x14000c3e0  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c3e5  mov     edx, eax
0x14000c3e7  mov     qword ptr [rbx], 0
0x14000c3ee  and     edx, 0FFFFFF3Fh
0x14000c3f4  lea     ebp, [rdi+3Fh]
0x14000c3f7  mov     ecx, eax
0x14000c3f9  mov     r8d, edx
0x14000c3fc  and     r8d, 3
0x14000c400  and     ecx, ebp
0x14000c402  shl     r8d, 2
0x14000c406  and     eax, 80h
0x14000c40b  or      r8d, ecx
0x14000c40e  shl     r8d, 2
0x14000c412  or      r8d, eax
0x14000c415  shl     r8d, 3
0x14000c419  test    edx, edx
0x14000c41b  jnz     short loc_14000C421
0x14000c41d  mov     eax, ebp
0x14000c41f  jmp     short loc_14000C429
0x14000c421  xor     eax, eax
0x14000c423  cmp     edx, 2
0x14000c426  cmovz   eax, ebp
0x14000c429  or      r8d, eax
0x14000c42c  mov     [rbx], r8d
0x14000c42f  bt      r8d, 0Ah
0x14000c434  jnb     short loc_14000C444
0x14000c436  cmp     r8d, 800h
0x14000c43d  jb      short loc_14000C444
0x14000c43f  mov     sil, dil
0x14000c442  jmp     short loc_14000C44E
0x14000c444  xor     sil, sil
0x14000c447  xor     al, al
0x14000c449  test    bpl, r8b
0x14000c44c  jz      short loc_14000C467
0x14000c44e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x14000c455  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x14000c45a  test    sil, sil
0x14000c45d  jz      short loc_14000C467
0x14000c45f  test    al, al
0x14000c461  jnz     short loc_14000C467
0x14000c463  btr     dword ptr [rbx], 0Ah
0x14000c467  mov     ecx, [rbx]
0x14000c469  test    bpl, cl
0x14000c46c  jz      short loc_14000C472
0x14000c46e  test    al, al
0x14000c470  jnz     short loc_14000C474
0x14000c472  xor     edi, edi
0x14000c474  and     ecx, 0FFFFFFFEh
0x14000c477  mov     rax, rbx
0x14000c47a  or      ecx, edi
0x14000c47c  mov     [rbx], ecx
0x14000c47e  add     rsp, 28h
0x14000c482  pop     rdi
0x14000c483  pop     rsi
0x14000c484  pop     rbp
0x14000c485  pop     rbx
0x14000c486  retn
```
