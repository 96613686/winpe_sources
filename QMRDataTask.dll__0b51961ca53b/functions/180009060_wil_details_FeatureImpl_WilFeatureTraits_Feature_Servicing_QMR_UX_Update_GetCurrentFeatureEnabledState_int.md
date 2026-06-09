# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180009060`
- end: `0x1800091a2`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `322`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180008170`

## callees

- `0x180008410`
- `0x180009060`
- `0x18000dc68`
- `0x180015010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetCurrentFeatureEnabledState(
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
    v4 = v2(59402696, 3);
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
    v13 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor & 4) == 0 )
    {
      v16 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
               v11,
               &v16);
      v13 = v16;
    }
    WORD2(v15) = 3;
    LODWORD(v15) = 0;
    wil::details::ReportUsageToService(&qword_180023FF0, 45036797, (v13 >> 10) & 1, (v13 >> 11) & 1, &v15, 1, 0);
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
0x180009060  mov     [rsp+arg_10], rbx
0x180009065  mov     [rsp+arg_18], rsi
0x18000906a  mov     [rsp+arg_0], rcx
0x18000906f  push    rdi
0x180009070  sub     rsp, 40h
0x180009074  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000907b  mov     rbx, rdx
0x18000907e  test    rax, rax
0x180009081  jz      short loc_180009096
0x180009083  mov     edx, 3
0x180009088  mov     ecx, 38A69C8h
0x18000908d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009092  mov     edx, eax
0x180009094  jmp     short loc_1800090A4
0x180009096  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000909d  test    rax, rax
0x1800090a0  jnz     short loc_180009083
0x1800090a2  xor     edx, edx
0x1800090a4  mov     r8d, edx
0x1800090a7  mov     qword ptr [rbx], 0
0x1800090ae  and     r8d, 0FFFFFF3Fh
0x1800090b5  mov     eax, edx
0x1800090b7  and     edx, 80h
0x1800090bd  mov     ecx, r8d
0x1800090c0  and     ecx, 3
0x1800090c3  mov     esi, 40h ; '@'
0x1800090c8  shl     ecx, 2
0x1800090cb  and     eax, esi
0x1800090cd  or      ecx, eax
0x1800090cf  shl     ecx, 2
0x1800090d2  or      ecx, edx
0x1800090d4  shl     ecx, 3
0x1800090d7  test    r8d, r8d
0x1800090da  jnz     short loc_1800090E3
0x1800090dc  mov     edx, esi
0x1800090de  mov     r8d, esi
0x1800090e1  jmp     short loc_1800090EF
0x1800090e3  xor     edx, edx
0x1800090e5  cmp     r8d, 2
0x1800090e9  cmovz   edx, esi
0x1800090ec  mov     r8d, edx
0x1800090ef  mov     eax, ecx
0x1800090f1  mov     edi, 1
0x1800090f6  or      eax, r8d
0x1800090f9  or      ecx, edx
0x1800090fb  mov     [rbx], eax
0x1800090fd  bt      ecx, 0Ah
0x180009101  jnb     short loc_18000910B
0x180009103  cmp     ecx, 800h
0x180009109  jnb     short loc_180009112
0x18000910b  xor     dl, dl
0x18000910d  test    sil, cl
0x180009110  jz      short loc_18000917B
0x180009112  mov     rax, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180009119  mov     r8d, [rax]
0x18000911c  test    r8b, 4
0x180009120  jnz     short loc_180009137
0x180009122  lea     rdx, [rsp+48h+arg_8]
0x180009127  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)
0x18000912c  mov     rcx, [rax]
0x18000912f  mov     [rsp+48h+arg_8], rcx
0x180009134  mov     r8d, ecx
0x180009137  xor     eax, eax
0x180009139  mov     word ptr [rsp+48h+arg_0+4], 3
0x180009140  mov     r9d, r8d
0x180009143  mov     [rsp+48h+var_18], eax
0x180009147  mov     dword ptr [rsp+48h+arg_0], eax
0x18000914b  lea     rcx, qword_180023FF0
0x180009152  shr     r9d, 0Bh
0x180009156  lea     rax, [rsp+48h+arg_0]
0x18000915b  shr     r8d, 0Ah
0x18000915f  and     r9d, edi
0x180009162  and     r8d, edi
0x180009165  mov     [rsp+48h+var_20], edi
0x180009169  mov     edx, 2AF34FDh
0x18000916e  mov     [rsp+48h+var_28], rax
0x180009173  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180009178  mov     dl, dil
0x18000917b  mov     eax, [rbx]
0x18000917d  test    sil, al
0x180009180  jz      short loc_180009186
0x180009182  test    dl, dl
0x180009184  jnz     short loc_180009188
0x180009186  xor     edi, edi
0x180009188  mov     rsi, [rsp+48h+arg_18]
0x18000918d  and     eax, 0FFFFFFFEh
0x180009190  or      eax, edi
0x180009192  mov     [rbx], eax
0x180009194  mov     rax, rbx
0x180009197  mov     rbx, [rsp+48h+arg_10]
0x18000919c  add     rsp, 40h
0x1800091a0  pop     rdi
0x1800091a1  retn
```
