# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c7e4`
- end: `0x14000c8c7`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000bec8`

## callees

- `0x14000c7e4`
- `0x14000fd8c`
- `0x140011454`
- `0x140011c54`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CAD, 3u, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl'::`2'::impl);
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
0x14000c7e4  push    rbx
0x14000c7e6  push    rbp
0x14000c7e7  push    rsi
0x14000c7e8  push    rdi
0x14000c7e9  sub     rsp, 28h
0x14000c7ed  mov     rbx, rdx
0x14000c7f0  mov     ecx, 3667CADh; this
0x14000c7f5  mov     edx, 3; unsigned int
0x14000c7fa  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c7ff  mov     edx, eax
0x14000c801  mov     qword ptr [rbx], 0
0x14000c808  and     edx, 0FFFFFF3Fh
0x14000c80e  mov     ecx, eax
0x14000c810  and     eax, 80h
0x14000c815  mov     r8d, edx
0x14000c818  and     r8d, 3
0x14000c81c  mov     ebp, 40h ; '@'
0x14000c821  shl     r8d, 2
0x14000c825  and     ecx, ebp
0x14000c827  or      r8d, ecx
0x14000c82a  shl     r8d, 2
0x14000c82e  or      r8d, eax
0x14000c831  shl     r8d, 3
0x14000c835  test    edx, edx
0x14000c837  jnz     short loc_14000C83F
0x14000c839  mov     ecx, ebp
0x14000c83b  mov     edx, ebp
0x14000c83d  jmp     short loc_14000C849
0x14000c83f  xor     ecx, ecx
0x14000c841  cmp     edx, 2
0x14000c844  cmovz   ecx, ebp
0x14000c847  mov     edx, ecx
0x14000c849  mov     eax, r8d
0x14000c84c  mov     edi, 1
0x14000c851  or      eax, edx
0x14000c853  or      r8d, ecx
0x14000c856  mov     [rbx], eax
0x14000c858  bt      r8d, 0Ah
0x14000c85d  jnb     short loc_14000C86D
0x14000c85f  cmp     r8d, 800h
0x14000c866  jb      short loc_14000C86D
0x14000c868  mov     sil, dil
0x14000c86b  jmp     short loc_14000C877
0x14000c86d  xor     sil, sil
0x14000c870  xor     cl, cl
0x14000c872  test    bpl, r8b
0x14000c875  jz      short loc_14000C8A7
0x14000c877  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ValAccTest@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest> `wil::Feature<__WilFeatureTraits_Feature_ValAccTest>::GetImpl(void)'::`2'::impl
0x14000c87e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::__private_IsEnabled(wil::ReportingKind)
0x14000c883  test    al, al
0x14000c885  jz      short loc_14000C898
0x14000c887  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetImpl(void)'::`2'::impl
0x14000c88e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000c893  mov     cl, dil
0x14000c896  jmp     short loc_14000C89A
0x14000c898  xor     cl, cl
0x14000c89a  test    sil, sil
0x14000c89d  jz      short loc_14000C8A7
0x14000c89f  test    cl, cl
0x14000c8a1  jnz     short loc_14000C8A7
0x14000c8a3  btr     dword ptr [rbx], 0Ah
0x14000c8a7  mov     eax, [rbx]
0x14000c8a9  test    bpl, al
0x14000c8ac  jz      short loc_14000C8B2
0x14000c8ae  test    cl, cl
0x14000c8b0  jnz     short loc_14000C8B4
0x14000c8b2  xor     edi, edi
0x14000c8b4  and     eax, 0FFFFFFFEh
0x14000c8b7  or      eax, edi
0x14000c8b9  mov     [rbx], eax
0x14000c8bb  mov     rax, rbx
0x14000c8be  add     rsp, 28h
0x14000c8c2  pop     rdi
0x14000c8c3  pop     rsi
0x14000c8c4  pop     rbp
0x14000c8c5  pop     rbx
0x14000c8c6  retn
```
