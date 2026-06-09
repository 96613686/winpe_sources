# CAudStreamSink::ActivateAudioClientInterface(void)

- ea: `0x180173d70`
- end: `0x180174677`
- name: `?ActivateAudioClientInterface@CAudStreamSink@@QEAAJXZ`
- size: `2311`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this)`
- caller_count: `4`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18014f204`
- `0x1801621bc`
- `0x1801beb1c`
- `0x18031941c`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004c6ec`
- `0x180050d6c`
- `0x18005a3d4`
- `0x18006b388`
- `0x18007b9ec`
- `0x1800e39a8`
- `0x1800ec0e0`
- `0x18012d300`
- `0x180173d70`
- `0x180177fd8`
- `0x18017fff8`
- `0x180183314`
- `0x180225f38`
- `0x180258480`
- `0x1802dedc4`
- `0x18031a7e4`
- `0x18032357c`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801741e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801741f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801741e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801741f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801741cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801741cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180173f9b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180173fef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174044`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174099`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801740ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174143`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180173f9b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180173fef`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174044`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174099`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801740ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180174143`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180174345`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180174345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180174355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017441c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801744a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180174355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18017441c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801744a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801744c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180174601`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801744c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180174601`

## string_xrefs

- `0x180173d9a`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x180173e66`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x1801743c8`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x18017445e`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x180174536`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x1801745bb`: `CAudStreamSink::ActivateAudioClientInterface`
- `0x18017411b`: `AllowCompressedFormatSupport`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::ActivateAudioClientInterface(CAudStreamSink *this)
{
  CallStackTracing *v2; // rcx
  int v3; // r13d
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  __int128 *v6; // rax
  __int128 v7; // xmm0
  int inited; // ebx
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // ecx
  char v13; // al
  __int64 v14; // r14
  int v15; // r15d
  __int64 v16; // rbx
  struct _RTL_CRITICAL_SECTION *v17; // rcx
  __int64 v18; // rcx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  int IsEqualToPendingStreamingEndpointId; // eax
  int v27; // ebx
  unsigned __int8 v28; // cl
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v41[8]; // [rsp+48h] [rbp-B8h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v43[8]; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv[2]; // [rsp+F0h] [rbp-10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v41,
    "CAudStreamSink::ActivateAudioClientInterface",
    8129);
  v2 = CallStackTracing::s_wpInstance;
  v3 = 0;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v6 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 825) + 280LL))(
                       *((_QWORD *)this + 825),
                       pv);
    v2 = CallStackTracing::s_wpInstance;
    v7 = *v6;
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
    *((_OWORD *)ThreadRelativeContext + 125) = v7;
  }
  memset(&pvar, 0, sizeof(pvar));
  if ( *((_QWORD *)this + 829) )
  {
    inited = -1072871856;
    if ( !v2 )
    {
      CallStackTracing::InitInstance();
      v2 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext(v2);
      if ( *((_DWORD *)v9 + 499) != -1072871856 )
        CallStackContext::TraceFailure(v9, "CAudStreamSink::ActivateAudioClientInterface", 8137, -1072871856);
    }
    if ( g_wppLevels )
    {
      v10 = 524;
LABEL_103:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        inited);
    }
    goto LABEL_104;
  }
  *((_DWORD *)this + 1670) = *((_DWORD *)this + 1812);
  if ( *((_DWORD *)this + 1820) )
  {
    *((_QWORD *)this + 837) = 2000000;
  }
  else if ( *((_DWORD *)this + 1818) )
  {
    *((_QWORD *)this + 837) = 20000000;
  }
  if ( *((_DWORD *)this + 1814) )
  {
    if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
    {
      pdwType = (LPDWORD)*((_QWORD *)this + 908);
      LODWORD(pv[0]) = 1852133953;
      McTemplateU0s4px_EventWriteTransfer(
        (_DWORD)v2,
        (unsigned int)&Audio_Renderer_Buffer_Duration_Set,
        (unsigned int)pv,
        (_DWORD)this,
        (char)pdwType);
    }
    v11 = *((_QWORD *)this + 908);
    if ( v11 > 6000000000LL )
      goto LABEL_20;
    if ( *((_DWORD *)this + 1813) )
    {
      if ( v11 <= *((_QWORD *)this + 837) )
      {
        *((_QWORD *)this + 839) = v11;
        goto LABEL_26;
      }
    }
    else if ( v11 >= *((_QWORD *)this + 839) )
    {
      *((_QWORD *)this + 837) = v11;
      goto LABEL_26;
    }
LABEL_20:
    inited = -1072875854;
    goto LABEL_104;
  }
LABEL_26:
  pvData = 0;
  pcbData = 4;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
          L"PullModeDisable",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_DWORD *)this + 1666) = 0;
  }
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
          L"PullModeLowLatencyLimit",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_QWORD *)this + 839) = pvData;
  }
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
          L"PullModeLowPowerLimit",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_QWORD *)this + 837) = pvData;
  }
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
          L"ForceLowLatency",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_DWORD *)this + 1813) = 1;
  }
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
          L"UseMediaStreamCategory",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_DWORD *)this + 1670) = 11;
  }
  pcbData = 4;
  pvData = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"AllowCompressedFormatSupport",
          0x18u,
          0,
          &pvData,
          &pcbData)
    && pvData )
  {
    *((_DWORD *)this + 1682) = 1;
  }
  v13 = *((_DWORD *)this + 1813) == 1;
  if ( (Microsoft_Windows_MediaFoundation_PerformanceEnableBits & 1) != 0 )
  {
    LODWORD(pv[0]) = 1852133953;
    McTemplateU0s4pt_EventWriteTransfer(v12, (unsigned int)&Audio_Low_Latency_Set, (unsigned int)pv, (_DWORD)this, v13);
  }
  v14 = *((_QWORD *)this + 818);
  if ( v14 )
    (*(void (__fastcall **)(_QWORD, struct tagPROPVARIANT *))(*(_QWORD *)v14 + 64LL))(*((_QWORD *)this + 818), &pvar);
  v15 = 0;
  while ( 1 )
  {
    v16 = *((_QWORD *)this + 831);
    if ( v16 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 216));
      v17 = (struct _RTL_CRITICAL_SECTION *)(v16 + 216);
      if ( *(_QWORD *)(v16 + 208) )
      {
        LeaveCriticalSection(v17);
        v15 = 1;
      }
      else
      {
        LeaveCriticalSection(v17);
        v15 = 0;
      }
    }
    v18 = *((_QWORD *)this + 842);
    v19 = *(_OWORD *)((char *)this + 7224);
    v43[0] = *(_OWORD *)((char *)this + 7208);
    v20 = *(_OWORD *)((char *)this + 7240);
    v43[1] = v19;
    v21 = *(_OWORD *)((char *)this + 7256);
    v43[2] = v20;
    v22 = *(_OWORD *)((char *)this + 7272);
    v43[3] = v21;
    v23 = *(_OWORD *)((char *)this + 7288);
    v43[4] = v22;
    v24 = *(_OWORD *)((char *)this + 7304);
    v43[5] = v23;
    v25 = *(_OWORD *)((char *)this + 7320);
    v43[6] = v24;
    v43[7] = v25;
    inited = CAudioClientManager::InitDevice(v18, v43);
    if ( inited < 0 )
      break;
    if ( !v15 )
      goto LABEL_64;
    pv[0] = 0;
    inited = CAudStreamSink::GetCurrentStreamingEndpointId(this, (unsigned __int16 **)pv);
    if ( inited < 0 )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v31 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v31 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(v31);
        if ( *((_DWORD *)v32 + 499) != inited )
          CallStackContext::TraceFailure(v32, "CAudStreamSink::ActivateAudioClientInterface", 8297, inited);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          526,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          this,
          inited);
      CoTaskMemFree(pv[0]);
      goto LABEL_104;
    }
    IsEqualToPendingStreamingEndpointId = CMMNotificationClient::IsEqualToPendingStreamingEndpointId(
                                            *((CMMNotificationClient **)this + 831),
                                            (const unsigned __int16 *)pv[0]);
    v27 = IsEqualToPendingStreamingEndpointId;
    v28 = (unsigned __int8)byte_1803CECE9;
    if ( (unsigned __int8)byte_1803CECE9 >= 8u )
    {
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        527,
        (unsigned int)&WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        (_DWORD)this,
        IsEqualToPendingStreamingEndpointId,
        (__int64)pv[0]);
      v28 = (unsigned __int8)byte_1803CECE9;
    }
    if ( !v27 )
    {
      if ( (unsigned int)++v3 >= 0x1E )
      {
        if ( v28 >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 529, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
        CoTaskMemFree(pv[0]);
LABEL_64:
        inited = CAudioClientManager::InitNonSpatialClient(
                   *((CAudioClientManager **)this + 842),
                   (struct IAudStreamSinkCallback *)(((unsigned __int64)this + 656)
                                                   & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                   &pvar);
        if ( inited >= 0 )
        {
          CAudioClientManager::GetAudioClient(
            *((CAudioClientManager **)this + 842),
            (struct IAudioClient2 **)this + 829);
          PropVariantClear((PROPVARIANT *)&pvar);
          if ( v14 )
            (*(void (__fastcall **)(__int64, struct tagPROPVARIANT *))(*(_QWORD *)v14 + 72LL))(v14, &pvar);
          inited = CAudioClientManager::InitSpatialClient(
                     *((CAudioClientManager **)this + 842),
                     (CAudStreamSink *)((char *)this + 656),
                     &pvar);
          if ( inited >= 0 )
          {
            if ( !*((_QWORD *)this + 916) || !*((_DWORD *)this + 1830) )
              CAudioClientManager::GetEndpointOffloadingCapability(
                *((CAudioClientManager **)this + 842),
                (int *)this + 1667);
          }
          else
          {
            v33 = CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::InitInstance();
              v33 = CallStackTracing::s_wpInstance;
            }
            if ( *((_BYTE *)v33 + 8) )
            {
              v34 = CallStackTracing::GetThreadRelativeContext(v33);
              if ( *((_DWORD *)v34 + 499) != inited )
                CallStackContext::TraceFailure(v34, "CAudStreamSink::ActivateAudioClientInterface", 8350, inited);
            }
            if ( g_wppLevels )
            {
              v10 = 531;
              goto LABEL_103;
            }
          }
        }
        else
        {
          v29 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v29 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v29 + 8) )
          {
            v30 = CallStackTracing::GetThreadRelativeContext(v29);
            if ( *((_DWORD *)v30 + 499) != inited )
              CallStackContext::TraceFailure(v30, "CAudStreamSink::ActivateAudioClientInterface", 8336, inited);
          }
          if ( g_wppLevels )
          {
            v10 = 530;
            goto LABEL_103;
          }
        }
        goto LABEL_104;
      }
      if ( v28 >= 8u )
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          528,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          this,
          v3,
          30 - v3);
      CAudioClientManager::Reset(*((CAudioClientManager **)this + 842));
      Sleep(0x64u);
    }
    CoTaskMemFree(pv[0]);
    if ( v27 )
      goto LABEL_64;
  }
  v35 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v35 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v35 + 8) )
  {
    v36 = CallStackTracing::GetThreadRelativeContext(v35);
    if ( *((_DWORD *)v36 + 499) != inited )
      CallStackContext::TraceFailure(v36, "CAudStreamSink::ActivateAudioClientInterface", 8290, inited);
  }
  if ( g_wppLevels )
  {
    v10 = 525;
    goto LABEL_103;
  }
LABEL_104:
  PropVariantClear((PROPVARIANT *)&pvar);
  if ( inited < 0 )
  {
    if ( (_BYTE)byte_1803CECE9 )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        532,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        this,
        inited,
        -1072869756);
    inited = -1072869756;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180173d70  push    rbp
0x180173d72  push    rbx
0x180173d73  push    rsi
0x180173d74  push    rdi
0x180173d75  push    r12
0x180173d77  push    r13
0x180173d79  push    r14
0x180173d7b  push    r15
0x180173d7d  lea     rbp, [rsp-18h]
0x180173d82  sub     rsp, 118h
0x180173d89  mov     rax, cs:__security_cookie
0x180173d90  xor     rax, rsp
0x180173d93  mov     [rbp+50h+var_50], rax
0x180173d97  mov     rsi, rcx
0x180173d9a  lea     rdx, aCaudstreamsink_6; "CAudStreamSink::ActivateAudioClientInte"...
0x180173da1  lea     rcx, [rsp+150h+var_108]; this
0x180173da6  mov     r8d, 1FC1h; int
0x180173dac  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180173db1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180173db8  xor     r13d, r13d
0x180173dbb  cmp     [rcx+8], r13b
0x180173dbf  jz      short loc_180173E1E
0x180173dc1  cmp     [rsi+19C8h], r13
0x180173dc8  jz      short loc_180173E1E
0x180173dca  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180173dcf  mov     rcx, [rsi+19C8h]
0x180173dd6  mov     rdi, rax
0x180173dd9  mov     rdx, [rcx]
0x180173ddc  mov     rax, [rdx+128h]
0x180173de3  call    cs:__guard_dispatch_icall_fptr
0x180173de9  mov     rcx, [rsi+19C8h]
0x180173df0  mov     ebx, eax
0x180173df2  mov     rdx, [rcx]
0x180173df5  mov     rax, [rdx+118h]
0x180173dfc  lea     rdx, [rbp+50h+pv]
0x180173e00  call    cs:__guard_dispatch_icall_fptr
0x180173e06  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180173e0d  movups  xmm0, xmmword ptr [rax]
0x180173e10  mov     [rdi+7E0h], ebx
0x180173e16  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180173e1e  xor     eax, eax
0x180173e20  lea     r12, [rsi+19E8h]
0x180173e27  xorps   xmm0, xmm0
0x180173e2a  mov     [rsp+150h+var_F0], rax
0x180173e2f  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x180173e34  cmp     [r12], r13
0x180173e38  jz      short loc_180173E97
0x180173e3a  mov     ebx, 0C00D4650h
0x180173e3f  test    rcx, rcx
0x180173e42  jnz     short loc_180173E50
0x180173e44  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180173e49  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180173e50  cmp     [rcx+8], r13b
0x180173e54  jz      short loc_180173E7B
0x180173e56  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180173e5b  cmp     [rax+7CCh], ebx
0x180173e61  jz      short loc_180173E7B
0x180173e63  mov     r9d, ebx; int
0x180173e66  lea     rdx, aCaudstreamsink_6; "CAudStreamSink::ActivateAudioClientInte"...
0x180173e6d  mov     r8d, 1FC9h; int
0x180173e73  mov     rcx, rax; this
0x180173e76  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180173e7b  mov     edi, 1
0x180173e80  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180173e87  jb      loc_1801745FC
0x180173e8d  mov     edx, 20Ch
0x180173e92  jmp     loc_1801745DE
0x180173e97  mov     eax, [rsi+1C50h]
0x180173e9d  mov     [rsi+1A18h], eax
0x180173ea3  cmp     [rsi+1C70h], r13d
0x180173eaa  jz      short loc_180173EB9
0x180173eac  mov     qword ptr [rsi+1A28h], 1E8480h
0x180173eb7  jmp     short loc_180173ECD
0x180173eb9  cmp     [rsi+1C68h], r13d
0x180173ec0  jz      short loc_180173ECD
0x180173ec2  mov     qword ptr [rsi+1A28h], 1312D00h
0x180173ecd  mov     edi, 1
0x180173ed2  cmp     [rsi+1C58h], r13d
0x180173ed9  jz      short loc_180173F55
0x180173edb  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, dil
0x180173ee2  jz      short loc_180173F0A
0x180173ee4  mov     rax, [rsi+1C60h]
0x180173eeb  lea     r8, [rbp+50h+pv]
0x180173eef  mov     r9, rsi
0x180173ef2  mov     [rsp+150h+pdwType], rax
0x180173ef7  lea     rdx, Audio_Renderer_Buffer_Duration_Set
0x180173efe  mov     dword ptr [rbp+50h+pv], 6E655241h
0x180173f05  call    McTemplateU0s4px_EventWriteTransfer
0x180173f0a  mov     rax, [rsi+1C60h]
0x180173f11  mov     rcx, 165A0BC00h
0x180173f1b  cmp     rax, rcx
0x180173f1e  jle     short loc_180173F2A
0x180173f20  mov     ebx, 0C00D36B2h
0x180173f25  jmp     loc_1801745FC
0x180173f2a  cmp     [rsi+1C54h], r13d
0x180173f31  jz      short loc_180173F45
0x180173f33  cmp     rax, [rsi+1A28h]
0x180173f3a  jg      short loc_180173F20
0x180173f3c  mov     [rsi+1A38h], rax
0x180173f43  jmp     short loc_180173F55
0x180173f45  cmp     rax, [rsi+1A38h]
0x180173f4c  jl      short loc_180173F20
0x180173f4e  mov     [rsi+1A28h], rax
0x180173f55  mov     ebx, 4
0x180173f5a  mov     [rsp+150h+var_110], r13d
0x180173f5f  lea     rax, [rsp+150h+var_10C]
0x180173f64  mov     [rsp+150h+var_10C], ebx
0x180173f68  mov     [rsp+150h+pcbData], rax; pcbData
0x180173f6d  lea     r8, aPullmodedisabl; "PullModeDisable"
0x180173f74  lea     rax, [rsp+150h+var_110]
0x180173f79  mov     r15, 0FFFFFFFF80000002h
0x180173f80  mov     [rsp+150h+pvData], rax; pvData
0x180173f85  lea     r14d, [rbx+14h]
0x180173f89  mov     r9d, r14d; dwFlags
0x180173f8c  mov     [rsp+150h+pdwType], r13; pdwType
0x180173f91  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Media Foun"...
0x180173f98  mov     rcx, r15; hkey
0x180173f9b  call    cs:__imp_RegGetValueW
0x180173fa2  nop     dword ptr [rax+rax+00h]
0x180173fa7  test    eax, eax
0x180173fa9  jnz     short loc_180173FB9
0x180173fab  cmp     [rsp+150h+var_110], r13d
0x180173fb0  jz      short loc_180173FB9
0x180173fb2  mov     [rsi+1A08h], r13d
0x180173fb9  lea     rax, [rsp+150h+var_10C]
0x180173fbe  mov     [rsp+150h+var_10C], ebx
0x180173fc2  mov     [rsp+150h+pcbData], rax; pcbData
0x180173fc7  lea     r8, aPullmodelowlat; "PullModeLowLatencyLimit"
0x180173fce  lea     rax, [rsp+150h+var_110]
0x180173fd3  mov     [rsp+150h+var_110], r13d
0x180173fd8  mov     [rsp+150h+pvData], rax; pvData
0x180173fdd  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Media Foun"...
0x180173fe4  mov     r9d, r14d; dwFlags
0x180173fe7  mov     [rsp+150h+pdwType], r13; pdwType
0x180173fec  mov     rcx, r15; hkey
0x180173fef  call    cs:__imp_RegGetValueW
0x180173ff6  nop     dword ptr [rax+rax+00h]
0x180173ffb  test    eax, eax
0x180173ffd  jnz     short loc_18017400E
0x180173fff  mov     eax, [rsp+150h+var_110]
0x180174003  test    eax, eax
0x180174005  jz      short loc_18017400E
0x180174007  mov     [rsi+1A38h], rax
0x18017400e  lea     rax, [rsp+150h+var_10C]
0x180174013  mov     [rsp+150h+var_10C], ebx
0x180174017  mov     [rsp+150h+pcbData], rax; pcbData
0x18017401c  lea     r8, aPullmodelowpow; "PullModeLowPowerLimit"
0x180174023  lea     rax, [rsp+150h+var_110]
0x180174028  mov     [rsp+150h+var_110], r13d
0x18017402d  mov     [rsp+150h+pvData], rax; pvData
0x180174032  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Media Foun"...
0x180174039  mov     r9d, r14d; dwFlags
0x18017403c  mov     [rsp+150h+pdwType], r13; pdwType
0x180174041  mov     rcx, r15; hkey
0x180174044  call    cs:__imp_RegGetValueW
0x18017404b  nop     dword ptr [rax+rax+00h]
0x180174050  test    eax, eax
0x180174052  jnz     short loc_180174063
0x180174054  mov     eax, [rsp+150h+var_110]
0x180174058  test    eax, eax
0x18017405a  jz      short loc_180174063
0x18017405c  mov     [rsi+1A28h], rax
0x180174063  lea     rax, [rsp+150h+var_10C]
0x180174068  mov     [rsp+150h+var_10C], ebx
0x18017406c  mov     [rsp+150h+pcbData], rax; pcbData
0x180174071  lea     r8, aForcelowlatenc; "ForceLowLatency"
0x180174078  lea     rax, [rsp+150h+var_110]
0x18017407d  mov     [rsp+150h+var_110], r13d
0x180174082  mov     [rsp+150h+pvData], rax; pvData
0x180174087  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Media Foun"...
0x18017408e  mov     r9d, r14d; dwFlags
0x180174091  mov     [rsp+150h+pdwType], r13; pdwType
0x180174096  mov     rcx, r15; hkey
0x180174099  call    cs:__imp_RegGetValueW
0x1801740a0  nop     dword ptr [rax+rax+00h]
0x1801740a5  test    eax, eax
0x1801740a7  jnz     short loc_1801740B6
0x1801740a9  cmp     [rsp+150h+var_110], r13d
0x1801740ae  jz      short loc_1801740B6
0x1801740b0  mov     [rsi+1C54h], edi
0x1801740b6  lea     rax, [rsp+150h+var_10C]
0x1801740bb  mov     [rsp+150h+var_10C], ebx
0x1801740bf  mov     [rsp+150h+pcbData], rax; pcbData
0x1801740c4  lea     r8, aUsemediastream; "UseMediaStreamCategory"
0x1801740cb  lea     rax, [rsp+150h+var_110]
0x1801740d0  mov     [rsp+150h+var_110], r13d
0x1801740d5  mov     [rsp+150h+pvData], rax; pvData
0x1801740da  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Media Foun"...
0x1801740e1  mov     r9d, r14d; dwFlags
0x1801740e4  mov     [rsp+150h+pdwType], r13; pdwType
0x1801740e9  mov     rcx, r15; hkey
0x1801740ec  call    cs:__imp_RegGetValueW
0x1801740f3  nop     dword ptr [rax+rax+00h]
0x1801740f8  test    eax, eax
0x1801740fa  jnz     short loc_18017410D
0x1801740fc  cmp     [rsp+150h+var_110], r13d
0x180174101  jz      short loc_18017410D
0x180174103  mov     dword ptr [rsi+1A18h], 0Bh
0x18017410d  lea     rax, [rsp+150h+var_10C]
0x180174112  mov     [rsp+150h+var_10C], ebx
0x180174116  mov     [rsp+150h+pcbData], rax; pcbData
0x18017411b  lea     r8, aAllowcompresse; "AllowCompressedFormatSupport"
0x180174122  lea     rax, [rsp+150h+var_110]
0x180174127  mov     [rsp+150h+var_110], r13d
0x18017412c  mov     [rsp+150h+pvData], rax; pvData
0x180174131  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180174138  mov     r9d, r14d; dwFlags
0x18017413b  mov     [rsp+150h+pdwType], r13; pdwType
0x180174140  mov     rcx, r15; hkey
0x180174143  call    cs:__imp_RegGetValueW
0x18017414a  nop     dword ptr [rax+rax+00h]
0x18017414f  test    eax, eax
0x180174151  jnz     short loc_180174160
0x180174153  cmp     [rsp+150h+var_110], r13d
0x180174158  jz      short loc_180174160
0x18017415a  mov     [rsi+1A48h], edi
0x180174160  cmp     [rsi+1C54h], edi
0x180174166  mov     eax, r13d
0x180174169  setz    al
0x18017416c  test    byte ptr cs:Microsoft_Windows_MediaFoundation_PerformanceEnableBits, dil
0x180174173  jz      short loc_180174193
0x180174175  mov     r9, rsi
0x180174178  mov     dword ptr [rbp+50h+pv], 6E655241h
0x18017417f  lea     r8, [rbp+50h+pv]
0x180174183  mov     dword ptr [rsp+150h+pdwType], eax
0x180174187  lea     rdx, Audio_Low_Latency_Set
0x18017418e  call    McTemplateU0s4pt_EventWriteTransfer
0x180174193  mov     r14, [rsi+1990h]
0x18017419a  test    r14, r14
0x18017419d  jz      short loc_1801741B4
0x18017419f  mov     rax, [r14]
0x1801741a2  lea     rdx, [rsp+150h+pvar]
0x1801741a7  mov     rcx, r14
0x1801741aa  mov     rax, [rax+40h]
0x1801741ae  call    cs:__guard_dispatch_icall_fptr
0x1801741b4  xor     r15d, r15d
0x1801741b7  mov     rbx, [rsi+19F8h]
0x1801741be  test    rbx, rbx
0x1801741c1  jz      short loc_180174206
0x1801741c3  lea     r15, [rbx+0D8h]
0x1801741ca  mov     rcx, r15; lpCriticalSection
0x1801741cd  call    cs:__imp_EnterCriticalSection
0x1801741d4  nop     dword ptr [rax+rax+00h]
0x1801741d9  cmp     qword ptr [rbx+0D0h], 0
0x1801741e1  mov     rcx, r15; lpCriticalSection
0x1801741e4  jz      short loc_1801741F7
0x1801741e6  call    cs:__imp_LeaveCriticalSection
0x1801741ed  nop     dword ptr [rax+rax+00h]
0x1801741f2  mov     r15d, edi
0x1801741f5  jmp     short loc_180174206
0x1801741f7  call    cs:__imp_LeaveCriticalSection
0x1801741fe  nop     dword ptr [rax+rax+00h]
0x180174203  xor     r15d, r15d
0x180174206  movups  xmm0, xmmword ptr [rsi+1C28h]
0x18017420d  mov     rcx, [rsi+1A50h]
0x180174214  lea     rdx, [rsp+150h+var_E0]
0x180174219  movups  xmm1, xmmword ptr [rsi+1C38h]
0x180174220  movaps  [rsp+150h+var_E0], xmm0
0x180174225  movups  xmm0, xmmword ptr [rsi+1C48h]
0x18017422c  movaps  [rbp+50h+var_D0], xmm1
0x180174230  movups  xmm1, xmmword ptr [rsi+1C58h]
0x180174237  movaps  [rbp+50h+var_C0], xmm0
0x18017423b  movups  xmm0, xmmword ptr [rsi+1C68h]
0x180174242  movaps  [rbp+50h+var_B0], xmm1
0x180174246  movups  xmm1, xmmword ptr [rsi+1C78h]
0x18017424d  movaps  [rbp+50h+var_A0], xmm0
0x180174251  movups  xmm0, xmmword ptr [rsi+1C88h]
0x180174258  movaps  [rbp+50h+var_90], xmm1
0x18017425c  movups  xmm1, xmmword ptr [rsi+1C98h]
0x180174263  movaps  [rbp+50h+var_80], xmm0
0x180174267  movaps  [rbp+50h+var_70], xmm1
0x18017426b  call    ?InitDevice@CAudioClientManager@@QEAAJUSARPARAMS@@@Z; CAudioClientManager::InitDevice(SARPARAMS)
0x180174270  mov     ebx, eax
0x180174272  test    eax, eax
0x180174274  js      loc_18017458A
0x18017427a  test    r15d, r15d
0x18017427d  jz      loc_180174369
0x180174283  lea     rdx, [rbp+50h+pv]; unsigned __int16 **
0x180174287  mov     [rbp+50h+pv], 0
0x18017428f  mov     rcx, rsi; this
0x180174292  call    ?GetCurrentStreamingEndpointId@CAudStreamSink@@QEAAJPEAPEAG@Z; CAudStreamSink::GetCurrentStreamingEndpointId(ushort * *)
0x180174297  mov     ebx, eax
0x180174299  test    eax, eax
0x18017429b  js      loc_18017442D
0x1801742a1  mov     rdx, [rbp+50h+pv]; unsigned __int16 *
0x1801742a5  mov     rcx, [rsi+19F8h]; this
0x1801742ac  call    ?IsEqualToPendingStreamingEndpointId@CMMNotificationClient@@QEAAHPEBG@Z; CMMNotificationClient::IsEqualToPendingStreamingEndpointId(ushort const *)
0x1801742b1  mov     ebx, eax
0x1801742b3  mov     cl, cs:byte_1803CECE9
0x1801742b9  cmp     cl, 8
0x1801742bc  jb      short loc_1801742F0
0x1801742be  mov     rcx, [rbp+50h+pv]
0x1801742c2  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1801742c9  mov     [rsp+150h+pvData], rcx
0x1801742ce  mov     edx, 20Fh
0x1801742d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801742da  mov     r9, rsi
0x1801742dd  mov     dword ptr [rsp+150h+pdwType], eax
0x1801742e1  mov     rcx, [rcx+38h]
0x1801742e5  call    WPP_SF_qDS
  ... truncated ...
```
