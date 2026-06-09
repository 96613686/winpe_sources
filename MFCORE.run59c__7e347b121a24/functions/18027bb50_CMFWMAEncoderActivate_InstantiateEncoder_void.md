# CMFWMAEncoderActivate::InstantiateEncoder(void)

- ea: `0x18027bb50`
- end: `0x18027c0fa`
- name: `?InstantiateEncoder@CMFWMAEncoderActivate@@MEAAJXZ`
- size: `1450`
- prototype: `__int64 __fastcall(CMFWMAEncoderActivate *__hidden this)`
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
- `0x180216540`
- `0x180258480`
- `0x18027b06c`
- `0x18027bb50`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027c0a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18027c0a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18027bd32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18027bd32`
- `MFPlat!MFTEnum` at `0x18027bc5c`
- `MFPlat!MFTEnum` at `0x18027bc5c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bc7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bd5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bdbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027be74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bf1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c000`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bc7e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bd5b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bdbe`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027be74`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027bf1d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18027c000`

## pseudocode

```c
__int64 __fastcall CMFWMAEncoderActivate::InstantiateEncoder(CMFWMAEncoderActivate *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rcx
  GUID v7; // xmm0
  __int64 v8; // rdx
  HRESULT Instance; // ebx
  __int64 v10; // r8
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  int v15; // esi
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  struct IMFTransform *v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  __int64 *v34; // rcx
  CallStackTracing *v35; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v38[4]; // [rsp+40h] [rbp-29h] BYREF
  UINT32 pcMFTs; // [rsp+44h] [rbp-25h] BYREF
  CLSID *ppclsidMFT; // [rsp+48h] [rbp-21h] BYREF
  GUID *v41; // [rsp+50h] [rbp-19h] BYREF
  struct IMFMediaType *v42; // [rsp+58h] [rbp-11h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-9h] BYREF
  __int64 v44; // [rsp+70h] [rbp+7h] BYREF
  MFT_REGISTER_TYPE_INFO pOutputType; // [rsp+78h] [rbp+Fh] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v38, "CMFWMAEncoderActivate::InstantiateEncoder", 791);
  v2 = (__int64 *)*((_QWORD *)this + 14);
  v42 = 0;
  memset(&pOutputType, 0, sizeof(pOutputType));
  v41 = 0;
  pcMFTs = 0;
  ppclsidMFT = 0;
  v3 = *v2;
  v44 = 0;
  guidCategory = AM_MEDIA_TYPE_REPRESENTATION;
  if ( (*(int (__fastcall **)(__int64 *, GUID *, GUID **))(v3 + 288))(v2, &guidCategory, &v41) < 0 )
  {
    v34 = (__int64 *)CallStackTracing::s_wpInstance;
    Instance = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4, v5);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFWMAEncoderActivate::InstantiateEncoder",
          811,
          -2147418113);
    }
    if ( g_wppLevels )
    {
      v14 = 69;
      goto LABEL_69;
    }
  }
  else
  {
    v6 = *((_QWORD *)this + 14);
    v7 = v41[1];
    guidCategory = AM_MEDIA_TYPE_REPRESENTATION;
    pOutputType.guidSubtype = v7;
    (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v6 + 296LL))(v6, &guidCategory);
    v41 = 0;
    pOutputType.guidMajorType = MEDIATYPE_Audio;
    guidCategory = MFT_CATEGORY_AUDIO_ENCODER;
    Instance = MFTEnum(&guidCategory, 0, 0, &pOutputType, 0, &ppclsidMFT, &pcMFTs);
    if ( Instance >= 0 )
    {
      Instance = -2147467259;
      v15 = 0;
      if ( pcMFTs )
      {
        while ( 1 )
        {
          Instance = CoCreateInstance(&ppclsidMFT[v15], 0, 1u, &IID_IMFTransform, (LPVOID *)this + 12);
          if ( Instance >= 0 )
            break;
          if ( ++v15 >= pcMFTs )
            goto LABEL_16;
        }
        Instance = CMFEncoderActivate::CopyPropertiesToEncoder(this);
        if ( Instance >= 0 )
        {
          Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IMFMediaType **))this + 12))(
                       *((_QWORD *)this + 12),
                       &IID_IMFTransform,
                       &v42);
          if ( Instance >= 0 )
          {
            Instance = MFWMEncoderConfigUtil::SetOutputTypeWithAudioCodecDataToWMAEncoder(
                         *((MFWMEncoderConfigUtil **)this + 14),
                         v42,
                         v24);
            if ( Instance < 0 )
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
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
              if ( *((_BYTE *)v30 + 8) )
              {
                v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
                if ( *((_DWORD *)v32 + 499) != Instance )
                  CallStackContext::TraceFailure(v32, "CMFWMAEncoderActivate::InstantiateEncoder", 847, Instance);
              }
              if ( g_wppLevels )
              {
                v14 = 74;
                goto LABEL_69;
              }
            }
          }
          else
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
              CallStackTracing::s_wpInstance = v26;
              if ( v26
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
              {
                v25 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v25 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v25 + 8) )
            {
              v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
              if ( *((_DWORD *)v27 + 499) != Instance )
                CallStackContext::TraceFailure(v27, "CMFWMAEncoderActivate::InstantiateEncoder", 845, Instance);
            }
            if ( g_wppLevels )
            {
              v14 = 73;
              goto LABEL_69;
            }
          }
        }
        else
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
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
            if ( *((_DWORD *)v22 + 499) != Instance )
              CallStackContext::TraceFailure(v22, "CMFWMAEncoderActivate::InstantiateEncoder", 843, Instance);
          }
          if ( g_wppLevels )
          {
            v14 = 72;
            goto LABEL_69;
          }
        }
      }
      else
      {
LABEL_16:
        v16 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10);
          CallStackTracing::s_wpInstance = v17;
          if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
          {
            v16 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v16 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v16 + 8) )
        {
          v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
          if ( *((_DWORD *)v33 + 499) != Instance )
            CallStackContext::TraceFailure(v33, "CMFWMAEncoderActivate::InstantiateEncoder", 840, Instance);
        }
        if ( g_wppLevels )
        {
          v14 = 71;
          goto LABEL_69;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v10);
        CallStackTracing::s_wpInstance = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != Instance )
          CallStackContext::TraceFailure(v13, "CMFWMAEncoderActivate::InstantiateEncoder", 822, Instance);
      }
      if ( g_wppLevels )
      {
        v14 = 70;
LABEL_69:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          &WPP_75d26da5eb2831ce3652601259e1a0b4_Traceguids,
          this,
          Instance);
      }
    }
  }
  if ( ppclsidMFT )
  {
    CoTaskMemFree(ppclsidMFT);
    ppclsidMFT = 0;
  }
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v44);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v42);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v38);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18027bb50  mov     [rsp-8+arg_8], rbx
0x18027bb55  mov     [rsp-8+arg_10], rsi
0x18027bb5a  push    rbp
0x18027bb5b  push    rdi
0x18027bb5c  push    r12
0x18027bb5e  push    r14
0x18027bb60  push    r15
0x18027bb62  lea     rbp, [rsp-37h]
0x18027bb67  sub     rsp, 0A0h
0x18027bb6e  mov     rax, cs:__security_cookie
0x18027bb75  xor     rax, rsp
0x18027bb78  mov     [rbp+57h+var_28], rax
0x18027bb7c  mov     rdi, rcx
0x18027bb7f  lea     r12, aCmfwmaencodera; "CMFWMAEncoderActivate::InstantiateEncod"...
0x18027bb86  mov     rdx, r12; char *
0x18027bb89  lea     rcx, [rbp+57h+var_80]; this
0x18027bb8d  mov     r8d, 317h; int
0x18027bb93  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18027bb98  mov     rcx, [rdi+70h]
0x18027bb9c  lea     r8, [rbp+57h+var_70]
0x18027bba0  xor     r15d, r15d
0x18027bba3  lea     rdx, [rbp+57h+guidCategory]
0x18027bba7  xorps   xmm0, xmm0
0x18027bbaa  mov     [rbp+57h+var_68], r15
0x18027bbae  movups  xmmword ptr [rbp+57h+pOutputType.guidMajorType.Data1], xmm0
0x18027bbb2  mov     [rbp+57h+var_70], r15
0x18027bbb6  movups  xmmword ptr [rbp+57h+pOutputType.guidSubtype.Data1], xmm0
0x18027bbba  mov     [rbp+57h+var_7C], r15d
0x18027bbbe  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x18027bbc5  mov     [rbp+57h+var_78], r15
0x18027bbc9  mov     rax, [rcx]
0x18027bbcc  mov     [rbp+57h+var_50], r15
0x18027bbd0  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x18027bbd5  mov     rax, [rax+120h]
0x18027bbdc  call    cs:__guard_dispatch_icall_fptr
0x18027bbe2  test    eax, eax
0x18027bbe4  js      loc_18027BFEF
0x18027bbea  mov     r8, [rbp+57h+var_70]
0x18027bbee  lea     rdx, [rbp+57h+guidCategory]
0x18027bbf2  mov     rcx, [rdi+70h]
0x18027bbf6  movups  xmm1, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x18027bbfd  movups  xmm0, xmmword ptr [r8+10h]
0x18027bc02  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm1
0x18027bc07  movdqu  xmmword ptr [rbp+57h+pOutputType.guidSubtype.Data1], xmm0
0x18027bc0c  mov     rax, [rcx]
0x18027bc0f  mov     rax, [rax+128h]
0x18027bc16  call    cs:__guard_dispatch_icall_fptr
0x18027bc1c  movups  xmm0, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x18027bc23  lea     rax, [rbp+57h+var_7C]
0x18027bc27  xor     r8d, r8d; pInputType
0x18027bc2a  movups  xmm1, xmmword ptr cs:MFT_CATEGORY_AUDIO_ENCODER.Data1
0x18027bc31  mov     [rsp+0C0h+pcMFTs], rax; pcMFTs
0x18027bc36  lea     r9, [rbp+57h+pOutputType]; pOutputType
0x18027bc3a  lea     rax, [rbp+57h+var_78]
0x18027bc3e  mov     [rbp+57h+var_70], r15
0x18027bc42  mov     [rsp+0C0h+ppclsidMFT], rax; ppclsidMFT
0x18027bc47  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x18027bc4b  xor     edx, edx; Flags
0x18027bc4d  mov     [rsp+0C0h+pAttributes], r15; pAttributes
0x18027bc52  movdqu  xmmword ptr [rbp+57h+pOutputType.guidMajorType.Data1], xmm0
0x18027bc57  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm1
0x18027bc5c  call    cs:__imp_MFTEnum
0x18027bc63  nop     dword ptr [rax+rax+00h]
0x18027bc68  mov     ebx, eax
0x18027bc6a  test    eax, eax
0x18027bc6c  jns     loc_18027BD04
0x18027bc72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bc79  test    rcx, rcx
0x18027bc7c  jnz     short loc_18027BCC6
0x18027bc7e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027bc85  nop     dword ptr [rax+rax+00h]
0x18027bc8a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bc91  mov     rcx, rax
0x18027bc94  test    rax, rax
0x18027bc97  jz      short loc_18027BCB8
0x18027bc99  mov     rax, [rax]
0x18027bc9c  mov     edx, 7F0h
0x18027bca1  mov     rax, [rax+8]
0x18027bca5  call    cs:__guard_dispatch_icall_fptr
0x18027bcab  test    eax, eax
0x18027bcad  jz      short loc_18027BCB8
0x18027bcaf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bcb6  jmp     short loc_18027BCC6
0x18027bcb8  lea     rcx, qword_1803CE250; this
0x18027bcbf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bcc6  cmp     [rcx+8], r15b
0x18027bcca  jz      short loc_18027BCED
0x18027bccc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027bcd1  cmp     [rax+7CCh], ebx
0x18027bcd7  jz      short loc_18027BCED
0x18027bcd9  mov     r9d, ebx; int
0x18027bcdc  mov     r8d, 336h; int
0x18027bce2  mov     rdx, r12; char *
0x18027bce5  mov     rcx, rax; this
0x18027bce8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027bced  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027bcf4  jb      loc_18027C09B
0x18027bcfa  mov     edx, 46h ; 'F'
0x18027bcff  jmp     loc_18027C07D
0x18027bd04  mov     ebx, 80004005h
0x18027bd09  mov     esi, r15d
0x18027bd0c  cmp     [rbp+57h+var_7C], r15d
0x18027bd10  jbe     short loc_18027BD4B
0x18027bd12  lea     r14, [rdi+60h]
0x18027bd16  xor     edx, edx; pUnkOuter
0x18027bd18  mov     ecx, esi
0x18027bd1a  shl     rcx, 4
0x18027bd1e  lea     r9, IID_IMFTransform; riid
0x18027bd25  add     rcx, [rbp+57h+var_78]; rclsid
0x18027bd29  mov     [rsp+0C0h+pAttributes], r14; ppv
0x18027bd2e  lea     r8d, [rdx+1]; dwClsContext
0x18027bd32  call    cs:__imp_CoCreateInstance
0x18027bd39  nop     dword ptr [rax+rax+00h]
0x18027bd3e  mov     ebx, eax
0x18027bd40  test    eax, eax
0x18027bd42  jns     short loc_18027BDA0
0x18027bd44  inc     esi
0x18027bd46  cmp     esi, [rbp+57h+var_7C]
0x18027bd49  jb      short loc_18027BD16
0x18027bd4b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bd52  test    rcx, rcx
0x18027bd55  jnz     loc_18027BFB1
0x18027bd5b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027bd62  nop     dword ptr [rax+rax+00h]
0x18027bd67  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bd6e  mov     rcx, rax
0x18027bd71  test    rax, rax
0x18027bd74  jz      loc_18027BFA3
0x18027bd7a  mov     rax, [rax]
0x18027bd7d  mov     edx, 7F0h
0x18027bd82  mov     rax, [rax+8]
0x18027bd86  call    cs:__guard_dispatch_icall_fptr
0x18027bd8c  test    eax, eax
0x18027bd8e  jz      loc_18027BFA3
0x18027bd94  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bd9b  jmp     loc_18027BFB1
0x18027bda0  mov     rcx, rdi; this
0x18027bda3  call    ?CopyPropertiesToEncoder@CMFEncoderActivate@@IEAAJXZ; CMFEncoderActivate::CopyPropertiesToEncoder(void)
0x18027bda8  mov     ebx, eax
0x18027bdaa  test    eax, eax
0x18027bdac  jns     loc_18027BE44
0x18027bdb2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bdb9  test    rcx, rcx
0x18027bdbc  jnz     short loc_18027BE06
0x18027bdbe  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027bdc5  nop     dword ptr [rax+rax+00h]
0x18027bdca  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bdd1  mov     rcx, rax
0x18027bdd4  test    rax, rax
0x18027bdd7  jz      short loc_18027BDF8
0x18027bdd9  mov     rax, [rax]
0x18027bddc  mov     edx, 7F0h
0x18027bde1  mov     rax, [rax+8]
0x18027bde5  call    cs:__guard_dispatch_icall_fptr
0x18027bdeb  test    eax, eax
0x18027bded  jz      short loc_18027BDF8
0x18027bdef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bdf6  jmp     short loc_18027BE06
0x18027bdf8  lea     rcx, qword_1803CE250; this
0x18027bdff  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027be06  cmp     [rcx+8], r15b
0x18027be0a  jz      short loc_18027BE2D
0x18027be0c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027be11  cmp     [rax+7CCh], ebx
0x18027be17  jz      short loc_18027BE2D
0x18027be19  mov     r9d, ebx; int
0x18027be1c  mov     r8d, 34Bh; int
0x18027be22  mov     rdx, r12; char *
0x18027be25  mov     rcx, rax; this
0x18027be28  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027be2d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027be34  jb      loc_18027C09B
0x18027be3a  mov     edx, 48h ; 'H'
0x18027be3f  jmp     loc_18027C07D
0x18027be44  mov     rcx, [r14]
0x18027be47  lea     r8, [rbp+57h+var_68]
0x18027be4b  lea     rdx, IID_IMFTransform
0x18027be52  mov     rax, [rcx]
0x18027be55  mov     rax, [rax]
0x18027be58  call    cs:__guard_dispatch_icall_fptr
0x18027be5e  mov     ebx, eax
0x18027be60  test    eax, eax
0x18027be62  jns     loc_18027BEFA
0x18027be68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027be6f  test    rcx, rcx
0x18027be72  jnz     short loc_18027BEBC
0x18027be74  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027be7b  nop     dword ptr [rax+rax+00h]
0x18027be80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027be87  mov     rcx, rax
0x18027be8a  test    rax, rax
0x18027be8d  jz      short loc_18027BEAE
0x18027be8f  mov     rax, [rax]
0x18027be92  mov     edx, 7F0h
0x18027be97  mov     rax, [rax+8]
0x18027be9b  call    cs:__guard_dispatch_icall_fptr
0x18027bea1  test    eax, eax
0x18027bea3  jz      short loc_18027BEAE
0x18027bea5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027beac  jmp     short loc_18027BEBC
0x18027beae  lea     rcx, qword_1803CE250; this
0x18027beb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bebc  cmp     [rcx+8], r15b
0x18027bec0  jz      short loc_18027BEE3
0x18027bec2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027bec7  cmp     [rax+7CCh], ebx
0x18027becd  jz      short loc_18027BEE3
0x18027becf  mov     r9d, ebx; int
0x18027bed2  mov     r8d, 34Dh; int
0x18027bed8  mov     rdx, r12; char *
0x18027bedb  mov     rcx, rax; this
0x18027bede  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027bee3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027beea  jb      loc_18027C09B
0x18027bef0  mov     edx, 49h ; 'I'
0x18027bef5  jmp     loc_18027C07D
0x18027befa  mov     rdx, [rbp+57h+var_68]; struct IMFMediaType *
0x18027befe  mov     rcx, [rdi+70h]; this
0x18027bf02  call    ?SetOutputTypeWithAudioCodecDataToWMAEncoder@MFWMEncoderConfigUtil@@YAJPEAUIMFMediaType@@PEAUIMFTransform@@@Z; MFWMEncoderConfigUtil::SetOutputTypeWithAudioCodecDataToWMAEncoder(IMFMediaType *,IMFTransform *)
0x18027bf07  mov     ebx, eax
0x18027bf09  test    eax, eax
0x18027bf0b  jns     loc_18027C09B
0x18027bf11  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bf18  test    rcx, rcx
0x18027bf1b  jnz     short loc_18027BF65
0x18027bf1d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027bf24  nop     dword ptr [rax+rax+00h]
0x18027bf29  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bf30  mov     rcx, rax
0x18027bf33  test    rax, rax
0x18027bf36  jz      short loc_18027BF57
0x18027bf38  mov     rax, [rax]
0x18027bf3b  mov     edx, 7F0h
0x18027bf40  mov     rax, [rax+8]
0x18027bf44  call    cs:__guard_dispatch_icall_fptr
0x18027bf4a  test    eax, eax
0x18027bf4c  jz      short loc_18027BF57
0x18027bf4e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bf55  jmp     short loc_18027BF65
0x18027bf57  lea     rcx, qword_1803CE250; this
0x18027bf5e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bf65  cmp     [rcx+8], r15b
0x18027bf69  jz      short loc_18027BF8C
0x18027bf6b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027bf70  cmp     [rax+7CCh], ebx
0x18027bf76  jz      short loc_18027BF8C
0x18027bf78  mov     r9d, ebx; int
0x18027bf7b  mov     r8d, 34Fh; int
0x18027bf81  mov     rdx, r12; char *
0x18027bf84  mov     rcx, rax; this
0x18027bf87  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027bf8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027bf93  jb      loc_18027C09B
0x18027bf99  mov     edx, 4Ah ; 'J'
0x18027bf9e  jmp     loc_18027C07D
0x18027bfa3  lea     rcx, qword_1803CE250; this
0x18027bfaa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bfb1  cmp     [rcx+8], r15b
0x18027bfb5  jz      short loc_18027BFD8
0x18027bfb7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027bfbc  cmp     [rax+7CCh], ebx
0x18027bfc2  jz      short loc_18027BFD8
0x18027bfc4  mov     r9d, ebx; int
0x18027bfc7  mov     r8d, 348h; int
0x18027bfcd  mov     rdx, r12; char *
0x18027bfd0  mov     rcx, rax; this
0x18027bfd3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18027bfd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18027bfdf  jb      loc_18027C09B
0x18027bfe5  mov     edx, 47h ; 'G'
0x18027bfea  jmp     loc_18027C07D
0x18027bfef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027bff6  mov     ebx, 8000FFFFh
0x18027bffb  test    rcx, rcx
0x18027bffe  jnz     short loc_18027C048
0x18027c000  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18027c007  nop     dword ptr [rax+rax+00h]
0x18027c00c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c013  mov     rcx, rax
0x18027c016  test    rax, rax
0x18027c019  jz      short loc_18027C03A
0x18027c01b  mov     rax, [rax]
0x18027c01e  mov     edx, 7F0h
0x18027c023  mov     rax, [rax+8]
0x18027c027  call    cs:__guard_dispatch_icall_fptr
0x18027c02d  test    eax, eax
0x18027c02f  jz      short loc_18027C03A
0x18027c031  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c038  jmp     short loc_18027C048
0x18027c03a  lea     rcx, qword_1803CE250; this
0x18027c041  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18027c048  cmp     [rcx+8], r15b
0x18027c04c  jz      short loc_18027C06F
0x18027c04e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18027c053  cmp     [rax+7CCh], ebx
0x18027c059  jz      short loc_18027C06F
0x18027c05b  mov     r9d, ebx; int
0x18027c05e  mov     r8d, 32Bh; int
0x18027c064  mov     rdx, r12; char *
0x18027c067  mov     rcx, rax; this
  ... truncated ...
```
