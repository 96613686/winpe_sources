# CMFWMVEncoderActivate::InstantiateEncoder(void)

- ea: `0x18027c100`
- end: `0x18027c716`
- name: `?InstantiateEncoder@CMFWMVEncoderActivate@@MEAAJXZ`
- size: `1558`
- prototype: `__int64 __fastcall(CMFWMVEncoderActivate *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x1801976f4`
- `0x180258480`
- `0x18027b06c`
- `0x18027c100`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027c6c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027c6c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18027c3ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18027c3ec`
- `MFPlat!MFTEnum` at `0x18027c316`
- `MFPlat!MFTEnum` at `0x18027c316`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c197`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c338`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c52e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c5d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c197`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c24b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c338`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c415`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c52e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c5d7`

## pseudocode

```c
__int64 __fastcall CMFWMVEncoderActivate::InstantiateEncoder(CMFWMVEncoderActivate *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // rdx
  HRESULT Instance; // ebx
  __int64 v5; // r8
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 *v18; // rcx
  CallStackTracing *v19; // rax
  struct CallStackContext *v20; // rax
  int v21; // esi
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  struct IMFTransform *v30; // r8
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v39; // rax
  _BYTE v41[4]; // [rsp+40h] [rbp-29h] BYREF
  UINT32 pcMFTs; // [rsp+44h] [rbp-25h] BYREF
  CLSID *ppclsidMFT; // [rsp+48h] [rbp-21h] BYREF
  struct IMFMediaType *v44; // [rsp+50h] [rbp-19h] BYREF
  __int64 v45; // [rsp+58h] [rbp-11h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-9h] BYREF
  MFT_REGISTER_TYPE_INFO pOutputType; // [rsp+70h] [rbp+7h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v41, "CMFWMVEncoderActivate::InstantiateEncoder", 680);
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 14);
  v45 = 0;
  memset(&pOutputType, 0, sizeof(pOutputType));
  ppclsidMFT = 0;
  pcMFTs = 0;
  v44 = 0;
  Instance = (**v2)(v2, &IID_IMFVideoMediaType, &v45);
  if ( Instance >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 304LL))(v45);
    if ( v10 )
    {
      pOutputType.guidMajorType = MEDIATYPE_Video;
      pOutputType.guidSubtype = *(GUID *)(v10 + 120);
      guidCategory = MFT_CATEGORY_VIDEO_ENCODER;
      Instance = MFTEnum(&guidCategory, 0, 0, &pOutputType, 0, &ppclsidMFT, &pcMFTs);
      if ( Instance >= 0 )
      {
        Instance = -2147467259;
        v21 = 0;
        if ( pcMFTs )
        {
          while ( 1 )
          {
            Instance = CoCreateInstance(&ppclsidMFT[v21], 0, 1u, &IID_IMFTransform, (LPVOID *)this + 12);
            if ( Instance >= 0 )
              break;
            if ( ++v21 >= pcMFTs )
              goto LABEL_37;
          }
          Instance = CMFEncoderActivate::CopyPropertiesToEncoder(this);
          if ( Instance >= 0 )
          {
            Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IMFMediaType **))this + 12))(
                         *((_QWORD *)this + 12),
                         &IID_IMFTransform,
                         &v44);
            if ( Instance >= 0 )
            {
              Instance = MFWMEncoderConfigUtil::SetOutputTypeToWMVEncoder(
                           *((MFWMEncoderConfigUtil **)this + 14),
                           v44,
                           v30);
              if ( Instance < 0 )
              {
                v36 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35);
                  CallStackTracing::s_wpInstance = v37;
                  if ( v37
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
                  {
                    v36 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v36 = &qword_1803CE250;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                  }
                }
                if ( *((_BYTE *)v36 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != Instance )
                    CallStackContext::TraceFailure(
                      ThreadRelativeContext,
                      "CMFWMVEncoderActivate::InstantiateEncoder",
                      728,
                      Instance);
                }
                if ( g_wppLevels )
                {
                  v9 = 65;
                  goto LABEL_80;
                }
              }
            }
            else
            {
              v31 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
                CallStackTracing::s_wpInstance = v32;
                if ( v32
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                {
                  v31 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v31 = &qword_1803CE250;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
                }
              }
              if ( *((_BYTE *)v31 + 8) )
              {
                v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                if ( *((_DWORD *)v33 + 499) != Instance )
                  CallStackContext::TraceFailure(v33, "CMFWMVEncoderActivate::InstantiateEncoder", 726, Instance);
              }
              if ( g_wppLevels )
              {
                v9 = 64;
                goto LABEL_80;
              }
            }
          }
          else
          {
            v26 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
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
              if ( *((_DWORD *)v28 + 499) != Instance )
                CallStackContext::TraceFailure(v28, "CMFWMVEncoderActivate::InstantiateEncoder", 724, Instance);
            }
            if ( g_wppLevels )
            {
              v9 = 63;
              goto LABEL_80;
            }
          }
        }
        else
        {
LABEL_37:
          v22 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
            CallStackTracing::s_wpInstance = v23;
            if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
            {
              v22 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v22 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
            if ( *((_DWORD *)v39 + 499) != Instance )
              CallStackContext::TraceFailure(v39, "CMFWMVEncoderActivate::InstantiateEncoder", 721, Instance);
          }
          if ( g_wppLevels )
          {
            v9 = 62;
            goto LABEL_80;
          }
        }
      }
      else
      {
        v18 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16, v17);
          CallStackTracing::s_wpInstance = v19;
          if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
          {
            v18 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v18 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v18 + 8) )
        {
          v20 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v18);
          if ( *((_DWORD *)v20 + 499) != Instance )
            CallStackContext::TraceFailure(v20, "CMFWMVEncoderActivate::InstantiateEncoder", 702, Instance);
        }
        if ( g_wppLevels )
        {
          v9 = 61;
          goto LABEL_80;
        }
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      Instance = -1072875852;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12);
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
        if ( *((_DWORD *)v15 + 499) != -1072875852 )
          CallStackContext::TraceFailure(v15, "CMFWMVEncoderActivate::InstantiateEncoder", 692, -1072875852);
      }
      if ( g_wppLevels )
      {
        v9 = 60;
        goto LABEL_80;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3, v5);
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
      if ( *((_DWORD *)v8 + 499) != Instance )
        CallStackContext::TraceFailure(v8, "CMFWMVEncoderActivate::InstantiateEncoder", 690, Instance);
    }
    if ( g_wppLevels )
    {
      v9 = 59;
LABEL_80:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_75d26da5eb2831ce3652601259e1a0b4_Traceguids,
        this,
        Instance);
    }
  }
  if ( ppclsidMFT )
  {
    CoTaskMemFree(ppclsidMFT);
    ppclsidMFT = 0;
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v44);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v45);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v41);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18027c100  mov     [rsp-8+arg_8], rbx
0x18027c105  mov     [rsp-8+arg_10], rsi
0x18027c10a  push    rbp
0x18027c10b  push    rdi
0x18027c10c  push    r12
0x18027c10e  push    r14
0x18027c110  push    r15
0x18027c112  lea     rbp, [rsp-37h]
0x18027c117  sub     rsp, 0A0h
0x18027c11e  mov     rax, cs:__security_cookie
0x18027c125  xor     rax, rsp
0x18027c128  mov     [rbp+57h+var_30], rax
0x18027c12c  mov     rdi, rcx
0x18027c12f  lea     r12, aCmfwmvencodera_0; "CMFWMVEncoderActivate::InstantiateEncod"...
0x18027c136  mov     rdx, r12; char *
0x18027c139  lea     rcx, [rbp+57h+var_80]; this
0x18027c13d  mov     r8d, 2A8h; int
0x18027c143  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18027c148  mov     rcx, [rdi+70h]
0x18027c14c  lea     r8, [rbp+57h+var_68]
0x18027c150  xor     r15d, r15d
0x18027c153  lea     rdx, IID_IMFVideoMediaType
0x18027c15a  xorps   xmm0, xmm0
0x18027c15d  mov     [rbp+57h+var_68], r15
0x18027c161  movups  xmmword ptr [rbp+57h+pOutputType.guidMajorType.Data1], xmm0
0x18027c165  mov     [rbp+57h+var_78], r15
0x18027c169  movups  xmmword ptr [rbp+57h+pOutputType.guidSubtype.Data1], xmm0
0x18027c16d  mov     [rbp+57h+var_7C], r15d
0x18027c171  mov     [rbp+57h+var_70], r15
0x18027c175  mov     rax, [rcx]
0x18027c178  mov     rax, [rax]
0x18027c17b  call    cs:__guard_dispatch_icall_fptr
0x18027c181  mov     ebx, eax
0x18027c183  test    eax, eax
0x18027c185  jns     loc_18027C21D
0x18027c18b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c192  test    rcx, rcx
0x18027c195  jnz     short loc_18027C1DF
0x18027c197  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c19e  nop     dword ptr [rax+rax+00h]
0x18027c1a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c1aa  mov     rcx, rax
0x18027c1ad  test    rax, rax
0x18027c1b0  jz      short loc_18027C1D1
0x18027c1b2  mov     rax, [rax]
0x18027c1b5  mov     edx, 7F0h
0x18027c1ba  mov     rax, [rax+8]
0x18027c1be  call    cs:__guard_dispatch_icall_fptr
0x18027c1c4  test    eax, eax
0x18027c1c6  jz      short loc_18027C1D1
0x18027c1c8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c1cf  jmp     short loc_18027C1DF
0x18027c1d1  lea     rcx, qword_1803CE250; this
0x18027c1d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c1df  cmp     [rcx+8], r15b
0x18027c1e3  jz      short loc_18027C206
0x18027c1e5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c1ea  cmp     [rax+7CCh], ebx
0x18027c1f0  jz      short loc_18027C206
0x18027c1f2  mov     r9d, ebx; int
0x18027c1f5  mov     r8d, 2B2h; int
0x18027c1fb  mov     rdx, r12; char *
0x18027c1fe  mov     rcx, rax; this
0x18027c201  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027c206  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027c20d  jb      loc_18027C6B7
0x18027c213  mov     edx, 3Bh ; ';'
0x18027c218  jmp     loc_18027C699
0x18027c21d  mov     rcx, [rbp+57h+var_68]
0x18027c221  mov     rax, [rcx]
0x18027c224  mov     rax, [rax+130h]
0x18027c22b  call    cs:__guard_dispatch_icall_fptr
0x18027c231  test    rax, rax
0x18027c234  jnz     loc_18027C2D1
0x18027c23a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c241  mov     ebx, 0C00D36B4h
0x18027c246  test    rcx, rcx
0x18027c249  jnz     short loc_18027C293
0x18027c24b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c252  nop     dword ptr [rax+rax+00h]
0x18027c257  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c25e  mov     rcx, rax
0x18027c261  test    rax, rax
0x18027c264  jz      short loc_18027C285
0x18027c266  mov     rax, [rax]
0x18027c269  mov     edx, 7F0h
0x18027c26e  mov     rax, [rax+8]
0x18027c272  call    cs:__guard_dispatch_icall_fptr
0x18027c278  test    eax, eax
0x18027c27a  jz      short loc_18027C285
0x18027c27c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c283  jmp     short loc_18027C293
0x18027c285  lea     rcx, qword_1803CE250; this
0x18027c28c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c293  cmp     [rcx+8], r15b
0x18027c297  jz      short loc_18027C2BA
0x18027c299  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c29e  cmp     [rax+7CCh], ebx
0x18027c2a4  jz      short loc_18027C2BA
0x18027c2a6  mov     r9d, ebx; int
0x18027c2a9  mov     r8d, 2B4h; int
0x18027c2af  mov     rdx, r12; char *
0x18027c2b2  mov     rcx, rax; this
0x18027c2b5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027c2ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027c2c1  jb      loc_18027C6B7
0x18027c2c7  mov     edx, 3Ch ; '<'
0x18027c2cc  jmp     loc_18027C699
0x18027c2d1  movups  xmm0, xmmword ptr cs:MEDIATYPE_Video.Data1
0x18027c2d8  lea     r9, [rbp+57h+pOutputType]; pOutputType
0x18027c2dc  xor     r8d, r8d; pInputType
0x18027c2df  movups  xmm1, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x18027c2e6  xor     edx, edx; Flags
0x18027c2e8  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x18027c2ec  movdqu  xmmword ptr [rbp+57h+pOutputType.guidMajorType.Data1], xmm0
0x18027c2f1  movups  xmm0, xmmword ptr [rax+78h]
0x18027c2f5  lea     rax, [rbp+57h+var_7C]
0x18027c2f9  mov     [rsp+0C0h+pcMFTs], rax; pcMFTs
0x18027c2fe  lea     rax, [rbp+57h+var_78]
0x18027c302  mov     [rsp+0C0h+ppclsidMFT], rax; ppclsidMFT
0x18027c307  mov     [rsp+0C0h+pAttributes], r15; pAttributes
0x18027c30c  movdqu  xmmword ptr [rbp+57h+pOutputType.guidSubtype.Data1], xmm0
0x18027c311  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm1
0x18027c316  call    cs:__imp_MFTEnum
0x18027c31d  nop     dword ptr [rax+rax+00h]
0x18027c322  mov     ebx, eax
0x18027c324  test    eax, eax
0x18027c326  jns     loc_18027C3BE
0x18027c32c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c333  test    rcx, rcx
0x18027c336  jnz     short loc_18027C380
0x18027c338  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c33f  nop     dword ptr [rax+rax+00h]
0x18027c344  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c34b  mov     rcx, rax
0x18027c34e  test    rax, rax
0x18027c351  jz      short loc_18027C372
0x18027c353  mov     rax, [rax]
0x18027c356  mov     edx, 7F0h
0x18027c35b  mov     rax, [rax+8]
0x18027c35f  call    cs:__guard_dispatch_icall_fptr
0x18027c365  test    eax, eax
0x18027c367  jz      short loc_18027C372
0x18027c369  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c370  jmp     short loc_18027C380
0x18027c372  lea     rcx, qword_1803CE250; this
0x18027c379  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c380  cmp     [rcx+8], r15b
0x18027c384  jz      short loc_18027C3A7
0x18027c386  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c38b  cmp     [rax+7CCh], ebx
0x18027c391  jz      short loc_18027C3A7
0x18027c393  mov     r9d, ebx; int
0x18027c396  mov     r8d, 2BEh; int
0x18027c39c  mov     rdx, r12; char *
0x18027c39f  mov     rcx, rax; this
0x18027c3a2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027c3a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027c3ae  jb      loc_18027C6B7
0x18027c3b4  mov     edx, 3Dh ; '='
0x18027c3b9  jmp     loc_18027C699
0x18027c3be  mov     ebx, 80004005h
0x18027c3c3  mov     esi, r15d
0x18027c3c6  cmp     [rbp+57h+var_7C], r15d
0x18027c3ca  jbe     short loc_18027C405
0x18027c3cc  lea     r14, [rdi+60h]
0x18027c3d0  xor     edx, edx; pUnkOuter
0x18027c3d2  mov     ecx, esi
0x18027c3d4  shl     rcx, 4
0x18027c3d8  lea     r9, IID_IMFTransform; riid
0x18027c3df  add     rcx, [rbp+57h+var_78]; rclsid
0x18027c3e3  mov     [rsp+0C0h+pAttributes], r14; ppv
0x18027c3e8  lea     r8d, [rdx+1]; dwClsContext
0x18027c3ec  call    cs:__imp_CoCreateInstance
0x18027c3f3  nop     dword ptr [rax+rax+00h]
0x18027c3f8  mov     ebx, eax
0x18027c3fa  test    eax, eax
0x18027c3fc  jns     short loc_18027C45A
0x18027c3fe  inc     esi
0x18027c400  cmp     esi, [rbp+57h+var_7C]
0x18027c403  jb      short loc_18027C3D0
0x18027c405  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c40c  test    rcx, rcx
0x18027c40f  jnz     loc_18027C664
0x18027c415  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c41c  nop     dword ptr [rax+rax+00h]
0x18027c421  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c428  mov     rcx, rax
0x18027c42b  test    rax, rax
0x18027c42e  jz      loc_18027C656
0x18027c434  mov     rax, [rax]
0x18027c437  mov     edx, 7F0h
0x18027c43c  mov     rax, [rax+8]
0x18027c440  call    cs:__guard_dispatch_icall_fptr
0x18027c446  test    eax, eax
0x18027c448  jz      loc_18027C656
0x18027c44e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c455  jmp     loc_18027C664
0x18027c45a  mov     rcx, rdi; this
0x18027c45d  call    ?CopyPropertiesToEncoder@CMFEncoderActivate@@IEAAJXZ; CMFEncoderActivate::CopyPropertiesToEncoder(void)
0x18027c462  mov     ebx, eax
0x18027c464  test    eax, eax
0x18027c466  jns     loc_18027C4FE
0x18027c46c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c473  test    rcx, rcx
0x18027c476  jnz     short loc_18027C4C0
0x18027c478  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c47f  nop     dword ptr [rax+rax+00h]
0x18027c484  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c48b  mov     rcx, rax
0x18027c48e  test    rax, rax
0x18027c491  jz      short loc_18027C4B2
0x18027c493  mov     rax, [rax]
0x18027c496  mov     edx, 7F0h
0x18027c49b  mov     rax, [rax+8]
0x18027c49f  call    cs:__guard_dispatch_icall_fptr
0x18027c4a5  test    eax, eax
0x18027c4a7  jz      short loc_18027C4B2
0x18027c4a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c4b0  jmp     short loc_18027C4C0
0x18027c4b2  lea     rcx, qword_1803CE250; this
0x18027c4b9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c4c0  cmp     [rcx+8], r15b
0x18027c4c4  jz      short loc_18027C4E7
0x18027c4c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c4cb  cmp     [rax+7CCh], ebx
0x18027c4d1  jz      short loc_18027C4E7
0x18027c4d3  mov     r9d, ebx; int
0x18027c4d6  mov     r8d, 2D4h; int
0x18027c4dc  mov     rdx, r12; char *
0x18027c4df  mov     rcx, rax; this
0x18027c4e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027c4e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027c4ee  jb      loc_18027C6B7
0x18027c4f4  mov     edx, 3Fh ; '?'
0x18027c4f9  jmp     loc_18027C699
0x18027c4fe  mov     rcx, [r14]
0x18027c501  lea     r8, [rbp+57h+var_70]
0x18027c505  lea     rdx, IID_IMFTransform
0x18027c50c  mov     rax, [rcx]
0x18027c50f  mov     rax, [rax]
0x18027c512  call    cs:__guard_dispatch_icall_fptr
0x18027c518  mov     ebx, eax
0x18027c51a  test    eax, eax
0x18027c51c  jns     loc_18027C5B4
0x18027c522  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c529  test    rcx, rcx
0x18027c52c  jnz     short loc_18027C576
0x18027c52e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c535  nop     dword ptr [rax+rax+00h]
0x18027c53a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c541  mov     rcx, rax
0x18027c544  test    rax, rax
0x18027c547  jz      short loc_18027C568
0x18027c549  mov     rax, [rax]
0x18027c54c  mov     edx, 7F0h
0x18027c551  mov     rax, [rax+8]
0x18027c555  call    cs:__guard_dispatch_icall_fptr
0x18027c55b  test    eax, eax
0x18027c55d  jz      short loc_18027C568
0x18027c55f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c566  jmp     short loc_18027C576
0x18027c568  lea     rcx, qword_1803CE250; this
0x18027c56f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c576  cmp     [rcx+8], r15b
0x18027c57a  jz      short loc_18027C59D
0x18027c57c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c581  cmp     [rax+7CCh], ebx
0x18027c587  jz      short loc_18027C59D
0x18027c589  mov     r9d, ebx; int
0x18027c58c  mov     r8d, 2D6h; int
0x18027c592  mov     rdx, r12; char *
0x18027c595  mov     rcx, rax; this
0x18027c598  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027c59d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027c5a4  jb      loc_18027C6B7
0x18027c5aa  mov     edx, 40h ; '@'
0x18027c5af  jmp     loc_18027C699
0x18027c5b4  mov     rdx, [rbp+57h+var_70]; struct IMFMediaType *
0x18027c5b8  mov     rcx, [rdi+70h]; this
0x18027c5bc  call    ?SetOutputTypeToWMVEncoder@MFWMEncoderConfigUtil@@YAJPEAUIMFMediaType@@PEAUIMFTransform@@@Z; MFWMEncoderConfigUtil::SetOutputTypeToWMVEncoder(IMFMediaType *,IMFTransform *)
0x18027c5c1  mov     ebx, eax
0x18027c5c3  test    eax, eax
0x18027c5c5  jns     loc_18027C6B7
0x18027c5cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c5d2  test    rcx, rcx
0x18027c5d5  jnz     short loc_18027C61F
0x18027c5d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c5de  nop     dword ptr [rax+rax+00h]
0x18027c5e3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c5ea  mov     rcx, rax
0x18027c5ed  test    rax, rax
0x18027c5f0  jz      short loc_18027C611
0x18027c5f2  mov     rax, [rax]
0x18027c5f5  mov     edx, 7F0h
0x18027c5fa  mov     rax, [rax+8]
0x18027c5fe  call    cs:__guard_dispatch_icall_fptr
0x18027c604  test    eax, eax
0x18027c606  jz      short loc_18027C611
0x18027c608  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
  ... truncated ...
```
