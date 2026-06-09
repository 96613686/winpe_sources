# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001fb4c`
- end: `0x18001fcb5`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f36c`

## callees

- `0x18001ebdc`
- `0x18001fb4c`
- `0x180020aa4`
- `0x180021464`
- `0x180032010`

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
  __int64 v13; // rcx
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
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FDC8,
      0x37E286Cu,
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
0x18001fb4c  mov     [rsp+arg_10], rbx
0x18001fb51  mov     [rsp+arg_0], rcx
0x18001fb56  push    rbp
0x18001fb57  push    rsi
0x18001fb58  push    rdi
0x18001fb59  sub     rsp, 40h
0x18001fb5d  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001fb64  mov     rbx, rdx
0x18001fb67  test    rax, rax
0x18001fb6a  jz      short loc_18001FB7F
0x18001fb6c  mov     edx, 3
0x18001fb71  mov     ecx, 38419ACh
0x18001fb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb7b  mov     edx, eax
0x18001fb7d  jmp     short loc_18001FB8D
0x18001fb7f  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fb86  test    rax, rax
0x18001fb89  jnz     short loc_18001FB6C
0x18001fb8b  xor     edx, edx
0x18001fb8d  mov     r8d, edx
0x18001fb90  mov     qword ptr [rbx], 0
0x18001fb97  and     r8d, 0FFFFFF3Fh
0x18001fb9e  mov     eax, edx
0x18001fba0  and     edx, 80h
0x18001fba6  mov     ecx, r8d
0x18001fba9  and     ecx, 3
0x18001fbac  mov     ebp, 40h ; '@'
0x18001fbb1  shl     ecx, 2
0x18001fbb4  and     eax, ebp
0x18001fbb6  or      ecx, eax
0x18001fbb8  shl     ecx, 2
0x18001fbbb  or      ecx, edx
0x18001fbbd  shl     ecx, 3
0x18001fbc0  test    r8d, r8d
0x18001fbc3  jnz     short loc_18001FBCC
0x18001fbc5  mov     edx, ebp
0x18001fbc7  mov     r8d, ebp
0x18001fbca  jmp     short loc_18001FBD8
0x18001fbcc  xor     edx, edx
0x18001fbce  cmp     r8d, 2
0x18001fbd2  cmovz   edx, ebp
0x18001fbd5  mov     r8d, edx
0x18001fbd8  mov     eax, ecx
0x18001fbda  mov     edi, 1
0x18001fbdf  or      eax, r8d
0x18001fbe2  or      ecx, edx
0x18001fbe4  mov     [rbx], eax
0x18001fbe6  bt      ecx, 0Ah
0x18001fbea  jnb     short loc_18001FBF9
0x18001fbec  cmp     ecx, 800h
0x18001fbf2  jb      short loc_18001FBF9
0x18001fbf4  mov     sil, dil
0x18001fbf7  jmp     short loc_18001FC07
0x18001fbf9  xor     sil, sil
0x18001fbfc  xor     dl, dl
0x18001fbfe  test    bpl, cl
0x18001fc01  jz      loc_18001FC91
0x18001fc07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestAccPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf> `wil::Feature<__WilFeatureTraits_Feature_TestAccPerf>::GetImpl(void)'::`2'::impl
0x18001fc0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::__private_IsEnabled(wil::ReportingKind)
0x18001fc13  test    al, al
0x18001fc15  jz      short loc_18001FC82
0x18001fc17  mov     rax, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18001fc1e  mov     r8d, [rax]
0x18001fc21  test    r8b, 4
0x18001fc25  jnz     short loc_18001FC3C
0x18001fc27  lea     rdx, [rsp+58h+arg_8]
0x18001fc2c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)
0x18001fc31  mov     rcx, [rax]
0x18001fc34  mov     [rsp+58h+arg_8], rcx
0x18001fc39  mov     r8d, ecx
0x18001fc3c  xor     eax, eax
0x18001fc3e  mov     word ptr [rsp+58h+arg_0+4], 3
0x18001fc45  mov     r9d, r8d
0x18001fc48  mov     [rsp+58h+var_28], eax
0x18001fc4c  mov     dword ptr [rsp+58h+arg_0], eax
0x18001fc50  lea     rcx, qword_18005FDC8
0x18001fc57  shr     r9d, 0Bh
0x18001fc5b  lea     rax, [rsp+58h+arg_0]
0x18001fc60  shr     r8d, 0Ah
0x18001fc64  and     r9d, edi
0x18001fc67  and     r8d, edi
0x18001fc6a  mov     [rsp+58h+var_30], edi
0x18001fc6e  mov     edx, 37E286Ch
0x18001fc73  mov     [rsp+58h+var_38], rax
0x18001fc78  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001fc7d  mov     dl, dil
0x18001fc80  jmp     short loc_18001FC84
0x18001fc82  xor     dl, dl
0x18001fc84  test    sil, sil
0x18001fc87  jz      short loc_18001FC91
0x18001fc89  test    dl, dl
0x18001fc8b  jnz     short loc_18001FC91
0x18001fc8d  btr     dword ptr [rbx], 0Ah
0x18001fc91  mov     eax, [rbx]
0x18001fc93  test    bpl, al
0x18001fc96  jz      short loc_18001FC9C
0x18001fc98  test    dl, dl
0x18001fc9a  jnz     short loc_18001FC9E
0x18001fc9c  xor     edi, edi
0x18001fc9e  and     eax, 0FFFFFFFEh
0x18001fca1  or      eax, edi
0x18001fca3  mov     [rbx], eax
0x18001fca5  mov     rax, rbx
0x18001fca8  mov     rbx, [rsp+58h+arg_10]
0x18001fcad  add     rsp, 40h
0x18001fcb1  pop     rdi
0x18001fcb2  pop     rsi
0x18001fcb3  pop     rbp
0x18001fcb4  retn
```
