# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000f594`
- end: `0x18000f6fd`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ed84`

## callees

- `0x18000e970`
- `0x18000f594`
- `0x1800120a8`
- `0x180013d74`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
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
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989021, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180026060, 58599553, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x18000f594  mov     [rsp+arg_10], rbx
0x18000f599  mov     [rsp+arg_0], rcx
0x18000f59e  push    rbp
0x18000f59f  push    rsi
0x18000f5a0  push    rdi
0x18000f5a1  sub     rsp, 40h
0x18000f5a5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000f5ac  mov     rbx, rdx
0x18000f5af  test    rax, rax
0x18000f5b2  jz      short loc_18000F5C7
0x18000f5b4  mov     edx, 3
0x18000f5b9  mov     ecx, 38419DDh
0x18000f5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5c3  mov     edx, eax
0x18000f5c5  jmp     short loc_18000F5D5
0x18000f5c7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000f5ce  test    rax, rax
0x18000f5d1  jnz     short loc_18000F5B4
0x18000f5d3  xor     edx, edx
0x18000f5d5  mov     r8d, edx
0x18000f5d8  mov     qword ptr [rbx], 0
0x18000f5df  and     r8d, 0FFFFFF3Fh
0x18000f5e6  mov     eax, edx
0x18000f5e8  and     edx, 80h
0x18000f5ee  mov     ecx, r8d
0x18000f5f1  and     ecx, 3
0x18000f5f4  mov     ebp, 40h ; '@'
0x18000f5f9  shl     ecx, 2
0x18000f5fc  and     eax, ebp
0x18000f5fe  or      ecx, eax
0x18000f600  shl     ecx, 2
0x18000f603  or      ecx, edx
0x18000f605  shl     ecx, 3
0x18000f608  test    r8d, r8d
0x18000f60b  jnz     short loc_18000F614
0x18000f60d  mov     edx, ebp
0x18000f60f  mov     r8d, ebp
0x18000f612  jmp     short loc_18000F620
0x18000f614  xor     edx, edx
0x18000f616  cmp     r8d, 2
0x18000f61a  cmovz   edx, ebp
0x18000f61d  mov     r8d, edx
0x18000f620  mov     eax, ecx
0x18000f622  mov     edi, 1
0x18000f627  or      eax, r8d
0x18000f62a  or      ecx, edx
0x18000f62c  mov     [rbx], eax
0x18000f62e  bt      ecx, 0Ah
0x18000f632  jnb     short loc_18000F641
0x18000f634  cmp     ecx, 800h
0x18000f63a  jb      short loc_18000F641
0x18000f63c  mov     sil, dil
0x18000f63f  jmp     short loc_18000F64F
0x18000f641  xor     sil, sil
0x18000f644  xor     dl, dl
0x18000f646  test    bpl, cl
0x18000f649  jz      loc_18000F6D9
0x18000f64f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18000f656  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18000f65b  test    al, al
0x18000f65d  jz      short loc_18000F6CA
0x18000f65f  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000f666  mov     r8d, [rax]
0x18000f669  test    r8b, 4
0x18000f66d  jnz     short loc_18000F684
0x18000f66f  lea     rdx, [rsp+58h+arg_8]
0x18000f674  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18000f679  mov     rcx, [rax]
0x18000f67c  mov     [rsp+58h+arg_8], rcx
0x18000f681  mov     r8d, ecx
0x18000f684  xor     eax, eax
0x18000f686  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000f68d  mov     r9d, r8d
0x18000f690  mov     [rsp+58h+var_28], eax
0x18000f694  mov     dword ptr [rsp+58h+arg_0], eax
0x18000f698  lea     rcx, qword_180026060
0x18000f69f  shr     r9d, 0Bh
0x18000f6a3  lea     rax, [rsp+58h+arg_0]
0x18000f6a8  shr     r8d, 0Ah
0x18000f6ac  and     r9d, edi
0x18000f6af  and     r8d, edi
0x18000f6b2  mov     [rsp+58h+var_30], edi
0x18000f6b6  mov     edx, 37E2881h
0x18000f6bb  mov     [rsp+58h+var_38], rax
0x18000f6c0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000f6c5  mov     dl, dil
0x18000f6c8  jmp     short loc_18000F6CC
0x18000f6ca  xor     dl, dl
0x18000f6cc  test    sil, sil
0x18000f6cf  jz      short loc_18000F6D9
0x18000f6d1  test    dl, dl
0x18000f6d3  jnz     short loc_18000F6D9
0x18000f6d5  btr     dword ptr [rbx], 0Ah
0x18000f6d9  mov     eax, [rbx]
0x18000f6db  test    bpl, al
0x18000f6de  jz      short loc_18000F6E4
0x18000f6e0  test    dl, dl
0x18000f6e2  jnz     short loc_18000F6E6
0x18000f6e4  xor     edi, edi
0x18000f6e6  and     eax, 0FFFFFFFEh
0x18000f6e9  or      eax, edi
0x18000f6eb  mov     [rbx], eax
0x18000f6ed  mov     rax, rbx
0x18000f6f0  mov     rbx, [rsp+58h+arg_10]
0x18000f6f5  add     rsp, 40h
0x18000f6f9  pop     rdi
0x18000f6fa  pop     rsi
0x18000f6fb  pop     rbp
0x18000f6fc  retn
```
