# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000c39c`
- end: `0x18000c4bc`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `288`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c1dc`

## callees

- `0x18000c088`
- `0x18000c39c`
- `0x18000cc60`
- `0x18000cfc0`

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
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x2E30A37, (unsigned int)a2, a3, a4);
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
    wil::details::ReportUsageToService(&qword_180027B50, 49453572, (v12 >> 10) & 1, (v12 >> 11) & 1, &v14, 1, 0);
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
0x18000c39c  mov     [rsp+arg_10], rbx
0x18000c3a1  mov     [rsp+arg_18], rsi
0x18000c3a6  mov     [rsp+arg_0], rcx
0x18000c3ab  push    rdi
0x18000c3ac  sub     rsp, 40h
0x18000c3b0  mov     ecx, 2E30A37h; this
0x18000c3b5  mov     rdi, rdx
0x18000c3b8  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000c3bd  mov     edx, eax
0x18000c3bf  mov     qword ptr [rdi], 0
0x18000c3c6  and     edx, 0FFFFFF3Fh
0x18000c3cc  mov     ecx, eax
0x18000c3ce  and     eax, 80h
0x18000c3d3  mov     r8d, edx
0x18000c3d6  and     r8d, 3
0x18000c3da  mov     esi, 40h ; '@'
0x18000c3df  shl     r8d, 2
0x18000c3e3  and     ecx, esi
0x18000c3e5  or      r8d, ecx
0x18000c3e8  shl     r8d, 2
0x18000c3ec  or      r8d, eax
0x18000c3ef  shl     r8d, 3
0x18000c3f3  test    edx, edx
0x18000c3f5  jnz     short loc_18000C3FD
0x18000c3f7  mov     ecx, esi
0x18000c3f9  mov     edx, esi
0x18000c3fb  jmp     short loc_18000C407
0x18000c3fd  xor     ecx, ecx
0x18000c3ff  cmp     edx, 2
0x18000c402  cmovz   ecx, esi
0x18000c405  mov     edx, ecx
0x18000c407  mov     eax, r8d
0x18000c40a  mov     ebx, 1
0x18000c40f  or      eax, edx
0x18000c411  or      r8d, ecx
0x18000c414  mov     [rdi], eax
0x18000c416  bt      r8d, 0Ah
0x18000c41b  jnb     short loc_18000C426
0x18000c41d  cmp     r8d, 800h
0x18000c424  jnb     short loc_18000C42D
0x18000c426  xor     cl, cl
0x18000c428  test    sil, r8b
0x18000c42b  jz      short loc_18000C495
0x18000c42d  mov     rax, cs:Feature_Standalone_Future__descriptor
0x18000c434  mov     r8d, [rax]
0x18000c437  test    r8b, 4
0x18000c43b  jnz     short loc_18000C452
0x18000c43d  lea     rdx, [rsp+48h+arg_8]
0x18000c442  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x18000c447  mov     rcx, [rax]
0x18000c44a  mov     [rsp+48h+arg_8], rcx
0x18000c44f  mov     r8d, ecx
0x18000c452  xor     eax, eax
0x18000c454  mov     word ptr [rsp+48h+arg_0+4], 3
0x18000c45b  mov     r9d, r8d
0x18000c45e  mov     [rsp+48h+var_18], eax
0x18000c462  mov     dword ptr [rsp+48h+arg_0], eax
0x18000c466  lea     rcx, qword_180027B50
0x18000c46d  shr     r9d, 0Bh
0x18000c471  lea     rax, [rsp+48h+arg_0]
0x18000c476  shr     r8d, 0Ah
0x18000c47a  and     r9d, ebx
0x18000c47d  and     r8d, ebx
0x18000c480  mov     [rsp+48h+var_20], ebx
0x18000c484  mov     edx, 2F29A04h
0x18000c489  mov     [rsp+48h+var_28], rax
0x18000c48e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c493  mov     cl, bl
0x18000c495  mov     eax, [rdi]
0x18000c497  test    sil, al
0x18000c49a  jz      short loc_18000C4A0
0x18000c49c  test    cl, cl
0x18000c49e  jnz     short loc_18000C4A2
0x18000c4a0  xor     ebx, ebx
0x18000c4a2  mov     rsi, [rsp+48h+arg_18]
0x18000c4a7  and     eax, 0FFFFFFFEh
0x18000c4aa  or      eax, ebx
0x18000c4ac  mov     rbx, [rsp+48h+arg_10]
0x18000c4b1  mov     [rdi], eax
0x18000c4b3  mov     rax, rdi
0x18000c4b6  add     rsp, 40h
0x18000c4ba  pop     rdi
0x18000c4bb  retn
```
