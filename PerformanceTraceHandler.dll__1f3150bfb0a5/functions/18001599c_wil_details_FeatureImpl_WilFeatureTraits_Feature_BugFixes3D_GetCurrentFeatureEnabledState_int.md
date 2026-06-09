# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001599c`
- end: `0x180015a5b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes3D@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014a8c`

## callees

- `0x18000cfc0`
- `0x18001599c`
- `0x180017dd4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes3D>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x39F1732, (unsigned int)a2, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl);
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
0x18001599c  push    rbx
0x18001599e  push    rbp
0x18001599f  push    rsi
0x1800159a0  push    rdi
0x1800159a1  sub     rsp, 28h
0x1800159a5  mov     ecx, 39F1732h; this
0x1800159aa  mov     rbx, rdx
0x1800159ad  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800159b2  mov     edx, eax
0x1800159b4  mov     qword ptr [rbx], 0
0x1800159bb  and     edx, 0FFFFFF3Fh
0x1800159c1  mov     ecx, eax
0x1800159c3  and     eax, 80h
0x1800159c8  mov     r8d, edx
0x1800159cb  and     r8d, 3
0x1800159cf  mov     ebp, 40h ; '@'
0x1800159d4  shl     r8d, 2
0x1800159d8  and     ecx, ebp
0x1800159da  or      r8d, ecx
0x1800159dd  shl     r8d, 2
0x1800159e1  or      r8d, eax
0x1800159e4  shl     r8d, 3
0x1800159e8  test    edx, edx
0x1800159ea  jnz     short loc_1800159F0
0x1800159ec  mov     eax, ebp
0x1800159ee  jmp     short loc_1800159F8
0x1800159f0  xor     eax, eax
0x1800159f2  cmp     edx, 2
0x1800159f5  cmovz   eax, ebp
0x1800159f8  or      r8d, eax
0x1800159fb  mov     edi, 1
0x180015a00  mov     [rbx], r8d
0x180015a03  bt      r8d, 0Ah
0x180015a08  jnb     short loc_180015A18
0x180015a0a  cmp     r8d, 800h
0x180015a11  jb      short loc_180015A18
0x180015a13  mov     sil, dil
0x180015a16  jmp     short loc_180015A22
0x180015a18  xor     sil, sil
0x180015a1b  xor     al, al
0x180015a1d  test    bpl, r8b
0x180015a20  jz      short loc_180015A3B
0x180015a22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180015a29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180015a2e  test    sil, sil
0x180015a31  jz      short loc_180015A3B
0x180015a33  test    al, al
0x180015a35  jnz     short loc_180015A3B
0x180015a37  btr     dword ptr [rbx], 0Ah
0x180015a3b  mov     ecx, [rbx]
0x180015a3d  test    bpl, cl
0x180015a40  jz      short loc_180015A46
0x180015a42  test    al, al
0x180015a44  jnz     short loc_180015A48
0x180015a46  xor     edi, edi
0x180015a48  and     ecx, 0FFFFFFFEh
0x180015a4b  mov     rax, rbx
0x180015a4e  or      ecx, edi
0x180015a50  mov     [rbx], ecx
0x180015a52  add     rsp, 28h
0x180015a56  pop     rdi
0x180015a57  pop     rsi
0x180015a58  pop     rbp
0x180015a59  pop     rbx
0x180015a5a  retn
```
