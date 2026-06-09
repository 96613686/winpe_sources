# MFCreateTranscodeTopologyFromByteStream

- ea: `0x1800019a0`
- end: `0x180002258`
- name: `MFCreateTranscodeTopologyFromByteStream`
- size: `2232`
- prototype: `__int64 __fastcall(__int64, __int64, struct IMFTranscodeProfile *, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002e75c`

## callees

- `0x1800019a0`
- `0x180002260`
- `0x1800035c0`
- `0x180009320`
- `0x180009820`
- `0x18001a330`
- `0x18001c280`
- `0x180035498`
- `0x180037100`
- `0x18004f3c8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001a84`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001a05`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001a05`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001a2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001b14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001bc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001c5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001eab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001f4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000208b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002133`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001a2b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001b14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001bc8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001c5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001cec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001e0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001eab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001f4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001fe5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18000208b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002133`

## string_xrefs

- `0x180001a90`: `MFCreateTranscodeTopologyFromByteStream`
- `0x180001ab6`: `MFCreateTranscodeTopologyFromByteStream`

## pseudocode

```c
__int64 __fastcall MFCreateTranscodeTopologyFromByteStream(
        __int64 a1,
        __int64 a2,
        struct IMFTranscodeProfile *a3,
        _QWORD *a4)
{
  CallStackTracing *v8; // rbx
  char *v9; // rdi
  DWORD LastError; // r14d
  char *Value; // rax
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  int v17; // r14d
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v20; // rdx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  int v27; // eax
  struct IMFTranscodeConfigPriv *v28; // rdi
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rax
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  struct IMFTranscodeManagerPriv *v39; // rbx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *v44; // rax
  int v45; // ecx
  int v46; // ecx
  struct IMFTranscodeManagerPriv *v48; // [rsp+30h] [rbp-38h] BYREF
  struct IMFTranscodeConfigPriv *v49; // [rsp+38h] [rbp-30h] BYREF
  int v50; // [rsp+88h] [rbp+20h] BYREF

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v8 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v9 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v8 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v12 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = (CallStackTracing *)&qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      v14 = (**(__int64 (__fastcall ***)(CallStackTracing *))v12)(v12);
      if ( v14 )
        v9 = (char *)v14;
    }
    SetLastError(LastError);
    v15 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v15 < *((_DWORD *)v9 + 498) )
    {
      v16 = 2 * v15;
      *(_QWORD *)&v9[8 * v16] = "MFCreateTranscodeTopologyFromByteStream";
      *(_DWORD *)&v9[8 * v16 + 8] = 251;
    }
    ++*((_DWORD *)v9 + 497);
  }
  v49 = 0;
  v48 = 0;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    v50 = 1229996372;
    McTemplateU0s4pd_EventWriteTransfer(
      a1,
      (unsigned int)Transcode_Create_Transcode_Topology_Begin,
      (unsigned int)&v50,
      (_DWORD)a4,
      0);
  }
  if ( !a4 )
  {
    v17 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v18;
      if ( !v18 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MFCreateTranscodeTopologyFromByteStream",
          261,
          -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v20 = 38;
LABEL_29:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        0,
        -2147467261);
      goto LABEL_134;
    }
    goto LABEL_134;
  }
  *a4 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v17 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v23;
        if ( !v23 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v24 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v24 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v24, "MFCreateTranscodeTopologyFromByteStream", 265, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v20 = 40;
        goto LABEL_29;
      }
      goto LABEL_134;
    }
    if ( !a3 )
    {
      v17 = -2147467261;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v25;
        if ( !v25 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v26 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v26 + 499) != -2147467261 )
          CallStackContext::TraceFailure(v26, "MFCreateTranscodeTopologyFromByteStream", 266, -2147467261);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v20 = 41;
        goto LABEL_29;
      }
      goto LABEL_134;
    }
    TryDumpTranscodeProfile(a3, L"TranscodeAPI\\DumpProfile");
    v27 = CTranscodeConfig::CreateInstance(&v49);
    v28 = v49;
    v17 = v27;
    if ( v27 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, __int64))(*(_QWORD *)v49 + 24LL))(v49, a1);
      if ( v17 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, __int64))(*(_QWORD *)v28 + 56LL))(v28, a2);
        if ( v17 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, struct IMFTranscodeProfile *))(*(_QWORD *)v28 + 72LL))(
                  v28,
                  a3);
          if ( v17 >= 0 )
          {
            v17 = CTranscodeManager::CreateInstance(&v48);
            if ( v17 >= 0 )
            {
              v39 = v48;
              v17 = (*(__int64 (__fastcall **)(struct IMFTranscodeManagerPriv *, struct IMFTranscodeConfigPriv *))(*(_QWORD *)v48 + 24LL))(
                      v48,
                      v28);
              if ( v17 >= 0 )
              {
                v17 = (*(__int64 (__fastcall **)(struct IMFTranscodeManagerPriv *, _QWORD *))(*(_QWORD *)v39 + 32LL))(
                        v39,
                        a4);
                if ( v17 >= 0 )
                {
LABEL_130:
                  if ( v28 )
                    (*(void (__fastcall **)(struct IMFTranscodeConfigPriv *))(*(_QWORD *)v28 + 16LL))(v28);
                  if ( v39 )
                    (*(void (__fastcall **)(struct IMFTranscodeManagerPriv *))(*(_QWORD *)v39 + 16LL))(v39);
                  goto LABEL_134;
                }
                if ( !CallStackTracing::s_wpInstance )
                {
                  v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v42;
                  if ( !v42
                    || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                  {
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
                {
                  v43 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                  if ( *((_DWORD *)v43 + 499) != v17 )
                    CallStackContext::TraceFailure(v43, "MFCreateTranscodeTopologyFromByteStream", 277, v17);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
LABEL_129:
                  v39 = v48;
                  goto LABEL_130;
                }
                v30 = 48;
              }
              else
              {
                if ( !CallStackTracing::s_wpInstance )
                {
                  v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v40;
                  if ( !v40
                    || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                  {
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
                {
                  v41 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                  if ( *((_DWORD *)v41 + 499) != v17 )
                    CallStackContext::TraceFailure(v41, "MFCreateTranscodeTopologyFromByteStream", 276, v17);
                }
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_129;
                v30 = 47;
              }
            }
            else
            {
              if ( !CallStackTracing::s_wpInstance )
              {
                v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v37;
                if ( !v37
                  || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                {
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
              {
                v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
                if ( *((_DWORD *)v38 + 499) != v17 )
                  CallStackContext::TraceFailure(v38, "MFCreateTranscodeTopologyFromByteStream", 275, v17);
              }
              if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                goto LABEL_129;
              v30 = 46;
            }
          }
          else
          {
            if ( !CallStackTracing::s_wpInstance )
            {
              v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v35;
              if ( !v35
                || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
              {
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
            {
              v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( *((_DWORD *)v36 + 499) != v17 )
                CallStackContext::TraceFailure(v36, "MFCreateTranscodeTopologyFromByteStream", 273, v17);
            }
            if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              goto LABEL_129;
            v30 = 45;
          }
        }
        else
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v33;
            if ( !v33
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)v34 + 499) != v17 )
              CallStackContext::TraceFailure(v34, "MFCreateTranscodeTopologyFromByteStream", 272, v17);
          }
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_129;
          v30 = 44;
        }
      }
      else
      {
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v31;
          if ( !v31 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v32 + 499) != v17 )
            CallStackContext::TraceFailure(v32, "MFCreateTranscodeTopologyFromByteStream", 271, v17);
        }
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_129;
        v30 = 43;
      }
    }
    else
    {
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v29 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v29 + 499) != v17 )
          CallStackContext::TraceFailure(v29, "MFCreateTranscodeTopologyFromByteStream", 270, v17);
      }
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_129;
      v30 = 42;
    }
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, 0, v17);
    goto LABEL_129;
  }
  v17 = -2147467261;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v21;
    if ( !v21 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v22 + 499) != -2147467261 )
      CallStackContext::TraceFailure(v22, "MFCreateTranscodeTopologyFromByteStream", 264, -2147467261);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v20 = 39;
    goto LABEL_29;
  }
LABEL_134:
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v44 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v45 = *((_DWORD *)v44 + 497);
    if ( v45 )
    {
      v46 = v45 - 1;
      *((_DWORD *)v44 + 497) = v46;
      if ( !v46 )
        CallStackContext::ClearState(v44);
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800019a0  mov     rax, rsp
0x1800019a3  push    rbx
0x1800019a4  sub     rsp, 60h
0x1800019a8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x1800019b0  mov     [rax+8], rbp
0x1800019b4  mov     rbp, r8
0x1800019b7  mov     [rax+10h], rsi
0x1800019bb  mov     rsi, r9
0x1800019be  mov     [rax+18h], rdi
0x1800019c2  mov     [rax-10h], r12
0x1800019c6  mov     r12, rcx
0x1800019c9  mov     [rax-28h], r15
0x1800019cd  mov     r15, rdx
0x1800019d0  jnz     short loc_1800019D7
0x1800019d2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800019d7  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800019de  mov     [rsp+68h+var_18], r13
0x1800019e3  mov     [rsp+68h+var_20], r14
0x1800019e8  cmp     byte ptr [rbx+8], 0
0x1800019ec  jz      loc_180001AB6
0x1800019f2  lea     rdi, [rbx+0D0h]
0x1800019f9  call    cs:__imp_GetLastError
0x1800019ff  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180001a02  mov     r14d, eax
0x180001a05  call    cs:__imp_TlsGetValue
0x180001a0b  test    rax, rax
0x180001a0e  jz      short loc_180001A15
0x180001a10  mov     rdi, rax
0x180001a13  jmp     short loc_180001A81
0x180001a15  call    cs:__imp_GetLastError
0x180001a1b  test    eax, eax
0x180001a1d  jnz     short loc_180001A81
0x180001a1f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a26  test    rcx, rcx
0x180001a29  jnz     short loc_180001A6F
0x180001a2b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001a31  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a38  mov     rcx, rax
0x180001a3b  test    rax, rax
0x180001a3e  jz      short loc_180001A5E
0x180001a40  mov     rax, [rax]
0x180001a43  mov     edx, 7F0h
0x180001a48  mov     rax, [rax+8]
0x180001a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a51  test    eax, eax
0x180001a53  jz      short loc_180001A5E
0x180001a55  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a5c  jmp     short loc_180001A6F
0x180001a5e  lea     rax, qword_180069A90
0x180001a65  mov     rcx, rax
0x180001a68  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001a6f  mov     rax, [rcx]
0x180001a72  mov     rax, [rax]
0x180001a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a7a  test    rax, rax
0x180001a7d  cmovnz  rdi, rax
0x180001a81  mov     ecx, r14d; dwErrCode
0x180001a84  call    cs:__imp_SetLastError
0x180001a8a  mov     eax, [rdi+7C4h]
0x180001a90  lea     r13, aMfcreatetransc_5; "MFCreateTranscodeTopologyFromByteStream"
0x180001a97  cmp     eax, [rdi+7C8h]
0x180001a9d  jnb     short loc_180001AAE
0x180001a9f  add     rax, rax
0x180001aa2  mov     [rdi+rax*8], r13
0x180001aa6  mov     dword ptr [rdi+rax*8+8], 0FBh
0x180001aae  inc     dword ptr [rdi+7C4h]
0x180001ab4  jmp     short loc_180001ABD
0x180001ab6  lea     r13, aMfcreatetransc_5; "MFCreateTranscodeTopologyFromByteStream"
0x180001abd  xor     edi, edi
0x180001abf  lea     rbx, qword_180069A90
0x180001ac6  test    cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, 1
0x180001acd  mov     [rsp+68h+var_30], rdi
0x180001ad2  mov     [rsp+68h+var_38], rdi
0x180001ad7  jz      short loc_180001AFC
0x180001ad9  lea     r8, [rsp+68h+arg_18]
0x180001ae1  mov     [rsp+68h+arg_18], 49504154h
0x180001aec  lea     rdx, Transcode_Create_Transcode_Topology_Begin
0x180001af3  mov     [rsp+68h+var_48], edi
0x180001af7  call    McTemplateU0s4pd_EventWriteTransfer
0x180001afc  test    rsi, rsi
0x180001aff  jnz     loc_180001BAD
0x180001b05  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180001b0c  mov     r14d, 80004003h
0x180001b12  jnz     short loc_180001B45
0x180001b14  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001b1a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001b21  mov     rcx, rax
0x180001b24  test    rax, rax
0x180001b27  jz      short loc_180001B3E
0x180001b29  mov     rax, [rax]
0x180001b2c  mov     edx, 7F0h
0x180001b31  mov     rax, [rax+8]
0x180001b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b3a  test    eax, eax
0x180001b3c  jnz     short loc_180001B45
0x180001b3e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001b45  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001b4c  cmp     [rbx+8], dil
0x180001b50  jz      short loc_180001B77
0x180001b52  mov     rcx, rbx; this
0x180001b55  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001b5a  cmp     [rax+7CCh], r14d
0x180001b61  jz      short loc_180001B77
0x180001b63  mov     r9d, r14d; int
0x180001b66  mov     r8d, 105h; int
0x180001b6c  mov     rdx, r13; char *
0x180001b6f  mov     rcx, rax; this
0x180001b72  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001b77  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001b7c  cmp     al, 1
0x180001b7e  jb      loc_1800021F7
0x180001b84  mov     edx, 26h ; '&'
0x180001b89  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b90  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180001b97  xor     r9d, r9d
0x180001b9a  mov     [rsp+68h+var_48], r14d
0x180001b9f  mov     rcx, [rcx+10h]
0x180001ba3  call    WPP_SF_qd
0x180001ba8  jmp     loc_1800021F7
0x180001bad  mov     [rsi], rdi
0x180001bb0  test    r12, r12
0x180001bb3  jnz     loc_180001C42
0x180001bb9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180001bc0  mov     r14d, 80004003h
0x180001bc6  jnz     short loc_180001BF9
0x180001bc8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001bce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001bd5  mov     rcx, rax
0x180001bd8  test    rax, rax
0x180001bdb  jz      short loc_180001BF2
0x180001bdd  mov     rax, [rax]
0x180001be0  mov     edx, 7F0h
0x180001be5  mov     rax, [rax+8]
0x180001be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bee  test    eax, eax
0x180001bf0  jnz     short loc_180001BF9
0x180001bf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001bf9  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c00  cmp     [rbx+8], dil
0x180001c04  jz      short loc_180001C2B
0x180001c06  mov     rcx, rbx; this
0x180001c09  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001c0e  cmp     [rax+7CCh], r14d
0x180001c15  jz      short loc_180001C2B
0x180001c17  mov     r9d, r14d; int
0x180001c1a  mov     r8d, 108h; int
0x180001c20  mov     rdx, r13; char *
0x180001c23  mov     rcx, rax; this
0x180001c26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001c2b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001c30  cmp     al, 1
0x180001c32  jb      loc_1800021F7
0x180001c38  mov     edx, 27h ; '''
0x180001c3d  jmp     loc_180001B89
0x180001c42  test    r15, r15
0x180001c45  jnz     loc_180001CD4
0x180001c4b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c52  mov     r14d, 80004003h
0x180001c58  jnz     short loc_180001C8B
0x180001c5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001c60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c67  mov     rcx, rax
0x180001c6a  test    rax, rax
0x180001c6d  jz      short loc_180001C84
0x180001c6f  mov     rax, [rax]
0x180001c72  mov     edx, 7F0h
0x180001c77  mov     rax, [rax+8]
0x180001c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c80  test    eax, eax
0x180001c82  jnz     short loc_180001C8B
0x180001c84  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c8b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001c92  cmp     [rbx+8], dil
0x180001c96  jz      short loc_180001CBD
0x180001c98  mov     rcx, rbx; this
0x180001c9b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001ca0  cmp     [rax+7CCh], r14d
0x180001ca7  jz      short loc_180001CBD
0x180001ca9  mov     r9d, r14d; int
0x180001cac  mov     r8d, 109h; int
0x180001cb2  mov     rdx, r13; char *
0x180001cb5  mov     rcx, rax; this
0x180001cb8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001cbd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001cc2  cmp     al, 1
0x180001cc4  jb      loc_1800021F7
0x180001cca  mov     edx, 28h ; '('
0x180001ccf  jmp     loc_180001B89
0x180001cd4  test    rbp, rbp
0x180001cd7  jnz     loc_180001D66
0x180001cdd  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180001ce4  mov     r14d, 80004003h
0x180001cea  jnz     short loc_180001D1D
0x180001cec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001cf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001cf9  mov     rcx, rax
0x180001cfc  test    rax, rax
0x180001cff  jz      short loc_180001D16
0x180001d01  mov     rax, [rax]
0x180001d04  mov     edx, 7F0h
0x180001d09  mov     rax, [rax+8]
0x180001d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d12  test    eax, eax
0x180001d14  jnz     short loc_180001D1D
0x180001d16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001d1d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001d24  cmp     [rbx+8], dil
0x180001d28  jz      short loc_180001D4F
0x180001d2a  mov     rcx, rbx; this
0x180001d2d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001d32  cmp     [rax+7CCh], r14d
0x180001d39  jz      short loc_180001D4F
0x180001d3b  mov     r9d, r14d; int
0x180001d3e  mov     r8d, 10Ah; int
0x180001d44  mov     rdx, r13; char *
0x180001d47  mov     rcx, rax; this
0x180001d4a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001d4f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001d54  cmp     al, 1
0x180001d56  jb      loc_1800021F7
0x180001d5c  mov     edx, 29h ; ')'
0x180001d61  jmp     loc_180001B89
0x180001d66  lea     rdx, aTranscodeapiDu; "TranscodeAPI\\DumpProfile"
0x180001d6d  mov     rcx, rbp; struct IMFTranscodeProfile *
0x180001d70  call    ?TryDumpTranscodeProfile@@YAJPEAUIMFTranscodeProfile@@PEBG@Z; TryDumpTranscodeProfile(IMFTranscodeProfile *,ushort const *)
0x180001d75  lea     rcx, [rsp+68h+var_30]; struct IMFTranscodeConfigPriv **
0x180001d7a  call    ?CreateInstance@CTranscodeConfig@@SAJPEAPEAUIMFTranscodeConfigPriv@@@Z; CTranscodeConfig::CreateInstance(IMFTranscodeConfigPriv * *)
0x180001d7f  mov     rdi, [rsp+68h+var_30]
0x180001d84  mov     r14d, eax
0x180001d87  test    eax, eax
0x180001d89  jns     short loc_180001DE3
0x180001d8b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180001d93  jnz     short loc_180001D9A
0x180001d95  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180001d9a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001da1  cmp     byte ptr [rbx+8], 0
0x180001da5  jz      short loc_180001DCC
0x180001da7  mov     rcx, rbx; this
0x180001daa  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001daf  cmp     [rax+7CCh], r14d
0x180001db6  jz      short loc_180001DCC
0x180001db8  mov     r9d, r14d; int
0x180001dbb  mov     r8d, 10Eh; int
0x180001dc1  mov     rdx, r13; char *
0x180001dc4  mov     rcx, rax; this
0x180001dc7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001dcc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001dd1  cmp     al, 1
0x180001dd3  jb      loc_1800021CA
0x180001dd9  mov     edx, 2Ah ; '*'
0x180001dde  jmp     loc_1800021AB
0x180001de3  mov     rax, [rdi]
0x180001de6  mov     rdx, r12
0x180001de9  mov     rcx, rdi
0x180001dec  mov     rax, [rax+18h]
0x180001df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001df5  mov     r14d, eax
0x180001df8  test    eax, eax
0x180001dfa  jns     loc_180001E84
0x180001e00  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e08  jnz     short loc_180001E3B
0x180001e0a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001e10  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e17  mov     rcx, rax
0x180001e1a  test    rax, rax
0x180001e1d  jz      short loc_180001E34
0x180001e1f  mov     rax, [rax]
0x180001e22  mov     edx, 7F0h
0x180001e27  mov     rax, [rax+8]
0x180001e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e30  test    eax, eax
0x180001e32  jnz     short loc_180001E3B
0x180001e34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e3b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001e42  cmp     byte ptr [rbx+8], 0
0x180001e46  jz      short loc_180001E6D
0x180001e48  mov     rcx, rbx; this
0x180001e4b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180001e50  cmp     [rax+7CCh], r14d
0x180001e57  jz      short loc_180001E6D
0x180001e59  mov     r9d, r14d; int
0x180001e5c  mov     r8d, 10Fh; int
0x180001e62  mov     rdx, r13; char *
0x180001e65  mov     rcx, rax; this
0x180001e68  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180001e6d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180001e72  cmp     al, 1
0x180001e74  jb      loc_1800021CA
0x180001e7a  mov     edx, 2Bh ; '+'
0x180001e7f  jmp     loc_1800021AB
0x180001e84  mov     rax, [rdi]
0x180001e87  mov     rdx, r15
0x180001e8a  mov     rcx, rdi
0x180001e8d  mov     rax, [rax+38h]
0x180001e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e96  mov     r14d, eax
0x180001e99  test    eax, eax
0x180001e9b  jns     loc_180001F25
0x180001ea1  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180001ea9  jnz     short loc_180001EDC
  ... truncated ...
```
