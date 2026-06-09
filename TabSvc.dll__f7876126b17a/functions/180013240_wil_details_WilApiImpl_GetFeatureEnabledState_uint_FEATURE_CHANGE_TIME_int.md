# wil::details::WilApiImpl_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x180013240`
- end: `0x1800133d7`
- name: `?WilApiImpl_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `407`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x180013240`
- `0x180018cd4`
- `0x180018e1c`
- `0x180019930`
- `0x18001a080`
- `0x18001bbe0`
- `0x180031010`

## string_xrefs

- `0x180013368`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil::details::WilApiImpl_GetFeatureEnabledState(wil::details *this, int a2, _DWORD *a3, int *a4)
{
  volatile __int32 *v4; // rsi
  unsigned int v5; // r12d
  int v6; // ebx
  bool v8; // r13
  unsigned int v9; // edi
  volatile __int32 v10; // eax
  int v11; // r15d
  int v12; // r9d
  int FeatureState; // eax
  int v14; // edx
  int v15; // ebx
  char v16; // r8
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  __int128 v21; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+48h] [rbp-28h]
  __int64 v23; // [rsp+50h] [rbp-20h] BYREF
  int v24; // [rsp+58h] [rbp-18h]

  v4 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v5 = (unsigned int)this;
  v6 = 1;
  v8 = (a2 & 0xFFFFFF7F) - 2 <= 1;
  v9 = 0;
  v22 = 0;
  v21 = 0;
  if ( (a2 & 0x80) != 0 )
    v4 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v10 = *v4;
  if ( (*v4 & 2) == 0 )
  {
LABEL_6:
    LODWORD(v20) = 1;
    v11 = wil::details::EnsureSubscribedToFeatureConfigurationChanges((wil::details *)&`wil::details::IsFeatureConfigured'::`2'::userStoreProbe);
    FeatureState = wil_QueryFeatureState((unsigned int)&v21, v5, v8, v12, (__int64)&v20, (__int64)a3);
    v14 = v20;
    v15 = FeatureState;
    v16 = _InterlockedExchange(v4, ((_DWORD)v20 != 0) + 6);
    if ( !v14 && (v16 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v4, 0, v11);
    if ( !v15 )
      goto LABEL_10;
    goto LABEL_23;
  }
  if ( (v10 & 1) == 0 )
    goto LABEL_10;
  if ( (v10 & 2) == 0 )
    goto LABEL_6;
  *a3 = 1;
  v23 = 0;
  v24 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  v20 = 0;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
      goto LABEL_10;
  }
  v19 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))NtDllProcedureAddress)(v5, !v8, &v20, &v23);
  if ( !v19 )
  {
    LODWORD(v21) = (HIDWORD(v23) >> 4) & 3;
    HIDWORD(v22) = (BYTE4(v23) >> 6) & 1;
    if ( (v23 & 0x8000000000LL) == 0 )
      v6 = 0;
    goto LABEL_24;
  }
  if ( v19 != 279 )
  {
LABEL_10:
    v6 = v22;
    goto LABEL_11;
  }
  if ( (v23 & 0x8000000000LL) == 0 )
LABEL_23:
    v6 = v22;
LABEL_24:
  v9 = v21;
LABEL_11:
  if ( v6 )
    v9 |= 0x80u;
  if ( HIDWORD(v22) )
    v9 |= 0x40u;
  return v9;
}

```

## disassembly

```asm
0x180013240  mov     [rsp-38h+arg_8], rbx
0x180013245  push    rbp
0x180013246  push    rsi
0x180013247  push    rdi
0x180013248  push    r12
0x18001324a  push    r13
0x18001324c  push    r14
0x18001324e  push    r15
0x180013250  mov     rbp, rsp
0x180013253  sub     rsp, 70h
0x180013257  mov     rax, cs:__security_cookie
0x18001325e  xor     rax, rsp
0x180013261  mov     [rbp+var_10], rax
0x180013265  mov     eax, edx
0x180013267  lea     rsi, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x18001326e  btr     edx, 7
0x180013272  mov     r12d, ecx
0x180013275  sub     edx, 2
0x180013278  mov     ebx, 1
0x18001327d  cmp     edx, ebx
0x18001327f  xorps   xmm0, xmm0
0x180013282  mov     r14, r8
0x180013285  setbe   r13b
0x180013289  xor     ecx, ecx
0x18001328b  xor     edi, edi
0x18001328d  mov     [rbp+var_28], rcx
0x180013291  bt      eax, 7
0x180013295  lea     rcx, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; this
0x18001329c  movups  [rbp+var_38], xmm0
0x1800132a0  cmovb   rsi, rcx
0x1800132a4  mov     eax, [rsi]
0x1800132a6  test    al, 2
0x1800132a8  jz      short loc_1800132B6
0x1800132aa  test    bl, al
0x1800132ac  jz      short loc_180013312
0x1800132ae  test    al, 2
0x1800132b0  jnz     loc_18001334C
0x1800132b6  mov     dword ptr [rbp+var_40], ebx
0x1800132b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800132be  mov     r15d, eax
0x1800132c1  movzx   r8d, r13b
0x1800132c5  lea     rax, [rbp+var_40]
0x1800132c9  mov     [rsp+70h+var_48], r14
0x1800132ce  mov     edx, r12d
0x1800132d1  mov     [rsp+70h+var_50], rax
0x1800132d6  lea     rcx, [rbp+var_38]
0x1800132da  call    wil_QueryFeatureState
0x1800132df  mov     edx, dword ptr [rbp+var_40]
0x1800132e2  mov     ebx, eax
0x1800132e4  mov     eax, edx
0x1800132e6  neg     eax
0x1800132e8  sbb     r8d, r8d
0x1800132eb  neg     r8d
0x1800132ee  add     r8d, 6
0x1800132f2  xchg    r8d, [rsi]
0x1800132f5  test    edx, edx
0x1800132f7  jnz     short loc_18001330A
0x1800132f9  test    r8b, 4
0x1800132fd  jnz     short loc_18001330A
0x1800132ff  mov     r8d, r15d
0x180013302  mov     rcx, rsi
0x180013305  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001330a  test    ebx, ebx
0x18001330c  jnz     loc_1800133CC
0x180013312  mov     ebx, dword ptr [rbp+var_28]
0x180013315  test    ebx, ebx
0x180013317  jz      short loc_18001331D
0x180013319  bts     edi, 7
0x18001331d  cmp     dword ptr [rbp+var_28+4], 0
0x180013321  jz      short loc_180013326
0x180013323  or      edi, 40h
0x180013326  mov     eax, edi
0x180013328  mov     rcx, [rbp+var_10]
0x18001332c  xor     rcx, rsp; StackCookie
0x18001332f  call    __security_check_cookie
0x180013334  mov     rbx, [rsp+70h+arg_8]
0x18001333c  add     rsp, 70h
0x180013340  pop     r15
0x180013342  pop     r14
0x180013344  pop     r13
0x180013346  pop     r12
0x180013348  pop     rdi
0x180013349  pop     rsi
0x18001334a  pop     rbp
0x18001334b  retn
0x18001334c  xor     eax, eax
0x18001334e  mov     [r8], ebx
0x180013351  mov     [rbp+var_20], rax
0x180013355  mov     [rbp+var_18], eax
0x180013358  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001335f  mov     [rbp+var_40], rdi
0x180013363  test    rax, rax
0x180013366  jnz     short loc_180013380
0x180013368  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001336f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013374  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001337b  test    rax, rax
0x18001337e  jz      short loc_180013312
0x180013380  movzx   edx, r13b
0x180013384  lea     r9, [rbp+var_20]
0x180013388  xor     edx, ebx
0x18001338a  lea     r8, [rbp+var_40]
0x18001338e  mov     ecx, r12d
0x180013391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013396  test    eax, eax
0x180013398  jnz     short loc_1800133BB
0x18001339a  mov     ecx, dword ptr [rbp+var_20+4]
0x18001339d  mov     eax, ecx
0x18001339f  shr     eax, 4
0x1800133a2  and     eax, 3
0x1800133a5  mov     dword ptr [rbp+var_38], eax
0x1800133a8  movzx   eax, cl
0x1800133ab  shr     eax, 6
0x1800133ae  and     eax, ebx
0x1800133b0  mov     dword ptr [rbp+var_28+4], eax
0x1800133b3  test    cl, cl
0x1800133b5  js      short loc_1800133CF
0x1800133b7  xor     ebx, ebx
0x1800133b9  jmp     short loc_1800133CF
0x1800133bb  cmp     eax, 117h
0x1800133c0  jnz     loc_180013312
0x1800133c6  test    byte ptr [rbp+var_20+4], 80h
0x1800133ca  jnz     short loc_1800133CF
0x1800133cc  mov     ebx, dword ptr [rbp+var_28]
0x1800133cf  mov     edi, dword ptr [rbp+var_38]
0x1800133d2  jmp     loc_180013315
```
