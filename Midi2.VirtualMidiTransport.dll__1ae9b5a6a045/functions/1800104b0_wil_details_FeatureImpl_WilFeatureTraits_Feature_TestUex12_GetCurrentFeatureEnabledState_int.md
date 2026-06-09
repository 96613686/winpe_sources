# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x1800104b0`
- end: `0x180010619`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fc40`

## callees

- `0x18000f82c`
- `0x1800104b0`
- `0x180011204`
- `0x180011d8c`
- `0x180021010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58989070, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18002DD48,
      0x37E2887u,
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
0x1800104b0  mov     [rsp+arg_10], rbx
0x1800104b5  mov     [rsp+arg_0], rcx
0x1800104ba  push    rbp
0x1800104bb  push    rsi
0x1800104bc  push    rdi
0x1800104bd  sub     rsp, 40h
0x1800104c1  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800104c8  mov     rbx, rdx
0x1800104cb  test    rax, rax
0x1800104ce  jz      short loc_1800104E3
0x1800104d0  mov     edx, 3
0x1800104d5  mov     ecx, 3841A0Eh
0x1800104da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104df  mov     edx, eax
0x1800104e1  jmp     short loc_1800104F1
0x1800104e3  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800104ea  test    rax, rax
0x1800104ed  jnz     short loc_1800104D0
0x1800104ef  xor     edx, edx
0x1800104f1  mov     r8d, edx
0x1800104f4  mov     qword ptr [rbx], 0
0x1800104fb  and     r8d, 0FFFFFF3Fh
0x180010502  mov     eax, edx
0x180010504  and     edx, 80h
0x18001050a  mov     ecx, r8d
0x18001050d  and     ecx, 3
0x180010510  mov     ebp, 40h ; '@'
0x180010515  shl     ecx, 2
0x180010518  and     eax, ebp
0x18001051a  or      ecx, eax
0x18001051c  shl     ecx, 2
0x18001051f  or      ecx, edx
0x180010521  shl     ecx, 3
0x180010524  test    r8d, r8d
0x180010527  jnz     short loc_180010530
0x180010529  mov     edx, ebp
0x18001052b  mov     r8d, ebp
0x18001052e  jmp     short loc_18001053C
0x180010530  xor     edx, edx
0x180010532  cmp     r8d, 2
0x180010536  cmovz   edx, ebp
0x180010539  mov     r8d, edx
0x18001053c  mov     eax, ecx
0x18001053e  mov     edi, 1
0x180010543  or      eax, r8d
0x180010546  or      ecx, edx
0x180010548  mov     [rbx], eax
0x18001054a  bt      ecx, 0Ah
0x18001054e  jnb     short loc_18001055D
0x180010550  cmp     ecx, 800h
0x180010556  jb      short loc_18001055D
0x180010558  mov     sil, dil
0x18001055b  jmp     short loc_18001056B
0x18001055d  xor     sil, sil
0x180010560  xor     dl, dl
0x180010562  test    bpl, cl
0x180010565  jz      loc_1800105F5
0x18001056b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x180010572  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x180010577  test    al, al
0x180010579  jz      short loc_1800105E6
0x18001057b  mov     rax, cs:Feature_Standalone_26_04_NonSec__descriptor
0x180010582  mov     r8d, [rax]
0x180010585  test    r8b, 4
0x180010589  jnz     short loc_1800105A0
0x18001058b  lea     rdx, [rsp+58h+arg_8]
0x180010590  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x180010595  mov     rcx, [rax]
0x180010598  mov     [rsp+58h+arg_8], rcx
0x18001059d  mov     r8d, ecx
0x1800105a0  xor     eax, eax
0x1800105a2  mov     word ptr [rsp+58h+arg_0+4], 3
0x1800105a9  mov     r9d, r8d
0x1800105ac  mov     [rsp+58h+var_28], eax
0x1800105b0  mov     dword ptr [rsp+58h+arg_0], eax
0x1800105b4  lea     rcx, qword_18002DD48
0x1800105bb  shr     r9d, 0Bh
0x1800105bf  lea     rax, [rsp+58h+arg_0]
0x1800105c4  shr     r8d, 0Ah
0x1800105c8  and     r9d, edi
0x1800105cb  and     r8d, edi
0x1800105ce  mov     [rsp+58h+var_30], edi
0x1800105d2  mov     edx, 37E2887h
0x1800105d7  mov     [rsp+58h+var_38], rax
0x1800105dc  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1800105e1  mov     dl, dil
0x1800105e4  jmp     short loc_1800105E8
0x1800105e6  xor     dl, dl
0x1800105e8  test    sil, sil
0x1800105eb  jz      short loc_1800105F5
0x1800105ed  test    dl, dl
0x1800105ef  jnz     short loc_1800105F5
0x1800105f1  btr     dword ptr [rbx], 0Ah
0x1800105f5  mov     eax, [rbx]
0x1800105f7  test    bpl, al
0x1800105fa  jz      short loc_180010600
0x1800105fc  test    dl, dl
0x1800105fe  jnz     short loc_180010602
0x180010600  xor     edi, edi
0x180010602  and     eax, 0FFFFFFFEh
0x180010605  or      eax, edi
0x180010607  mov     [rbx], eax
0x180010609  mov     rax, rbx
0x18001060c  mov     rbx, [rsp+58h+arg_10]
0x180010611  add     rsp, 40h
0x180010615  pop     rdi
0x180010616  pop     rsi
0x180010617  pop     rbp
0x180010618  retn
```
