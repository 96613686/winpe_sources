# Microsoft::DiagnosticsHub::StandardCollector::AgentController::CommunicateWithAgents(SessionEvent,tagVARIANT const *,tagVARIANT const *,tagVARIANT *)

- ea: `0x18000f1b0`
- end: `0x18000f90f`
- name: `?CommunicateWithAgents@AgentController@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJW4SessionEvent@@PEBUtagVARIANT@@1PEAU6@@Z`
- size: `1887`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003160`
- `0x1800054d0`
- `0x1800062b0`
- `0x180006420`
- `0x18000af70`
- `0x18000b030`
- `0x18000b094`
- `0x18001c3b0`
- `0x18001c978`
- `0x180024494`

## callees

- `0x18000a2d0`
- `0x18000d7ec`
- `0x18000f1b0`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x18000f2bd`
- `VCRUNTIME140!memcmp` at `0x18000f2bd`
- `KERNEL32!LeaveCriticalSection` at `0x18000f4b1`
- `KERNEL32!LeaveCriticalSection` at `0x18000f505`
- `KERNEL32!LeaveCriticalSection` at `0x18000f5ae`
- `KERNEL32!LeaveCriticalSection` at `0x18000f849`
- `KERNEL32!LeaveCriticalSection` at `0x18000f8d6`
- `KERNEL32!LeaveCriticalSection` at `0x18000f904`
- `KERNEL32!LeaveCriticalSection` at `0x18000f4b1`
- `KERNEL32!LeaveCriticalSection` at `0x18000f505`
- `KERNEL32!LeaveCriticalSection` at `0x18000f5ae`
- `KERNEL32!LeaveCriticalSection` at `0x18000f849`
- `KERNEL32!LeaveCriticalSection` at `0x18000f8d6`
- `KERNEL32!LeaveCriticalSection` at `0x18000f904`
- `KERNEL32!EnterCriticalSection` at `0x18000f2e7`
- `KERNEL32!EnterCriticalSection` at `0x18000f3c6`
- `KERNEL32!EnterCriticalSection` at `0x18000f53f`
- `KERNEL32!EnterCriticalSection` at `0x18000f61d`
- `KERNEL32!EnterCriticalSection` at `0x18000f69d`
- `KERNEL32!EnterCriticalSection` at `0x18000f718`
- `KERNEL32!EnterCriticalSection` at `0x18000f7b9`
- `KERNEL32!EnterCriticalSection` at `0x18000f85e`
- `KERNEL32!EnterCriticalSection` at `0x18000f2e7`
- `KERNEL32!EnterCriticalSection` at `0x18000f3c6`
- `KERNEL32!EnterCriticalSection` at `0x18000f53f`
- `KERNEL32!EnterCriticalSection` at `0x18000f61d`
- `KERNEL32!EnterCriticalSection` at `0x18000f69d`
- `KERNEL32!EnterCriticalSection` at `0x18000f718`
- `KERNEL32!EnterCriticalSection` at `0x18000f7b9`
- `KERNEL32!EnterCriticalSection` at `0x18000f85e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f47f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f495`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f526`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f47f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f495`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f526`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f444`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f455`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f4ba`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f444`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f455`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f4ba`
- `OLEAUT32!__imp_VarBstrCat` at `0x18000f46f`
- `OLEAUT32!__imp_VarBstrCat` at `0x18000f46f`

## string_xrefs

- `0x18000f348`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f434`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f596`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f5ed`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f675`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f6f0`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f78c`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f831`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f8be`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\AgentController.cpp`
- `0x18000f42d`: `Removing IStandardCollectorBasicAgent - BeforeProcessLaunch callback failed with 0x%08x`
- `0x18000f341`: `Removing IStandardCollectorBasicAgent - OnStartProfilingProcess callback failed with 0x%08x`
- `0x18000f58f`: `Removing IStandardCollectorBasicAgent2 - OnStopProfilingProcess callback failed with 0x%08x`
- `0x18000f82a`: `Removing IStandardCollectorBasicDebuggerAgent - OnEnterBreakState callback failed with 0x%08x`
- `0x18000f785`: `Removing IStandardCollectorBasicDebuggerAgent - OnExitBreakState callback failed with 0x%08x`
- `0x18000f6e9`: `Removing IStandardCollectorBasicAgent - BeforeSessionStop callback failed with 0x%08x`
- `0x18000f66e`: `Removing IStandardCollectorBasicAgent - OnSessionClose callback failed with 0x%08x`
- `0x18000f5e6`: `CommunicateWithAgents() was called with an unknown SessionEvent.`
- `0x18000f8b7`: `Removing IStandardCollectorEventsCallbackAgent - event callback failed with 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::AgentController::CommunicateWithAgents(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  unsigned int v6; // r12d
  __int64 result; // rax
  unsigned int *v9; // r12
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  _BYTE *v11; // r15
  _BYTE *n; // rdi
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r12
  OLECHAR *v16; // rbx
  _BYTE *v17; // r15
  _BYTE *v18; // rax
  int v19; // eax
  OLECHAR *v20; // r12
  HRESULT v21; // r12d
  OLECHAR *v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rbx
  _BYTE *v24; // r15
  _BYTE *k; // rdi
  int v26; // eax
  _BYTE *v27; // r15
  _BYTE *j; // rdi
  int v29; // eax
  _BYTE *v30; // r15
  _BYTE *i; // rdi
  int v32; // eax
  _BYTE *v33; // rdi
  _BYTE *v34; // r12
  int BreakpointInfo; // r15d
  int v36; // eax
  _BYTE *v37; // rdi
  _BYTE *v38; // r12
  int v39; // eax
  struct _RTL_CRITICAL_SECTION *v40; // rbx
  _BYTE *v41; // r15
  _BYTE *v42; // rdi
  __int64 v43; // rsi
  int v44; // eax
  BSTR bstrString; // [rsp+38h] [rbp-59h] BYREF
  __int64 v47; // [rsp+40h] [rbp-51h]
  __int64 v48; // [rsp+48h] [rbp-49h]
  _BYTE *m; // [rsp+50h] [rbp-41h]
  __int64 v50; // [rsp+58h] [rbp-39h]
  BSTR pbstrResult; // [rsp+60h] [rbp-31h] BYREF
  BSTR pbstr; // [rsp+68h] [rbp-29h] BYREF
  _QWORD Buf1[2]; // [rsp+70h] [rbp-21h] BYREF
  __int128 v54; // [rsp+80h] [rbp-11h] BYREF
  __int64 v55; // [rsp+90h] [rbp-1h]

  v50 = a4;
  v6 = a2;
  if ( *(_BYTE *)(a1 + 689) )
    return 3775987731LL;
  if ( a5 )
  {
    v55 = 0;
    *(_OWORD *)a5 = 0;
    *(_QWORD *)(a5 + 16) = v55;
  }
  if ( a2 > 6 )
  {
    switch ( a2 )
    {
      case 7:
        v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 448);
        Buf1[0] = a1 + 448;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 448));
        v37 = *(_BYTE **)(a1 + 488);
        v38 = *(_BYTE **)(a1 + 496);
        while ( v37 != v38 )
        {
          if ( !v37[8] )
          {
            v54 = 0;
            v55 = 0;
            BreakpointInfo = anonymous_namespace_::GetBreakpointInfo(a3, &v54);
            if ( BreakpointInfo < 0 )
            {
LABEL_102:
              _mm_lfence();
              LeaveCriticalSection(v10);
              return (unsigned int)BreakpointInfo;
            }
            v39 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v37 + 40LL))(*(_QWORD *)v37, &v54);
            if ( v39 < 0 )
            {
              _mm_lfence();
              v37[8] = 1;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 56),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                L"Removing IStandardCollectorBasicDebuggerAgent - OnEnterBreakState callback failed with 0x%08x",
                (unsigned int)v39);
            }
          }
          v37 += 16;
        }
        goto LABEL_93;
      case 8:
        v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 448);
        Buf1[0] = a1 + 448;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 448));
        v33 = *(_BYTE **)(a1 + 488);
        v34 = *(_BYTE **)(a1 + 496);
        while ( v33 != v34 )
        {
          if ( !v33[8] )
          {
            v54 = 0;
            v55 = 0;
            BreakpointInfo = anonymous_namespace_::GetBreakpointInfo(a3, &v54);
            if ( BreakpointInfo < 0 )
              goto LABEL_102;
            v36 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v33 + 48LL))(*(_QWORD *)v33, &v54);
            if ( v36 < 0 )
            {
              _mm_lfence();
              v33[8] = 1;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 56),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                L"Removing IStandardCollectorBasicDebuggerAgent - OnExitBreakState callback failed with 0x%08x",
                (unsigned int)v36);
            }
          }
          v33 += 16;
        }
        goto LABEL_93;
      case 9:
        v23 = (struct _RTL_CRITICAL_SECTION *)(a1 + 384);
        Buf1[0] = a1 + 384;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
        v30 = *(_BYTE **)(a1 + 432);
        for ( i = *(_BYTE **)(a1 + 424); i != v30; i += 16 )
        {
          if ( !i[8] )
          {
            v32 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)i + 56LL))(*(_QWORD *)i);
            if ( v32 < 0 )
            {
              _mm_lfence();
              i[8] = 1;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 56),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                L"Removing IStandardCollectorBasicAgent - BeforeSessionStop callback failed with 0x%08x",
                (unsigned int)v32);
            }
          }
        }
        break;
      case 10:
        if ( !a3 || *(_WORD *)a3 != 11 )
          return 2147942487LL;
        v23 = (struct _RTL_CRITICAL_SECTION *)(a1 + 384);
        Buf1[0] = a1 + 384;
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
        v27 = *(_BYTE **)(a1 + 432);
        for ( j = *(_BYTE **)(a1 + 424); j != v27; j += 16 )
        {
          if ( !j[8] )
          {
            v29 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)j + 64LL))(
                    *(_QWORD *)j,
                    *(unsigned __int16 *)(a3 + 8));
            if ( v29 < 0 )
            {
              _mm_lfence();
              j[8] = 1;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 56),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                L"Removing IStandardCollectorBasicAgent - OnSessionClose callback failed with 0x%08x",
                (unsigned int)v29);
            }
          }
        }
        break;
      default:
        goto LABEL_61;
    }
    goto LABEL_56;
  }
  switch ( a2 )
  {
    case 6:
      v23 = (struct _RTL_CRITICAL_SECTION *)(a1 + 608);
      Buf1[0] = a1 + 608;
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 608));
      v24 = *(_BYTE **)(a1 + 656);
      for ( k = *(_BYTE **)(a1 + 648); k != v24; k += 16 )
      {
        if ( !k[8] )
        {
          v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)k + 72LL))(
                  *(_QWORD *)k,
                  *(unsigned int *)(a3 + 8));
          if ( v26 < 0 )
          {
            _mm_lfence();
            k[8] = 1;
            DiagHubCommon::LogStream::Write(
              (DiagHubCommon::LogStream *)((char *)_logger + 56),
              L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
              L"Removing IStandardCollectorBasicAgent2 - OnStopProfilingProcess callback failed with 0x%08x",
              (unsigned int)v26);
          }
        }
      }
LABEL_56:
      LeaveCriticalSection(v23);
      goto LABEL_95;
    case 1:
    case 2:
      goto LABEL_95;
    case 3:
      if ( a3 && a4 )
      {
        v14 = 0;
        v48 = 0;
        if ( *(_WORD *)a3 == 8 )
        {
          v14 = *(_QWORD *)(a3 + 8);
          v48 = v14;
        }
        v15 = 0;
        v47 = 0;
        if ( *(_WORD *)a4 == 8 )
        {
          v15 = *(_QWORD *)(a4 + 8);
          v47 = v15;
        }
        if ( v14 || v15 )
        {
          v16 = 0;
          bstrString = 0;
          Buf1[0] = a1 + 384;
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
          v17 = *(_BYTE **)(a1 + 424);
          v18 = *(_BYTE **)(a1 + 432);
          for ( m = v18; v17 != v18; v17 += 16 )
          {
            if ( !v17[8] )
            {
              pbstr = 0;
              v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, BSTR *))(**(_QWORD **)v17 + 40LL))(
                      *(_QWORD *)v17,
                      v48,
                      v15,
                      &pbstr);
              if ( v19 < 0 )
              {
                _mm_lfence();
                v17[8] = 1;
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)_logger + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                  L"Removing IStandardCollectorBasicAgent - BeforeProcessLaunch callback failed with 0x%08x",
                  (unsigned int)v19);
              }
              if ( SysStringLen(pbstr) )
              {
                v20 = pbstr;
                if ( SysStringLen(pbstr) )
                {
                  pbstrResult = 0;
                  v21 = VarBstrCat(v16, v20, &pbstrResult);
                  if ( v21 < 0 )
                  {
                    SysFreeString(pbstr);
                    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
                    goto LABEL_46;
                  }
                  SysFreeString(v16);
                  v16 = pbstrResult;
                  bstrString = pbstrResult;
                }
                v15 = v47;
              }
              SysFreeString(pbstr);
              v18 = m;
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
          if ( !SysStringLen(v16) )
          {
            LOWORD(pbstr) = 0;
            v21 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, (const unsigned __int16 *)&pbstr, 1);
            v16 = bstrString;
            if ( v21 < 0 )
            {
LABEL_46:
              SysFreeString(v16);
              return (unsigned int)v21;
            }
          }
          if ( a5 )
          {
            *(_WORD *)a5 = 8;
            v22 = v16;
            v16 = 0;
            *(_QWORD *)(a5 + 8) = v22;
          }
          SysFreeString(v16);
          goto LABEL_94;
        }
      }
      return 2147942487LL;
  }
  if ( a2 != 4 )
  {
    if ( a2 == 5 )
    {
      if ( a3 && *(_WORD *)a3 == 36 )
      {
        result = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a3 + 16) + 48LL))(
                   *(_QWORD *)(a3 + 16),
                   Buf1);
        if ( (int)result < 0
          || (result = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**(_QWORD **)(a3 + 16) + 64LL))(
                         *(_QWORD *)(a3 + 16),
                         &pbstr),
              (int)result < 0) )
        {
          _mm_lfence();
          return result;
        }
        if ( !memcmp(Buf1, &GUID_b4936d6a_893b_4cdc_b4ff_5282c0eae45b, 0x10u) && (_DWORD)pbstr == 16 )
        {
          v9 = *(unsigned int **)(a3 + 8);
          v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 384);
          m = (_BYTE *)(a1 + 384);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
          v11 = *(_BYTE **)(a1 + 432);
          for ( n = *(_BYTE **)(a1 + 424); n != v11; n += 16 )
          {
            if ( !n[8] )
            {
              v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)n + 48LL))(
                      *(_QWORD *)n,
                      *v9,
                      v9[1],
                      *((_QWORD *)v9 + 1));
              if ( v13 < 0 )
              {
                _mm_lfence();
                n[8] = 1;
                DiagHubCommon::LogStream::Write(
                  (DiagHubCommon::LogStream *)((char *)_logger + 56),
                  L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
                  L"Removing IStandardCollectorBasicAgent - OnStartProfilingProcess callback failed with 0x%08x",
                  (unsigned int)v13);
              }
            }
          }
LABEL_93:
          LeaveCriticalSection(v10);
LABEL_94:
          v6 = a2;
          goto LABEL_95;
        }
      }
      return 2147942487LL;
    }
LABEL_61:
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 112),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
      L"CommunicateWithAgents() was called with an unknown SessionEvent.");
    return 2147942487LL;
  }
LABEL_95:
  v40 = (struct _RTL_CRITICAL_SECTION *)(a1 + 112);
  Buf1[0] = a1 + 112;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  v41 = *(_BYTE **)(a1 + 160);
  v42 = *(_BYTE **)(a1 + 152);
  if ( v42 != v41 )
  {
    v43 = v50;
    do
    {
      if ( !v42[8] )
      {
        v44 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)v42 + 40LL))(
                *(_QWORD *)v42,
                v6,
                a3,
                v43);
        if ( v44 < 0 )
        {
          _mm_lfence();
          v42[8] = 1;
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 56),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\AgentController.cpp",
            L"Removing IStandardCollectorEventsCallbackAgent - event callback failed with 0x%08x",
            (unsigned int)v44);
        }
      }
      v42 += 16;
    }
    while ( v42 != v41 );
  }
  LeaveCriticalSection(v40);
  return 0;
}

```

## disassembly

```asm
0x18000f1b0  push    rbp
0x18000f1b2  push    rbx
0x18000f1b3  push    rsi
0x18000f1b4  push    rdi
0x18000f1b5  push    r12
0x18000f1b7  push    r13
0x18000f1b9  push    r14
0x18000f1bb  push    r15
0x18000f1bd  lea     rbp, [rsp-17h]
0x18000f1c2  sub     rsp, 0A8h
0x18000f1c9  mov     rax, cs:__security_cookie
0x18000f1d0  xor     rax, rsp
0x18000f1d3  mov     [rbp+4Fh+var_48], rax
0x18000f1d7  mov     [rbp+4Fh+var_88], r9
0x18000f1db  mov     r14, r8
0x18000f1de  mov     r12d, edx
0x18000f1e1  mov     [rbp+4Fh+var_B0], edx
0x18000f1e4  mov     rsi, rcx
0x18000f1e7  mov     r13, [rbp+4Fh+arg_20]
0x18000f1eb  mov     al, [rcx+2B1h]
0x18000f1f1  xor     r15d, r15d
0x18000f1f4  test    al, al
0x18000f1f6  jz      short loc_18000F202
0x18000f1f8  mov     eax, 0E1110013h
0x18000f1fd  jmp     loc_18000F8DE
0x18000f202  test    r13, r13
0x18000f205  jz      short loc_18000F220
0x18000f207  xorps   xmm0, xmm0
0x18000f20a  xor     eax, eax
0x18000f20c  mov     [rbp+4Fh+var_50], rax
0x18000f210  movups  xmmword ptr [r13+0], xmm0
0x18000f215  movsd   xmm0, [rbp+4Fh+var_50]
0x18000f21a  movsd   qword ptr [r13+10h], xmm0
0x18000f220  cmp     edx, 6
0x18000f223  jg      loc_18000F5B9
0x18000f229  jz      loc_18000F531
0x18000f22f  mov     ecx, edx
0x18000f231  sub     ecx, 1
0x18000f234  jz      loc_18000F853
0x18000f23a  sub     ecx, 1
0x18000f23d  jz      loc_18000F853
0x18000f243  sub     ecx, 1
0x18000f246  jz      loc_18000F362
0x18000f24c  sub     ecx, 1
0x18000f24f  jz      loc_18000F853
0x18000f255  cmp     ecx, 1
0x18000f258  jnz     loc_18000F5DB
0x18000f25e  test    r14, r14
0x18000f261  jz      loc_18000F5F9
0x18000f267  cmp     word ptr [r8], 24h ; '$'
0x18000f26c  jnz     loc_18000F5F9
0x18000f272  mov     rcx, [r8+10h]
0x18000f276  mov     rax, [rcx]
0x18000f279  lea     rdx, [rbp+4Fh+Buf1]
0x18000f27d  mov     rax, [rax+30h]
0x18000f281  call    cs:__guard_dispatch_icall_fptr
0x18000f287  test    eax, eax
0x18000f289  jns     short loc_18000F293
0x18000f28b  lfence
0x18000f28e  jmp     loc_18000F8DE
0x18000f293  mov     rcx, [r14+10h]
0x18000f297  mov     rax, [rcx]
0x18000f29a  lea     rdx, [rbp+4Fh+pbstr]
0x18000f29e  mov     rax, [rax+40h]
0x18000f2a2  call    cs:__guard_dispatch_icall_fptr
0x18000f2a8  test    eax, eax
0x18000f2aa  js      short loc_18000F28B
0x18000f2ac  mov     r8d, 10h; Size
0x18000f2b2  lea     rdx, _GUID_b4936d6a_893b_4cdc_b4ff_5282c0eae45b; Buf2
0x18000f2b9  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000f2bd  call    cs:__imp_memcmp
0x18000f2c3  test    eax, eax
0x18000f2c5  jnz     loc_18000F5F9
0x18000f2cb  cmp     dword ptr [rbp+4Fh+pbstr], 10h
0x18000f2cf  jnz     loc_18000F5F9
0x18000f2d5  mov     r12, [r14+8]
0x18000f2d9  lea     rbx, [rsi+180h]
0x18000f2e0  mov     [rbp+4Fh+var_90], rbx
0x18000f2e4  mov     rcx, rbx; lpCriticalSection
0x18000f2e7  call    cs:__imp_EnterCriticalSection
0x18000f2ed  nop
0x18000f2ee  mov     r15, [rsi+1B0h]
0x18000f2f5  mov     rdi, [rsi+1A8h]
0x18000f2fc  cmp     rdi, r15
0x18000f2ff  jz      short loc_18000F35D
0x18000f301  xor     r13d, r13d
0x18000f304  cmp     [rdi+8], r13b
0x18000f308  jnz     short loc_18000F354
0x18000f30a  mov     rcx, [rdi]
0x18000f30d  mov     rax, [rcx]
0x18000f310  mov     r9, [r12+8]
0x18000f315  mov     r8d, [r12+4]
0x18000f31a  mov     edx, [r12]
0x18000f31e  mov     rax, [rax+30h]
0x18000f322  call    cs:__guard_dispatch_icall_fptr
0x18000f328  test    eax, eax
0x18000f32a  jns     short loc_18000F354
0x18000f32c  lfence
0x18000f32f  mov     byte ptr [rdi+8], 1
0x18000f333  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000f33a  add     rcx, 38h ; '8'; this
0x18000f33e  mov     r9d, eax
0x18000f341  lea     r8, aRemovingIstand_3; "Removing IStandardCollectorBasicAgent -"...
0x18000f348  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000f34f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000f354  add     rdi, 10h
0x18000f358  cmp     rdi, r15
0x18000f35b  jnz     short loc_18000F304
0x18000f35d  jmp     loc_18000F846
0x18000f362  test    r14, r14
0x18000f365  jz      loc_18000F5F9
0x18000f36b  test    r9, r9
0x18000f36e  jz      loc_18000F5F9
0x18000f374  mov     rax, r15
0x18000f377  mov     [rbp+4Fh+var_98], rax
0x18000f37b  mov     ecx, 8
0x18000f380  cmp     [r8], cx
0x18000f384  jnz     short loc_18000F38E
0x18000f386  mov     rax, [r8+8]
0x18000f38a  mov     [rbp+4Fh+var_98], rax
0x18000f38e  mov     r12, r15
0x18000f391  mov     [rbp+4Fh+var_A0], r15
0x18000f395  cmp     [r9], cx
0x18000f399  jnz     short loc_18000F3A3
0x18000f39b  mov     r12, [r9+8]
0x18000f39f  mov     [rbp+4Fh+var_A0], r12
0x18000f3a3  test    rax, rax
0x18000f3a6  jnz     short loc_18000F3B1
0x18000f3a8  test    r12, r12
0x18000f3ab  jz      loc_18000F5F9
0x18000f3b1  mov     rbx, r15
0x18000f3b4  mov     [rbp+4Fh+bstrString], rbx
0x18000f3b8  lea     rdi, [rsi+180h]
0x18000f3bf  mov     [rbp+4Fh+Buf1], rdi
0x18000f3c3  mov     rcx, rdi; lpCriticalSection
0x18000f3c6  call    cs:__imp_EnterCriticalSection
0x18000f3cc  nop
0x18000f3cd  mov     r15, [rsi+1A8h]
0x18000f3d4  mov     rax, [rsi+1B0h]
0x18000f3db  mov     [rbp+4Fh+var_90], rax
0x18000f3df  cmp     r15, rax
0x18000f3e2  jz      loc_18000F4AE
0x18000f3e8  xor     ecx, ecx
0x18000f3ea  cmp     [r15+8], cl
0x18000f3ee  jnz     loc_18000F4A1
0x18000f3f4  mov     [rbp+4Fh+pbstr], rcx
0x18000f3f8  mov     rcx, [r15]
0x18000f3fb  mov     rax, [rcx]
0x18000f3fe  lea     r9, [rbp+4Fh+pbstr]
0x18000f402  mov     r8, r12
0x18000f405  mov     rdx, [rbp+4Fh+var_98]
0x18000f409  mov     rax, [rax+28h]
0x18000f40d  call    cs:__guard_dispatch_icall_fptr
0x18000f413  test    eax, eax
0x18000f415  jns     short loc_18000F440
0x18000f417  lfence
0x18000f41a  mov     byte ptr [r15+8], 1
0x18000f41f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000f426  add     rcx, 38h ; '8'; this
0x18000f42a  mov     r9d, eax
0x18000f42d  lea     r8, aRemovingIstand_6; "Removing IStandardCollectorBasicAgent -"...
0x18000f434  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000f43b  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000f440  mov     rcx, [rbp+4Fh+pbstr]; pbstr
0x18000f444  call    cs:__imp_SysStringLen
0x18000f44a  test    eax, eax
0x18000f44c  jz      short loc_18000F491
0x18000f44e  mov     r12, [rbp+4Fh+pbstr]
0x18000f452  mov     rcx, r12; pbstr
0x18000f455  call    cs:__imp_SysStringLen
0x18000f45b  xor     ecx, ecx
0x18000f45d  test    eax, eax
0x18000f45f  jz      short loc_18000F48D
0x18000f461  mov     [rbp+4Fh+pbstrResult], rcx
0x18000f465  lea     r8, [rbp+4Fh+pbstrResult]; pbstrResult
0x18000f469  mov     rdx, r12; bstrRight
0x18000f46c  mov     rcx, rbx; bstrLeft
0x18000f46f  call    cs:__imp_VarBstrCat
0x18000f475  mov     r12d, eax
0x18000f478  test    eax, eax
0x18000f47a  js      short loc_18000F4F7
0x18000f47c  mov     rcx, rbx; bstrString
0x18000f47f  call    cs:__imp_SysFreeString
0x18000f485  mov     rbx, [rbp+4Fh+pbstrResult]
0x18000f489  mov     [rbp+4Fh+bstrString], rbx
0x18000f48d  mov     r12, [rbp+4Fh+var_A0]
0x18000f491  mov     rcx, [rbp+4Fh+pbstr]; bstrString
0x18000f495  call    cs:__imp_SysFreeString
0x18000f49b  mov     rax, [rbp+4Fh+var_90]
0x18000f49f  xor     ecx, ecx
0x18000f4a1  add     r15, 10h
0x18000f4a5  cmp     r15, rax
0x18000f4a8  jnz     loc_18000F3EA
0x18000f4ae  mov     rcx, rdi; lpCriticalSection
0x18000f4b1  call    cs:__imp_LeaveCriticalSection
0x18000f4b7  mov     rcx, rbx; pbstr
0x18000f4ba  call    cs:__imp_SysStringLen
0x18000f4c0  xor     edi, edi
0x18000f4c2  test    eax, eax
0x18000f4c4  jnz     short loc_18000F50D
0x18000f4c6  mov     word ptr [rbp+4Fh+pbstr], di
0x18000f4ca  lea     r8d, [rdi+1]; int
0x18000f4ce  lea     rdx, [rbp+4Fh+pbstr]; unsigned __int16 *
0x18000f4d2  lea     rcx, [rbp+4Fh+bstrString]; this
0x18000f4d6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18000f4db  mov     r12d, eax
0x18000f4de  mov     rbx, [rbp+4Fh+bstrString]
0x18000f4e2  test    eax, eax
0x18000f4e4  jns     short loc_18000F50D
0x18000f4e6  mov     rcx, rbx; bstrString
0x18000f4e9  call    cs:__imp_SysFreeString
0x18000f4ef  mov     eax, r12d
0x18000f4f2  jmp     loc_18000F8DE
0x18000f4f7  mov     rcx, [rbp+4Fh+pbstr]; bstrString
0x18000f4fb  call    cs:__imp_SysFreeString
0x18000f501  nop
0x18000f502  mov     rcx, rdi; lpCriticalSection
0x18000f505  call    cs:__imp_LeaveCriticalSection
0x18000f50b  jmp     short loc_18000F4E6
0x18000f50d  test    r13, r13
0x18000f510  jz      short loc_18000F523
0x18000f512  mov     word ptr [r13+0], 8
0x18000f519  mov     rax, rbx
0x18000f51c  mov     rbx, rdi
0x18000f51f  mov     [r13+8], rax
0x18000f523  mov     rcx, rbx; bstrString
0x18000f526  call    cs:__imp_SysFreeString
0x18000f52c  jmp     loc_18000F84F
0x18000f531  lea     rbx, [rcx+260h]
0x18000f538  mov     [rbp+4Fh+Buf1], rbx
0x18000f53c  mov     rcx, rbx; lpCriticalSection
0x18000f53f  call    cs:__imp_EnterCriticalSection
0x18000f545  nop
0x18000f546  mov     r15, [rsi+290h]
0x18000f54d  mov     rdi, [rsi+288h]
0x18000f554  cmp     rdi, r15
0x18000f557  jz      short loc_18000F5AB
0x18000f559  xor     r13d, r13d
0x18000f55c  cmp     [rdi+8], r13b
0x18000f560  jnz     short loc_18000F5A2
0x18000f562  mov     rcx, [rdi]
0x18000f565  mov     rax, [rcx]
0x18000f568  mov     edx, [r14+8]
0x18000f56c  mov     rax, [rax+48h]
0x18000f570  call    cs:__guard_dispatch_icall_fptr
0x18000f576  test    eax, eax
0x18000f578  jns     short loc_18000F5A2
0x18000f57a  lfence
0x18000f57d  mov     byte ptr [rdi+8], 1
0x18000f581  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000f588  add     rcx, 38h ; '8'; this
0x18000f58c  mov     r9d, eax
0x18000f58f  lea     r8, aRemovingIstand_0; "Removing IStandardCollectorBasicAgent2 "...
0x18000f596  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000f59d  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000f5a2  add     rdi, 10h
0x18000f5a6  cmp     rdi, r15
0x18000f5a9  jnz     short loc_18000F55C
0x18000f5ab  mov     rcx, rbx; lpCriticalSection
0x18000f5ae  call    cs:__imp_LeaveCriticalSection
0x18000f5b4  jmp     loc_18000F853
0x18000f5b9  mov     ecx, edx
0x18000f5bb  sub     ecx, 7
0x18000f5be  jz      loc_18000F7AB
0x18000f5c4  sub     ecx, 1
0x18000f5c7  jz      loc_18000F70A
0x18000f5cd  sub     ecx, 1
0x18000f5d0  jz      loc_18000F68F
0x18000f5d6  cmp     ecx, 1
0x18000f5d9  jz      short loc_18000F603
0x18000f5db  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000f5e2  add     rcx, 70h ; 'p'; this
0x18000f5e6  lea     r8, aCommunicatewit; "CommunicateWithAgents() was called with"...
0x18000f5ed  lea     rdx, aDAWork1SSource_18; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000f5f4  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000f5f9  mov     eax, 80070057h
0x18000f5fe  jmp     loc_18000F8DE
0x18000f603  test    r14, r14
0x18000f606  jz      short loc_18000F5F9
0x18000f608  cmp     word ptr [r8], 0Bh
0x18000f60d  jnz     short loc_18000F5F9
0x18000f60f  lea     rbx, [rsi+180h]
0x18000f616  mov     [rbp+4Fh+Buf1], rbx
0x18000f61a  mov     rcx, rbx; lpCriticalSection
0x18000f61d  call    cs:__imp_EnterCriticalSection
0x18000f623  nop
0x18000f624  mov     r15, [rsi+1B0h]
0x18000f62b  mov     rdi, [rsi+1A8h]
0x18000f632  cmp     rdi, r15
0x18000f635  jz      short loc_18000F68A
0x18000f637  xor     r13d, r13d
0x18000f63a  cmp     [rdi+8], r13b
0x18000f63e  jnz     short loc_18000F681
0x18000f640  mov     rcx, [rdi]
0x18000f643  mov     rax, [rcx]
0x18000f646  movzx   edx, word ptr [r14+8]
0x18000f64b  mov     rax, [rax+40h]
0x18000f64f  call    cs:__guard_dispatch_icall_fptr
0x18000f655  test    eax, eax
0x18000f657  jns     short loc_18000F681
  ... truncated ...
```
