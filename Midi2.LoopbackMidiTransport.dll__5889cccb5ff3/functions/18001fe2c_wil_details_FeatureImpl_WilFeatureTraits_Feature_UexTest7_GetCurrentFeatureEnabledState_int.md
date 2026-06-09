# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001fe2c`
- end: `0x18001ff95`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f52c`

## callees

- `0x18001eec4`
- `0x18001fe2c`
- `0x180020aa4`
- `0x1800213c8`
- `0x180032010`

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
      (__int64)&qword_18005FDA8,
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
0x18001fe2c  mov     [rsp+arg_10], rbx
0x18001fe31  mov     [rsp+arg_0], rcx
0x18001fe36  push    rbp
0x18001fe37  push    rsi
0x18001fe38  push    rdi
0x18001fe39  sub     rsp, 40h
0x18001fe3d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001fe44  mov     rbx, rdx
0x18001fe47  test    rax, rax
0x18001fe4a  jz      short loc_18001FE5F
0x18001fe4c  mov     edx, 3
0x18001fe51  mov     ecx, 38419DDh
0x18001fe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe5b  mov     edx, eax
0x18001fe5d  jmp     short loc_18001FE6D
0x18001fe5f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fe66  test    rax, rax
0x18001fe69  jnz     short loc_18001FE4C
0x18001fe6b  xor     edx, edx
0x18001fe6d  mov     r8d, edx
0x18001fe70  mov     qword ptr [rbx], 0
0x18001fe77  and     r8d, 0FFFFFF3Fh
0x18001fe7e  mov     eax, edx
0x18001fe80  and     edx, 80h
0x18001fe86  mov     ecx, r8d
0x18001fe89  and     ecx, 3
0x18001fe8c  mov     ebp, 40h ; '@'
0x18001fe91  shl     ecx, 2
0x18001fe94  and     eax, ebp
0x18001fe96  or      ecx, eax
0x18001fe98  shl     ecx, 2
0x18001fe9b  or      ecx, edx
0x18001fe9d  shl     ecx, 3
0x18001fea0  test    r8d, r8d
0x18001fea3  jnz     short loc_18001FEAC
0x18001fea5  mov     edx, ebp
0x18001fea7  mov     r8d, ebp
0x18001feaa  jmp     short loc_18001FEB8
0x18001feac  xor     edx, edx
0x18001feae  cmp     r8d, 2
0x18001feb2  cmovz   edx, ebp
0x18001feb5  mov     r8d, edx
0x18001feb8  mov     eax, ecx
0x18001feba  mov     edi, 1
0x18001febf  or      eax, r8d
0x18001fec2  or      ecx, edx
0x18001fec4  mov     [rbx], eax
0x18001fec6  bt      ecx, 0Ah
0x18001feca  jnb     short loc_18001FED9
0x18001fecc  cmp     ecx, 800h
0x18001fed2  jb      short loc_18001FED9
0x18001fed4  mov     sil, dil
0x18001fed7  jmp     short loc_18001FEE7
0x18001fed9  xor     sil, sil
0x18001fedc  xor     dl, dl
0x18001fede  test    bpl, cl
0x18001fee1  jz      loc_18001FF71
0x18001fee7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x18001feee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x18001fef3  test    al, al
0x18001fef5  jz      short loc_18001FF62
0x18001fef7  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001fefe  mov     r8d, [rax]
0x18001ff01  test    r8b, 4
0x18001ff05  jnz     short loc_18001FF1C
0x18001ff07  lea     rdx, [rsp+58h+arg_8]
0x18001ff0c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x18001ff11  mov     rcx, [rax]
0x18001ff14  mov     [rsp+58h+arg_8], rcx
0x18001ff19  mov     r8d, ecx
0x18001ff1c  xor     eax, eax
0x18001ff1e  mov     word ptr [rsp+58h+arg_0+4], 3
0x18001ff25  mov     r9d, r8d
0x18001ff28  mov     [rsp+58h+var_28], eax
0x18001ff2c  mov     dword ptr [rsp+58h+arg_0], eax
0x18001ff30  lea     rcx, qword_18005FDA8
0x18001ff37  shr     r9d, 0Bh
0x18001ff3b  lea     rax, [rsp+58h+arg_0]
0x18001ff40  shr     r8d, 0Ah
0x18001ff44  and     r9d, edi
0x18001ff47  and     r8d, edi
0x18001ff4a  mov     [rsp+58h+var_30], edi
0x18001ff4e  mov     edx, 37E2881h
0x18001ff53  mov     [rsp+58h+var_38], rax
0x18001ff58  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001ff5d  mov     dl, dil
0x18001ff60  jmp     short loc_18001FF64
0x18001ff62  xor     dl, dl
0x18001ff64  test    sil, sil
0x18001ff67  jz      short loc_18001FF71
0x18001ff69  test    dl, dl
0x18001ff6b  jnz     short loc_18001FF71
0x18001ff6d  btr     dword ptr [rbx], 0Ah
0x18001ff71  mov     eax, [rbx]
0x18001ff73  test    bpl, al
0x18001ff76  jz      short loc_18001FF7C
0x18001ff78  test    dl, dl
0x18001ff7a  jnz     short loc_18001FF7E
0x18001ff7c  xor     edi, edi
0x18001ff7e  and     eax, 0FFFFFFFEh
0x18001ff81  or      eax, edi
0x18001ff83  mov     [rbx], eax
0x18001ff85  mov     rax, rbx
0x18001ff88  mov     rbx, [rsp+58h+arg_10]
0x18001ff8d  add     rsp, 40h
0x18001ff91  pop     rdi
0x18001ff92  pop     rsi
0x18001ff93  pop     rbp
0x18001ff94  retn
```
