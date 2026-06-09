# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180010620`
- end: `0x180010789`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fd20`

## callees

- `0x18000f6b8`
- `0x180010620`
- `0x180011204`
- `0x180011b1c`
- `0x180021010`

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
      (__int64)&qword_18002DD58,
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
0x180010620  mov     [rsp+arg_10], rbx
0x180010625  mov     [rsp+arg_0], rcx
0x18001062a  push    rbp
0x18001062b  push    rsi
0x18001062c  push    rdi
0x18001062d  sub     rsp, 40h
0x180010631  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180010638  mov     rbx, rdx
0x18001063b  test    rax, rax
0x18001063e  jz      short loc_180010653
0x180010640  mov     edx, 3
0x180010645  mov     ecx, 38419DDh
0x18001064a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001064f  mov     edx, eax
0x180010651  jmp     short loc_180010661
0x180010653  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001065a  test    rax, rax
0x18001065d  jnz     short loc_180010640
0x18001065f  xor     edx, edx
0x180010661  mov     r8d, edx
0x180010664  mov     qword ptr [rbx], 0
0x18001066b  and     r8d, 0FFFFFF3Fh
0x180010672  mov     eax, edx
0x180010674  and     edx, 80h
0x18001067a  mov     ecx, r8d
0x18001067d  and     ecx, 3
0x180010680  mov     ebp, 40h ; '@'
0x180010685  shl     ecx, 2
0x180010688  and     eax, ebp
0x18001068a  or      ecx, eax
0x18001068c  shl     ecx, 2
0x18001068f  or      ecx, edx
0x180010691  shl     ecx, 3
0x180010694  test    r8d, r8d
0x180010697  jnz     short loc_1800106A0
0x180010699  mov     edx, ebp
0x18001069b  mov     r8d, ebp
0x18001069e  jmp     short loc_1800106AC
0x1800106a0  xor     edx, edx
0x1800106a2  cmp     r8d, 2
0x1800106a6  cmovz   edx, ebp
0x1800106a9  mov     r8d, edx
0x1800106ac  mov     eax, ecx
0x1800106ae  mov     edi, 1
0x1800106b3  or      eax, r8d
0x1800106b6  or      ecx, edx
0x1800106b8  mov     [rbx], eax
0x1800106ba  bt      ecx, 0Ah
0x1800106be  jnb     short loc_1800106CD
0x1800106c0  cmp     ecx, 800h
0x1800106c6  jb      short loc_1800106CD
0x1800106c8  mov     sil, dil
0x1800106cb  jmp     short loc_1800106DB
0x1800106cd  xor     sil, sil
0x1800106d0  xor     dl, dl
0x1800106d2  test    bpl, cl
0x1800106d5  jz      loc_180010765
0x1800106db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x1800106e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1800106e7  test    al, al
0x1800106e9  jz      short loc_180010756
0x1800106eb  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x1800106f2  mov     r8d, [rax]
0x1800106f5  test    r8b, 4
0x1800106f9  jnz     short loc_180010710
0x1800106fb  lea     rdx, [rsp+58h+arg_8]
0x180010700  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x180010705  mov     rcx, [rax]
0x180010708  mov     [rsp+58h+arg_8], rcx
0x18001070d  mov     r8d, ecx
0x180010710  xor     eax, eax
0x180010712  mov     word ptr [rsp+58h+arg_0+4], 3
0x180010719  mov     r9d, r8d
0x18001071c  mov     [rsp+58h+var_28], eax
0x180010720  mov     dword ptr [rsp+58h+arg_0], eax
0x180010724  lea     rcx, qword_18002DD58
0x18001072b  shr     r9d, 0Bh
0x18001072f  lea     rax, [rsp+58h+arg_0]
0x180010734  shr     r8d, 0Ah
0x180010738  and     r9d, edi
0x18001073b  and     r8d, edi
0x18001073e  mov     [rsp+58h+var_30], edi
0x180010742  mov     edx, 37E2881h
0x180010747  mov     [rsp+58h+var_38], rax
0x18001074c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180010751  mov     dl, dil
0x180010754  jmp     short loc_180010758
0x180010756  xor     dl, dl
0x180010758  test    sil, sil
0x18001075b  jz      short loc_180010765
0x18001075d  test    dl, dl
0x18001075f  jnz     short loc_180010765
0x180010761  btr     dword ptr [rbx], 0Ah
0x180010765  mov     eax, [rbx]
0x180010767  test    bpl, al
0x18001076a  jz      short loc_180010770
0x18001076c  test    dl, dl
0x18001076e  jnz     short loc_180010772
0x180010770  xor     edi, edi
0x180010772  and     eax, 0FFFFFFFEh
0x180010775  or      eax, edi
0x180010777  mov     [rbx], eax
0x180010779  mov     rax, rbx
0x18001077c  mov     rbx, [rsp+58h+arg_10]
0x180010781  add     rsp, 40h
0x180010785  pop     rdi
0x180010786  pop     rsi
0x180010787  pop     rbp
0x180010788  retn
```
