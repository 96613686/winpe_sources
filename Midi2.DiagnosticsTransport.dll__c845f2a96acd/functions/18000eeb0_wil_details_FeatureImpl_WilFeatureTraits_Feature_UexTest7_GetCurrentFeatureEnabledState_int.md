# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000eeb0`
- end: `0x18000f019`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000e5b0`

## callees

- `0x18000df48`
- `0x18000eeb0`
- `0x18000fbd4`
- `0x180010118`
- `0x180013010`

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
  __int64 v13; // rcx
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
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18001A868,
      0x37E2881u,
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
0x18000eeb0  mov     [rsp+arg_10], rbx
0x18000eeb5  mov     [rsp+arg_0], rcx
0x18000eeba  push    rbp
0x18000eebb  push    rsi
0x18000eebc  push    rdi
0x18000eebd  sub     rsp, 40h
0x18000eec1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000eec8  mov     rbx, rdx
0x18000eecb  test    rax, rax
0x18000eece  jz      short loc_18000EEE3
0x18000eed0  mov     edx, 3
0x18000eed5  mov     ecx, 38419DDh
0x18000eeda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eedf  mov     edx, eax
0x18000eee1  jmp     short loc_18000EEF1
0x18000eee3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000eeea  test    rax, rax
0x18000eeed  jnz     short loc_18000EED0
0x18000eeef  xor     edx, edx
0x18000eef1  mov     r8d, edx
0x18000eef4  mov     qword ptr [rbx], 0
0x18000eefb  and     r8d, 0FFFFFF3Fh
0x18000ef02  mov     eax, edx
0x18000ef04  and     edx, 80h
0x18000ef0a  mov     ecx, r8d
0x18000ef0d  and     ecx, 3
0x18000ef10  mov     ebp, 40h ; '@'
0x18000ef15  shl     ecx, 2
0x18000ef18  and     eax, ebp
0x18000ef1a  or      ecx, eax
0x18000ef1c  shl     ecx, 2
0x18000ef1f  or      ecx, edx
0x18000ef21  shl     ecx, 3
0x18000ef24  test    r8d, r8d
0x18000ef27  jnz     short loc_18000EF30
0x18000ef29  mov     edx, ebp
0x18000ef2b  mov     r8d, ebp
0x18000ef2e  jmp     short loc_18000EF3C
0x18000ef30  xor     edx, edx
0x18000ef32  cmp     r8d, 2
0x18000ef36  cmovz   edx, ebp
0x18000ef39  mov     r8d, edx
0x18000ef3c  mov     eax, ecx
0x18000ef3e  mov     edi, 1
0x18000ef43  or      eax, r8d
0x18000ef46  or      ecx, edx
0x18000ef48  mov     [rbx], eax
0x18000ef4a  bt      ecx, 0Ah
0x18000ef4e  jnb     short loc_18000EF5D
0x18000ef50  cmp     ecx, 800h
0x18000ef56  jb      short loc_18000EF5D
0x18000ef58  mov     sil, dil
0x18000ef5b  jmp     short loc_18000EF6B
0x18000ef5d  xor     sil, sil
0x18000ef60  xor     dl, dl
0x18000ef62  test    bpl, cl
0x18000ef65  jz      loc_18000EFF5
0x18000ef6b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18000ef72  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18000ef77  test    al, al
0x18000ef79  jz      short loc_18000EFE6
0x18000ef7b  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000ef82  mov     r8d, [rax]
0x18000ef85  test    r8b, 4
0x18000ef89  jnz     short loc_18000EFA0
0x18000ef8b  lea     rdx, [rsp+58h+arg_8]
0x18000ef90  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18000ef95  mov     rcx, [rax]
0x18000ef98  mov     [rsp+58h+arg_8], rcx
0x18000ef9d  mov     r8d, ecx
0x18000efa0  xor     eax, eax
0x18000efa2  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000efa9  mov     r9d, r8d
0x18000efac  mov     [rsp+58h+var_28], eax
0x18000efb0  mov     dword ptr [rsp+58h+arg_0], eax
0x18000efb4  lea     rcx, qword_18001A868
0x18000efbb  shr     r9d, 0Bh
0x18000efbf  lea     rax, [rsp+58h+arg_0]
0x18000efc4  shr     r8d, 0Ah
0x18000efc8  and     r9d, edi
0x18000efcb  and     r8d, edi
0x18000efce  mov     [rsp+58h+var_30], edi
0x18000efd2  mov     edx, 37E2881h
0x18000efd7  mov     [rsp+58h+var_38], rax
0x18000efdc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000efe1  mov     dl, dil
0x18000efe4  jmp     short loc_18000EFE8
0x18000efe6  xor     dl, dl
0x18000efe8  test    sil, sil
0x18000efeb  jz      short loc_18000EFF5
0x18000efed  test    dl, dl
0x18000efef  jnz     short loc_18000EFF5
0x18000eff1  btr     dword ptr [rbx], 0Ah
0x18000eff5  mov     eax, [rbx]
0x18000eff7  test    bpl, al
0x18000effa  jz      short loc_18000F000
0x18000effc  test    dl, dl
0x18000effe  jnz     short loc_18000F002
0x18000f000  xor     edi, edi
0x18000f002  and     eax, 0FFFFFFFEh
0x18000f005  or      eax, edi
0x18000f007  mov     [rbx], eax
0x18000f009  mov     rax, rbx
0x18000f00c  mov     rbx, [rsp+58h+arg_10]
0x18000f011  add     rsp, 40h
0x18000f015  pop     rdi
0x18000f016  pop     rsi
0x18000f017  pop     rbp
0x18000f018  retn
```
