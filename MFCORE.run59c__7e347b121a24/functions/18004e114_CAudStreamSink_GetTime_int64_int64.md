# CAudStreamSink::GetTime(__int64 *,__int64 *)

- ea: `0x18004e114`
- end: `0x18004e90a`
- name: `?GetTime@CAudStreamSink@@QEAAJPEA_J0@Z`
- size: `2038`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18004d9a0`
- `0x18031d560`

## callees

- `0x18001616c`
- `0x18001b9b0`
- `0x1800402c0`
- `0x18004d16c`
- `0x18004d1cc`
- `0x18004e114`
- `0x18004e910`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180258480`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e27d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e3c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e557`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e59b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e5df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e623`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e19f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e2a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e3f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e4a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e19f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e2a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e3f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e4a3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e185`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e28e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e3d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e489`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e185`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e28e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e3d6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004e489`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e670`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e72a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e866`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e670`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e72a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004e866`

## string_xrefs

- `0x18004e269`: `CAudStreamSink::GetStreamState`
- `0x18004e2ba`: `CAudStreamSink::GetStreamState`
- `0x18004e7b7`: `CAudStreamSink::GetStreamState`
- `0x18004e15c`: `CAudStreamSink::GetTime`
- `0x18004e6af`: `CAudStreamSink::GetTime`
- `0x18004e846`: `CAudStreamSink::GetTime`
- `0x18004e8f3`: `CAudStreamSink::GetTime`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::GetTime(CAudStreamSink *this, __int64 *a2, __int64 *a3)
{
  CallStackTracing *v3; // rdi
  __int64 *v4; // r15
  __int64 *v5; // r13
  char *v7; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v10; // rax
  CallStackTracing *v11; // rdi
  __int64 v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v14; // ebx
  __int128 v15; // xmm0
  __int64 v16; // rdx
  __int64 v17; // rcx
  int ExactTime; // edi
  __int64 v19; // r8
  CallStackTracing *v20; // rbx
  char *v21; // rdi
  DWORD v22; // ebp
  char *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  struct CallStackContext *v26; // rdi
  int v27; // ebx
  __int128 v28; // xmm0
  CallStackTracing *v29; // rcx
  int v30; // r15d
  CallStackTracing *v31; // rbx
  CallStackContext *v32; // rbp
  DWORD v33; // r13d
  CallStackContext *v34; // rax
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rbx
  CallStackTracing *v41; // rbx
  CallStackContext *v42; // rsi
  DWORD v43; // ebp
  CallStackContext *v44; // rax
  int v45; // eax
  int v46; // eax
  CallStackTracing *v48; // rcx
  __int64 v49; // rax
  CallStackTracing *v50; // rcx
  __int64 v51; // rax
  CallStackTracing *v52; // rcx
  __int64 v53; // rax
  CallStackTracing *v54; // rcx
  __int64 v55; // rax
  CallStackTracing *v56; // rax
  struct CallStackContext *v57; // rax
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  CallStackTracing *v60; // rax
  __int64 v61; // rdx
  struct CallStackContext *v62; // rax
  CallStackTracing *v63; // rax
  struct CallStackContext *v64; // rax
  int v66; // [rsp+38h] [rbp-70h] BYREF
  __int64 v67; // [rsp+40h] [rbp-68h] BYREF
  __int64 *v68; // [rsp+48h] [rbp-60h]
  _BYTE v69[16]; // [rsp+50h] [rbp-58h] BYREF

  v3 = CallStackTracing::s_wpInstance;
  v4 = a3;
  v68 = a2;
  v5 = a2;
  v67 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v48 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v48 = CallStackTracing::s_wpInstance;
      }
      v49 = (**(__int64 (__fastcall ***)(CallStackTracing *))v48)(v48);
      if ( v49 )
        v7 = (char *)v49;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    v11 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v12 = 2 * v10;
      *(_QWORD *)&v7[8 * v12] = "CAudStreamSink::GetTime";
      *(_DWORD *)&v7[8 * v12 + 8] = 4008;
    }
    ++*((_DWORD *)v7 + 497);
    if ( *((_BYTE *)v11 + 8) && *((_QWORD *)this + 825) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
      v15 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                         *((_QWORD *)this + 825),
                         v69);
      *((_DWORD *)ThreadRelativeContext + 504) = v14;
      *((_OWORD *)ThreadRelativeContext + 125) = v15;
    }
  }
  ExactTime = CAudStreamSink::GetExactTime(this, v5, &v67);
  if ( ExactTime >= 0 )
  {
    v66 = 0;
    if ( !CallStackTracing::s_wpInstance )
      CallStackTracing::InitInstance();
    v20 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v21 = (char *)CallStackTracing::s_wpInstance + 208;
      v22 = GetLastError();
      v23 = (char *)TlsGetValue(*((_DWORD *)v20 + 3));
      if ( v23 )
      {
        v21 = v23;
      }
      else if ( !GetLastError() )
      {
        v50 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v50 = CallStackTracing::s_wpInstance;
        }
        v51 = (**(__int64 (__fastcall ***)(CallStackTracing *))v50)(v50);
        if ( v51 )
          v21 = (char *)v51;
      }
      SetLastError(v22);
      v24 = *((unsigned int *)v21 + 497);
      if ( (unsigned int)v24 < *((_DWORD *)v21 + 498) )
      {
        v25 = 2 * v24;
        *(_QWORD *)&v21[8 * v25] = "CAudStreamSink::GetStreamState";
        *(_DWORD *)&v21[8 * v25 + 8] = 7097;
      }
      ++*((_DWORD *)v21 + 497);
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
      v28 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                         *((_QWORD *)this + 825),
                         v69);
      *((_DWORD *)v26 + 504) = v27;
      *((_OWORD *)v26 + 125) = v28;
    }
    v29 = *(CallStackTracing **)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 384);
    if ( !v29 || *((_DWORD *)this + 64) || *((_DWORD *)this + 1354) )
    {
      v30 = *((_DWORD *)this + 1628);
      ExactTime = 0;
    }
    else
    {
      ExactTime = (*(__int64 (__fastcall **)(CallStackTracing *, int *))(*(_QWORD *)v29 + 24LL))(v29, &v66);
      if ( ExactTime < 0 )
      {
        v30 = 0;
        if ( !CallStackTracing::s_wpInstance )
        {
          v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v29, v16, v19);
          CallStackTracing::s_wpInstance = v58;
          v29 = v58;
          if ( !v58 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
        if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
        {
          v59 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
          if ( *((_DWORD *)v59 + 499) != ExactTime )
            CallStackContext::TraceFailure(v59, "CAudStreamSink::GetStreamState", 7112, ExactTime);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            456,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            this,
            ExactTime);
      }
      else
      {
        v30 = v66;
        *((_DWORD *)this + 1628) = v66;
      }
    }
    v31 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v32 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
      v33 = GetLastError();
      v34 = (CallStackContext *)TlsGetValue(*((_DWORD *)v31 + 3));
      if ( v34 )
      {
        v32 = v34;
      }
      else if ( !GetLastError() )
      {
        v52 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v52 = CallStackTracing::s_wpInstance;
        }
        v53 = (**(__int64 (__fastcall ***)(CallStackTracing *))v52)(v52);
        if ( v53 )
          v32 = (CallStackContext *)v53;
      }
      SetLastError(v33);
      v5 = v68;
      v35 = *((_DWORD *)v32 + 497);
      if ( v35 )
      {
        v36 = v35 - 1;
        *((_DWORD *)v32 + 497) = v36;
        if ( !v36 )
          CallStackContext::ClearState(v32);
      }
    }
    if ( ExactTime < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
      {
        v60 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v29, v16, v19);
        CallStackTracing::s_wpInstance = v60;
        if ( !v60 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v62 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v62 + 499) != ExactTime )
          CallStackContext::TraceFailure(v62, "CAudStreamSink::GetTime", 4010, ExactTime);
      }
      if ( !g_wppLevels )
        goto LABEL_37;
      v61 = 274;
    }
    else
    {
      if ( v30 != 2 )
        goto LABEL_37;
      ExactTime = CAudStreamSink::TryRemoveClockJitter(this, v5, &v67);
      if ( ExactTime >= 0 )
        goto LABEL_37;
      if ( !CallStackTracing::s_wpInstance )
      {
        v63 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v38, v37, v39);
        CallStackTracing::s_wpInstance = v63;
        if ( !v63 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v63 + 8LL))(v63, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v64 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v64 + 499) != ExactTime )
          CallStackContext::TraceFailure(v64, "CAudStreamSink::GetTime", 4014, ExactTime);
      }
      if ( !g_wppLevels )
        goto LABEL_37;
      v61 = 275;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v61,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      ExactTime);
LABEL_37:
    v4 = a3;
    goto LABEL_38;
  }
  if ( !CallStackTracing::s_wpInstance )
  {
    v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v17, v16, v19);
    CallStackTracing::s_wpInstance = v56;
    if ( !v56 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v57 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v57 + 499) != ExactTime )
      CallStackContext::TraceFailure(v57, "CAudStreamSink::GetTime", 4008, ExactTime);
  }
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      273,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      ExactTime);
LABEL_38:
  v40 = v67;
  if ( (unsigned __int8)byte_1803CECE9 >= 0x20u )
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      276,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      *v5,
      v67);
  if ( v4 )
    *v4 = v40;
  v41 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v42 = (CallStackTracing *)((char *)CallStackTracing::s_wpInstance + 208);
    v43 = GetLastError();
    v44 = (CallStackContext *)TlsGetValue(*((_DWORD *)v41 + 3));
    if ( v44 )
    {
      v42 = v44;
    }
    else if ( !GetLastError() )
    {
      v54 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v54 = CallStackTracing::s_wpInstance;
      }
      v55 = (**(__int64 (__fastcall ***)(CallStackTracing *))v54)(v54);
      if ( v55 )
        v42 = (CallStackContext *)v55;
    }
    SetLastError(v43);
    v45 = *((_DWORD *)v42 + 497);
    if ( v45 )
    {
      v46 = v45 - 1;
      *((_DWORD *)v42 + 497) = v46;
      if ( !v46 )
        CallStackContext::ClearState(v42);
    }
  }
  return (unsigned int)ExactTime;
}

```

## disassembly

```asm
0x18004e114  push    rbx
0x18004e116  push    rbp
0x18004e117  push    rsi
0x18004e118  push    rdi
0x18004e119  push    r13
0x18004e11b  push    r14
0x18004e11d  push    r15
0x18004e11f  sub     rsp, 70h
0x18004e123  mov     rax, cs:__security_cookie
0x18004e12a  xor     rax, rsp
0x18004e12d  mov     [rsp+0A8h+var_48], rax
0x18004e132  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e139  xor     ebp, ebp
0x18004e13b  mov     [rsp+0A8h+var_78], r8
0x18004e140  mov     r15, r8
0x18004e143  mov     [rsp+0A8h+var_60], rdx
0x18004e148  mov     r13, rdx
0x18004e14b  mov     [rsp+0A8h+var_68], rbp
0x18004e150  mov     rsi, rcx
0x18004e153  test    rdi, rdi
0x18004e156  jz      loc_18004E53C
0x18004e15c  lea     r14, aCaudstreamsink_91; "CAudStreamSink::GetTime"
0x18004e163  cmp     [rdi+8], bpl
0x18004e167  jz      loc_18004E237
0x18004e16d  lea     rbx, [rdi+0D0h]
0x18004e174  call    cs:__imp_GetLastError
0x18004e17b  nop     dword ptr [rax+rax+00h]
0x18004e180  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18004e183  mov     ebp, eax
0x18004e185  call    cs:__imp_TlsGetValue
0x18004e18c  nop     dword ptr [rax+rax+00h]
0x18004e191  test    rax, rax
0x18004e194  jz      loc_18004E557
0x18004e19a  mov     rbx, rax
0x18004e19d  mov     ecx, ebp; dwErrCode
0x18004e19f  call    cs:__imp_SetLastError
0x18004e1a6  nop     dword ptr [rax+rax+00h]
0x18004e1ab  mov     eax, [rbx+7C4h]
0x18004e1b1  xor     ebp, ebp
0x18004e1b3  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e1ba  cmp     eax, [rbx+7C8h]
0x18004e1c0  jnb     short loc_18004E1D1
0x18004e1c2  add     rax, rax
0x18004e1c5  mov     [rbx+rax*8], r14
0x18004e1c9  mov     dword ptr [rbx+rax*8+8], 0FA8h
0x18004e1d1  inc     dword ptr [rbx+7C4h]
0x18004e1d7  cmp     [rdi+8], bpl
0x18004e1db  jz      short loc_18004E237
0x18004e1dd  cmp     [rsi+19C8h], rbp
0x18004e1e4  jz      short loc_18004E237
0x18004e1e6  mov     rcx, rdi; this
0x18004e1e9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e1ee  mov     rcx, [rsi+19C8h]
0x18004e1f5  mov     rdi, rax
0x18004e1f8  mov     rdx, [rcx]
0x18004e1fb  mov     rax, [rdx+128h]
0x18004e202  call    cs:__guard_dispatch_icall_fptr
0x18004e208  mov     rcx, [rsi+19C8h]
0x18004e20f  mov     ebx, eax
0x18004e211  mov     rdx, [rcx]
0x18004e214  mov     rax, [rdx+118h]
0x18004e21b  lea     rdx, [rsp+0A8h+var_58]
0x18004e220  call    cs:__guard_dispatch_icall_fptr
0x18004e226  movups  xmm0, xmmword ptr [rax]
0x18004e229  mov     [rdi+7E0h], ebx
0x18004e22f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004e237  lea     r8, [rsp+0A8h+var_68]; __int64 *
0x18004e23c  mov     rdx, r13; __int64 *
0x18004e23f  mov     rcx, rsi; this
0x18004e242  call    ?GetExactTime@CAudStreamSink@@IEAAJPEA_J0@Z; CAudStreamSink::GetExactTime(__int64 *,__int64 *)
0x18004e247  mov     edi, eax
0x18004e249  test    eax, eax
0x18004e24b  js      loc_18004E667
0x18004e251  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e258  mov     [rsp+0A8h+var_70], ebp
0x18004e25c  jz      loc_18004E54D
0x18004e262  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e269  lea     rcx, aCaudstreamsink_5; "CAudStreamSink::GetStreamState"
0x18004e270  cmp     [rbx+8], bpl
0x18004e274  jz      short loc_18004E2E0
0x18004e276  lea     rdi, [rbx+0D0h]
0x18004e27d  call    cs:__imp_GetLastError
0x18004e284  nop     dword ptr [rax+rax+00h]
0x18004e289  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004e28c  mov     ebp, eax
0x18004e28e  call    cs:__imp_TlsGetValue
0x18004e295  nop     dword ptr [rax+rax+00h]
0x18004e29a  test    rax, rax
0x18004e29d  jz      loc_18004E59B
0x18004e2a3  mov     rdi, rax
0x18004e2a6  mov     ecx, ebp; dwErrCode
0x18004e2a8  call    cs:__imp_SetLastError
0x18004e2af  nop     dword ptr [rax+rax+00h]
0x18004e2b4  mov     eax, [rdi+7C4h]
0x18004e2ba  lea     rcx, aCaudstreamsink_5; "CAudStreamSink::GetStreamState"
0x18004e2c1  xor     ebp, ebp
0x18004e2c3  cmp     eax, [rdi+7C8h]
0x18004e2c9  jnb     short loc_18004E2DA
0x18004e2cb  add     rax, rax
0x18004e2ce  mov     [rdi+rax*8], rcx
0x18004e2d2  mov     dword ptr [rdi+rax*8+8], 1BB9h
0x18004e2da  inc     dword ptr [rdi+7C4h]
0x18004e2e0  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e2e7  cmp     [rbx+8], bpl
0x18004e2eb  jz      short loc_18004E347
0x18004e2ed  cmp     [rsi+19C8h], rbp
0x18004e2f4  jz      short loc_18004E347
0x18004e2f6  mov     rcx, rbx; this
0x18004e2f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004e2fe  mov     rcx, [rsi+19C8h]
0x18004e305  mov     rdi, rax
0x18004e308  mov     rdx, [rcx]
0x18004e30b  mov     rax, [rdx+128h]
0x18004e312  call    cs:__guard_dispatch_icall_fptr
0x18004e318  mov     rcx, [rsi+19C8h]
0x18004e31f  mov     ebx, eax
0x18004e321  mov     rdx, [rcx]
0x18004e324  mov     rax, [rdx+118h]
0x18004e32b  lea     rdx, [rsp+0A8h+var_58]
0x18004e330  call    cs:__guard_dispatch_icall_fptr
0x18004e336  movups  xmm0, xmmword ptr [rax]
0x18004e339  mov     [rdi+7E0h], ebx
0x18004e33f  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18004e347  mov     rax, [rsi+178h]
0x18004e34e  lea     r14, qword_1803CE250
0x18004e355  movsxd  rcx, dword ptr [rax+4]
0x18004e359  mov     rcx, [rcx+rsi+180h]
0x18004e361  test    rcx, rcx
0x18004e364  jz      loc_18004E4E5
0x18004e36a  cmp     [rsi+100h], ebp
0x18004e370  jnz     loc_18004E4E5
0x18004e376  cmp     [rsi+1528h], ebp
0x18004e37c  jnz     loc_18004E4E5
0x18004e382  mov     rax, [rcx]
0x18004e385  lea     rdx, [rsp+0A8h+var_70]
0x18004e38a  mov     rax, [rax+18h]
0x18004e38e  call    cs:__guard_dispatch_icall_fptr
0x18004e394  mov     edi, eax
0x18004e396  test    eax, eax
0x18004e398  js      loc_18004E71E
0x18004e39e  mov     r15d, [rsp+0A8h+var_70]
0x18004e3a3  mov     [rsi+1970h], r15d
0x18004e3aa  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e3b1  cmp     [rbx+8], bpl
0x18004e3b5  jz      short loc_18004E41D
0x18004e3b7  cmp     byte ptr [rbx+8], 0
0x18004e3bb  lea     rbp, [rbx+0D0h]
0x18004e3c2  jz      short loc_18004E402
0x18004e3c4  call    cs:__imp_GetLastError
0x18004e3cb  nop     dword ptr [rax+rax+00h]
0x18004e3d0  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004e3d3  mov     r13d, eax
0x18004e3d6  call    cs:__imp_TlsGetValue
0x18004e3dd  nop     dword ptr [rax+rax+00h]
0x18004e3e2  test    rax, rax
0x18004e3e5  jz      loc_18004E5DF
0x18004e3eb  mov     rbp, rax
0x18004e3ee  mov     ecx, r13d; dwErrCode
0x18004e3f1  call    cs:__imp_SetLastError
0x18004e3f8  nop     dword ptr [rax+rax+00h]
0x18004e3fd  mov     r13, [rsp+0A8h+var_60]
0x18004e402  mov     eax, [rbp+7C4h]
0x18004e408  test    eax, eax
0x18004e40a  jz      short loc_18004E41B
0x18004e40c  sub     eax, 1
0x18004e40f  mov     [rbp+7C4h], eax
0x18004e415  jz      loc_18004E4F3
0x18004e41b  xor     ebp, ebp
0x18004e41d  test    edi, edi
0x18004e41f  js      loc_18004E7CE
0x18004e425  cmp     r15d, 2
0x18004e429  jnz     short loc_18004E445
0x18004e42b  lea     r8, [rsp+0A8h+var_68]; __int64 *
0x18004e430  mov     rdx, r13; __int64 *
0x18004e433  mov     rcx, rsi; this
0x18004e436  call    ?TryRemoveClockJitter@CAudStreamSink@@IEAAJPEA_J0@Z; CAudStreamSink::TryRemoveClockJitter(__int64 *,__int64 *)
0x18004e43b  mov     edi, eax
0x18004e43d  test    eax, eax
0x18004e43f  js      loc_18004E85D
0x18004e445  mov     r15, [rsp+0A8h+var_78]
0x18004e44a  cmp     cs:byte_1803CECE9, 20h ; ' '
0x18004e451  mov     rbx, [rsp+0A8h+var_68]
0x18004e456  jnb     loc_18004E50A
0x18004e45c  test    r15, r15
0x18004e45f  jz      short loc_18004E464
0x18004e461  mov     [r15], rbx
0x18004e464  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e46b  cmp     [rbx+8], bpl
0x18004e46f  jz      short loc_18004E4C6
0x18004e471  lea     rsi, [rbx+0D0h]
0x18004e478  call    cs:__imp_GetLastError
0x18004e47f  nop     dword ptr [rax+rax+00h]
0x18004e484  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18004e487  mov     ebp, eax
0x18004e489  call    cs:__imp_TlsGetValue
0x18004e490  nop     dword ptr [rax+rax+00h]
0x18004e495  test    rax, rax
0x18004e498  jz      loc_18004E623
0x18004e49e  mov     rsi, rax
0x18004e4a1  mov     ecx, ebp; dwErrCode
0x18004e4a3  call    cs:__imp_SetLastError
0x18004e4aa  nop     dword ptr [rax+rax+00h]
0x18004e4af  mov     eax, [rsi+7C4h]
0x18004e4b5  xor     ebp, ebp
0x18004e4b7  test    eax, eax
0x18004e4b9  jz      short loc_18004E4C6
0x18004e4bb  sub     eax, 1
0x18004e4be  mov     [rsi+7C4h], eax
0x18004e4c4  jz      short loc_18004E500
0x18004e4c6  mov     eax, edi
0x18004e4c8  mov     rcx, [rsp+0A8h+var_48]
0x18004e4cd  xor     rcx, rsp; StackCookie
0x18004e4d0  call    __security_check_cookie
0x18004e4d5  add     rsp, 70h
0x18004e4d9  pop     r15
0x18004e4db  pop     r14
0x18004e4dd  pop     r13
0x18004e4df  pop     rdi
0x18004e4e0  pop     rsi
0x18004e4e1  pop     rbp
0x18004e4e2  pop     rbx
0x18004e4e3  retn
0x18004e4e5  mov     r15d, [rsi+1970h]
0x18004e4ec  mov     edi, ebp
0x18004e4ee  jmp     loc_18004E3AA
0x18004e4f3  mov     rcx, rbp; this
0x18004e4f6  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18004e4fb  jmp     loc_18004E41B
0x18004e500  mov     rcx, rsi; this
0x18004e503  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x18004e508  jmp     short loc_18004E4C6
0x18004e50a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e511  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18004e518  mov     rax, [r13+0]
0x18004e51c  mov     edx, 114h
0x18004e521  mov     [rsp+0A8h+var_80], rbx
0x18004e526  mov     r9, rsi
0x18004e529  mov     [rsp+0A8h+var_88], rax
0x18004e52e  mov     rcx, [rcx+38h]
0x18004e532  call    WPP_SF_qqq
0x18004e537  jmp     loc_18004E45C
0x18004e53c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e541  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e548  jmp     loc_18004E15C
0x18004e54d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e552  jmp     loc_18004E262
0x18004e557  call    cs:__imp_GetLastError
0x18004e55e  nop     dword ptr [rax+rax+00h]
0x18004e563  test    eax, eax
0x18004e565  jnz     loc_18004E19D
0x18004e56b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e572  test    rcx, rcx
0x18004e575  jnz     short loc_18004E583
0x18004e577  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e57c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e583  mov     rax, [rcx]
0x18004e586  mov     rax, [rax]
0x18004e589  call    cs:__guard_dispatch_icall_fptr
0x18004e58f  test    rax, rax
0x18004e592  cmovnz  rbx, rax
0x18004e596  jmp     loc_18004E19D
0x18004e59b  call    cs:__imp_GetLastError
0x18004e5a2  nop     dword ptr [rax+rax+00h]
0x18004e5a7  test    eax, eax
0x18004e5a9  jnz     loc_18004E2A6
0x18004e5af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5b6  test    rcx, rcx
0x18004e5b9  jnz     short loc_18004E5C7
0x18004e5bb  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e5c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5c7  mov     rax, [rcx]
0x18004e5ca  mov     rax, [rax]
0x18004e5cd  call    cs:__guard_dispatch_icall_fptr
0x18004e5d3  test    rax, rax
0x18004e5d6  cmovnz  rdi, rax
0x18004e5da  jmp     loc_18004E2A6
0x18004e5df  call    cs:__imp_GetLastError
0x18004e5e6  nop     dword ptr [rax+rax+00h]
0x18004e5eb  test    eax, eax
0x18004e5ed  jnz     loc_18004E3EE
0x18004e5f3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e5fa  test    rcx, rcx
0x18004e5fd  jnz     short loc_18004E60B
0x18004e5ff  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e604  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e60b  mov     rax, [rcx]
0x18004e60e  mov     rax, [rax]
0x18004e611  call    cs:__guard_dispatch_icall_fptr
0x18004e617  test    rax, rax
0x18004e61a  cmovnz  rbp, rax
0x18004e61e  jmp     loc_18004E3EE
0x18004e623  call    cs:__imp_GetLastError
0x18004e62a  nop     dword ptr [rax+rax+00h]
0x18004e62f  test    eax, eax
0x18004e631  jnz     loc_18004E4A1
0x18004e637  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004e63e  test    rcx, rcx
0x18004e641  jnz     short loc_18004E64F
0x18004e643  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004e648  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
