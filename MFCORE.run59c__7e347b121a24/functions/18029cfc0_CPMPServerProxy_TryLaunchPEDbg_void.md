# CPMPServerProxy::TryLaunchPEDbg(void)

- ea: `0x18029cfc0`
- end: `0x18029da35`
- name: `?TryLaunchPEDbg@CPMPServerProxy@@IEAAXXZ`
- size: `2677`
- prototype: `void __fastcall(CPMPServerProxy *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180187f24`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800cf174`
- `0x1800ec0e0`
- `0x18025839c`
- `0x1802583e8`
- `0x1802592a0`
- `0x18029cfc0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18029d411`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18029d90e`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18029d411`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18029d90e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d4db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d9e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029da00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d4db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029d9e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029da00`
- `MFPlat!MFGetConfigurationString` at `0x18029d036`
- `MFPlat!MFGetConfigurationString` at `0x18029d1ba`
- `MFPlat!MFGetConfigurationString` at `0x18029d515`
- `MFPlat!MFGetConfigurationString` at `0x18029d699`
- `MFPlat!MFGetConfigurationString` at `0x18029d036`
- `MFPlat!MFGetConfigurationString` at `0x18029d1ba`
- `MFPlat!MFGetConfigurationString` at `0x18029d515`
- `MFPlat!MFGetConfigurationString` at `0x18029d699`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d1dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d29e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d357`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d431`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d5fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d6bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d77d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d83b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d92e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d058`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d11e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d1dc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d29e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d357`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d431`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d537`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d5fd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d6bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d77d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d83b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18029d92e`

## pseudocode

```c
void __fastcall CPMPServerProxy::TryLaunchPEDbg(CPMPServerProxy *this)
{
  unsigned __int16 *v2; // rsi
  unsigned __int16 *v3; // r14
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  unsigned __int16 *v9; // rax
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  unsigned __int16 *v16; // rax
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  unsigned __int16 *v29; // rax
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  unsigned __int16 *v36; // rax
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-49h] BYREF
  char v48; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned int v49; // [rsp+130h] [rbp+77h] BYREF

  v49 = 0;
  v2 = 0;
  v3 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v48, "CPMPServerProxy::TryLaunchPEDbg", 1723);
  v4 = MFGetConfigurationString(1, L"Platform\\PEDbg1", 0, &v49);
  if ( v4 >= 0 )
  {
    if ( v49 <= 1 )
      goto LABEL_140;
    v9 = (unsigned __int16 *)operator new[](saturated_mul(v49, 2u));
    v2 = v9;
    if ( v9 )
    {
      v4 = MFGetConfigurationString(1, L"Platform\\PEDbg1", v9, &v49);
      if ( v4 >= 0 )
      {
        v16 = (unsigned __int16 *)operator new[](saturated_mul(v49 + 256, 2u));
        v3 = v16;
        if ( v16 )
        {
          v4 = StringCchPrintfW(v16, v49 + 256, v2, *((unsigned int *)this + 19));
          if ( v4 >= 0 )
          {
            if ( CreateProcessW(0, v3, 0, 0, 1, 0x40000u, 0, 0, &StartupInfo, &ProcessInformation) )
            {
              operator delete(v2);
              v2 = 0;
              operator delete(v3);
              v3 = 0;
              if ( ProcessInformation.hProcess )
              {
                CloseHandle(ProcessInformation.hProcess);
                ProcessInformation.hProcess = 0;
              }
              if ( ProcessInformation.hThread )
              {
                CloseHandle(ProcessInformation.hThread);
                ProcessInformation.hThread = 0;
              }
              v4 = MFGetConfigurationString(1, L"Platform\\PEDbg2", 0, &v49);
              if ( v4 >= 0 )
              {
                if ( v49 <= 1 )
                  goto LABEL_140;
                v29 = (unsigned __int16 *)operator new[](saturated_mul(v49, 2u));
                v2 = v29;
                if ( v29 )
                {
                  v4 = MFGetConfigurationString(1, L"Platform\\PEDbg2", v29, &v49);
                  if ( v4 >= 0 )
                  {
                    v36 = (unsigned __int16 *)operator new[](saturated_mul(v49 + 256, 2u));
                    v3 = v36;
                    if ( v36 )
                    {
                      v4 = StringCchPrintfW(v36, v49 + 256, v2);
                      if ( v4 >= 0 )
                      {
                        memset_0(&StartupInfo, 0, sizeof(StartupInfo));
                        memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                        if ( !CreateProcessW(0, v3, 0, 0, 1, 0, 0, 0, &StartupInfo, &ProcessInformation) )
                        {
                          v43 = (__int64 *)CallStackTracing::s_wpInstance;
                          if ( !CallStackTracing::s_wpInstance )
                          {
                            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                            CallStackTracing::s_wpInstance = v44;
                            if ( v44
                              && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(
                                   v44,
                                   2032) )
                            {
                              v43 = (__int64 *)CallStackTracing::s_wpInstance;
                            }
                            else
                            {
                              v43 = &qword_1803CE250;
                              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                            }
                          }
                          v4 = -2147467259;
                          if ( *((_BYTE *)v43 + 8) )
                          {
                            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                            if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467259 )
                              CallStackContext::TraceFailure(
                                ThreadRelativeContext,
                                "CPMPServerProxy::TryLaunchPEDbg",
                                1845,
                                -2147467259);
                          }
                          if ( g_wppLevels )
                          {
                            v8 = 119;
                            goto LABEL_139;
                          }
                        }
                      }
                      else
                      {
                        v40 = (__int64 *)CallStackTracing::s_wpInstance;
                        if ( !CallStackTracing::s_wpInstance )
                        {
                          v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                          CallStackTracing::s_wpInstance = v41;
                          if ( v41
                            && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(
                                 v41,
                                 2032) )
                          {
                            v40 = (__int64 *)CallStackTracing::s_wpInstance;
                          }
                          else
                          {
                            v40 = &qword_1803CE250;
                            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                          }
                        }
                        if ( *((_BYTE *)v40 + 8) )
                        {
                          v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                          if ( *((_DWORD *)v42 + 499) != v4 )
                            CallStackContext::TraceFailure(v42, "CPMPServerProxy::TryLaunchPEDbg", 1826, v4);
                        }
                        if ( g_wppLevels )
                        {
                          v8 = 118;
                          goto LABEL_139;
                        }
                      }
                    }
                    else
                    {
                      v37 = (__int64 *)CallStackTracing::s_wpInstance;
                      if ( !CallStackTracing::s_wpInstance )
                      {
                        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                        CallStackTracing::s_wpInstance = v38;
                        if ( v38
                          && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(
                               v38,
                               2032) )
                        {
                          v37 = (__int64 *)CallStackTracing::s_wpInstance;
                        }
                        else
                        {
                          v37 = &qword_1803CE250;
                          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                        }
                      }
                      v4 = -2147024882;
                      if ( *((_BYTE *)v37 + 8) )
                      {
                        v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
                        if ( *((_DWORD *)v39 + 499) != -2147024882 )
                          CallStackContext::TraceFailure(v39, "CPMPServerProxy::TryLaunchPEDbg", 1815, -2147024882);
                      }
                      if ( g_wppLevels )
                      {
                        v8 = 117;
                        goto LABEL_139;
                      }
                    }
                  }
                  else
                  {
                    v33 = (__int64 *)CallStackTracing::s_wpInstance;
                    if ( !CallStackTracing::s_wpInstance )
                    {
                      v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                      CallStackTracing::s_wpInstance = v34;
                      if ( v34
                        && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(
                             v34,
                             2032) )
                      {
                        v33 = (__int64 *)CallStackTracing::s_wpInstance;
                      }
                      else
                      {
                        v33 = &qword_1803CE250;
                        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                      }
                    }
                    if ( *((_BYTE *)v33 + 8) )
                    {
                      v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
                      if ( *((_DWORD *)v35 + 499) != v4 )
                        CallStackContext::TraceFailure(v35, "CPMPServerProxy::TryLaunchPEDbg", 1810, v4);
                    }
                    if ( g_wppLevels )
                    {
                      v8 = 116;
                      goto LABEL_139;
                    }
                  }
                }
                else
                {
                  v30 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                    CallStackTracing::s_wpInstance = v31;
                    if ( v31
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
                    {
                      v30 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v30 = &qword_1803CE250;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                    }
                  }
                  v4 = -2147024882;
                  if ( *((_BYTE *)v30 + 8) )
                  {
                    v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                    if ( *((_DWORD *)v32 + 499) != -2147024882 )
                      CallStackContext::TraceFailure(v32, "CPMPServerProxy::TryLaunchPEDbg", 1803, -2147024882);
                  }
                  if ( g_wppLevels )
                  {
                    v8 = 115;
                    goto LABEL_139;
                  }
                }
              }
              else
              {
                v26 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v27;
                  if ( v27
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
                  {
                    v26 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v26 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v26 + 8) )
                {
                  v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
                  if ( *((_DWORD *)v28 + 499) != v4 )
                    CallStackContext::TraceFailure(v28, "CPMPServerProxy::TryLaunchPEDbg", 1790, v4);
                }
                if ( g_wppLevels )
                {
                  v8 = 114;
                  goto LABEL_139;
                }
              }
            }
            else
            {
              v23 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v24;
                if ( v24
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
                {
                  v23 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v23 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              v4 = -2147467259;
              if ( *((_BYTE *)v23 + 8) )
              {
                v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
                if ( *((_DWORD *)v25 + 499) != -2147467259 )
                  CallStackContext::TraceFailure(v25, "CPMPServerProxy::TryLaunchPEDbg", 1778, -2147467259);
              }
              if ( g_wppLevels )
              {
                v8 = 113;
                goto LABEL_139;
              }
            }
          }
          else
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)v22 + 499) != v4 )
                CallStackContext::TraceFailure(v22, "CPMPServerProxy::TryLaunchPEDbg", 1761, v4);
            }
            if ( g_wppLevels )
            {
              v8 = 112;
              goto LABEL_139;
            }
          }
        }
        else
        {
          v17 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v18;
            if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
            {
              v17 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v17 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          v4 = -2147024882;
          if ( *((_BYTE *)v17 + 8) )
          {
            v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
            if ( *((_DWORD *)v19 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v19, "CPMPServerProxy::TryLaunchPEDbg", 1754, -2147024882);
          }
          if ( g_wppLevels )
          {
            v8 = 111;
            goto LABEL_139;
          }
        }
      }
      else
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v13 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v13 + 8) )
        {
          v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
          if ( *((_DWORD *)v15 + 499) != v4 )
            CallStackContext::TraceFailure(v15, "CPMPServerProxy::TryLaunchPEDbg", 1743, v4);
        }
        if ( g_wppLevels )
        {
          v8 = 110;
          goto LABEL_139;
        }
      }
    }
    else
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v11;
        if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
        {
          v10 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v10 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      v4 = -2147024882;
      if ( *((_BYTE *)v10 + 8) )
      {
        v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
        if ( *((_DWORD *)v12 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v12, "CPMPServerProxy::TryLaunchPEDbg", 1736, -2147024882);
      }
      if ( g_wppLevels )
      {
        v8 = 109;
        goto LABEL_139;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CPMPServerProxy::TryLaunchPEDbg", 1723, v4);
    }
    if ( g_wppLevels )
    {
      v8 = 108;
LABEL_139:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_1ede33fc6d933efc25e43a6be7416609_Traceguids, this, v4);
    }
  }
LABEL_140:
  operator delete(v2);
  operator delete(v3);
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( ProcessInformation.hThread )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v48);
}

```

## disassembly

```asm
0x18029cfc0  mov     [rsp-8+arg_0], rbx
0x18029cfc5  push    rbp
0x18029cfc6  push    rsi
0x18029cfc7  push    rdi
0x18029cfc8  push    r12
0x18029cfca  push    r13
0x18029cfcc  push    r14
0x18029cfce  push    r15
0x18029cfd0  lea     rbp, [rsp-27h]
0x18029cfd5  sub     rsp, 0E0h
0x18029cfdc  xor     r15d, r15d
0x18029cfdf  mov     rdi, rcx
0x18029cfe2  xor     edx, edx; Val
0x18029cfe4  mov     [rbp+57h+arg_10], r15d
0x18029cfe8  lea     rcx, [rbp+57h+StartupInfo]; void *
0x18029cfec  mov     esi, r15d
0x18029cfef  mov     r14d, r15d
0x18029cff2  lea     r8d, [r15+68h]; Size
0x18029cff6  call    memset_0
0x18029cffb  xorps   xmm0, xmm0
0x18029cffe  lea     r13, aCpmpserverprox_7; "CPMPServerProxy::TryLaunchPEDbg"
0x18029d005  xor     eax, eax
0x18029d007  lea     rcx, [rbp+57h+arg_8]; this
0x18029d00b  mov     rdx, r13; char *
0x18029d00e  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18029d012  mov     r8d, 6BBh; int
0x18029d018  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18029d01c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18029d021  lea     r12d, [r15+1]
0x18029d025  xor     r8d, r8d
0x18029d028  mov     ecx, r12d
0x18029d02b  lea     r9, [rbp+57h+arg_10]
0x18029d02f  lea     rdx, aPlatformPedbg1; "Platform\\PEDbg1"
0x18029d036  call    cs:__imp_MFGetConfigurationString
0x18029d03d  nop     dword ptr [rax+rax+00h]
0x18029d042  mov     ebx, eax
0x18029d044  test    eax, eax
0x18029d046  jns     loc_18029D0DE
0x18029d04c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d053  test    rcx, rcx
0x18029d056  jnz     short loc_18029D0A0
0x18029d058  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d05f  nop     dword ptr [rax+rax+00h]
0x18029d064  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d06b  mov     rcx, rax
0x18029d06e  test    rax, rax
0x18029d071  jz      short loc_18029D092
0x18029d073  mov     rax, [rax]
0x18029d076  mov     edx, 7F0h
0x18029d07b  mov     rax, [rax+8]
0x18029d07f  call    cs:__guard_dispatch_icall_fptr
0x18029d085  test    eax, eax
0x18029d087  jz      short loc_18029D092
0x18029d089  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d090  jmp     short loc_18029D0A0
0x18029d092  lea     rcx, qword_1803CE250; this
0x18029d099  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d0a0  cmp     [rcx+8], r15b
0x18029d0a4  jz      short loc_18029D0C7
0x18029d0a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d0ab  cmp     [rax+7CCh], ebx
0x18029d0b1  jz      short loc_18029D0C7
0x18029d0b3  mov     r9d, ebx; int
0x18029d0b6  mov     r8d, 6BBh; int
0x18029d0bc  mov     rdx, r13; char *
0x18029d0bf  mov     rcx, rax; this
0x18029d0c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d0c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d0ce  jb      loc_18029D9CE
0x18029d0d4  mov     edx, 6Ch ; 'l'
0x18029d0d9  jmp     loc_18029D9B0
0x18029d0de  cmp     [rbp+57h+arg_10], r12d
0x18029d0e2  jbe     loc_18029D9CE
0x18029d0e8  mov     ecx, [rbp+57h+arg_10]
0x18029d0eb  mov     eax, 2
0x18029d0f0  mul     rcx
0x18029d0f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18029d0fa  cmovb   rax, rcx
0x18029d0fe  mov     rcx, rax; unsigned __int64
0x18029d101  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18029d106  mov     rsi, rax
0x18029d109  test    rax, rax
0x18029d10c  jnz     loc_18029D1A9
0x18029d112  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d119  test    rcx, rcx
0x18029d11c  jnz     short loc_18029D166
0x18029d11e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d125  nop     dword ptr [rax+rax+00h]
0x18029d12a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d131  mov     rcx, rax
0x18029d134  test    rax, rax
0x18029d137  jz      short loc_18029D158
0x18029d139  mov     rax, [rax]
0x18029d13c  mov     edx, 7F0h
0x18029d141  mov     rax, [rax+8]
0x18029d145  call    cs:__guard_dispatch_icall_fptr
0x18029d14b  test    eax, eax
0x18029d14d  jz      short loc_18029D158
0x18029d14f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d156  jmp     short loc_18029D166
0x18029d158  lea     rcx, qword_1803CE250; this
0x18029d15f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d166  mov     ebx, 8007000Eh
0x18029d16b  cmp     [rcx+8], r15b
0x18029d16f  jz      short loc_18029D192
0x18029d171  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d176  cmp     [rax+7CCh], ebx
0x18029d17c  jz      short loc_18029D192
0x18029d17e  mov     r9d, ebx; int
0x18029d181  mov     r8d, 6C8h; int
0x18029d187  mov     rdx, r13; char *
0x18029d18a  mov     rcx, rax; this
0x18029d18d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d192  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d199  jb      loc_18029D9CE
0x18029d19f  mov     edx, 6Dh ; 'm'
0x18029d1a4  jmp     loc_18029D9B0
0x18029d1a9  lea     r9, [rbp+57h+arg_10]
0x18029d1ad  mov     r8, rsi
0x18029d1b0  lea     rdx, aPlatformPedbg1; "Platform\\PEDbg1"
0x18029d1b7  mov     ecx, r12d
0x18029d1ba  call    cs:__imp_MFGetConfigurationString
0x18029d1c1  nop     dword ptr [rax+rax+00h]
0x18029d1c6  mov     ebx, eax
0x18029d1c8  test    eax, eax
0x18029d1ca  jns     loc_18029D262
0x18029d1d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d1d7  test    rcx, rcx
0x18029d1da  jnz     short loc_18029D224
0x18029d1dc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d1e3  nop     dword ptr [rax+rax+00h]
0x18029d1e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d1ef  mov     rcx, rax
0x18029d1f2  test    rax, rax
0x18029d1f5  jz      short loc_18029D216
0x18029d1f7  mov     rax, [rax]
0x18029d1fa  mov     edx, 7F0h
0x18029d1ff  mov     rax, [rax+8]
0x18029d203  call    cs:__guard_dispatch_icall_fptr
0x18029d209  test    eax, eax
0x18029d20b  jz      short loc_18029D216
0x18029d20d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d214  jmp     short loc_18029D224
0x18029d216  lea     rcx, qword_1803CE250; this
0x18029d21d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d224  cmp     [rcx+8], r15b
0x18029d228  jz      short loc_18029D24B
0x18029d22a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d22f  cmp     [rax+7CCh], ebx
0x18029d235  jz      short loc_18029D24B
0x18029d237  mov     r9d, ebx; int
0x18029d23a  mov     r8d, 6CFh; int
0x18029d240  mov     rdx, r13; char *
0x18029d243  mov     rcx, rax; this
0x18029d246  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d24b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d252  jb      loc_18029D9CE
0x18029d258  mov     edx, 6Eh ; 'n'
0x18029d25d  jmp     loc_18029D9B0
0x18029d262  mov     ecx, [rbp+57h+arg_10]
0x18029d265  mov     eax, 2
0x18029d26a  add     ecx, 100h
0x18029d270  mul     rcx
0x18029d273  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18029d27a  cmovb   rax, rcx
0x18029d27e  mov     rcx, rax; unsigned __int64
0x18029d281  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18029d286  mov     r14, rax
0x18029d289  test    rax, rax
0x18029d28c  jnz     loc_18029D329
0x18029d292  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d299  test    rcx, rcx
0x18029d29c  jnz     short loc_18029D2E6
0x18029d29e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d2a5  nop     dword ptr [rax+rax+00h]
0x18029d2aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d2b1  mov     rcx, rax
0x18029d2b4  test    rax, rax
0x18029d2b7  jz      short loc_18029D2D8
0x18029d2b9  mov     rax, [rax]
0x18029d2bc  mov     edx, 7F0h
0x18029d2c1  mov     rax, [rax+8]
0x18029d2c5  call    cs:__guard_dispatch_icall_fptr
0x18029d2cb  test    eax, eax
0x18029d2cd  jz      short loc_18029D2D8
0x18029d2cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d2d6  jmp     short loc_18029D2E6
0x18029d2d8  lea     rcx, qword_1803CE250; this
0x18029d2df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d2e6  mov     ebx, 8007000Eh
0x18029d2eb  cmp     [rcx+8], r15b
0x18029d2ef  jz      short loc_18029D312
0x18029d2f1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d2f6  cmp     [rax+7CCh], ebx
0x18029d2fc  jz      short loc_18029D312
0x18029d2fe  mov     r9d, ebx; int
0x18029d301  mov     r8d, 6DAh; int
0x18029d307  mov     rdx, r13; char *
0x18029d30a  mov     rcx, rax; this
0x18029d30d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d312  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d319  jb      loc_18029D9CE
0x18029d31f  mov     edx, 6Fh ; 'o'
0x18029d324  jmp     loc_18029D9B0
0x18029d329  mov     edx, [rbp+57h+arg_10]
0x18029d32c  mov     r8, rsi; unsigned __int16 *
0x18029d32f  mov     r9d, [rdi+4Ch]
0x18029d333  add     edx, 100h; unsigned __int64
0x18029d339  mov     rcx, r14; unsigned __int16 *
0x18029d33c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18029d341  mov     ebx, eax
0x18029d343  test    eax, eax
0x18029d345  jns     loc_18029D3DD
0x18029d34b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d352  test    rcx, rcx
0x18029d355  jnz     short loc_18029D39F
0x18029d357  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d35e  nop     dword ptr [rax+rax+00h]
0x18029d363  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d36a  mov     rcx, rax
0x18029d36d  test    rax, rax
0x18029d370  jz      short loc_18029D391
0x18029d372  mov     rax, [rax]
0x18029d375  mov     edx, 7F0h
0x18029d37a  mov     rax, [rax+8]
0x18029d37e  call    cs:__guard_dispatch_icall_fptr
0x18029d384  test    eax, eax
0x18029d386  jz      short loc_18029D391
0x18029d388  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d38f  jmp     short loc_18029D39F
0x18029d391  lea     rcx, qword_1803CE250; this
0x18029d398  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d39f  cmp     [rcx+8], r15b
0x18029d3a3  jz      short loc_18029D3C6
0x18029d3a5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d3aa  cmp     [rax+7CCh], ebx
0x18029d3b0  jz      short loc_18029D3C6
0x18029d3b2  mov     r9d, ebx; int
0x18029d3b5  mov     r8d, 6E1h; int
0x18029d3bb  mov     rdx, r13; char *
0x18029d3be  mov     rcx, rax; this
0x18029d3c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d3c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d3cd  jb      loc_18029D9CE
0x18029d3d3  mov     edx, 70h ; 'p'
0x18029d3d8  jmp     loc_18029D9B0
0x18029d3dd  lea     rax, [rbp+57h+ProcessInformation]
0x18029d3e1  xor     r9d, r9d; lpThreadAttributes
0x18029d3e4  mov     [rsp+110h+lpProcessInformation], rax; lpProcessInformation
0x18029d3e9  xor     r8d, r8d; lpProcessAttributes
0x18029d3ec  lea     rax, [rbp+57h+StartupInfo]
0x18029d3f0  mov     rdx, r14; lpCommandLine
0x18029d3f3  mov     [rsp+110h+lpStartupInfo], rax; lpStartupInfo
0x18029d3f8  xor     ecx, ecx; lpApplicationName
0x18029d3fa  mov     [rsp+110h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18029d3ff  mov     [rsp+110h+lpEnvironment], r15; lpEnvironment
0x18029d404  mov     [rsp+110h+dwCreationFlags], 40000h; dwCreationFlags
0x18029d40c  mov     [rsp+110h+bInheritHandles], r12d; bInheritHandles
0x18029d411  call    cs:__imp_CreateProcessW
0x18029d418  nop     dword ptr [rax+rax+00h]
0x18029d41d  test    eax, eax
0x18029d41f  jnz     loc_18029D4BC
0x18029d425  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d42c  test    rcx, rcx
0x18029d42f  jnz     short loc_18029D479
0x18029d431  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18029d438  nop     dword ptr [rax+rax+00h]
0x18029d43d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d444  mov     rcx, rax
0x18029d447  test    rax, rax
0x18029d44a  jz      short loc_18029D46B
0x18029d44c  mov     rax, [rax]
0x18029d44f  mov     edx, 7F0h
0x18029d454  mov     rax, [rax+8]
0x18029d458  call    cs:__guard_dispatch_icall_fptr
0x18029d45e  test    eax, eax
0x18029d460  jz      short loc_18029D46B
0x18029d462  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d469  jmp     short loc_18029D479
0x18029d46b  lea     rcx, qword_1803CE250; this
0x18029d472  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18029d479  mov     ebx, 80004005h
0x18029d47e  cmp     [rcx+8], r15b
0x18029d482  jz      short loc_18029D4A5
0x18029d484  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18029d489  cmp     [rax+7CCh], ebx
0x18029d48f  jz      short loc_18029D4A5
0x18029d491  mov     r9d, ebx; int
0x18029d494  mov     r8d, 6F2h; int
0x18029d49a  mov     rdx, r13; char *
0x18029d49d  mov     rcx, rax; this
0x18029d4a0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18029d4a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x18029d4ac  jb      loc_18029D9CE
0x18029d4b2  mov     edx, 71h ; 'q'
0x18029d4b7  jmp     loc_18029D9B0
0x18029d4bc  mov     rcx, rsi; Block
0x18029d4bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18029d4c4  mov     rcx, r14; Block
0x18029d4c7  mov     rsi, r15
  ... truncated ...
```
