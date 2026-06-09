# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18005b1d4`
- end: `0x18005b359`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18005a918`

## callees

- `0x180048d90`
- `0x18004c07c`
- `0x1800597b4`
- `0x18005aa00`
- `0x18005b1d4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+20h] BYREF
  __int64 v17; // [rsp+68h] [rbp+28h] BYREF

  v16 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x3667CA7, (unsigned int)a2, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_ValLabTest__descriptor;
    if ( (*(_DWORD *)Feature_ValLabTest__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
                         v7,
                         &v17);
      v12 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_1800E5DD0,
      0x3667CA2u,
      (v12 >> 10) & 1,
      (v12 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    v14 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_1800E5E40,
      0x2AF34F8u,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18005b1d4  mov     [rsp-18h+arg_10], rbx
0x18005b1d9  mov     [rsp-18h+arg_0], rcx
0x18005b1de  push    rbp
0x18005b1df  push    rdi
0x18005b1e0  push    r14
0x18005b1e2  mov     rbp, rsp
0x18005b1e5  sub     rsp, 40h
0x18005b1e9  mov     ecx, 3667CA7h; this
0x18005b1ee  mov     rdi, rdx
0x18005b1f1  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18005b1f6  mov     edx, eax
0x18005b1f8  mov     qword ptr [rdi], 0
0x18005b1ff  and     edx, 0FFFFFF3Fh
0x18005b205  mov     ecx, eax
0x18005b207  and     eax, 80h
0x18005b20c  mov     r8d, edx
0x18005b20f  and     r8d, 3
0x18005b213  mov     r14d, 40h ; '@'
0x18005b219  shl     r8d, 2
0x18005b21d  and     ecx, r14d
0x18005b220  or      r8d, ecx
0x18005b223  shl     r8d, 2
0x18005b227  or      r8d, eax
0x18005b22a  shl     r8d, 3
0x18005b22e  test    edx, edx
0x18005b230  jnz     short loc_18005B23A
0x18005b232  mov     ecx, r14d
0x18005b235  mov     edx, r14d
0x18005b238  jmp     short loc_18005B245
0x18005b23a  xor     ecx, ecx
0x18005b23c  cmp     edx, 2
0x18005b23f  cmovz   ecx, r14d
0x18005b243  mov     edx, ecx
0x18005b245  mov     eax, r8d
0x18005b248  mov     ebx, 1
0x18005b24d  or      eax, edx
0x18005b24f  or      r8d, ecx
0x18005b252  mov     [rdi], eax
0x18005b254  bt      r8d, 0Ah
0x18005b259  jnb     short loc_18005B264
0x18005b25b  cmp     r8d, 800h
0x18005b262  jnb     short loc_18005B26F
0x18005b264  xor     cl, cl
0x18005b266  test    r14b, r8b
0x18005b269  jz      loc_18005B333
0x18005b26f  mov     rax, cs:Feature_ValLabTest__descriptor
0x18005b276  mov     r8d, [rax]
0x18005b279  test    r8b, 4
0x18005b27d  jnz     short loc_18005B292
0x18005b27f  lea     rdx, [rbp+arg_8]
0x18005b283  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)
0x18005b288  mov     rcx, [rax]
0x18005b28b  mov     [rbp+arg_8], rcx
0x18005b28f  mov     r8d, ecx
0x18005b292  xor     eax, eax
0x18005b294  mov     word ptr [rbp+arg_0+4], 3
0x18005b29a  mov     r9d, r8d
0x18005b29d  mov     [rsp+40h+var_10], eax
0x18005b2a1  mov     dword ptr [rbp+arg_0], eax
0x18005b2a4  lea     rcx, qword_1800E5DD0
0x18005b2ab  shr     r9d, 0Bh
0x18005b2af  lea     rax, [rbp+arg_0]
0x18005b2b3  shr     r8d, 0Ah
0x18005b2b7  and     r9d, ebx
0x18005b2ba  and     r8d, ebx
0x18005b2bd  mov     [rsp+40h+var_18], ebx
0x18005b2c1  mov     edx, 3667CA2h
0x18005b2c6  mov     [rsp+40h+var_20], rax
0x18005b2cb  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18005b2d0  mov     rax, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18005b2d7  mov     r8d, [rax]
0x18005b2da  test    r8b, 4
0x18005b2de  jnz     short loc_18005B2F3
0x18005b2e0  lea     rdx, [rbp+arg_8]
0x18005b2e4  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)
0x18005b2e9  mov     rcx, [rax]
0x18005b2ec  mov     [rbp+arg_8], rcx
0x18005b2f0  mov     r8d, ecx
0x18005b2f3  xor     eax, eax
0x18005b2f5  mov     word ptr [rbp+arg_0+4], 3
0x18005b2fb  mov     r9d, r8d
0x18005b2fe  mov     [rsp+40h+var_10], eax
0x18005b302  mov     dword ptr [rbp+arg_0], eax
0x18005b305  lea     rcx, qword_1800E5E40
0x18005b30c  shr     r9d, 0Bh
0x18005b310  lea     rax, [rbp+arg_0]
0x18005b314  shr     r8d, 0Ah
0x18005b318  and     r9d, ebx
0x18005b31b  and     r8d, ebx
0x18005b31e  mov     [rsp+40h+var_18], ebx
0x18005b322  mov     edx, 2AF34F8h
0x18005b327  mov     [rsp+40h+var_20], rax
0x18005b32c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18005b331  mov     cl, bl
0x18005b333  mov     eax, [rdi]
0x18005b335  test    r14b, al
0x18005b338  jz      short loc_18005B33E
0x18005b33a  test    cl, cl
0x18005b33c  jnz     short loc_18005B340
0x18005b33e  xor     ebx, ebx
0x18005b340  and     eax, 0FFFFFFFEh
0x18005b343  or      eax, ebx
0x18005b345  mov     rbx, [rsp+40h+arg_10]
0x18005b34a  mov     [rdi], eax
0x18005b34c  mov     rax, rdi
0x18005b34f  add     rsp, 40h
0x18005b353  pop     r14
0x18005b355  pop     rdi
0x18005b356  pop     rbp
0x18005b357  retn
```
