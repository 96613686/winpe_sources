# MFTranscodeGetAudioOutputAvailableTypes

- ea: `0x180005290`
- end: `0x180005a32`
- name: `MFTranscodeGetAudioOutputAvailableTypes`
- size: `1954`
- prototype: `HRESULT __stdcall(const GUID *const guidSubType, DWORD dwMFTFlags, IMFAttributes *pCodecConfig, IMFCollection **ppAvailableTypes)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005ed0`

## callees

- `0x1800026f0`
- `0x1800035c0`
- `0x180004a40`
- `0x180005290`
- `0x180005a40`
- `0x18000a3f4`
- `0x1800153ac`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x1800377fc`
- `0x18004f3c8`
- `0x18004f410`
- `0x1800555b0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800059b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800053e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800054e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800057d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005861`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800058ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800053e3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800054e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005588`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800057d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180005861`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800058ec`
- `MFPlat!MFCreateCollection` at `0x18000556c`
- `MFPlat!MFCreateCollection` at `0x18000556c`
- `MFPlat!MFCreateMediaType` at `0x1800056a5`
- `MFPlat!MFCreateMediaType` at `0x1800056a5`

## pseudocode

```c
HRESULT __stdcall MFTranscodeGetAudioOutputAvailableTypes(
        const GUID *const guidSubType,
        DWORD dwMFTFlags,
        IMFAttributes *pCodecConfig,
        IMFCollection **ppAvailableTypes)
{
  CallStackTracing *v6; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // esi
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  unsigned int v19; // ebx
  bool v20; // zf
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  unsigned int v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rdx
  int *v36; // r9
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  unsigned int i; // ebx
  __int64 v50; // rdi
  __int64 v51; // rcx
  unsigned int v53; // [rsp+30h] [rbp-39h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-31h] BYREF
  MFWMEncoderConfigUtil *v55; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v56[8]; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  __int64 v58; // [rsp+58h] [rbp-11h] BYREF
  IMFCollection *v59; // [rsp+60h] [rbp-9h] BYREF
  __int128 v60; // [rsp+68h] [rbp-1h] BYREF

  v6 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v6 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v6);
    v10 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v10 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v11 = 2 * v10;
      *((_QWORD *)ThreadRelativeContext + v11) = "MFTranscodeGetAudioOutputAvailableTypes";
      *((_DWORD *)ThreadRelativeContext + 2 * v11 + 2) = 68;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v6 = CallStackTracing::s_wpInstance;
  }
  v53 = 0;
  pv = 0;
  v58 = 0;
  v59 = 0;
  v55 = 0;
  v60 = 0;
  if ( ppAvailableTypes )
  {
    *ppAvailableTypes = 0;
    v12 = CMFTHelper::EnumMFTActivates(&MFMediaType_Audio, guidSubType, dwMFTFlags, &v53, (struct IMFActivate ***)&pv);
    if ( v12 >= 0 )
    {
      v19 = 0;
      v20 = v53 == 0;
      if ( v53 )
      {
        do
        {
          if ( v58 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
            v58 = 0;
          }
          if ( (!pCodecConfig
             || (int)CMFTHelper::ConfigMFTActivate(pCodecConfig, 0, *((struct IMFActivate **)pv + v19)) >= 0)
            && (*(int (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)pv + v19) + 264LL))(
                 *((_QWORD *)pv + v19),
                 &IID_IMFTransform,
                 &v58) >= 0 )
          {
            break;
          }
          ++v19;
        }
        while ( v19 < v53 );
        v20 = v19 == v53;
      }
      if ( v20 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        v12 = -1072847854;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != -1072847854 )
            CallStackContext::TraceFailure(v23, "MFTranscodeGetAudioOutputAvailableTypes", 120, -1072847854);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 19;
          goto LABEL_15;
        }
      }
      else
      {
        v12 = MFCreateCollection(&v59);
        if ( v12 >= 0 )
        {
          v28 = 0;
          v29 = *(_QWORD *)&guidSubType->Data1 - *(_QWORD *)&MFAudioFormat_WMASPDIF.Data1;
          if ( *(_QWORD *)&guidSubType->Data1 == *(_QWORD *)&MFAudioFormat_WMASPDIF.Data1 )
            v29 = *(_QWORD *)guidSubType->Data4 - *(_QWORD *)MFAudioFormat_WMASPDIF.Data4;
          if ( !v29 )
            goto LABEL_133;
          v30 = *(_QWORD *)&guidSubType->Data1 - *(_QWORD *)&MFAudioFormat_WMAudioV8.Data1;
          if ( *(_QWORD *)&guidSubType->Data1 == *(_QWORD *)&MFAudioFormat_WMAudioV8.Data1 )
            v30 = *(_QWORD *)guidSubType->Data4 - *(_QWORD *)MFAudioFormat_WMAudioV8.Data4;
          if ( !v30 )
            goto LABEL_133;
          v31 = *(_QWORD *)&guidSubType->Data1 - *(_QWORD *)&MFAudioFormat_WMAudioV9.Data1;
          if ( *(_QWORD *)&guidSubType->Data1 == *(_QWORD *)&MFAudioFormat_WMAudioV9.Data1 )
            v31 = *(_QWORD *)guidSubType->Data4 - *(_QWORD *)MFAudioFormat_WMAudioV9.Data4;
          if ( !v31 )
            goto LABEL_133;
          v32 = *(_QWORD *)&guidSubType->Data1 - *(_QWORD *)&MFAudioFormat_WMAudio_Lossless.Data1;
          if ( *(_QWORD *)&guidSubType->Data1 == *(_QWORD *)&MFAudioFormat_WMAudio_Lossless.Data1 )
            v32 = *(_QWORD *)guidSubType->Data4 - *(_QWORD *)MFAudioFormat_WMAudio_Lossless.Data4;
          if ( !v32 )
          {
LABEL_133:
            if ( pCodecConfig && (unsigned int)MFGetAttributeUINT32(pCodecConfig, MF_LOW_LATENCY, 0) )
            {
              ppMFType = 0;
              if ( MFCreateMediaType(&ppMFType) >= 0
                && ((int (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                     ppMFType,
                     &MF_MT_MAJOR_TYPE,
                     &MFMediaType_Audio) >= 0
                && ((int (__fastcall *)(IMFMediaType *, const GUID *, const GUID *const))ppMFType->lpVtbl->SetGUID)(
                     ppMFType,
                     &MF_MT_SUBTYPE,
                     guidSubType) >= 0 )
              {
                MFLowLatencyHelpers::SetLowLatencyOnObject(v33, v58, v34, ppMFType);
              }
              ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppMFType);
            }
          }
          while ( 1 )
          {
            if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, MFWMEncoderConfigUtil **))(*(_QWORD *)v58 + 112LL))(
                   v58,
                   0,
                   v28,
                   &v55) < 0 )
            {
              *ppAvailableTypes = v59;
              v59 = 0;
              goto LABEL_118;
            }
            LODWORD(ppMFType) = 0;
            v12 = (*(__int64 (__fastcall **)(MFWMEncoderConfigUtil *, const GUID *, __int128 *))(*(_QWORD *)v55 + 80LL))(
                    v55,
                    &MF_MT_SUBTYPE,
                    &v60);
            if ( v12 < 0 )
              break;
            v37 = v60 - *(_QWORD *)&guidSubType->Data1;
            if ( (_QWORD)v60 == *(_QWORD *)&guidSubType->Data1 )
              v37 = *((_QWORD *)&v60 + 1) - *(_QWORD *)guidSubType->Data4;
            if ( !v37 )
            {
              v12 = MFWMEncoderConfigUtil::ValidateWMADeviceConformanceSetting(
                      v55,
                      (struct IMFMediaType *)pCodecConfig,
                      (struct IMFAttributes *)&ppMFType,
                      v36);
              if ( v12 < 0 )
              {
                v43 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38);
                  CallStackTracing::s_wpInstance = v44;
                  if ( v44
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                  {
                    v43 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v43 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v43 + 8) )
                {
                  v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
                  if ( *((_DWORD *)v45 + 499) != v12 )
                    CallStackContext::TraceFailure(v45, "MFTranscodeGetAudioOutputAvailableTypes", 163, v12);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v14 = 22;
                  goto LABEL_15;
                }
                goto LABEL_118;
              }
              if ( (_DWORD)ppMFType )
              {
                v12 = ((__int64 (__fastcall *)(IMFCollection *, MFWMEncoderConfigUtil *))v59->lpVtbl->AddElement)(
                        v59,
                        v55);
                if ( v12 < 0 )
                {
                  v40 = (__int64 *)CallStackTracing::s_wpInstance;
                  if ( !CallStackTracing::s_wpInstance )
                  {
                    v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
                    CallStackTracing::s_wpInstance = v41;
                    if ( v41
                      && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
                    {
                      v40 = (__int64 *)CallStackTracing::s_wpInstance;
                    }
                    else
                    {
                      v40 = &qword_180069A90;
                      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                    }
                  }
                  if ( *((_BYTE *)v40 + 8) )
                  {
                    v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
                    if ( *((_DWORD *)v42 + 499) != v12 )
                      CallStackContext::TraceFailure(v42, "MFTranscodeGetAudioOutputAvailableTypes", 167, v12);
                  }
                  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  {
                    v14 = 23;
                    goto LABEL_15;
                  }
                  goto LABEL_118;
                }
              }
            }
            if ( v55 )
            {
              (*(void (__fastcall **)(MFWMEncoderConfigUtil *))(*(_QWORD *)v55 + 16LL))(v55);
              v55 = 0;
            }
            ++v28;
          }
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v47;
            if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
            {
              v46 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v46 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v46 + 8) )
          {
            v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
            if ( *((_DWORD *)v48 + 499) != v12 )
              CallStackContext::TraceFailure(v48, "MFTranscodeGetAudioOutputAvailableTypes", 159, v12);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 21;
            goto LABEL_15;
          }
        }
        else
        {
          v25 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
            CallStackTracing::s_wpInstance = v26;
            if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
            {
              v25 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v25 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v25 + 8) )
          {
            v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
            if ( *((_DWORD *)v27 + 499) != v12 )
              CallStackContext::TraceFailure(v27, "MFTranscodeGetAudioOutputAvailableTypes", 126, v12);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 20;
            goto LABEL_15;
          }
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v15);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != v12 )
          CallStackContext::TraceFailure(v18, "MFTranscodeGetAudioOutputAvailableTypes", 90, v12);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v14 = 18;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v12 = -2147467261;
    if ( !v6 )
    {
      CallStackTracing::InitInstance();
      v6 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v6);
      if ( *((_DWORD *)v13 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v13, "MFTranscodeGetAudioOutputAvailableTypes", 80, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 17;
LABEL_15:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids, 0, v12);
    }
  }
LABEL_118:
  if ( pv )
  {
    for ( i = 0; i < v53; ++i )
    {
      v50 = 8LL * i;
      v51 = *(_QWORD *)((char *)pv + v50);
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        *(_QWORD *)((char *)pv + v50) = 0;
      }
    }
    CoTaskMemFree(pv);
  }
  if ( v58 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
    v58 = 0;
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(MFWMEncoderConfigUtil *))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v59 )
  {
    ((void (__fastcall *)(IMFCollection *))v59->lpVtbl->Release)(v59);
    v59 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v56);
  return v12;
}

```

## disassembly

```asm
0x180005290  push    rbp
0x180005292  push    rbx
0x180005293  push    rsi
0x180005294  push    rdi
0x180005295  push    r12
0x180005297  push    r13
0x180005299  push    r14
0x18000529b  push    r15
0x18000529d  lea     rbp, [rsp-1Fh]
0x1800052a2  sub     rsp, 88h
0x1800052a9  mov     rax, cs:__security_cookie
0x1800052b0  xor     rax, rsp
0x1800052b3  mov     [rbp+57h+var_48], rax
0x1800052b7  mov     rdi, rcx
0x1800052ba  mov     r15, r9
0x1800052bd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800052c4  mov     r14, r8
0x1800052c7  mov     ebx, edx
0x1800052c9  test    rcx, rcx
0x1800052cc  jnz     short loc_1800052DA
0x1800052ce  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800052d3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800052da  cmp     byte ptr [rcx+8], 0
0x1800052de  lea     r13, aMftranscodeget_0; "MFTranscodeGetAudioOutputAvailableTypes"
0x1800052e5  jz      short loc_180005316
0x1800052e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800052ec  mov     ecx, [rax+7C4h]
0x1800052f2  cmp     ecx, [rax+7C8h]
0x1800052f8  jnb     short loc_180005309
0x1800052fa  add     rcx, rcx
0x1800052fd  mov     [rax+rcx*8], r13
0x180005301  mov     dword ptr [rax+rcx*8+8], 44h ; 'D'
0x180005309  inc     dword ptr [rax+7C4h]
0x18000530f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005316  xor     r12d, r12d
0x180005319  xorps   xmm0, xmm0
0x18000531c  mov     [rbp+57h+var_90], r12d
0x180005320  mov     [rbp+57h+pv], r12
0x180005324  mov     [rbp+57h+var_68], r12
0x180005328  mov     [rbp+57h+var_60], r12
0x18000532c  mov     [rbp+57h+var_80], r12
0x180005330  movups  [rbp+57h+var_58], xmm0
0x180005334  test    r15, r15
0x180005337  jnz     short loc_1800053AB
0x180005339  mov     esi, 80004003h
0x18000533e  test    rcx, rcx
0x180005341  jnz     short loc_18000534F
0x180005343  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180005348  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18000534f  cmp     [rcx+8], r12b
0x180005353  jz      short loc_180005376
0x180005355  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000535a  cmp     [rax+7CCh], esi
0x180005360  jz      short loc_180005376
0x180005362  mov     r9d, esi; int
0x180005365  mov     r8d, 50h ; 'P'; int
0x18000536b  mov     rdx, r13; char *
0x18000536e  mov     rcx, rax; this
0x180005371  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005376  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18000537b  cmp     al, 1
0x18000537d  jb      loc_180005972
0x180005383  mov     edx, 11h
0x180005388  mov     rcx, cs:WPP_GLOBAL_Control
0x18000538f  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180005396  xor     r9d, r9d
0x180005399  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18000539d  mov     rcx, [rcx+10h]
0x1800053a1  call    WPP_SF_qd
0x1800053a6  jmp     loc_180005972
0x1800053ab  lea     rax, [rbp+57h+pv]
0x1800053af  mov     [r15], r12
0x1800053b2  lea     r9, [rbp+57h+var_90]; unsigned int *
0x1800053b6  mov     [rsp+0C0h+var_A0], rax; struct IMFActivate ***
0x1800053bb  mov     r8d, ebx; unsigned int
0x1800053be  lea     rcx, MFMediaType_Audio; struct _GUID *
0x1800053c5  mov     rdx, rdi; struct _GUID *
0x1800053c8  call    ?EnumMFTActivates@CMFTHelper@@SAJAEBU_GUID@@0KPEAIPEAPEAPEAUIMFActivate@@@Z; CMFTHelper::EnumMFTActivates(_GUID const &,_GUID const &,ulong,uint *,IMFActivate * * *)
0x1800053cd  mov     esi, eax
0x1800053cf  test    eax, eax
0x1800053d1  jns     loc_180005462
0x1800053d7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800053de  test    rcx, rcx
0x1800053e1  jnz     short loc_180005424
0x1800053e3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800053e9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800053f0  mov     rcx, rax
0x1800053f3  test    rax, rax
0x1800053f6  jz      short loc_180005416
0x1800053f8  mov     rax, [rax]
0x1800053fb  mov     edx, 7F0h
0x180005400  mov     rax, [rax+8]
0x180005404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005409  test    eax, eax
0x18000540b  jz      short loc_180005416
0x18000540d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005414  jmp     short loc_180005424
0x180005416  lea     rcx, qword_180069A90; this
0x18000541d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180005424  cmp     [rcx+8], r12b
0x180005428  jz      short loc_18000544B
0x18000542a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000542f  cmp     [rax+7CCh], esi
0x180005435  jz      short loc_18000544B
0x180005437  mov     r9d, esi; int
0x18000543a  mov     r8d, 5Ah ; 'Z'; int
0x180005440  mov     rdx, r13; char *
0x180005443  mov     rcx, rax; this
0x180005446  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000544b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180005450  cmp     al, 1
0x180005452  jb      loc_180005972
0x180005458  mov     edx, 12h
0x18000545d  jmp     loc_180005388
0x180005462  mov     ebx, r12d
0x180005465  cmp     ebx, [rbp+57h+var_90]
0x180005468  jnb     short loc_1800054D2
0x18000546a  mov     rcx, [rbp+57h+var_68]
0x18000546e  test    rcx, rcx
0x180005471  jz      short loc_180005483
0x180005473  mov     rax, [rcx]
0x180005476  mov     rax, [rax+10h]
0x18000547a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547f  mov     [rbp+57h+var_68], r12
0x180005483  test    r14, r14
0x180005486  jz      short loc_1800054A0
0x180005488  mov     r8, [rbp+57h+pv]
0x18000548c  xor     edx, edx; struct IMFMediaType *
0x18000548e  mov     eax, ebx
0x180005490  mov     rcx, r14; struct IMFAttributes *
0x180005493  mov     r8, [r8+rax*8]; struct IMFActivate *
0x180005497  call    ?ConfigMFTActivate@CMFTHelper@@SAJPEAUIMFAttributes@@PEAUIMFMediaType@@PEAUIMFActivate@@@Z; CMFTHelper::ConfigMFTActivate(IMFAttributes *,IMFMediaType *,IMFActivate *)
0x18000549c  test    eax, eax
0x18000549e  js      short loc_1800054C8
0x1800054a0  mov     rax, [rbp+57h+pv]
0x1800054a4  lea     r8, [rbp+57h+var_68]
0x1800054a8  mov     ecx, ebx
0x1800054aa  lea     rdx, IID_IMFTransform
0x1800054b1  mov     rcx, [rax+rcx*8]
0x1800054b5  mov     rax, [rcx]
0x1800054b8  mov     rax, [rax+108h]
0x1800054bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054c4  test    eax, eax
0x1800054c6  jns     short loc_1800054CF
0x1800054c8  inc     ebx
0x1800054ca  cmp     ebx, [rbp+57h+var_90]
0x1800054cd  jb      short loc_18000546A
0x1800054cf  cmp     ebx, [rbp+57h+var_90]
0x1800054d2  jnz     loc_180005568
0x1800054d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800054df  mov     esi, 0C00DA412h
0x1800054e4  test    rcx, rcx
0x1800054e7  jnz     short loc_18000552A
0x1800054e9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800054ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800054f6  mov     rcx, rax
0x1800054f9  test    rax, rax
0x1800054fc  jz      short loc_18000551C
0x1800054fe  mov     rax, [rax]
0x180005501  mov     edx, 7F0h
0x180005506  mov     rax, [rax+8]
0x18000550a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000550f  test    eax, eax
0x180005511  jz      short loc_18000551C
0x180005513  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000551a  jmp     short loc_18000552A
0x18000551c  lea     rcx, qword_180069A90; this
0x180005523  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18000552a  cmp     [rcx+8], r12b
0x18000552e  jz      short loc_180005551
0x180005530  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180005535  cmp     [rax+7CCh], esi
0x18000553b  jz      short loc_180005551
0x18000553d  mov     r9d, esi; int
0x180005540  mov     r8d, 78h ; 'x'; int
0x180005546  mov     rdx, r13; char *
0x180005549  mov     rcx, rax; this
0x18000554c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180005551  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180005556  cmp     al, 1
0x180005558  jb      loc_180005972
0x18000555e  mov     edx, 13h
0x180005563  jmp     loc_180005388
0x180005568  lea     rcx, [rbp+57h+var_60]
0x18000556c  call    cs:__imp_MFCreateCollection
0x180005572  mov     esi, eax
0x180005574  test    eax, eax
0x180005576  jns     loc_180005607
0x18000557c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180005583  test    rcx, rcx
0x180005586  jnz     short loc_1800055C9
0x180005588  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000558e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180005595  mov     rcx, rax
0x180005598  test    rax, rax
0x18000559b  jz      short loc_1800055BB
0x18000559d  mov     rax, [rax]
0x1800055a0  mov     edx, 7F0h
0x1800055a5  mov     rax, [rax+8]
0x1800055a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ae  test    eax, eax
0x1800055b0  jz      short loc_1800055BB
0x1800055b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800055b9  jmp     short loc_1800055C9
0x1800055bb  lea     rcx, qword_180069A90; this
0x1800055c2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800055c9  cmp     [rcx+8], r12b
0x1800055cd  jz      short loc_1800055F0
0x1800055cf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800055d4  cmp     [rax+7CCh], esi
0x1800055da  jz      short loc_1800055F0
0x1800055dc  mov     r9d, esi; int
0x1800055df  mov     r8d, 7Eh ; '~'; int
0x1800055e5  mov     rdx, r13; char *
0x1800055e8  mov     rcx, rax; this
0x1800055eb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800055f0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800055f5  cmp     al, 1
0x1800055f7  jb      loc_180005972
0x1800055fd  mov     edx, 14h
0x180005602  jmp     loc_180005388
0x180005607  mov     rax, [rdi]
0x18000560a  mov     ebx, r12d
0x18000560d  sub     rax, qword ptr cs:MFAudioFormat_WMASPDIF.Data1
0x180005614  jnz     short loc_180005621
0x180005616  mov     rax, [rdi+8]
0x18000561a  sub     rax, qword ptr cs:MFAudioFormat_WMASPDIF.Data4
0x180005621  test    rax, rax
0x180005624  jz      short loc_18000567E
0x180005626  mov     rax, [rdi]
0x180005629  sub     rax, qword ptr cs:MFAudioFormat_WMAudioV8.Data1
0x180005630  jnz     short loc_18000563D
0x180005632  mov     rax, [rdi+8]
0x180005636  sub     rax, qword ptr cs:MFAudioFormat_WMAudioV8.Data4
0x18000563d  test    rax, rax
0x180005640  jz      short loc_18000567E
0x180005642  mov     rax, [rdi]
0x180005645  sub     rax, qword ptr cs:MFAudioFormat_WMAudioV9.Data1
0x18000564c  jnz     short loc_180005659
0x18000564e  mov     rax, [rdi+8]
0x180005652  sub     rax, qword ptr cs:MFAudioFormat_WMAudioV9.Data4
0x180005659  test    rax, rax
0x18000565c  jz      short loc_18000567E
0x18000565e  mov     rax, [rdi]
0x180005661  sub     rax, qword ptr cs:MFAudioFormat_WMAudio_Lossless.Data1
0x180005668  jnz     short loc_180005675
0x18000566a  mov     rax, [rdi+8]
0x18000566e  sub     rax, qword ptr cs:MFAudioFormat_WMAudio_Lossless.Data4
0x180005675  test    rax, rax
0x180005678  jnz     loc_180005710
0x18000567e  test    r14, r14
0x180005681  jz      loc_180005710
0x180005687  xor     r8d, r8d
0x18000568a  lea     rdx, MF_LOW_LATENCY
0x180005691  mov     rcx, r14
0x180005694  call    MFGetAttributeUINT32
0x180005699  test    eax, eax
0x18000569b  jz      short loc_180005710
0x18000569d  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x1800056a1  mov     [rbp+57h+ppMFType], r12
0x1800056a5  call    cs:__imp_MFCreateMediaType
0x1800056ab  test    eax, eax
0x1800056ad  js      short loc_180005702
0x1800056af  mov     rcx, [rbp+57h+ppMFType]
0x1800056b3  lea     r8, MFMediaType_Audio
0x1800056ba  lea     rdx, MF_MT_MAJOR_TYPE
0x1800056c1  mov     rax, [rcx]
0x1800056c4  mov     rax, [rax+0C0h]
0x1800056cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d0  test    eax, eax
0x1800056d2  js      short loc_180005702
0x1800056d4  mov     rcx, [rbp+57h+ppMFType]
0x1800056d8  lea     rdx, MF_MT_SUBTYPE
0x1800056df  mov     r8, rdi
0x1800056e2  mov     rax, [rcx]
0x1800056e5  mov     rax, [rax+0C0h]
0x1800056ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f1  test    eax, eax
0x1800056f3  js      short loc_180005702
0x1800056f5  mov     r9, [rbp+57h+ppMFType]
0x1800056f9  mov     rdx, [rbp+57h+var_68]
0x1800056fd  call    ?SetLowLatencyOnObject@MFLowLatencyHelpers@@YAJHPEAUIUnknown@@W4ObjectType@1@PEAUIMFMediaType@@@Z; MFLowLatencyHelpers::SetLowLatencyOnObject(int,IUnknown *,MFLowLatencyHelpers::ObjectType,IMFMediaType *)
0x180005702  lea     rcx, [rbp+57h+ppMFType]
0x180005706  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x18000570b  nop     dword ptr [rax+rax+00h]
0x180005710  mov     rcx, [rbp+57h+var_68]
0x180005714  lea     r9, [rbp+57h+var_80]
0x180005718  mov     r8d, ebx
0x18000571b  xor     edx, edx
0x18000571d  mov     rax, [rcx]
0x180005720  mov     rax, [rax+70h]
0x180005724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005729  test    eax, eax
0x18000572b  js      loc_180005967
0x180005731  mov     rcx, [rbp+57h+var_80]
0x180005735  lea     r8, [rbp+57h+var_58]
0x180005739  lea     rdx, MF_MT_SUBTYPE
0x180005740  mov     dword ptr [rbp+57h+ppMFType], r12d
0x180005744  mov     rax, [rcx]
0x180005747  mov     rax, [rax+50h]
  ... truncated ...
```
