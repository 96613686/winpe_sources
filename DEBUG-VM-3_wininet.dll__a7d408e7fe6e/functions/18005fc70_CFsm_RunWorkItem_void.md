# CFsm::RunWorkItem(void *)

- ea: `0x18005fc70`
- end: `0x180060640`
- name: `?RunWorkItem@CFsm@@SAKPEAX@Z`
- size: `2512`
- prototype: `unsigned int __fastcall(CFsm *this)`
- caller_count: `6`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003a74c`
- `0x18005eeb0`
- `0x18008a9d0`
- `0x18010d040`
- `0x180115424`
- `0x1801289f0`

## callees

- `0x18005e7e0`
- `0x18005fc70`
- `0x180060650`
- `0x180060d30`
- `0x180060f00`
- `0x180064060`
- `0x1800641c0`
- `0x1800c60c8`
- `0x1800d2e04`
- `0x180102904`
- `0x18013ed20`
- `0x18014a7a0`
- `0x18015ee50`
- `0x18015eef0`
- `0x1801b13f8`
- `0x1801c9c31`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e8f78`
- `0x1801e913c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fd08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ffa4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060442`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005fd08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ffa4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800602a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060442`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800605e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ff53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005fccf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ff53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060004`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800600fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800601a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180060213`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006039e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800600fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800601a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180060213`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006039e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005ffbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18005ffbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005ffc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005ffc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006047f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006047f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fcf4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005fcf4`
- `ntdll!EtwEventActivityIdControl` at `0x18005fe53`
- `ntdll!EtwEventActivityIdControl` at `0x18005fe97`
- `ntdll!EtwEventActivityIdControl` at `0x18005ff88`
- `ntdll!EtwEventActivityIdControl` at `0x18006003c`
- `ntdll!EtwEventActivityIdControl` at `0x18005fe53`
- `ntdll!EtwEventActivityIdControl` at `0x18005fe97`
- `ntdll!EtwEventActivityIdControl` at `0x18005ff88`
- `ntdll!EtwEventActivityIdControl` at `0x18006003c`
- `ntdll!RtlGetLastNtStatus` at `0x18006010f`
- `ntdll!RtlGetLastNtStatus` at `0x1800601b2`
- `ntdll!RtlGetLastNtStatus` at `0x180060224`
- `ntdll!RtlGetLastNtStatus` at `0x18006010f`
- `ntdll!RtlGetLastNtStatus` at `0x1800601b2`
- `ntdll!RtlGetLastNtStatus` at `0x180060224`

## pseudocode

```c
__int64 __fastcall CFsm::RunWorkItem(CFsm *this, int a2, int a3)
{
  CFsm *v3; // r15
  DWORD LastError; // eax
  DWORD v5; // edi
  LPVOID Value; // r13
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // rcx
  struct _GUID *v12; // rdi
  int v13; // eax
  struct _GUID v14; // xmm0
  int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rcx
  struct _GUID *v18; // rax
  struct _GUID *v19; // rax
  int v20; // r12d
  int v21; // r14d
  __int64 v22; // rcx
  __int64 v23; // rcx
  struct _GUID *p_Buf1; // rax
  int v25; // eax
  unsigned __int64 v26; // rcx
  const struct _GUID *v27; // r9
  bool v28; // sf
  int v29; // eax
  bool v30; // sf
  CPushSyncBlock *v31; // r12
  __int64 v32; // rcx
  int v33; // edx
  unsigned int v34; // esi
  int v35; // r8d
  __int64 v36; // rdi
  DWORD v37; // eax
  DWORD v38; // edi
  int v39; // eax
  bool v40; // sf
  signed __int32 v41; // esi
  DWORD TickCount; // ebx
  DWORD CurrentProcessId; // eax
  DWORD v44; // eax
  DWORD v45; // edi
  int v46; // eax
  bool v47; // sf
  __int64 v49; // rbx
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rbx
  __int64 v53; // rbx
  __int64 v54; // rcx
  const struct _EVENT_DESCRIPTOR *v55; // rdx
  unsigned __int64 v56; // rcx
  _BYTE *v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rcx
  __int64 v60; // r9
  _BYTE *v61; // r8
  _BYTE *v62; // rax
  __int64 v63; // rcx
  DWORD CurrentThreadId; // eax
  const char *v65; // rcx
  unsigned int v66; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v67; // [rsp+28h] [rbp-D8h]
  unsigned int v68; // [rsp+30h] [rbp-D0h]
  int v69; // [rsp+50h] [rbp-B0h]
  CPushSyncBlock *v70; // [rsp+58h] [rbp-A8h]
  int v71; // [rsp+60h] [rbp-A0h]
  int v72; // [rsp+64h] [rbp-9Ch]
  _OWORD v73[6]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v74; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v75[3]; // [rsp+D4h] [rbp-2Ch] BYREF
  struct _GUID v76; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID Buf1; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID v78; // [rsp+100h] [rbp+0h] BYREF
  int v79; // [rsp+110h] [rbp+10h]
  __int128 v80; // [rsp+118h] [rbp+18h] BYREF
  __int64 v81; // [rsp+128h] [rbp+28h] BYREF
  __int128 v82; // [rsp+130h] [rbp+30h]
  __int64 v83; // [rsp+140h] [rbp+40h]
  _UNKNOWN *retaddr; // [rsp+178h] [rbp+78h]

  memset(v73, 0, sizeof(v73));
  v79 = 0;
  v3 = this;
  v78 = 0;
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_sqqqPDd(
      (_DWORD)this,
      a2,
      a3,
      (unsigned int)word_180222338,
      (__int64)this,
      *((_QWORD *)this + 8),
      *((_QWORD *)this + 9),
      *((_QWORD *)this + 15),
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 10));
  LastError = GetLastError();
  v5 = LastError;
  if ( qword_180269EA8 && LastError && LastError != 997 && LastError != 12150 && LastError != 12028 && LastError != 122 )
  {
    v52 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
    GetSystemTimeAsFileTime((LPFILETIME)(v52 + qword_180269EA8));
    *(_DWORD *)(v52 + qword_180269EA8 + 8) = v5;
    *(_DWORD *)(v52 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  Value = TlsGetValue(InternetTlsIndex);
  if ( !Value )
  {
    if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(1037, 22, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
    }
    Value = (LPVOID)InternetCreateThreadInfo(1);
    if ( !Value && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
    {
      WPP_SF_(1037, 23, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
      SetLastError(v5);
      return 12004;
    }
  }
  SetLastError(v5);
  if ( !Value )
    return 12004;
  v70 = 0;
  InternetSaveThreadInfo(v73, v7, v8, v9);
  v10 = *((_DWORD *)Value + 18);
  *((_DWORD *)Value + 16) = 1;
  v11 = *((_QWORD *)v3 + 9);
  v72 = v10;
  if ( v11 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 192LL))(v11) )
    *((_DWORD *)Value + 18) = 1;
  while ( 1 )
  {
    v12 = (struct _GUID *)((char *)v3 + 172);
    v71 = *((_DWORD *)v3 + 36);
    v13 = *((_DWORD *)v3 + 38);
    v14 = 0;
    *((_QWORD *)Value + 10) = v3;
    v75[0] = 0;
    v81 = 0;
    v82 = 0;
    v74 = 32;
    v69 = v13;
    v83 = 0;
    v15 = *((_DWORD *)v3 + 47);
    *(_QWORD *)&v76.Data1 = 0;
    if ( !*((_DWORD *)v3 + 48) )
    {
      v16 = *((_QWORD *)v3 + 9);
      *((_DWORD *)v3 + 48) = 1;
      if ( v16 )
      {
        v14 = *(struct _GUID *)(v16 + 164);
LABEL_13:
        *v12 = v14;
        goto LABEL_14;
      }
      v50 = *((_QWORD *)v3 + 8);
      if ( !v50 )
      {
        if ( (v15 & 0x20) != 0 )
        {
          WxEtwGenerateActivityId((struct _GUID *)((char *)v3 + 172));
          *((_DWORD *)v3 + 47) &= ~0x20u;
          goto LABEL_14;
        }
        v51 = *((_QWORD *)v3 + 4);
        if ( v51 )
        {
          *v12 = *(struct _GUID *)(v51 + 172);
          goto LABEL_14;
        }
        goto LABEL_13;
      }
      MapHandleToAddress(v50, &v76, 0);
      v63 = *(_QWORD *)&v76.Data1;
      if ( *(_QWORD *)&v76.Data1 )
      {
        *v12 = *(struct _GUID *)(*(_QWORD *)&v76.Data1 + 164LL);
        DereferenceObject(v63);
        *(_QWORD *)&v76.Data1 = 0;
      }
    }
LABEL_14:
    v17 = 16;
    v18 = &v78;
    do
    {
      LOBYTE(v18->Data1) = 0;
      v18 = (struct _GUID *)((char *)v18 + 1);
      --v17;
    }
    while ( v17 );
    v79 = 0;
    v19 = &v78;
    v20 = v15 & 4;
    v21 = v15 & 8;
    v22 = 16;
    if ( (v15 & 0x20) != 0 )
      v12 = 0;
    v80 = 0;
    Buf1 = 0;
    do
    {
      LOBYTE(v19->Data1) = 0;
      v19 = (struct _GUID *)((char *)v19 + 1);
      --v22;
    }
    while ( v22 );
    v76 = 0;
    v23 = 16;
    p_Buf1 = &Buf1;
    do
    {
      LOBYTE(p_Buf1->Data1) = 0;
      p_Buf1 = (struct _GUID *)((char *)p_Buf1 + 1);
      --v23;
    }
    while ( v23 );
    v25 = EtwEventActivityIdControl(1, &v76);
    v28 = v25 < 0;
    if ( v25 > 0 )
      v28 = 1;
    if ( v28 )
      *(_DWORD *)&v76.Data2 = 128;
    else
      Buf1 = v76;
    if ( !v12 )
    {
      v41 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
      TickCount = GetTickCount();
      CurrentProcessId = GetCurrentProcessId();
      *(_QWORD *)&v80 = __PAIR64__(v41, (unsigned int)retaddr);
      v12 = (struct _GUID *)&v80;
      *((_QWORD *)&v80 + 1) = __PAIR64__(CurrentProcessId, TickCount);
    }
    if ( v21 && g_fEtwCorrelationProviderInitialized && Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfo(v26, &ActivityStart, v12, v27, v66);
    *(_DWORD *)&v76.Data2 = 0;
    v29 = EtwEventActivityIdControl(2, v12);
    v30 = v29 < 0;
    if ( v29 > 0 )
      v30 = 1;
    if ( v30 )
      *(_DWORD *)&v76.Data2 = 144;
    if ( v20
      && g_fEtwCorrelationProviderInitialized
      && memcmp_0(&Buf1, &qword_18021DEE0, 0x10u)
      && memcmp_0(v12, &qword_18021DEE0, 0x10u)
      && Microsoft_Windows_Networking_CorrelationEnabled )
    {
      EtwEx_tidActivityInfoTransfer(v56, v55, v12, &Buf1, v66, v67, v68);
    }
    v31 = v70;
    v79 = 1;
    v78 = Buf1;
    if ( v70 )
    {
      CPushSyncBlock::Release(v70);
      v31 = 0;
      v70 = 0;
    }
    if ( v71 )
    {
      v32 = *((_QWORD *)v3 + 9);
      if ( v32 )
      {
        v31 = (CPushSyncBlock *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 128LL))(v32);
        v70 = v31;
      }
      else
      {
        v31 = 0;
        v70 = 0;
      }
    }
    v34 = CFsm::Run(v3, (struct _INTERNET_THREAD_INFO *)Value, v75, &v81, &v74);
    if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    {
      v65 = "HANDLE";
      if ( v69 != 1 )
        v65 = "BOOL";
      WPP_SF_dDqDdsd(v74, v33, v35, v75[0], v75[0], (__int64)&v81, v81, v74, (__int64)v65, v34);
    }
    if ( v34 == 997 )
      goto LABEL_52;
    v3 = (CFsm *)*((_QWORD *)Value + 10);
    v36 = *((_QWORD *)Value + 7);
    if ( !v3 )
      break;
    if ( v71 )
      DereferenceObject(*((_QWORD *)Value + 7));
    v37 = GetLastError();
    v38 = v37;
    if ( qword_180269EA8 && v37 && v37 != 997 && v37 != 12150 && v37 != 12028 && v37 != 122 )
    {
      v49 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
      GetSystemTimeAsFileTime((LPFILETIME)(v49 + qword_180269EA8));
      *(_DWORD *)(v49 + qword_180269EA8 + 8) = v38;
      *(_DWORD *)(v49 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
    }
    if ( v79 )
    {
      *(_DWORD *)&v76.Data2 = 0;
      v39 = EtwEventActivityIdControl(2, &v78);
      v40 = v39 < 0;
      if ( v39 > 0 )
        v40 = 1;
      if ( v40 )
        *(_DWORD *)&v76.Data2 = 144;
    }
    SetLastError(v38);
  }
  if ( v71 && *(_DWORD *)(v36 + 524) )
  {
    Buf1 = 0;
    if ( v74 == 4 )
    {
      if ( v34 )
      {
        *(_DWORD *)Buf1.Data4 = v34;
      }
      else
      {
        if ( v69 == 1 )
          *(_QWORD *)&Buf1.Data1 = v75[0];
        else
          *(_QWORD *)&Buf1.Data1 = 1;
        *(_DWORD *)Buf1.Data4 = v81;
      }
      v74 = 16;
    }
    if ( GlobalFsmErrorRingBuffer )
    {
      if ( v34 )
      {
        if ( v36 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36) == 1902465608 )
          {
            if ( *(_DWORD *)(v36 + 864) )
            {
              v57 = *(_BYTE **)(v36 + 856);
              if ( v57 )
              {
                v58 = 80LL * (((unsigned __int8)_InterlockedExchangeAdd(&GlobalFsmErrorRingBufferIndex, 1u) + 1) & 0x3F);
                GetSystemTimeAsFileTime((LPFILETIME)(v58 + GlobalFsmErrorRingBuffer));
                v59 = 63;
                v60 = 64;
                *(_DWORD *)(v58 + GlobalFsmErrorRingBuffer + 8) = v34;
                v61 = (_BYTE *)(v58 + GlobalFsmErrorRingBuffer + 12);
                do
                {
                  if ( !v59 )
                    break;
                  if ( !*v57 )
                    break;
                  *v61++ = *v57++;
                  --v59;
                  --v60;
                }
                while ( v60 );
                v62 = v61 - 1;
                if ( v60 )
                  v62 = v61;
                *v62 = 0;
              }
            }
          }
        }
      }
    }
    if ( v31 )
    {
      CPushSyncBlock::EnterCallback(v31);
      SetLastError(v34);
      InternetIndicateStatus(0x64u);
      CPushSyncBlock::LeaveCallback(v31);
    }
    else
    {
      SetLastError(v34);
      InternetIndicateStatus(0x64u);
    }
    v54 = *((_QWORD *)Value + 7);
    if ( v54 )
      DereferenceObject(v54);
  }
LABEL_52:
  if ( v31 )
    CPushSyncBlock::Release(v31);
  *((_DWORD *)Value + 16) = 0;
  v44 = GetLastError();
  v45 = v44;
  if ( qword_180269EA8 && v44 && v44 != 997 && v44 != 12150 && v44 != 12028 && v44 != 122 )
  {
    v53 = 16LL * (unsigned __int8)_InterlockedIncrement(&dword_180269EA4);
    GetSystemTimeAsFileTime((LPFILETIME)(v53 + qword_180269EA8));
    *(_DWORD *)(v53 + qword_180269EA8 + 8) = v45;
    *(_DWORD *)(v53 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
  }
  if ( v79 )
  {
    *(_DWORD *)&v76.Data2 = 0;
    v46 = EtwEventActivityIdControl(2, &v78);
    v47 = v46 < 0;
    if ( v46 > 0 )
      v47 = 1;
    if ( v47 )
      *(_DWORD *)&v76.Data2 = 144;
  }
  SetLastError(v45);
  if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
    WPP_SF_d(1033, 30, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v34);
  InternetRestoreThreadInfo(v73);
  *((_DWORD *)Value + 18) = v72 != 0;
  return v34;
}

```

## disassembly

```asm
0x18005fc70  push    rbp
0x18005fc72  push    rsi
0x18005fc73  push    rdi
0x18005fc74  push    r13
0x18005fc76  push    r15
0x18005fc78  lea     rbp, [rsp-50h]
0x18005fc7d  sub     rsp, 150h
0x18005fc84  mov     rax, cs:__security_cookie
0x18005fc8b  xor     rax, rsp
0x18005fc8e  mov     [rbp+70h+var_28], rax
0x18005fc92  xorps   xmm0, xmm0
0x18005fc95  xor     eax, eax
0x18005fc97  movups  [rsp+170h+var_100], xmm0
0x18005fc9c  mov     [rbp+70h+var_60], eax
0x18005fc9f  mov     r15, rcx
0x18005fca2  movups  [rbp+70h+var_F0], xmm0
0x18005fca6  movups  [rbp+70h+var_E0], xmm0
0x18005fcaa  movups  [rbp+70h+var_D0], xmm0
0x18005fcae  movups  [rbp+70h+var_C0], xmm0
0x18005fcb2  movups  [rbp+70h+var_B0], xmm0
0x18005fcb6  movups  [rbp+70h+var_70], xmm0
0x18005fcba  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005fcc1  jnz     loc_1800604A3
0x18005fcc7  mov     [rsp+170h+arg_8], rbx
0x18005fccf  call    cs:__imp_GetLastError
0x18005fcd5  cmp     cs:qword_180269EA8, 0
0x18005fcdd  mov     esi, 1
0x18005fce2  mov     edi, eax
0x18005fce4  jz      short loc_18005FCEE
0x18005fce6  test    eax, eax
0x18005fce8  jnz     loc_180060157
0x18005fcee  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x18005fcf4  call    cs:__imp_TlsGetValue
0x18005fcfa  mov     r13, rax
0x18005fcfd  test    rax, rax
0x18005fd00  jz      loc_180060401
0x18005fd06  mov     ecx, edi; dwErrCode
0x18005fd08  call    cs:__imp_SetLastError
0x18005fd0e  test    r13, r13
0x18005fd11  jz      loc_180060448
0x18005fd17  mov     [rsp+170h+arg_10], r12
0x18005fd1f  lea     rcx, [rsp+170h+var_100]
0x18005fd24  mov     [rsp+170h+arg_18], r14
0x18005fd2c  mov     [rsp+170h+var_118], 0
0x18005fd35  call    InternetSaveThreadInfo
0x18005fd3a  mov     eax, [r13+48h]
0x18005fd3e  mov     [r13+40h], esi
0x18005fd42  mov     rcx, [r15+48h]
0x18005fd46  mov     [rsp+170h+var_10C], eax
0x18005fd4a  test    rcx, rcx
0x18005fd4d  jz      short loc_18005FD66
0x18005fd4f  mov     rax, [rcx]
0x18005fd52  mov     rax, [rax+0C0h]
0x18005fd59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd5e  test    eax, eax
0x18005fd60  jnz     loc_1800604F1
0x18005fd66  mov     eax, [r15+90h]
0x18005fd6d  lea     rdi, [r15+0ACh]
0x18005fd74  xor     edx, edx
0x18005fd76  mov     [rsp+170h+var_110], eax
0x18005fd7a  mov     eax, [r15+98h]
0x18005fd81  xorps   xmm0, xmm0
0x18005fd84  mov     [r13+50h], r15
0x18005fd88  mov     [rbp+70h+var_9C], edx
0x18005fd8b  mov     [rbp+70h+var_48], rdx
0x18005fd8f  movups  [rbp+70h+var_40], xmm0
0x18005fd93  mov     [rbp+70h+var_A0], 20h ; ' '
0x18005fd9a  mov     [rsp+170h+var_120], eax
0x18005fd9e  xor     eax, eax
0x18005fda0  mov     [rbp+70h+var_30], rax
0x18005fda4  mov     ebx, [r15+0BCh]
0x18005fdab  mov     qword ptr [rbp+70h+var_90], rdx
0x18005fdaf  cmp     [r15+0C0h], eax
0x18005fdb6  jnz     short loc_18005FDD6
0x18005fdb8  mov     rax, [r15+48h]
0x18005fdbc  mov     [r15+0C0h], esi
0x18005fdc3  test    rax, rax
0x18005fdc6  jz      loc_180060125
0x18005fdcc  movups  xmm0, xmmword ptr [rax+0A4h]
0x18005fdd3  movups  xmmword ptr [rdi], xmm0
0x18005fdd6  mov     ecx, 10h
0x18005fddb  lea     rax, [rbp+70h+var_70]
0x18005fddf  nop
0x18005fde0  mov     byte ptr [rax], 0
0x18005fde3  lea     rax, [rax+1]
0x18005fde7  sub     rcx, 1
0x18005fdeb  jnz     short loc_18005FDE0
0x18005fded  mov     r12d, ebx
0x18005fdf0  mov     [rbp+70h+var_60], edx
0x18005fdf3  mov     r14d, ebx
0x18005fdf6  lea     rax, [rbp+70h+var_70]
0x18005fdfa  and     r12d, 4
0x18005fdfe  and     r14d, 8
0x18005fe02  test    bl, 20h
0x18005fe05  xorps   xmm0, xmm0
0x18005fe08  xorps   xmm1, xmm1
0x18005fe0b  mov     ecx, 10h
0x18005fe10  cmovnz  rdi, rdx
0x18005fe14  movups  [rbp+70h+var_58], xmm0
0x18005fe18  movups  [rbp+70h+Buf1], xmm1
0x18005fe1c  nop     dword ptr [rax+00h]
0x18005fe20  mov     byte ptr [rax], 0
0x18005fe23  lea     rax, [rax+1]
0x18005fe27  sub     rcx, 1
0x18005fe2b  jnz     short loc_18005FE20
0x18005fe2d  xorps   xmm0, xmm0
0x18005fe30  mov     dword ptr [rbp+70h+var_90+4], edx
0x18005fe33  movups  [rbp+70h+var_90], xmm0
0x18005fe37  mov     ecx, 10h
0x18005fe3c  lea     rax, [rbp+70h+Buf1]
0x18005fe40  mov     byte ptr [rax], 0
0x18005fe43  lea     rax, [rax+1]
0x18005fe47  sub     rcx, 1
0x18005fe4b  jnz     short loc_18005FE40
0x18005fe4d  lea     rdx, [rbp+70h+var_90]
0x18005fe51  mov     ecx, esi
0x18005fe53  call    cs:__imp_EtwEventActivityIdControl
0x18005fe59  test    eax, eax
0x18005fe5b  jle     short loc_18005FE67
0x18005fe5d  movzx   eax, ax
0x18005fe60  or      eax, 80070000h
0x18005fe65  test    eax, eax
0x18005fe67  js      loc_180060529
0x18005fe6d  movaps  xmm0, [rbp+70h+var_90]
0x18005fe71  movdqa  [rbp+70h+Buf1], xmm0
0x18005fe76  test    rdi, rdi
0x18005fe79  jz      loc_18005FFAF
0x18005fe7f  test    r14d, r14d
0x18005fe82  jnz     loc_180060535
0x18005fe88  mov     rdx, rdi
0x18005fe8b  mov     dword ptr [rbp+70h+var_90+4], 0
0x18005fe92  mov     ecx, 2
0x18005fe97  call    cs:__imp_EtwEventActivityIdControl
0x18005fe9d  test    eax, eax
0x18005fe9f  jle     short loc_18005FEAB
0x18005fea1  movzx   eax, ax
0x18005fea4  or      eax, 80070000h
0x18005fea9  test    eax, eax
0x18005feab  js      loc_180060564
0x18005feb1  test    r12d, r12d
0x18005feb4  jnz     loc_1800602D5
0x18005feba  mov     r12, [rsp+170h+var_118]
0x18005febf  movaps  xmm0, [rbp+70h+Buf1]
0x18005fec3  mov     [rbp+70h+var_60], esi
0x18005fec6  movups  [rbp+70h+var_70], xmm0
0x18005feca  test    r12, r12
0x18005fecd  jnz     loc_180060570
0x18005fed3  mov     ebx, [rsp+170h+var_110]
0x18005fed7  test    ebx, ebx
0x18005fed9  jz      short loc_18005FEFF
0x18005fedb  mov     rcx, [r15+48h]
0x18005fedf  test    rcx, rcx
0x18005fee2  jz      loc_1800600A7
0x18005fee8  mov     rax, [rcx]
0x18005feeb  mov     rax, [rax+80h]
0x18005fef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fef7  mov     r12, rax
0x18005fefa  mov     [rsp+170h+var_118], rax
0x18005feff  lea     rax, [rbp+70h+var_A0]
0x18005ff03  mov     rdx, r13; struct _INTERNET_THREAD_INFO *
0x18005ff06  lea     r9, [rbp+70h+var_48]; void *
0x18005ff0a  mov     [rsp+170h+var_150], rax; unsigned int *
0x18005ff0f  lea     r8, [rbp+70h+var_9C]; unsigned int *
0x18005ff13  mov     rcx, r15; this
0x18005ff16  call    ?Run@CFsm@@QEAAKPEAU_INTERNET_THREAD_INFO@@PEAKPEAX1@Z; CFsm::Run(_INTERNET_THREAD_INFO *,ulong *,void *,ulong *)
0x18005ff1b  mov     esi, eax
0x18005ff1d  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005ff24  jnz     loc_180060585
0x18005ff2a  cmp     esi, 3E5h
0x18005ff30  jz      loc_18005FFE5
0x18005ff36  mov     r15, [r13+50h]
0x18005ff3a  lea     r14, [rbp+70h+var_48]
0x18005ff3e  mov     rdi, [r13+38h]
0x18005ff42  test    r15, r15
0x18005ff45  jz      loc_18006023A
0x18005ff4b  test    ebx, ebx
0x18005ff4d  jnz     loc_180060472
0x18005ff53  call    cs:__imp_GetLastError
0x18005ff59  cmp     cs:qword_180269EA8, 0
0x18005ff61  mov     esi, 1
0x18005ff66  mov     edi, eax
0x18005ff68  jz      short loc_18005FF72
0x18005ff6a  test    eax, eax
0x18005ff6c  jnz     loc_1800600B4
0x18005ff72  cmp     [rbp+70h+var_60], 0
0x18005ff76  jz      short loc_18005FFA2
0x18005ff78  lea     rdx, [rbp+70h+var_70]
0x18005ff7c  mov     dword ptr [rbp+70h+var_90+4], 0
0x18005ff83  mov     ecx, 2
0x18005ff88  call    cs:__imp_EtwEventActivityIdControl
0x18005ff8e  test    eax, eax
0x18005ff90  jle     short loc_18005FF9C
0x18005ff92  movzx   eax, ax
0x18005ff95  or      eax, 80070000h
0x18005ff9a  test    eax, eax
0x18005ff9c  js      loc_1800605CF
0x18005ffa2  mov     ecx, edi; dwErrCode
0x18005ffa4  call    cs:__imp_SetLastError
0x18005ffaa  jmp     loc_18005FD66
0x18005ffaf  mov     rdi, [rbp+78h]
0x18005ffb3  lock xadd cs:?g_dwActivityIdCount@@3KC, esi; ulong volatile g_dwActivityIdCount
0x18005ffbb  inc     esi
0x18005ffbd  call    cs:__imp_GetTickCount
0x18005ffc3  mov     ebx, eax
0x18005ffc5  call    cs:__imp_GetCurrentProcessId
0x18005ffcb  mov     dword ptr [rbp+70h+var_58], edi
0x18005ffce  lea     rdi, [rbp+70h+var_58]
0x18005ffd2  mov     dword ptr [rbp+70h+var_58+4], esi
0x18005ffd5  mov     esi, 1
0x18005ffda  mov     dword ptr [rbp+70h+var_58+0Ch], eax
0x18005ffdd  mov     dword ptr [rbp+70h+var_58+8], ebx
0x18005ffe0  jmp     loc_18005FE7F
0x18005ffe5  mov     r15d, 1
0x18005ffeb  mov     r14, [rsp+170h+arg_18]
0x18005fff3  test    r12, r12
0x18005fff6  jnz     loc_180060609
0x18005fffc  mov     dword ptr [r13+40h], 0
0x180060004  call    cs:__imp_GetLastError
0x18006000a  cmp     cs:qword_180269EA8, 0
0x180060012  mov     edi, eax
0x180060014  mov     r12, [rsp+170h+arg_10]
0x18006001c  jz      short loc_180060026
0x18006001e  test    eax, eax
0x180060020  jnz     loc_1800601C8
0x180060026  cmp     [rbp+70h+var_60], 0
0x18006002a  jz      short loc_180060056
0x18006002c  lea     rdx, [rbp+70h+var_70]
0x180060030  mov     dword ptr [rbp+70h+var_90+4], 0
0x180060037  mov     ecx, 2
0x18006003c  call    cs:__imp_EtwEventActivityIdControl
0x180060042  test    eax, eax
0x180060044  jle     short loc_180060050
0x180060046  movzx   eax, ax
0x180060049  or      eax, 80070000h
0x18006004e  test    eax, eax
0x180060050  js      loc_180060616
0x180060056  mov     ecx, edi; dwErrCode
0x180060058  call    cs:__imp_SetLastError
0x18006005e  test    byte ptr cs:xmmword_180266B60+1, 2
0x180060065  jnz     loc_180060622
0x18006006b  lea     rcx, [rsp+170h+var_100]
0x180060070  call    InternetRestoreThreadInfo
0x180060075  xor     eax, eax
0x180060077  cmp     [rsp+170h+var_10C], eax
0x18006007b  setnz   al
0x18006007e  mov     [r13+48h], eax
0x180060082  mov     eax, esi
0x180060084  mov     rbx, [rsp+170h+arg_8]
0x18006008c  mov     rcx, [rbp+70h+var_28]
0x180060090  xor     rcx, rsp; StackCookie
0x180060093  call    __security_check_cookie
0x180060098  add     rsp, 150h
0x18006009f  pop     r15
0x1800600a1  pop     r13
0x1800600a3  pop     rdi
0x1800600a4  pop     rsi
0x1800600a5  pop     rbp
0x1800600a6  retn
0x1800600a7  xor     r12d, r12d
0x1800600aa  mov     [rsp+170h+var_118], r12
0x1800600af  jmp     loc_18005FEFF
0x1800600b4  cmp     edi, 3E5h
0x1800600ba  jz      loc_18005FF72
0x1800600c0  cmp     edi, 2F76h
0x1800600c6  jz      loc_18005FF72
0x1800600cc  cmp     edi, 2EFCh
0x1800600d2  jz      loc_18005FF72
0x1800600d8  cmp     edi, 7Ah ; 'z'
0x1800600db  jz      loc_18005FF72
0x1800600e1  mov     eax, esi
0x1800600e3  lock xadd cs:dword_180269EA4, eax
0x1800600eb  mov     rcx, cs:qword_180269EA8
0x1800600f2  inc     eax
0x1800600f4  movzx   ebx, al
0x1800600f7  shl     rbx, 4
0x1800600fb  add     rcx, rbx; lpSystemTimeAsFileTime
0x1800600fe  call    cs:__imp_GetSystemTimeAsFileTime
0x180060104  mov     rax, cs:qword_180269EA8
0x18006010b  mov     [rbx+rax+8], edi
0x18006010f  call    cs:__imp_RtlGetLastNtStatus
0x180060115  mov     rcx, cs:qword_180269EA8
0x18006011c  mov     [rbx+rcx+0Ch], eax
0x180060120  jmp     loc_18005FF72
0x180060125  mov     rcx, [r15+40h]
0x180060129  test    rcx, rcx
0x18006012c  jnz     loc_180060452
0x180060132  test    bl, 20h
0x180060135  jnz     loc_180060514
0x18006013b  mov     rax, [r15+20h]
0x18006013f  test    rax, rax
0x180060142  jz      loc_18005FDD3
0x180060148  movups  xmm0, xmmword ptr [rax+0ACh]
0x18006014f  movups  xmmword ptr [rdi], xmm0
0x180060152  jmp     loc_18005FDD6
0x180060157  cmp     edi, 3E5h
0x18006015d  jz      loc_18005FCEE
0x180060163  cmp     edi, 2F76h
0x180060169  jz      loc_18005FCEE
0x18006016f  cmp     edi, 2EFCh
0x180060175  jz      loc_18005FCEE
  ... truncated ...
```
