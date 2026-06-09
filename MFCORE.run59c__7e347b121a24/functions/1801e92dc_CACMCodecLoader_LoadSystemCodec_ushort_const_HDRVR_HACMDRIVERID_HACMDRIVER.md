# CACMCodecLoader::LoadSystemCodec(ushort const *,HDRVR__ * *,HACMDRIVERID__ * *,HACMDRIVER__ * *)

- ea: `0x1801e92dc`
- end: `0x1801e9eca`
- name: `?LoadSystemCodec@CACMCodecLoader@@IEAAJPEBGPEAPEAUHDRVR__@@PEAPEAUHACMDRIVERID__@@PEAPEAUHACMDRIVER__@@@Z`
- size: `3054`
- prototype: `int(CACMCodecLoader *__hidden this, const unsigned __int16 *, HDRVR *, HACMDRIVERID *, HACMDRIVER *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x1801da12c`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800aca50`
- `0x1800ec0e0`
- `0x18012ae00`
- `0x180137a48`
- `0x18017d0d8`
- `0x18018566c`
- `0x1801e92dc`
- `0x1801e9ed0`
- `0x18025839c`
- `0x1802583a8`
- `0x1802583e8`
- `0x180258480`
- `0x1802592a0`
- `0x180273258`
- `0x18029e10c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801e997a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801e997a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e942e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e942e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9514`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e95f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e96a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9753`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e98e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e99a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9a69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9c18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9d85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9e22`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9394`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9462`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9514`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e95f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e96a5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9753`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9810`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e98e6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e99a2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9a69`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9b27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9c18`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9d85`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801e9e22`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverRemove` at `0x1801e9ce6`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverRemove` at `0x1801e9ce6`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverAddW` at `0x1801e9a40`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverAddW` at `0x1801e9a40`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverOpen` at `0x1801e9afe`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverOpen` at `0x1801e9afe`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverClose` at `0x1801e9cd0`
- `ext-ms-win-mm-msacm-l1-1-0!acmDriverClose` at `0x1801e9cd0`
- `api-ms-win-mm-misc-l1-1-0!GetDriverModuleHandle` at `0x1801e98bb`
- `api-ms-win-mm-misc-l1-1-0!GetDriverModuleHandle` at `0x1801e98bb`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x1801e97e5`
- `api-ms-win-mm-misc-l1-1-0!OpenDriver` at `0x1801e97e5`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x1801e9cff`
- `api-ms-win-mm-misc-l1-1-0!CloseDriver` at `0x1801e9cff`

## pseudocode

```c
__int64 __fastcall CACMCodecLoader::LoadSystemCodec(
        CACMCodecLoader *this,
        const unsigned __int16 *a2,
        HDRVR *a3,
        HACMDRIVERID *a4,
        HACMDRIVER *a5)
{
  HDRVR *v5; // r14
  HACMDRIVERID *v8; // rdi
  unsigned __int16 *v9; // r12
  __int64 v10; // rdx
  int v11; // esi
  __int64 v12; // r8
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  unsigned __int64 v27; // rbx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  HDRVR v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rdx
  HMODULE DriverModuleHandle; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  HINSTANCE v53; // rbx
  __int64 *v54; // rcx
  CallStackTracing *v55; // rax
  struct CallStackContext *v56; // rax
  FARPROC ProcAddress; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 *v60; // rcx
  CallStackTracing *v61; // rax
  struct CallStackContext *v62; // rax
  MMRESULT v63; // eax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 *v66; // rcx
  CallStackTracing *v67; // rax
  struct CallStackContext *v68; // rax
  MMRESULT v69; // eax
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 *v72; // rcx
  CallStackTracing *v73; // rax
  struct CallStackContext *v74; // rax
  void *v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  unsigned __int64 v78; // r14
  HACMDRIVERID v79; // rdi
  HDRVR v80; // rbx
  unsigned int v81; // edx
  __int64 v82; // rdx
  __int64 v83; // r8
  __int64 *v84; // rcx
  CallStackTracing *v85; // rax
  struct CallStackContext *v86; // rax
  __int64 v87; // rdx
  __int64 v89; // rdx
  unsigned int v90; // edx
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 *v93; // rcx
  CallStackTracing *v94; // rax
  struct CallStackContext *v95; // rax
  __int64 *v96; // rcx
  CallStackTracing *v97; // rax
  struct CallStackContext *v98; // rax
  _BYTE v99[8]; // [rsp+30h] [rbp-D0h] BYREF
  HDRVR *v100; // [rsp+38h] [rbp-C8h]
  HACMDRIVERID *v101; // [rsp+40h] [rbp-C0h]
  unsigned __int64 v102; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v103; // [rsp+50h] [rbp-B0h] BYREF
  LPHACMDRIVER phad; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v5 = a3;
  v100 = a3;
  phad = a5;
  v101 = a4;
  v8 = a4;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v99, "CACMCodecLoader::LoadSystemCodec", 242);
  memset_0(Buffer, 0, 0x208u);
  v9 = 0;
  *v5 = 0;
  *v8 = 0;
  *a5 = 0;
  v103 = 0;
  v102 = 0;
  if ( !*((_DWORD *)this + 10) )
  {
    v11 = HRESULTFromMMRESULT(8u);
    if ( v11 < 0 )
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v12);
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
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != v11 )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CACMCodecLoader::LoadSystemCodec", 259, v11);
      }
      if ( !g_wppLevels )
        goto LABEL_140;
      v16 = 19;
      goto LABEL_13;
    }
  }
  GetSystemDirectoryW(Buffer, 0x104u);
  v11 = StringCchLengthW(a2, 0x7FFFFFFFu, &v103);
  if ( v11 < 0 )
  {
    v19 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v18);
      CallStackTracing::s_wpInstance = v20;
      if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
      {
        v19 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v19 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
      if ( *((_DWORD *)v21 + 499) != v11 )
        CallStackContext::TraceFailure(v21, "CACMCodecLoader::LoadSystemCodec", 263, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 20;
    goto LABEL_13;
  }
  v11 = StringCchLengthW(Buffer, 0x104u, &v102);
  if ( v11 < 0 )
  {
    v24 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
      CallStackTracing::s_wpInstance = v25;
      if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v24 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
      if ( *((_DWORD *)v26 + 499) != v11 )
        CallStackContext::TraceFailure(v26, "CACMCodecLoader::LoadSystemCodec", 264, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 21;
    goto LABEL_13;
  }
  v27 = v102 + 2 + v103;
  v9 = (unsigned __int16 *)operator new[](saturated_mul(v27, 2u));
  v11 = StringCchCopyW(v9, v27, Buffer);
  if ( v11 < 0 )
  {
    v30 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
      CallStackTracing::s_wpInstance = v31;
      if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v30 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v30 + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
      if ( *((_DWORD *)v32 + 499) != v11 )
        CallStackContext::TraceFailure(v32, "CACMCodecLoader::LoadSystemCodec", 268, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 22;
    goto LABEL_13;
  }
  v11 = StringCchCatW(v9, v27, L"\\");
  if ( v11 < 0 )
  {
    v35 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v35 + 8) )
    {
      v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
      if ( *((_DWORD *)v37 + 499) != v11 )
        CallStackContext::TraceFailure(v37, "CACMCodecLoader::LoadSystemCodec", 269, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 23;
    goto LABEL_13;
  }
  v11 = StringCchCatW(v9, v27, a2);
  if ( v11 < 0 )
  {
    v40 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
      CallStackTracing::s_wpInstance = v41;
      if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
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
      if ( *((_DWORD *)v42 + 499) != v11 )
        CallStackContext::TraceFailure(v42, "CACMCodecLoader::LoadSystemCodec", 270, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 24;
    goto LABEL_13;
  }
  v43 = OpenDriver(v9, 0, 0);
  *v5 = v43;
  if ( !v43 )
  {
    v46 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -1072861832;
    if ( !CallStackTracing::s_wpInstance )
    {
      v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v44, v45);
      CallStackTracing::s_wpInstance = v47;
      if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
      {
        v46 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v46 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
      if ( *((_DWORD *)v48 + 499) != -1072861832 )
        CallStackContext::TraceFailure(v48, "CACMCodecLoader::LoadSystemCodec", 275, -1072861832);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v49 = 25;
    goto LABEL_80;
  }
  DriverModuleHandle = GetDriverModuleHandle(v43);
  v53 = DriverModuleHandle;
  if ( !DriverModuleHandle )
  {
    v54 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -1072861832;
    if ( !CallStackTracing::s_wpInstance )
    {
      v55 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v51, v52);
      CallStackTracing::s_wpInstance = v55;
      if ( v55 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v55 + 8LL))(v55, 2032) )
      {
        v54 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v54 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v54 + 8) )
    {
      v56 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v54);
      if ( *((_DWORD *)v56 + 499) != -1072861832 )
        CallStackContext::TraceFailure(v56, "CACMCodecLoader::LoadSystemCodec", 281, -1072861832);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v49 = 26;
    goto LABEL_80;
  }
  ProcAddress = GetProcAddress(DriverModuleHandle, "DriverProc");
  if ( !ProcAddress )
  {
    v60 = (__int64 *)CallStackTracing::s_wpInstance;
    v11 = -1072861832;
    if ( !CallStackTracing::s_wpInstance )
    {
      v61 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v58, v59);
      CallStackTracing::s_wpInstance = v61;
      if ( v61 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v61 + 8LL))(v61, 2032) )
      {
        v60 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v60 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v60 + 8) )
    {
      v62 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v60);
      if ( *((_DWORD *)v62 + 499) != -1072861832 )
        CallStackContext::TraceFailure(v62, "CACMCodecLoader::LoadSystemCodec", 287, -1072861832);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v49 = 27;
LABEL_80:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v49,
      &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
      this,
      -1072861832);
    goto LABEL_140;
  }
  v63 = acmDriverAddW(v8, v53, (LPARAM)ProcAddress, 0, 3u);
  v11 = HRESULTFromMMRESULT(v63);
  if ( v11 < 0 )
  {
    v66 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v67 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v64, v65);
      CallStackTracing::s_wpInstance = v67;
      if ( v67 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
      {
        v66 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v66 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v66 + 8) )
    {
      v68 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v66);
      if ( *((_DWORD *)v68 + 499) != v11 )
        CallStackContext::TraceFailure(v68, "CACMCodecLoader::LoadSystemCodec", 290, v11);
    }
    if ( !g_wppLevels )
      goto LABEL_140;
    v16 = 28;
    goto LABEL_13;
  }
  v69 = acmDriverOpen(phad, *v8, 0);
  v11 = HRESULTFromMMRESULT(v69);
  if ( v11 >= 0 )
  {
    v75 = operator new(0x30u);
    v78 = (unsigned __int64)v75;
    if ( !v75 )
    {
      v96 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v97 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v76, v77);
        CallStackTracing::s_wpInstance = v97;
        if ( v97 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v97 + 8LL))(v97, 2032) )
        {
          v96 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v96 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v96 + 8) )
      {
        v98 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v96);
        if ( *((_DWORD *)v98 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v98, "CACMCodecLoader::LoadSystemCodec", 295, -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
          this,
          -2147024882);
      goto LABEL_139;
    }
    v79 = *v8;
    v80 = *v100;
    CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v75, a2);
    *(_QWORD *)(v78 + 24) = v80;
    *(_QWORD *)(v78 + 32) = v79;
    *(_DWORD *)(v78 + 40) = 1;
    if ( (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty(v78) )
    {
      CACMCodecLoader::ACM_CODEC_ENTRY::`scalar deleting destructor'((CACMCodecLoader::ACM_CODEC_ENTRY *)v78, v81);
      v84 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v85 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v82, v83);
        CallStackTracing::s_wpInstance = v85;
        if ( v85 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v85 + 8LL))(v85, 2032) )
        {
          v84 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v84 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v84 + 8) )
      {
        v86 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v84);
        if ( *((_DWORD *)v86 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v86, "CACMCodecLoader::LoadSystemCodec", 300, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_138;
      v87 = 31;
    }
    else
    {
      v89 = *((unsigned int *)this + 62);
      v102 = v78;
      if ( (int)CTSparseBlock<unsigned long,CMFNamedPropertyStore::PROP_REC *,20,1>::SetValue(
                  (char *)this + 48,
                  v89,
                  &v102) >= 0 )
      {
        ++*((_DWORD *)this + 62);
        goto LABEL_146;
      }
      CACMCodecLoader::ACM_CODEC_ENTRY::`scalar deleting destructor'((CACMCodecLoader::ACM_CODEC_ENTRY *)v78, v90);
      v93 = (__int64 *)CallStackTracing::s_wpInstance;
      v11 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v94 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v91, v92);
        CallStackTracing::s_wpInstance = v94;
        if ( v94 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v94 + 8LL))(v94, 2032) )
        {
          v93 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v93 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v93 + 8) )
      {
        v95 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v93);
        if ( *((_DWORD *)v95 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v95, "CACMCodecLoader::LoadSystemCodec", 306, -2147024882);
      }
      if ( !g_wppLevels )
        goto LABEL_138;
      v87 = 32;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v87,
      &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids,
      this,
      -2147024882);
LABEL_138:
    v8 = v101;
LABEL_139:
    v5 = v100;
    goto LABEL_140;
  }
  v72 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v73 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v70, v71);
    CallStackTracing::s_wpInstance = v73;
    if ( v73 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v73 + 8LL))(v73, 2032) )
    {
      v72 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v72 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v72 + 8) )
  {
    v74 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v72);
    if ( *((_DWORD *)v74 + 499) != v11 )
      CallStackContext::TraceFailure(v74, "CACMCodecLoader::LoadSystemCodec", 291, v11);
  }
  if ( !g_wppLevels )
    goto LABEL_140;
  v16 = 29;
LABEL_13:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_a3216b5dee8234e6df5ca2fe73b99a91_Traceguids, this, v11);
LABEL_140:
  if ( *phad )
    acmDriverClose(*phad, 0);
  if ( *v8 )
    acmDriverRemove(*v8, 0);
  if ( *v5 )
    CloseDriver(*v5, 0, 0);
LABEL_146:
  operator delete(v9);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v99);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801e92dc  push    rbp
0x1801e92de  push    rbx
0x1801e92df  push    rsi
0x1801e92e0  push    rdi
0x1801e92e1  push    r12
0x1801e92e3  push    r13
0x1801e92e5  push    r14
0x1801e92e7  push    r15
0x1801e92e9  lea     rbp, [rsp-188h]
0x1801e92f1  sub     rsp, 288h
0x1801e92f8  mov     rax, cs:__security_cookie
0x1801e92ff  xor     rax, rsp
0x1801e9302  mov     [rbp+1C0h+var_50], rax
0x1801e9309  mov     rsi, [rbp+1C0h+arg_20]
0x1801e9310  mov     r14, r8
0x1801e9313  mov     [rsp+2C0h+var_288], r8
0x1801e9318  mov     r15, rdx
0x1801e931b  mov     r13, rcx
0x1801e931e  mov     [rsp+2C0h+phad], rsi
0x1801e9323  mov     r8d, 0F2h; int
0x1801e9329  mov     [rsp+2C0h+var_280], r9
0x1801e932e  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e9335  mov     rdi, r9
0x1801e9338  lea     rcx, [rsp+2C0h+var_290]; this
0x1801e933d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801e9342  xor     edx, edx; Val
0x1801e9344  lea     rcx, [rsp+2C0h+Buffer]; void *
0x1801e9349  mov     r8d, 208h; Size
0x1801e934f  call    memset_0
0x1801e9354  xor     r12d, r12d
0x1801e9357  mov     [r14], r12
0x1801e935a  mov     [rdi], r12
0x1801e935d  mov     [rsi], r12
0x1801e9360  mov     [rsp+2C0h+var_270], r12
0x1801e9365  mov     [rsp+2C0h+var_278], r12
0x1801e936a  cmp     [r13+28h], r12d
0x1801e936e  jnz     loc_1801E9422
0x1801e9374  lea     ecx, [r12+8]; unsigned int
0x1801e9379  call    ?HRESULTFromMMRESULT@@YAJI@Z; HRESULTFromMMRESULT(uint)
0x1801e937e  mov     esi, eax
0x1801e9380  test    eax, eax
0x1801e9382  jns     loc_1801E9422
0x1801e9388  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e938f  test    rcx, rcx
0x1801e9392  jnz     short loc_1801E93DC
0x1801e9394  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e939b  nop     dword ptr [rax+rax+00h]
0x1801e93a0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e93a7  mov     rcx, rax
0x1801e93aa  test    rax, rax
0x1801e93ad  jz      short loc_1801E93CE
0x1801e93af  mov     rax, [rax]
0x1801e93b2  mov     edx, 7F0h
0x1801e93b7  mov     rax, [rax+8]
0x1801e93bb  call    cs:__guard_dispatch_icall_fptr
0x1801e93c1  test    eax, eax
0x1801e93c3  jz      short loc_1801E93CE
0x1801e93c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e93cc  jmp     short loc_1801E93DC
0x1801e93ce  lea     rcx, qword_1803CE250; this
0x1801e93d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e93dc  cmp     [rcx+8], r12b
0x1801e93e0  jz      short loc_1801E9407
0x1801e93e2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e93e7  cmp     [rax+7CCh], esi
0x1801e93ed  jz      short loc_1801E9407
0x1801e93ef  mov     r9d, esi; int
0x1801e93f2  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e93f9  mov     r8d, 103h; int
0x1801e93ff  mov     rcx, rax; this
0x1801e9402  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e9407  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e940e  jb      loc_1801E9CC1
0x1801e9414  mov     edx, 13h
0x1801e9419  mov     [rsp+2C0h+fdwAdd], esi
0x1801e941d  jmp     loc_1801E9899
0x1801e9422  mov     ebx, 104h
0x1801e9427  lea     rcx, [rsp+2C0h+Buffer]; lpBuffer
0x1801e942c  mov     edx, ebx; uSize
0x1801e942e  call    cs:__imp_GetSystemDirectoryW
0x1801e9435  nop     dword ptr [rax+rax+00h]
0x1801e943a  lea     r8, [rsp+2C0h+var_270]; unsigned __int64 *
0x1801e943f  mov     edx, 7FFFFFFFh; unsigned __int64
0x1801e9444  mov     rcx, r15; unsigned __int16 *
0x1801e9447  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801e944c  mov     esi, eax
0x1801e944e  test    eax, eax
0x1801e9450  jns     loc_1801E94EC
0x1801e9456  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e945d  test    rcx, rcx
0x1801e9460  jnz     short loc_1801E94AA
0x1801e9462  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e9469  nop     dword ptr [rax+rax+00h]
0x1801e946e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e9475  mov     rcx, rax
0x1801e9478  test    rax, rax
0x1801e947b  jz      short loc_1801E949C
0x1801e947d  mov     rax, [rax]
0x1801e9480  mov     edx, 7F0h
0x1801e9485  mov     rax, [rax+8]
0x1801e9489  call    cs:__guard_dispatch_icall_fptr
0x1801e948f  test    eax, eax
0x1801e9491  jz      short loc_1801E949C
0x1801e9493  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e949a  jmp     short loc_1801E94AA
0x1801e949c  lea     rcx, qword_1803CE250; this
0x1801e94a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e94aa  cmp     [rcx+8], r12b
0x1801e94ae  jz      short loc_1801E94D5
0x1801e94b0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e94b5  cmp     [rax+7CCh], esi
0x1801e94bb  jz      short loc_1801E94D5
0x1801e94bd  mov     r9d, esi; int
0x1801e94c0  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e94c7  mov     r8d, 107h; int
0x1801e94cd  mov     rcx, rax; this
0x1801e94d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e94d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e94dc  jb      loc_1801E9CC1
0x1801e94e2  mov     edx, 14h
0x1801e94e7  jmp     loc_1801E9419
0x1801e94ec  lea     r8, [rsp+2C0h+var_278]; unsigned __int64 *
0x1801e94f1  mov     rdx, rbx; unsigned __int64
0x1801e94f4  lea     rcx, [rsp+2C0h+Buffer]; unsigned __int16 *
0x1801e94f9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1801e94fe  mov     esi, eax
0x1801e9500  test    eax, eax
0x1801e9502  jns     loc_1801E959E
0x1801e9508  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e950f  test    rcx, rcx
0x1801e9512  jnz     short loc_1801E955C
0x1801e9514  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e951b  nop     dword ptr [rax+rax+00h]
0x1801e9520  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e9527  mov     rcx, rax
0x1801e952a  test    rax, rax
0x1801e952d  jz      short loc_1801E954E
0x1801e952f  mov     rax, [rax]
0x1801e9532  mov     edx, 7F0h
0x1801e9537  mov     rax, [rax+8]
0x1801e953b  call    cs:__guard_dispatch_icall_fptr
0x1801e9541  test    eax, eax
0x1801e9543  jz      short loc_1801E954E
0x1801e9545  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e954c  jmp     short loc_1801E955C
0x1801e954e  lea     rcx, qword_1803CE250; this
0x1801e9555  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e955c  cmp     [rcx+8], r12b
0x1801e9560  jz      short loc_1801E9587
0x1801e9562  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e9567  cmp     [rax+7CCh], esi
0x1801e956d  jz      short loc_1801E9587
0x1801e956f  mov     r9d, esi; int
0x1801e9572  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e9579  mov     r8d, 108h; int
0x1801e957f  mov     rcx, rax; this
0x1801e9582  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e9587  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e958e  jb      loc_1801E9CC1
0x1801e9594  mov     edx, 15h
0x1801e9599  jmp     loc_1801E9419
0x1801e959e  mov     rax, [rsp+2C0h+var_278]
0x1801e95a3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801e95aa  mov     rbx, [rsp+2C0h+var_270]
0x1801e95af  add     rax, 2
0x1801e95b3  add     rbx, rax
0x1801e95b6  mov     eax, 2
0x1801e95bb  mul     rbx
0x1801e95be  cmovb   rax, rcx
0x1801e95c2  mov     rcx, rax; unsigned __int64
0x1801e95c5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801e95ca  lea     r8, [rsp+2C0h+Buffer]; unsigned __int16 *
0x1801e95cf  mov     rdx, rbx; unsigned __int64
0x1801e95d2  mov     rcx, rax; unsigned __int16 *
0x1801e95d5  mov     r12, rax
0x1801e95d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801e95dd  mov     esi, eax
0x1801e95df  test    eax, eax
0x1801e95e1  jns     loc_1801E967D
0x1801e95e7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e95ee  test    rcx, rcx
0x1801e95f1  jnz     short loc_1801E963B
0x1801e95f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e95fa  nop     dword ptr [rax+rax+00h]
0x1801e95ff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e9606  mov     rcx, rax
0x1801e9609  test    rax, rax
0x1801e960c  jz      short loc_1801E962D
0x1801e960e  mov     rax, [rax]
0x1801e9611  mov     edx, 7F0h
0x1801e9616  mov     rax, [rax+8]
0x1801e961a  call    cs:__guard_dispatch_icall_fptr
0x1801e9620  test    eax, eax
0x1801e9622  jz      short loc_1801E962D
0x1801e9624  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e962b  jmp     short loc_1801E963B
0x1801e962d  lea     rcx, qword_1803CE250; this
0x1801e9634  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e963b  cmp     byte ptr [rcx+8], 0
0x1801e963f  jz      short loc_1801E9666
0x1801e9641  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e9646  cmp     [rax+7CCh], esi
0x1801e964c  jz      short loc_1801E9666
0x1801e964e  mov     r9d, esi; int
0x1801e9651  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e9658  mov     r8d, 10Ch; int
0x1801e965e  mov     rcx, rax; this
0x1801e9661  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e9666  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e966d  jb      loc_1801E9CC1
0x1801e9673  mov     edx, 16h
0x1801e9678  jmp     loc_1801E9419
0x1801e967d  lea     r8, asc_18037A36C; "\\"
0x1801e9684  mov     rdx, rbx; unsigned __int64
0x1801e9687  mov     rcx, r12; unsigned __int16 *
0x1801e968a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801e968f  mov     esi, eax
0x1801e9691  test    eax, eax
0x1801e9693  jns     loc_1801E972F
0x1801e9699  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e96a0  test    rcx, rcx
0x1801e96a3  jnz     short loc_1801E96ED
0x1801e96a5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e96ac  nop     dword ptr [rax+rax+00h]
0x1801e96b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e96b8  mov     rcx, rax
0x1801e96bb  test    rax, rax
0x1801e96be  jz      short loc_1801E96DF
0x1801e96c0  mov     rax, [rax]
0x1801e96c3  mov     edx, 7F0h
0x1801e96c8  mov     rax, [rax+8]
0x1801e96cc  call    cs:__guard_dispatch_icall_fptr
0x1801e96d2  test    eax, eax
0x1801e96d4  jz      short loc_1801E96DF
0x1801e96d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e96dd  jmp     short loc_1801E96ED
0x1801e96df  lea     rcx, qword_1803CE250; this
0x1801e96e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e96ed  cmp     byte ptr [rcx+8], 0
0x1801e96f1  jz      short loc_1801E9718
0x1801e96f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e96f8  cmp     [rax+7CCh], esi
0x1801e96fe  jz      short loc_1801E9718
0x1801e9700  mov     r9d, esi; int
0x1801e9703  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e970a  mov     r8d, 10Dh; int
0x1801e9710  mov     rcx, rax; this
0x1801e9713  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e9718  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e971f  jb      loc_1801E9CC1
0x1801e9725  mov     edx, 17h
0x1801e972a  jmp     loc_1801E9419
0x1801e972f  mov     r8, r15; unsigned __int16 *
0x1801e9732  mov     rdx, rbx; unsigned __int64
0x1801e9735  mov     rcx, r12; unsigned __int16 *
0x1801e9738  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801e973d  mov     esi, eax
0x1801e973f  test    eax, eax
0x1801e9741  jns     loc_1801E97DD
0x1801e9747  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e974e  test    rcx, rcx
0x1801e9751  jnz     short loc_1801E979B
0x1801e9753  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801e975a  nop     dword ptr [rax+rax+00h]
0x1801e975f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e9766  mov     rcx, rax
0x1801e9769  test    rax, rax
0x1801e976c  jz      short loc_1801E978D
0x1801e976e  mov     rax, [rax]
0x1801e9771  mov     edx, 7F0h
0x1801e9776  mov     rax, [rax+8]
0x1801e977a  call    cs:__guard_dispatch_icall_fptr
0x1801e9780  test    eax, eax
0x1801e9782  jz      short loc_1801E978D
0x1801e9784  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e978b  jmp     short loc_1801E979B
0x1801e978d  lea     rcx, qword_1803CE250; this
0x1801e9794  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801e979b  cmp     byte ptr [rcx+8], 0
0x1801e979f  jz      short loc_1801E97C6
0x1801e97a1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801e97a6  cmp     [rax+7CCh], esi
0x1801e97ac  jz      short loc_1801E97C6
0x1801e97ae  mov     r9d, esi; int
0x1801e97b1  lea     rdx, aCacmcodecloade; "CACMCodecLoader::LoadSystemCodec"
0x1801e97b8  mov     r8d, 10Eh; int
0x1801e97be  mov     rcx, rax; this
0x1801e97c1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801e97c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801e97cd  jb      loc_1801E9CC1
0x1801e97d3  mov     edx, 18h
0x1801e97d8  jmp     loc_1801E9419
0x1801e97dd  xor     r8d, r8d; lParam2
0x1801e97e0  xor     edx, edx; szSectionName
0x1801e97e2  mov     rcx, r12; szDriverName
0x1801e97e5  call    cs:__imp_OpenDriver
0x1801e97ec  nop     dword ptr [rax+rax+00h]
0x1801e97f1  mov     [r14], rax
0x1801e97f4  test    rax, rax
0x1801e97f7  jnz     loc_1801E98B8
  ... truncated ...
```
