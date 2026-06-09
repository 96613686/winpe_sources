# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014c2c`
- end: `0x180014d95`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180013df8`

## callees

- `0x18000ab68`
- `0x180013668`
- `0x180014c2c`
- `0x180015574`
- `0x18002a010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(
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
    v4 = v2(58988972, 3);
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_1800337A8, 58599532, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
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
0x180014c2c  mov     [rsp+arg_10], rbx
0x180014c31  mov     [rsp+arg_0], rcx
0x180014c36  push    rbp
0x180014c37  push    rsi
0x180014c38  push    rdi
0x180014c39  sub     rsp, 40h
0x180014c3d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180014c44  mov     rbx, rdx
0x180014c47  test    rax, rax
0x180014c4a  jz      short loc_180014C5F
0x180014c4c  mov     edx, 3
0x180014c51  mov     ecx, 38419ACh
0x180014c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c5b  mov     edx, eax
0x180014c5d  jmp     short loc_180014C6D
0x180014c5f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180014c66  test    rax, rax
0x180014c69  jnz     short loc_180014C4C
0x180014c6b  xor     edx, edx
0x180014c6d  mov     r8d, edx
0x180014c70  mov     qword ptr [rbx], 0
0x180014c77  and     r8d, 0FFFFFF3Fh
0x180014c7e  mov     eax, edx
0x180014c80  and     edx, 80h
0x180014c86  mov     ecx, r8d
0x180014c89  and     ecx, 3
0x180014c8c  mov     ebp, 40h ; '@'
0x180014c91  shl     ecx, 2
0x180014c94  and     eax, ebp
0x180014c96  or      ecx, eax
0x180014c98  shl     ecx, 2
0x180014c9b  or      ecx, edx
0x180014c9d  shl     ecx, 3
0x180014ca0  test    r8d, r8d
0x180014ca3  jnz     short loc_180014CAC
0x180014ca5  mov     edx, ebp
0x180014ca7  mov     r8d, ebp
0x180014caa  jmp     short loc_180014CB8
0x180014cac  xor     edx, edx
0x180014cae  cmp     r8d, 2
0x180014cb2  cmovz   edx, ebp
0x180014cb5  mov     r8d, edx
0x180014cb8  mov     eax, ecx
0x180014cba  mov     edi, 1
0x180014cbf  or      eax, r8d
0x180014cc2  or      ecx, edx
0x180014cc4  mov     [rbx], eax
0x180014cc6  bt      ecx, 0Ah
0x180014cca  jnb     short loc_180014CD9
0x180014ccc  cmp     ecx, 800h
0x180014cd2  jb      short loc_180014CD9
0x180014cd4  mov     sil, dil
0x180014cd7  jmp     short loc_180014CE7
0x180014cd9  xor     sil, sil
0x180014cdc  xor     dl, dl
0x180014cde  test    bpl, cl
0x180014ce1  jz      loc_180014D71
0x180014ce7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x180014cee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x180014cf3  test    al, al
0x180014cf5  jz      short loc_180014D62
0x180014cf7  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180014cfe  mov     r8d, [rax]
0x180014d01  test    r8b, 4
0x180014d05  jnz     short loc_180014D1C
0x180014d07  lea     rdx, [rsp+58h+arg_8]
0x180014d0c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x180014d11  mov     rcx, [rax]
0x180014d14  mov     [rsp+58h+arg_8], rcx
0x180014d19  mov     r8d, ecx
0x180014d1c  xor     eax, eax
0x180014d1e  mov     word ptr [rsp+58h+arg_0+4], 3
0x180014d25  mov     r9d, r8d
0x180014d28  mov     [rsp+58h+var_28], eax
0x180014d2c  mov     dword ptr [rsp+58h+arg_0], eax
0x180014d30  lea     rcx, qword_1800337A8
0x180014d37  shr     r9d, 0Bh
0x180014d3b  lea     rax, [rsp+58h+arg_0]
0x180014d40  shr     r8d, 0Ah
0x180014d44  and     r9d, edi
0x180014d47  and     r8d, edi
0x180014d4a  mov     [rsp+58h+var_30], edi
0x180014d4e  mov     edx, 37E286Ch
0x180014d53  mov     [rsp+58h+var_38], rax
0x180014d58  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014d5d  mov     dl, dil
0x180014d60  jmp     short loc_180014D64
0x180014d62  xor     dl, dl
0x180014d64  test    sil, sil
0x180014d67  jz      short loc_180014D71
0x180014d69  test    dl, dl
0x180014d6b  jnz     short loc_180014D71
0x180014d6d  btr     dword ptr [rbx], 0Ah
0x180014d71  mov     eax, [rbx]
0x180014d73  test    bpl, al
0x180014d76  jz      short loc_180014D7C
0x180014d78  test    dl, dl
0x180014d7a  jnz     short loc_180014D7E
0x180014d7c  xor     edi, edi
0x180014d7e  and     eax, 0FFFFFFFEh
0x180014d81  or      eax, edi
0x180014d83  mov     [rbx], eax
0x180014d85  mov     rax, rbx
0x180014d88  mov     rbx, [rsp+58h+arg_10]
0x180014d8d  add     rsp, 40h
0x180014d91  pop     rdi
0x180014d92  pop     rsi
0x180014d93  pop     rbp
0x180014d94  retn
```
