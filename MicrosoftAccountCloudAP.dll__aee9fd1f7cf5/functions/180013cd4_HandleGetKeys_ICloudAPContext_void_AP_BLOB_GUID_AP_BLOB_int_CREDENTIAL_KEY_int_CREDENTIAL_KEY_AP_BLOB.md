# HandleGetKeys(ICloudAPContext *,void *,_AP_BLOB *,_GUID *,_AP_BLOB *,int,_CREDENTIAL_KEY * *,int *,_CREDENTIAL_KEY * *,_AP_BLOB *)

- ea: `0x180013cd4`
- end: `0x18001419a`
- name: `?HandleGetKeys@@YAJPEAVICloudAPContext@@PEAXPEAU_AP_BLOB@@PEAU_GUID@@2HPEAPEAU_CREDENTIAL_KEY@@PEAH42@Z`
- size: `1222`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, struct _AP_BLOB *, struct _GUID *, struct _AP_BLOB *, int, struct _CREDENTIAL_KEY **, int *, struct _CREDENTIAL_KEY **, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180009cb0`

## callees

- `0x180008428`
- `0x180008440`
- `0x18000baac`
- `0x18000d824`
- `0x18000d980`
- `0x18000dc94`
- `0x18000e0c4`
- `0x18000e0f0`
- `0x18000f778`
- `0x18000f84c`
- `0x180010040`
- `0x180010064`
- `0x180010830`
- `0x1800112f0`
- `0x180012130`
- `0x1800121b4`
- `0x180013cd4`
- `0x180015d14`
- `0x1800267c0`
- `0x180032010`

## string_xrefs

- `0x180013dc1`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013ecb`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013fdd`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014062`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013ebe`: `WLIDCCreateContextEx failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall HandleGetKeys(
        struct ICloudAPContext *a1,
        void *a2,
        struct _AP_BLOB *a3,
        struct _GUID *a4,
        struct _AP_BLOB *a5,
        int a6,
        struct _CREDENTIAL_KEY **a7,
        int *a8,
        struct _CREDENTIAL_KEY **a9,
        struct _AP_BLOB *a10)
{
  void *v13; // r14
  __int64 v14; // rax
  __int64 v15; // r13
  int *v16; // rbx
  struct _CREDENTIAL_KEY **v17; // rdi
  struct _CREDENTIAL_KEY **v18; // rsi
  int v19; // eax
  struct MSACloudAPValidationInfo *v20; // r13
  int v21; // eax
  int v22; // r15d
  int VersionTimeStamp; // eax
  int v24; // eax
  int v25; // r15d
  struct _CREDENTIAL_KEY *v26; // r15
  int v27; // eax
  int v28; // r14d
  struct _CREDENTIAL_KEY *v29; // rax
  unsigned int v30; // ebx
  const unsigned __int16 *v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+20h] [rbp-E0h]
  void *v36[3]; // [rsp+40h] [rbp-C0h] BYREF
  struct _CREDENTIAL_KEY *v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h]
  struct _CREDENTIAL_KEY *v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  void **v44; // [rsp+98h] [rbp-68h] BYREF
  int v45; // [rsp+A0h] [rbp-60h]
  __int64 v46; // [rsp+A8h] [rbp-58h]
  struct MSACloudAPValidationInfo *v47[3]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v48; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v49[3]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v50[10]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *Source; // [rsp+150h] [rbp+50h] BYREF
  int updated; // [rsp+158h] [rbp+58h] BYREF
  int v53; // [rsp+15Ch] [rbp+5Ch]

  v53 = HIDWORD(a2);
  updated = 0;
  memset(v47, 0, sizeof(v47));
  memset(v49, 0, sizeof(v49));
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v43);
  a5 = 0;
  v48 = 0;
  Source = 0;
  a10 = 0;
  v40 = 0;
  v42 = 0;
  v41 = 0;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  v13 = (void *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v36[0] = 0;
  v36[2] = v13;
  v36[1] = 0;
  v14 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  v50[0] = "HandleGetKeys";
  v50[1] = &updated;
  v50[2] = 0;
  v50[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleGetKeys",
    (const char *)0x41A,
    0,
    v32);
  v16 = a8;
  v17 = a9;
  v18 = a7;
  if ( !a3 || !*((_QWORD *)a3 + 1) || *(_DWORD *)a3 <= 0x38u || !a7 || !a9 )
  {
    updated = -1073741811;
    goto LABEL_41;
  }
  if ( a8 )
    *a8 = 0;
  *v18 = 0;
  *v17 = 0;
  if ( !a4 && !a6 )
  {
    updated = -1073741811;
LABEL_42:
    *v18 = 0;
    goto LABEL_43;
  }
  updated = DeserializeOpaqueBlob(a3, v47);
  if ( updated < 0 )
    goto LABEL_38;
  v45 = 0;
  v46 = v15;
  v44 = &AutoImpersonateClient::`vftable';
  v19 = AutoLsaImpersonateClient::LsaImpersonate((AutoLsaImpersonateClient *)&v44);
  updated = LiveMapHResultToNtStatus(v19);
  if ( updated < 0
    || (v20 = v47[0],
        v21 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, __int64, void **))(*(_QWORD *)v13 + 48LL))(
                v13,
                *((_QWORD *)v47[0] + 28),
                L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
                0x800000,
                v36),
        v22 = v21,
        v21 < 0)
    && (LODWORD(v33) = v21,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x44Cu,
          L"WLIDCCreateContextEx failed with error 0x%x",
          v33),
        updated = LiveMapHResultToNtStatus(v22),
        updated < 0) )
  {
    AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v44);
    goto LABEL_38;
  }
  AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v44);
  updated = UpdateTokenFromValidationInfo((struct ILiveIdNtService *)v13, v36[0], v20);
  if ( updated < 0 )
    goto LABEL_38;
  if ( a4 )
  {
    VersionTimeStamp = GetVersionTimeStamp(a4, (__int64 *)&a5);
    updated = VersionTimeStamp;
    if ( VersionTimeStamp == -1073741275 )
    {
      if ( v16 )
        *v16 = 1;
      updated = 0;
    }
    else
    {
      if ( VersionTimeStamp < 0 )
        goto LABEL_38;
      v24 = (*(__int64 (__fastcall **)(void *, void *, _QWORD, const wchar_t *, _QWORD, struct _AP_BLOB *, unsigned __int16 **))(*(_QWORD *)v13 + 128LL))(
              v13,
              v36[0],
              0,
              L"CredentialKey",
              0,
              a5,
              &Source);
      v25 = v24;
      if ( v24 == -2147186523 )
      {
        v26 = 0;
        if ( v16 )
          *v16 = 1;
        goto LABEL_30;
      }
      if ( v24 >= 0 )
      {
        updated = BuildCredentialKey(Source, a4, &v40);
        if ( updated < 0 )
          goto LABEL_38;
        v26 = v40;
        goto LABEL_30;
      }
      LODWORD(v34) = v24;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        0x488u,
        L"WLIDCGetKeyWithVersion failed with error 0x%x",
        v34);
      updated = LiveMapHResultToNtStatus(v25);
      if ( updated < 0 )
        goto LABEL_38;
    }
  }
  v26 = 0;
LABEL_30:
  if ( !a6 )
  {
    v29 = 0;
    goto LABEL_36;
  }
  v27 = (*(__int64 (__fastcall **)(void *, void *, _QWORD, const wchar_t *, struct _AP_BLOB **, unsigned __int16 **, struct _AP_BLOB **))(*(_QWORD *)v13 + 120LL))(
          v13,
          v36[0],
          0,
          L"CredentialKey",
          &a10,
          &Source,
          &a5);
  v28 = v27;
  if ( v27 >= 0
    || (LODWORD(v35) = v27,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x4A0u,
          L"WLIDCGetKeyLatest failed with error 0x%x",
          v35),
        updated = LiveMapHResultToNtStatus(v28),
        updated >= 0) )
  {
    GetVersionGuid((__int64)a5, &v48);
    updated = BuildCredentialKey(Source, &v48, &v37);
    if ( updated >= 0 )
    {
      v29 = v37;
LABEL_36:
      v40 = 0;
      v41 = 0;
      *v18 = v26;
      v37 = 0;
      v38 = 0;
      *v17 = v29;
    }
  }
LABEL_38:
  if ( updated >= 0 )
    goto LABEL_47;
LABEL_41:
  if ( v18 )
    goto LABEL_42;
LABEL_43:
  if ( v17 )
    *v17 = 0;
  if ( v16 )
    *v16 = 0;
LABEL_47:
  v30 = updated;
  CTraceFuncW<long>::~CTraceFuncW<long>(v50);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(v36);
  Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>::~Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>(&v37);
  Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>::~Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>(&v40);
  if ( a10 )
  {
    LiveFree(a10);
    a10 = 0;
  }
  if ( Source )
  {
    LiveFree(Source);
    Source = 0;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v43 - 24));
  ATL::CRegKey::Close((ATL::CRegKey *)v49);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(v47);
  return v30;
}

```

## disassembly

```asm
0x180013cd4  mov     [rsp-8+arg_18], rbx
0x180013cd9  mov     [rsp-8+arg_8], rdx
0x180013cde  push    rbp
0x180013cdf  push    rsi
0x180013ce0  push    rdi
0x180013ce1  push    r12
0x180013ce3  push    r13
0x180013ce5  push    r14
0x180013ce7  push    r15
0x180013ce9  lea     rbp, [rsp-10h]
0x180013cee  sub     rsp, 110h
0x180013cf5  mov     r12, r9
0x180013cf8  mov     r15, r8
0x180013cfb  mov     rbx, rcx
0x180013cfe  xor     edi, edi
0x180013d00  mov     dword ptr [rbp+40h+arg_8], edi
0x180013d03  mov     [rbp+40h+var_90], rdi
0x180013d07  mov     [rbp+40h+var_80], rdi
0x180013d0b  mov     [rbp+40h+var_88], rdi
0x180013d0f  mov     [rbp+40h+var_68], rdi
0x180013d13  mov     [rbp+40h+var_60], rdi
0x180013d17  mov     [rbp+40h+var_58], rdi
0x180013d1b  lea     rcx, [rbp+40h+var_B0]
0x180013d1f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180013d24  nop
0x180013d25  mov     [rbp+40h+arg_20], rdi
0x180013d29  xorps   xmm0, xmm0
0x180013d2c  movups  xmmword ptr [rbp+40h+var_78.Data1], xmm0
0x180013d30  mov     [rbp+40h+Source], rdi
0x180013d34  mov     [rbp+40h+arg_48], rdi
0x180013d3b  mov     [rsp+140h+var_D0], rdi
0x180013d40  mov     [rbp+40h+var_C0], rdi
0x180013d44  mov     [rsp+140h+var_C8], rdi
0x180013d49  mov     [rsp+140h+var_E8], rdi
0x180013d4e  mov     [rsp+140h+var_D8], rdi
0x180013d53  mov     [rsp+140h+var_E0], rdi
0x180013d58  mov     rax, [rbx]
0x180013d5b  mov     rcx, rbx
0x180013d5e  mov     rax, [rax+18h]
0x180013d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d67  mov     r14, rax
0x180013d6a  mov     [rsp+140h+var_100], rdi
0x180013d6f  mov     [rsp+140h+var_F0], rax
0x180013d74  mov     [rsp+140h+var_F8], rdi
0x180013d79  mov     rcx, [rbx]
0x180013d7c  mov     rax, [rcx+8]
0x180013d80  mov     rcx, rbx
0x180013d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d88  mov     rdx, rax
0x180013d8b  mov     rcx, [rax]
0x180013d8e  mov     rax, [rcx+18h]
0x180013d92  mov     rcx, rdx
0x180013d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d9a  mov     r13, rax
0x180013d9d  lea     rdx, aHandlegetkeys; "HandleGetKeys"
0x180013da4  mov     [rbp+40h+var_50], rdx
0x180013da8  lea     rax, [rbp+40h+arg_8]
0x180013dac  mov     [rbp+40h+var_48], rax
0x180013db0  mov     [rbp+40h+var_40], rdi
0x180013db4  mov     [rbp+40h+var_38], rdi
0x180013db8  xor     r9d, r9d; unsigned int
0x180013dbb  mov     r8d, 41Ah; char *
0x180013dc1  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013dc8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180013dcd  nop
0x180013dce  mov     rbx, [rbp+40h+arg_38]
0x180013dd5  mov     rdi, [rbp+40h+arg_40]
0x180013ddc  mov     rsi, [rbp+40h+arg_30]
0x180013de3  xor     eax, eax
0x180013de5  test    r15, r15
0x180013de8  jz      loc_1800140E2
0x180013dee  cmp     [r15+8], rax
0x180013df2  jz      loc_1800140E2
0x180013df8  cmp     dword ptr [r15], 38h ; '8'
0x180013dfc  jbe     loc_1800140E2
0x180013e02  test    rsi, rsi
0x180013e05  jz      loc_1800140E2
0x180013e0b  test    rdi, rdi
0x180013e0e  jz      loc_1800140E2
0x180013e14  test    rbx, rbx
0x180013e17  jz      short loc_180013E1B
0x180013e19  mov     [rbx], eax
0x180013e1b  mov     [rsi], rax
0x180013e1e  mov     [rdi], rax
0x180013e21  test    r12, r12
0x180013e24  jnz     short loc_180013E3A
0x180013e26  cmp     [rbp+40h+arg_28], eax
0x180013e29  jnz     short loc_180013E3A
0x180013e2b  mov     dword ptr [rbp+40h+arg_8], 0C000000Dh
0x180013e32  xor     r13d, r13d
0x180013e35  jmp     loc_1800140F1
0x180013e3a  lea     rdx, [rbp+40h+var_90]; struct MSACloudAPValidationInfo **
0x180013e3e  mov     rcx, r15; struct _AP_BLOB *
0x180013e41  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x180013e46  mov     dword ptr [rbp+40h+arg_8], eax
0x180013e49  test    eax, eax
0x180013e4b  js      loc_1800140D7
0x180013e51  mov     [rbp+40h+var_A0], 0
0x180013e58  mov     [rbp+40h+var_98], r13
0x180013e5c  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x180013e63  mov     [rbp+40h+var_A8], rax
0x180013e67  lea     rcx, [rbp+40h+var_A8]; this
0x180013e6b  call    ?LsaImpersonate@AutoLsaImpersonateClient@@QEAAJXZ; AutoLsaImpersonateClient::LsaImpersonate(void)
0x180013e70  mov     ecx, eax; int
0x180013e72  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180013e77  mov     dword ptr [rbp+40h+arg_8], eax
0x180013e7a  test    eax, eax
0x180013e7c  js      loc_1800140CE
0x180013e82  mov     rax, [r14]
0x180013e85  lea     rcx, [rsp+140h+var_100]
0x180013e8a  mov     [rsp+140h+var_120], rcx
0x180013e8f  mov     r9d, 800000h
0x180013e95  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x180013e9c  mov     r13, [rbp+40h+var_90]
0x180013ea0  mov     rdx, [r13+0E0h]
0x180013ea7  mov     rcx, r14
0x180013eaa  mov     rax, [rax+30h]
0x180013eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eb3  mov     r15d, eax
0x180013eb6  test    eax, eax
0x180013eb8  jns     short loc_180013EEF
0x180013eba  mov     dword ptr [rsp+140h+var_120], eax
0x180013ebe  lea     r9, aWlidccreatecon; "WLIDCCreateContextEx failed with error "...
0x180013ec5  mov     r8d, 44Ch; unsigned int
0x180013ecb  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013ed2  mov     ecx, 2; unsigned __int8
0x180013ed7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180013edc  mov     ecx, r15d; int
0x180013edf  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180013ee4  mov     dword ptr [rbp+40h+arg_8], eax
0x180013ee7  test    eax, eax
0x180013ee9  js      loc_1800140CE
0x180013eef  lea     rcx, [rbp+40h+var_A8]; this
0x180013ef3  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x180013ef8  mov     r8, r13; struct MSACloudAPValidationInfo *
0x180013efb  mov     rdx, [rsp+140h+var_100]; void *
0x180013f00  mov     rcx, r14; struct ILiveIdNtService *
0x180013f03  call    ?UpdateTokenFromValidationInfo@@YAJPEAVILiveIdNtService@@PEAXPEAUMSACloudAPValidationInfo@@@Z; UpdateTokenFromValidationInfo(ILiveIdNtService *,void *,MSACloudAPValidationInfo *)
0x180013f08  mov     dword ptr [rbp+40h+arg_8], eax
0x180013f0b  xor     r13d, r13d
0x180013f0e  test    eax, eax
0x180013f10  js      loc_1800140DA
0x180013f16  test    r12, r12
0x180013f19  jz      loc_180014001
0x180013f1f  lea     rdx, [rbp+40h+arg_20]; __int64 *
0x180013f23  mov     rcx, r12; struct _GUID *
0x180013f26  call    ?GetVersionTimeStamp@@YAJAEBU_GUID@@AEA_J@Z; GetVersionTimeStamp(_GUID const &,__int64 &)
0x180013f2b  mov     dword ptr [rbp+40h+arg_8], eax
0x180013f2e  cmp     eax, 0C0000225h
0x180013f33  jnz     short loc_180013F49
0x180013f35  test    rbx, rbx
0x180013f38  jz      short loc_180013F40
0x180013f3a  mov     dword ptr [rbx], 1
0x180013f40  mov     dword ptr [rbp+40h+arg_8], r13d
0x180013f44  jmp     loc_180014001
0x180013f49  test    eax, eax
0x180013f4b  js      loc_1800140DA
0x180013f51  mov     rcx, [rbp+40h+arg_20]
0x180013f55  mov     rax, [r14]
0x180013f58  lea     rdx, [rbp+40h+Source]
0x180013f5c  mov     [rsp+140h+var_110], rdx
0x180013f61  mov     [rsp+140h+var_118], rcx
0x180013f66  mov     [rsp+140h+var_120], r13
0x180013f6b  lea     r9, aCredentialkey; "CredentialKey"
0x180013f72  xor     r8d, r8d
0x180013f75  mov     rdx, [rsp+140h+var_100]
0x180013f7a  mov     rcx, r14
0x180013f7d  mov     rax, [rax+80h]
0x180013f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f89  mov     r15d, eax
0x180013f8c  cmp     eax, 800488A5h
0x180013f91  jnz     short loc_180013FA3
0x180013f93  mov     r15, r13
0x180013f96  test    rbx, rbx
0x180013f99  jz      short loc_180014004
0x180013f9b  mov     dword ptr [rbx], 1
0x180013fa1  jmp     short loc_180014004
0x180013fa3  test    r15d, r15d
0x180013fa6  js      short loc_180013FCB
0x180013fa8  lea     r8, [rsp+140h+var_D0]; struct _CREDENTIAL_KEY **
0x180013fad  mov     rdx, r12; struct _GUID *
0x180013fb0  mov     rcx, [rbp+40h+Source]; Source
0x180013fb4  call    ?BuildCredentialKey@@YAJPEBGPEAU_GUID@@PEAPEAU_CREDENTIAL_KEY@@@Z; BuildCredentialKey(ushort const *,_GUID *,_CREDENTIAL_KEY * *)
0x180013fb9  mov     dword ptr [rbp+40h+arg_8], eax
0x180013fbc  test    eax, eax
0x180013fbe  js      loc_1800140DA
0x180013fc4  mov     r15, [rsp+140h+var_D0]
0x180013fc9  jmp     short loc_180014004
0x180013fcb  mov     dword ptr [rsp+140h+var_120], r15d
0x180013fd0  lea     r9, aWlidcgetkeywit_0; "WLIDCGetKeyWithVersion failed with erro"...
0x180013fd7  mov     r8d, 488h; unsigned int
0x180013fdd  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013fe4  mov     ecx, 2; unsigned __int8
0x180013fe9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180013fee  mov     ecx, r15d; int
0x180013ff1  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180013ff6  mov     dword ptr [rbp+40h+arg_8], eax
0x180013ff9  test    eax, eax
0x180013ffb  js      loc_1800140DA
0x180014001  mov     r15, r13
0x180014004  cmp     [rbp+40h+arg_28], r13d
0x180014008  jz      loc_1800140AF
0x18001400e  mov     rax, [r14]
0x180014011  lea     rcx, [rbp+40h+arg_20]
0x180014015  mov     [rsp+140h+var_110], rcx
0x18001401a  lea     rcx, [rbp+40h+Source]
0x18001401e  mov     [rsp+140h+var_118], rcx
0x180014023  lea     rcx, [rbp+40h+arg_48]
0x18001402a  mov     [rsp+140h+var_120], rcx
0x18001402f  lea     r9, aCredentialkey; "CredentialKey"
0x180014036  xor     r8d, r8d
0x180014039  mov     rdx, [rsp+140h+var_100]
0x18001403e  mov     rcx, r14
0x180014041  mov     rax, [rax+78h]
0x180014045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001404a  mov     r14d, eax
0x18001404d  test    eax, eax
0x18001404f  jns     short loc_180014082
0x180014051  mov     dword ptr [rsp+140h+var_120], eax
0x180014055  lea     r9, aWlidcgetkeylat; "WLIDCGetKeyLatest failed with error 0x%"...
0x18001405c  mov     r8d, 4A0h; unsigned int
0x180014062  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014069  mov     ecx, 2; unsigned __int8
0x18001406e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014073  mov     ecx, r14d; int
0x180014076  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18001407b  mov     dword ptr [rbp+40h+arg_8], eax
0x18001407e  test    eax, eax
0x180014080  js      short loc_1800140DA
0x180014082  lea     rdx, [rbp+40h+var_78]; struct _GUID *
0x180014086  mov     rcx, [rbp+40h+arg_20]; __int64
0x18001408a  call    ?GetVersionGuid@@YAX_JAEAU_GUID@@@Z; GetVersionGuid(__int64,_GUID &)
0x18001408f  lea     r8, [rsp+140h+var_E8]; struct _CREDENTIAL_KEY **
0x180014094  lea     rdx, [rbp+40h+var_78]; struct _GUID *
0x180014098  mov     rcx, [rbp+40h+Source]; Source
0x18001409c  call    ?BuildCredentialKey@@YAJPEBGPEAU_GUID@@PEAPEAU_CREDENTIAL_KEY@@@Z; BuildCredentialKey(ushort const *,_GUID *,_CREDENTIAL_KEY * *)
0x1800140a1  mov     dword ptr [rbp+40h+arg_8], eax
0x1800140a4  test    eax, eax
0x1800140a6  js      short loc_1800140DA
0x1800140a8  mov     rax, [rsp+140h+var_E8]
0x1800140ad  jmp     short loc_1800140B2
0x1800140af  mov     rax, r13
0x1800140b2  mov     [rsp+140h+var_D0], r13
0x1800140b7  mov     [rsp+140h+var_C8], r13
0x1800140bc  mov     [rsi], r15
0x1800140bf  mov     [rsp+140h+var_E8], r13
0x1800140c4  mov     [rsp+140h+var_E0], r13
0x1800140c9  mov     [rdi], rax
0x1800140cc  jmp     short loc_1800140DA
0x1800140ce  lea     rcx, [rbp+40h+var_A8]; this
0x1800140d2  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x1800140d7  xor     r13d, r13d
0x1800140da  cmp     dword ptr [rbp+40h+arg_8], r13d
0x1800140de  jge     short loc_180014104
0x1800140e0  jmp     short loc_1800140EC
0x1800140e2  mov     dword ptr [rbp+40h+arg_8], 0C000000Dh
0x1800140e9  xor     r13d, r13d
0x1800140ec  test    rsi, rsi
0x1800140ef  jz      short loc_1800140F4
0x1800140f1  mov     [rsi], r13
0x1800140f4  test    rdi, rdi
0x1800140f7  jz      short loc_1800140FC
0x1800140f9  mov     [rdi], r13
0x1800140fc  test    rbx, rbx
0x1800140ff  jz      short loc_180014104
0x180014101  mov     [rbx], r13d
0x180014104  mov     ebx, dword ptr [rbp+40h+arg_8]
0x180014107  lea     rcx, [rbp+40h+var_50]
0x18001410b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180014110  nop
0x180014111  lea     rcx, [rsp+140h+var_100]
0x180014116  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VILiveIdNtService@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(void)
0x18001411b  nop
0x18001411c  lea     rcx, [rsp+140h+var_E8]
0x180014121  call    ??1?$Auto@PEAU_CREDENTIAL_KEY@@VCredentialKeyFunctor@@VDummyContext@@@@QEAA@XZ; Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>::~Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>(void)
0x180014126  nop
0x180014127  lea     rcx, [rsp+140h+var_D0]
0x18001412c  call    ??1?$Auto@PEAU_CREDENTIAL_KEY@@VCredentialKeyFunctor@@VDummyContext@@@@QEAA@XZ; Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>::~Auto<_CREDENTIAL_KEY *,CredentialKeyFunctor,DummyContext>(void)
0x180014131  nop
0x180014132  mov     rcx, [rbp+40h+arg_48]; void *
0x180014139  test    rcx, rcx
0x18001413c  jz      short loc_18001414A
0x18001413e  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180014143  mov     [rbp+40h+arg_48], r13
0x18001414a  mov     rcx, [rbp+40h+Source]; void *
0x18001414e  test    rcx, rcx
0x180014151  jz      short loc_18001415C
0x180014153  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x180014158  mov     [rbp+40h+Source], r13
0x18001415c  mov     rcx, [rbp+40h+var_B0]
0x180014160  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180014164  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180014169  nop
0x18001416a  lea     rcx, [rbp+40h+var_68]; this
0x18001416e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014173  nop
0x180014174  lea     rcx, [rbp+40h+var_90]
0x180014178  call    ??1?$Auto@PEAUMSACloudAPValidationInfo@@VValidationInfoFunctor@@VDummyContext@@@@QEAA@XZ; Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(void)
0x18001417d  mov     eax, ebx
0x18001417f  mov     rbx, [rsp+140h+arg_18]
  ... truncated ...
```
