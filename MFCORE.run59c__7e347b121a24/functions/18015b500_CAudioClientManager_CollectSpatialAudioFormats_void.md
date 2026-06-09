# CAudioClientManager::CollectSpatialAudioFormats(void)

- ea: `0x18015b500`
- end: `0x18015bba5`
- name: `?CollectSpatialAudioFormats@CAudioClientManager@@QEAAJXZ`
- size: `1701`
- prototype: `__int64 __fastcall(CAudioClientManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801ad254`

## callees

- `0x18002fee0`
- `0x180035170`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18015b500`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015bb50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015bb50`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18015b72f`
- `MFPlat!MFInitMediaTypeFromWaveFormatEx` at `0x18015b72f`
- `MFPlat!MFCreateMediaType` at `0x18015b708`
- `MFPlat!MFCreateMediaType` at `0x18015b708`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b581`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b64d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b869`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b98d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015ba1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015bab1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b581`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b64d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b7d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b869`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b8fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015b98d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015ba1f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18015bab1`

## pseudocode

```c
__int64 __fastcall CAudioClientManager::CollectSpatialAudioFormats(CAudioClientManager *this)
{
  __int64 v2; // rcx
  HRESULT v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  unsigned int i; // esi
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 *v41; // rcx
  CallStackTracing *v42; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 *v44; // rcx
  CallStackTracing *v45; // rax
  struct CallStackContext *v46; // rax
  _QWORD v48[3]; // [rsp+30h] [rbp-18h] BYREF
  char v49; // [rsp+80h] [rbp+38h] BYREF
  unsigned int v50; // [rsp+88h] [rbp+40h] BYREF
  WAVEFORMATEX *pWaveFormat; // [rsp+90h] [rbp+48h] BYREF
  IMFMediaType *ppMFType; // [rsp+98h] [rbp+50h] BYREF

  v2 = *((_QWORD *)this + 10);
  v3 = 0;
  v48[0] = 0;
  ppMFType = 0;
  v50 = 0;
  if ( !v2 || !*((_DWORD *)this + 256) )
    return (unsigned int)v3;
  v3 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v2 + 48LL))(v2, v48);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v49,
    "CAudioClientManager::CollectSpatialAudioFormats",
    379);
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v48[0] + 24LL))(v48[0], &v50);
    if ( v3 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v50 )
          goto LABEL_97;
        pWaveFormat = 0;
        v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, WAVEFORMATEX **))(*(_QWORD *)v48[0] + 32LL))(
               v48[0],
               i,
               &pWaveFormat);
        if ( v3 < 0 )
          break;
        v3 = MFCreateMediaType(&ppMFType);
        if ( v3 < 0 )
        {
          v41 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v42 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
            CallStackTracing::s_wpInstance = v42;
            if ( v42 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
            {
              v41 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v41 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v41 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v41);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CAudioClientManager::CollectSpatialAudioFormats",
                393,
                v3);
          }
          if ( !g_wppLevels )
            goto LABEL_96;
          v31 = 47;
          goto LABEL_95;
        }
        v3 = MFInitMediaTypeFromWaveFormatEx(ppMFType, pWaveFormat, pWaveFormat->cbSize + 18);
        if ( v3 < 0 )
        {
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)v40 + 499) != v3 )
              CallStackContext::TraceFailure(v40, "CAudioClientManager::CollectSpatialAudioFormats", 397, v3);
          }
          if ( !g_wppLevels )
            goto LABEL_96;
          v31 = 48;
          goto LABEL_95;
        }
        v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64 *))ppMFType->lpVtbl->SetGUID)(
               ppMFType,
               &MF_MT_SUBTYPE,
               &MFAudioFormat_Float_SpatialObjects);
        if ( v3 < 0 )
        {
          v35 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23);
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
            if ( *((_DWORD *)v37 + 499) != v3 )
              CallStackContext::TraceFailure(v37, "CAudioClientManager::CollectSpatialAudioFormats", 401, v3);
          }
          if ( !g_wppLevels )
            goto LABEL_96;
          v31 = 49;
          goto LABEL_95;
        }
        v3 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, _QWORD))ppMFType->lpVtbl->SetUINT32)(
               ppMFType,
               &MF_MT_ALL_SAMPLES_INDEPENDENT,
               0);
        if ( v3 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v3 )
              CallStackContext::TraceFailure(v34, "CAudioClientManager::CollectSpatialAudioFormats", 406, v3);
          }
          if ( !g_wppLevels )
            goto LABEL_96;
          v31 = 50;
          goto LABEL_95;
        }
        if ( !CVPtrList::AddTail((CAudioClientManager *)((char *)this + 112), ppMFType) )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          v3 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v28 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v30, "CAudioClientManager::CollectSpatialAudioFormats", 410, -2147024882);
          }
          if ( g_wppLevels )
          {
            v31 = 51;
            goto LABEL_95;
          }
LABEL_96:
          CoTaskMemFree(pWaveFormat);
          pWaveFormat = 0;
          goto LABEL_97;
        }
        ppMFType = 0;
        CoTaskMemFree(pWaveFormat);
      }
      v44 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v45 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
        CallStackTracing::s_wpInstance = v45;
        if ( v45 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v45 + 8LL))(v45, 2032) )
        {
          v44 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v44);
        if ( *((_DWORD *)v46 + 499) != v3 )
          CallStackContext::TraceFailure(v46, "CAudioClientManager::CollectSpatialAudioFormats", 389, v3);
      }
      if ( !g_wppLevels )
        goto LABEL_96;
      v31 = 46;
LABEL_95:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_11cd199e38df33cabe00a5a44f2afe60_Traceguids, this, v3);
      goto LABEL_96;
    }
    v12 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11);
      CallStackTracing::s_wpInstance = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
      if ( *((_DWORD *)v14 + 499) != v3 )
        CallStackContext::TraceFailure(v14, "CAudioClientManager::CollectSpatialAudioFormats", 382, v3);
    }
    if ( !g_wppLevels )
      goto LABEL_97;
    v9 = 45;
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v8 + 499) != v3 )
        CallStackContext::TraceFailure(v8, "CAudioClientManager::CollectSpatialAudioFormats", 379, v3);
    }
    if ( !g_wppLevels )
      goto LABEL_97;
    v9 = 44;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_11cd199e38df33cabe00a5a44f2afe60_Traceguids, this, v3);
LABEL_97:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  if ( v48[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v48[0] + 16LL))(v48[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18015b500  push    rbp
0x18015b502  push    rbx
0x18015b503  push    rsi
0x18015b504  push    rdi
0x18015b505  push    r14
0x18015b507  push    r15
0x18015b509  mov     rbp, rsp
0x18015b50c  sub     rsp, 48h
0x18015b510  xor     r14d, r14d
0x18015b513  mov     rdi, rcx
0x18015b516  mov     rcx, [rcx+50h]
0x18015b51a  mov     ebx, r14d
0x18015b51d  mov     [rbp+var_18], r14
0x18015b521  mov     [rbp+ppMFType], r14
0x18015b525  mov     [rbp+arg_8], r14d
0x18015b529  test    rcx, rcx
0x18015b52c  jz      loc_18015BB95
0x18015b532  cmp     [rdi+400h], r14d
0x18015b539  jz      loc_18015BB95
0x18015b53f  mov     rax, [rcx]
0x18015b542  lea     rdx, [rbp+var_18]
0x18015b546  mov     rax, [rax+30h]
0x18015b54a  call    cs:__guard_dispatch_icall_fptr
0x18015b550  mov     esi, 17Bh
0x18015b555  lea     r15, aCaudioclientma_16; "CAudioClientManager::CollectSpatialAudi"...
0x18015b55c  mov     r8d, esi; int
0x18015b55f  lea     rcx, [rbp+arg_0]; this
0x18015b563  mov     rdx, r15; char *
0x18015b566  mov     ebx, eax
0x18015b568  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18015b56d  test    ebx, ebx
0x18015b56f  jns     loc_18015B622
0x18015b575  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b57c  test    rcx, rcx
0x18015b57f  jnz     short loc_18015B5C9
0x18015b581  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b588  nop     dword ptr [rax+rax+00h]
0x18015b58d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b594  mov     rcx, rax
0x18015b597  test    rax, rax
0x18015b59a  jz      short loc_18015B5BB
0x18015b59c  mov     rax, [rax]
0x18015b59f  mov     edx, 7F0h
0x18015b5a4  mov     rax, [rax+8]
0x18015b5a8  call    cs:__guard_dispatch_icall_fptr
0x18015b5ae  test    eax, eax
0x18015b5b0  jz      short loc_18015B5BB
0x18015b5b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b5b9  jmp     short loc_18015B5C9
0x18015b5bb  lea     rcx, qword_1803CE250; this
0x18015b5c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b5c9  cmp     [rcx+8], r14b
0x18015b5cd  jz      short loc_18015B5ED
0x18015b5cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b5d4  cmp     [rax+7CCh], ebx
0x18015b5da  jz      short loc_18015B5ED
0x18015b5dc  mov     r9d, ebx; int
0x18015b5df  mov     r8d, esi; int
0x18015b5e2  mov     rdx, r15; char *
0x18015b5e5  mov     rcx, rax; this
0x18015b5e8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b5ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015b5f4  jb      loc_18015BB60
0x18015b5fa  mov     edx, 2Ch ; ','
0x18015b5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18015b606  lea     r8, WPP_11cd199e38df33cabe00a5a44f2afe60_Traceguids
0x18015b60d  mov     r9, rdi
0x18015b610  mov     [rsp+48h+var_28], ebx
0x18015b614  mov     rcx, [rcx+10h]
0x18015b618  call    WPP_SF_qD
0x18015b61d  jmp     loc_18015BB60
0x18015b622  mov     rcx, [rbp+var_18]
0x18015b626  lea     rdx, [rbp+arg_8]
0x18015b62a  mov     rax, [rcx]
0x18015b62d  mov     rax, [rax+18h]
0x18015b631  call    cs:__guard_dispatch_icall_fptr
0x18015b637  mov     ebx, eax
0x18015b639  test    eax, eax
0x18015b63b  jns     loc_18015B6D3
0x18015b641  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b648  test    rcx, rcx
0x18015b64b  jnz     short loc_18015B695
0x18015b64d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b654  nop     dword ptr [rax+rax+00h]
0x18015b659  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b660  mov     rcx, rax
0x18015b663  test    rax, rax
0x18015b666  jz      short loc_18015B687
0x18015b668  mov     rax, [rax]
0x18015b66b  mov     edx, 7F0h
0x18015b670  mov     rax, [rax+8]
0x18015b674  call    cs:__guard_dispatch_icall_fptr
0x18015b67a  test    eax, eax
0x18015b67c  jz      short loc_18015B687
0x18015b67e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b685  jmp     short loc_18015B695
0x18015b687  lea     rcx, qword_1803CE250; this
0x18015b68e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b695  cmp     [rcx+8], r14b
0x18015b699  jz      short loc_18015B6BC
0x18015b69b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b6a0  cmp     [rax+7CCh], ebx
0x18015b6a6  jz      short loc_18015B6BC
0x18015b6a8  mov     r9d, ebx; int
0x18015b6ab  mov     r8d, 17Eh; int
0x18015b6b1  mov     rdx, r15; char *
0x18015b6b4  mov     rcx, rax; this
0x18015b6b7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b6bc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015b6c3  jb      loc_18015BB60
0x18015b6c9  mov     edx, 2Dh ; '-'
0x18015b6ce  jmp     loc_18015B5FF
0x18015b6d3  mov     esi, r14d
0x18015b6d6  cmp     esi, [rbp+arg_8]
0x18015b6d9  jnb     loc_18015BB60
0x18015b6df  mov     rcx, [rbp+var_18]
0x18015b6e3  lea     r8, [rbp+pWaveFormat]
0x18015b6e7  mov     [rbp+pWaveFormat], r14
0x18015b6eb  mov     edx, esi
0x18015b6ed  mov     rax, [rcx]
0x18015b6f0  mov     rax, [rax+20h]
0x18015b6f4  call    cs:__guard_dispatch_icall_fptr
0x18015b6fa  mov     ebx, eax
0x18015b6fc  test    eax, eax
0x18015b6fe  js      loc_18015BAA5
0x18015b704  lea     rcx, [rbp+ppMFType]; ppMFType
0x18015b708  call    cs:__imp_MFCreateMediaType
0x18015b70f  nop     dword ptr [rax+rax+00h]
0x18015b714  mov     ebx, eax
0x18015b716  test    eax, eax
0x18015b718  js      loc_18015BA13
0x18015b71e  mov     rdx, [rbp+pWaveFormat]; pWaveFormat
0x18015b722  mov     rcx, [rbp+ppMFType]; pMFType
0x18015b726  movzx   r8d, word ptr [rdx+10h]
0x18015b72b  add     r8d, 12h; cbBufSize
0x18015b72f  call    cs:__imp_MFInitMediaTypeFromWaveFormatEx
0x18015b736  nop     dword ptr [rax+rax+00h]
0x18015b73b  mov     ebx, eax
0x18015b73d  test    eax, eax
0x18015b73f  js      loc_18015B981
0x18015b745  mov     rcx, [rbp+ppMFType]
0x18015b749  lea     r8, MFAudioFormat_Float_SpatialObjects
0x18015b750  lea     rdx, MF_MT_SUBTYPE
0x18015b757  mov     rax, [rcx]
0x18015b75a  mov     rax, [rax+0C0h]
0x18015b761  call    cs:__guard_dispatch_icall_fptr
0x18015b767  mov     ebx, eax
0x18015b769  test    eax, eax
0x18015b76b  js      loc_18015B8EF
0x18015b771  mov     rcx, [rbp+ppMFType]
0x18015b775  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x18015b77c  xor     r8d, r8d
0x18015b77f  mov     rax, [rcx]
0x18015b782  mov     rax, [rax+0A8h]
0x18015b789  call    cs:__guard_dispatch_icall_fptr
0x18015b78f  mov     ebx, eax
0x18015b791  test    eax, eax
0x18015b793  js      loc_18015B85D
0x18015b799  mov     rdx, [rbp+ppMFType]; void *
0x18015b79d  lea     rcx, [rdi+70h]; this
0x18015b7a1  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x18015b7a6  test    rax, rax
0x18015b7a9  jz      short loc_18015B7C6
0x18015b7ab  mov     rcx, [rbp+pWaveFormat]; pv
0x18015b7af  mov     [rbp+ppMFType], r14
0x18015b7b3  call    cs:__imp_CoTaskMemFree
0x18015b7ba  nop     dword ptr [rax+rax+00h]
0x18015b7bf  inc     esi
0x18015b7c1  jmp     loc_18015B6D6
0x18015b7c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b7cd  mov     ebx, 8007000Eh
0x18015b7d2  test    rcx, rcx
0x18015b7d5  jnz     short loc_18015B81F
0x18015b7d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b7de  nop     dword ptr [rax+rax+00h]
0x18015b7e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b7ea  mov     rcx, rax
0x18015b7ed  test    rax, rax
0x18015b7f0  jz      short loc_18015B811
0x18015b7f2  mov     rax, [rax]
0x18015b7f5  mov     edx, 7F0h
0x18015b7fa  mov     rax, [rax+8]
0x18015b7fe  call    cs:__guard_dispatch_icall_fptr
0x18015b804  test    eax, eax
0x18015b806  jz      short loc_18015B811
0x18015b808  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b80f  jmp     short loc_18015B81F
0x18015b811  lea     rcx, qword_1803CE250; this
0x18015b818  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b81f  cmp     [rcx+8], r14b
0x18015b823  jz      short loc_18015B846
0x18015b825  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b82a  cmp     [rax+7CCh], ebx
0x18015b830  jz      short loc_18015B846
0x18015b832  mov     r9d, ebx; int
0x18015b835  mov     r8d, 19Ah; int
0x18015b83b  mov     rdx, r15; char *
0x18015b83e  mov     rcx, rax; this
0x18015b841  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b846  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015b84d  jb      loc_18015BB4C
0x18015b853  mov     edx, 33h ; '3'
0x18015b858  jmp     loc_18015BB2E
0x18015b85d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b864  test    rcx, rcx
0x18015b867  jnz     short loc_18015B8B1
0x18015b869  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b870  nop     dword ptr [rax+rax+00h]
0x18015b875  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b87c  mov     rcx, rax
0x18015b87f  test    rax, rax
0x18015b882  jz      short loc_18015B8A3
0x18015b884  mov     rax, [rax]
0x18015b887  mov     edx, 7F0h
0x18015b88c  mov     rax, [rax+8]
0x18015b890  call    cs:__guard_dispatch_icall_fptr
0x18015b896  test    eax, eax
0x18015b898  jz      short loc_18015B8A3
0x18015b89a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b8a1  jmp     short loc_18015B8B1
0x18015b8a3  lea     rcx, qword_1803CE250; this
0x18015b8aa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b8b1  cmp     [rcx+8], r14b
0x18015b8b5  jz      short loc_18015B8D8
0x18015b8b7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b8bc  cmp     [rax+7CCh], ebx
0x18015b8c2  jz      short loc_18015B8D8
0x18015b8c4  mov     r9d, ebx; int
0x18015b8c7  mov     r8d, 196h; int
0x18015b8cd  mov     rdx, r15; char *
0x18015b8d0  mov     rcx, rax; this
0x18015b8d3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b8d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015b8df  jb      loc_18015BB4C
0x18015b8e5  mov     edx, 32h ; '2'
0x18015b8ea  jmp     loc_18015BB2E
0x18015b8ef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b8f6  test    rcx, rcx
0x18015b8f9  jnz     short loc_18015B943
0x18015b8fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b902  nop     dword ptr [rax+rax+00h]
0x18015b907  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b90e  mov     rcx, rax
0x18015b911  test    rax, rax
0x18015b914  jz      short loc_18015B935
0x18015b916  mov     rax, [rax]
0x18015b919  mov     edx, 7F0h
0x18015b91e  mov     rax, [rax+8]
0x18015b922  call    cs:__guard_dispatch_icall_fptr
0x18015b928  test    eax, eax
0x18015b92a  jz      short loc_18015B935
0x18015b92c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b933  jmp     short loc_18015B943
0x18015b935  lea     rcx, qword_1803CE250; this
0x18015b93c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b943  cmp     [rcx+8], r14b
0x18015b947  jz      short loc_18015B96A
0x18015b949  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b94e  cmp     [rax+7CCh], ebx
0x18015b954  jz      short loc_18015B96A
0x18015b956  mov     r9d, ebx; int
0x18015b959  mov     r8d, 191h; int
0x18015b95f  mov     rdx, r15; char *
0x18015b962  mov     rcx, rax; this
0x18015b965  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b96a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015b971  jb      loc_18015BB4C
0x18015b977  mov     edx, 31h ; '1'
0x18015b97c  jmp     loc_18015BB2E
0x18015b981  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b988  test    rcx, rcx
0x18015b98b  jnz     short loc_18015B9D5
0x18015b98d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18015b994  nop     dword ptr [rax+rax+00h]
0x18015b999  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b9a0  mov     rcx, rax
0x18015b9a3  test    rax, rax
0x18015b9a6  jz      short loc_18015B9C7
0x18015b9a8  mov     rax, [rax]
0x18015b9ab  mov     edx, 7F0h
0x18015b9b0  mov     rax, [rax+8]
0x18015b9b4  call    cs:__guard_dispatch_icall_fptr
0x18015b9ba  test    eax, eax
0x18015b9bc  jz      short loc_18015B9C7
0x18015b9be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b9c5  jmp     short loc_18015B9D5
0x18015b9c7  lea     rcx, qword_1803CE250; this
0x18015b9ce  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18015b9d5  cmp     [rcx+8], r14b
0x18015b9d9  jz      short loc_18015B9FC
0x18015b9db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18015b9e0  cmp     [rax+7CCh], ebx
0x18015b9e6  jz      short loc_18015B9FC
0x18015b9e8  mov     r9d, ebx; int
0x18015b9eb  mov     r8d, 18Dh; int
0x18015b9f1  mov     rdx, r15; char *
0x18015b9f4  mov     rcx, rax; this
0x18015b9f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18015b9fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18015ba03  jb      loc_18015BB4C
  ... truncated ...
```
