# CMFTHelper::ConfigMFTActivate(IMFAttributes *,IMFMediaType *,IMFActivate *)

- ea: `0x1800377fc`
- end: `0x180037e24`
- name: `?ConfigMFTActivate@CMFTHelper@@SAJPEAUIMFAttributes@@PEAUIMFMediaType@@PEAUIMFActivate@@@Z`
- size: `1576`
- prototype: `__int64 __fastcall(struct IMFAttributes *, struct IMFMediaType *, struct IMFActivate *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005290`
- `0x1800430ec`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x180009c5c`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x1800377fc`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037880`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800379fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ab6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037b6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037d36`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037880`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037924`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800379fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037ab6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037b6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037c2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180037d36`

## string_xrefs

- `0x180037818`: `CMFTHelper::ConfigMFTActivate`

## pseudocode

```c
__int64 __fastcall CMFTHelper::ConfigMFTActivate(
        struct IMFAttributes *a1,
        struct IMFMediaType *a2,
        struct IMFActivate *a3)
{
  struct IMFActivateVtbl *lpVtbl; // rax
  struct IMFAttributes *v7; // rdi
  HRESULT (__stdcall *QueryInterface)(IMFActivate *, const IID *const, void **); // rax
  __int64 v9; // rdx
  int MFTActivateCodecAPIAttributes; // ebx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  struct IMFMediaTypeVtbl *v27; // rax
  __int64 v28; // rdx
  __int64 *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  __int64 v32; // rdx
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  __int64 *v37; // rcx
  CallStackTracing *v38; // rax
  struct CallStackContext *v39; // rax
  int v41; // [rsp+30h] [rbp-20h] BYREF
  __int64 v42; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v43[2]; // [rsp+40h] [rbp-10h] BYREF
  struct IMFAttributes *v44; // [rsp+90h] [rbp+40h] BYREF
  int v45; // [rsp+98h] [rbp+48h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v44, "CMFTHelper::ConfigMFTActivate", 83);
  lpVtbl = a3->lpVtbl;
  v42 = 0;
  v7 = 0;
  v44 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v45 = 0;
  v41 = 0;
  v43[0] = 0;
  MFTActivateCodecAPIAttributes = ((__int64 (__fastcall *)(struct IMFActivate *, GUID *, __int64 *))QueryInterface)(
                                    a3,
                                    &IID_IMFAttributes,
                                    &v42);
  if ( MFTActivateCodecAPIAttributes < 0 )
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MFTActivateCodecAPIAttributes )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CMFTHelper::ConfigMFTActivate",
          92,
          MFTActivateCodecAPIAttributes);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v14 = 15;
LABEL_86:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids,
        0,
        MFTActivateCodecAPIAttributes);
      goto LABEL_87;
    }
    goto LABEL_87;
  }
  MFTActivateCodecAPIAttributes = CMFTHelper::GetMFTActivateCodecAPIAttributes(a1, a2, &v44);
  if ( MFTActivateCodecAPIAttributes < 0 )
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
      if ( *((_DWORD *)v18 + 499) != MFTActivateCodecAPIAttributes )
        CallStackContext::TraceFailure(v18, "CMFTHelper::ConfigMFTActivate", 97, MFTActivateCodecAPIAttributes);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids,
        0,
        MFTActivateCodecAPIAttributes);
    v7 = v44;
    goto LABEL_87;
  }
  v7 = v44;
  if ( !v44 )
  {
LABEL_48:
    if ( a2 )
    {
      v27 = a2->lpVtbl;
      v45 = 0;
      MFTActivateCodecAPIAttributes = ((__int64 (__fastcall *)(struct IMFMediaType *, int *))v27->GetCount)(a2, &v45);
      if ( MFTActivateCodecAPIAttributes < 0 )
      {
        v29 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28);
          CallStackTracing::s_wpInstance = v30;
          if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
          {
            v29 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v29 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v29);
          if ( *((_DWORD *)v31 + 499) != MFTActivateCodecAPIAttributes )
            CallStackContext::TraceFailure(v31, "CMFTHelper::ConfigMFTActivate", 114, MFTActivateCodecAPIAttributes);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 19;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( v45 )
      {
        MFTActivateCodecAPIAttributes = (*(__int64 (__fastcall **)(__int64, const GUID *, struct IMFMediaType *))(*(_QWORD *)v42 + 216LL))(
                                          v42,
                                          &MFT_PREFERRED_OUTPUTTYPE_Attribute,
                                          a2);
        if ( MFTActivateCodecAPIAttributes < 0 )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( *((_DWORD *)v35 + 499) != MFTActivateCodecAPIAttributes )
              CallStackContext::TraceFailure(v35, "CMFTHelper::ConfigMFTActivate", 117, MFTActivateCodecAPIAttributes);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v14 = 20;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
      }
    }
    if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *, _QWORD *))a1->lpVtbl->GetUnknown)(
           a1,
           &MFT_FIELDOFUSE_UNLOCK_Attribute,
           &IID_IUnknown,
           v43) >= 0
      && !(*(unsigned int (__fastcall **)(__int64, const GUID *, int *))(*(_QWORD *)v42 + 56LL))(
            v42,
            &MF_TRANSFORM_FLAGS_Attribute,
            &v41)
      && (v41 & 8) != 0 )
    {
      MFTActivateCodecAPIAttributes = (*(__int64 (__fastcall **)(__int64, const GUID *, _QWORD))(*(_QWORD *)v42 + 216LL))(
                                        v42,
                                        &MFT_FIELDOFUSE_UNLOCK_Attribute,
                                        v43[0]);
      if ( MFTActivateCodecAPIAttributes < 0 )
      {
        v37 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v36);
          CallStackTracing::s_wpInstance = v38;
          if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
          {
            v37 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v37 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v39 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
          if ( *((_DWORD *)v39 + 499) != MFTActivateCodecAPIAttributes )
            CallStackContext::TraceFailure(v39, "CMFTHelper::ConfigMFTActivate", 128, MFTActivateCodecAPIAttributes);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 21;
          goto LABEL_86;
        }
      }
    }
    goto LABEL_87;
  }
  MFTActivateCodecAPIAttributes = ((__int64 (__fastcall *)(struct IMFAttributes *, int *))v44->lpVtbl->GetCount)(
                                    v44,
                                    &v45);
  if ( MFTActivateCodecAPIAttributes >= 0 )
  {
    if ( v45 )
    {
      MFTActivateCodecAPIAttributes = (*(__int64 (__fastcall **)(__int64, const GUID *, struct IMFAttributes *))(*(_QWORD *)v42 + 216LL))(
                                        v42,
                                        &MFT_PREFERRED_ENCODER_PROFILE,
                                        v7);
      if ( MFTActivateCodecAPIAttributes < 0 )
      {
        v24 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)v26 + 499) != MFTActivateCodecAPIAttributes )
            CallStackContext::TraceFailure(v26, "CMFTHelper::ConfigMFTActivate", 104, MFTActivateCodecAPIAttributes);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v14 = 18;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
    }
    goto LABEL_48;
  }
  v20 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
    CallStackTracing::s_wpInstance = v21;
    if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v20 = &qword_180069A90;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
    }
  }
  if ( *((_BYTE *)v20 + 8) )
  {
    v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
    if ( *((_DWORD *)v22 + 499) != MFTActivateCodecAPIAttributes )
      CallStackContext::TraceFailure(v22, "CMFTHelper::ConfigMFTActivate", 100, MFTActivateCodecAPIAttributes);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v14 = 17;
    goto LABEL_86;
  }
LABEL_87:
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v7 )
    ((void (__fastcall *)(struct IMFAttributes *))v7->lpVtbl->Release)(v7);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(v43);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v44);
  return (unsigned int)MFTActivateCodecAPIAttributes;
}

```

## disassembly

```asm
0x1800377fc  mov     [rsp-28h+arg_0], rbx
0x180037801  mov     [rsp-28h+arg_8], rsi
0x180037806  push    rbp
0x180037807  push    rdi
0x180037808  push    r12
0x18003780a  push    r14
0x18003780c  push    r15
0x18003780e  mov     rbp, rsp
0x180037811  sub     rsp, 50h
0x180037815  mov     rbx, r8
0x180037818  lea     r12, aCmfthelperConf; "CMFTHelper::ConfigMFTActivate"
0x18003781f  mov     rsi, rdx
0x180037822  mov     r14, rcx
0x180037825  mov     rdx, r12; char *
0x180037828  lea     rcx, [rbp+arg_10]; this
0x18003782c  mov     r8d, 53h ; 'S'; int
0x180037832  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180037837  mov     rax, [rbx]
0x18003783a  lea     r8, [rbp+var_18]
0x18003783e  xor     r15d, r15d
0x180037841  lea     rdx, IID_IMFAttributes
0x180037848  mov     rcx, rbx
0x18003784b  mov     [rbp+var_18], r15
0x18003784f  mov     edi, r15d
0x180037852  mov     [rbp+arg_10], r15
0x180037856  mov     rax, [rax]
0x180037859  mov     [rbp+arg_18], r15d
0x18003785d  mov     [rbp+var_20], r15d
0x180037861  mov     [rbp+var_10], r15
0x180037865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003786a  mov     ebx, eax
0x18003786c  test    eax, eax
0x18003786e  jns     loc_1800378FF
0x180037874  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003787b  test    rcx, rcx
0x18003787e  jnz     short loc_1800378C1
0x180037880  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037886  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003788d  mov     rcx, rax
0x180037890  test    rax, rax
0x180037893  jz      short loc_1800378B3
0x180037895  mov     rax, [rax]
0x180037898  mov     edx, 7F0h
0x18003789d  mov     rax, [rax+8]
0x1800378a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800378a6  test    eax, eax
0x1800378a8  jz      short loc_1800378B3
0x1800378aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800378b1  jmp     short loc_1800378C1
0x1800378b3  lea     rcx, qword_180069A90; this
0x1800378ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800378c1  cmp     [rcx+8], r15b
0x1800378c5  jz      short loc_1800378E8
0x1800378c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800378cc  cmp     [rax+7CCh], ebx
0x1800378d2  jz      short loc_1800378E8
0x1800378d4  mov     r9d, ebx; int
0x1800378d7  mov     r8d, 5Ch ; '\'; int
0x1800378dd  mov     rdx, r12; char *
0x1800378e0  mov     rcx, rax; this
0x1800378e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800378e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800378ed  cmp     al, 1
0x1800378ef  jb      loc_180037DCA
0x1800378f5  mov     edx, 0Fh
0x1800378fa  jmp     loc_180037DAC
0x1800378ff  lea     r8, [rbp+arg_10]; struct IMFAttributes **
0x180037903  mov     rdx, rsi; struct IMFMediaType *
0x180037906  mov     rcx, r14; struct IMFAttributes *
0x180037909  call    ?GetMFTActivateCodecAPIAttributes@CMFTHelper@@CAJPEAUIMFAttributes@@PEAUIMFMediaType@@PEAPEAU2@@Z; CMFTHelper::GetMFTActivateCodecAPIAttributes(IMFAttributes *,IMFMediaType *,IMFAttributes * *)
0x18003790e  mov     ebx, eax
0x180037910  test    eax, eax
0x180037912  jns     loc_1800379C1
0x180037918  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003791f  test    rcx, rcx
0x180037922  jnz     short loc_180037965
0x180037924  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003792a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037931  mov     rcx, rax
0x180037934  test    rax, rax
0x180037937  jz      short loc_180037957
0x180037939  mov     rax, [rax]
0x18003793c  mov     edx, 7F0h
0x180037941  mov     rax, [rax+8]
0x180037945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003794a  test    eax, eax
0x18003794c  jz      short loc_180037957
0x18003794e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037955  jmp     short loc_180037965
0x180037957  lea     rcx, qword_180069A90; this
0x18003795e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037965  cmp     [rcx+8], r15b
0x180037969  jz      short loc_18003798C
0x18003796b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037970  cmp     [rax+7CCh], ebx
0x180037976  jz      short loc_18003798C
0x180037978  mov     r9d, ebx; int
0x18003797b  mov     r8d, 61h ; 'a'; int
0x180037981  mov     rdx, r12; char *
0x180037984  mov     rcx, rax; this
0x180037987  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003798c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037991  cmp     al, 1
0x180037993  jb      short loc_1800379B8
0x180037995  mov     rcx, cs:WPP_GLOBAL_Control
0x18003799c  lea     r8, WPP_51ca0e26e9bc306247403b211e8b86d4_Traceguids
0x1800379a3  mov     edx, 10h
0x1800379a8  mov     [rsp+50h+var_30], ebx
0x1800379ac  xor     r9d, r9d
0x1800379af  mov     rcx, [rcx+10h]
0x1800379b3  call    WPP_SF_qd
0x1800379b8  mov     rdi, [rbp+arg_10]
0x1800379bc  jmp     loc_180037DCA
0x1800379c1  mov     rdi, [rbp+arg_10]
0x1800379c5  test    rdi, rdi
0x1800379c8  jz      loc_180037B35
0x1800379ce  mov     rax, [rdi]
0x1800379d1  lea     rdx, [rbp+arg_18]
0x1800379d5  mov     rcx, rdi
0x1800379d8  mov     rax, [rax+0F0h]
0x1800379df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800379e4  mov     ebx, eax
0x1800379e6  test    eax, eax
0x1800379e8  jns     loc_180037A79
0x1800379ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800379f5  test    rcx, rcx
0x1800379f8  jnz     short loc_180037A3B
0x1800379fa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037a00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037a07  mov     rcx, rax
0x180037a0a  test    rax, rax
0x180037a0d  jz      short loc_180037A2D
0x180037a0f  mov     rax, [rax]
0x180037a12  mov     edx, 7F0h
0x180037a17  mov     rax, [rax+8]
0x180037a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037a20  test    eax, eax
0x180037a22  jz      short loc_180037A2D
0x180037a24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037a2b  jmp     short loc_180037A3B
0x180037a2d  lea     rcx, qword_180069A90; this
0x180037a34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037a3b  cmp     [rcx+8], r15b
0x180037a3f  jz      short loc_180037A62
0x180037a41  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037a46  cmp     [rax+7CCh], ebx
0x180037a4c  jz      short loc_180037A62
0x180037a4e  mov     r9d, ebx; int
0x180037a51  mov     r8d, 64h ; 'd'; int
0x180037a57  mov     rdx, r12; char *
0x180037a5a  mov     rcx, rax; this
0x180037a5d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037a62  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037a67  cmp     al, 1
0x180037a69  jb      loc_180037DCA
0x180037a6f  mov     edx, 11h
0x180037a74  jmp     loc_180037DAC
0x180037a79  cmp     [rbp+arg_18], r15d
0x180037a7d  jz      loc_180037B35
0x180037a83  mov     rcx, [rbp+var_18]
0x180037a87  lea     rdx, MFT_PREFERRED_ENCODER_PROFILE
0x180037a8e  mov     r8, rdi
0x180037a91  mov     rax, [rcx]
0x180037a94  mov     rax, [rax+0D8h]
0x180037a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037aa0  mov     ebx, eax
0x180037aa2  test    eax, eax
0x180037aa4  jns     loc_180037B35
0x180037aaa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ab1  test    rcx, rcx
0x180037ab4  jnz     short loc_180037AF7
0x180037ab6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037abc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ac3  mov     rcx, rax
0x180037ac6  test    rax, rax
0x180037ac9  jz      short loc_180037AE9
0x180037acb  mov     rax, [rax]
0x180037ace  mov     edx, 7F0h
0x180037ad3  mov     rax, [rax+8]
0x180037ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037adc  test    eax, eax
0x180037ade  jz      short loc_180037AE9
0x180037ae0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037ae7  jmp     short loc_180037AF7
0x180037ae9  lea     rcx, qword_180069A90; this
0x180037af0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037af7  cmp     [rcx+8], r15b
0x180037afb  jz      short loc_180037B1E
0x180037afd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037b02  cmp     [rax+7CCh], ebx
0x180037b08  jz      short loc_180037B1E
0x180037b0a  mov     r9d, ebx; int
0x180037b0d  mov     r8d, 68h ; 'h'; int
0x180037b13  mov     rdx, r12; char *
0x180037b16  mov     rcx, rax; this
0x180037b19  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037b1e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037b23  cmp     al, 1
0x180037b25  jb      loc_180037DCA
0x180037b2b  mov     edx, 12h
0x180037b30  jmp     loc_180037DAC
0x180037b35  test    rsi, rsi
0x180037b38  jz      loc_180037CA9
0x180037b3e  mov     rax, [rsi]
0x180037b41  lea     rdx, [rbp+arg_18]
0x180037b45  mov     rcx, rsi
0x180037b48  mov     [rbp+arg_18], r15d
0x180037b4c  mov     rax, [rax+0F0h]
0x180037b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b58  mov     ebx, eax
0x180037b5a  test    eax, eax
0x180037b5c  jns     loc_180037BED
0x180037b62  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b69  test    rcx, rcx
0x180037b6c  jnz     short loc_180037BAF
0x180037b6e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037b74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b7b  mov     rcx, rax
0x180037b7e  test    rax, rax
0x180037b81  jz      short loc_180037BA1
0x180037b83  mov     rax, [rax]
0x180037b86  mov     edx, 7F0h
0x180037b8b  mov     rax, [rax+8]
0x180037b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037b94  test    eax, eax
0x180037b96  jz      short loc_180037BA1
0x180037b98  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037b9f  jmp     short loc_180037BAF
0x180037ba1  lea     rcx, qword_180069A90; this
0x180037ba8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037baf  cmp     [rcx+8], r15b
0x180037bb3  jz      short loc_180037BD6
0x180037bb5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037bba  cmp     [rax+7CCh], ebx
0x180037bc0  jz      short loc_180037BD6
0x180037bc2  mov     r9d, ebx; int
0x180037bc5  mov     r8d, 72h ; 'r'; int
0x180037bcb  mov     rdx, r12; char *
0x180037bce  mov     rcx, rax; this
0x180037bd1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037bd6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037bdb  cmp     al, 1
0x180037bdd  jb      loc_180037DCA
0x180037be3  mov     edx, 13h
0x180037be8  jmp     loc_180037DAC
0x180037bed  cmp     [rbp+arg_18], r15d
0x180037bf1  jz      loc_180037CA9
0x180037bf7  mov     rcx, [rbp+var_18]
0x180037bfb  lea     rdx, MFT_PREFERRED_OUTPUTTYPE_Attribute
0x180037c02  mov     r8, rsi
0x180037c05  mov     rax, [rcx]
0x180037c08  mov     rax, [rax+0D8h]
0x180037c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c14  mov     ebx, eax
0x180037c16  test    eax, eax
0x180037c18  jns     loc_180037CA9
0x180037c1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c25  test    rcx, rcx
0x180037c28  jnz     short loc_180037C6B
0x180037c2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180037c30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c37  mov     rcx, rax
0x180037c3a  test    rax, rax
0x180037c3d  jz      short loc_180037C5D
0x180037c3f  mov     rax, [rax]
0x180037c42  mov     edx, 7F0h
0x180037c47  mov     rax, [rax+8]
0x180037c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c50  test    eax, eax
0x180037c52  jz      short loc_180037C5D
0x180037c54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c5b  jmp     short loc_180037C6B
0x180037c5d  lea     rcx, qword_180069A90; this
0x180037c64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180037c6b  cmp     [rcx+8], r15b
0x180037c6f  jz      short loc_180037C92
0x180037c71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180037c76  cmp     [rax+7CCh], ebx
0x180037c7c  jz      short loc_180037C92
0x180037c7e  mov     r9d, ebx; int
0x180037c81  mov     r8d, 75h ; 'u'; int
0x180037c87  mov     rdx, r12; char *
0x180037c8a  mov     rcx, rax; this
0x180037c8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180037c92  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180037c97  cmp     al, 1
0x180037c99  jb      loc_180037DCA
0x180037c9f  mov     edx, 14h
0x180037ca4  jmp     loc_180037DAC
0x180037ca9  mov     rax, [r14]
0x180037cac  lea     r9, [rbp+var_10]
0x180037cb0  lea     r8, IID_IUnknown
0x180037cb7  mov     rcx, r14
0x180037cba  lea     rdx, MFT_FIELDOFUSE_UNLOCK_Attribute
0x180037cc1  mov     rax, [rax+88h]
0x180037cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ccd  test    eax, eax
0x180037ccf  js      loc_180037DCA
0x180037cd5  mov     rcx, [rbp+var_18]
0x180037cd9  lea     r8, [rbp+var_20]
  ... truncated ...
```
