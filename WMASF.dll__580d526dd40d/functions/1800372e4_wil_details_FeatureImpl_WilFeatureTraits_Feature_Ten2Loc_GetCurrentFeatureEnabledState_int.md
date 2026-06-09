# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800372e4`
- end: `0x1800373c2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036b60`

## callees

- `0x1800372e4`
- `0x180039f60`
- `0x18003bc40`
- `0x18003bf3c`

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
0x1800372e4  push    rbx
0x1800372e6  push    rbp
0x1800372e7  push    rsi
0x1800372e8  push    rdi
0x1800372e9  sub     rsp, 28h
0x1800372ed  mov     ecx, 38419CAh; this
0x1800372f2  mov     rbx, rdx
0x1800372f5  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800372fa  mov     edx, eax
0x1800372fc  mov     qword ptr [rbx], 0
0x180037303  and     edx, 0FFFFFF3Fh
0x180037309  mov     ecx, eax
0x18003730b  and     eax, 80h
0x180037310  mov     r8d, edx
0x180037313  and     r8d, 3
0x180037317  mov     ebp, 40h ; '@'
0x18003731c  shl     r8d, 2
0x180037320  and     ecx, ebp
0x180037322  or      r8d, ecx
0x180037325  shl     r8d, 2
0x180037329  or      r8d, eax
0x18003732c  shl     r8d, 3
0x180037330  test    edx, edx
0x180037332  jnz     short loc_18003733A
0x180037334  mov     ecx, ebp
0x180037336  mov     edx, ebp
0x180037338  jmp     short loc_180037344
0x18003733a  xor     ecx, ecx
0x18003733c  cmp     edx, 2
0x18003733f  cmovz   ecx, ebp
0x180037342  mov     edx, ecx
0x180037344  mov     eax, r8d
0x180037347  mov     edi, 1
0x18003734c  or      eax, edx
0x18003734e  or      r8d, ecx
0x180037351  mov     [rbx], eax
0x180037353  bt      r8d, 0Ah
0x180037358  jnb     short loc_180037368
0x18003735a  cmp     r8d, 800h
0x180037361  jb      short loc_180037368
0x180037363  mov     sil, dil
0x180037366  jmp     short loc_180037372
0x180037368  xor     sil, sil
0x18003736b  xor     cl, cl
0x18003736d  test    bpl, r8b
0x180037370  jz      short loc_1800373A2
0x180037372  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x180037379  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18003737e  test    al, al
0x180037380  jz      short loc_180037393
0x180037382  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x180037389  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003738e  mov     cl, dil
0x180037391  jmp     short loc_180037395
0x180037393  xor     cl, cl
0x180037395  test    sil, sil
0x180037398  jz      short loc_1800373A2
0x18003739a  test    cl, cl
0x18003739c  jnz     short loc_1800373A2
0x18003739e  btr     dword ptr [rbx], 0Ah
0x1800373a2  mov     eax, [rbx]
0x1800373a4  test    bpl, al
0x1800373a7  jz      short loc_1800373AD
0x1800373a9  test    cl, cl
0x1800373ab  jnz     short loc_1800373AF
0x1800373ad  xor     edi, edi
0x1800373af  and     eax, 0FFFFFFFEh
0x1800373b2  or      eax, edi
0x1800373b4  mov     [rbx], eax
0x1800373b6  mov     rax, rbx
0x1800373b9  add     rsp, 28h
0x1800373bd  pop     rdi
0x1800373be  pop     rsi
0x1800373bf  pop     rbp
0x1800373c0  pop     rbx
0x1800373c1  retn
```
