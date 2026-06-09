# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180008f18`
- end: `0x18000905a`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180008090`

## callees

- `0x18000886c`
- `0x180008f18`
- `0x18000dc68`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  int v7; // edx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  wil::details *v11; // rcx
  char v12; // dl
  unsigned int v13; // r8d
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58580710, 3);
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
  v11 = (wil::details *)(v7 | (unsigned int)v6);
  *(_DWORD *)a2 = v10;
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800
    || (v12 = 0, ((unsigned __int8)v11 & 0x40) != 0) )
  {
    v13 = *(_DWORD *)Feature_Standalone_Future__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180024070, 49453572, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
    v12 = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v12 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180008f18  mov     [rsp+arg_10], rbx
0x180008f1d  mov     [rsp+arg_18], rsi
0x180008f22  mov     [rsp+arg_0], rcx
0x180008f27  push    rdi
0x180008f28  sub     rsp, 40h
0x180008f2c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180008f33  mov     rbx, rdx
0x180008f36  test    rax, rax
0x180008f39  jz      short loc_180008F4E
0x180008f3b  mov     edx, 3
0x180008f40  mov     ecx, 37DDEE6h
0x180008f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4a  mov     edx, eax
0x180008f4c  jmp     short loc_180008F5C
0x180008f4e  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180008f55  test    rax, rax
0x180008f58  jnz     short loc_180008F3B
0x180008f5a  xor     edx, edx
0x180008f5c  mov     r8d, edx
0x180008f5f  mov     qword ptr [rbx], 0
0x180008f66  and     r8d, 0FFFFFF3Fh
0x180008f6d  mov     eax, edx
0x180008f6f  and     edx, 80h
0x180008f75  mov     ecx, r8d
0x180008f78  and     ecx, 3
0x180008f7b  mov     esi, 40h ; '@'
0x180008f80  shl     ecx, 2
0x180008f83  and     eax, esi
0x180008f85  or      ecx, eax
0x180008f87  shl     ecx, 2
0x180008f8a  or      ecx, edx
0x180008f8c  shl     ecx, 3
0x180008f8f  test    r8d, r8d
0x180008f92  jnz     short loc_180008F9B
0x180008f94  mov     edx, esi
0x180008f96  mov     r8d, esi
0x180008f99  jmp     short loc_180008FA7
0x180008f9b  xor     edx, edx
0x180008f9d  cmp     r8d, 2
0x180008fa1  cmovz   edx, esi
0x180008fa4  mov     r8d, edx
0x180008fa7  mov     eax, ecx
0x180008fa9  mov     edi, 1
0x180008fae  or      eax, r8d
0x180008fb1  or      ecx, edx
0x180008fb3  mov     [rbx], eax
0x180008fb5  bt      ecx, 0Ah
0x180008fb9  jnb     short loc_180008FC3
0x180008fbb  cmp     ecx, 800h
0x180008fc1  jnb     short loc_180008FCA
0x180008fc3  xor     dl, dl
0x180008fc5  test    sil, cl
0x180008fc8  jz      short loc_180009033
0x180008fca  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180008fd1  mov     r8d, [rax]
0x180008fd4  test    r8b, 4
0x180008fd8  jnz     short loc_180008FEF
0x180008fda  lea     rdx, [rsp+48h+arg_8]
0x180008fdf  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180008fe4  mov     rcx, [rax]
0x180008fe7  mov     [rsp+48h+arg_8], rcx
0x180008fec  mov     r8d, ecx
0x180008fef  xor     eax, eax
0x180008ff1  mov     word ptr [rsp+48h+arg_0+4], 3
0x180008ff8  mov     r9d, r8d
0x180008ffb  mov     [rsp+48h+var_18], eax
0x180008fff  mov     dword ptr [rsp+48h+arg_0], eax
0x180009003  lea     rcx, qword_180024070
0x18000900a  shr     r9d, 0Bh
0x18000900e  lea     rax, [rsp+48h+arg_0]
0x180009013  shr     r8d, 0Ah
0x180009017  and     r9d, edi
0x18000901a  and     r8d, edi
0x18000901d  mov     [rsp+48h+var_20], edi
0x180009021  mov     edx, 2F29A04h
0x180009026  mov     [rsp+48h+var_28], rax
0x18000902b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009030  mov     dl, dil
0x180009033  mov     eax, [rbx]
0x180009035  test    sil, al
0x180009038  jz      short loc_18000903E
0x18000903a  test    dl, dl
0x18000903c  jnz     short loc_180009040
0x18000903e  xor     edi, edi
0x180009040  mov     rsi, [rsp+48h+arg_18]
0x180009045  and     eax, 0FFFFFFFEh
0x180009048  or      eax, edi
0x18000904a  mov     [rbx], eax
0x18000904c  mov     rax, rbx
0x18000904f  mov     rbx, [rsp+48h+arg_10]
0x180009054  add     rsp, 40h
0x180009058  pop     rdi
0x180009059  retn
```
