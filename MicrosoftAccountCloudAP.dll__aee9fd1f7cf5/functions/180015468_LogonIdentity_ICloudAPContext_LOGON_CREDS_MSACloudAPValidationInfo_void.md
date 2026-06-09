# LogonIdentity(ICloudAPContext *,LOGON_CREDS *,MSACloudAPValidationInfo *,void * *)

- ea: `0x180015468`
- end: `0x180015d0b`
- name: `?LogonIdentity@@YAJPEAVICloudAPContext@@PEAULOGON_CREDS@@PEAUMSACloudAPValidationInfo@@PEAPEAX@Z`
- size: `2211`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, struct LOGON_CREDS *, struct MSACloudAPValidationInfo *, void **)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800141a0`

## callees

- `0x1800011fc`
- `0x1800014bc`
- `0x180001584`
- `0x180003160`
- `0x180003b14`
- `0x180007484`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x180010064`
- `0x1800112f0`
- `0x180012130`
- `0x1800121b4`
- `0x18001223c`
- `0x18001254c`
- `0x180015468`
- `0x180015d14`
- `0x18002466c`
- `0x180024814`
- `0x1800267c0`
- `0x180027724`
- `0x180029ed4`
- `0x18002a0c8`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015697`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015afe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015697`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015713`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001570b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015713`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x1800156f4`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x1800156f4`

## string_xrefs

- `0x180015576`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800155c5`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x18001567a`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180015736`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180015989`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180015c00`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180015a8d`: `DefaultCredsUpdateRequired`
- `0x1800155b8`: `Failed to retrieve the requested user's SID, hr = 0x%x`
- `0x18001566d`: `Caller Local Sid = %ls.`
- `0x18001597c`: `Attempting live authentication with cred type = %d`
- `0x180015ac2`: `WriteBufferToRegistry failed with 0x%x, continuing...`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LogonIdentity(
        struct ICloudAPContext *a1,
        const unsigned __int16 **a2,
        struct MSACloudAPValidationInfo *a3,
        void **a4)
{
  int v7; // r15d
  struct ILiveIdNtService *v8; // rsi
  struct IWinApiLite *v9; // r13
  __int64 v10; // r12
  int SID; // eax
  unsigned __int16 *v12; // rdi
  int v13; // eax
  int v14; // r14d
  unsigned int LastError; // eax
  _BOOL8 v16; // rdx
  int v17; // r8d
  __int64 v18; // r14
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  int v23; // r14d
  unsigned __int8 *v24; // r15
  int v25; // eax
  const unsigned __int16 *v26; // rax
  int v27; // eax
  int updated; // eax
  int v29; // eax
  HKEY v30; // rdx
  const unsigned __int16 *v31; // r9
  int v32; // ebx
  int v33; // eax
  unsigned __int8 *v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // r9
  void *v41; // rax
  void ***v42; // rcx
  __int64 v43; // rcx
  int v44; // eax
  unsigned int v45; // ebx
  unsigned int *v47; // [rsp+20h] [rbp-E0h]
  unsigned int *v48; // [rsp+20h] [rbp-E0h]
  unsigned int *v49; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v50; // [rsp+20h] [rbp-E0h]
  unsigned int *v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v53; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 *v54; // [rsp+68h] [rbp-98h] BYREF
  struct IExecutionContextLite *v55; // [rsp+70h] [rbp-90h] BYREF
  struct MSACloudAPValidationInfo *v56; // [rsp+78h] [rbp-88h] BYREF
  struct ICloudAPContext *v57; // [rsp+80h] [rbp-80h] BYREF
  void **v58; // [rsp+88h] [rbp-78h] BYREF
  __int64 v59; // [rsp+90h] [rbp-70h]
  struct IWinApiLite *v60; // [rsp+98h] [rbp-68h]
  void *v61; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  struct ILiveIdNtService *v63; // [rsp+B0h] [rbp-50h]
  struct _LUID Luid; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 *v65; // [rsp+C0h] [rbp-40h] BYREF
  void **v66; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-30h]
  struct IWinApiLite *v68; // [rsp+D8h] [rbp-28h]
  struct IExecutionContextLite *v69; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v70; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v71; // [rsp+F0h] [rbp-10h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  void **v73; // [rsp+100h] [rbp+0h]
  _QWORD v74[5]; // [rsp+108h] [rbp+8h] BYREF
  char v75[8]; // [rsp+130h] [rbp+30h] BYREF
  int v76; // [rsp+138h] [rbp+38h]
  const wchar_t *v77; // [rsp+140h] [rbp+40h]
  const unsigned __int16 *v78; // [rsp+148h] [rbp+48h]
  int v79; // [rsp+150h] [rbp+50h]
  const unsigned __int16 *v80; // [rsp+158h] [rbp+58h]
  int v81; // [rsp+160h] [rbp+60h]
  const unsigned __int16 *v82; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v83; // [rsp+170h] [rbp+70h]
  unsigned __int16 v84[264]; // [rsp+180h] [rbp+80h] BYREF

  v73 = a4;
  v56 = a3;
  v57 = a1;
  v7 = 0;
  v52 = 0;
  v65 = 0;
  v54 = 0;
  v53 = 0;
  v70 = 0;
  v72 = 0;
  v71 = 0;
  memset_0(v75, 0, 0x48u);
  Luid = 0;
  memset_0(v84, 0, 0x208u);
  v55 = (struct IExecutionContextLite *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v8 = (struct ILiveIdNtService *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v9 = (struct IWinApiLite *)(*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)v55 + 24LL))(v55);
  v10 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)v55 + 48LL))(v55);
  v61 = 0;
  v63 = v8;
  v62 = 0;
  v69 = v55;
  v74[0] = "LogonIdentity";
  v74[1] = &v52;
  v74[2] = 0;
  v74[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "LogonIdentity",
    (const char *)0x4EB,
    0,
    (const unsigned __int16 *)v47);
  if ( !a2 || !*a2 || !a4 )
  {
    v52 = -1073741811;
    v16 = 0;
    goto LABEL_69;
  }
  *a4 = 0;
  SID = CWLIDCCHelper::GetSID(v9, *a2, &v70);
  if ( SID >= 0 )
  {
    v12 = v70;
  }
  else
  {
    LODWORD(v48) = SID;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
      0x4FEu,
      L"Failed to retrieve the requested user's SID, hr = 0x%x",
      v48);
    v66 = 0;
    v68 = 0;
    v67 = 0;
    v12 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v66);
  }
  LODWORD(v67) = 0;
  v68 = v9;
  v66 = &AutoImpersonateClient::`vftable';
  v58 = 0;
  v60 = 0;
  v59 = 0;
  v13 = AutoLsaImpersonateClient::LsaImpersonate((AutoLsaImpersonateClient *)&v66);
  v52 = LiveMapHResultToNtStatus(v13);
  if ( v52 < 0
    || (v14 = (*(__int64 (__fastcall **)(__int64, void ***))(*(_QWORD *)v10 + 32LL))(v10, &v58),
        v52 = LiveMapHResultToNtStatus(v14),
        v52 < 0) )
  {
    Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v58);
    v42 = &v66;
    goto LABEL_63;
  }
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    0x50Fu,
    L"Caller Local Sid = %ls.",
    v58);
  if ( v12 && (unsigned int)_o__wcsicmp(v58, v12) )
    v7 = 1;
  else
    v14 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, const unsigned __int16 *, const wchar_t *, __int64, void **))(*(_QWORD *)v8 + 48LL))(
            v8,
            *a2,
            L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
            8585216,
            &v61);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v58);
  AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v66);
  if ( !v7 )
  {
LABEL_20:
    v52 = LiveMapHResultToNtStatus(v14);
    if ( v52 < 0 )
      goto LABEL_65;
    if ( *((_DWORD *)a2 + 6) == 3 )
    {
      v18 = 33563136;
      goto LABEL_34;
    }
    LODWORD(v59) = 0;
    v60 = v9;
    v58 = &AutoImpersonateClient::`vftable';
    if ( !v7 )
    {
      v19 = AutoLsaImpersonateClient::LsaImpersonate((AutoLsaImpersonateClient *)&v58);
      v52 = LiveMapHResultToNtStatus(v19);
      if ( v52 < 0 )
        goto LABEL_62;
    }
    v20 = *((_DWORD *)a2 + 6);
    if ( v20 == 2 )
    {
      v21 = CredSerializationHelper::SerializeNgcKeyNameAndAuthTicket(v55, a2[4], a2[19], &v54, &v53);
    }
    else
    {
      if ( v20 != 1 )
      {
        LODWORD(v49) = *((_DWORD *)a2 + 6);
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x55Fu,
          L"Bogus cred type, pLogonCreds->credType = %d",
          v49);
        v52 = -1073741811;
LABEL_62:
        v42 = &v58;
LABEL_63:
        AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)v42);
LABEL_65:
        if ( v52 >= 0 )
          goto LABEL_75;
        goto LABEL_66;
      }
      v22 = -1;
      do
        ++v22;
      while ( a2[4][v22] );
      v21 = CredSerializationHelper::SerializeCredentials(v55, 1, 1);
    }
    v23 = v21;
    CMIDLPtr<unsigned short *>::Clear(&v65);
    v24 = v54;
    v65 = v54;
    v52 = LiveMapHResultToNtStatus(v23);
    if ( v52 >= 0 )
    {
      v25 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, void *, _QWORD, _QWORD, unsigned __int8 *))(*(_QWORD *)v8 + 176LL))(
              v8,
              v61,
              0,
              v53,
              v24);
      v52 = LiveMapHResultToNtStatus(v25);
      if ( v52 >= 0 )
      {
        v18 = 0x200000000LL;
        AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v58);
LABEL_34:
        v26 = a2[7];
        if ( v26 )
        {
          v77 = L"http://Passport.NET/tb";
          v76 = 0;
          v78 = v26;
          v83 = a2[13];
          v82 = a2[10];
          v80 = a2[16];
          v81 = 1;
          v79 = *((_DWORD *)a2 + 44);
          v27 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, void *, char *, _QWORD))(*(_QWORD *)v8 + 208LL))(
                  v8,
                  v61,
                  v75,
                  0);
          updated = LiveMapHResultToNtStatus(v27);
        }
        else
        {
          if ( !v56 )
            goto LABEL_39;
          updated = UpdateTokenFromValidationInfo(v8, v61, v56);
        }
        v52 = updated;
        if ( updated < 0 )
          goto LABEL_65;
LABEL_39:
        LODWORD(v49) = *((_DWORD *)a2 + 6);
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x58Fu,
          L"Attempting live authentication with cred type = %d",
          v49);
        v52 = AcquireTokenFromSvc(v57, v61, v18, a2[23]);
        if ( v52 < 0 )
          goto LABEL_65;
        if ( !v12 )
          goto LABEL_59;
        v53 = 0;
        if ( (*(int (__fastcall **)(__int64, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v10 + 16LL))(
               v10,
               v12,
               &v53,
               0) < 0
          || !v53 )
        {
          goto LABEL_59;
        }
        v50 = *a2;
        v29 = StringCchPrintfW(v84, 0x104u, L"%ls\\%ls\\%ls", L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
        if ( v29 < 0 )
        {
          LODWORD(v50) = v29;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0x5B3u,
            L"StringCchPrintf failed with 0x%x, continuing...",
            v50);
LABEL_59:
          v41 = v61;
          v61 = 0;
          v62 = 0;
          *v73 = v41;
          goto LABEL_65;
        }
        v54 = 0;
        v32 = RegistryHelper::ReadBufferFromRegistry(
                (RegistryHelper *)&v69,
                v30,
                v84,
                v31,
                (bool)v50,
                &v54,
                (unsigned int *)&v55);
        if ( v32 == -2147024894 )
        {
          if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x200000000000LL) )
          {
            v57 = (struct ICloudAPContext *)50331648;
            LODWORD(v55) = -2147024894;
            v56 = (struct MSACloudAPValidationInfo *)v12;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v38,
              (__int64)byte_18004411B,
              v39,
              v40,
              (const unsigned __int16 **)&v56,
              (__int64)&v55,
              (__int64)&v57);
          }
          goto LABEL_58;
        }
        v33 = RegistryHelper::WriteBufferToRegistry(
                (RegistryHelper *)&v69,
                0,
                v84,
                L"DefaultCredSaved",
                1u,
                (unsigned __int8 *)L"DefaultCredsUpdateRequired",
                0x38u);
        if ( v33 >= 0 )
        {
          if ( v32 >= 0 )
          {
            v34 = v54;
            if ( v54 )
            {
              if ( !(unsigned int)_o__wcsicmp(v54, L"DefaultCredsUpdateRequired") )
                goto LABEL_58;
            }
            else
            {
              v34 = 0;
            }
            if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
            {
              v57 = (struct ICloudAPContext *)50331648;
              v56 = (struct MSACloudAPValidationInfo *)v34;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v35,
                (__int64)byte_180044151,
                v36,
                v37,
                (const unsigned __int16 **)&v56,
                (__int64)&v57);
            }
          }
        }
        else
        {
          LODWORD(v51) = v33;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0x5CFu,
            L"WriteBufferToRegistry failed with 0x%x, continuing...",
            v51);
        }
LABEL_58:
        CMIDLPtr<unsigned short *>::Clear(&v54);
        goto LABEL_59;
      }
    }
    goto LABEL_62;
  }
  if ( AllocateLocallyUniqueId(&Luid)
    || ((int)GetLastError() > 0
      ? (LastError = (unsigned __int16)GetLastError() | 0xC0070000)
      : (LastError = GetLastError()),
        v52 = LastError,
        LODWORD(v49) = LastError,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x525u,
          L"Failed to allocate locally unique ID, status = 0x%x",
          v49),
        v52 >= 0) )
  {
    v14 = (*(__int64 (__fastcall **)(struct ILiveIdNtService *, const unsigned __int16 *, unsigned __int16 *, _QWORD, LONG, __int64, void **))(*(_QWORD *)v8 + 56LL))(
            v8,
            *a2,
            v12,
            Luid.LowPart,
            Luid.HighPart,
            12779520,
            &v61);
    goto LABEL_20;
  }
LABEL_66:
  v16 = 0;
  v53 = 0;
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64, unsigned __int16 *, unsigned int *, _QWORD))(*(_QWORD *)v10 + 16LL))(
      v10,
      v12,
      &v53,
      0);
    v16 = v53 == 1;
  }
LABEL_69:
  v43 = 0;
  while ( 1 )
  {
    v17 = 3 * v43;
    if ( v52 == *((_DWORD *)qword_18003AAC0 + 3 * v43) && v16 == *((_DWORD *)qword_18003AAC0 + 3 * v43 + 1) )
      break;
    if ( (unsigned __int64)++v43 >= 0xA )
    {
      v44 = -1073741718;
      goto LABEL_74;
    }
  }
  v44 = *((_DWORD *)&qword_18003AAC0[1] + 3 * v43);
LABEL_74:
  v52 = v44;
LABEL_75:
  v45 = v52;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v74, v16, v17);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>((__int64 *)&v61);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v70);
  CMIDLPtr<unsigned short *>::Clear(&v65);
  return v45;
}

```

## disassembly

```asm
0x180015468  push    rbp
0x18001546a  push    rbx
0x18001546b  push    rsi
0x18001546c  push    rdi
0x18001546d  push    r12
0x18001546f  push    r13
0x180015471  push    r14
0x180015473  push    r15
0x180015475  lea     rbp, [rsp-2A8h]
0x18001547d  sub     rsp, 3A8h
0x180015484  mov     rax, cs:__security_cookie
0x18001548b  xor     rax, rsp
0x18001548e  mov     [rbp+2E0h+var_50], rax
0x180015495  mov     r14, r9
0x180015498  mov     [rbp+2E0h+var_2E0], r9
0x18001549c  mov     [rsp+3E0h+var_368], r8
0x1800154a1  mov     rbx, rdx
0x1800154a4  mov     rsi, rcx
0x1800154a7  mov     [rbp+2E0h+var_360], rcx
0x1800154ab  xor     r15d, r15d
0x1800154ae  mov     [rsp+3E0h+var_380], r15d
0x1800154b3  mov     [rbp+2E0h+var_320], r15
0x1800154b7  mov     [rsp+3E0h+var_378], r15
0x1800154bc  mov     [rsp+3E0h+var_37C], r15d
0x1800154c1  mov     [rbp+2E0h+var_2F8], r15
0x1800154c5  mov     [rbp+2E0h+var_2E8], r15
0x1800154c9  mov     [rbp+2E0h+var_2F0], r15
0x1800154cd  xor     edx, edx; Val
0x1800154cf  lea     r8d, [r15+48h]; Size
0x1800154d3  lea     rcx, [rbp+2E0h+var_2B0]; void *
0x1800154d7  call    memset_0
0x1800154dc  mov     qword ptr [rbp+2E0h+Luid.LowPart], r15
0x1800154e0  xor     edx, edx; Val
0x1800154e2  mov     r8d, 208h; Size
0x1800154e8  lea     rcx, [rbp+2E0h+var_260]; void *
0x1800154ef  call    memset_0
0x1800154f4  mov     rax, [rsi]
0x1800154f7  mov     rcx, rsi
0x1800154fa  mov     rax, [rax+8]
0x1800154fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015503  mov     rdi, rax
0x180015506  mov     [rsp+3E0h+var_370], rax
0x18001550b  mov     rcx, [rsi]
0x18001550e  mov     rax, [rcx+18h]
0x180015512  mov     rcx, rsi
0x180015515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001551a  mov     rsi, rax
0x18001551d  mov     rcx, [rdi]
0x180015520  mov     rax, [rcx+18h]
0x180015524  mov     rcx, rdi
0x180015527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001552c  mov     r13, rax
0x18001552f  mov     rcx, [rdi]
0x180015532  mov     rax, [rcx+30h]
0x180015536  mov     rcx, rdi
0x180015539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001553e  mov     r12, rax
0x180015541  mov     [rbp+2E0h+var_340], r15
0x180015545  mov     [rbp+2E0h+var_330], rsi
0x180015549  mov     [rbp+2E0h+var_338], r15
0x18001554d  mov     [rbp+2E0h+var_300], rdi
0x180015551  lea     rdx, aLogonidentity; "LogonIdentity"
0x180015558  mov     [rbp+2E0h+var_2D8], rdx
0x18001555c  lea     rax, [rsp+3E0h+var_380]
0x180015561  mov     [rbp+2E0h+var_2D0], rax
0x180015565  mov     [rbp+2E0h+var_2C8], r15
0x180015569  mov     [rbp+2E0h+var_2C0], r15
0x18001556d  xor     r9d, r9d; unsigned int
0x180015570  mov     r8d, 4EBh; char *
0x180015576  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001557d  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180015582  nop
0x180015583  test    rbx, rbx
0x180015586  jz      loc_180015C77
0x18001558c  cmp     [rbx], r15
0x18001558f  jz      loc_180015C77
0x180015595  test    r14, r14
0x180015598  jz      loc_180015C77
0x18001559e  mov     [r14], r15
0x1800155a1  lea     r8, [rbp+2E0h+var_2F8]; unsigned __int16 **
0x1800155a5  mov     rdx, [rbx]; unsigned __int16 *
0x1800155a8  mov     rcx, r13; struct IWinApiLite *
0x1800155ab  call    ?GetSID@CWLIDCCHelper@@SAJPEAVIWinApiLite@@PEBGPEAPEAG@Z; CWLIDCCHelper::GetSID(IWinApiLite *,ushort const *,ushort * *)
0x1800155b0  test    eax, eax
0x1800155b2  jns     short loc_1800155FB
0x1800155b4  mov     dword ptr [rsp+3E0h+var_3C0], eax
0x1800155b8  lea     r9, aFailedToRetrie; "Failed to retrieve the requested user's"...
0x1800155bf  mov     r8d, 4FEh; unsigned int
0x1800155c5  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800155cc  lea     ecx, [r15+2]; unsigned __int8
0x1800155d0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800155d5  mov     [rbp+2E0h+var_318], r15
0x1800155d9  mov     [rbp+2E0h+var_308], r15
0x1800155dd  mov     [rbp+2E0h+var_310], r15
0x1800155e1  mov     edi, r15d
0x1800155e4  mov     [rbp+2E0h+var_2F8], r15
0x1800155e8  mov     [rbp+2E0h+var_2F0], r15
0x1800155ec  mov     [rbp+2E0h+var_2E8], r15
0x1800155f0  lea     rcx, [rbp+2E0h+var_318]
0x1800155f4  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800155f9  jmp     short loc_1800155FF
0x1800155fb  mov     rdi, [rbp+2E0h+var_2F8]
0x1800155ff  mov     dword ptr [rbp+2E0h+var_310], r15d
0x180015603  mov     [rbp+2E0h+var_308], r13
0x180015607  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x18001560e  mov     [rbp+2E0h+var_318], rax
0x180015612  mov     [rbp+2E0h+var_358], r15
0x180015616  mov     [rbp+2E0h+var_348], r15
0x18001561a  mov     [rbp+2E0h+var_350], r15
0x18001561e  lea     rcx, [rbp+2E0h+var_318]; this
0x180015622  call    ?LsaImpersonate@AutoLsaImpersonateClient@@QEAAJXZ; AutoLsaImpersonateClient::LsaImpersonate(void)
0x180015627  mov     ecx, eax; int
0x180015629  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18001562e  mov     [rsp+3E0h+var_380], eax
0x180015632  test    eax, eax
0x180015634  js      loc_180015C24
0x18001563a  mov     rax, [r12]
0x18001563e  lea     rdx, [rbp+2E0h+var_358]
0x180015642  mov     rcx, r12
0x180015645  mov     rax, [rax+20h]
0x180015649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001564e  mov     r14d, eax
0x180015651  mov     ecx, eax; int
0x180015653  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180015658  mov     [rsp+3E0h+var_380], eax
0x18001565c  test    eax, eax
0x18001565e  js      loc_180015C24
0x180015664  mov     rcx, [rbp+2E0h+var_358]
0x180015668  mov     [rsp+3E0h+var_3C0], rcx
0x18001566d  lea     r9, aCallerLocalSid; "Caller Local Sid = %ls."
0x180015674  mov     r8d, 50Fh; unsigned int
0x18001567a  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180015681  mov     ecx, 5; unsigned __int8
0x180015686  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001568b  test    rdi, rdi
0x18001568e  jz      short loc_1800156A9
0x180015690  mov     rdx, rdi
0x180015693  mov     rcx, [rbp+2E0h+var_358]
0x180015697  call    cs:__imp__o__wcsicmp
0x18001569d  test    eax, eax
0x18001569f  jz      short loc_1800156A9
0x1800156a1  mov     r15d, 1
0x1800156a7  jmp     short loc_1800156D4
0x1800156a9  mov     rax, [rsi]
0x1800156ac  lea     rcx, [rbp+2E0h+var_340]
0x1800156b0  mov     [rsp+3E0h+var_3C0], rcx
0x1800156b5  mov     r9d, 830000h
0x1800156bb  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x1800156c2  mov     rdx, [rbx]
0x1800156c5  mov     rcx, rsi
0x1800156c8  mov     rax, [rax+30h]
0x1800156cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156d1  mov     r14d, eax
0x1800156d4  lea     rcx, [rbp+2E0h+var_358]
0x1800156d8  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800156dd  nop
0x1800156de  lea     rcx, [rbp+2E0h+var_318]; this
0x1800156e2  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x1800156e7  test    r15d, r15d
0x1800156ea  jz      loc_180015787
0x1800156f0  lea     rcx, [rbp+2E0h+Luid]; Luid
0x1800156f4  call    cs:__imp_AllocateLocallyUniqueId
0x1800156fa  xor     r14d, r14d
0x1800156fd  test    eax, eax
0x1800156ff  jnz     short loc_180015752
0x180015701  call    cs:__imp_GetLastError
0x180015707  test    eax, eax
0x180015709  jg      short loc_180015713
0x18001570b  call    cs:__imp_GetLastError
0x180015711  jmp     short loc_180015721
0x180015713  call    cs:__imp_GetLastError
0x180015719  movzx   eax, ax
0x18001571c  or      eax, 0C0070000h
0x180015721  mov     [rsp+3E0h+var_380], eax
0x180015725  mov     dword ptr [rsp+3E0h+var_3C0], eax
0x180015729  lea     r9, aFailedToAlloca; "Failed to allocate locally unique ID, s"...
0x180015730  mov     r8d, 525h; unsigned int
0x180015736  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18001573d  mov     ecx, 2; unsigned __int8
0x180015742  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180015747  cmp     [rsp+3E0h+var_380], r14d
0x18001574c  jl      loc_180015C40
0x180015752  mov     rax, [rsi]
0x180015755  lea     rcx, [rbp+2E0h+var_340]
0x180015759  mov     [rsp+3E0h+var_3B0], rcx
0x18001575e  mov     [rsp+3E0h+var_3B8], 0C30000h
0x180015767  mov     ecx, [rbp+2E0h+Luid.HighPart]
0x18001576a  mov     dword ptr [rsp+3E0h+var_3C0], ecx
0x18001576e  mov     r9d, [rbp+2E0h+Luid.LowPart]
0x180015772  mov     r8, rdi
0x180015775  mov     rdx, [rbx]
0x180015778  mov     rcx, rsi
0x18001577b  mov     rax, [rax+38h]
0x18001577f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015784  mov     r14d, eax
0x180015787  mov     ecx, r14d; int
0x18001578a  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18001578f  mov     [rsp+3E0h+var_380], eax
0x180015793  xor     ecx, ecx
0x180015795  test    eax, eax
0x180015797  js      loc_180015C34
0x18001579d  cmp     dword ptr [rbx+18h], 3
0x1800157a1  jnz     short loc_1800157B1
0x1800157a3  mov     r14d, 2002200h
0x1800157a9  xor     r15d, r15d
0x1800157ac  jmp     loc_1800158E3
0x1800157b1  mov     dword ptr [rbp+2E0h+var_350], ecx
0x1800157b4  mov     [rbp+2E0h+var_348], r13
0x1800157b8  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x1800157bf  mov     [rbp+2E0h+var_358], rax
0x1800157c3  test    r15d, r15d
0x1800157c6  jnz     short loc_1800157E9
0x1800157c8  lea     rcx, [rbp+2E0h+var_358]; this
0x1800157cc  call    ?LsaImpersonate@AutoLsaImpersonateClient@@QEAAJXZ; AutoLsaImpersonateClient::LsaImpersonate(void)
0x1800157d1  mov     ecx, eax; int
0x1800157d3  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800157d8  mov     [rsp+3E0h+var_380], eax
0x1800157dc  xor     r15d, r15d
0x1800157df  test    eax, eax
0x1800157e1  js      loc_180015C19
0x1800157e7  jmp     short loc_1800157EC
0x1800157e9  xor     r15d, r15d
0x1800157ec  mov     eax, [rbx+18h]
0x1800157ef  cmp     eax, 2
0x1800157f2  jnz     short loc_18001581A
0x1800157f4  lea     rax, [rsp+3E0h+var_37C]
0x1800157f9  mov     [rsp+3E0h+var_3C0], rax; unsigned int *
0x1800157fe  lea     r9, [rsp+3E0h+var_378]; unsigned __int8 **
0x180015803  mov     r8, [rbx+98h]; unsigned __int16 *
0x18001580a  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18001580e  mov     rcx, [rsp+3E0h+var_370]; struct IExecutionContextLite *
0x180015813  call    ?SerializeNgcKeyNameAndAuthTicket@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAEPEAK@Z; CredSerializationHelper::SerializeNgcKeyNameAndAuthTicket(IExecutionContextLite *,ushort const *,ushort const *,uchar * *,ulong *)
0x180015818  jmp     short loc_18001586E
0x18001581a  cmp     eax, 1
0x18001581d  jnz     loc_180015BEF
0x180015823  mov     r9, [rbx+20h]
0x180015827  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001582b  inc     rax
0x18001582e  cmp     [r9+rax*2], r15w
0x180015833  jnz     short loc_18001582B
0x180015835  lea     rcx, [rsp+3E0h+var_37C]
0x18001583a  mov     [rsp+3E0h+var_390], rcx
0x18001583f  lea     rcx, [rsp+3E0h+var_378]
0x180015844  mov     [rsp+3E0h+var_398], rcx
0x180015849  mov     [rsp+3E0h+var_3A8], r15d
0x18001584e  mov     [rsp+3E0h+var_3B0], r15
0x180015853  mov     dword ptr [rsp+3E0h+var_3B8], r15d
0x180015858  mov     dword ptr [rsp+3E0h+var_3C0], eax
0x18001585c  mov     edx, 1
0x180015861  mov     r8d, edx
0x180015864  mov     rcx, [rsp+3E0h+var_370]
0x180015869  call    ?SerializeCredentials@CredSerializationHelper@@SAJPEAVIExecutionContextLite@@W4_WLIDCredentialsType@@W4_WLIDCredentialAttribute@@PEBGK23K_NPEAPEAEPEAK@Z; CredSerializationHelper::SerializeCredentials(IExecutionContextLite *,_WLIDCredentialsType,_WLIDCredentialAttribute,ushort const *,ulong,_WLIDCredentialAttribute,ushort const *,ulong,bool,uchar * *,ulong *)
0x18001586e  mov     r14d, eax
0x180015871  lea     rcx, [rbp+2E0h+var_320]
0x180015875  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18001587a  mov     r15, [rsp+3E0h+var_378]
0x18001587f  mov     [rbp+2E0h+var_320], r15
0x180015883  mov     ecx, r14d; int
0x180015886  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x18001588b  mov     [rsp+3E0h+var_380], eax
0x18001588f  test    eax, eax
0x180015891  js      loc_180015BEA
0x180015897  mov     rax, [rsi]
0x18001589a  mov     [rsp+3E0h+var_3C0], r15
0x18001589f  mov     r9d, [rsp+3E0h+var_37C]
0x1800158a4  xor     r8d, r8d
0x1800158a7  mov     rdx, [rbp+2E0h+var_340]
0x1800158ab  mov     rcx, rsi
0x1800158ae  mov     rax, [rax+0B0h]
0x1800158b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ba  mov     ecx, eax; int
0x1800158bc  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800158c1  mov     [rsp+3E0h+var_380], eax
0x1800158c5  xor     r15d, r15d
0x1800158c8  test    eax, eax
0x1800158ca  js      loc_180015C19
0x1800158d0  mov     r14, 200000000h
0x1800158da  lea     rcx, [rbp+2E0h+var_358]; this
0x1800158de  call    ??1AutoImpersonateClient@@UEAA@XZ; AutoImpersonateClient::~AutoImpersonateClient(void)
0x1800158e3  mov     rax, [rbx+38h]
0x1800158e7  test    rax, rax
0x1800158ea  jz      short loc_180015950
0x1800158ec  lea     rcx, aHttpPassportNe; "http://Passport.NET/tb"
0x1800158f3  mov     [rbp+2E0h+var_2A0], rcx
0x1800158f7  mov     [rbp+2E0h+var_2A8], r15d
0x1800158fb  mov     [rbp+2E0h+var_298], rax
0x1800158ff  mov     rax, [rbx+68h]
0x180015903  mov     [rbp+2E0h+var_270], rax
0x180015907  mov     rax, [rbx+50h]
0x18001590b  mov     [rbp+2E0h+var_278], rax
0x18001590f  mov     rax, [rbx+80h]
0x180015916  mov     [rbp+2E0h+var_288], rax
0x18001591a  mov     [rbp+2E0h+var_280], 1
0x180015921  mov     eax, [rbx+0B0h]
0x180015927  mov     [rbp+2E0h+var_290], eax
0x18001592a  mov     rax, [rsi]
0x18001592d  xor     r9d, r9d
0x180015930  lea     r8, [rbp+2E0h+var_2B0]
0x180015934  mov     rdx, [rbp+2E0h+var_340]
0x180015938  mov     rcx, rsi
  ... truncated ...
```
