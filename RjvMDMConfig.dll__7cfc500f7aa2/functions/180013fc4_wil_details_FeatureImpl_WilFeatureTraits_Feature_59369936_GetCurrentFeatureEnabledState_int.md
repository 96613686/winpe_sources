# wil::details::FeatureImpl<__WilFeatureTraits_Feature_59369936>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013fc4`
- end: `0x180014089`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_59369936@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012e9c`

## callees

- `0x180011098`
- `0x180013fc4`
- `0x180015afc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_59369936>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x389E9D0, 3u, a3, a4);
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
0x180013fc4  push    rbx
0x180013fc6  push    rbp
0x180013fc7  push    rsi
0x180013fc8  push    rdi
0x180013fc9  sub     rsp, 28h
0x180013fcd  mov     rbx, rdx
0x180013fd0  mov     ecx, 389E9D0h; this
0x180013fd5  mov     edx, 3; unsigned int
0x180013fda  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180013fdf  mov     edx, eax
0x180013fe1  mov     qword ptr [rbx], 0
0x180013fe8  and     edx, 0FFFFFF3Fh
0x180013fee  mov     ecx, eax
0x180013ff0  and     eax, 80h
0x180013ff5  mov     r8d, edx
0x180013ff8  and     r8d, 3
0x180013ffc  mov     ebp, 40h ; '@'
0x180014001  shl     r8d, 2
0x180014005  and     ecx, ebp
0x180014007  or      r8d, ecx
0x18001400a  shl     r8d, 2
0x18001400e  or      r8d, eax
0x180014011  shl     r8d, 3
0x180014015  test    edx, edx
0x180014017  jnz     short loc_18001401D
0x180014019  mov     eax, ebp
0x18001401b  jmp     short loc_180014025
0x18001401d  xor     eax, eax
0x18001401f  cmp     edx, 2
0x180014022  cmovz   eax, ebp
0x180014025  or      r8d, eax
0x180014028  mov     edi, 1
0x18001402d  mov     [rbx], r8d
0x180014030  bt      r8d, 0Ah
0x180014035  jnb     short loc_180014045
0x180014037  cmp     r8d, 800h
0x18001403e  jb      short loc_180014045
0x180014040  mov     sil, dil
0x180014043  jmp     short loc_18001404F
0x180014045  xor     sil, sil
0x180014048  xor     al, al
0x18001404a  test    bpl, r8b
0x18001404d  jz      short loc_180014068
0x18001404f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x180014056  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001405b  test    sil, sil
0x18001405e  jz      short loc_180014068
0x180014060  test    al, al
0x180014062  jnz     short loc_180014068
0x180014064  btr     dword ptr [rbx], 0Ah
0x180014068  mov     ecx, [rbx]
0x18001406a  test    bpl, cl
0x18001406d  jz      short loc_180014073
0x18001406f  test    al, al
0x180014071  jnz     short loc_180014075
0x180014073  xor     edi, edi
0x180014075  and     ecx, 0FFFFFFFEh
0x180014078  mov     rax, rbx
0x18001407b  or      ecx, edi
0x18001407d  mov     [rbx], ecx
0x18001407f  add     rsp, 28h
0x180014083  pop     rdi
0x180014084  pop     rsi
0x180014085  pop     rbp
0x180014086  pop     rbx
0x180014087  retn
```
