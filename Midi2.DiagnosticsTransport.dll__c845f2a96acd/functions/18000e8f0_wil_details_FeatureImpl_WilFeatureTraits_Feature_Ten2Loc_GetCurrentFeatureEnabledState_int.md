# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000e8f0`
- end: `0x18000ea59`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e230`

## callees

- `0x18000ddd4`
- `0x18000e8f0`
- `0x18000fbd4`
- `0x180010250`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989002, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001A878,
      0x37E287Eu,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18000e8f0  mov     [rsp+arg_10], rbx
0x18000e8f5  mov     [rsp+arg_0], rcx
0x18000e8fa  push    rbp
0x18000e8fb  push    rsi
0x18000e8fc  push    rdi
0x18000e8fd  sub     rsp, 40h
0x18000e901  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e908  mov     rbx, rdx
0x18000e90b  test    rax, rax
0x18000e90e  jz      short loc_18000E923
0x18000e910  mov     edx, 3
0x18000e915  mov     ecx, 38419CAh
0x18000e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91f  mov     edx, eax
0x18000e921  jmp     short loc_18000E931
0x18000e923  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e92a  test    rax, rax
0x18000e92d  jnz     short loc_18000E910
0x18000e92f  xor     edx, edx
0x18000e931  mov     r8d, edx
0x18000e934  mov     qword ptr [rbx], 0
0x18000e93b  and     r8d, 0FFFFFF3Fh
0x18000e942  mov     eax, edx
0x18000e944  and     edx, 80h
0x18000e94a  mov     ecx, r8d
0x18000e94d  and     ecx, 3
0x18000e950  mov     ebp, 40h ; '@'
0x18000e955  shl     ecx, 2
0x18000e958  and     eax, ebp
0x18000e95a  or      ecx, eax
0x18000e95c  shl     ecx, 2
0x18000e95f  or      ecx, edx
0x18000e961  shl     ecx, 3
0x18000e964  test    r8d, r8d
0x18000e967  jnz     short loc_18000E970
0x18000e969  mov     edx, ebp
0x18000e96b  mov     r8d, ebp
0x18000e96e  jmp     short loc_18000E97C
0x18000e970  xor     edx, edx
0x18000e972  cmp     r8d, 2
0x18000e976  cmovz   edx, ebp
0x18000e979  mov     r8d, edx
0x18000e97c  mov     eax, ecx
0x18000e97e  mov     edi, 1
0x18000e983  or      eax, r8d
0x18000e986  or      ecx, edx
0x18000e988  mov     [rbx], eax
0x18000e98a  bt      ecx, 0Ah
0x18000e98e  jnb     short loc_18000E99D
0x18000e990  cmp     ecx, 800h
0x18000e996  jb      short loc_18000E99D
0x18000e998  mov     sil, dil
0x18000e99b  jmp     short loc_18000E9AB
0x18000e99d  xor     sil, sil
0x18000e9a0  xor     dl, dl
0x18000e9a2  test    bpl, cl
0x18000e9a5  jz      loc_18000EA35
0x18000e9ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x18000e9b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x18000e9b7  test    al, al
0x18000e9b9  jz      short loc_18000EA26
0x18000e9bb  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000e9c2  mov     r8d, [rax]
0x18000e9c5  test    r8b, 4
0x18000e9c9  jnz     short loc_18000E9E0
0x18000e9cb  lea     rdx, [rsp+58h+arg_8]
0x18000e9d0  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x18000e9d5  mov     rcx, [rax]
0x18000e9d8  mov     [rsp+58h+arg_8], rcx
0x18000e9dd  mov     r8d, ecx
0x18000e9e0  xor     eax, eax
0x18000e9e2  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000e9e9  mov     r9d, r8d
0x18000e9ec  mov     [rsp+58h+var_28], eax
0x18000e9f0  mov     dword ptr [rsp+58h+arg_0], eax
0x18000e9f4  lea     rcx, qword_18001A878
0x18000e9fb  shr     r9d, 0Bh
0x18000e9ff  lea     rax, [rsp+58h+arg_0]
0x18000ea04  shr     r8d, 0Ah
0x18000ea08  and     r9d, edi
0x18000ea0b  and     r8d, edi
0x18000ea0e  mov     [rsp+58h+var_30], edi
0x18000ea12  mov     edx, 37E287Eh
0x18000ea17  mov     [rsp+58h+var_38], rax
0x18000ea1c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000ea21  mov     dl, dil
0x18000ea24  jmp     short loc_18000EA28
0x18000ea26  xor     dl, dl
0x18000ea28  test    sil, sil
0x18000ea2b  jz      short loc_18000EA35
0x18000ea2d  test    dl, dl
0x18000ea2f  jnz     short loc_18000EA35
0x18000ea31  btr     dword ptr [rbx], 0Ah
0x18000ea35  mov     eax, [rbx]
0x18000ea37  test    bpl, al
0x18000ea3a  jz      short loc_18000EA40
0x18000ea3c  test    dl, dl
0x18000ea3e  jnz     short loc_18000EA42
0x18000ea40  xor     edi, edi
0x18000ea42  and     eax, 0FFFFFFFEh
0x18000ea45  or      eax, edi
0x18000ea47  mov     [rbx], eax
0x18000ea49  mov     rax, rbx
0x18000ea4c  mov     rbx, [rsp+58h+arg_10]
0x18000ea51  add     rsp, 40h
0x18000ea55  pop     rdi
0x18000ea56  pop     rsi
0x18000ea57  pop     rbp
0x18000ea58  retn
```
