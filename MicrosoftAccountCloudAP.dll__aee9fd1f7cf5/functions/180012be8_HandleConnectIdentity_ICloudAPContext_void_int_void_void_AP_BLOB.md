# HandleConnectIdentity(ICloudAPContext *,void *,int,void *,void *,_AP_BLOB *)

- ea: `0x180012be8`
- end: `0x180013142`
- name: `?HandleConnectIdentity@@YAJPEAVICloudAPContext@@PEAXH11PEAU_AP_BLOB@@@Z`
- size: `1370`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, int, void *, __int64, struct _AP_BLOB *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009b50`

## callees

- `0x1800011fc`
- `0x1800013c4`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000d980`
- `0x18000e0f0`
- `0x180010064`
- `0x1800112f0`
- `0x180012130`
- `0x1800121b4`
- `0x180012be8`
- `0x180015338`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d8e`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180012d6d`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180012d6d`

## string_xrefs

- `0x180012ca5`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012d50`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012db0`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012e5f`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012fba`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013058`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180012d43`: `Local Sid = %ls. Profile loaded = %d`
- `0x180012fad`: `WLIDCUpdateConnectedIdentity failed with error 0x%x`
- `0x180013010`: `GetCurrentUserSidString failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall HandleConnectIdentity(
        struct ICloudAPContext *a1,
        void *a2,
        int a3,
        void *a4,
        __int64 a5,
        struct _AP_BLOB *a6)
{
  __int64 v9; // r13
  __int64 v10; // r14
  void *v11; // rdi
  void *v12; // r12
  signed int LastError; // ebx
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct MSACloudAPValidationInfo *v18; // r14
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rbx
  int v24; // eax
  const unsigned __int16 *v25; // r9
  unsigned int v26; // r8d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const unsigned __int16 *v31; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+20h] [rbp-E0h]
  void *v35[3]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v36[3]; // [rsp+58h] [rbp-A8h] BYREF
  void **v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+78h] [rbp-88h]
  __int64 v39; // [rsp+80h] [rbp-80h]
  struct MSACloudAPValidationInfo *v40[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v41[3]; // [rsp+A0h] [rbp-60h] BYREF
  char *v42; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v43[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v45; // [rsp+E8h] [rbp-18h]
  _QWORD v46[11]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v47; // [rsp+160h] [rbp+60h] BYREF
  struct _LUID Luid; // [rsp+168h] [rbp+68h] BYREF
  int updated; // [rsp+170h] [rbp+70h] BYREF

  updated = 0;
  v44 = 0;
  v45 = 0;
  Luid = 0;
  memset(v41, 0, sizeof(v41));
  memset(v40, 0, sizeof(v40));
  v9 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
  v11 = (void *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v35[0] = 0;
  v35[2] = v11;
  v35[1] = 0;
  v46[0] = "HandleConnectIdentity";
  v46[1] = &updated;
  v46[2] = 0;
  v46[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleConnectIdentity",
    (const char *)0x7D,
    0,
    v31);
  v12 = (void *)a5;
  if ( !a5 || !a6 )
  {
    LastError = -1073741811;
    updated = -1073741811;
    goto LABEL_39;
  }
  LastError = DeserializeOpaqueBlob(a6, v40);
  updated = LastError;
  if ( LastError < 0
    || !(*(unsigned int (__fastcall **)(__int64, void *, _QWORD *))(*(_QWORD *)v10 + 192LL))(v10, v12, v41)
    && ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
      : (LastError = GetLastError()),
        updated = LastError,
        LastError < 0) )
  {
LABEL_39:
    if ( !a3 )
      goto LABEL_41;
LABEL_40:
    LastError = 0;
    updated = 0;
    goto LABEL_41;
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    0x97u,
    L"Local Sid = %ls. Profile loaded = %d",
    v41[0],
    a3);
  if ( a3 )
  {
    memset(v36, 0, sizeof(v36));
    v37 = &AutoImpersonateClient::`vftable';
    v38 = 0;
    v39 = v10;
    if ( !a4 )
    {
      updated = -1073741811;
LABEL_23:
      AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v37);
      Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v36);
      goto LABEL_40;
    }
    v17 = AutoImpersonateClient::Impersonate((AutoImpersonateClient *)&v37, a4);
    updated = LiveMapHResultToNtStatus(v17);
    if ( updated < 0 )
      goto LABEL_23;
    v18 = v40[0];
    v19 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, __int64, void **))(*(_QWORD *)v11 + 48LL))(
            v11,
            *((_QWORD *)v40[0] + 28),
            L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
            8585216,
            v35);
    updated = LiveMapHResultToNtStatus(v19);
    if ( updated < 0 )
      goto LABEL_23;
    updated = UpdateTokenFromValidationInfo((struct ILiveIdNtService *)v11, v35[0], v18);
    if ( updated < 0 )
      goto LABEL_23;
    v20 = (*(__int64 (__fastcall **)(void *, void *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v11 + 200LL))(
            v11,
            v35[0],
            L"ps:password",
            0,
            0);
    updated = LiveMapHResultToNtStatus(v20);
    if ( updated < 0 )
      goto LABEL_23;
    v21 = (*(__int64 (__fastcall **)(void *, void *, __int64))(*(_QWORD *)v11 + 72LL))(v11, v35[0], 1);
    v22 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v34) = v21;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        0xE8u,
        L"WLIDCUpdateConnectedIdentity failed with error 0x%x",
        v34);
      updated = LiveMapHResultToNtStatus(v22);
      if ( updated < 0 )
        goto LABEL_23;
    }
    memset(v43, 0, sizeof(v43));
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 48LL))(v9);
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v23 + 32LL))(v23, v43);
    if ( v24 >= 0 )
    {
      v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, _QWORD *, _QWORD))(*(_QWORD *)v23 + 24LL))(
              v23,
              v43[0],
              L"HasPassword",
              v36,
              0);
      if ( v24 >= 0 )
      {
LABEL_35:
        Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v43);
        if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
        {
          a5 = 50331648;
          v47 = v36[0];
          v42 = (char *)v18 + 8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v27,
            (unsigned int)&byte_18004437F,
            v28,
            v29,
            (__int64)&v42,
            (__int64)&v47,
            (__int64)&a5);
        }
        goto LABEL_23;
      }
      v25 = L"GetStoredIdentityProperty failed with error 0x%x";
      v26 = 252;
    }
    else
    {
      v25 = L"GetCurrentUserSidString failed with error 0x%x";
      v26 = 245;
    }
    LODWORD(v34) = v24;
    TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp", v26, v25, v34);
    goto LABEL_35;
  }
  if ( AllocateLocallyUniqueId(&Luid)
    || ((int)GetLastError() > 0 ? (v14 = (unsigned __int16)GetLastError() | 0xC0070000) : (v14 = GetLastError()),
        updated = v14,
        LODWORD(v32) = v14,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0xA0u,
          L"Failed to allocate locally unique ID, status = 0x%x",
          v32),
        LastError = updated,
        updated >= 0) )
  {
    v15 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, __int64, void **))(*(_QWORD *)v11 + 48LL))(
            v11,
            *((_QWORD *)v40[0] + 28),
            L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
            8585216,
            v35);
    LastError = LiveMapHResultToNtStatus(v15);
    updated = LastError;
    if ( LastError >= 0 )
    {
      *(_QWORD *)&v44 = 2;
      *((struct _LUID *)&v44 + 1) = Luid;
      *(_QWORD *)&v45 = v41[0];
      DWORD2(v45) = 2;
      v16 = (*(__int64 (__fastcall **)(void *, void *, __int128 *))(*(_QWORD *)v11 + 64LL))(v11, v35[0], &v44);
      if ( v16 >= 0 )
      {
        LastError = updated;
      }
      else
      {
        if ( v16 == -2147024713 )
        {
          LODWORD(v33) = -2147024713;
          TracePrintW(
            5u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0xBBu,
            L"The requested user was previously connected. (hr = 0x%x)",
            v33);
          v16 = 0;
        }
        LastError = LiveMapHResultToNtStatus(v16);
        updated = LastError;
      }
    }
  }
LABEL_41:
  CTraceFuncW<long>::~CTraceFuncW<long>(v46);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(v35);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>(v40);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(v41);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180012be8  mov     [rsp-8+arg_18], rbx
0x180012bed  mov     qword ptr [rsp-8+Luid.LowPart], rdx
0x180012bf2  push    rbp
0x180012bf3  push    rsi
0x180012bf4  push    rdi
0x180012bf5  push    r12
0x180012bf7  push    r13
0x180012bf9  push    r14
0x180012bfb  push    r15
0x180012bfd  lea     rbp, [rsp-20h]
0x180012c02  sub     rsp, 120h
0x180012c09  mov     r15, r9
0x180012c0c  mov     esi, r8d
0x180012c0f  mov     rbx, rcx
0x180012c12  xor     r12d, r12d
0x180012c15  mov     [rbp+50h+arg_10], r12d
0x180012c19  xorps   xmm0, xmm0
0x180012c1c  movups  [rbp+50h+var_78], xmm0
0x180012c20  movups  [rbp+50h+var_68], xmm0
0x180012c24  mov     qword ptr [rbp+50h+Luid.LowPart], r12
0x180012c28  mov     [rbp+50h+var_B0], r12
0x180012c2c  mov     [rbp+50h+var_A0], r12
0x180012c30  mov     [rbp+50h+var_A8], r12
0x180012c34  mov     [rbp+50h+var_C8], r12
0x180012c38  mov     [rbp+50h+var_B8], r12
0x180012c3c  mov     [rbp+50h+var_C0], r12
0x180012c40  mov     rax, [rcx]
0x180012c43  mov     rax, [rax+8]
0x180012c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c4c  mov     r13, rax
0x180012c4f  mov     rcx, [rax]
0x180012c52  mov     rax, [rcx+18h]
0x180012c56  mov     rcx, r13
0x180012c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5e  mov     r14, rax
0x180012c61  mov     rcx, [rbx]
0x180012c64  mov     rax, [rcx+18h]
0x180012c68  mov     rcx, rbx
0x180012c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c70  mov     rdi, rax
0x180012c73  mov     [rsp+150h+var_110], r12
0x180012c78  mov     [rsp+150h+var_100], rax
0x180012c7d  mov     [rsp+150h+var_108], r12
0x180012c82  lea     rdx, aHandleconnecti; "HandleConnectIdentity"
0x180012c89  mov     [rbp+50h+var_58], rdx
0x180012c8d  lea     rax, [rbp+50h+arg_10]
0x180012c91  mov     [rbp+50h+var_50], rax
0x180012c95  mov     [rbp+50h+var_48], r12
0x180012c99  mov     [rbp+50h+var_40], r12
0x180012c9d  xor     r9d, r9d; unsigned int
0x180012ca0  lea     r8d, [r12+7Dh]; char *
0x180012ca5  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012cac  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180012cb1  nop
0x180012cb2  mov     r12, [rbp+50h+arg_20]
0x180012cb9  test    r12, r12
0x180012cbc  jz      loc_1800130E8
0x180012cc2  mov     rcx, [rbp+50h+arg_28]; struct _AP_BLOB *
0x180012cc9  test    rcx, rcx
0x180012ccc  jz      loc_1800130E8
0x180012cd2  lea     rdx, [rbp+50h+var_C8]; struct MSACloudAPValidationInfo **
0x180012cd6  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x180012cdb  mov     ebx, eax
0x180012cdd  mov     [rbp+50h+arg_10], eax
0x180012ce0  test    eax, eax
0x180012ce2  js      loc_1800130F0
0x180012ce8  mov     rax, [r14]
0x180012ceb  lea     r8, [rbp+50h+var_B0]
0x180012cef  mov     rdx, r12
0x180012cf2  mov     rcx, r14
0x180012cf5  mov     rax, [rax+0C0h]
0x180012cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d01  xor     r12d, r12d
0x180012d04  test    eax, eax
0x180012d06  jnz     short loc_180012D36
0x180012d08  call    cs:__imp_GetLastError
0x180012d0e  test    eax, eax
0x180012d10  jg      short loc_180012D1C
0x180012d12  call    cs:__imp_GetLastError
0x180012d18  mov     ebx, eax
0x180012d1a  jmp     short loc_180012D2B
0x180012d1c  call    cs:__imp_GetLastError
0x180012d22  movzx   ebx, ax
0x180012d25  or      ebx, 0C0070000h
0x180012d2b  mov     [rbp+50h+arg_10], ebx
0x180012d2e  test    ebx, ebx
0x180012d30  js      loc_1800130F3
0x180012d36  mov     dword ptr [rsp+150h+var_128], esi
0x180012d3a  mov     rax, [rbp+50h+var_B0]
0x180012d3e  mov     [rsp+150h+var_130], rax
0x180012d43  lea     r9, aLocalSidLsProf; "Local Sid = %ls. Profile loaded = %d"
0x180012d4a  mov     r8d, 97h; unsigned int
0x180012d50  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012d57  mov     ecx, 5; unsigned __int8
0x180012d5c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180012d61  test    esi, esi
0x180012d63  jnz     loc_180012E8C
0x180012d69  lea     rcx, [rbp+50h+Luid]; Luid
0x180012d6d  call    cs:__imp_AllocateLocallyUniqueId
0x180012d73  mov     esi, 2
0x180012d78  test    eax, eax
0x180012d7a  jnz     short loc_180012DC9
0x180012d7c  call    cs:__imp_GetLastError
0x180012d82  test    eax, eax
0x180012d84  jg      short loc_180012D8E
0x180012d86  call    cs:__imp_GetLastError
0x180012d8c  jmp     short loc_180012D9C
0x180012d8e  call    cs:__imp_GetLastError
0x180012d94  movzx   eax, ax
0x180012d97  or      eax, 0C0070000h
0x180012d9c  mov     [rbp+50h+arg_10], eax
0x180012d9f  mov     dword ptr [rsp+150h+var_130], eax
0x180012da3  lea     r9, aFailedToAlloca; "Failed to allocate locally unique ID, s"...
0x180012daa  mov     r8d, 0A0h; unsigned int
0x180012db0  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012db7  mov     ecx, esi; unsigned __int8
0x180012db9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180012dbe  mov     ebx, [rbp+50h+arg_10]
0x180012dc1  test    ebx, ebx
0x180012dc3  js      loc_1800130FD
0x180012dc9  mov     rax, [rdi]
0x180012dcc  lea     rcx, [rsp+150h+var_110]
0x180012dd1  mov     [rsp+150h+var_130], rcx
0x180012dd6  mov     r9d, 830000h
0x180012ddc  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x180012de3  mov     rdx, [rbp+50h+var_C8]
0x180012de7  mov     rdx, [rdx+0E0h]
0x180012dee  mov     rcx, rdi
0x180012df1  mov     rax, [rax+30h]
0x180012df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dfa  mov     ecx, eax; int
0x180012dfc  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012e01  mov     ebx, eax
0x180012e03  mov     [rbp+50h+arg_10], eax
0x180012e06  test    eax, eax
0x180012e08  js      loc_1800130FD
0x180012e0e  mov     qword ptr [rbp+50h+var_78], rsi
0x180012e12  mov     eax, [rbp+50h+Luid.LowPart]
0x180012e15  mov     dword ptr [rbp+50h+var_78+8], eax
0x180012e18  mov     eax, [rbp+50h+Luid.HighPart]
0x180012e1b  mov     dword ptr [rbp+50h+var_78+0Ch], eax
0x180012e1e  mov     rax, [rbp+50h+var_B0]
0x180012e22  mov     qword ptr [rbp+50h+var_68], rax
0x180012e26  mov     dword ptr [rbp+50h+var_68+8], esi
0x180012e29  mov     rax, [rdi]
0x180012e2c  lea     r8, [rbp+50h+var_78]
0x180012e30  mov     rdx, [rsp+150h+var_110]
0x180012e35  mov     rcx, rdi
0x180012e38  mov     rax, [rax+40h]
0x180012e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e41  test    eax, eax
0x180012e43  jns     short loc_180012E84
0x180012e45  mov     edx, 800700B7h
0x180012e4a  cmp     eax, edx
0x180012e4c  jnz     short loc_180012E73
0x180012e4e  mov     dword ptr [rsp+150h+var_130], edx
0x180012e52  lea     r9, aTheRequestedUs; "The requested user was previously conne"...
0x180012e59  mov     r8d, 0BBh; unsigned int
0x180012e5f  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012e66  mov     ecx, 5; unsigned __int8
0x180012e6b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180012e70  mov     eax, r12d
0x180012e73  mov     ecx, eax; int
0x180012e75  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012e7a  mov     ebx, eax
0x180012e7c  mov     [rbp+50h+arg_10], eax
0x180012e7f  jmp     loc_1800130FD
0x180012e84  mov     ebx, [rbp+50h+arg_10]
0x180012e87  jmp     loc_1800130FD
0x180012e8c  mov     [rsp+150h+var_F8], r12
0x180012e91  mov     [rsp+150h+var_E8], r12
0x180012e96  mov     [rsp+150h+var_F0], r12
0x180012e9b  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x180012ea2  mov     [rsp+150h+var_E0], rax
0x180012ea7  mov     [rsp+150h+var_D8], r12d
0x180012eac  mov     [rbp+50h+var_D0], r14
0x180012eb0  test    r15, r15
0x180012eb3  jnz     short loc_180012ED7
0x180012eb5  mov     ebx, 0C000000Dh
0x180012eba  mov     [rbp+50h+arg_10], ebx
0x180012ebd  lea     rcx, [rsp+150h+var_E0]; this
0x180012ec2  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x180012ec7  nop
0x180012ec8  lea     rcx, [rsp+150h+var_F8]
0x180012ecd  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180012ed2  jmp     loc_1800130F7
0x180012ed7  mov     rdx, r15; void *
0x180012eda  lea     rcx, [rsp+150h+var_E0]; this
0x180012edf  call    ?Impersonate@AutoImpersonateClient@@QEAAJPEAX@Z; AutoImpersonateClient::Impersonate(void *)
0x180012ee4  mov     ecx, eax; int
0x180012ee6  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012eeb  mov     [rbp+50h+arg_10], eax
0x180012eee  test    eax, eax
0x180012ef0  js      short loc_180012EBD
0x180012ef2  mov     rax, [rdi]
0x180012ef5  lea     rcx, [rsp+150h+var_110]
0x180012efa  mov     [rsp+150h+var_130], rcx
0x180012eff  mov     r9d, 830000h
0x180012f05  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x180012f0c  mov     r14, [rbp+50h+var_C8]
0x180012f10  mov     rdx, [r14+0E0h]
0x180012f17  mov     rcx, rdi
0x180012f1a  mov     rax, [rax+30h]
0x180012f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f23  mov     ecx, eax; int
0x180012f25  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012f2a  mov     [rbp+50h+arg_10], eax
0x180012f2d  test    eax, eax
0x180012f2f  js      short loc_180012EBD
0x180012f31  mov     r8, r14; struct MSACloudAPValidationInfo *
0x180012f34  mov     rdx, [rsp+150h+var_110]; void *
0x180012f39  mov     rcx, rdi; struct ILiveIdNtService *
0x180012f3c  call    ?UpdateTokenFromValidationInfo@@YAJPEAVILiveIdNtService@@PEAXPEAUMSACloudAPValidationInfo@@@Z; UpdateTokenFromValidationInfo(ILiveIdNtService *,void *,MSACloudAPValidationInfo *)
0x180012f41  mov     [rbp+50h+arg_10], eax
0x180012f44  test    eax, eax
0x180012f46  js      loc_180012EBD
0x180012f4c  mov     rax, [rdi]
0x180012f4f  mov     [rsp+150h+var_130], r12
0x180012f54  xor     r9d, r9d
0x180012f57  lea     r8, aPsPassword; "ps:password"
0x180012f5e  mov     rdx, [rsp+150h+var_110]
0x180012f63  mov     rcx, rdi
0x180012f66  mov     rax, [rax+0C8h]
0x180012f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f72  mov     ecx, eax; int
0x180012f74  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012f79  mov     [rbp+50h+arg_10], eax
0x180012f7c  test    eax, eax
0x180012f7e  js      loc_180012EBD
0x180012f84  mov     rax, [rdi]
0x180012f87  mov     r8d, 1
0x180012f8d  mov     rdx, [rsp+150h+var_110]
0x180012f92  mov     rcx, rdi
0x180012f95  mov     rax, [rax+48h]
0x180012f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f9e  mov     ebx, eax
0x180012fa0  mov     esi, 2
0x180012fa5  test    eax, eax
0x180012fa7  jns     short loc_180012FDA
0x180012fa9  mov     dword ptr [rsp+150h+var_130], eax
0x180012fad  lea     r9, aWlidcupdatecon_0; "WLIDCUpdateConnectedIdentity failed wit"...
0x180012fb4  mov     r8d, 0E8h; unsigned int
0x180012fba  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180012fc1  mov     ecx, esi; unsigned __int8
0x180012fc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180012fc8  mov     ecx, ebx; int
0x180012fca  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180012fcf  mov     [rbp+50h+arg_10], eax
0x180012fd2  test    eax, eax
0x180012fd4  js      loc_180012EBD
0x180012fda  mov     [rbp+50h+var_90], r12
0x180012fde  mov     [rbp+50h+var_80], r12
0x180012fe2  mov     [rbp+50h+var_88], r12
0x180012fe6  mov     rax, [r13+0]
0x180012fea  mov     rcx, r13
0x180012fed  mov     rax, [rax+30h]
0x180012ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ff6  mov     rbx, rax
0x180012ff9  mov     rdx, [rax]
0x180012ffc  mov     rax, [rdx+20h]
0x180013000  lea     rdx, [rbp+50h+var_90]
0x180013004  mov     rcx, rbx
0x180013007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001300c  test    eax, eax
0x18001300e  jns     short loc_18001301F
0x180013010  lea     r9, aGetcurrentuser; "GetCurrentUserSidString failed with err"...
0x180013017  mov     r8d, 0F5h
0x18001301d  jmp     short loc_180013054
0x18001301f  mov     rax, [rbx]
0x180013022  mov     [rsp+150h+var_130], r12
0x180013027  lea     r9, [rsp+150h+var_F8]
0x18001302c  lea     r8, aHaspassword; "HasPassword"
0x180013033  mov     rdx, [rbp+50h+var_90]
0x180013037  mov     rcx, rbx
0x18001303a  mov     rax, [rax+18h]
0x18001303e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013043  test    eax, eax
0x180013045  jns     short loc_180013067
0x180013047  lea     r9, aGetstoredident_0; "GetStoredIdentityProperty failed with e"...
0x18001304e  mov     r8d, 0FCh; unsigned int
0x180013054  mov     dword ptr [rsp+150h+var_130], eax
0x180013058  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001305f  mov     ecx, esi; unsigned __int8
0x180013061  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180013066  nop
0x180013067  lea     rcx, [rbp+50h+var_90]
0x18001306b  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x180013070  mov     eax, cs:dword_18004D048
0x180013076  cmp     eax, 5
0x180013079  jbe     loc_180012EBD
0x18001307f  mov     rdx, 400000000000h
0x180013089  lea     rcx, dword_18004D048
0x180013090  call    _tlgKeywordOn
0x180013095  test    al, al
0x180013097  jz      loc_180012EBD
0x18001309d  mov     [rbp+50h+arg_20], 3000000h
0x1800130a8  mov     rax, [rsp+150h+var_F8]
0x1800130ad  mov     [rbp+50h+arg_0], rax
0x1800130b1  lea     rax, [r14+8]
0x1800130b5  mov     [rbp+50h+var_98], rax
  ... truncated ...
```
