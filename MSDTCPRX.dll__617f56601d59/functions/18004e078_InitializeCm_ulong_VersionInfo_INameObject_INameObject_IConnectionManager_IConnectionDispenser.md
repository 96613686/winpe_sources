# InitializeCm(ulong,_VersionInfo,INameObject *,INameObject *,IConnectionManager * *,IConnectionDispenser * *)

- ea: `0x18004e078`
- end: `0x18004e772`
- name: `?InitializeCm@@YAJKU_VersionInfo@@PEAUINameObject@@1PEAPEAUIConnectionManager@@PEAPEAUIConnectionDispenser@@@Z`
- size: `1786`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019310`
- `0x180022928`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x18000f8d0`
- `0x180013140`
- `0x18001d138`
- `0x18004dce8`
- `0x18004dd04`
- `0x18004e078`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e752`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e752`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e182`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e2a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e235`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004e235`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e29e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e65b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e29e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004e65b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e24b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004e24b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e6af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e6af`

## string_xrefs

- `0x18004e120`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x18004e1c8`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x18004e25e`: `com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp`
- `0x18004e291`: `Call to OpenThreadToken Failed`
- `0x18004e2c3`: `Call to SetThreadToken Failed`
- `0x18004e680`: `Call to SetThreadToken Failed`
- `0x18004e68f`: `ReImpersonateIfNecessary`
- `0x18004e6b9`: `ReImpersonateIfNecessary failed`
- `0x18004e0b7`: `InitializeCm (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@434): InitalizeCm - NULL != o_ppConnMgr`
- `0x18004e0cd`: `InitializeCm (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@435): InitalizeCm - NULL != o_ppConnDisp`
- `0x18004e0f6`: `InitializeCm (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@442): InitializeCm - NULL != g_pIConnDisp`
- `0x18004e108`: `Global variables already initialized, returning`
- `0x18004e19e`: `InitializeCm (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@455): InitializeCm - NULL != g_pIConnDisp`
- `0x18004e1b0`: `Global variables already initialized after getting lock, returning`
- `0x18004e360`: `DllGetDTCConnectionManager failed.`
- `0x18004e395`: `QueryInterface for IID_IConnectionManagerConfig2 failed.`
- `0x18004e53b`: `CConnectionManagerConfig::SetPhaseToPostInit failed.`
- `0x18004e5c6`: `InitializeCm (com\complus\dtc\dtc\msdtcprx\src\cmutil.cpp@618): InitializeCm - Before return - NULL != g_pIConnDisp`
- `0x18004e6e4`: `ReImpersonateIfNecessary failed in CITmProxyInit::InitCm`

## pseudocode

```c
__int64 __fastcall InitializeCm(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5, _QWORD *a6)
{
  bool v7; // zf
  struct IConnectionDispenser *v8; // rcx
  signed int DTCConnectionManager; // edi
  struct IConnectionDispenser *v11; // rcx
  struct IConnectionManager *v12; // r14
  struct IConnectionManager *v13; // rsi
  HANDLE CurrentThread; // rax
  signed int v15; // eax
  __int64 v16; // r9
  const wchar_t *v17; // r10
  signed int LastError; // eax
  const wchar_t *v19; // rax
  __int64 v20; // r9
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rcx
  unsigned int DTCRegistryInt; // edi
  struct IConnectionManager *v24; // rcx
  void (__fastcall *v25)(struct IConnectionManager *, __int64); // rax
  __int64 v26; // rdx
  CPrxImpIConnectionNotify *v27; // rax
  CPrxImpIConnectionNotify *v28; // rax
  CPrxImpIConnectionNotify *v29; // rbx
  const wchar_t *v30; // rax
  __int64 v31; // r9
  struct IConnectionManager *v32; // rcx
  signed int v33; // ebx
  signed int v34; // eax
  __int64 v35; // [rsp+28h] [rbp-48h]
  bool v36[4]; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-2Ch] BYREF
  struct IConnectionDispenser *v38; // [rsp+48h] [rbp-28h] BYREF
  struct IConnectionManager *v39; // [rsp+50h] [rbp-20h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-18h]
  void *TokenHandle; // [rsp+60h] [rbp-10h] BYREF
  CPrxImpIConnectionNotify *v42; // [rsp+68h] [rbp-8h]

  v39 = 0;
  v38 = 0;
  v37 = 0;
  if ( !a5 )
    DtcInternalErrorW(L"InitializeCm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@434): InitalizeCm - NULL != o_ppConnMgr");
  if ( !a6 )
    DtcInternalErrorW(L"InitializeCm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@435): InitalizeCm - NULL != o_ppConnDisp");
  v7 = g_pIConnMgr == 0;
  *a5 = 0;
  *a6 = 0;
  if ( !v7 )
  {
    if ( !g_pIConnDisp )
      DtcInternalErrorW(L"InitializeCm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@442): InitializeCm - NULL != g_pIConnDisp");
    TraceStringInline(
      15,
      4,
      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
      443,
      L"InitializeCm",
      0,
      L"Global variables already initialized, returning");
    (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)g_pIConnMgr + 8LL))(g_pIConnMgr);
    v8 = g_pIConnDisp;
    *a5 = g_pIConnMgr;
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v8 + 8LL))(v8);
    *a6 = g_pIConnDisp;
    return 0;
  }
  EnterCriticalSection(&stru_1800D5F88);
  if ( !g_pIConnMgr )
  {
    v12 = 0;
    v42 = 0;
    v13 = 0;
    TokenHandle = 0;
    DTCConnectionManager = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( SetThreadToken(0, 0) )
        goto LABEL_26;
      LastError = GetLastError();
      DTCConnectionManager = LastError;
      if ( LastError > 0 )
        DTCConnectionManager = (unsigned __int16)LastError | 0x80070000;
      v16 = 66;
      v17 = L"Call to SetThreadToken Failed";
    }
    else
    {
      v15 = GetLastError();
      if ( v15 == 1008 )
        goto LABEL_26;
      if ( v15 > 0 )
        DTCConnectionManager = (unsigned __int16)v15 | 0x80070000;
      else
        DTCConnectionManager = v15;
      v16 = 55;
      v17 = L"Call to OpenThreadToken Failed";
    }
    LODWORD(v35) = DTCConnectionManager;
    TraceStringInline(15, 1, L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp", v16, L"RevertIfNecessary", v35, v17);
    if ( DTCConnectionManager < 0 )
    {
      Token = TokenHandle;
      if ( TokenHandle )
      {
        CloseHandle(TokenHandle);
        Token = 0;
        goto LABEL_28;
      }
LABEL_27:
      if ( DTCConnectionManager >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a4 + 40LL))(a4, &v37);
        DTCConnectionManager = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, &v39);
        if ( DTCConnectionManager )
        {
          v19 = L"DllGetDTCConnectionManager failed.";
          v20 = 488;
          goto LABEL_57;
        }
        v12 = v39;
        DTCConnectionManager = (**(__int64 (__fastcall ***)(struct IConnectionManager *, GUID *, struct IConnectionManager **))v39)(
                                 v39,
                                 &IID_IConnectionManagerConfig2,
                                 &v39);
        if ( DTCConnectionManager )
        {
          v19 = L"QueryInterface for IID_IConnectionManagerConfig2 failed.";
          v20 = 499;
          goto LABEL_57;
        }
        v13 = v39;
        v36[0] = 0;
        DTCRegistryInt = GetDTCRegistryInt(v22, v21);
        MtxCluIsClusterPresentNonAdmin(0, v36);
        if ( v36[0] || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 56LL))(a4) )
        {
          v36[0] = 0;
          MtxCluIsClusterPresentNonAdmin(0, v36);
          v26 = v37;
          if ( v36[0] )
          {
            v26 = v37 | 1;
            v37 |= 1u;
          }
          v24 = v13;
          v25 = *(void (__fastcall **)(struct IConnectionManager *, __int64))(*(_QWORD *)v13 + 120LL);
        }
        else
        {
          v24 = v13;
          v25 = *(void (__fastcall **)(struct IConnectionManager *, __int64))(*(_QWORD *)v13 + 120LL);
          if ( DTCRegistryInt )
            v26 = 33;
          else
            v26 = 32;
        }
        v25(v24, v26);
        (*(void (__fastcall **)(struct IConnectionManager *, __int64))(*(_QWORD *)v13 + 136LL))(v13, a2);
        (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v13 + 104LL))(v13);
        (*(void (__fastcall **)(struct IConnectionManager *, __int64))(*(_QWORD *)v13 + 72LL))(v13, 1);
        (*(void (__fastcall **)(struct IConnectionManager *, __int64))(*(_QWORD *)v13 + 40LL))(v13, 100);
        v27 = (CPrxImpIConnectionNotify *)operator new(0x10u);
        v42 = v27;
        if ( v27 )
        {
          v28 = CPrxImpIConnectionNotify::CPrxImpIConnectionNotify(v27);
          v42 = v28;
          v29 = v28;
          if ( v28 )
          {
            (*(void (__fastcall **)(CPrxImpIConnectionNotify *))(*(_QWORD *)v28 + 8LL))(v28);
            DTCConnectionManager = (*(__int64 (__fastcall **)(struct IConnectionManager *, __int64, CPrxImpIConnectionNotify *, _QWORD))(*(_QWORD *)v12 + 24LL))(
                                     v12,
                                     a3,
                                     v29,
                                     0);
            if ( DTCConnectionManager )
            {
              v19 = L"CConnectionManager::Init failed.";
              v20 = 569;
            }
            else
            {
              DTCConnectionManager = (*(__int64 (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v12 + 32LL))(v12);
              if ( !DTCConnectionManager )
              {
                DTCConnectionManager = (*(__int64 (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v13 + 24LL))(v13);
                (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v13 + 16LL))(v13);
                v13 = 0;
                if ( DTCConnectionManager )
                {
                  v30 = L"CConnectionManagerConfig::SetPhaseToPostInit failed.";
                  v31 = 588;
                }
                else
                {
                  DTCConnectionManager = (**(__int64 (__fastcall ***)(struct IConnectionManager *, GUID *, struct IConnectionDispenser **))v12)(
                                           v12,
                                           &IID_IConnectionDispenser,
                                           &v38);
                  if ( !DTCConnectionManager )
                  {
                    v32 = v12;
                    g_pIConnMgr = v12;
                    g_pIConnDisp = v38;
                    v38 = 0;
                    if ( !g_pIConnDisp )
                      DtcInternalErrorW(
                        L"InitializeCm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@618): InitializeCm - Before retu"
                         "rn - NULL != g_pIConnDisp");
                    v12 = 0;
                    (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v32 + 8LL))(v32);
                    *a5 = g_pIConnMgr;
                    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)g_pIConnDisp + 8LL))(g_pIConnDisp);
                    *a6 = g_pIConnDisp;
                    goto LABEL_58;
                  }
                  v30 = L"QueryInterface for IID_IConnectionDispenser failed.";
                  v31 = 604;
                }
                LODWORD(v35) = DTCConnectionManager;
                TraceStringInline(
                  15,
                  1,
                  L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
                  v31,
                  L"InitializeCm",
                  v35,
                  v30);
                (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v12 + 40LL))(v12);
LABEL_58:
                if ( Token )
                {
                  v33 = 0;
                  if ( !SetThreadToken(0, Token) )
                  {
                    v34 = GetLastError();
                    v33 = v34;
                    if ( v34 > 0 )
                      v33 = (unsigned __int16)v34 | 0x80070000;
                    LODWORD(v35) = v33;
                    TraceStringInline(
                      15,
                      1,
                      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
                      119,
                      L"ReImpersonateIfNecessary",
                      v35,
                      L"Call to SetThreadToken Failed");
                  }
                  CloseHandle(Token);
                  if ( v33 < 0 )
                  {
                    LODWORD(v35) = v33;
                    TraceStringInline(
                      15,
                      1,
                      L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
                      629,
                      L"InitializeCm",
                      v35,
                      L"ReImpersonateIfNecessary failed");
                    DtcInternalErrorW(L"ReImpersonateIfNecessary failed in CITmProxyInit::InitCm");
                  }
                }
                if ( v13 )
                  (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v13 + 16LL))(v13);
                if ( v42 )
                  (*(void (__fastcall **)(CPrxImpIConnectionNotify *))(*(_QWORD *)v42 + 16LL))(v42);
                if ( v12 )
                  (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v12 + 16LL))(v12);
                goto LABEL_71;
              }
              v19 = L"CConnectionManager::StartListening failed.";
              v20 = 577;
            }
LABEL_57:
            LODWORD(v35) = DTCConnectionManager;
            TraceStringInline(
              15,
              1,
              L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
              v20,
              L"InitializeCm",
              v35,
              v19);
            goto LABEL_58;
          }
        }
        else
        {
          v42 = 0;
        }
        DTCConnectionManager = -2147024882;
        v19 = L"Unable to allocate memory for CPrxImpIConnectionNotify.";
        v20 = 559;
        goto LABEL_57;
      }
LABEL_28:
      v19 = L"RevertIfNecessary failed";
      v20 = 474;
      goto LABEL_57;
    }
LABEL_26:
    Token = TokenHandle;
    goto LABEL_27;
  }
  if ( !g_pIConnDisp )
    DtcInternalErrorW(L"InitializeCm (com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp@455): InitializeCm - NULL != g_pIConnDisp");
  DTCConnectionManager = 0;
  TraceStringInline(
    15,
    4,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\cmutil.cpp",
    456,
    L"InitializeCm",
    0,
    L"Global variables already initialized after getting lock, returning");
  (*(void (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)g_pIConnMgr + 8LL))(g_pIConnMgr);
  v11 = g_pIConnDisp;
  *a5 = g_pIConnMgr;
  (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v11 + 8LL))(v11);
  *a6 = g_pIConnDisp;
LABEL_71:
  if ( v38 )
  {
    (*(void (__fastcall **)(struct IConnectionDispenser *))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  LeaveCriticalSection(&stru_1800D5F88);
  return (unsigned int)DTCConnectionManager;
}

```

## disassembly

```asm
0x18004e078  mov     rax, rsp
0x18004e07b  mov     [rax+10h], rbx
0x18004e07f  mov     [rax+20h], r9
0x18004e083  mov     [rax+18h], r8
0x18004e087  mov     [rax+8], ecx
0x18004e08a  push    rbp
0x18004e08b  push    rsi
0x18004e08c  push    rdi
0x18004e08d  push    r12
0x18004e08f  push    r13
0x18004e091  push    r14
0x18004e093  push    r15
0x18004e095  mov     rbp, rsp
0x18004e098  sub     rsp, 70h
0x18004e09c  mov     r14, [rbp+arg_20]
0x18004e0a0  xor     r15d, r15d
0x18004e0a3  mov     [rbp+var_20], r15
0x18004e0a7  mov     rbx, rdx
0x18004e0aa  mov     [rbp+var_28], r15
0x18004e0ae  mov     [rbp+var_2C], r15d
0x18004e0b2  test    r14, r14
0x18004e0b5  jnz     short loc_18004E0C4
0x18004e0b7  lea     rcx, aInitializecmCo_2; "InitializeCm (com\\complus\\dtc\\dtc\\m"...
0x18004e0be  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004e0c4  mov     rsi, [rbp+arg_28]
0x18004e0c8  test    rsi, rsi
0x18004e0cb  jnz     short loc_18004E0DA
0x18004e0cd  lea     rcx, aInitializecmCo_1; "InitializeCm (com\\complus\\dtc\\dtc\\m"...
0x18004e0d4  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004e0da  cmp     cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA, r15; IConnectionManager * g_pIConnMgr
0x18004e0e1  mov     [r14], r15
0x18004e0e4  mov     [rsi], r15
0x18004e0e7  jz      loc_18004E17B
0x18004e0ed  cmp     cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA, r15; IConnectionDispenser * g_pIConnDisp
0x18004e0f4  jnz     short loc_18004E103
0x18004e0f6  lea     rcx, aInitializecmCo_0; "InitializeCm (com\\complus\\dtc\\dtc\\m"...
0x18004e0fd  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004e103  mov     edx, 4
0x18004e108  lea     rax, aGlobalVariable_0; "Global variables already initialized, r"...
0x18004e10f  mov     [rsp+70h+var_40], rax
0x18004e114  lea     r13, aInitializecm; "InitializeCm"
0x18004e11b  mov     [rsp+70h+var_48], r15
0x18004e120  lea     r8, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004e127  mov     r9d, 1BBh
0x18004e12d  mov     [rsp+70h+var_50], r13
0x18004e132  lea     ecx, [rdx+0Bh]
0x18004e135  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004e13a  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x18004e141  mov     rax, [rcx]
0x18004e144  mov     rax, [rax+8]
0x18004e148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e14d  mov     rax, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x18004e154  mov     rcx, cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA; IConnectionDispenser * g_pIConnDisp
0x18004e15b  mov     [r14], rax
0x18004e15e  mov     rax, [rcx]
0x18004e161  mov     rax, [rax+8]
0x18004e165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e16a  mov     rax, cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA; IConnectionDispenser * g_pIConnDisp
0x18004e171  mov     [rsi], rax
0x18004e174  xor     eax, eax
0x18004e176  jmp     loc_18004E75A
0x18004e17b  lea     rcx, stru_1800D5F88; lpCriticalSection
0x18004e182  call    cs:__imp_EnterCriticalSection
0x18004e188  cmp     cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA, r15; IConnectionManager * g_pIConnMgr
0x18004e18f  jz      loc_18004E224
0x18004e195  cmp     cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA, r15; IConnectionDispenser * g_pIConnDisp
0x18004e19c  jnz     short loc_18004E1AB
0x18004e19e  lea     rcx, aInitializecmCo; "InitializeCm (com\\complus\\dtc\\dtc\\m"...
0x18004e1a5  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18004e1ab  mov     edx, 4
0x18004e1b0  lea     rax, aGlobalVariable; "Global variables already initialized af"...
0x18004e1b7  mov     [rsp+70h+var_40], rax
0x18004e1bc  lea     r13, aInitializecm; "InitializeCm"
0x18004e1c3  mov     [rsp+70h+var_48], r15
0x18004e1c8  lea     r8, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004e1cf  mov     r9d, 1C8h
0x18004e1d5  mov     [rsp+70h+var_50], r13
0x18004e1da  lea     ecx, [rdx+0Bh]
0x18004e1dd  mov     edi, r15d
0x18004e1e0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004e1e5  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x18004e1ec  mov     rax, [rcx]
0x18004e1ef  mov     rax, [rax+8]
0x18004e1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e1f8  mov     rax, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x18004e1ff  mov     rcx, cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA; IConnectionDispenser * g_pIConnDisp
0x18004e206  mov     [r14], rax
0x18004e209  mov     rax, [rcx]
0x18004e20c  mov     rax, [rax+8]
0x18004e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e215  mov     rax, cs:?g_pIConnDisp@@3PEAUIConnectionDispenser@@EA; IConnectionDispenser * g_pIConnDisp
0x18004e21c  mov     [rsi], rax
0x18004e21f  jmp     loc_18004E72E
0x18004e224  mov     r14, r15
0x18004e227  mov     [rbp+var_8], r15
0x18004e22b  mov     rsi, r15
0x18004e22e  mov     [rbp+TokenHandle], r15
0x18004e232  mov     edi, r15d
0x18004e235  call    cs:__imp_GetCurrentThread
0x18004e23b  mov     edx, 4; DesiredAccess
0x18004e240  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004e244  mov     rcx, rax; ThreadHandle
0x18004e247  lea     r8d, [rdx-3]; OpenAsSelf
0x18004e24b  call    cs:__imp_OpenThreadToken
0x18004e251  lea     r13, aInitializecm; "InitializeCm"
0x18004e258  mov     r12d, 0Fh
0x18004e25e  lea     r15, aComComplusDtcD; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18004e265  test    eax, eax
0x18004e267  jnz     short loc_18004E29A
0x18004e269  call    cs:__imp_GetLastError
0x18004e26f  cmp     eax, 3F0h
0x18004e274  jz      loc_18004E311
0x18004e27a  test    eax, eax
0x18004e27c  jg      short loc_18004E282
0x18004e27e  mov     edi, eax
0x18004e280  jmp     short loc_18004E28B
0x18004e282  movzx   edi, ax
0x18004e285  or      edi, 80070000h
0x18004e28b  mov     r9d, 37h ; '7'
0x18004e291  lea     r10, aCallToOpenthre; "Call to OpenThreadToken Failed"
0x18004e298  jmp     short loc_18004E2CA
0x18004e29a  xor     edx, edx; Token
0x18004e29c  xor     ecx, ecx; Thread
0x18004e29e  call    cs:__imp_SetThreadToken
0x18004e2a4  test    eax, eax
0x18004e2a6  jnz     short loc_18004E311
0x18004e2a8  call    cs:__imp_GetLastError
0x18004e2ae  mov     edi, eax
0x18004e2b0  test    eax, eax
0x18004e2b2  jle     short loc_18004E2BD
0x18004e2b4  movzx   edi, ax
0x18004e2b7  or      edi, 80070000h
0x18004e2bd  mov     r9d, 42h ; 'B'
0x18004e2c3  lea     r10, aCallToSetthrea; "Call to SetThreadToken Failed"
0x18004e2ca  lea     rax, aRevertifnecess; "RevertIfNecessary"
0x18004e2d1  mov     r8, r15
0x18004e2d4  mov     dl, 1
0x18004e2d6  mov     ecx, r12d
0x18004e2d9  mov     [rsp+70h+var_40], r10
0x18004e2de  mov     dword ptr [rsp+70h+var_48], edi
0x18004e2e2  movzx   edx, dl
0x18004e2e5  mov     [rsp+70h+var_50], rax
0x18004e2ea  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18004e2ef  test    edi, edi
0x18004e2f1  jns     short loc_18004E311
0x18004e2f3  mov     rax, [rbp+TokenHandle]
0x18004e2f7  mov     [rbp+Token], rax
0x18004e2fb  test    rax, rax
0x18004e2fe  jz      short loc_18004E319
0x18004e300  mov     rcx, rax; hObject
0x18004e303  call    cs:__imp_CloseHandle
0x18004e309  xor     ecx, ecx
0x18004e30b  mov     [rbp+Token], rcx
0x18004e30f  jmp     short loc_18004E31D
0x18004e311  mov     rcx, [rbp+TokenHandle]
0x18004e315  mov     [rbp+Token], rcx
0x18004e319  test    edi, edi
0x18004e31b  jns     short loc_18004E32F
0x18004e31d  lea     rax, aRevertifnecess_0; "RevertIfNecessary failed"
0x18004e324  mov     r9d, 1DAh
0x18004e32a  jmp     loc_18004E629
0x18004e32f  mov     rcx, [rbp+arg_18]
0x18004e333  lea     rdx, [rbp+var_2C]
0x18004e337  mov     rax, [rcx]
0x18004e33a  mov     rax, [rax+28h]
0x18004e33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e343  lea     r8, [rbp+var_20]
0x18004e347  lea     rdx, IID_IConnectionManager
0x18004e34e  lea     rcx, CLSID_DTCCM
0x18004e355  call    DllGetDTCConnectionManager
0x18004e35a  mov     edi, eax
0x18004e35c  test    eax, eax
0x18004e35e  jz      short loc_18004E372
0x18004e360  lea     rax, aDllgetdtcconne_0; "DllGetDTCConnectionManager failed."
0x18004e367  mov     r9d, 1E8h
0x18004e36d  jmp     loc_18004E629
0x18004e372  mov     r14, [rbp+var_20]
0x18004e376  lea     r8, [rbp+var_20]
0x18004e37a  lea     rdx, IID_IConnectionManagerConfig2
0x18004e381  mov     rcx, r14
0x18004e384  mov     rax, [r14]
0x18004e387  mov     rax, [rax]
0x18004e38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e38f  mov     edi, eax
0x18004e391  test    eax, eax
0x18004e393  jz      short loc_18004E3A7
0x18004e395  lea     rax, aQueryinterface; "QueryInterface for IID_IConnectionManag"...
0x18004e39c  mov     r9d, 1F3h
0x18004e3a2  jmp     loc_18004E629
0x18004e3a7  mov     rsi, [rbp+var_20]
0x18004e3ab  call    ?GetDTCRegistryInt@@YAKPEBGK@Z; GetDTCRegistryInt(ushort const *,ulong)
0x18004e3b0  lea     rdx, [rbp+var_30]; bool *
0x18004e3b4  mov     [rbp+var_30], 0
0x18004e3b8  xor     ecx, ecx; unsigned __int16 *
0x18004e3ba  mov     edi, eax
0x18004e3bc  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18004e3c1  cmp     [rbp+var_30], 0
0x18004e3c5  jnz     short loc_18004E3FA
0x18004e3c7  mov     rdx, [rbp+arg_18]
0x18004e3cb  mov     rcx, [rdx]
0x18004e3ce  mov     rax, [rcx+38h]
0x18004e3d2  mov     rcx, rdx
0x18004e3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3da  test    eax, eax
0x18004e3dc  jz      short loc_18004E3FA
0x18004e3de  mov     rax, [rsi]
0x18004e3e1  mov     rcx, rsi
0x18004e3e4  mov     rax, [rax+78h]
0x18004e3e8  test    edi, edi
0x18004e3ea  jz      short loc_18004E3F3
0x18004e3ec  mov     edx, 21h ; '!'
0x18004e3f1  jmp     short loc_18004E422
0x18004e3f3  mov     edx, 20h ; ' '
0x18004e3f8  jmp     short loc_18004E422
0x18004e3fa  lea     rdx, [rbp+var_30]; bool *
0x18004e3fe  mov     [rbp+var_30], 0
0x18004e402  xor     ecx, ecx; unsigned __int16 *
0x18004e404  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x18004e409  cmp     [rbp+var_30], 0
0x18004e40d  mov     edx, [rbp+var_2C]
0x18004e410  jz      short loc_18004E418
0x18004e412  or      edx, 1
0x18004e415  mov     [rbp+var_2C], edx
0x18004e418  mov     rax, [rsi]
0x18004e41b  mov     rcx, rsi
0x18004e41e  mov     rax, [rax+78h]
0x18004e422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e427  mov     rax, [rsi]
0x18004e42a  mov     rdx, rbx
0x18004e42d  mov     rcx, rsi
0x18004e430  mov     rax, [rax+88h]
0x18004e437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e43c  mov     rax, [rsi]
0x18004e43f  mov     rcx, rsi
0x18004e442  mov     edx, [rbp+arg_0]
0x18004e445  mov     rax, [rax+68h]
0x18004e449  test    edx, edx
0x18004e44b  jnz     short loc_18004E452
0x18004e44d  mov     edx, 0Ah
0x18004e452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e457  mov     rax, [rsi]
0x18004e45a  mov     edx, 1
0x18004e45f  mov     rcx, rsi
0x18004e462  mov     rax, [rax+48h]
0x18004e466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e46b  mov     rax, [rsi]
0x18004e46e  mov     edx, 64h ; 'd'
0x18004e473  mov     rcx, rsi
0x18004e476  mov     rax, [rax+28h]
0x18004e47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e47f  mov     ecx, 10h; Size
0x18004e484  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004e489  mov     [rbp+var_8], rax
0x18004e48d  test    rax, rax
0x18004e490  jz      loc_18004E613
0x18004e496  mov     rcx, rax; this
0x18004e499  call    ??0CPrxImpIConnectionNotify@@QEAA@XZ; CPrxImpIConnectionNotify::CPrxImpIConnectionNotify(void)
0x18004e49e  mov     [rbp+var_8], rax
0x18004e4a2  mov     rbx, rax
0x18004e4a5  test    rax, rax
0x18004e4a8  jz      loc_18004E617
0x18004e4ae  mov     rax, [rax]
0x18004e4b1  mov     rcx, rbx
0x18004e4b4  mov     rax, [rax+8]
0x18004e4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4bd  mov     rax, [r14]
0x18004e4c0  xor     r9d, r9d
0x18004e4c3  mov     rdx, [rbp+arg_10]
0x18004e4c7  mov     r8, rbx
0x18004e4ca  mov     rcx, r14
0x18004e4cd  mov     rax, [rax+18h]
0x18004e4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4d6  mov     edi, eax
0x18004e4d8  test    eax, eax
0x18004e4da  jz      short loc_18004E4EE
0x18004e4dc  lea     rax, aCconnectionman_1; "CConnectionManager::Init failed."
0x18004e4e3  mov     r9d, 239h
0x18004e4e9  jmp     loc_18004E629
0x18004e4ee  mov     rax, [r14]
0x18004e4f1  mov     rcx, r14
0x18004e4f4  mov     rax, [rax+20h]
0x18004e4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4fd  mov     edi, eax
0x18004e4ff  test    eax, eax
0x18004e501  jz      short loc_18004E515
0x18004e503  lea     rax, aCconnectionman_0; "CConnectionManager::StartListening fail"...
0x18004e50a  mov     r9d, 241h
0x18004e510  jmp     loc_18004E629
0x18004e515  mov     rax, [rsi]
0x18004e518  mov     rcx, rsi
0x18004e51b  mov     rax, [rax+18h]
0x18004e51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e524  mov     edi, eax
0x18004e526  mov     rcx, rsi
0x18004e529  mov     rax, [rsi]
0x18004e52c  mov     rax, [rax+10h]
0x18004e530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e535  xor     esi, esi
0x18004e537  test    edi, edi
0x18004e539  jz      short loc_18004E57A
  ... truncated ...
```
