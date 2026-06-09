# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001f824`
- end: `0x18001f949`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001f67c`

## callees

- `0x180016330`
- `0x180017994`
- `0x18001f524`
- `0x18001f824`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, 3u, a3, a4);
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
    v12 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v15);
      v12 = v15;
    }
    WORD2(v14) = 3;
    LODWORD(v14) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18003CA20,
      0x2F29A04u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v14,
      1u,
      0);
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
0x18001f824  mov     [rsp+arg_10], rbx
0x18001f829  mov     [rsp+arg_18], rsi
0x18001f82e  mov     [rsp+arg_0], rcx
0x18001f833  push    rdi
0x18001f834  sub     rsp, 40h
0x18001f838  mov     rdi, rdx
0x18001f83b  mov     ecx, 2E30A37h; this
0x18001f840  mov     edx, 3; unsigned int
0x18001f845  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18001f84a  mov     edx, eax
0x18001f84c  mov     qword ptr [rdi], 0
0x18001f853  and     edx, 0FFFFFF3Fh
0x18001f859  mov     ecx, eax
0x18001f85b  and     eax, 80h
0x18001f860  mov     r8d, edx
0x18001f863  and     r8d, 3
0x18001f867  mov     esi, 40h ; '@'
0x18001f86c  shl     r8d, 2
0x18001f870  and     ecx, esi
0x18001f872  or      r8d, ecx
0x18001f875  shl     r8d, 2
0x18001f879  or      r8d, eax
0x18001f87c  shl     r8d, 3
0x18001f880  test    edx, edx
0x18001f882  jnz     short loc_18001F88A
0x18001f884  mov     ecx, esi
0x18001f886  mov     edx, esi
0x18001f888  jmp     short loc_18001F894
0x18001f88a  xor     ecx, ecx
0x18001f88c  cmp     edx, 2
0x18001f88f  cmovz   ecx, esi
0x18001f892  mov     edx, ecx
0x18001f894  mov     eax, r8d
0x18001f897  mov     ebx, 1
0x18001f89c  or      eax, edx
0x18001f89e  or      r8d, ecx
0x18001f8a1  mov     [rdi], eax
0x18001f8a3  bt      r8d, 0Ah
0x18001f8a8  jnb     short loc_18001F8B3
0x18001f8aa  cmp     r8d, 800h
0x18001f8b1  jnb     short loc_18001F8BA
0x18001f8b3  xor     cl, cl
0x18001f8b5  test    sil, r8b
0x18001f8b8  jz      short loc_18001F922
0x18001f8ba  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18001f8c1  mov     r8d, [rax]
0x18001f8c4  test    r8b, 4
0x18001f8c8  jnz     short loc_18001F8DF
0x18001f8ca  lea     rdx, [rsp+48h+arg_8]
0x18001f8cf  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18001f8d4  mov     rcx, [rax]
0x18001f8d7  mov     [rsp+48h+arg_8], rcx
0x18001f8dc  mov     r8d, ecx
0x18001f8df  xor     eax, eax
0x18001f8e1  mov     word ptr [rsp+48h+arg_0+4], 3
0x18001f8e8  mov     r9d, r8d
0x18001f8eb  mov     [rsp+48h+var_18], eax
0x18001f8ef  mov     dword ptr [rsp+48h+arg_0], eax
0x18001f8f3  lea     rcx, qword_18003CA20
0x18001f8fa  shr     r9d, 0Bh
0x18001f8fe  lea     rax, [rsp+48h+arg_0]
0x18001f903  shr     r8d, 0Ah
0x18001f907  and     r9d, ebx
0x18001f90a  and     r8d, ebx
0x18001f90d  mov     [rsp+48h+var_20], ebx
0x18001f911  mov     edx, 2F29A04h
0x18001f916  mov     [rsp+48h+var_28], rax
0x18001f91b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001f920  mov     cl, bl
0x18001f922  mov     eax, [rdi]
0x18001f924  test    sil, al
0x18001f927  jz      short loc_18001F92D
0x18001f929  test    cl, cl
0x18001f92b  jnz     short loc_18001F92F
0x18001f92d  xor     ebx, ebx
0x18001f92f  mov     rsi, [rsp+48h+arg_18]
0x18001f934  and     eax, 0FFFFFFFEh
0x18001f937  or      eax, ebx
0x18001f939  mov     rbx, [rsp+48h+arg_10]
0x18001f93e  mov     [rdi], eax
0x18001f940  mov     rax, rdi
0x18001f943  add     rsp, 40h
0x18001f947  pop     rdi
0x18001f948  retn
```
