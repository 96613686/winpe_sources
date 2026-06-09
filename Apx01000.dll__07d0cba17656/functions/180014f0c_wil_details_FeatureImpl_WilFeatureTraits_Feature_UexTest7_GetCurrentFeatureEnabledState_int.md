# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014f0c`
- end: `0x180015075`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013fb8`

## callees

- `0x18000ab68`
- `0x180013950`
- `0x180014f0c`
- `0x1800154d8`
- `0x18002a010`

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
    wil::details::ReportUsageToService(&qword_1800337C8, 58599553, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180014f0c  mov     [rsp+arg_10], rbx
0x180014f11  mov     [rsp+arg_0], rcx
0x180014f16  push    rbp
0x180014f17  push    rsi
0x180014f18  push    rdi
0x180014f19  sub     rsp, 40h
0x180014f1d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014f24  mov     rbx, rdx
0x180014f27  test    rax, rax
0x180014f2a  jz      short loc_180014F3F
0x180014f2c  mov     edx, 3
0x180014f31  mov     ecx, 38419DDh
0x180014f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f3b  mov     edx, eax
0x180014f3d  jmp     short loc_180014F4D
0x180014f3f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014f46  test    rax, rax
0x180014f49  jnz     short loc_180014F2C
0x180014f4b  xor     edx, edx
0x180014f4d  mov     r8d, edx
0x180014f50  mov     qword ptr [rbx], 0
0x180014f57  and     r8d, 0FFFFFF3Fh
0x180014f5e  mov     eax, edx
0x180014f60  and     edx, 80h
0x180014f66  mov     ecx, r8d
0x180014f69  and     ecx, 3
0x180014f6c  mov     ebp, 40h ; '@'
0x180014f71  shl     ecx, 2
0x180014f74  and     eax, ebp
0x180014f76  or      ecx, eax
0x180014f78  shl     ecx, 2
0x180014f7b  or      ecx, edx
0x180014f7d  shl     ecx, 3
0x180014f80  test    r8d, r8d
0x180014f83  jnz     short loc_180014F8C
0x180014f85  mov     edx, ebp
0x180014f87  mov     r8d, ebp
0x180014f8a  jmp     short loc_180014F98
0x180014f8c  xor     edx, edx
0x180014f8e  cmp     r8d, 2
0x180014f92  cmovz   edx, ebp
0x180014f95  mov     r8d, edx
0x180014f98  mov     eax, ecx
0x180014f9a  mov     edi, 1
0x180014f9f  or      eax, r8d
0x180014fa2  or      ecx, edx
0x180014fa4  mov     [rbx], eax
0x180014fa6  bt      ecx, 0Ah
0x180014faa  jnb     short loc_180014FB9
0x180014fac  cmp     ecx, 800h
0x180014fb2  jb      short loc_180014FB9
0x180014fb4  mov     sil, dil
0x180014fb7  jmp     short loc_180014FC7
0x180014fb9  xor     sil, sil
0x180014fbc  xor     dl, dl
0x180014fbe  test    bpl, cl
0x180014fc1  jz      loc_180015051
0x180014fc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x180014fce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x180014fd3  test    al, al
0x180014fd5  jz      short loc_180015042
0x180014fd7  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x180014fde  mov     r8d, [rax]
0x180014fe1  test    r8b, 4
0x180014fe5  jnz     short loc_180014FFC
0x180014fe7  lea     rdx, [rsp+58h+arg_8]
0x180014fec  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x180014ff1  mov     rcx, [rax]
0x180014ff4  mov     [rsp+58h+arg_8], rcx
0x180014ff9  mov     r8d, ecx
0x180014ffc  xor     eax, eax
0x180014ffe  mov     word ptr [rsp+58h+arg_0+4], 3
0x180015005  mov     r9d, r8d
0x180015008  mov     [rsp+58h+var_28], eax
0x18001500c  mov     dword ptr [rsp+58h+arg_0], eax
0x180015010  lea     rcx, qword_1800337C8
0x180015017  shr     r9d, 0Bh
0x18001501b  lea     rax, [rsp+58h+arg_0]
0x180015020  shr     r8d, 0Ah
0x180015024  and     r9d, edi
0x180015027  and     r8d, edi
0x18001502a  mov     [rsp+58h+var_30], edi
0x18001502e  mov     edx, 37E2881h
0x180015033  mov     [rsp+58h+var_38], rax
0x180015038  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001503d  mov     dl, dil
0x180015040  jmp     short loc_180015044
0x180015042  xor     dl, dl
0x180015044  test    sil, sil
0x180015047  jz      short loc_180015051
0x180015049  test    dl, dl
0x18001504b  jnz     short loc_180015051
0x18001504d  btr     dword ptr [rbx], 0Ah
0x180015051  mov     eax, [rbx]
0x180015053  test    bpl, al
0x180015056  jz      short loc_18001505C
0x180015058  test    dl, dl
0x18001505a  jnz     short loc_18001505E
0x18001505c  xor     edi, edi
0x18001505e  and     eax, 0FFFFFFFEh
0x180015061  or      eax, edi
0x180015063  mov     [rbx], eax
0x180015065  mov     rax, rbx
0x180015068  mov     rbx, [rsp+58h+arg_10]
0x18001506d  add     rsp, 40h
0x180015071  pop     rdi
0x180015072  pop     rsi
0x180015073  pop     rbp
0x180015074  retn
```
