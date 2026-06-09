# CAudStreamSink::InitializeAudioClient(_AUDCLNT_SHAREMODE,ulong,__int64 *,__int64,tWAVEFORMATEX const *,_GUID const *,AudioClientProperties,IAudioClient2 * *)

- ea: `0x1801621bc`
- end: `0x180162ae6`
- name: `?InitializeAudioClient@CAudStreamSink@@QEAAJW4_AUDCLNT_SHAREMODE@@KPEA_J_JPEBUtWAVEFORMATEX@@PEBU_GUID@@UAudioClientProperties@@PEAPEAUIAudioClient2@@@Z`
- size: `2346`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, enum _AUDCLNT_SHAREMODE, unsigned int, __int64 *, __int64, const struct tWAVEFORMATEX *, const struct _GUID *, struct AudioClientProperties *, struct IAudioClient2 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800b33a0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x18007b9ec`
- `0x18007d750`
- `0x1800e39a8`
- `0x1800ec0e0`
- `0x1801621bc`
- `0x180173d70`
- `0x180177fd8`
- `0x18017fff8`
- `0x180183314`
- `0x180258480`
- `0x18031acac`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180162803`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180162aad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180162803`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180162aad`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801622d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801623c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162510`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016268f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162774`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162853`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016292d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162a02`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801622d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1801623c6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162510`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016268f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162774`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162853`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18016292d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180162a02`

## string_xrefs

- `0x180162226`: `CAudStreamSink::InitializeAudioClient`
- `0x180162335`: `CAudStreamSink::InitializeAudioClient`
- `0x180162424`: `CAudStreamSink::InitializeAudioClient`
- `0x18016256e`: `CAudStreamSink::InitializeAudioClient`
- `0x1801626ed`: `CAudStreamSink::InitializeAudioClient`
- `0x1801627d2`: `CAudStreamSink::InitializeAudioClient`
- `0x1801628b1`: `CAudStreamSink::InitializeAudioClient`
- `0x18016298b`: `CAudStreamSink::InitializeAudioClient`
- `0x180162a60`: `CAudStreamSink::InitializeAudioClient`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::InitializeAudioClient(
        CAudStreamSink *this,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        const struct tWAVEFORMATEX *a6,
        const struct _GUID *a7,
        struct AudioClientProperties *a8,
        struct IAudioClient2 **a9)
{
  struct AudioClientProperties *v10; // rdi
  CAudioClientManager *v13; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v15; // ebx
  __int128 v16; // xmm0
  __int64 v17; // rdx
  int inited; // ebx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  int v29; // eax
  struct IAudioClient2 *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rcx
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // r15
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  CallStackTracing *v53; // rax
  struct CallStackContext *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 *v57; // rcx
  CallStackTracing *v58; // rax
  struct CallStackContext *v59; // rax
  CAudioClientManager *v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 *v63; // rcx
  CallStackTracing *v64; // rax
  struct CallStackContext *v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 *v68; // rcx
  CallStackTracing *v69; // rax
  struct CallStackContext *v70; // rax
  _BYTE v72[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v73; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v74; // [rsp+48h] [rbp-B8h]
  enum _AUDCLNT_SHAREMODE v75; // [rsp+4Ch] [rbp-B4h]
  __int64 *v76; // [rsp+50h] [rbp-B0h]
  struct AudioClientProperties *v77; // [rsp+58h] [rbp-A8h]
  const struct _GUID *v78; // [rsp+60h] [rbp-A0h]
  struct tagPROPVARIANT pvar; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v80[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v81[16]; // [rsp+100h] [rbp+0h] BYREF

  v10 = a8;
  v78 = a7;
  v74 = a3;
  v75 = a2;
  v76 = a4;
  v77 = a8;
  memset(&pvar, 0, sizeof(pvar));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v72, "CAudStreamSink::InitializeAudioClient", 9485);
  v13 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v16 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**((_QWORD **)this + 825) + 280LL))(
                       *((_QWORD *)this + 825),
                       v81);
    *((_DWORD *)ThreadRelativeContext + 504) = v15;
    *((_OWORD *)ThreadRelativeContext + 125) = v16;
    v10 = v77;
  }
  if ( !*a9 )
  {
    inited = CAudStreamSink::ActivateAudioClientInterface(this);
    if ( inited < 0 )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v17, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
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
        if ( *((_DWORD *)v22 + 499) != inited )
          CallStackContext::TraceFailure(v22, "CAudStreamSink::InitializeAudioClient", 9489, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 587;
      goto LABEL_16;
    }
  }
  if ( (unsigned int)CAudioClientManager::IsSpatialType(v13, a6) )
    CAudioClientManager::GetSpatialAudioClient(*((CAudioClientManager **)this + 842), a9);
  inited = ((__int64 (__fastcall *)(_QWORD, struct AudioClientProperties *))(*a9)->lpVtbl->SetClientProperties)(
             *a9,
             v10);
  if ( inited < 0 )
  {
    v26 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
      CallStackTracing::s_wpInstance = v27;
      if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
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
      if ( *((_DWORD *)v28 + 499) != inited )
        CallStackContext::TraceFailure(v28, "CAudStreamSink::InitializeAudioClient", 9498, inited);
    }
    if ( !g_wppLevels )
      goto LABEL_112;
    v23 = 588;
    goto LABEL_16;
  }
  v29 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))(*a9)->lpVtbl->Initialize)(*a9, a2, a3);
  inited = v29;
  if ( v29 != -2004287463 )
  {
    if ( v29 >= 0 )
      goto LABEL_114;
    goto LABEL_112;
  }
  if ( (a3 & 0x40000) != 0 && (a2 == 1 || v10->bIsOffload) )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        589,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        -2004287463);
    v30 = *a9;
    v73 = 0;
    inited = ((__int64 (__fastcall *)(struct IAudioClient2 *, int *))v30->lpVtbl->GetBufferSize)(v30, &v73);
    if ( inited < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31, v32);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
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
        if ( *((_DWORD *)v35 + 499) != inited )
          CallStackContext::TraceFailure(v35, "CAudStreamSink::InitializeAudioClient", 9518, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 590;
      goto LABEL_16;
    }
    *v76 = (unsigned int)(int)((double)a6->nBlockAlign * (double)v73 * 10000000.0 / (double)(int)a6->nAvgBytesPerSec
                             + 0.5);
    if ( *a9 )
    {
      ((void (__fastcall *)(_QWORD))(*a9)->lpVtbl->Release)(*a9);
      *a9 = 0;
    }
    CAudioClientManager::Reset(*((CAudioClientManager **)this + 842));
    v36 = *((_QWORD *)this + 842);
    v37 = *(_OWORD *)((char *)this + 7224);
    v80[0] = *(_OWORD *)((char *)this + 7208);
    v38 = *(_OWORD *)((char *)this + 7240);
    v80[1] = v37;
    v39 = *(_OWORD *)((char *)this + 7256);
    v80[2] = v38;
    v40 = *(_OWORD *)((char *)this + 7272);
    v80[3] = v39;
    v41 = *(_OWORD *)((char *)this + 7288);
    v80[4] = v40;
    v42 = *(_OWORD *)((char *)this + 7304);
    v80[5] = v41;
    v43 = *(_OWORD *)((char *)this + 7320);
    v80[6] = v42;
    v80[7] = v43;
    inited = CAudioClientManager::InitDevice(v36, (__int64)v80);
    if ( inited < 0 )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
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
        if ( *((_DWORD *)v48 + 499) != inited )
          CallStackContext::TraceFailure(v48, "CAudStreamSink::InitializeAudioClient", 9527, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 591;
      goto LABEL_16;
    }
    v49 = *((_QWORD *)this + 818);
    if ( v49 )
      (*(void (__fastcall **)(_QWORD, struct tagPROPVARIANT *))(*(_QWORD *)v49 + 64LL))(*((_QWORD *)this + 818), &pvar);
    inited = CAudioClientManager::InitNonSpatialClient(
               *((CAudioClientManager **)this + 842),
               (struct IAudStreamSinkCallback *)(((unsigned __int64)this + 656)
                                               & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
               &pvar);
    if ( inited < 0 )
    {
      v52 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v53 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v50, v51);
        CallStackTracing::s_wpInstance = v53;
        if ( v53 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v53 + 8LL))(v53, 2032) )
        {
          v52 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v52 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v52 + 8) )
      {
        v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v52);
        if ( *((_DWORD *)v54 + 499) != inited )
          CallStackContext::TraceFailure(v54, "CAudStreamSink::InitializeAudioClient", 9541, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 592;
      goto LABEL_16;
    }
    PropVariantClear((PROPVARIANT *)&pvar);
    if ( v49 )
      (*(void (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v49 + 72LL))(v49, &pvar);
    inited = CAudioClientManager::InitSpatialClient(
               *((CAudioClientManager **)this + 842),
               (CAudStreamSink *)((char *)this + 656),
               &pvar);
    if ( inited < 0 )
    {
      v57 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v58 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v55, v56);
        CallStackTracing::s_wpInstance = v58;
        if ( v58 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v58 + 8LL))(v58, 2032) )
        {
          v57 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v57 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v57 + 8) )
      {
        v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v57);
        if ( *((_DWORD *)v59 + 499) != inited )
          CallStackContext::TraceFailure(v59, "CAudStreamSink::InitializeAudioClient", 9552, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 593;
      goto LABEL_16;
    }
    if ( (unsigned int)CAudioClientManager::IsSpatialType(*((CAudioClientManager **)this + 842), a6) )
      CAudioClientManager::GetSpatialAudioClient(v60, a9);
    else
      CAudioClientManager::GetAudioClient(v60, a9);
    inited = ((__int64 (__fastcall *)(_QWORD, struct AudioClientProperties *))(*a9)->lpVtbl->SetClientProperties)(
               *a9,
               v77);
    if ( inited < 0 )
    {
      v63 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v64 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v61, v62);
        CallStackTracing::s_wpInstance = v64;
        if ( v64 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
        {
          v63 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v63 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v63 + 8) )
      {
        v65 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v63);
        if ( *((_DWORD *)v65 + 499) != inited )
          CallStackContext::TraceFailure(v65, "CAudStreamSink::InitializeAudioClient", 9569, inited);
      }
      if ( !g_wppLevels )
        goto LABEL_112;
      v23 = 594;
      goto LABEL_16;
    }
    inited = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))(*a9)->lpVtbl->Initialize)(*a9, (unsigned int)v75, v74);
    if ( inited >= 0 )
      goto LABEL_114;
    v68 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v69 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v66, v67);
      CallStackTracing::s_wpInstance = v69;
      if ( v69 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v69 + 8LL))(v69, 2032) )
      {
        v68 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v68 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v68 + 8) )
    {
      v70 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v68);
      if ( *((_DWORD *)v70 + 499) != inited )
        CallStackContext::TraceFailure(v70, "CAudStreamSink::InitializeAudioClient", 9575, inited);
    }
    if ( g_wppLevels )
    {
      v23 = 595;
LABEL_16:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        inited);
    }
  }
LABEL_112:
  if ( *a9 )
  {
    ((void (__fastcall *)(_QWORD))(*a9)->lpVtbl->Release)(*a9);
    *a9 = 0;
  }
LABEL_114:
  PropVariantClear((PROPVARIANT *)&pvar);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v72);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1801621bc  push    rbp
0x1801621be  push    rbx
0x1801621bf  push    rsi
0x1801621c0  push    rdi
0x1801621c1  push    r12
0x1801621c3  push    r13
0x1801621c5  push    r14
0x1801621c7  push    r15
0x1801621c9  lea     rbp, [rsp-28h]
0x1801621ce  sub     rsp, 128h
0x1801621d5  mov     rax, cs:__security_cookie
0x1801621dc  xor     rax, rsp
0x1801621df  mov     [rbp+60h+var_50], rax
0x1801621e3  mov     rax, [rbp+60h+arg_30]
0x1801621ea  mov     r13d, r8d
0x1801621ed  mov     rdi, [rbp+60h+arg_38]
0x1801621f4  mov     r15d, edx
0x1801621f7  mov     r12, [rbp+60h+arg_28]
0x1801621fe  mov     rsi, rcx
0x180162201  mov     r14, [rbp+60h+arg_40]
0x180162208  lea     rcx, [rsp+160h+var_120]; this
0x18016220d  mov     [rsp+160h+var_100], rax
0x180162212  xorps   xmm0, xmm0
0x180162215  xor     eax, eax
0x180162217  mov     [rsp+160h+var_118], r8d
0x18016221c  mov     [rsp+160h+var_114], edx
0x180162220  mov     r8d, 250Dh; int
0x180162226  lea     rdx, aCaudstreamsink_28; "CAudStreamSink::InitializeAudioClient"
0x18016222d  mov     [rsp+160h+var_E8], rax
0x180162232  mov     [rsp+160h+var_110], r9
0x180162237  mov     [rsp+160h+var_108], rdi
0x18016223c  movups  xmmword ptr [rsp+160h+pvar], xmm0
0x180162241  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180162246  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18016224d  cmp     byte ptr [rcx+8], 0
0x180162251  jz      short loc_1801622AF
0x180162253  cmp     qword ptr [rsi+19C8h], 0
0x18016225b  jz      short loc_1801622AF
0x18016225d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180162262  mov     rcx, [rsi+19C8h]
0x180162269  mov     rdi, rax
0x18016226c  mov     rdx, [rcx]
0x18016226f  mov     rax, [rdx+128h]
0x180162276  call    cs:__guard_dispatch_icall_fptr
0x18016227c  mov     rcx, [rsi+19C8h]
0x180162283  mov     ebx, eax
0x180162285  mov     rdx, [rcx]
0x180162288  mov     rax, [rdx+118h]
0x18016228f  lea     rdx, [rbp+60h+var_60]
0x180162293  call    cs:__guard_dispatch_icall_fptr
0x180162299  movups  xmm0, xmmword ptr [rax]
0x18016229c  mov     [rdi+7E0h], ebx
0x1801622a2  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801622aa  mov     rdi, [rsp+160h+var_108]
0x1801622af  cmp     qword ptr [r14], 0
0x1801622b3  jnz     loc_18016237F
0x1801622b9  mov     rcx, rsi; this
0x1801622bc  call    ?ActivateAudioClientInterface@CAudStreamSink@@QEAAJXZ; CAudStreamSink::ActivateAudioClientInterface(void)
0x1801622c1  mov     ebx, eax
0x1801622c3  test    eax, eax
0x1801622c5  jns     loc_18016237F
0x1801622cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801622d2  test    rcx, rcx
0x1801622d5  jnz     short loc_18016231F
0x1801622d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801622de  nop     dword ptr [rax+rax+00h]
0x1801622e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801622ea  mov     rcx, rax
0x1801622ed  test    rax, rax
0x1801622f0  jz      short loc_180162311
0x1801622f2  mov     rax, [rax]
0x1801622f5  mov     edx, 7F0h
0x1801622fa  mov     rax, [rax+8]
0x1801622fe  call    cs:__guard_dispatch_icall_fptr
0x180162304  test    eax, eax
0x180162306  jz      short loc_180162311
0x180162308  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016230f  jmp     short loc_18016231F
0x180162311  lea     rcx, qword_1803CE250; this
0x180162318  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016231f  cmp     byte ptr [rcx+8], 0
0x180162323  jz      short loc_18016234A
0x180162325  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18016232a  cmp     [rax+7CCh], ebx
0x180162330  jz      short loc_18016234A
0x180162332  mov     r9d, ebx; int
0x180162335  lea     rdx, aCaudstreamsink_28; "CAudStreamSink::InitializeAudioClient"
0x18016233c  mov     r8d, 2511h; int
0x180162342  mov     rcx, rax; this
0x180162345  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18016234a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180162351  jb      loc_180162A8C
0x180162357  mov     edx, 24Bh
0x18016235c  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180162363  mov     rcx, cs:WPP_GLOBAL_Control
0x18016236a  mov     r9, rsi
0x18016236d  mov     dword ptr [rsp+160h+var_140], ebx
0x180162371  mov     rcx, [rcx+10h]
0x180162375  call    WPP_SF_qD
0x18016237a  jmp     loc_180162A8C
0x18016237f  mov     rdx, r12; struct tWAVEFORMATEX *
0x180162382  call    ?IsSpatialType@CAudioClientManager@@QEAAHPEBUtWAVEFORMATEX@@@Z; CAudioClientManager::IsSpatialType(tWAVEFORMATEX const *)
0x180162387  test    eax, eax
0x180162389  jz      short loc_18016239A
0x18016238b  mov     rcx, [rsi+1A50h]; this
0x180162392  mov     rdx, r14; struct IAudioClient2 **
0x180162395  call    ?GetSpatialAudioClient@CAudioClientManager@@QEAAJPEAPEAUIAudioClient2@@@Z; CAudioClientManager::GetSpatialAudioClient(IAudioClient2 * *)
0x18016239a  mov     rcx, [r14]
0x18016239d  mov     rdx, rdi
0x1801623a0  mov     rax, [rcx]
0x1801623a3  mov     rax, [rax+80h]
0x1801623aa  call    cs:__guard_dispatch_icall_fptr
0x1801623b0  mov     ebx, eax
0x1801623b2  test    eax, eax
0x1801623b4  jns     loc_180162450
0x1801623ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801623c1  test    rcx, rcx
0x1801623c4  jnz     short loc_18016240E
0x1801623c6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1801623cd  nop     dword ptr [rax+rax+00h]
0x1801623d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801623d9  mov     rcx, rax
0x1801623dc  test    rax, rax
0x1801623df  jz      short loc_180162400
0x1801623e1  mov     rax, [rax]
0x1801623e4  mov     edx, 7F0h
0x1801623e9  mov     rax, [rax+8]
0x1801623ed  call    cs:__guard_dispatch_icall_fptr
0x1801623f3  test    eax, eax
0x1801623f5  jz      short loc_180162400
0x1801623f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801623fe  jmp     short loc_18016240E
0x180162400  lea     rcx, qword_1803CE250; this
0x180162407  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18016240e  cmp     byte ptr [rcx+8], 0
0x180162412  jz      short loc_180162439
0x180162414  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180162419  cmp     [rax+7CCh], ebx
0x18016241f  jz      short loc_180162439
0x180162421  mov     r9d, ebx; int
0x180162424  lea     rdx, aCaudstreamsink_28; "CAudStreamSink::InitializeAudioClient"
0x18016242b  mov     r8d, 251Ah; int
0x180162431  mov     rcx, rax; this
0x180162434  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180162439  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180162440  jb      loc_180162A8C
0x180162446  mov     edx, 24Ch
0x18016244b  jmp     loc_18016235C
0x180162450  mov     rdx, [rsp+160h+var_100]
0x180162455  mov     r8d, r13d
0x180162458  mov     rax, [rsp+160h+var_110]
0x18016245d  mov     rcx, [r14]
0x180162460  mov     [rsp+160h+var_130], rdx
0x180162465  mov     edx, r15d
0x180162468  mov     [rsp+160h+var_138], r12
0x18016246d  mov     r9, [rax]
0x180162470  mov     rax, [rcx]
0x180162473  mov     [rsp+160h+var_140], r9
0x180162478  mov     rax, [rax+18h]
0x18016247c  call    cs:__guard_dispatch_icall_fptr
0x180162482  mov     ebx, eax
0x180162484  cmp     eax, 88890019h
0x180162489  jnz     loc_180162A88
0x18016248f  bt      r13d, 12h
0x180162494  jnb     loc_180162A8C
0x18016249a  cmp     r15d, 1
0x18016249e  jz      short loc_1801624AA
0x1801624a0  cmp     dword ptr [rdi+4], 0
0x1801624a4  jz      loc_180162A8C
0x1801624aa  cmp     cs:byte_1803CECE9, 10h
0x1801624b1  lea     rdi, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1801624b8  jb      short loc_1801624DD
0x1801624ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1801624c1  mov     edx, 24Dh
0x1801624c6  mov     r9, rsi
0x1801624c9  mov     dword ptr [rsp+160h+var_140], 88890019h
0x1801624d1  mov     r8, rdi
0x1801624d4  mov     rcx, [rcx+38h]
0x1801624d8  call    WPP_SF_qD
0x1801624dd  mov     rcx, [r14]
0x1801624e0  lea     rdx, [rsp+160h+var_11C]
0x1801624e5  mov     [rsp+160h+var_11C], 0
0x1801624ed  mov     rax, [rcx]
0x1801624f0  mov     rax, [rax+20h]
0x1801624f4  call    cs:__guard_dispatch_icall_fptr
0x1801624fa  mov     ebx, eax
0x1801624fc  test    eax, eax
0x1801624fe  jns     loc_18016259D
0x180162504  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016250b  test    rcx, rcx
0x18016250e  jnz     short loc_180162558
0x180162510  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180162517  nop     dword ptr [rax+rax+00h]
0x18016251c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180162523  mov     rcx, rax
0x180162526  test    rax, rax
0x180162529  jz      short loc_18016254A
0x18016252b  mov     rax, [rax]
0x18016252e  mov     edx, 7F0h
0x180162533  mov     rax, [rax+8]
0x180162537  call    cs:__guard_dispatch_icall_fptr
0x18016253d  test    eax, eax
0x18016253f  jz      short loc_18016254A
0x180162541  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180162548  jmp     short loc_180162558
0x18016254a  lea     rcx, qword_1803CE250; this
0x180162551  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180162558  cmp     byte ptr [rcx+8], 0
0x18016255c  jz      short loc_180162583
0x18016255e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180162563  cmp     [rax+7CCh], ebx
0x180162569  jz      short loc_180162583
0x18016256b  mov     r9d, ebx; int
0x18016256e  lea     rdx, aCaudstreamsink_28; "CAudStreamSink::InitializeAudioClient"
0x180162575  mov     r8d, 252Eh; int
0x18016257b  mov     rcx, rax; this
0x18016257e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180162583  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18016258a  jb      loc_180162A8C
0x180162590  mov     edx, 24Eh
0x180162595  mov     r8, rdi
0x180162598  jmp     loc_180162363
0x18016259d  movzx   eax, word ptr [r12+0Ch]
0x1801625a3  xorps   xmm0, xmm0
0x1801625a6  mov     rcx, [rsp+160h+var_110]
0x1801625ab  movd    xmm1, eax
0x1801625af  mov     eax, [rsp+160h+var_11C]
0x1801625b3  cvtdq2pd xmm1, xmm1
0x1801625b7  cvtsi2sd xmm0, rax
0x1801625bc  mov     eax, [r12+8]
0x1801625c1  mulsd   xmm1, xmm0
0x1801625c5  xorps   xmm0, xmm0
0x1801625c8  cvtsi2sd xmm0, rax
0x1801625cd  mulsd   xmm1, cs:__real@416312d000000000
0x1801625d5  divsd   xmm1, xmm0
0x1801625d9  addsd   xmm1, cs:__real@3fe0000000000000
0x1801625e1  cvttsd2si rax, xmm1
0x1801625e6  mov     [rcx], rax
0x1801625e9  mov     rcx, [r14]
0x1801625ec  test    rcx, rcx
0x1801625ef  jz      short loc_180162605
0x1801625f1  mov     rax, [rcx]
0x1801625f4  mov     rax, [rax+10h]
0x1801625f8  call    cs:__guard_dispatch_icall_fptr
0x1801625fe  mov     qword ptr [r14], 0
0x180162605  mov     rcx, [rsi+1A50h]; this
0x18016260c  call    ?Reset@CAudioClientManager@@QEAAXXZ; CAudioClientManager::Reset(void)
0x180162611  movups  xmm0, xmmword ptr [rsi+1C28h]
0x180162618  mov     rcx, [rsi+1A50h]
0x18016261f  lea     rdx, [rbp+60h+var_E0]
0x180162623  movups  xmm1, xmmword ptr [rsi+1C38h]
0x18016262a  movaps  [rbp+60h+var_E0], xmm0
0x18016262e  movups  xmm0, xmmword ptr [rsi+1C48h]
0x180162635  movaps  [rbp+60h+var_D0], xmm1
0x180162639  movups  xmm1, xmmword ptr [rsi+1C58h]
0x180162640  movaps  [rbp+60h+var_C0], xmm0
0x180162644  movups  xmm0, xmmword ptr [rsi+1C68h]
0x18016264b  movaps  [rbp+60h+var_B0], xmm1
0x18016264f  movups  xmm1, xmmword ptr [rsi+1C78h]
0x180162656  movaps  [rbp+60h+var_A0], xmm0
0x18016265a  movups  xmm0, xmmword ptr [rsi+1C88h]
0x180162661  movaps  [rbp+60h+var_90], xmm1
0x180162665  movups  xmm1, xmmword ptr [rsi+1C98h]
0x18016266c  movaps  [rbp+60h+var_80], xmm0
0x180162670  movaps  [rbp+60h+var_70], xmm1
0x180162674  call    ?InitDevice@CAudioClientManager@@QEAAJUSARPARAMS@@@Z; CAudioClientManager::InitDevice(SARPARAMS)
0x180162679  mov     ebx, eax
0x18016267b  test    eax, eax
0x18016267d  jns     loc_180162719
0x180162683  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18016268a  test    rcx, rcx
0x18016268d  jnz     short loc_1801626D7
0x18016268f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180162696  nop     dword ptr [rax+rax+00h]
0x18016269b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1801626a2  mov     rcx, rax
0x1801626a5  test    rax, rax
0x1801626a8  jz      short loc_1801626C9
0x1801626aa  mov     rax, [rax]
0x1801626ad  mov     edx, 7F0h
0x1801626b2  mov     rax, [rax+8]
0x1801626b6  call    cs:__guard_dispatch_icall_fptr
0x1801626bc  test    eax, eax
0x1801626be  jz      short loc_1801626C9
0x1801626c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801626c7  jmp     short loc_1801626D7
0x1801626c9  lea     rcx, qword_1803CE250; this
0x1801626d0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801626d7  cmp     byte ptr [rcx+8], 0
0x1801626db  jz      short loc_180162702
0x1801626dd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801626e2  cmp     [rax+7CCh], ebx
0x1801626e8  jz      short loc_180162702
0x1801626ea  mov     r9d, ebx; int
0x1801626ed  lea     rdx, aCaudstreamsink_28; "CAudStreamSink::InitializeAudioClient"
0x1801626f4  mov     r8d, 2537h; int
0x1801626fa  mov     rcx, rax; this
0x1801626fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180162702  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180162709  jb      loc_180162A8C
  ... truncated ...
```
