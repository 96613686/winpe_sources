# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800223b4`
- end: `0x180022539`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `389`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180021750`

## callees

- `0x180011c30`
- `0x18001a6e4`
- `0x180020a58`
- `0x180021830`
- `0x1800223b4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // r8d
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // r8d
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, 3u, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180041F08, 57048226, (v12 >> 10) & 1, (v12 >> 11) & 1, &v16, 1, 0);
    v14 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180041B90, 45036792, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x1800223b4  mov     [rsp-18h+arg_10], rbx
0x1800223b9  mov     [rsp-18h+arg_0], rcx
0x1800223be  push    rbp
0x1800223bf  push    rdi
0x1800223c0  push    r14
0x1800223c2  mov     rbp, rsp
0x1800223c5  sub     rsp, 40h
0x1800223c9  mov     rdi, rdx
0x1800223cc  mov     ecx, 3667CA7h; this
0x1800223d1  mov     edx, 3; unsigned int
0x1800223d6  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800223db  mov     r8d, eax
0x1800223de  mov     qword ptr [rdi], 0
0x1800223e5  and     r8d, 0FFFFFF3Fh
0x1800223ec  mov     ecx, eax
0x1800223ee  and     eax, 80h
0x1800223f3  mov     edx, r8d
0x1800223f6  and     edx, 3
0x1800223f9  mov     r14d, 40h ; '@'
0x1800223ff  shl     edx, 2
0x180022402  and     ecx, r14d
0x180022405  or      edx, ecx
0x180022407  shl     edx, 2
0x18002240a  or      edx, eax
0x18002240c  shl     edx, 3
0x18002240f  test    r8d, r8d
0x180022412  jnz     short loc_18002241C
0x180022414  mov     ecx, r14d
0x180022417  mov     r8d, r14d
0x18002241a  jmp     short loc_180022429
0x18002241c  xor     ecx, ecx
0x18002241e  cmp     r8d, 2
0x180022422  cmovz   ecx, r14d
0x180022426  mov     r8d, ecx
0x180022429  mov     eax, edx
0x18002242b  mov     ebx, 1
0x180022430  or      eax, r8d
0x180022433  or      edx, ecx
0x180022435  mov     [rdi], eax
0x180022437  bt      edx, 0Ah
0x18002243b  jnb     short loc_180022445
0x18002243d  cmp     edx, 800h
0x180022443  jnb     short loc_180022450
0x180022445  xor     cl, cl
0x180022447  test    r14b, dl
0x18002244a  jz      loc_180022514
0x180022450  mov     rax, cs:Feature_ValLabTest__descriptor
0x180022457  mov     r8d, [rax]
0x18002245a  test    r8b, 4
0x18002245e  jnz     short loc_180022473
0x180022460  lea     rdx, [rbp+arg_8]
0x180022464  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x180022469  mov     rcx, [rax]
0x18002246c  mov     [rbp+arg_8], rcx
0x180022470  mov     r8d, ecx
0x180022473  xor     eax, eax
0x180022475  mov     word ptr [rbp+arg_0+4], 3
0x18002247b  mov     r9d, r8d
0x18002247e  mov     [rsp+40h+var_10], eax
0x180022482  mov     dword ptr [rbp+arg_0], eax
0x180022485  lea     rcx, qword_180041F08
0x18002248c  shr     r9d, 0Bh
0x180022490  lea     rax, [rbp+arg_0]
0x180022494  shr     r8d, 0Ah
0x180022498  and     r9d, ebx
0x18002249b  and     r8d, ebx
0x18002249e  mov     [rsp+40h+var_18], ebx
0x1800224a2  mov     edx, 3667CA2h
0x1800224a7  mov     [rsp+40h+var_20], rax
0x1800224ac  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800224b1  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800224b8  mov     r8d, [rax]
0x1800224bb  test    r8b, 4
0x1800224bf  jnz     short loc_1800224D4
0x1800224c1  lea     rdx, [rbp+arg_8]
0x1800224c5  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x1800224ca  mov     rcx, [rax]
0x1800224cd  mov     [rbp+arg_8], rcx
0x1800224d1  mov     r8d, ecx
0x1800224d4  xor     eax, eax
0x1800224d6  mov     word ptr [rbp+arg_0+4], 3
0x1800224dc  mov     r9d, r8d
0x1800224df  mov     [rsp+40h+var_10], eax
0x1800224e3  mov     dword ptr [rbp+arg_0], eax
0x1800224e6  lea     rcx, qword_180041B90
0x1800224ed  shr     r9d, 0Bh
0x1800224f1  lea     rax, [rbp+arg_0]
0x1800224f5  shr     r8d, 0Ah
0x1800224f9  and     r9d, ebx
0x1800224fc  and     r8d, ebx
0x1800224ff  mov     [rsp+40h+var_18], ebx
0x180022503  mov     edx, 2AF34F8h
0x180022508  mov     [rsp+40h+var_20], rax
0x18002250d  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022512  mov     cl, bl
0x180022514  mov     eax, [rdi]
0x180022516  test    r14b, al
0x180022519  jz      short loc_18002251F
0x18002251b  test    cl, cl
0x18002251d  jnz     short loc_180022521
0x18002251f  xor     ebx, ebx
0x180022521  and     eax, 0FFFFFFFEh
0x180022524  or      eax, ebx
0x180022526  mov     rbx, [rsp+40h+arg_10]
0x18002252b  mov     [rdi], eax
0x18002252d  mov     rax, rdi
0x180022530  add     rsp, 40h
0x180022534  pop     r14
0x180022536  pop     rdi
0x180022537  pop     rbp
0x180022538  retn
```
