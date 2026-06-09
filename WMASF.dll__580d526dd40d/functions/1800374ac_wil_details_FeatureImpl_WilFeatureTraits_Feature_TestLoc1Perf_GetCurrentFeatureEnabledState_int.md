# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800374ac`
- end: `0x18003758a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036d48`

## callees

- `0x1800374ac`
- `0x180039ec4`
- `0x18003bc40`
- `0x18003bf00`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419AC, (unsigned int)a2, a3, a4);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl'::`2'::impl);
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
0x1800374ac  push    rbx
0x1800374ae  push    rbp
0x1800374af  push    rsi
0x1800374b0  push    rdi
0x1800374b1  sub     rsp, 28h
0x1800374b5  mov     ecx, 38419ACh; this
0x1800374ba  mov     rbx, rdx
0x1800374bd  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800374c2  mov     edx, eax
0x1800374c4  mov     qword ptr [rbx], 0
0x1800374cb  and     edx, 0FFFFFF3Fh
0x1800374d1  mov     ecx, eax
0x1800374d3  and     eax, 80h
0x1800374d8  mov     r8d, edx
0x1800374db  and     r8d, 3
0x1800374df  mov     ebp, 40h ; '@'
0x1800374e4  shl     r8d, 2
0x1800374e8  and     ecx, ebp
0x1800374ea  or      r8d, ecx
0x1800374ed  shl     r8d, 2
0x1800374f1  or      r8d, eax
0x1800374f4  shl     r8d, 3
0x1800374f8  test    edx, edx
0x1800374fa  jnz     short loc_180037502
0x1800374fc  mov     ecx, ebp
0x1800374fe  mov     edx, ebp
0x180037500  jmp     short loc_18003750C
0x180037502  xor     ecx, ecx
0x180037504  cmp     edx, 2
0x180037507  cmovz   ecx, ebp
0x18003750a  mov     edx, ecx
0x18003750c  mov     eax, r8d
0x18003750f  mov     edi, 1
0x180037514  or      eax, edx
0x180037516  or      r8d, ecx
0x180037519  mov     [rbx], eax
0x18003751b  bt      r8d, 0Ah
0x180037520  jnb     short loc_180037530
0x180037522  cmp     r8d, 800h
0x180037529  jb      short loc_180037530
0x18003752b  mov     sil, dil
0x18003752e  jmp     short loc_18003753A
0x180037530  xor     sil, sil
0x180037533  xor     cl, cl
0x180037535  test    bpl, r8b
0x180037538  jz      short loc_18003756A
0x18003753a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180037541  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180037546  test    al, al
0x180037548  jz      short loc_18003755B
0x18003754a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetImpl(void)'::`2'::impl
0x180037551  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180037556  mov     cl, dil
0x180037559  jmp     short loc_18003755D
0x18003755b  xor     cl, cl
0x18003755d  test    sil, sil
0x180037560  jz      short loc_18003756A
0x180037562  test    cl, cl
0x180037564  jnz     short loc_18003756A
0x180037566  btr     dword ptr [rbx], 0Ah
0x18003756a  mov     eax, [rbx]
0x18003756c  test    bpl, al
0x18003756f  jz      short loc_180037575
0x180037571  test    cl, cl
0x180037573  jnz     short loc_180037577
0x180037575  xor     edi, edi
0x180037577  and     eax, 0FFFFFFFEh
0x18003757a  or      eax, edi
0x18003757c  mov     [rbx], eax
0x18003757e  mov     rax, rbx
0x180037581  add     rsp, 28h
0x180037585  pop     rdi
0x180037586  pop     rsi
0x180037587  pop     rbp
0x180037588  pop     rbx
0x180037589  retn
```
