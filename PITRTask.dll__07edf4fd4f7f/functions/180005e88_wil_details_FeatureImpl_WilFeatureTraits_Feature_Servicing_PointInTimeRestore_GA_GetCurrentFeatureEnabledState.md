# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180005e88`
- end: `0x180006005`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `381`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1800057bc`

## callees

- `0x1800058b0`
- `0x180005e88`
- `0x1800088a8`
- `0x18000bad4`
- `0x1800107c0`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetCurrentFeatureEnabledState(
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
  char v12; // si
  bool v13; // dl
  unsigned int v14; // r8d
  char IsEnabled; // al
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  int v18; // [rsp+48h] [rbp-30h] BYREF
  __int16 v19; // [rsp+4Ch] [rbp-2Ch]

  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(60394409, 3);
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
  if ( ((unsigned __int16)v11 & 0x400) != 0 && (unsigned int)v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( ((unsigned __int8)v11 & 0x40) == 0 )
      goto LABEL_19;
  }
  v14 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (*(_DWORD *)Feature_Standalone_Future__descriptor & 4) == 0 )
  {
    v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
             v11,
             &v17);
    v14 = v17;
  }
  v19 = 3;
  v18 = 0;
  wil::details::ReportUsageToService(&qword_18001BE08, 49453572, (v14 >> 10) & 1, (v14 >> 11) & 1, &v18, 1, 0);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl'::`2'::impl);
  v13 = IsEnabled != 0;
  if ( v12 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_19:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180005e88  mov     [rsp+arg_0], rbx
0x180005e8d  push    rbp
0x180005e8e  push    rsi
0x180005e8f  push    rdi
0x180005e90  sub     rsp, 60h
0x180005e94  mov     rax, cs:__security_cookie
0x180005e9b  xor     rax, rsp
0x180005e9e  mov     [rsp+78h+var_28], rax
0x180005ea3  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005eaa  mov     rbx, rdx
0x180005ead  test    rax, rax
0x180005eb0  jz      short loc_180005EC5
0x180005eb2  mov     edx, 3
0x180005eb7  mov     ecx, 3998BA9h
0x180005ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec1  mov     edx, eax
0x180005ec3  jmp     short loc_180005ED3
0x180005ec5  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180005ecc  test    rax, rax
0x180005ecf  jnz     short loc_180005EB2
0x180005ed1  xor     edx, edx
0x180005ed3  mov     r8d, edx
0x180005ed6  mov     qword ptr [rbx], 0
0x180005edd  and     r8d, 0FFFFFF3Fh
0x180005ee4  mov     eax, edx
0x180005ee6  and     edx, 80h
0x180005eec  mov     ecx, r8d
0x180005eef  and     ecx, 3
0x180005ef2  mov     ebp, 40h ; '@'
0x180005ef7  shl     ecx, 2
0x180005efa  and     eax, ebp
0x180005efc  or      ecx, eax
0x180005efe  shl     ecx, 2
0x180005f01  or      ecx, edx
0x180005f03  shl     ecx, 3
0x180005f06  test    r8d, r8d
0x180005f09  jnz     short loc_180005F12
0x180005f0b  mov     edx, ebp
0x180005f0d  mov     r8d, ebp
0x180005f10  jmp     short loc_180005F1E
0x180005f12  xor     edx, edx
0x180005f14  cmp     r8d, 2
0x180005f18  cmovz   edx, ebp
0x180005f1b  mov     r8d, edx
0x180005f1e  mov     eax, ecx
0x180005f20  mov     edi, 1
0x180005f25  or      eax, r8d
0x180005f28  or      ecx, edx
0x180005f2a  mov     [rbx], eax
0x180005f2c  bt      ecx, 0Ah
0x180005f30  jnb     short loc_180005F3F
0x180005f32  cmp     ecx, 800h
0x180005f38  jb      short loc_180005F3F
0x180005f3a  mov     sil, dil
0x180005f3d  jmp     short loc_180005F4D
0x180005f3f  xor     sil, sil
0x180005f42  xor     dl, dl
0x180005f44  test    bpl, cl
0x180005f47  jz      loc_180005FD1
0x180005f4d  mov     rax, cs:Feature_Standalone_Future__descriptor
0x180005f54  mov     r8d, [rax]
0x180005f57  test    r8b, 4
0x180005f5b  jnz     short loc_180005F72
0x180005f5d  lea     rdx, [rsp+78h+var_38]
0x180005f62  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)
0x180005f67  mov     rcx, [rax]
0x180005f6a  mov     [rsp+78h+var_38], rcx
0x180005f6f  mov     r8d, ecx
0x180005f72  xor     eax, eax
0x180005f74  mov     [rsp+78h+var_2C], 3
0x180005f7b  mov     r9d, r8d
0x180005f7e  mov     [rsp+78h+var_48], eax
0x180005f82  mov     [rsp+78h+var_30], eax
0x180005f86  lea     rcx, qword_18001BE08
0x180005f8d  shr     r9d, 0Bh
0x180005f91  lea     rax, [rsp+78h+var_30]
0x180005f96  shr     r8d, 0Ah
0x180005f9a  and     r9d, edi
0x180005f9d  and     r8d, edi
0x180005fa0  mov     [rsp+78h+var_50], edi
0x180005fa4  mov     edx, 2F29A04h
0x180005fa9  mov     [rsp+78h+var_58], rax
0x180005fae  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180005fb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::GetImpl(void)'::`2'::impl
0x180005fba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore>::__private_IsEnabled(wil::ReportingKind)
0x180005fbf  test    al, al
0x180005fc1  setnz   dl
0x180005fc4  test    sil, sil
0x180005fc7  jz      short loc_180005FD1
0x180005fc9  test    dl, dl
0x180005fcb  jnz     short loc_180005FD1
0x180005fcd  btr     dword ptr [rbx], 0Ah
0x180005fd1  mov     eax, [rbx]
0x180005fd3  test    bpl, al
0x180005fd6  jz      short loc_180005FDC
0x180005fd8  test    dl, dl
0x180005fda  jnz     short loc_180005FDE
0x180005fdc  xor     edi, edi
0x180005fde  and     eax, 0FFFFFFFEh
0x180005fe1  or      eax, edi
0x180005fe3  mov     [rbx], eax
0x180005fe5  mov     rax, rbx
0x180005fe8  mov     rcx, [rsp+78h+var_28]
0x180005fed  xor     rcx, rsp; StackCookie
0x180005ff0  call    __security_check_cookie
0x180005ff5  mov     rbx, [rsp+78h+arg_0]
0x180005ffd  add     rsp, 60h
0x180006001  pop     rdi
0x180006002  pop     rsi
0x180006003  pop     rbp
0x180006004  retn
```
