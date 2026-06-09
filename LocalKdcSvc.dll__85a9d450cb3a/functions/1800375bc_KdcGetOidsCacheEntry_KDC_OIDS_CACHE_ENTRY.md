# KdcGetOidsCacheEntry(_KDC_OIDS_CACHE_ENTRY * *)

- ea: `0x1800375bc`
- end: `0x180037866`
- name: `?KdcGetOidsCacheEntry@@YAJPEAPEAU_KDC_OIDS_CACHE_ENTRY@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(struct _KDC_OIDS_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004ffac`

## callees

- `0x18000a814`
- `0x18000a84c`
- `0x1800101ec`
- `0x180033f9c`
- `0x180034fcc`
- `0x180035054`
- `0x180037180`
- `0x1800373d4`
- `0x1800375bc`
- `0x180040420`
- `0x180072338`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18003762a`
- `ntdll!RtlAcquireResourceShared` at `0x18003762a`
- `ntdll!RtlConvertSharedToExclusive` at `0x18003771a`
- `ntdll!RtlConvertSharedToExclusive` at `0x18003771a`
- `SAMSRV!SamIGetConfigurationOidList` at `0x180037664`
- `SAMSRV!SamIGetConfigurationOidList` at `0x18003774b`
- `SAMSRV!SamIGetConfigurationOidList` at `0x180037664`
- `SAMSRV!SamIGetConfigurationOidList` at `0x18003774b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcGetOidsCacheEntry(struct _KDC_OIDS_CACHE_ENTRY **a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  int v4; // ebx
  CSecurityData *v5; // rcx
  __int64 v6; // rdx
  struct _KDC_OIDS_CACHE_ENTRY *v7; // rax
  struct _SAM_OID_LIST *v9; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v10[16]; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v11[24]; // [rsp+58h] [rbp-18h] BYREF
  char v12; // [rsp+90h] [rbp+20h] BYREF
  int v13; // [rsp+98h] [rbp+28h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+30h] BYREF
  struct _KDC_OIDS_CACHE_ENTRY *v15; // [rsp+A8h] [rbp+38h] BYREF

  v13 = 0;
  v14 = 0;
  v9 = 0;
  v15 = 0;
  v2 = lambda_14fd01bcd5a8d1a80ee3c701b30d75de_::_lambda_14fd01bcd5a8d1a80ee3c701b30d75de_(v10, &v9, &v15);
  wil::scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___(v11, v2);
  *a1 = 0;
  if ( !KdcGlobalOidsCache )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
LABEL_33:
    v4 = 0;
    goto LABEL_34;
  }
  RtlAcquireResourceShared(&stru_1800B4288, 1u);
  wil::scope_exit__lambda_500af5cf5d3940d97548a17119cc5657___(&v12);
  v4 = SamIGetConfigurationOidList(GlobalAccountDomainHandle, 0, 0, 0xFFFFFFFFLL, &v13, &v14, 0);
  if ( v4 == -1073741637 )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, 3221225659LL);
    }
LABEL_32:
    wil::details::lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___::_lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___(&v12);
    goto LABEL_33;
  }
  if ( v4 >= 0 )
  {
    if ( qword_1800B42E8 == v14 )
      goto LABEL_14;
    RtlConvertSharedToExclusive(&stru_1800B4288);
    v4 = SamIGetConfigurationOidList(GlobalAccountDomainHandle, 0, 0, 0xFFFFFFFFLL, &v13, &v14, &v9);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_12;
      v6 = 45;
      goto LABEL_11;
    }
    if ( qword_1800B42E8 == v14 )
    {
LABEL_14:
      v7 = qword_1800B42F0;
    }
    else
    {
      v4 = KdcCreateOidsCacheEntry(v9, &v15);
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_12;
        }
        v6 = 46;
        goto LABEL_11;
      }
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_ii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids,
          qword_1800B42E8,
          v14);
      }
      qword_1800B42E8 = v14;
      if ( qword_1800B42F0 )
        KdcDereferenceOidsCacheEntry(qword_1800B42F0);
      v7 = v15;
      qword_1800B42F0 = v15;
      v15 = 0;
    }
    if ( v7 )
    {
      *a1 = v7;
      _InterlockedIncrement((volatile signed __int32 *)v7);
    }
    goto LABEL_32;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CSecurityData *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_12;
  v6 = 44;
LABEL_11:
  WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, (unsigned int)v4);
LABEL_12:
  wil::details::lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___::_lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___(&v12);
LABEL_34:
  wil::details::lambda_call__lambda_c11b3d1e766b08bf35095a4f323e1b44___::_lambda_call__lambda_c11b3d1e766b08bf35095a4f323e1b44___(v11);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800375bc  push    rbp
0x1800375be  push    rbx
0x1800375bf  push    rdi
0x1800375c0  mov     rbp, rsp
0x1800375c3  sub     rsp, 70h
0x1800375c7  mov     rdi, rcx
0x1800375ca  mov     [rbp+arg_8], 0
0x1800375d1  mov     [rbp+arg_10], 0
0x1800375d9  mov     [rbp+var_30], 0
0x1800375e1  mov     [rbp+arg_18], 0
0x1800375e9  lea     r8, [rbp+arg_18]
0x1800375ed  lea     rdx, [rbp+var_30]
0x1800375f1  lea     rcx, [rbp+var_28]
0x1800375f5  call    _lambda_14fd01bcd5a8d1a80ee3c701b30d75de____lambda_14fd01bcd5a8d1a80ee3c701b30d75de_
0x1800375fa  mov     rdx, rax
0x1800375fd  lea     rcx, [rbp+var_18]
0x180037601  call    wil__scope_exit__lambda_14fd01bcd5a8d1a80ee3c701b30d75de___
0x180037606  nop
0x180037607  mov     qword ptr [rdi], 0
0x18003760e  cmp     cs:?KdcGlobalOidsCache@@3U_KDC_OIDS_CACHE@@A, 0; _KDC_OIDS_CACHE KdcGlobalOidsCache
0x180037615  jnz     short loc_180037621
0x180037617  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003761c  jmp     loc_180037851
0x180037621  mov     dl, 1; Wait
0x180037623  lea     rcx, stru_1800B4288; Resource
0x18003762a  call    cs:__imp_RtlAcquireResourceShared
0x180037630  lea     rcx, [rbp+arg_0]
0x180037634  call    wil__scope_exit__lambda_500af5cf5d3940d97548a17119cc5657___
0x180037639  mov     [rsp+70h+var_40], 0
0x180037642  lea     rax, [rbp+arg_10]
0x180037646  mov     [rsp+70h+var_48], rax
0x18003764b  lea     rax, [rbp+arg_8]
0x18003764f  mov     [rsp+70h+var_50], rax
0x180037654  or      r9d, 0FFFFFFFFh
0x180037658  xor     r8d, r8d
0x18003765b  xor     edx, edx
0x18003765d  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x180037664  call    cs:__imp_SamIGetConfigurationOidList
0x18003766a  mov     ebx, eax
0x18003766c  cmp     eax, 0C00000BBh
0x180037671  jnz     short loc_1800376B7
0x180037673  lea     rax, WPP_GLOBAL_Control
0x18003767a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037681  cmp     rcx, rax
0x180037684  jz      loc_180037848
0x18003768a  test    dword ptr [rcx+1Ch], 1000h
0x180037691  jz      loc_180037848
0x180037697  mov     edx, 2Bh ; '+'
0x18003769c  mov     r9d, 0C00000BBh
0x1800376a2  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x1800376a9  mov     rcx, [rcx+10h]
0x1800376ad  call    WPP_SF_d
0x1800376b2  jmp     loc_180037848
0x1800376b7  test    ebx, ebx
0x1800376b9  jns     short loc_1800376FA
0x1800376bb  lea     rax, WPP_GLOBAL_Control
0x1800376c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376c9  cmp     rcx, rax
0x1800376cc  jz      short loc_1800376EC
0x1800376ce  test    byte ptr [rcx+1Ch], 1
0x1800376d2  jz      short loc_1800376EC
0x1800376d4  mov     edx, 2Ch ; ','
0x1800376d9  mov     r9d, ebx
0x1800376dc  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x1800376e3  mov     rcx, [rcx+10h]
0x1800376e7  call    WPP_SF_d
0x1800376ec  lea     rcx, [rbp+arg_0]
0x1800376f0  call    wil__details__lambda_call__lambda_203115f0dd0c3589982ec83af902fae6______lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___
0x1800376f5  jmp     loc_180037853
0x1800376fa  mov     rax, [rbp+arg_10]
0x1800376fe  cmp     cs:qword_1800B42E8, rax
0x180037705  jnz     short loc_180037713
0x180037707  mov     rax, cs:qword_1800B42F0
0x18003770e  jmp     loc_18003783D
0x180037713  lea     rcx, stru_1800B4288; Resource
0x18003771a  call    cs:__imp_RtlConvertSharedToExclusive
0x180037720  lea     rax, [rbp+var_30]
0x180037724  mov     [rsp+70h+var_40], rax
0x180037729  lea     rax, [rbp+arg_10]
0x18003772d  mov     [rsp+70h+var_48], rax
0x180037732  lea     rax, [rbp+arg_8]
0x180037736  mov     [rsp+70h+var_50], rax
0x18003773b  or      r9d, 0FFFFFFFFh
0x18003773f  xor     r8d, r8d
0x180037742  xor     edx, edx
0x180037744  mov     rcx, cs:?GlobalAccountDomainHandle@@3PEAXEA; void * GlobalAccountDomainHandle
0x18003774b  call    cs:__imp_SamIGetConfigurationOidList
0x180037751  mov     ebx, eax
0x180037753  test    eax, eax
0x180037755  jns     short loc_18003777E
0x180037757  lea     rax, WPP_GLOBAL_Control
0x18003775e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037765  cmp     rcx, rax
0x180037768  jz      short loc_1800376EC
0x18003776a  test    byte ptr [rcx+1Ch], 1
0x18003776e  jz      loc_1800376EC
0x180037774  mov     edx, 2Dh ; '-'
0x180037779  jmp     loc_1800376D9
0x18003777e  mov     rax, [rbp+arg_10]
0x180037782  cmp     cs:qword_1800B42E8, rax
0x180037789  jz      loc_180037707
0x18003778f  lea     rdx, [rbp+arg_18]; struct _KDC_OIDS_CACHE_ENTRY **
0x180037793  mov     rcx, [rbp+var_30]; struct _SAM_OID_LIST *
0x180037797  call    ?KdcCreateOidsCacheEntry@@YAJPEBU_SAM_OID_LIST@@PEAPEAU_KDC_OIDS_CACHE_ENTRY@@@Z; KdcCreateOidsCacheEntry(_SAM_OID_LIST const *,_KDC_OIDS_CACHE_ENTRY * *)
0x18003779c  mov     ebx, eax
0x18003779e  test    eax, eax
0x1800377a0  jns     short loc_1800377CD
0x1800377a2  lea     rax, WPP_GLOBAL_Control
0x1800377a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377b0  cmp     rcx, rax
0x1800377b3  jz      loc_1800376EC
0x1800377b9  test    byte ptr [rcx+1Ch], 1
0x1800377bd  jz      loc_1800376EC
0x1800377c3  mov     edx, 2Eh ; '.'
0x1800377c8  jmp     loc_1800376D9
0x1800377cd  lea     rax, WPP_GLOBAL_Control
0x1800377d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377db  cmp     rcx, rax
0x1800377de  jz      short loc_18003780E
0x1800377e0  test    dword ptr [rcx+1Ch], 1000h
0x1800377e7  jz      short loc_18003780E
0x1800377e9  mov     edx, 2Fh ; '/'
0x1800377ee  mov     rax, [rbp+arg_10]
0x1800377f2  mov     [rsp+70h+var_50], rax
0x1800377f7  mov     r9, cs:qword_1800B42E8
0x1800377fe  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180037805  mov     rcx, [rcx+10h]
0x180037809  call    WPP_SF_ii
0x18003780e  mov     rax, [rbp+arg_10]
0x180037812  mov     cs:qword_1800B42E8, rax
0x180037819  mov     rcx, cs:qword_1800B42F0; struct _KDC_OIDS_CACHE_ENTRY *
0x180037820  test    rcx, rcx
0x180037823  jz      short loc_18003782A
0x180037825  call    ?KdcDereferenceOidsCacheEntry@@YAXPEAU_KDC_OIDS_CACHE_ENTRY@@@Z; KdcDereferenceOidsCacheEntry(_KDC_OIDS_CACHE_ENTRY *)
0x18003782a  mov     rax, [rbp+arg_18]
0x18003782e  mov     cs:qword_1800B42F0, rax
0x180037835  mov     [rbp+arg_18], 0
0x18003783d  test    rax, rax
0x180037840  jz      short loc_180037848
0x180037842  mov     [rdi], rax
0x180037845  lock inc dword ptr [rax]
0x180037848  lea     rcx, [rbp+arg_0]
0x18003784c  call    wil__details__lambda_call__lambda_203115f0dd0c3589982ec83af902fae6______lambda_call__lambda_203115f0dd0c3589982ec83af902fae6___
0x180037851  xor     ebx, ebx
0x180037853  lea     rcx, [rbp+var_18]
0x180037857  call    wil__details__lambda_call__lambda_c11b3d1e766b08bf35095a4f323e1b44______lambda_call__lambda_c11b3d1e766b08bf35095a4f323e1b44___
0x18003785c  mov     eax, ebx
0x18003785e  add     rsp, 70h
0x180037862  pop     rdi
0x180037863  pop     rbx
0x180037864  pop     rbp
0x180037865  retn
```
