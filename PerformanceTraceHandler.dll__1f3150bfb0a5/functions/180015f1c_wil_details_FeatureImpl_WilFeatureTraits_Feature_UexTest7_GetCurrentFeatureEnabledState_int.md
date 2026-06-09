# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180015f1c`
- end: `0x180016064`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `328`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800155b8`

## callees

- `0x18000cc60`
- `0x18000cfc0`
- `0x1800151bc`
- `0x180015f1c`
- `0x180017d20`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
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
  wil::details *v14; // rcx
  unsigned int v15; // r8d
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF
  __int64 v18; // [rsp+68h] [rbp+10h] BYREF

  v17 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419DD, (unsigned int)a2, a3, a4);
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
      goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl) )
  {
    v15 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor & 4) == 0 )
    {
      v18 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
               v14,
               &v18);
      v15 = v18;
    }
    WORD2(v17) = 3;
    LODWORD(v17) = 0;
    wil::details::ReportUsageToService(&qword_180027DB8, 58599553, (v15 >> 10) & 1, (v15 >> 11) & 1, &v17, 1, 0);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_18:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180015f1c  mov     [rsp+arg_10], rbx
0x180015f21  mov     [rsp+arg_0], rcx
0x180015f26  push    rbp
0x180015f27  push    rsi
0x180015f28  push    rdi
0x180015f29  sub     rsp, 40h
0x180015f2d  mov     ecx, 38419DDh; this
0x180015f32  mov     rbx, rdx
0x180015f35  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180015f3a  mov     edx, eax
0x180015f3c  mov     qword ptr [rbx], 0
0x180015f43  and     edx, 0FFFFFF3Fh
0x180015f49  mov     ecx, eax
0x180015f4b  and     eax, 80h
0x180015f50  mov     r8d, edx
0x180015f53  and     r8d, 3
0x180015f57  mov     ebp, 40h ; '@'
0x180015f5c  shl     r8d, 2
0x180015f60  and     ecx, ebp
0x180015f62  or      r8d, ecx
0x180015f65  shl     r8d, 2
0x180015f69  or      r8d, eax
0x180015f6c  shl     r8d, 3
0x180015f70  test    edx, edx
0x180015f72  jnz     short loc_180015F7A
0x180015f74  mov     ecx, ebp
0x180015f76  mov     edx, ebp
0x180015f78  jmp     short loc_180015F84
0x180015f7a  xor     ecx, ecx
0x180015f7c  cmp     edx, 2
0x180015f7f  cmovz   ecx, ebp
0x180015f82  mov     edx, ecx
0x180015f84  mov     eax, r8d
0x180015f87  mov     edi, 1
0x180015f8c  or      eax, edx
0x180015f8e  or      r8d, ecx
0x180015f91  mov     [rbx], eax
0x180015f93  bt      r8d, 0Ah
0x180015f98  jnb     short loc_180015FA8
0x180015f9a  cmp     r8d, 800h
0x180015fa1  jb      short loc_180015FA8
0x180015fa3  mov     sil, dil
0x180015fa6  jmp     short loc_180015FB6
0x180015fa8  xor     sil, sil
0x180015fab  xor     cl, cl
0x180015fad  test    bpl, r8b
0x180015fb0  jz      loc_180016040
0x180015fb6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x180015fbd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x180015fc2  test    al, al
0x180015fc4  jz      short loc_180016031
0x180015fc6  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x180015fcd  mov     r8d, [rax]
0x180015fd0  test    r8b, 4
0x180015fd4  jnz     short loc_180015FEB
0x180015fd6  lea     rdx, [rsp+58h+arg_8]
0x180015fdb  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x180015fe0  mov     rcx, [rax]
0x180015fe3  mov     [rsp+58h+arg_8], rcx
0x180015fe8  mov     r8d, ecx
0x180015feb  xor     eax, eax
0x180015fed  mov     word ptr [rsp+58h+arg_0+4], 3
0x180015ff4  mov     r9d, r8d
0x180015ff7  mov     [rsp+58h+var_28], eax
0x180015ffb  mov     dword ptr [rsp+58h+arg_0], eax
0x180015fff  lea     rcx, qword_180027DB8
0x180016006  shr     r9d, 0Bh
0x18001600a  lea     rax, [rsp+58h+arg_0]
0x18001600f  shr     r8d, 0Ah
0x180016013  and     r9d, edi
0x180016016  and     r8d, edi
0x180016019  mov     [rsp+58h+var_30], edi
0x18001601d  mov     edx, 37E2881h
0x180016022  mov     [rsp+58h+var_38], rax
0x180016027  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001602c  mov     cl, dil
0x18001602f  jmp     short loc_180016033
0x180016031  xor     cl, cl
0x180016033  test    sil, sil
0x180016036  jz      short loc_180016040
0x180016038  test    cl, cl
0x18001603a  jnz     short loc_180016040
0x18001603c  btr     dword ptr [rbx], 0Ah
0x180016040  mov     eax, [rbx]
0x180016042  test    bpl, al
0x180016045  jz      short loc_18001604B
0x180016047  test    cl, cl
0x180016049  jnz     short loc_18001604D
0x18001604b  xor     edi, edi
0x18001604d  and     eax, 0FFFFFFFEh
0x180016050  or      eax, edi
0x180016052  mov     [rbx], eax
0x180016054  mov     rax, rbx
0x180016057  mov     rbx, [rsp+58h+arg_10]
0x18001605c  add     rsp, 40h
0x180016060  pop     rdi
0x180016061  pop     rsi
0x180016062  pop     rbp
0x180016063  retn
```
