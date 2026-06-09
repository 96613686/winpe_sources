# HandleUserProfileLoaded(ICloudAPContext *,void *,void *,_AP_BLOB *,int)

- ea: `0x18001495c`
- end: `0x180014fe8`
- name: `?HandleUserProfileLoaded@@YAJPEAVICloudAPContext@@PEAX1PEAU_AP_BLOB@@H@Z`
- size: `1676`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, void *, struct _AP_BLOB *, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000a020`

## callees

- `0x1800011fc`
- `0x180001744`
- `0x180001900`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000d980`
- `0x18000e0f0`
- `0x18000fa74`
- `0x18000fb34`
- `0x180010064`
- `0x1800112f0`
- `0x180012130`
- `0x1800121b4`
- `0x18001495c`
- `0x180015338`
- `0x180017d88`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c07`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014caa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c07`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c95`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014caa`

## string_xrefs

- `0x180014a61`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014ae4`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014b33`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014b6d`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014bcf`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014d26`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014ddf`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180014dd2`: `WLIDCUpdateConnectedIdentity failed with error 0x%x`
- `0x180014ad7`: `ImpersonateLoggedOnUser failed, error = 0x%x`
- `0x180014b26`: `Unable to query user's SID with error 0x%x`
- `0x180014b60`: `Local Sid = %ls.`
- `0x180014c8a`: `DefaultCredsUpdateRequired`
- `0x180014d19`: `WLIDCCreateContextEx failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall HandleUserProfileLoaded(struct ICloudAPContext *a1, void *a2, void *a3, struct _AP_BLOB *a4, int a5)
{
  int v7; // r13d
  unsigned int v8; // esi
  struct MSACloudAPValidationInfo *v9; // r14
  __int64 v10; // r12
  void *v11; // rdi
  __int64 v12; // rbx
  HANDLE v13; // rax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // r15d
  unsigned int v21; // r15d
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  BOOL v26; // edi
  __int64 v27; // rcx
  __int64 v28; // r9
  int v29; // eax
  unsigned int v30; // ebx
  const unsigned __int16 *v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+20h] [rbp-E0h]
  __int64 v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v39; // [rsp+88h] [rbp-78h] BYREF
  struct IExecutionContextLite *v40; // [rsp+90h] [rbp-70h] BYREF
  const unsigned __int16 *v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v43[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v44[3]; // [rsp+C0h] [rbp-40h] BYREF
  void *v45[3]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v46; // [rsp+F0h] [rbp-10h] BYREF
  const unsigned __int16 *v47; // [rsp+F8h] [rbp-8h] BYREF
  const unsigned __int16 *v48; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int16 *v49; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v50[3]; // [rsp+110h] [rbp+10h] BYREF
  struct MSACloudAPValidationInfo *v51[3]; // [rsp+128h] [rbp+28h] BYREF
  void **v52; // [rsp+140h] [rbp+40h] BYREF
  int v53; // [rsp+148h] [rbp+48h]
  __int64 v54; // [rsp+150h] [rbp+50h]
  _QWORD v55[11]; // [rsp+158h] [rbp+58h] BYREF
  int updated; // [rsp+1C0h] [rbp+C0h] BYREF
  void *v57; // [rsp+1C8h] [rbp+C8h] BYREF
  HANDLE TokenHandle; // [rsp+1D0h] [rbp+D0h] BYREF

  TokenHandle = a3;
  v57 = a2;
  LOBYTE(v7) = 0;
  updated = 0;
  v8 = 0;
  v9 = 0;
  memset(v51, 0, sizeof(v51));
  memset(v44, 0, sizeof(v44));
  memset(v43, 0, sizeof(v43));
  memset(v50, 0, sizeof(v50));
  v40 = (struct IExecutionContextLite *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 8LL))(a1);
  v12 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)v40 + 24LL))(v40);
  v10 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)v40 + 48LL))(v40);
  v11 = (void *)(*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v52 = &AutoImpersonateClient::`vftable';
  v53 = 0;
  v54 = v12;
  v45[0] = 0;
  v45[2] = v11;
  v45[1] = 0;
  LOBYTE(v57) = 0;
  LOBYTE(v12) = 0;
  v55[0] = "HandleUserProfileLoaded";
  v55[1] = &updated;
  v55[2] = 0;
  v55[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleUserProfileLoaded",
    (const char *)0x2A9,
    0,
    v32);
  v13 = TokenHandle;
  if ( !TokenHandle || !a4 || !*((_QWORD *)a4 + 1) || *(_DWORD *)a4 <= 0x38u )
  {
    updated = -1073741811;
LABEL_38:
    if ( !IsWinLogon(v13) )
      goto LABEL_47;
    goto LABEL_39;
  }
  updated = DeserializeOpaqueBlob(a4, v51);
  v9 = v51[0];
  if ( updated >= 0 )
  {
    v14 = AutoImpersonateClient::Impersonate((AutoImpersonateClient *)&v52, TokenHandle);
    v8 = v14;
    if ( v14 >= 0
      || (LODWORD(v33) = v14,
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
            0x2BFu,
            L"ImpersonateLoggedOnUser failed, error = 0x%x",
            v33),
          updated = LiveMapHResultToNtStatus(v8),
          updated >= 0) )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 32LL))(v10, v44);
      v8 = v15;
      if ( v15 >= 0
        || (LODWORD(v33) = v15,
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
              0x2C6u,
              L"Unable to query user's SID with error 0x%x",
              v33),
            updated = LiveMapHResultToNtStatus(v8),
            updated >= 0) )
      {
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x2CAu,
          L"Local Sid = %ls.",
          v44[0]);
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD *, _QWORD))(*(_QWORD *)v10 + 24LL))(
                v10,
                v44[0],
                L"DefaultCredSaved",
                v43,
                0);
        v8 = v16;
        if ( v16 == -2147023728 )
        {
          v8 = 0;
          v7 = 1;
        }
        else
        {
          v7 = 0;
          if ( v16 < 0 )
          {
            LODWORD(v34) = v16;
            TracePrintW(
              2u,
              "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
              0x2DBu,
              L"Unable to query user's PPCRL_CREDPROPERTY_DEFAULTCREDSAVED value with error 0x%x",
              v34);
            updated = LiveMapHResultToNtStatus(v8);
            if ( updated < 0 )
              goto LABEL_33;
          }
        }
        if ( !v43[0] || !(unsigned int)_o__wcsicmp(v43[0], &qword_18003AB48) )
          goto LABEL_25;
        if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
        {
          v42 = 50331648;
          v41 = (const unsigned __int16 *)v43[0];
          v20 = a5;
          v37 = a5;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v17,
            (__int64)byte_1800442D9,
            v18,
            v19,
            (__int64)&v37,
            &v41,
            (__int64)&v42);
        }
        else
        {
          v20 = a5;
        }
        if ( !v20 && (unsigned int)_o__wcsicmp(v43[0], L"DefaultCredsUpdateRequired")
          || !(unsigned int)_o__wcsicmp(v43[0], L"Persisted") )
        {
          updated = 0;
        }
        else
        {
LABEL_25:
          LOBYTE(v57) = 1;
          v21 = v7 | 2;
          if ( !a5 )
            v21 = v7;
          v22 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, const wchar_t *, __int64, void **))(*(_QWORD *)v11 + 48LL))(
                  v11,
                  &qword_18003AB48,
                  L"{ba1e4578-b17c-48b0-986e-2178f2da7eef}",
                  0x800000,
                  v45);
          v8 = v22;
          if ( v22 >= 0
            || (LODWORD(v35) = v22,
                TracePrintW(
                  2u,
                  "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
                  0x308u,
                  L"WLIDCCreateContextEx failed with error 0x%x",
                  v35),
                updated = LiveMapHResultToNtStatus(v8),
                updated >= 0) )
          {
            updated = UpdateTokenFromValidationInfo((struct ILiveIdNtService *)v11, v45[0], v9);
            if ( updated >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(void *, void *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)v11 + 200LL))(
                     v11,
                     v45[0],
                     L"ps:password",
                     0,
                     0);
              LODWORD(v12) = v8 >> 31;
              updated = LiveMapHResultToNtStatus(v8);
              if ( updated >= 0 )
              {
                v23 = (*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, v45[0], v21);
                v8 = v23;
                if ( v23 < 0 )
                {
                  LODWORD(v36) = v23;
                  TracePrintW(
                    2u,
                    "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
                    0x324u,
                    L"WLIDCUpdateConnectedIdentity failed with error 0x%x",
                    v36);
                  updated = LiveMapHResultToNtStatus(v8);
                }
              }
            }
          }
        }
        LOBYTE(v7) = (_BYTE)v57;
      }
    }
  }
LABEL_33:
  if ( v9 )
    FamilyNotifications::NotifyIfAccountIsFamilyRelated(v40, *((const unsigned __int16 **)v9 + 28));
  if ( !(_BYTE)v7 )
  {
    v13 = TokenHandle;
    goto LABEL_38;
  }
LABEL_39:
  v26 = IsInternetPresent();
  if ( (_BYTE)v7 )
    (*(void (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD *, _QWORD))(*(_QWORD *)v10 + 24LL))(
      v10,
      v44[0],
      L"DefaultCredSaved",
      v50,
      0);
  v24 = (unsigned int)dword_18004D048;
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    v46 = 50331648;
    v47 = (const unsigned __int16 *)v44[0];
    if ( v9 )
      v29 = *((_DWORD *)v9 + 1);
    else
      v29 = 0;
    LODWORD(TokenHandle) = v29;
    v48 = (const unsigned __int16 *)v50[0];
    v49 = (const unsigned __int16 *)v43[0];
    LODWORD(v57) = (unsigned __int8)v12;
    v37 = updated;
    v38 = v28;
    v39 = v8;
    LODWORD(v40) = a5;
    LODWORD(v41) = (unsigned __int8)v7;
    LODWORD(v42) = v26;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v27,
      (__int64)byte_1800441DB,
      v25,
      v28,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v57,
      &v49,
      &v48,
      (__int64)&TokenHandle,
      &v47,
      (__int64)&v46);
  }
LABEL_47:
  v30 = updated;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v55, v24, v25);
  Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>((__int64 *)v45);
  AutoImpersonateClient::~AutoImpersonateClient((AutoImpersonateClient *)&v52);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v50);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v43);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v44);
  Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>::~Auto<MSACloudAPValidationInfo *,ValidationInfoFunctor,DummyContext>((__int64)v51);
  return v30;
}

```

## disassembly

```asm
0x18001495c  mov     [rsp-8+arg_18], rbx
0x180014961  mov     [rsp-8+TokenHandle], r8
0x180014966  mov     [rsp-8+arg_8], rdx
0x18001496b  push    rbp
0x18001496c  push    rsi
0x18001496d  push    rdi
0x18001496e  push    r12
0x180014970  push    r13
0x180014972  push    r14
0x180014974  push    r15
0x180014976  lea     rbp, [rsp-80h]
0x18001497b  sub     rsp, 180h
0x180014982  mov     r15, r9
0x180014985  mov     rdi, rcx
0x180014988  xor     r13d, r13d
0x18001498b  mov     [rbp+0B0h+arg_0], r13d
0x180014992  mov     esi, r13d
0x180014995  mov     r14d, r13d
0x180014998  mov     [rbp+0B0h+var_88], r13
0x18001499c  mov     [rbp+0B0h+var_78], r13
0x1800149a0  mov     [rbp+0B0h+var_80], r13
0x1800149a4  mov     [rbp+0B0h+var_F0], r13
0x1800149a8  mov     [rbp+0B0h+var_E0], r13
0x1800149ac  mov     [rbp+0B0h+var_E8], r13
0x1800149b0  mov     [rbp+0B0h+var_108], r13
0x1800149b4  mov     [rbp+0B0h+var_F8], r13
0x1800149b8  mov     [rbp+0B0h+var_100], r13
0x1800149bc  mov     [rbp+0B0h+var_A0], r13
0x1800149c0  mov     [rbp+0B0h+var_90], r13
0x1800149c4  mov     [rbp+0B0h+var_98], r13
0x1800149c8  mov     rax, [rcx]
0x1800149cb  mov     rax, [rax+8]
0x1800149cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149d4  mov     r12, rax
0x1800149d7  mov     [rbp+0B0h+var_120], rax
0x1800149db  mov     rax, [rax]
0x1800149de  mov     rcx, r12
0x1800149e1  mov     rax, [rax+18h]
0x1800149e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ea  mov     rbx, rax
0x1800149ed  mov     rax, [r12]
0x1800149f1  mov     rcx, r12
0x1800149f4  mov     rax, [rax+30h]
0x1800149f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fd  mov     r12, rax
0x180014a00  mov     rax, [rdi]
0x180014a03  mov     rcx, rdi
0x180014a06  mov     rax, [rax+18h]
0x180014a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a0f  mov     rdi, rax
0x180014a12  lea     rax, ??_7AutoImpersonateClient@@6B@; const AutoImpersonateClient::`vftable'
0x180014a19  mov     [rbp+0B0h+var_70], rax
0x180014a1d  mov     [rbp+0B0h+var_68], r13d
0x180014a21  mov     [rbp+0B0h+var_60], rbx
0x180014a25  mov     [rbp+0B0h+var_D8], r13
0x180014a29  mov     [rbp+0B0h+var_C8], rdi
0x180014a2d  mov     [rbp+0B0h+var_D0], r13
0x180014a31  mov     byte ptr [rbp+0B0h+arg_8], r13b
0x180014a38  xor     bl, bl
0x180014a3a  lea     rdx, aHandleuserprof; "HandleUserProfileLoaded"
0x180014a41  mov     [rbp+0B0h+var_58], rdx
0x180014a45  lea     rax, [rbp+0B0h+arg_0]
0x180014a4c  mov     [rbp+0B0h+var_50], rax
0x180014a50  mov     [rbp+0B0h+var_48], r13
0x180014a54  mov     [rbp+0B0h+var_40], r13
0x180014a58  xor     r9d, r9d; unsigned int
0x180014a5b  mov     r8d, 2A9h; char *
0x180014a61  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014a68  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180014a6d  nop
0x180014a6e  mov     rax, [rbp+0B0h+TokenHandle]
0x180014a75  test    rax, rax
0x180014a78  jz      loc_180014E25
0x180014a7e  test    r15, r15
0x180014a81  jz      loc_180014E25
0x180014a87  cmp     [r15+8], r13
0x180014a8b  jz      loc_180014E25
0x180014a91  cmp     dword ptr [r15], 38h ; '8'
0x180014a95  jbe     loc_180014E25
0x180014a9b  lea     rdx, [rbp+0B0h+var_88]; struct MSACloudAPValidationInfo **
0x180014a9f  mov     rcx, r15; struct _AP_BLOB *
0x180014aa2  call    ?DeserializeOpaqueBlob@@YAJPEAU_AP_BLOB@@PEAPEAUMSACloudAPValidationInfo@@@Z; DeserializeOpaqueBlob(_AP_BLOB *,MSACloudAPValidationInfo * *)
0x180014aa7  mov     [rbp+0B0h+arg_0], eax
0x180014aad  mov     r14, [rbp+0B0h+var_88]
0x180014ab1  test    eax, eax
0x180014ab3  js      loc_180014E02
0x180014ab9  mov     rdx, [rbp+0B0h+TokenHandle]; void *
0x180014ac0  lea     rcx, [rbp+0B0h+var_70]; this
0x180014ac4  call    ?Impersonate@AutoImpersonateClient@@QEAAJPEAX@Z; AutoImpersonateClient::Impersonate(void *)
0x180014ac9  mov     esi, eax
0x180014acb  lea     r15d, [r13+2]
0x180014acf  test    eax, eax
0x180014ad1  jns     short loc_180014B08
0x180014ad3  mov     dword ptr [rsp+1B0h+var_190], eax
0x180014ad7  lea     r9, aImpersonatelog; "ImpersonateLoggedOnUser failed, error ="...
0x180014ade  mov     r8d, 2BFh; unsigned int
0x180014ae4  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014aeb  mov     ecx, r15d; unsigned __int8
0x180014aee  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014af3  mov     ecx, esi; int
0x180014af5  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014afa  mov     [rbp+0B0h+arg_0], eax
0x180014b00  test    eax, eax
0x180014b02  js      loc_180014E02
0x180014b08  mov     rax, [r12]
0x180014b0c  lea     rdx, [rbp+0B0h+var_F0]
0x180014b10  mov     rcx, r12
0x180014b13  mov     rax, [rax+20h]
0x180014b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b1c  mov     esi, eax
0x180014b1e  test    eax, eax
0x180014b20  jns     short loc_180014B57
0x180014b22  mov     dword ptr [rsp+1B0h+var_190], eax
0x180014b26  lea     r9, aUnableToQueryU; "Unable to query user's SID with error 0"...
0x180014b2d  mov     r8d, 2C6h; unsigned int
0x180014b33  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014b3a  mov     ecx, r15d; unsigned __int8
0x180014b3d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014b42  mov     ecx, esi; int
0x180014b44  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014b49  mov     [rbp+0B0h+arg_0], eax
0x180014b4f  test    eax, eax
0x180014b51  js      loc_180014E02
0x180014b57  mov     rax, [rbp+0B0h+var_F0]
0x180014b5b  mov     [rsp+1B0h+var_190], rax
0x180014b60  lea     r9, aLocalSidLs; "Local Sid = %ls."
0x180014b67  mov     r8d, 2CAh; unsigned int
0x180014b6d  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014b74  mov     ecx, 5; unsigned __int8
0x180014b79  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014b7e  mov     rax, [r12]
0x180014b82  mov     [rsp+1B0h+var_190], 0
0x180014b8b  lea     r9, [rbp+0B0h+var_108]
0x180014b8f  lea     r8, aDefaultcredsav; "DefaultCredSaved"
0x180014b96  mov     rdx, [rbp+0B0h+var_F0]
0x180014b9a  mov     rcx, r12
0x180014b9d  mov     rax, [rax+18h]
0x180014ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ba6  mov     esi, eax
0x180014ba8  cmp     eax, 80070490h
0x180014bad  jnz     short loc_180014BB7
0x180014baf  xor     esi, esi
0x180014bb1  lea     r13d, [rsi+1]
0x180014bb5  jmp     short loc_180014BF3
0x180014bb7  xor     r13d, r13d
0x180014bba  test    esi, esi
0x180014bbc  jns     short loc_180014BF3
0x180014bbe  mov     dword ptr [rsp+1B0h+var_190], esi
0x180014bc2  lea     r9, aUnableToQueryU_0; "Unable to query user's PPCRL_CREDPROPER"...
0x180014bc9  mov     r8d, 2DBh; unsigned int
0x180014bcf  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014bd6  mov     ecx, r15d; unsigned __int8
0x180014bd9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014bde  mov     ecx, esi; int
0x180014be0  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014be5  mov     [rbp+0B0h+arg_0], eax
0x180014beb  test    eax, eax
0x180014bed  js      loc_180014E02
0x180014bf3  mov     rcx, [rbp+0B0h+var_108]
0x180014bf7  test    rcx, rcx
0x180014bfa  jz      loc_180014CCA
0x180014c00  lea     rdx, qword_18003AB48
0x180014c07  call    cs:__imp__o__wcsicmp
0x180014c0d  test    eax, eax
0x180014c0f  jz      loc_180014CCA
0x180014c15  mov     eax, cs:dword_18004D048
0x180014c1b  cmp     eax, 5
0x180014c1e  jbe     short loc_180014C7E
0x180014c20  mov     rdx, 400000000000h
0x180014c2a  lea     rcx, dword_18004D048
0x180014c31  call    _tlgKeywordOn
0x180014c36  test    al, al
0x180014c38  jz      short loc_180014C7E
0x180014c3a  mov     [rbp+0B0h+var_110], 3000000h
0x180014c42  mov     rax, [rbp+0B0h+var_108]
0x180014c46  mov     [rbp+0B0h+var_118], rax
0x180014c4a  mov     r15d, [rbp+0B0h+arg_20]
0x180014c51  mov     [rbp+0B0h+var_130], r15d
0x180014c55  lea     rax, [rbp+0B0h+var_110]
0x180014c59  mov     [rsp+1B0h+var_180], rax
0x180014c5e  lea     rax, [rbp+0B0h+var_118]
0x180014c62  mov     [rsp+1B0h+var_188], rax
0x180014c67  lea     rax, [rbp+0B0h+var_130]
0x180014c6b  mov     [rsp+1B0h+var_190], rax
0x180014c70  lea     rdx, byte_1800442D9
0x180014c77  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x180014c7c  jmp     short loc_180014C85
0x180014c7e  mov     r15d, [rbp+0B0h+arg_20]
0x180014c85  test    r15d, r15d
0x180014c88  jnz     short loc_180014C9F
0x180014c8a  lea     rdx, aDefaultcredsup; "DefaultCredsUpdateRequired"
0x180014c91  mov     rcx, [rbp+0B0h+var_108]
0x180014c95  call    cs:__imp__o__wcsicmp
0x180014c9b  test    eax, eax
0x180014c9d  jnz     short loc_180014CB4
0x180014c9f  lea     rdx, aPersisted; "Persisted"
0x180014ca6  mov     rcx, [rbp+0B0h+var_108]
0x180014caa  call    cs:__imp__o__wcsicmp
0x180014cb0  test    eax, eax
0x180014cb2  jnz     short loc_180014CCA
0x180014cb4  mov     [rbp+0B0h+arg_0], 0
0x180014cbe  mov     r13b, byte ptr [rbp+0B0h+arg_8]
0x180014cc5  jmp     loc_180014E02
0x180014cca  mov     byte ptr [rbp+0B0h+arg_8], 1
0x180014cd1  mov     r15d, r13d
0x180014cd4  or      r15d, 2
0x180014cd8  cmp     [rbp+0B0h+arg_20], 0
0x180014cdf  cmovz   r15d, r13d
0x180014ce3  mov     rax, [rdi]
0x180014ce6  lea     rcx, [rbp+0B0h+var_D8]
0x180014cea  mov     [rsp+1B0h+var_190], rcx
0x180014cef  mov     r9d, 800000h
0x180014cf5  lea     r8, aBa1e4578B17c48; "{ba1e4578-b17c-48b0-986e-2178f2da7eef}"
0x180014cfc  lea     rdx, qword_18003AB48
0x180014d03  mov     rcx, rdi
0x180014d06  mov     rax, [rax+30h]
0x180014d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d0f  mov     esi, eax
0x180014d11  test    eax, eax
0x180014d13  jns     short loc_180014D4C
0x180014d15  mov     dword ptr [rsp+1B0h+var_190], eax
0x180014d19  lea     r9, aWlidccreatecon; "WLIDCCreateContextEx failed with error "...
0x180014d20  mov     r8d, 308h; unsigned int
0x180014d26  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014d2d  mov     ecx, 2; unsigned __int8
0x180014d32  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014d37  mov     ecx, esi; int
0x180014d39  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014d3e  mov     [rbp+0B0h+arg_0], eax
0x180014d44  test    eax, eax
0x180014d46  js      loc_180014CBE
0x180014d4c  mov     r8, r14; struct MSACloudAPValidationInfo *
0x180014d4f  mov     rdx, [rbp+0B0h+var_D8]; void *
0x180014d53  mov     rcx, rdi; struct ILiveIdNtService *
0x180014d56  call    ?UpdateTokenFromValidationInfo@@YAJPEAVILiveIdNtService@@PEAXPEAUMSACloudAPValidationInfo@@@Z; UpdateTokenFromValidationInfo(ILiveIdNtService *,void *,MSACloudAPValidationInfo *)
0x180014d5b  mov     [rbp+0B0h+arg_0], eax
0x180014d61  test    eax, eax
0x180014d63  js      loc_180014CBE
0x180014d69  mov     rax, [rdi]
0x180014d6c  mov     [rsp+1B0h+var_190], 0
0x180014d75  xor     r9d, r9d
0x180014d78  lea     r8, aPsPassword; "ps:password"
0x180014d7f  mov     rdx, [rbp+0B0h+var_D8]
0x180014d83  mov     rcx, rdi
0x180014d86  mov     rax, [rax+0C8h]
0x180014d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d92  mov     esi, eax
0x180014d94  mov     ebx, eax
0x180014d96  shr     ebx, 1Fh
0x180014d99  mov     ecx, eax; int
0x180014d9b  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014da0  mov     [rbp+0B0h+arg_0], eax
0x180014da6  test    eax, eax
0x180014da8  js      loc_180014CBE
0x180014dae  mov     rax, [rdi]
0x180014db1  mov     r8d, r15d
0x180014db4  mov     rdx, [rbp+0B0h+var_D8]
0x180014db8  mov     rcx, rdi
0x180014dbb  mov     rax, [rax+48h]
0x180014dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc4  mov     esi, eax
0x180014dc6  test    eax, eax
0x180014dc8  jns     loc_180014CBE
0x180014dce  mov     dword ptr [rsp+1B0h+var_190], eax
0x180014dd2  lea     r9, aWlidcupdatecon_0; "WLIDCUpdateConnectedIdentity failed wit"...
0x180014dd9  mov     r8d, 324h; unsigned int
0x180014ddf  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180014de6  mov     ecx, 2; unsigned __int8
0x180014deb  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180014df0  mov     ecx, esi; int
0x180014df2  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x180014df7  mov     [rbp+0B0h+arg_0], eax
0x180014dfd  jmp     loc_180014CBE
0x180014e02  test    r14, r14
0x180014e05  jz      short loc_180014E17
0x180014e07  mov     rdx, [r14+0E0h]; unsigned __int16 *
0x180014e0e  mov     rcx, [rbp+0B0h+var_120]; struct IExecutionContextLite *
0x180014e12  call    ?NotifyIfAccountIsFamilyRelated@FamilyNotifications@@SAJPEAVIExecutionContextLite@@PEBG@Z; FamilyNotifications::NotifyIfAccountIsFamilyRelated(IExecutionContextLite *,ushort const *)
0x180014e17  test    r13b, r13b
0x180014e1a  jnz     short loc_180014E3F
0x180014e1c  mov     rax, [rbp+0B0h+TokenHandle]
0x180014e23  jmp     short loc_180014E2F
0x180014e25  mov     [rbp+0B0h+arg_0], 0C000000Dh
0x180014e2f  mov     rcx, rax; TokenHandle
0x180014e32  call    ?IsWinLogon@@YA_NPEAX@Z; IsWinLogon(void *)
0x180014e37  test    al, al
0x180014e39  jz      loc_180014F80
0x180014e3f  call    ?IsInternetPresent@@YA_NXZ; IsInternetPresent(void)
0x180014e44  movzx   edi, al
0x180014e47  xor     r9d, r9d
0x180014e4a  test    r13b, r13b
0x180014e4d  jz      short loc_180014E76
0x180014e4f  mov     rcx, [r12]
0x180014e53  mov     rax, [rcx+18h]
0x180014e57  mov     [rsp+1B0h+var_190], r9
0x180014e5c  lea     r9, [rbp+0B0h+var_A0]
0x180014e60  lea     r8, aDefaultcredsav; "DefaultCredSaved"
0x180014e67  mov     rdx, [rbp+0B0h+var_F0]
0x180014e6b  mov     rcx, r12
0x180014e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
