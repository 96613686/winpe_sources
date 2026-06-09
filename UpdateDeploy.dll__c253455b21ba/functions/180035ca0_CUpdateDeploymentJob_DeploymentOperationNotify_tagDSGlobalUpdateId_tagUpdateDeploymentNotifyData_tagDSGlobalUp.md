# CUpdateDeploymentJob::DeploymentOperationNotify(tagDSGlobalUpdateId,tagUpdateDeploymentNotifyData *,tagDSGlobalUpdateId *)

- ea: `0x180035ca0`
- end: `0x180036525`
- name: `?DeploymentOperationNotify@CUpdateDeploymentJob@@UEAAJUtagDSGlobalUpdateId@@PEAUtagUpdateDeploymentNotifyData@@PEAU2@@Z`
- size: `2181`
- prototype: `int __high(struct tagDSGlobalUpdateId, struct tagUpdateDeploymentNotifyData *, struct tagDSGlobalUpdateId *)`
- caller_count: `0`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x180008b30`
- `0x180008f5c`
- `0x18000c0ac`
- `0x18000cd48`
- `0x18000db84`
- `0x18000dce4`
- `0x1800110fc`
- `0x180024fd8`
- `0x1800250a8`
- `0x180028720`
- `0x180028c94`
- `0x18002a37c`
- `0x18002a584`
- `0x18002a674`
- `0x18002aa98`
- `0x180035ca0`
- `0x18003652c`
- `0x1800365c4`
- `0x180037014`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180036300`
- `RPCRT4!UuidFromStringW` at `0x180036481`
- `RPCRT4!UuidFromStringW` at `0x180036300`
- `RPCRT4!UuidFromStringW` at `0x180036481`

## string_xrefs

- `0x180035f7e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180035fe7`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180035f38`: `CUpdateDeploymentJob::DeploymentOperationNotify`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CUpdateDeploymentJob::DeploymentOperationNotify(
        __int64 a1,
        const UUID *a2,
        __int64 a3,
        const struct tagDSGlobalUpdateId *a4)
{
  int Index1ById; // ebx
  __int64 v8; // rdx
  unsigned int v9; // r15d
  __int64 v10; // r8
  __int64 v11; // r12
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, void **, __int64); // rdi
  __int64 v15; // r13
  wchar_t **v16; // rbx
  wchar_t **v17; // rdi
  __int64 v18; // rax
  void *v19; // rcx
  wchar_t **v20; // rcx
  int v21; // eax
  wchar_t **v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  int v25; // eax
  __int64 v26; // rbx
  _WORD *v27; // rcx
  _WORD *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // eax
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  __int64 v35; // rax
  int DoesCommitOperationRequireReboot; // eax
  __int64 v37; // rcx
  __int64 v38; // r9
  void *v39; // rcx
  int v40; // eax
  _WORD *v41; // rax
  __int64 v42; // r8
  __int64 v43; // r14
  void *v44; // rcx
  int v45; // eax
  __int64 v46; // r9
  int v47; // eax
  unsigned int v48; // eax
  CUpdateDeploymentJob *v49; // rcx
  int v50; // [rsp+20h] [rbp-59h]
  int v51; // [rsp+20h] [rbp-59h]
  unsigned int v52; // [rsp+40h] [rbp-39h] BYREF
  UUID v53; // [rsp+48h] [rbp-31h] BYREF
  __int64 v54; // [rsp+58h] [rbp-21h]
  unsigned int v55; // [rsp+60h] [rbp-19h] BYREF
  int v56; // [rsp+64h] [rbp-15h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-11h] BYREF
  void *lpMem; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v55 = -1;
  v52 = -1;
  lpMem = 0;
  if ( !a3 )
  {
    Index1ById = -2147467261;
    v8 = 5850;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)Index1ById,
      v50);
    goto LABEL_24;
  }
  if ( a4 )
  {
    Index1ById = CUpdateDeploymentJob::FindIndex1ById((CUpdateDeploymentJob *)(a1 - 8), a4, &v55);
    if ( Index1ById < 0 )
    {
      v8 = 5859;
      goto LABEL_43;
    }
    v9 = v55;
  }
  else
  {
    v9 = *(_DWORD *)(a1 + 664);
  }
  if ( v9 == -1 )
  {
    Index1ById = -2145120257;
    v8 = 5862;
    goto LABEL_43;
  }
  Index1ById = CUpdateDeploymentJob::FindIndex2ById((CUpdateDeploymentJob *)(a1 - 8), a2, v9, &v52);
  v10 = 0;
  if ( Index1ById < 0 )
  {
    v8 = 5864;
    goto LABEL_43;
  }
  v11 = v52;
  if ( v52 == -1 )
  {
    Index1ById = -2145120257;
    v8 = 5866;
    goto LABEL_43;
  }
  if ( *(_DWORD *)a3 != 1 )
  {
    if ( *(_DWORD *)a3 != 2 )
    {
      if ( *(_DWORD *)a3 == 3 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 536LL) & 0x20) != 0 )
        {
          v12 = *(_QWORD *)(a1 + 696);
          v13 = *(__int64 (__fastcall **)(__int64, void **, __int64))(*(_QWORD *)v12 + 128LL);
          if ( lpMem )
            SusFree(lpMem);
          Index1ById = v13(v12, &lpMem, v10);
          if ( Index1ById < 0 )
          {
            v8 = 5875;
            goto LABEL_43;
          }
        }
        (*(void (__fastcall **)(_QWORD, _QWORD, void *))(**(_QWORD **)(a1 + 720) + 24LL))(
          *(_QWORD *)(a1 + 720),
          *(_QWORD *)(a3 + 8),
          lpMem);
      }
      Index1ById = 0;
      goto LABEL_24;
    }
    *(_QWORD *)&Uuid.Data1 = *(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9);
    v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&Uuid.Data1 + 552LL) + 8LL * v52);
    *(_DWORD *)(v15 + 352) = *(_DWORD *)(a3 + 136);
    *(_DWORD *)(v15 + 348) = *(_QWORD *)(a3 + 152) != 0;
    v16 = 0;
    v17 = 0;
    if ( *(_QWORD *)(a3 + 48) )
    {
      v18 = v15 + 200;
      v19 = *(void **)(v15 + 200);
      if ( v19 )
      {
        SusFree(v19);
        v18 = v15 + 200;
        *(_QWORD *)(v15 + 200) = 0;
      }
      DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 48), v18);
    }
    v20 = *(wchar_t ***)(a3 + 64);
    if ( v20 )
    {
      v16 = SusDuplicateStringArray(v20, *(_DWORD *)(a3 + 72));
      if ( !v16 )
      {
        v8 = 5947;
LABEL_42:
        Index1ById = -2147024882;
        goto LABEL_43;
      }
    }
    *(_QWORD *)(v15 + 264) = v16;
    *(_DWORD *)(v15 + 272) = *(_DWORD *)(a3 + 72);
    v21 = *(_DWORD *)(a3 + 168);
    if ( *(_QWORD *)(a3 + 160) )
    {
      if ( v21 )
        goto LABEL_39;
    }
    else if ( !v21 )
    {
      goto LABEL_39;
    }
    WUTrace(
      "CUpdateDeploymentJob::DeploymentOperationNotify",
      5955,
      32,
      3,
      0,
      L"TelemetryAssert (%ws): %ws",
      L"(data.rgpszDriverRecoveryIds == nullptr && data.cDriverRecoveryIds == 0) || (data.rgpszDriverRecoveryIds != nullpt"
       "r && data.cDriverRecoveryIds != 0)",
      L"Failed");
    WUTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
LABEL_39:
    v22 = *(wchar_t ***)(a3 + 160);
    if ( v22 )
    {
      v17 = SusDuplicateStringArray(v22, *(_DWORD *)(a3 + 168));
      if ( !v17 )
      {
        v8 = 5960;
        goto LABEL_42;
      }
    }
    *(_QWORD *)(v15 + 368) = v17;
    *(_DWORD *)(v15 + 376) = *(_DWORD *)(a3 + 168);
    DPCopyMSIExtendedInformation((struct tagMSIExtendedInfo *)(v15 + 216), (const struct tagMSIExtendedInfo *)(a3 + 80));
    v23 = *(void **)(v15 + 144);
    if ( v23 )
    {
      SusFree(v23);
      *(_QWORD *)(v15 + 144) = 0;
    }
    DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 144), v15 + 144);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl'::`2'::impl) )
    {
      v24 = *(void **)(v15 + 384);
      if ( v24 )
      {
        SusFree(v24);
        *(_QWORD *)(v15 + 384) = 0;
      }
      v25 = DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 176), v15 + 384);
      if ( v25 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1756,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v25,
          v50);
      *(_OWORD *)(v15 + 392) = *(_OWORD *)(a3 + 184);
      *(_QWORD *)(v15 + 408) = *(_QWORD *)(a3 + 200);
      *(_DWORD *)(v15 + 416) = *(_DWORD *)(a3 + 208);
    }
    v26 = *(_QWORD *)&Uuid.Data1;
    *(_DWORD *)(*(_QWORD *)&Uuid.Data1 + 96LL) = *(_DWORD *)(a3 + 40);
    v27 = *(_WORD **)(v26 + 128);
    if ( v27 && *v27 || (v28 = *(_WORD **)(a3 + 128)) == 0 || !*v28 )
    {
      Index1ById = 0;
    }
    else
    {
      if ( v27 )
      {
        SusFree(v27);
        *(_QWORD *)(v26 + 128) = 0;
      }
      v29 = DuplicateString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 128), v26 + 128);
      Index1ById = 0;
      if ( v29 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1763,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v29,
          v50);
    }
    if ( *(_DWORD *)(a3 + 8) != 3 )
    {
      v30 = *(_QWORD *)(a3 + 56);
      if ( v30 )
      {
        v55 = 0;
        v56 = 0;
        v50 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 552LL) + 8 * v11) + 288;
        if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned int *, int *))(**(_QWORD **)(a1 + 720) + 32LL))(
               *(_QWORD *)(a1 + 720),
               v30,
               &v55,
               &v56) >= 0 )
        {
          v31 = v55;
          if ( (v55 & 0x80000000) != 0 )
          {
            *(_DWORD *)(a3 + 8) = 0;
            *(_DWORD *)(a3 + 36) = v31;
            *(_DWORD *)(a3 + 40) = v56;
          }
          else
          {
            *(_DWORD *)(a3 + 8) = 1;
          }
        }
        if ( *(_DWORD *)(a3 + 8) != 4 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 720) + 40LL))(
            *(_QWORD *)(a1 + 720),
            *(_QWORD *)(a3 + 56));
      }
    }
    v32 = *(_DWORD *)(a3 + 8);
    if ( v32 )
    {
      v33 = v32 - 1;
      if ( v33 )
      {
        v34 = v33 - 1;
        if ( !v34 )
        {
          CUpdateDeploymentJob::OnUpdateAborted((CUpdateDeploymentJob *)(a1 - 8), v9);
          goto LABEL_24;
        }
        if ( (unsigned int)(v34 - 1) > 1 )
          goto LABEL_24;
      }
      v35 = *(_QWORD *)&Uuid.Data1;
      if ( *(_DWORD *)(*(_QWORD *)&Uuid.Data1 + 56LL) == 8 )
      {
        DoesCommitOperationRequireReboot = CUpdateDeploymentJob::DoesCommitOperationRequireReboot(
                                             (CUpdateDeploymentJob *)(a1 - 8),
                                             *(const wchar_t **)(v15 + 80),
                                             (int *)(a3 + 16));
        if ( DoesCommitOperationRequireReboot < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x17B4,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)DoesCommitOperationRequireReboot,
            v50);
        v35 = *(_QWORD *)&Uuid.Data1;
      }
      if ( *(_DWORD *)(a3 + 12) )
      {
        v37 = a1 - 8;
        v38 = 2;
      }
      else
      {
        if ( !*(_DWORD *)(a3 + 16) && !*(_DWORD *)(v15 + 196) )
          goto LABEL_85;
        v37 = a1 - 8;
        v38 = 2;
        if ( !*(_DWORD *)(v35 + 488) )
          v38 = 1;
      }
      CUpdateDeploymentJob::SetRebootStatus(v37, v9, (unsigned int)v11, v38);
LABEL_85:
      if ( v9 < *(_DWORD *)(a1 + 680) )
      {
        _mm_lfence();
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 552LL) + 8 * v11) + 108LL) = *(_DWORD *)(a3 + 20);
      }
      if ( *(_DWORD *)(a3 + 24) )
      {
        if ( v9 < *(_DWORD *)(a1 + 680) )
        {
          _mm_lfence();
          if ( (unsigned int)v11 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 544LL) )
          {
            _mm_lfence();
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 552LL) + 8 * v11) + 112LL) = 1;
          }
        }
      }
      v39 = *(void **)(v15 + 136);
      if ( v39 )
      {
        SusFree(v39);
        *(_QWORD *)(v15 + 136) = 0;
      }
      DuplicateOptionalString<wchar_t *,wchar_t *>(*(_QWORD *)(a3 + 152), v15 + 136);
      Index1ById = 0;
      CUpdateDeploymentJob::OnUpdateProgress((CUpdateDeploymentJob *)(a1 - 8), v9, v11, 0x64u, 0, 0, 1, 0);
      Uuid = GUID_NULL;
      v40 = UuidFromStringW(*(RPC_WSTR *)(v15 + 16), &Uuid);
      if ( v40 >= 1 )
        v40 = (unsigned __int16)v40 | 0x80010000;
      if ( v40 >= 0 )
      {
        v53 = Uuid;
        v54 = 0;
        CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::Add(
          a1 + 632,
          &v53,
          &v53);
      }
      if ( *(_DWORD *)(a3 + 8) == 3 || *(_DWORD *)(a3 + 8) == 4 )
      {
        v41 = *(_WORD **)(a3 + 56);
        if ( v41 )
        {
          v42 = 0x7FFFFFFF;
          do
          {
            if ( !*v41 )
              break;
            ++v41;
            --v42;
          }
          while ( v42 );
          v43 = (0x7FFFFFFF - v42) & -(__int64)(v42 != 0);
          if ( !v42 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x17EC,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)0x80070057LL,
              v51);
          v44 = *(void **)(v15 + 184);
          if ( v44 )
          {
            SusFree(v44);
            *(_QWORD *)(v15 + 184) = 0;
          }
          v45 = DPCopyBufferWithAlloc(
                  2 * (int)v43 + 2,
                  *(const unsigned __int8 **)(a3 + 56),
                  (unsigned int *)(v15 + 176),
                  (unsigned __int8 **)(v15 + 184));
          Index1ById = 0;
          if ( v45 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x17F2,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)(unsigned int)v45,
              v51);
        }
        *(_DWORD *)(v15 + 208) = *(_DWORD *)(a3 + 8) == 4;
      }
      goto LABEL_24;
    }
    if ( *(_DWORD *)(a3 + 12) )
      goto LABEL_113;
    if ( !*(_DWORD *)(a3 + 16) )
    {
LABEL_115:
      CUpdateDeploymentJob::OnUpdateFailure(
        (CUpdateDeploymentJob *)(a1 - 8),
        v9,
        *(_DWORD *)(a3 + 36),
        *(_DWORD *)(a3 + 40),
        &v52);
      Uuid = GUID_NULL;
      v47 = UuidFromStringW(*(RPC_WSTR *)(v15 + 16), &Uuid);
      if ( v47 >= 1 )
        v47 = (unsigned __int16)v47 | 0x80010000;
      if ( v47 >= 0 )
      {
        v53 = Uuid;
        v54 = *(_QWORD *)(a3 + 36);
        CSusMap<_GUID,tagDPProcessedUpdate,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpNoop<tagDPProcessedUpdate>>::Add(
          a1 + 632,
          &v53,
          &v53);
      }
      goto LABEL_24;
    }
    v46 = 1;
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 688) + 8LL * v9) + 488LL) )
LABEL_113:
      v46 = 2;
    CUpdateDeploymentJob::SetRebootStatus(a1 - 8, v9, (unsigned int)v11, v46);
    goto LABEL_115;
  }
  Index1ById = 0;
  v48 = 0;
  if ( *(_DWORD *)(a3 + 28) && *(_DWORD *)(a3 + 24) )
    v48 = (unsigned int)(100 * *(_DWORD *)(a3 + 24)) / *(_DWORD *)(a3 + 28);
  v49 = (CUpdateDeploymentJob *)(a1 - 8);
  if ( *(_DWORD *)(a3 + 48) )
    CUpdateDeploymentJob::OnUpdateTopLevelProgress(v49, v9, v48);
  else
    CUpdateDeploymentJob::OnUpdateProgress(
      v49,
      v9,
      v52,
      v48,
      *(_DWORD *)(a3 + 32),
      *(const unsigned __int8 **)(a3 + 40),
      0,
      0);
LABEL_24:
  if ( lpMem )
    SusFree(lpMem);
  return (unsigned int)Index1ById;
}

```

## disassembly

```asm
0x180035ca0  push    rbp
0x180035ca2  push    rbx
0x180035ca3  push    rsi
0x180035ca4  push    rdi
0x180035ca5  push    r12
0x180035ca7  push    r13
0x180035ca9  push    r14
0x180035cab  push    r15
0x180035cad  lea     rbp, [rsp-1Fh]
0x180035cb2  sub     rsp, 98h
0x180035cb9  mov     rax, cs:__security_cookie
0x180035cc0  xor     rax, rsp
0x180035cc3  mov     [rbp+57h+var_50], rax
0x180035cc7  mov     rsi, r8
0x180035cca  mov     r12, rdx
0x180035ccd  mov     r14, rcx
0x180035cd0  or      r13d, 0FFFFFFFFh
0x180035cd4  mov     [rbp+57h+var_70], r13d
0x180035cd8  mov     [rbp+57h+var_90], r13d
0x180035cdc  xor     r8d, r8d
0x180035cdf  mov     [rbp+57h+lpMem], r8
0x180035ce3  test    rsi, rsi
0x180035ce6  jnz     short loc_180035CF7
0x180035ce8  mov     ebx, 80004003h
0x180035ced  mov     edx, 16DAh
0x180035cf2  jmp     loc_180035F77
0x180035cf7  test    r9, r9
0x180035cfa  jnz     short loc_180035D05
0x180035cfc  mov     r15d, [rcx+298h]
0x180035d03  jmp     short loc_180035D29
0x180035d05  lea     r8, [rbp+57h+var_70]; unsigned int *
0x180035d09  mov     rdx, r9; struct tagDSGlobalUpdateId *
0x180035d0c  add     rcx, 0FFFFFFFFFFFFFFF8h; this
0x180035d10  call    ?FindIndex1ById@CUpdateDeploymentJob@@AEAAJAEBUtagDSGlobalUpdateId@@PEAK@Z; CUpdateDeploymentJob::FindIndex1ById(tagDSGlobalUpdateId const &,ulong *)
0x180035d15  mov     ebx, eax
0x180035d17  test    eax, eax
0x180035d19  jns     short loc_180035D25
0x180035d1b  mov     edx, 16E3h
0x180035d20  jmp     loc_180035F77
0x180035d25  mov     r15d, [rbp+57h+var_70]
0x180035d29  cmp     r15d, r13d
0x180035d2c  jnz     short loc_180035D3D
0x180035d2e  mov     ebx, 80240FFFh
0x180035d33  mov     edx, 16E6h
0x180035d38  jmp     loc_180035F77
0x180035d3d  lea     r9, [rbp+57h+var_90]; unsigned int *
0x180035d41  mov     r8d, r15d; unsigned int
0x180035d44  mov     rdx, r12; struct tagDSGlobalUpdateId *
0x180035d47  lea     rcx, [r14-8]; this
0x180035d4b  call    ?FindIndex2ById@CUpdateDeploymentJob@@AEAAJAEBUtagDSGlobalUpdateId@@KPEAK@Z; CUpdateDeploymentJob::FindIndex2ById(tagDSGlobalUpdateId const &,ulong,ulong *)
0x180035d50  mov     ebx, eax
0x180035d52  xor     r8d, r8d
0x180035d55  test    eax, eax
0x180035d57  jns     short loc_180035D63
0x180035d59  mov     edx, 16E8h
0x180035d5e  jmp     loc_180035F77
0x180035d63  mov     r12d, [rbp+57h+var_90]
0x180035d67  cmp     r12d, r13d
0x180035d6a  jnz     short loc_180035D7B
0x180035d6c  mov     ebx, 80240FFFh
0x180035d71  mov     edx, 16EAh
0x180035d76  jmp     loc_180035F77
0x180035d7b  mov     ecx, [rsi]
0x180035d7d  sub     ecx, 1
0x180035d80  jz      loc_1800364CA
0x180035d86  sub     ecx, 1
0x180035d89  jz      loc_180035E37
0x180035d8f  cmp     ecx, 1
0x180035d92  jnz     short loc_180035E04
0x180035d94  mov     ecx, r15d
0x180035d97  mov     rax, [r14+2B0h]
0x180035d9e  mov     rcx, [rax+rcx*8]
0x180035da2  test    byte ptr [rcx+218h], 20h
0x180035da9  jz      short loc_180035DE9
0x180035dab  mov     rbx, [r14+2B8h]
0x180035db2  mov     rax, [rbx]
0x180035db5  mov     rdi, [rax+80h]
0x180035dbc  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180035dc0  test    rcx, rcx
0x180035dc3  jz      short loc_180035DCA
0x180035dc5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180035dca  lea     rdx, [rbp+57h+lpMem]
0x180035dce  mov     rcx, rbx
0x180035dd1  mov     rax, rdi
0x180035dd4  call    _guard_dispatch_icall
0x180035dd9  mov     ebx, eax
0x180035ddb  test    eax, eax
0x180035ddd  jns     short loc_180035DE9
0x180035ddf  mov     edx, 16F3h
0x180035de4  jmp     loc_180035F77
0x180035de9  mov     rcx, [r14+2D0h]
0x180035df0  mov     rax, [rcx]
0x180035df3  mov     r8, [rbp+57h+lpMem]
0x180035df7  mov     rdx, [rsi+8]
0x180035dfb  mov     rax, [rax+18h]
0x180035dff  call    _guard_dispatch_icall
0x180035e04  xor     ebx, ebx
0x180035e06  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180035e0a  test    rcx, rcx
0x180035e0d  jz      short loc_180035E15
0x180035e0f  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180035e14  nop
0x180035e15  mov     eax, ebx
0x180035e17  mov     rcx, [rbp+57h+var_50]
0x180035e1b  xor     rcx, rsp; StackCookie
0x180035e1e  call    __security_check_cookie
0x180035e23  add     rsp, 98h
0x180035e2a  pop     r15
0x180035e2c  pop     r14
0x180035e2e  pop     r13
0x180035e30  pop     r12
0x180035e32  pop     rdi
0x180035e33  pop     rsi
0x180035e34  pop     rbx
0x180035e35  pop     rbp
0x180035e36  retn
0x180035e37  mov     ecx, r15d
0x180035e3a  mov     rax, [r14+2B0h]
0x180035e41  mov     rax, [rax+rcx*8]
0x180035e45  mov     qword ptr [rbp+57h+Uuid.Data1], rax
0x180035e49  mov     rax, [rax+228h]
0x180035e50  mov     r13, [rax+r12*8]
0x180035e54  mov     eax, [rsi+88h]
0x180035e5a  mov     [r13+160h], eax
0x180035e61  mov     eax, r8d
0x180035e64  cmp     [rsi+98h], r8
0x180035e6b  setnz   al
0x180035e6e  mov     [r13+15Ch], eax
0x180035e75  mov     rbx, r8
0x180035e78  mov     rdi, r8
0x180035e7b  cmp     [rsi+30h], r8
0x180035e7f  jz      short loc_180035EB0
0x180035e81  lea     rax, [r13+0C8h]
0x180035e88  mov     rcx, [rax]; lpMem
0x180035e8b  test    rcx, rcx
0x180035e8e  jz      short loc_180035EA1
0x180035e90  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180035e95  lea     rax, [r13+0C8h]
0x180035e9c  xor     edx, edx
0x180035e9e  mov     [rax], rdx
0x180035ea1  mov     rdx, rax
0x180035ea4  mov     rcx, [rsi+30h]
0x180035ea8  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180035ead  xor     r8d, r8d
0x180035eb0  mov     rcx, [rsi+40h]; wchar_t **
0x180035eb4  test    rcx, rcx
0x180035eb7  jz      short loc_180035ED6
0x180035eb9  mov     edx, [rsi+48h]; unsigned int
0x180035ebc  call    ?SusDuplicateStringArray@@YAPEAPEA_WQEAPEA_WI@Z; SusDuplicateStringArray(wchar_t * * const,uint)
0x180035ec1  mov     rbx, rax
0x180035ec4  xor     r8d, r8d
0x180035ec7  test    rax, rax
0x180035eca  jnz     short loc_180035ED6
0x180035ecc  mov     edx, 173Bh
0x180035ed1  jmp     loc_180035F72
0x180035ed6  mov     [r13+108h], rbx
0x180035edd  mov     eax, [rsi+48h]
0x180035ee0  mov     [r13+110h], eax
0x180035ee7  mov     eax, [rsi+0A8h]
0x180035eed  cmp     [rsi+0A0h], r8
0x180035ef4  jnz     short loc_180035EFC
0x180035ef6  test    eax, eax
0x180035ef8  jz      short loc_180035F4E
0x180035efa  jmp     short loc_180035F00
0x180035efc  test    eax, eax
0x180035efe  jnz     short loc_180035F4E
0x180035f00  lea     rax, aFailed; "Failed"
0x180035f07  mov     qword ptr [rsp+0D0h+var_98], rax
0x180035f0c  lea     rax, aDataRgpszdrive; "(data.rgpszDriverRecoveryIds == nullptr"...
0x180035f13  mov     qword ptr [rsp+0D0h+var_A0], rax
0x180035f18  lea     rax, aTelemetryasser; "TelemetryAssert (%ws): %ws"
0x180035f1f  mov     [rsp+0D0h+var_A8], rax
0x180035f24  mov     [rsp+0D0h+var_B0], r8; int
0x180035f29  mov     edx, 1743h
0x180035f2e  mov     r9d, 3
0x180035f34  lea     r8d, [r9+1Dh]
0x180035f38  lea     rcx, aCupdatedeploym_5; "CUpdateDeploymentJob::DeploymentOperati"...
0x180035f3f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180035f44  or      ecx, 0FFFFFFFFh; unsigned int
0x180035f47  mov     edx, ecx; unsigned int
0x180035f49  call    ?WUTelemetryAssertTriggered@@YAXII@Z; WUTelemetryAssertTriggered(uint,uint)
0x180035f4e  mov     rcx, [rsi+0A0h]; wchar_t **
0x180035f55  test    rcx, rcx
0x180035f58  jz      short loc_180035F8F
0x180035f5a  mov     edx, [rsi+0A8h]; unsigned int
0x180035f60  call    ?SusDuplicateStringArray@@YAPEAPEA_WQEAPEA_WI@Z; SusDuplicateStringArray(wchar_t * * const,uint)
0x180035f65  mov     rdi, rax
0x180035f68  test    rax, rax
0x180035f6b  jnz     short loc_180035F8F
0x180035f6d  mov     edx, 1748h; void *
0x180035f72  mov     ebx, 8007000Eh
0x180035f77  mov     rcx, [rbp+5Fh]; this
0x180035f7b  mov     r9d, ebx; char *
0x180035f7e  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180035f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f8a  jmp     loc_180035E06
0x180035f8f  mov     [r13+170h], rdi
0x180035f96  mov     eax, [rsi+0A8h]
0x180035f9c  mov     [r13+178h], eax
0x180035fa3  lea     rdx, [rsi+50h]; struct tagMSIExtendedInfo *
0x180035fa7  lea     rcx, [r13+0D8h]; struct tagMSIExtendedInfo *
0x180035fae  call    ?DPCopyMSIExtendedInformation@@YAJAEAUtagMSIExtendedInfo@@AEBU1@@Z; DPCopyMSIExtendedInformation(tagMSIExtendedInfo &,tagMSIExtendedInfo const &)
0x180035fb3  lea     rbx, [r13+90h]
0x180035fba  mov     rcx, [rbx]; lpMem
0x180035fbd  xor     edi, edi
0x180035fbf  test    rcx, rcx
0x180035fc2  jz      short loc_180035FCC
0x180035fc4  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180035fc9  mov     [rbx], rdi
0x180035fcc  mov     rdx, rbx
0x180035fcf  mov     rcx, [rsi+90h]
0x180035fd6  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180035fdb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration> `wil::Feature<__WilFeatureTraits_Feature_ModelCacheGeneration>::GetImpl(void)'::`2'::impl
0x180035fe2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ModelCacheGeneration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ModelCacheGeneration>::__private_IsEnabled(void)
0x180035fe7  lea     rdi, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180035fee  xor     edx, edx
0x180035ff0  test    al, al
0x180035ff2  jz      short loc_180036065
0x180035ff4  lea     rbx, [r13+180h]
0x180035ffb  mov     rcx, [rbx]; lpMem
0x180035ffe  test    rcx, rcx
0x180036001  jz      short loc_18003600D
0x180036003  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180036008  xor     edx, edx
0x18003600a  mov     [rbx], rdx
0x18003600d  mov     rdx, rbx
0x180036010  mov     rcx, [rsi+0B0h]
0x180036017  call    ??$DuplicateOptionalString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateOptionalString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x18003601c  mov     rcx, [rbp+5Fh]; this
0x180036020  xor     edx, edx
0x180036022  test    eax, eax
0x180036024  jns     short loc_180036038
0x180036026  mov     r9d, eax; char *
0x180036029  mov     r8, rdi; unsigned int
0x18003602c  mov     edx, 1756h; void *
0x180036031  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180036036  xor     edx, edx
0x180036038  movups  xmm0, xmmword ptr [rsi+0B8h]
0x18003603f  movups  xmmword ptr [r13+188h], xmm0
0x180036047  movsd   xmm1, qword ptr [rsi+0C8h]
0x18003604f  movsd   qword ptr [r13+198h], xmm1
0x180036058  mov     eax, [rsi+0D0h]
0x18003605e  mov     [r13+1A0h], eax
0x180036065  mov     eax, [rsi+28h]
0x180036068  mov     rbx, qword ptr [rbp+57h+Uuid.Data1]
0x18003606c  mov     [rbx+60h], eax
0x18003606f  mov     rcx, [rbx+80h]; lpMem
0x180036076  test    rcx, rcx
0x180036079  jz      short loc_180036080
0x18003607b  cmp     [rcx], dx
0x18003607e  jnz     short loc_1800360D3
0x180036080  mov     rax, [rsi+80h]
0x180036087  test    rax, rax
0x18003608a  jz      short loc_1800360D3
0x18003608c  cmp     [rax], dx
0x18003608f  jz      short loc_1800360D3
0x180036091  test    rcx, rcx
0x180036094  jz      short loc_1800360A4
0x180036096  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003609b  xor     edx, edx
0x18003609d  mov     [rbx+80h], rdx
0x1800360a4  lea     rdx, [rbx+80h]
0x1800360ab  mov     rcx, [rsi+80h]
0x1800360b2  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1800360b7  mov     rcx, [rbp+5Fh]; this
0x1800360bb  xor     ebx, ebx
0x1800360bd  test    eax, eax
0x1800360bf  jns     short loc_1800360D5
0x1800360c1  mov     r9d, eax; char *
0x1800360c4  mov     r8, rdi; unsigned int
0x1800360c7  mov     edx, 1763h; void *
0x1800360cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800360d1  jmp     short loc_1800360D5
0x1800360d3  xor     ebx, ebx
0x1800360d5  cmp     dword ptr [rsi+8], 3
0x1800360d9  jz      loc_18003617B
0x1800360df  mov     rdx, [rsi+38h]
0x1800360e3  test    rdx, rdx
0x1800360e6  jz      loc_18003617B
0x1800360ec  mov     [rbp+57h+var_70], ebx
0x1800360ef  mov     [rbp+57h+var_6C], ebx
0x1800360f2  mov     ecx, r15d
0x1800360f5  mov     rax, [r14+2B0h]
0x1800360fc  mov     rax, [rax+rcx*8]
0x180036100  mov     rax, [rax+228h]
0x180036107  mov     r8, [rax+r12*8]
0x18003610b  mov     rcx, [r14+2D0h]
0x180036112  lea     r9, [r8+120h]
0x180036119  mov     rax, [rcx]
0x18003611c  mov     r8, [r8+118h]
0x180036123  mov     [rsp+0D0h+var_A8], r8
0x180036128  mov     [rsp+0D0h+var_B0], r9; int
0x18003612d  lea     r9, [rbp+57h+var_6C]
0x180036131  lea     r8, [rbp+57h+var_70]
0x180036135  mov     rax, [rax+20h]
0x180036139  call    _guard_dispatch_icall
0x18003613e  test    eax, eax
0x180036140  js      short loc_18003615E
0x180036142  mov     eax, [rbp+57h+var_70]
0x180036145  test    eax, eax
  ... truncated ...
```
