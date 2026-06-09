# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005430`
- end: `0x18000558b`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `347`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180005054`

## callees

- `0x180005148`
- `0x180005430`
- `0x180008650`
- `0x18000c610`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCurrentFeatureEnabledState(
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
  __int64 v15; // [rsp+40h] [rbp-28h] BYREF
  int v16; // [rsp+48h] [rbp-20h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-1Ch]

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(60337618, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
               v11,
               &v15);
      v13 = v15;
    }
    v17 = 3;
    v16 = 0;
    wil::details::ReportUsageToService(&qword_180015F78, 58599550, (v13 >> 10) & 1, (v13 >> 11) & 1, &v16, 1, 0);
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
0x180005430  mov     [rsp+arg_0], rbx
0x180005435  mov     [rsp+arg_18], rsi
0x18000543a  push    rdi
0x18000543b  sub     rsp, 60h
0x18000543f  mov     rax, cs:__security_cookie
0x180005446  xor     rax, rsp
0x180005449  mov     [rsp+68h+var_18], rax
0x18000544e  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005455  mov     rbx, rdx
0x180005458  test    rax, rax
0x18000545b  jz      short loc_180005470
0x18000545d  mov     edx, 3
0x180005462  mov     ecx, 398ADD2h
0x180005467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000546c  mov     edx, eax
0x18000546e  jmp     short loc_18000547E
0x180005470  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180005477  test    rax, rax
0x18000547a  jnz     short loc_18000545D
0x18000547c  xor     edx, edx
0x18000547e  mov     r8d, edx
0x180005481  mov     qword ptr [rbx], 0
0x180005488  and     r8d, 0FFFFFF3Fh
0x18000548f  mov     eax, edx
0x180005491  and     edx, 80h
0x180005497  mov     ecx, r8d
0x18000549a  and     ecx, 3
0x18000549d  mov     esi, 40h ; '@'
0x1800054a2  shl     ecx, 2
0x1800054a5  and     eax, esi
0x1800054a7  or      ecx, eax
0x1800054a9  shl     ecx, 2
0x1800054ac  or      ecx, edx
0x1800054ae  shl     ecx, 3
0x1800054b1  test    r8d, r8d
0x1800054b4  jnz     short loc_1800054BD
0x1800054b6  mov     edx, esi
0x1800054b8  mov     r8d, esi
0x1800054bb  jmp     short loc_1800054C9
0x1800054bd  xor     edx, edx
0x1800054bf  cmp     r8d, 2
0x1800054c3  cmovz   edx, esi
0x1800054c6  mov     r8d, edx
0x1800054c9  mov     eax, ecx
0x1800054cb  mov     edi, 1
0x1800054d0  or      eax, r8d
0x1800054d3  or      ecx, edx
0x1800054d5  mov     [rbx], eax
0x1800054d7  bt      ecx, 0Ah
0x1800054db  jnb     short loc_1800054E5
0x1800054dd  cmp     ecx, 800h
0x1800054e3  jnb     short loc_1800054EC
0x1800054e5  xor     dl, dl
0x1800054e7  test    sil, cl
0x1800054ea  jz      short loc_180005555
0x1800054ec  mov     rax, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800054f3  mov     r8d, [rax]
0x1800054f6  test    r8b, 4
0x1800054fa  jnz     short loc_180005511
0x1800054fc  lea     rdx, [rsp+68h+var_28]
0x180005501  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)
0x180005506  mov     rcx, [rax]
0x180005509  mov     [rsp+68h+var_28], rcx
0x18000550e  mov     r8d, ecx
0x180005511  xor     eax, eax
0x180005513  mov     [rsp+68h+var_1C], 3
0x18000551a  mov     r9d, r8d
0x18000551d  mov     [rsp+68h+var_38], eax
0x180005521  mov     [rsp+68h+var_20], eax
0x180005525  lea     rcx, qword_180015F78
0x18000552c  shr     r9d, 0Bh
0x180005530  lea     rax, [rsp+68h+var_20]
0x180005535  shr     r8d, 0Ah
0x180005539  and     r9d, edi
0x18000553c  and     r8d, edi
0x18000553f  mov     [rsp+68h+var_40], edi
0x180005543  mov     edx, 37E287Eh
0x180005548  mov     [rsp+68h+var_48], rax
0x18000554d  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180005552  mov     dl, dil
0x180005555  mov     eax, [rbx]
0x180005557  test    sil, al
0x18000555a  jz      short loc_180005560
0x18000555c  test    dl, dl
0x18000555e  jnz     short loc_180005562
0x180005560  xor     edi, edi
0x180005562  and     eax, 0FFFFFFFEh
0x180005565  or      eax, edi
0x180005567  mov     [rbx], eax
0x180005569  mov     rax, rbx
0x18000556c  mov     rcx, [rsp+68h+var_18]
0x180005571  xor     rcx, rsp; StackCookie
0x180005574  call    __security_check_cookie
0x180005579  lea     r11, [rsp+68h+var_8]
0x18000557e  mov     rbx, [r11+10h]
0x180005582  mov     rsi, [r11+28h]
0x180005586  mov     rsp, r11
0x180005589  pop     rdi
0x18000558a  retn
```
