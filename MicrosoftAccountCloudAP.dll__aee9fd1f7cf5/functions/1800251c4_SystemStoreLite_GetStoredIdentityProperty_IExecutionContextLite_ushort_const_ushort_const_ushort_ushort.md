# SystemStoreLite::GetStoredIdentityProperty(IExecutionContextLite *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x1800251c4`
- end: `0x18002586d`
- name: `?GetStoredIdentityProperty@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEBG1PEAPEAG2@Z`
- size: `1705`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180024c50`
- `0x1800250ec`
- `0x180025c08`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180007484`
- `0x180008440`
- `0x18000baac`
- `0x18000d91c`
- `0x18000def8`
- `0x180023b5c`
- `0x180023c04`
- `0x180024ce8`
- `0x1800251c4`
- `0x180025874`
- `0x180025d90`
- `0x1800267c0`
- `0x180026c8c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025665`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800256cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025665`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800256cf`

## string_xrefs

- `0x18002532e`: `hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)`
- `0x1800257ce`: `pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr`
- `0x180025378`: `hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L"%s\\%s", static_cast<LPWSTR>(pSystemSidString), WLID_REG_STORED_IDENTITY )`
- `0x180025787`: `hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L"%s\\%s", currentSubKey, static_cast<LPCWSTR>(pCurrentUserSidString))`
- `0x18002558b`: `SID missing from LiveID key. (win32 = 0x%0x)`
- `0x180025538`: `StringCchPrintf failed for full user SID path. (localHr = 0x%0x)`
- `0x18002569a`: `hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)`
- `0x1800256b4`: `hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)`

## pseudocode

```c
__int64 __fastcall SystemStoreLite::GetStoredIdentityProperty(
        struct IExecutionContextLite *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  __int64 v9; // rdi
  unsigned __int16 *v10; // r14
  int SystemSidString; // eax
  int v12; // eax
  signed int v13; // eax
  unsigned int i; // ebx
  signed int v15; // eax
  int v16; // eax
  signed int v17; // eax
  signed int v18; // eax
  const unsigned __int16 *v19; // r9
  unsigned int v20; // r8d
  unsigned __int8 v21; // cl
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  int v24; // r9d
  __int64 v25; // rbx
  int v26; // eax
  const char *v27; // rax
  unsigned int v28; // r8d
  unsigned __int16 *v29; // rbx
  signed int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdx
  int v33; // r8d
  char *v35; // [rsp+20h] [rbp-E0h]
  char *v36; // [rsp+20h] [rbp-E0h]
  char *v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD uBytes[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h]
  __int64 v44; // [rsp+80h] [rbp-80h]
  _QWORD v45[3]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v46[3]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v47[3]; // [rsp+B8h] [rbp-48h] BYREF
  int *v48[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v49[4]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v50[264]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v51[264]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v52[264]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v53[264]; // [rsp+740h] [rbp+640h] BYREF

  v9 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 8LL))(a1);
  v10 = 0;
  memset(v46, 0, sizeof(v46));
  memset_0(v52, 0, 0x208u);
  memset_0(v50, 0, 0x208u);
  memset_0(v51, 0, 0x208u);
  v45[0] = 0;
  v45[2] = v9;
  v45[1] = 0;
  v42 = 0;
  v44 = 0;
  v43 = 0;
  v41 = 0;
  v40 = 0;
  memset(uBytes, 0, sizeof(uBytes));
  v38 = 0;
  v49[0] = "SystemStoreLite::GetStoredIdentityProperty";
  v49[1] = &v38;
  v49[2] = 1;
  v49[3] = &qword_180040170;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetStoredIdentityProperty",
    (const char *)0x8F,
    0,
    (const unsigned __int16 *)v35);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v48,
    "SystemStoreLite::GetStoredIdentityProperty",
    &v38,
    11,
    &qword_180040178);
  if ( !a2 || !a3 || !a4 )
  {
    v38 = -2147024809;
    v27 = "pContext != nullptr && pCurrentUserSidString != nullptr && pPropertyName != nullptr && ppPropertyValue != nullptr";
    v24 = -2147024809;
    v28 = 153;
LABEL_60:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      v28,
      v24,
      v27);
    goto LABEL_61;
  }
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  SystemSidString = SystemStoreLite::GetSystemSidString(a1, v46);
  v38 = SystemSidString;
  if ( SystemSidString < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xA3u,
      SystemSidString,
      "hr = SystemStoreLite::GetSystemSidString(pContext, &pSystemSidString)");
    goto LABEL_61;
  }
  v12 = StringCchPrintfW(v52, 0x104u, L"%s\\%s", v46[0], L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
  v38 = v12;
  if ( v12 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xACu,
      v12,
      "hr = StringCchPrintfW( storedIdentitiesRegistryPath, MAX_PATH, L\"%s\\\\%s\", static_cast<LPWSTR>(pSystemSidString"
      "), WLID_REG_STORED_IDENTITY )");
    goto LABEL_61;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
          v9,
          -2147483645,
          v52,
          0,
          131097,
          v45);
  if ( v13 == 2 )
  {
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      0xBCu,
      L"System store not found.");
    v38 = -2147023728;
    goto LABEL_61;
  }
  if ( v13 )
  {
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v38 = v13;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0xC1u,
      v13,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_61;
  }
  for ( i = 0; ; ++i )
  {
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *, int))(*(_QWORD *)v9 + 40LL))(
            v9,
            v45[0],
            i,
            v50,
            260);
    if ( v15 == 259 )
    {
      v38 = -2147023728;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        0xD5u,
        L"SystemStore property not found.");
      goto LABEL_61;
    }
    if ( v15 )
    {
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      v38 = v15;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xD9u,
        v15,
        "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
      goto LABEL_61;
    }
    v16 = StringCchPrintfW(v51, 0x104u, L"%s\\%s", v50, a2);
    v38 = v16;
    if ( v16 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
        "SystemStoreLite::GetStoredIdentityProperty",
        0xE1u,
        v16,
        "hr = StringCchPrintfW( currentSubKeyWithUserSid, MAX_PATH, L\"%s\\\\%s\", currentSubKey, static_cast<LPCWSTR>(pC"
        "urrentUserSidString))");
      goto LABEL_61;
    }
    LODWORD(v36) = 2;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, char *, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)v9 + 56LL))(
            v9,
            v45[0],
            v51,
            a3,
            v36,
            0,
            0,
            uBytes);
    if ( v17 != 2 )
      break;
    memset_0(v53, 0, 0x208u);
    v47[0] = 0;
    v47[2] = v9;
    v47[1] = 0;
    v18 = StringCchPrintfW(v53, 0x104u, L"%s\\%s", v52, v51);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 *, _QWORD, int, _QWORD *))(*(_QWORD *)v9 + 80LL))(
              v9,
              -2147483645,
              v53,
              0,
              131097,
              v47);
      if ( !v18 )
        goto LABEL_32;
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      v19 = L"SID missing from LiveID key. (win32 = 0x%0x)";
      v20 = 277;
      v21 = 3;
    }
    else
    {
      v19 = L"StringCchPrintf failed for full user SID path. (localHr = 0x%0x)";
      v20 = 262;
      v21 = 2;
    }
    LODWORD(v37) = v18;
    TracePrintW(v21, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v20, v19, v37);
LABEL_32:
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>((__int64)v47);
  }
  if ( v17 )
  {
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    v38 = v17;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x11Bu,
      v17,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_61;
  }
  if ( a5 )
  {
    v22 = 130;
    v23 = v50;
    do
    {
      if ( !*v23 )
        break;
      ++v23;
      --v22;
    }
    while ( v22 );
    v24 = v22 == 0 ? 0x80070057 : 0;
    v38 = v24;
    if ( !v22 )
    {
      v27 = "hr = StringCbLengthW(currentSubKey, MAX_PATH, &liveUserBufferLengthInBytes)";
      v28 = 290;
      goto LABEL_60;
    }
    v25 = -(__int64)(v22 != 0) & (2 * (130 - v22));
    v10 = (unsigned __int16 *)LocalAlloc(0x40u, v25 + 2);
    Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)&uBytes[1]);
    *(_QWORD *)&uBytes[1] = v10;
    if ( v10 )
    {
      v26 = StringCbCopyW(v10, v25 + 2, v50);
      v38 = v26;
      if ( v26 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
          "SystemStoreLite::GetStoredIdentityProperty",
          0x128u,
          v26,
          "hr = StringCbCopyW(pLiveUserName, liveUserBufferLengthInBytes, currentSubKey)");
        goto LABEL_61;
      }
      goto LABEL_48;
    }
LABEL_49:
    v38 = -2147024882;
    goto LABEL_61;
  }
LABEL_48:
  v29 = (unsigned __int16 *)LocalAlloc(0x40u, uBytes[0]);
  Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear((__int64)&v42);
  v42 = v29;
  if ( !v29 )
    goto LABEL_49;
  v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, const unsigned __int16 *, int, _QWORD, unsigned __int16 *, _DWORD *))(*(_QWORD *)v9 + 56LL))(
          v9,
          v45[0],
          v51,
          a3,
          2,
          0,
          v29,
          uBytes);
  if ( v30 )
  {
    if ( v30 > 0 )
      v30 = (unsigned __int16)v30 | 0x80070000;
    v38 = v30;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetStoredIdentityProperty",
      0x13Bu,
      v30,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
  }
  else
  {
    v42 = 0;
    v43 = 0;
    *a4 = v29;
    if ( a5 )
    {
      *(_QWORD *)&uBytes[1] = 0;
      v40 = 0;
      *a5 = v10;
    }
  }
LABEL_61:
  v31 = v38;
  ErrorVerifier::CheckAgainstList((PPTraceStatus *)v48[3], *v48[2], (unsigned __int64)v48[1], v48[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49, v32, v33);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&uBytes[1]);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)&v42);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>((__int64)v45);
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v46);
  return v31;
}

```

## disassembly

```asm
0x1800251c4  push    rbp
0x1800251c6  push    rbx
0x1800251c7  push    rsi
0x1800251c8  push    rdi
0x1800251c9  push    r12
0x1800251cb  push    r13
0x1800251cd  push    r14
0x1800251cf  push    r15
0x1800251d1  lea     rbp, [rsp-868h]
0x1800251d9  sub     rsp, 968h
0x1800251e0  mov     rax, cs:__security_cookie
0x1800251e7  xor     rax, rsp
0x1800251ea  mov     [rbp+8A0h+var_50], rax
0x1800251f1  mov     r15, r9
0x1800251f4  mov     r12, r8
0x1800251f7  mov     r13, rdx
0x1800251fa  mov     rbx, rcx
0x1800251fd  mov     rsi, [rbp+8A0h+arg_20]
0x180025204  mov     rax, [rcx]
0x180025207  mov     rax, [rax+8]
0x18002520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025210  mov     rdi, rax
0x180025213  xor     r14d, r14d
0x180025216  mov     [rbp+8A0h+var_900], r14
0x18002521a  mov     [rbp+8A0h+var_8F0], r14
0x18002521e  mov     [rbp+8A0h+var_8F8], r14
0x180025222  xor     edx, edx; Val
0x180025224  mov     r8d, 208h; Size
0x18002522a  lea     rcx, [rbp+8A0h+var_470]; void *
0x180025231  call    memset_0
0x180025236  xor     edx, edx; Val
0x180025238  mov     r8d, 208h; Size
0x18002523e  lea     rcx, [rbp+8A0h+var_890]; void *
0x180025242  call    memset_0
0x180025247  xor     edx, edx; Val
0x180025249  mov     r8d, 208h; Size
0x18002524f  lea     rcx, [rbp+8A0h+var_680]; void *
0x180025256  call    memset_0
0x18002525b  mov     [rbp+8A0h+var_918], r14
0x18002525f  mov     [rbp+8A0h+var_908], rdi
0x180025263  mov     [rbp+8A0h+var_910], r14
0x180025267  mov     [rsp+9A0h+var_930], r14
0x18002526c  mov     [rbp+8A0h+var_920], r14
0x180025270  mov     [rsp+9A0h+var_928], r14
0x180025275  mov     qword ptr [rsp+9A0h+uBytes+4], r14
0x18002527a  xor     eax, eax
0x18002527c  mov     [rsp+9A0h+var_938], rax
0x180025281  mov     [rsp+9A0h+var_940], rax
0x180025286  mov     dword ptr [rsp+9A0h+uBytes], eax
0x18002528a  mov     [rsp+9A0h+var_950], eax
0x18002528e  lea     rcx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x180025295  mov     [rbp+8A0h+var_8B0], rcx
0x180025299  lea     rax, [rsp+9A0h+var_950]
0x18002529e  mov     [rbp+8A0h+var_8A8], rax
0x1800252a2  mov     [rbp+8A0h+var_8A0], 1
0x1800252aa  lea     rax, qword_180040170
0x1800252b1  mov     [rbp+8A0h+var_898], rax
0x1800252b5  xor     r9d, r9d; unsigned int
0x1800252b8  mov     r8d, 8Fh; char *
0x1800252be  mov     rdx, rcx; char *
0x1800252c1  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800252c8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800252cd  nop
0x1800252ce  lea     rax, qword_180040178
0x1800252d5  mov     [rsp+9A0h+var_980], rax; int *
0x1800252da  lea     r9d, [r14+0Bh]; unsigned __int64
0x1800252de  lea     r8, [rsp+9A0h+var_950]; int *
0x1800252e3  lea     rdx, aSystemstorelit_0; "SystemStoreLite::GetStoredIdentityPrope"...
0x1800252ea  lea     rcx, [rbp+8A0h+var_8D0]; this
0x1800252ee  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800252f3  nop
0x1800252f4  test    r13, r13
0x1800252f7  jz      loc_1800257C6
0x1800252fd  test    r12, r12
0x180025300  jz      loc_1800257C6
0x180025306  test    r15, r15
0x180025309  jz      loc_1800257C6
0x18002530f  mov     [r15], r14
0x180025312  test    rsi, rsi
0x180025315  jz      short loc_18002531A
0x180025317  mov     [rsi], r14
0x18002531a  lea     rdx, [rbp+8A0h+var_900]; unsigned __int16 **
0x18002531e  mov     rcx, rbx; struct IExecutionContextLite *
0x180025321  call    ?GetSystemSidString@SystemStoreLite@@CAJPEAVIExecutionContextLite@@PEAPEAG@Z; SystemStoreLite::GetSystemSidString(IExecutionContextLite *,ushort * *)
0x180025326  mov     [rsp+9A0h+var_950], eax
0x18002532a  test    eax, eax
0x18002532c  jns     short loc_180025348
0x18002532e  lea     r8, aHrSystemstorel_0; "hr = SystemStoreLite::GetSystemSidStrin"...
0x180025335  mov     [rsp+9A0h+var_980], r8
0x18002533a  mov     r9d, eax
0x18002533d  mov     r8d, 0A3h
0x180025343  jmp     loc_1800257E6
0x180025348  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18002534f  mov     [rsp+9A0h+var_980], rax
0x180025354  mov     r9, [rbp+8A0h+var_900]
0x180025358  lea     r8, aSS; "%s\\%s"
0x18002535f  mov     edx, 104h; unsigned __int64
0x180025364  lea     rcx, [rbp+8A0h+var_470]; unsigned __int16 *
0x18002536b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025370  mov     [rsp+9A0h+var_950], eax
0x180025374  test    eax, eax
0x180025376  jns     short loc_180025392
0x180025378  lea     rcx, aHrStringcchpri; "hr = StringCchPrintfW( storedIdentities"...
0x18002537f  mov     [rsp+9A0h+var_980], rcx
0x180025384  mov     r9d, eax
0x180025387  mov     r8d, 0ACh
0x18002538d  jmp     loc_1800257E6
0x180025392  mov     rax, [rdi]
0x180025395  lea     rcx, [rbp+8A0h+var_918]
0x180025399  mov     [rsp+9A0h+var_978], rcx
0x18002539e  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x1800253a6  xor     r9d, r9d
0x1800253a9  lea     r8, [rbp+8A0h+var_470]
0x1800253b0  mov     rdx, 0FFFFFFFF80000003h
0x1800253b7  mov     rcx, rdi
0x1800253ba  mov     rax, [rax+50h]
0x1800253be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253c3  cmp     eax, 2
0x1800253c6  jnz     short loc_1800253F1
0x1800253c8  lea     r9, aSystemStoreNot; "System store not found."
0x1800253cf  mov     r8d, 0BCh; unsigned int
0x1800253d5  lea     rdx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800253dc  lea     ecx, [rax+1]; unsigned __int8
0x1800253df  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800253e4  mov     [rsp+9A0h+var_950], 80070490h
0x1800253ec  jmp     loc_1800257F9
0x1800253f1  test    eax, eax
0x1800253f3  jz      short loc_180025421
0x1800253f5  jle     short loc_1800253FF
0x1800253f7  movzx   eax, ax
0x1800253fa  or      eax, 80070000h
0x1800253ff  mov     [rsp+9A0h+var_950], eax
0x180025403  test    eax, eax
0x180025405  jns     short loc_180025421
0x180025407  lea     rcx, aHrHresultFromW_7; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x18002540e  mov     [rsp+9A0h+var_980], rcx
0x180025413  mov     r9d, eax
0x180025416  mov     r8d, 0C1h
0x18002541c  jmp     loc_1800257E6
0x180025421  xor     ebx, ebx
0x180025423  mov     rax, [rdi]
0x180025426  mov     dword ptr [rsp+9A0h+var_980], 104h
0x18002542e  lea     r9, [rbp+8A0h+var_890]
0x180025432  mov     r8d, ebx
0x180025435  mov     rdx, [rbp+8A0h+var_918]
0x180025439  mov     rcx, rdi
0x18002543c  mov     rax, [rax+28h]
0x180025440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025445  cmp     eax, 103h
0x18002544a  jz      loc_18002579E
0x180025450  test    eax, eax
0x180025452  jz      short loc_18002546A
0x180025454  jle     short loc_18002545E
0x180025456  movzx   eax, ax
0x180025459  or      eax, 80070000h
0x18002545e  mov     [rsp+9A0h+var_950], eax
0x180025462  test    eax, eax
0x180025464  js      loc_1800255BE
0x18002546a  mov     [rsp+9A0h+var_980], r13
0x18002546f  lea     r9, [rbp+8A0h+var_890]
0x180025473  lea     r8, aSS; "%s\\%s"
0x18002547a  mov     edx, 104h; unsigned __int64
0x18002547f  lea     rcx, [rbp+8A0h+var_680]; unsigned __int16 *
0x180025486  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002548b  mov     [rsp+9A0h+var_950], eax
0x18002548f  test    eax, eax
0x180025491  js      loc_180025787
0x180025497  mov     rax, [rdi]
0x18002549a  lea     rcx, [rsp+9A0h+uBytes]
0x18002549f  mov     [rsp+9A0h+var_968], rcx
0x1800254a4  mov     [rsp+9A0h+var_970], 0
0x1800254ad  mov     [rsp+9A0h+var_978], 0
0x1800254b6  mov     dword ptr [rsp+9A0h+var_980], 2
0x1800254be  mov     r9, r12
0x1800254c1  lea     r8, [rbp+8A0h+var_680]
0x1800254c8  mov     rdx, [rbp+8A0h+var_918]
0x1800254cc  mov     rcx, rdi
0x1800254cf  mov     rax, [rax+38h]
0x1800254d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d8  cmp     eax, 2
0x1800254db  jnz     loc_1800255D8
0x1800254e1  xor     edx, edx; Val
0x1800254e3  mov     r8d, 208h; Size
0x1800254e9  lea     rcx, [rbp+8A0h+var_260]; void *
0x1800254f0  call    memset_0
0x1800254f5  mov     [rbp+8A0h+var_8E8], 0
0x1800254fd  mov     [rbp+8A0h+var_8D8], rdi
0x180025501  mov     [rbp+8A0h+var_8E0], 0
0x180025509  lea     rax, [rbp+8A0h+var_680]
0x180025510  mov     [rsp+9A0h+var_980], rax
0x180025515  lea     r9, [rbp+8A0h+var_470]
0x18002551c  lea     r8, aSS; "%s\\%s"
0x180025523  mov     edx, 104h; unsigned __int64
0x180025528  lea     rcx, [rbp+8A0h+var_260]; unsigned __int16 *
0x18002552f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180025534  test    eax, eax
0x180025536  jns     short loc_18002554C
0x180025538  lea     r9, aStringcchprint; "StringCchPrintf failed for full user SI"...
0x18002553f  mov     r8d, 106h
0x180025545  mov     ecx, 2
0x18002554a  jmp     short loc_18002559D
0x18002554c  mov     rax, [rdi]
0x18002554f  lea     rcx, [rbp+8A0h+var_8E8]
0x180025553  mov     [rsp+9A0h+var_978], rcx
0x180025558  mov     dword ptr [rsp+9A0h+var_980], 20019h
0x180025560  xor     r9d, r9d
0x180025563  lea     r8, [rbp+8A0h+var_260]
0x18002556a  mov     rdx, 0FFFFFFFF80000003h
0x180025571  mov     rcx, rdi
0x180025574  mov     rax, [rax+50h]
0x180025578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002557d  test    eax, eax
0x18002557f  jz      short loc_1800255AE
0x180025581  jle     short loc_18002558B
0x180025583  movzx   eax, ax
0x180025586  or      eax, 80070000h
0x18002558b  lea     r9, aSidMissingFrom; "SID missing from LiveID key. (win32 = 0"...
0x180025592  mov     r8d, 115h; unsigned int
0x180025598  mov     ecx, 3; unsigned __int8
0x18002559d  mov     dword ptr [rsp+9A0h+var_980], eax
0x1800255a1  lea     rdx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800255a8  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800255ad  nop
0x1800255ae  lea     rcx, [rbp+8A0h+var_8E8]
0x1800255b2  call    ??1?$Auto@PEAUHKEY__@@VRegistryFunctor@@VIRegistryFunctions@@@@QEAA@XZ; Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(void)
0x1800255b7  inc     ebx
0x1800255b9  jmp     loc_180025423
0x1800255be  lea     rcx, aHrHresultFromW_7; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x1800255c5  mov     [rsp+9A0h+var_980], rcx
0x1800255ca  mov     r9d, eax
0x1800255cd  mov     r8d, 0D9h
0x1800255d3  jmp     loc_1800257E6
0x1800255d8  xor     r13d, r13d
0x1800255db  test    eax, eax
0x1800255dd  jz      short loc_18002560B
0x1800255df  jle     short loc_1800255E9
0x1800255e1  movzx   eax, ax
0x1800255e4  or      eax, 80070000h
0x1800255e9  mov     [rsp+9A0h+var_950], eax
0x1800255ed  test    eax, eax
0x1800255ef  jns     short loc_18002560B
0x1800255f1  lea     rcx, aHrHresultFromW_7; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x1800255f8  mov     [rsp+9A0h+var_980], rcx
0x1800255fd  mov     r9d, eax
0x180025600  mov     r8d, 11Bh
0x180025606  jmp     loc_1800257E6
0x18002560b  test    rsi, rsi
0x18002560e  jz      loc_1800256C6
0x180025614  mov     edx, 82h
0x180025619  mov     ecx, edx
0x18002561b  lea     rax, [rbp+8A0h+var_890]
0x18002561f  cmp     [rax], r13w
0x180025623  jz      short loc_18002562F
0x180025625  add     rax, 2
0x180025629  sub     rcx, 1
0x18002562d  jnz     short loc_18002561F
0x18002562f  mov     rax, rcx
0x180025632  neg     rax
0x180025635  sbb     r9d, r9d
0x180025638  not     r9d
0x18002563b  and     r9d, 80070057h
0x180025642  mov     [rsp+9A0h+var_950], r9d
0x180025647  test    rcx, rcx
0x18002564a  jz      short loc_1800256B4
0x18002564c  sub     rdx, rcx
0x18002564f  lea     rbx, [rdx+rdx]
0x180025653  neg     rcx
0x180025656  sbb     rax, rax
0x180025659  and     rbx, rax
0x18002565c  lea     rdx, [rbx+2]; uBytes
0x180025660  mov     ecx, 40h ; '@'; uFlags
0x180025665  call    cs:__imp_LocalAlloc
0x18002566b  mov     r14, rax
0x18002566e  lea     rcx, [rsp+9A0h+uBytes+4]
0x180025673  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180025678  mov     qword ptr [rsp+9A0h+uBytes+4], r14
0x18002567d  test    r14, r14
0x180025680  jz      short loc_1800256EC
0x180025682  lea     r8, [rbp+8A0h+var_890]; unsigned __int16 *
0x180025686  lea     rdx, [rbx+2]; unsigned __int64
0x18002568a  mov     rcx, r14; unsigned __int16 *
0x18002568d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180025692  mov     [rsp+9A0h+var_950], eax
0x180025696  test    eax, eax
0x180025698  jns     short loc_1800256C6
0x18002569a  lea     rcx, aHrStringcbcopy; "hr = StringCbCopyW(pLiveUserName, liveU"...
0x1800256a1  mov     [rsp+9A0h+var_980], rcx
0x1800256a6  mov     r9d, eax
0x1800256a9  mov     r8d, 128h
0x1800256af  jmp     loc_1800257E6
0x1800256b4  lea     rax, aHrStringcbleng; "hr = StringCbLengthW(currentSubKey, MAX"...
0x1800256bb  mov     r8d, 122h
0x1800256c1  jmp     loc_1800257E1
0x1800256c6  mov     edx, dword ptr [rsp+9A0h+uBytes]; uBytes
0x1800256ca  mov     ecx, 40h ; '@'; uFlags
0x1800256cf  call    cs:__imp_LocalAlloc
0x1800256d5  mov     rbx, rax
0x1800256d8  lea     rcx, [rsp+9A0h+var_930]
0x1800256dd  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x1800256e2  mov     [rsp+9A0h+var_930], rbx
  ... truncated ...
```
