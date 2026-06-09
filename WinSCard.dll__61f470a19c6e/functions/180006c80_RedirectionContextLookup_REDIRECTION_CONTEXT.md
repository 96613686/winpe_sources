# RedirectionContextLookup(_REDIRECTION_CONTEXT * *)

- ea: `0x180006c80`
- end: `0x180007931`
- name: `?RedirectionContextLookup@@YAKPEAPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `3249`
- prototype: `unsigned int __fastcall(struct _REDIRECTION_CONTEXT **)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006400`
- `0x180007940`
- `0x180007ec0`
- `0x180007f40`
- `0x1800093e4`
- `0x180019b80`
- `0x18002b490`
- `0x18002b734`
- `0x18002ba08`

## callees

- `0x180006890`
- `0x180006c80`
- `0x180007bc0`
- `0x180017580`
- `0x1800176a0`
- `0x180017c48`
- `0x180019644`
- `0x18001991c`
- `0x1800239b8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006faf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180006faf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006dd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006dd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007163`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800072de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fb9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006f7d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006f7d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007191`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007012`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007191`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800072e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006f32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006f67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006fce`

## pseudocode

```c
__int64 __fastcall RedirectionContextLookup(struct _RTL_CRITICAL_SECTION **a1)
{
  DWORD CurrentThreadId; // eax
  int v3; // r10d
  unsigned __int64 *v4; // rdx
  int v5; // r15d
  DWORD v6; // r8d
  int v7; // r9d
  unsigned int i; // eax
  bool v9; // zf
  int v10; // edx
  int v11; // r10d
  char *v12; // rcx
  __int64 v13; // r12
  __int64 v14; // rdx
  char *v15; // rax
  const char *v16; // rdi
  __int64 v17; // rax
  char *v18; // r8
  const char *v19; // r9
  char *v20; // rax
  LPCRITICAL_SECTION DebugInfo; // rbx
  DWORD v22; // eax
  unsigned __int64 v23; // rdx
  int v24; // r10d
  int v25; // r8d
  unsigned int j; // ecx
  bool v27; // zf
  int v28; // r10d
  char *v29; // rcx
  __int64 v30; // rdx
  char *v31; // rax
  __int64 v32; // rax
  char *v33; // r8
  char *v34; // rax
  HANDLE CurrentThread; // rax
  unsigned int LastError; // ebp
  HANDLE CurrentProcess; // rax
  int SpinCount; // eax
  DWORD v39; // eax
  unsigned __int64 v40; // rdx
  int v41; // ebx
  __int64 v42; // r9
  int v43; // r8d
  unsigned int k; // ecx
  bool v45; // zf
  int v46; // r10d
  char *v47; // rcx
  __int64 v48; // rdx
  char *v49; // rax
  const char *v50; // rsi
  const char *v51; // r10
  char *v52; // r8
  char *v53; // rax
  struct _RTL_CRITICAL_SECTION *v54; // rbx
  __int64 v55; // rcx
  __int64 v56; // rcx
  DWORD v57; // eax
  unsigned __int64 v58; // rdx
  char *m; // rcx
  int v60; // r10d
  DWORD v61; // r9d
  int v62; // r8d
  bool v63; // zf
  int v64; // r11d
  PVOID *v65; // r10
  __int64 v66; // rdx
  char *v67; // rax
  const char *v68; // r8
  _BYTE *v69; // rcx
  __int64 v70; // rax
  _BYTE *v71; // rax
  DWORD v72; // eax
  unsigned __int64 v73; // rdx
  int v74; // r9d
  unsigned __int64 *v75; // r11
  unsigned int n; // ecx
  bool v77; // zf
  int v78; // r10d
  char *v79; // rcx
  char *v80; // rax
  char *v81; // rdi
  __int64 v82; // rdx
  char *v83; // rax
  __int64 v85; // rdx
  __int64 v86; // rdx
  __int64 v87; // rcx
  int v88; // r9d
  int v89; // r10d
  int v90; // r11d
  int v91; // r10d
  int v92; // r11d
  int v93; // r10d
  int v94; // r11d
  char v95; // di
  int v96; // ebx
  int v97; // r11d
  int ii; // esi
  int v99; // r10d
  int TokenInformation; // [rsp+78h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  v3 = `WppTraceIndent'::`2'::idxCurrentThread;
  v4 = &`WppTraceIndent'::`2'::ThreadTable;
  v5 = -1;
  v6 = CurrentThreadId;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v3 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_180045874 = 0;
    goto LABEL_15;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
  {
    v7 = -1;
    for ( i = 0; ; ++i )
    {
      v9 = i == 32;
      if ( i >= 0x20 )
        break;
      v10 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
      if ( v10 == v6 )
      {
        v3 = i;
        `WppTraceIndent'::`2'::idxCurrentThread = i;
        v4 = &`WppTraceIndent'::`2'::ThreadTable;
        v9 = i == 32;
        break;
      }
      if ( v7 == -1 && !v10 )
        v7 = i;
      v4 = &`WppTraceIndent'::`2'::ThreadTable;
    }
    if ( v9 )
    {
      if ( v7 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_168;
      }
      v3 = v7;
      `WppTraceIndent'::`2'::idxCurrentThread = v7;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v7) = v6;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v7 + 1) = 0;
    }
  }
  if ( v3 >= 0 )
  {
LABEL_15:
    v11 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v3 + 1);
    goto LABEL_16;
  }
LABEL_168:
  v11 = 0;
LABEL_16:
  v12 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v11 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v12, (unsigned __int64)v4, "..") && v90 + 1 <= v89 )
      ;
    v12 = (char *)WPP_GLOBAL_Control;
  }
  v13 = 256;
  v14 = 256;
  v15 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( 1 )
  {
    v16 = ">";
    if ( !*v15 )
      break;
    ++v15;
    if ( !--v14 )
      goto LABEL_26;
  }
  v17 = 2147483646;
  v18 = (char *)&`wil::SetLastError'::`5'::depth - v14;
  v19 = ">";
  do
  {
    if ( !v17 )
      break;
    if ( !*v19 )
      break;
    *v18++ = *v19++;
    --v17;
    --v14;
  }
  while ( v14 );
  v20 = v18 - 1;
  if ( v14 )
    v20 = v18;
  *v20 = 0;
LABEL_26:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v12 != (char *)&WPP_GLOBAL_Control && (v12[28] & 2) != 0 && (unsigned __int8)v12[25] >= 5u )
    WPP_SF_s(*((_QWORD *)v12 + 2), 26, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  EnterCriticalSection(&g_RedirectionContextListCS);
  DebugInfo = g_pRedirectionContextList;
  TokenInformation = 0;
  v22 = GetCurrentThreadId();
  v24 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v24 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v22;
    dword_180045874 = 0;
    goto LABEL_43;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v22 )
  {
    v25 = -1;
    for ( j = 0; ; ++j )
    {
      v27 = j == 32;
      if ( j >= 0x20 )
        break;
      v23 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)j);
      if ( (_DWORD)v23 == v22 )
      {
        v24 = j;
        `WppTraceIndent'::`2'::idxCurrentThread = j;
        v27 = j == 32;
        break;
      }
      if ( v25 == -1 && !(_DWORD)v23 )
        v25 = j;
    }
    if ( v27 )
    {
      if ( v25 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_170;
      }
      v24 = v25;
      `WppTraceIndent'::`2'::idxCurrentThread = v25;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v25) = v22;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v25 + 1) = 0;
    }
  }
  if ( v24 >= 0 )
  {
LABEL_43:
    v28 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v24 + 1);
    goto LABEL_44;
  }
LABEL_170:
  v28 = 0;
LABEL_44:
  v29 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v28 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v29, v23, "..") && v92 + 1 <= v91 )
      ;
    v29 = (char *)WPP_GLOBAL_Control;
  }
  v30 = 256;
  v31 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v31 )
  {
    ++v31;
    if ( !--v30 )
      goto LABEL_54;
  }
  v32 = 2147483646;
  v33 = (char *)&`wil::SetLastError'::`5'::depth - v30;
  do
  {
    if ( !v32 )
      break;
    if ( !*v16 )
      break;
    *v33++ = *v16++;
    --v32;
    --v30;
  }
  while ( v30 );
  v34 = v33 - 1;
  if ( v30 )
    v34 = v33;
  *v34 = 0;
LABEL_54:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v29 != (char *)&WPP_GLOBAL_Control && (v29[28] & 2) != 0 && (unsigned __int8)v29[25] >= 5u )
    WPP_SF_s(*((_QWORD *)v29 + 2), 20, &WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids);
  if ( *a1 )
  {
    SpinCount = (*a1)[1].SpinCount;
    LastError = 0;
    TokenInformation = SpinCount;
    *a1 = 0;
    goto LABEL_66;
  }
  TokenHandle = 0;
  ReturnLength = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      goto LABEL_62;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_61:
      LastError = GetLastError();
      goto LABEL_62;
    }
  }
  LastError = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_61;
LABEL_62:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( LastError )
    goto LABEL_71;
  SpinCount = TokenInformation;
LABEL_66:
  if ( DebugInfo )
  {
    while ( SpinCount != LODWORD(DebugInfo[1].SpinCount) )
    {
      DebugInfo = (LPCRITICAL_SECTION)DebugInfo[12].DebugInfo;
      if ( !DebugInfo )
        goto LABEL_67;
    }
    *a1 = DebugInfo;
  }
  else
  {
LABEL_67:
    LastError = 1168;
  }
LABEL_71:
  v39 = GetCurrentThreadId();
  v41 = `WppTraceIndent'::`2'::idxCurrentThread;
  LODWORD(v42) = v39;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v41 = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v39;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    dword_180045874 = 0;
    goto LABEL_85;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v39 )
  {
    v43 = -1;
    for ( k = 0; ; ++k )
    {
      v45 = k == 32;
      if ( k >= 0x20 )
        break;
      v40 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
      if ( (_DWORD)v40 == v39 )
      {
        v41 = k;
        `WppTraceIndent'::`2'::idxCurrentThread = k;
        v45 = k == 32;
        break;
      }
      if ( v43 == -1 && !(_DWORD)v40 )
        v43 = k;
    }
    if ( v45 )
    {
      if ( v43 == -1 )
      {
        v41 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_172;
      }
      v41 = v43;
      `WppTraceIndent'::`2'::idxCurrentThread = v43;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v43) = v39;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v43 + 1) = 0;
    }
  }
  if ( v41 >= 0 )
  {
LABEL_85:
    v46 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v41 + 1);
    goto LABEL_86;
  }
LABEL_172:
  v46 = 0;
LABEL_86:
  v47 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v46 >= 1 )
  {
    while ( !(unsigned int)StringCbCatA(v47, v40, "..") && v94 + 1 <= v93 )
      ;
    v47 = (char *)WPP_GLOBAL_Control;
    v41 = `WppTraceIndent'::`2'::idxCurrentThread;
  }
  v48 = 256;
  v49 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( 1 )
  {
    v50 = "<";
    if ( !*v49 )
      break;
    ++v49;
    if ( !--v48 )
      goto LABEL_96;
  }
  v42 = 2147483646;
  v51 = "<";
  v52 = (char *)&`wil::SetLastError'::`5'::depth - v48;
  do
  {
    if ( !v42 )
      break;
    if ( !*v51 )
      break;
    *v52++ = *v51++;
    --v42;
    --v48;
  }
  while ( v48 );
  v53 = v52 - 1;
  if ( v48 )
    v53 = v52;
  *v53 = 0;
LABEL_96:
  if ( v41 >= 0 )
  {
    v85 = 8LL * v41;
    v9 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v85 + 4))-- == 1;
    if ( v9 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v85) = 0;
  }
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v47 != (char *)&WPP_GLOBAL_Control && (v47[28] & 2) != 0 && (unsigned __int8)v47[25] >= 5u )
    WPP_SF_sd(*((_QWORD *)v47 + 2), 21, (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids, v42, LastError);
  if ( LastError == 1168 )
  {
    LastError = I_RedirectionContextInitialize(a1);
    if ( LastError )
      goto LABEL_134;
    WppTraceIndent(v87, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
        v88,
        (*a1)[1].SpinCount);
    }
    if ( !g_fReleaseRedirectionContextRegistered )
      I_RedirectionContextReleaseRegister();
    (*a1)[12].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)g_pRedirectionContextList;
    g_pRedirectionContextList = *a1;
  }
  else if ( !LastError )
  {
    v54 = *a1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixSmartcardRedirection_Deadlock>::GetImpl'::`2'::impl) )
    {
      v95 = _InterlockedIncrement((volatile signed __int32 *)&v54[1].DebugInfo + 1);
      WppTraceIndent(v55, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          (_DWORD)WPP_pszIndent,
          v54[1].SpinCount,
          v95);
      }
    }
    else
    {
      EnterCriticalSection(v54);
      ++HIDWORD(v54[1].DebugInfo);
      LeaveCriticalSection(v54);
      WppTraceIndent(v56, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
          (_DWORD)WPP_pszIndent,
          v54[1].SpinCount,
          HIDWORD(v54[1].DebugInfo));
      }
    }
  }
  v57 = GetCurrentThreadId();
  v60 = `WppTraceIndent'::`2'::idxCurrentThread;
  v61 = v57;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v60 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v57;
    dword_180045874 = 0;
    goto LABEL_121;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v57 )
  {
    v62 = -1;
    for ( m = 0; ; m = (char *)(unsigned int)((_DWORD)m + 1) )
    {
      v63 = (_DWORD)m == 32;
      if ( (unsigned int)m >= 0x20 )
        break;
      v58 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)m);
      if ( (_DWORD)v58 == v57 )
      {
        v60 = (int)m;
        `WppTraceIndent'::`2'::idxCurrentThread = (int)m;
        v63 = (_DWORD)m == 32;
        break;
      }
      if ( v62 == -1 && !(_DWORD)v58 )
        v62 = (int)m;
    }
    if ( v63 )
    {
      if ( v62 == -1 )
      {
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_180;
      }
      v60 = v62;
      `WppTraceIndent'::`2'::idxCurrentThread = v62;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v62) = v57;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v62 + 1) = 0;
    }
  }
  if ( v60 < 0 )
  {
LABEL_180:
    v64 = 0;
    goto LABEL_122;
  }
LABEL_121:
  v64 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v60 + 1);
LABEL_122:
  v65 = (PVOID *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v96 = 1;
    if ( v64 >= 1 )
    {
      do
      {
        if ( (unsigned int)StringCbCatA(m, v58, "..") )
          break;
        ++v96;
      }
      while ( v96 <= v97 );
      v65 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v66 = 256;
  v67 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v67 )
  {
    ++v67;
    if ( !--v66 )
      goto LABEL_132;
  }
  v68 = " ";
  v69 = (char *)&`wil::SetLastError'::`5'::depth - v66;
  v70 = 2147483646;
  do
  {
    if ( !v70 )
      break;
    v61 = *(unsigned __int8 *)v68;
    if ( !(_BYTE)v61 )
      break;
    *v69 = v61;
    ++v68;
    ++v69;
    --v70;
    --v66;
  }
  while ( v66 );
  v71 = v69 - 1;
  if ( v66 )
    v71 = v69;
  *v71 = 0;
LABEL_132:
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v65 != &WPP_GLOBAL_Control && (*((_BYTE *)v65 + 28) & 4) != 0 && *((_BYTE *)v65 + 25) >= 4u )
    WPP_SF_sd(
      (unsigned int)v65[2],
      28,
      (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids,
      v61,
      (*a1)[1].SpinCount);
LABEL_134:
  LeaveCriticalSection(&g_RedirectionContextListCS);
  v72 = GetCurrentThreadId();
  v74 = `WppTraceIndent'::`2'::idxCurrentThread;
  v75 = &`WppTraceIndent'::`2'::ThreadTable;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v74 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v72;
    dword_180045874 = 0;
    goto LABEL_148;
  }
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
    || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v72 )
  {
    for ( n = 0; ; ++n )
    {
      v77 = n == 32;
      if ( n >= 0x20 )
        break;
      v73 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)n);
      if ( (_DWORD)v73 == v72 )
      {
        v74 = n;
        `WppTraceIndent'::`2'::idxCurrentThread = n;
        v77 = n == 32;
        break;
      }
      if ( v5 == -1 && !(_DWORD)v73 )
        v5 = n;
    }
    if ( v77 )
    {
      if ( v5 == -1 )
      {
        v74 = -2;
        `WppTraceIndent'::`2'::idxCurrentThread = -2;
        goto LABEL_174;
      }
      v74 = v5;
      `WppTraceIndent'::`2'::idxCurrentThread = v5;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v5) = v72;
      *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v5 + 1) = 0;
    }
  }
  if ( v74 >= 0 )
  {
LABEL_148:
    v78 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v74 + 1);
    goto LABEL_149;
  }
LABEL_174:
  v78 = 0;
LABEL_149:
  v79 = (char *)WPP_GLOBAL_Control;
  `WppTraceIndent'::`2'::szIndentPrefix = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v78 >= 1 )
  {
    for ( ii = 1; ii <= v99; ++ii )
    {
      if ( (unsigned int)StringCbCatA(v79, v73, "..") )
        break;
    }
    v79 = (char *)WPP_GLOBAL_Control;
    v50 = "<";
    v74 = `WppTraceIndent'::`2'::idxCurrentThread;
  }
  v80 = &`WppTraceIndent'::`2'::szIndentPrefix;
  while ( *v80 )
  {
    ++v80;
    if ( !--v13 )
      goto LABEL_159;
  }
  v81 = (char *)&`wil::SetLastError'::`5'::depth - v13;
  v82 = 2147483646;
  do
  {
    if ( !v82 )
      break;
    if ( !*v50 )
      break;
    *v81++ = *v50++;
    --v82;
    --v13;
  }
  while ( v13 );
  v83 = v81 - 1;
  if ( v13 )
    v83 = v81;
  *v83 = 0;
LABEL_159:
  if ( v74 >= 0 )
  {
    v86 = v74;
    v9 = HIDWORD(v75[v86])-- == 1;
    if ( v9 )
      LODWORD(v75[v86]) = 0;
  }
  WPP_pszIndent = &`WppTraceIndent'::`2'::szIndentPrefix;
  if ( v79 != (char *)&WPP_GLOBAL_Control && (v79[28] & 2) != 0 && (unsigned __int8)v79[25] >= 5u )
    WPP_SF_sd(*((_QWORD *)v79 + 2), 29, (unsigned int)&WPP_ff6f9e331ef63b4fe1fc76f2b0998229_Traceguids, v74, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180006c80  mov     [rsp+arg_0], rbx
0x180006c85  push    rbp
0x180006c86  push    rsi
0x180006c87  push    rdi
0x180006c88  push    r12
0x180006c8a  push    r13
0x180006c8c  push    r14
0x180006c8e  push    r15
0x180006c90  sub     rsp, 30h
0x180006c94  mov     r13, rcx
0x180006c97  call    cs:__imp_GetCurrentThreadId
0x180006c9d  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006ca4  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006cab  mov     r15d, 0FFFFFFFFh
0x180006cb1  xor     r14d, r14d
0x180006cb4  mov     r8d, eax
0x180006cb7  cmp     r10d, r15d
0x180006cba  jz      loc_180006E3A
0x180006cc0  cmp     r10d, 0FFFFFFFEh
0x180006cc4  jz      short loc_180006CCC
0x180006cc6  cmp     [rdx+r10*8], eax
0x180006cca  jz      short loc_180006D13
0x180006ccc  mov     r9d, r15d
0x180006ccf  mov     eax, r14d
0x180006cd2  cmp     eax, 20h ; ' '
0x180006cd5  jnb     short loc_180006D0D
0x180006cd7  movsxd  rcx, eax
0x180006cda  mov     edx, [rdx+rcx*8]
0x180006cdd  cmp     edx, r8d
0x180006ce0  jz      short loc_180006CFA
0x180006ce2  cmp     r9d, r15d
0x180006ce5  jz      short loc_180006CF2
0x180006ce7  inc     eax
0x180006ce9  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006cf0  jmp     short loc_180006CD2
0x180006cf2  test    edx, edx
0x180006cf4  cmovz   r9d, eax
0x180006cf8  jmp     short loc_180006CE7
0x180006cfa  mov     r10d, eax
0x180006cfd  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006d03  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; unsigned __int64
0x180006d0a  cmp     eax, 20h ; ' '
0x180006d0d  jz      loc_1800074E7
0x180006d13  test    r10d, r10d
0x180006d16  js      loc_180007453
0x180006d1c  movsxd  rax, r10d
0x180006d1f  inc     dword ptr [rdx+rax*8+4]
0x180006d23  mov     r10d, [rdx+rax*8+4]
0x180006d28  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x180006d2f  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006d36  test    byte ptr [rcx+1Ch], 2
0x180006d3a  jnz     loc_18000768C
0x180006d40  mov     r12d, 100h
0x180006d46  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006d4d  mov     edx, r12d
0x180006d50  mov     rax, r10
0x180006d53  cmp     byte ptr [rax], 0
0x180006d56  lea     rdi, asc_1800382D0; ">"
0x180006d5d  mov     ebp, 7FFFFFFEh
0x180006d62  lea     rsi, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006d69  jnz     loc_180007640
0x180006d6f  mov     r8, rsi
0x180006d72  mov     eax, ebp
0x180006d74  sub     r8, rdx
0x180006d77  mov     r9, rdi
0x180006d7a  test    rdx, rdx
0x180006d7d  jz      short loc_180006DA6
0x180006d7f  test    rax, rax
0x180006d82  jz      short loc_180006D9F
0x180006d84  movzx   r10d, byte ptr [r9]
0x180006d88  test    r10b, r10b
0x180006d8b  jz      short loc_180006D9F
0x180006d8d  mov     [r8], r10b
0x180006d90  inc     r9
0x180006d93  inc     r8
0x180006d96  dec     rax
0x180006d99  sub     rdx, 1
0x180006d9d  jnz     short loc_180006D7F
0x180006d9f  lea     r10, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006da6  test    rdx, rdx
0x180006da9  lea     rax, [r8-1]
0x180006dad  cmovnz  rax, r8
0x180006db1  mov     byte ptr [rax], 0
0x180006db4  mov     cs:?WPP_pszIndent@@3PEADEA, r10; char * WPP_pszIndent
0x180006dbb  lea     rax, WPP_GLOBAL_Control
0x180006dc2  cmp     rcx, rax
0x180006dc5  jz      short loc_180006DD1
0x180006dc7  test    byte ptr [rcx+1Ch], 2
0x180006dcb  jnz     loc_1800076C9
0x180006dd1  lea     rcx, ?g_RedirectionContextListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006dd8  call    cs:__imp_EnterCriticalSection
0x180006dde  mov     rbx, cs:?g_pRedirectionContextList@@3PEAU_REDIRECTION_CONTEXT@@EA; _REDIRECTION_CONTEXT * g_pRedirectionContextList
0x180006de5  mov     [rsp+68h+TokenInformation], r14d
0x180006dea  call    cs:__imp_GetCurrentThreadId
0x180006df0  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006df7  lea     r11, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006dfe  mov     r9d, eax
0x180006e01  cmp     r10d, r15d
0x180006e04  jz      loc_180006FE8
0x180006e0a  cmp     r10d, 0FFFFFFFEh
0x180006e0e  jz      short loc_180006E16
0x180006e10  cmp     [r11+r10*8], eax
0x180006e14  jz      short loc_180006E71
0x180006e16  mov     r8d, r15d
0x180006e19  mov     ecx, r14d
0x180006e1c  nop     dword ptr [rax+00h]
0x180006e20  cmp     ecx, 20h ; ' '
0x180006e23  jnb     short loc_180006E6B
0x180006e25  movsxd  rax, ecx
0x180006e28  mov     edx, [r11+rax*8]; unsigned __int64
0x180006e2c  cmp     edx, r9d
0x180006e2f  jz      short loc_180006E5F
0x180006e31  cmp     r8d, r15d
0x180006e34  jz      short loc_180006E57
0x180006e36  inc     ecx
0x180006e38  jmp     short loc_180006E20
0x180006e3a  mov     r10d, r14d
0x180006e3d  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r14d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006e44  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r8d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006e4b  mov     cs:dword_180045874, r14d
0x180006e52  jmp     loc_180006D1C
0x180006e57  test    edx, edx
0x180006e59  cmovz   r8d, ecx
0x180006e5d  jmp     short loc_180006E36
0x180006e5f  mov     r10d, ecx
0x180006e62  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006e68  cmp     ecx, 20h ; ' '
0x180006e6b  jz      loc_18000750B
0x180006e71  test    r10d, r10d
0x180006e74  js      loc_180007465
0x180006e7a  movsxd  rax, r10d
0x180006e7d  inc     dword ptr [r11+rax*8+4]
0x180006e82  mov     r10d, [r11+rax*8+4]
0x180006e87  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x180006e8e  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006e95  test    byte ptr [rcx+1Ch], 2
0x180006e99  jnz     loc_1800076ED
0x180006e9f  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006ea6  mov     rdx, r12
0x180006ea9  mov     rax, r9
0x180006eac  cmp     byte ptr [rax], 0
0x180006eaf  jnz     loc_180007652
0x180006eb5  mov     r8, rsi
0x180006eb8  mov     rax, rbp
0x180006ebb  sub     r8, rdx
0x180006ebe  test    rdx, rdx
0x180006ec1  jz      short loc_180006EEA
0x180006ec3  test    rax, rax
0x180006ec6  jz      short loc_180006EE3
0x180006ec8  movzx   r9d, byte ptr [rdi]
0x180006ecc  test    r9b, r9b
0x180006ecf  jz      short loc_180006EE3
0x180006ed1  mov     [r8], r9b
0x180006ed4  inc     rdi
0x180006ed7  inc     r8
0x180006eda  dec     rax
0x180006edd  sub     rdx, 1
0x180006ee1  jnz     short loc_180006EC3
0x180006ee3  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180006eea  test    rdx, rdx
0x180006eed  lea     rax, [r8-1]
0x180006ef1  cmovnz  rax, r8
0x180006ef5  mov     byte ptr [rax], 0
0x180006ef8  mov     cs:?WPP_pszIndent@@3PEADEA, r9; char * WPP_pszIndent
0x180006eff  lea     rax, WPP_GLOBAL_Control
0x180006f06  cmp     rcx, rax
0x180006f09  jz      short loc_180006F15
0x180006f0b  test    byte ptr [rcx+1Ch], 2
0x180006f0f  jnz     loc_18000772A
0x180006f15  mov     rax, [r13+0]
0x180006f19  test    rax, rax
0x180006f1c  jnz     loc_1800071DD
0x180006f22  mov     [rsp+68h+TokenHandle], r14
0x180006f2a  mov     [rsp+68h+arg_10], r14d
0x180006f32  call    cs:__imp_GetCurrentThread
0x180006f38  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180006f40  mov     edx, 8; DesiredAccess
0x180006f45  mov     rcx, rax; ThreadHandle
0x180006f48  mov     r8d, 1; OpenAsSelf
0x180006f4e  call    cs:__imp_OpenThreadToken
0x180006f54  test    eax, eax
0x180006f56  jnz     short loc_180006F87
0x180006f58  call    cs:__imp_GetLastError
0x180006f5e  mov     ebp, eax
0x180006f60  cmp     eax, 3F0h
0x180006f65  jnz     short loc_180006FC1
0x180006f67  call    cs:__imp_GetCurrentProcess
0x180006f6d  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180006f75  mov     edx, 8; DesiredAccess
0x180006f7a  mov     rcx, rax; ProcessHandle
0x180006f7d  call    cs:__imp_OpenProcessToken
0x180006f83  test    eax, eax
0x180006f85  jz      short loc_180006FB9
0x180006f87  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180006f8f  lea     rax, [rsp+68h+arg_10]
0x180006f97  mov     r9d, 4; TokenInformationLength
0x180006f9d  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180006fa2  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x180006fa7  mov     edx, 0Ch; TokenInformationClass
0x180006fac  mov     ebp, r14d
0x180006faf  call    cs:__imp_GetTokenInformation
0x180006fb5  test    eax, eax
0x180006fb7  jnz     short loc_180006FC1
0x180006fb9  call    cs:__imp_GetLastError
0x180006fbf  mov     ebp, eax
0x180006fc1  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180006fc9  test    rcx, rcx
0x180006fcc  jz      short loc_180006FD4
0x180006fce  call    cs:__imp_CloseHandle
0x180006fd4  test    ebp, ebp
0x180006fd6  jnz     short loc_180007012
0x180006fd8  mov     eax, [rsp+68h+TokenInformation]
0x180006fdc  test    rbx, rbx
0x180006fdf  jnz     short loc_180007005
0x180006fe1  mov     ebp, 490h
0x180006fe6  jmp     short loc_180007012
0x180006fe8  mov     r10d, r14d
0x180006feb  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r14d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x180006ff2  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180006ff9  mov     cs:dword_180045874, r14d
0x180007000  jmp     loc_180006E7A
0x180007005  cmp     eax, [rbx+48h]
0x180007008  jnz     loc_1800071F0
0x18000700e  mov     [r13+0], rbx
0x180007012  call    cs:__imp_GetCurrentThreadId
0x180007018  movsxd  rbx, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000701f  lea     r11, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x180007026  mov     r9d, eax
0x180007029  cmp     ebx, r15d
0x18000702c  jz      loc_180007205
0x180007032  cmp     ebx, 0FFFFFFFEh
0x180007035  jz      short loc_18000703D
0x180007037  cmp     [r11+rbx*8], eax
0x18000703b  jz      short loc_180007076
0x18000703d  mov     r8d, r15d
0x180007040  mov     ecx, r14d
0x180007043  cmp     ecx, 20h ; ' '
0x180007046  jnb     short loc_180007070
0x180007048  movsxd  rax, ecx
0x18000704b  mov     edx, [r11+rax*8]; unsigned __int64
0x18000704f  cmp     edx, r9d
0x180007052  jz      short loc_180007065
0x180007054  cmp     r8d, r15d
0x180007057  jz      short loc_18000705D
0x180007059  inc     ecx
0x18000705b  jmp     short loc_180007043
0x18000705d  test    edx, edx
0x18000705f  cmovz   r8d, ecx
0x180007063  jmp     short loc_180007059
0x180007065  mov     ebx, ecx
0x180007067  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ecx; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000706d  cmp     ecx, 20h ; ' '
0x180007070  jz      loc_18000752F
0x180007076  test    ebx, ebx
0x180007078  js      loc_180007478
0x18000707e  movsxd  rax, ebx
0x180007081  mov     r10d, [r11+rax*8+4]
0x180007086  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18000708d  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x180007094  test    byte ptr [rcx+1Ch], 2
0x180007098  jnz     loc_18000774E
0x18000709e  mov     rdx, r12
0x1800070a1  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x1800070a8  cmp     byte ptr [rax], 0
0x1800070ab  lea     rsi, asc_1800382CC; "<"
0x1800070b2  jnz     loc_180007615
0x1800070b8  lea     rdi, ?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800070bf  mov     r9d, 7FFFFFFEh
0x1800070c5  mov     r8, rdi
0x1800070c8  mov     r10, rsi
0x1800070cb  sub     r8, rdx
0x1800070ce  test    rdx, rdx
0x1800070d1  jz      short loc_1800070F2
0x1800070d3  test    r9, r9
0x1800070d6  jz      short loc_1800070F2
0x1800070d8  movzx   eax, byte ptr [r10]
0x1800070dc  test    al, al
0x1800070de  jz      short loc_1800070F2
0x1800070e0  mov     [r8], al
0x1800070e3  inc     r10
0x1800070e6  inc     r8
0x1800070e9  dec     r9
0x1800070ec  sub     rdx, 1
0x1800070f0  jnz     short loc_1800070D3
0x1800070f2  test    rdx, rdx
0x1800070f5  lea     rax, [r8-1]
0x1800070f9  cmovnz  rax, r8
0x1800070fd  mov     byte ptr [rax], 0
0x180007100  test    ebx, ebx
0x180007102  jns     loc_180007495
0x180007108  lea     rbx, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000710f  mov     cs:?WPP_pszIndent@@3PEADEA, rbx; char * WPP_pszIndent
0x180007116  lea     rax, WPP_GLOBAL_Control
0x18000711d  cmp     rcx, rax
0x180007120  jz      short loc_18000712C
0x180007122  test    byte ptr [rcx+1Ch], 2
0x180007126  jnz     loc_180007664
0x18000712c  cmp     ebp, 490h
0x180007132  jz      loc_18000759B
0x180007138  test    ebp, ebp
  ... truncated ...
```
