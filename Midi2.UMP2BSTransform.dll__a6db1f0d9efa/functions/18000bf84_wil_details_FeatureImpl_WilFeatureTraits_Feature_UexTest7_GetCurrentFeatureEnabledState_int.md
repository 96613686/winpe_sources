# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000bf84`
- end: `0x18000c0ed`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000b7f4`

## callees

- `0x18000b3e0`
- `0x18000bf84`
- `0x18000c804`
- `0x18000de18`
- `0x18000f010`

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
      (__int64)&qword_180015808,
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
0x18000bf84  mov     [rsp+arg_10], rbx
0x18000bf89  mov     [rsp+arg_0], rcx
0x18000bf8e  push    rbp
0x18000bf8f  push    rsi
0x18000bf90  push    rdi
0x18000bf91  sub     rsp, 40h
0x18000bf95  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000bf9c  mov     rbx, rdx
0x18000bf9f  test    rax, rax
0x18000bfa2  jz      short loc_18000BFB7
0x18000bfa4  mov     edx, 3
0x18000bfa9  mov     ecx, 38419DDh
0x18000bfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfb3  mov     edx, eax
0x18000bfb5  jmp     short loc_18000BFC5
0x18000bfb7  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000bfbe  test    rax, rax
0x18000bfc1  jnz     short loc_18000BFA4
0x18000bfc3  xor     edx, edx
0x18000bfc5  mov     r8d, edx
0x18000bfc8  mov     qword ptr [rbx], 0
0x18000bfcf  and     r8d, 0FFFFFF3Fh
0x18000bfd6  mov     eax, edx
0x18000bfd8  and     edx, 80h
0x18000bfde  mov     ecx, r8d
0x18000bfe1  and     ecx, 3
0x18000bfe4  mov     ebp, 40h ; '@'
0x18000bfe9  shl     ecx, 2
0x18000bfec  and     eax, ebp
0x18000bfee  or      ecx, eax
0x18000bff0  shl     ecx, 2
0x18000bff3  or      ecx, edx
0x18000bff5  shl     ecx, 3
0x18000bff8  test    r8d, r8d
0x18000bffb  jnz     short loc_18000C004
0x18000bffd  mov     edx, ebp
0x18000bfff  mov     r8d, ebp
0x18000c002  jmp     short loc_18000C010
0x18000c004  xor     edx, edx
0x18000c006  cmp     r8d, 2
0x18000c00a  cmovz   edx, ebp
0x18000c00d  mov     r8d, edx
0x18000c010  mov     eax, ecx
0x18000c012  mov     edi, 1
0x18000c017  or      eax, r8d
0x18000c01a  or      ecx, edx
0x18000c01c  mov     [rbx], eax
0x18000c01e  bt      ecx, 0Ah
0x18000c022  jnb     short loc_18000C031
0x18000c024  cmp     ecx, 800h
0x18000c02a  jb      short loc_18000C031
0x18000c02c  mov     sil, dil
0x18000c02f  jmp     short loc_18000C03F
0x18000c031  xor     sil, sil
0x18000c034  xor     dl, dl
0x18000c036  test    bpl, cl
0x18000c039  jz      loc_18000C0C9
0x18000c03f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18000c046  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18000c04b  test    al, al
0x18000c04d  jz      short loc_18000C0BA
0x18000c04f  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000c056  mov     r8d, [rax]
0x18000c059  test    r8b, 4
0x18000c05d  jnz     short loc_18000C074
0x18000c05f  lea     rdx, [rsp+58h+arg_8]
0x18000c064  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18000c069  mov     rcx, [rax]
0x18000c06c  mov     [rsp+58h+arg_8], rcx
0x18000c071  mov     r8d, ecx
0x18000c074  xor     eax, eax
0x18000c076  mov     word ptr [rsp+58h+arg_0+4], 3
0x18000c07d  mov     r9d, r8d
0x18000c080  mov     [rsp+58h+var_28], eax
0x18000c084  mov     dword ptr [rsp+58h+arg_0], eax
0x18000c088  lea     rcx, qword_180015808
0x18000c08f  shr     r9d, 0Bh
0x18000c093  lea     rax, [rsp+58h+arg_0]
0x18000c098  shr     r8d, 0Ah
0x18000c09c  and     r9d, edi
0x18000c09f  and     r8d, edi
0x18000c0a2  mov     [rsp+58h+var_30], edi
0x18000c0a6  mov     edx, 37E2881h
0x18000c0ab  mov     [rsp+58h+var_38], rax
0x18000c0b0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c0b5  mov     dl, dil
0x18000c0b8  jmp     short loc_18000C0BC
0x18000c0ba  xor     dl, dl
0x18000c0bc  test    sil, sil
0x18000c0bf  jz      short loc_18000C0C9
0x18000c0c1  test    dl, dl
0x18000c0c3  jnz     short loc_18000C0C9
0x18000c0c5  btr     dword ptr [rbx], 0Ah
0x18000c0c9  mov     eax, [rbx]
0x18000c0cb  test    bpl, al
0x18000c0ce  jz      short loc_18000C0D4
0x18000c0d0  test    dl, dl
0x18000c0d2  jnz     short loc_18000C0D6
0x18000c0d4  xor     edi, edi
0x18000c0d6  and     eax, 0FFFFFFFEh
0x18000c0d9  or      eax, edi
0x18000c0db  mov     [rbx], eax
0x18000c0dd  mov     rax, rbx
0x18000c0e0  mov     rbx, [rsp+58h+arg_10]
0x18000c0e5  add     rsp, 40h
0x18000c0e9  pop     rdi
0x18000c0ea  pop     rsi
0x18000c0eb  pop     rbp
0x18000c0ec  retn
```
