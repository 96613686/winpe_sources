# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005f98`
- end: `0x180006076`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005434`

## callees

- `0x180005f98`
- `0x180008ca4`
- `0x18000a544`
- `0x18000a9e8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180005f98  push    rbx
0x180005f9a  push    rbp
0x180005f9b  push    rsi
0x180005f9c  push    rdi
0x180005f9d  sub     rsp, 28h
0x180005fa1  mov     ecx, 38419CAh; this
0x180005fa6  mov     rbx, rdx
0x180005fa9  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180005fae  mov     edx, eax
0x180005fb0  mov     qword ptr [rbx], 0
0x180005fb7  and     edx, 0FFFFFF3Fh
0x180005fbd  mov     ecx, eax
0x180005fbf  and     eax, 80h
0x180005fc4  mov     r8d, edx
0x180005fc7  and     r8d, 3
0x180005fcb  mov     ebp, 40h ; '@'
0x180005fd0  shl     r8d, 2
0x180005fd4  and     ecx, ebp
0x180005fd6  or      r8d, ecx
0x180005fd9  shl     r8d, 2
0x180005fdd  or      r8d, eax
0x180005fe0  shl     r8d, 3
0x180005fe4  test    edx, edx
0x180005fe6  jnz     short loc_180005FEE
0x180005fe8  mov     ecx, ebp
0x180005fea  mov     edx, ebp
0x180005fec  jmp     short loc_180005FF8
0x180005fee  xor     ecx, ecx
0x180005ff0  cmp     edx, 2
0x180005ff3  cmovz   ecx, ebp
0x180005ff6  mov     edx, ecx
0x180005ff8  mov     eax, r8d
0x180005ffb  mov     edi, 1
0x180006000  or      eax, edx
0x180006002  or      r8d, ecx
0x180006005  mov     [rbx], eax
0x180006007  bt      r8d, 0Ah
0x18000600c  jnb     short loc_18000601C
0x18000600e  cmp     r8d, 800h
0x180006015  jb      short loc_18000601C
0x180006017  mov     sil, dil
0x18000601a  jmp     short loc_180006026
0x18000601c  xor     sil, sil
0x18000601f  xor     cl, cl
0x180006021  test    bpl, r8b
0x180006024  jz      short loc_180006056
0x180006026  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18000602d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x180006032  test    al, al
0x180006034  jz      short loc_180006047
0x180006036  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x18000603d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180006042  mov     cl, dil
0x180006045  jmp     short loc_180006049
0x180006047  xor     cl, cl
0x180006049  test    sil, sil
0x18000604c  jz      short loc_180006056
0x18000604e  test    cl, cl
0x180006050  jnz     short loc_180006056
0x180006052  btr     dword ptr [rbx], 0Ah
0x180006056  mov     eax, [rbx]
0x180006058  test    bpl, al
0x18000605b  jz      short loc_180006061
0x18000605d  test    cl, cl
0x18000605f  jnz     short loc_180006063
0x180006061  xor     edi, edi
0x180006063  and     eax, 0FFFFFFFEh
0x180006066  or      eax, edi
0x180006068  mov     [rbx], eax
0x18000606a  mov     rax, rbx
0x18000606d  add     rsp, 28h
0x180006071  pop     rdi
0x180006072  pop     rsi
0x180006073  pop     rbp
0x180006074  pop     rbx
0x180006075  retn
```
