# CTranscodeManager::Init(IMFTranscodeConfigPriv *)

- ea: `0x180035b70`
- end: `0x18003611b`
- name: `?Init@CTranscodeManager@@UEAAJPEAUIMFTranscodeConfigPriv@@@Z`
- size: `1451`
- prototype: `__int64 __fastcall(CTranscodeManager *__hidden this, struct IMFTranscodeConfigPriv *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180035460`
- `0x180035b70`
- `0x18003618c`
- `0x18003b8cc`
- `0x18003efa0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035bd7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035cb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035eb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035f52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003600e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035bd7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035cb8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035d60`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035e08`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035eb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180035f52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003600e`

## pseudocode

```c
__int64 __fastcall CTranscodeManager::Init(CTranscodeManager *this, struct IMFTranscodeConfigPriv *a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  int TopoBuilder; // ebx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 *v19; // rcx
  CallStackTracing *v20; // rax
  struct CallStackContext *v21; // rax
  __int64 v22; // rdx
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  __int64 v30; // rdx
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFTopology *v35; // [rsp+30h] [rbp-30h] BYREF
  struct IMFMediaSource *v36; // [rsp+38h] [rbp-28h] BYREF
  CTranscodeTopoBuilder *v37; // [rsp+40h] [rbp-20h] BYREF
  struct IMFByteStream *v38; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int16 *v39; // [rsp+50h] [rbp-10h] BYREF
  char v40; // [rsp+A0h] [rbp+40h] BYREF
  struct IMFTranscodeProfile *v41; // [rsp+A8h] [rbp+48h] BYREF

  v36 = 0;
  v39 = 0;
  v38 = 0;
  v41 = 0;
  v35 = 0;
  v37 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v40, "CTranscodeManager::Init", 626);
  if ( a2 )
  {
    CTranscodeManager::Reset(this);
    *((_QWORD *)this + 2) = a2;
    (*(void (__fastcall **)(struct IMFTranscodeConfigPriv *))(*(_QWORD *)a2 + 8LL))(a2);
    TopoBuilder = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, struct IMFMediaSource **))(*(_QWORD *)a2 + 32LL))(
                    a2,
                    &v36);
    if ( TopoBuilder >= 0 )
    {
      TopoBuilder = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, struct IMFByteStream **))(*(_QWORD *)a2 + 64LL))(
                      a2,
                      &v38);
      if ( TopoBuilder >= 0 )
      {
        TopoBuilder = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, unsigned __int16 **))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        &v39);
        if ( TopoBuilder >= 0 )
        {
          TopoBuilder = (*(__int64 (__fastcall **)(struct IMFTranscodeConfigPriv *, struct IMFTranscodeProfile **))(*(_QWORD *)a2 + 80LL))(
                          a2,
                          &v41);
          if ( TopoBuilder >= 0 )
          {
            TopoBuilder = CTranscodeTopoBuilder::GetTopoBuilder(v41, &v37);
            if ( TopoBuilder >= 0 )
            {
              TopoBuilder = CTranscodeTopoBuilder::Build(v37, (OLECHAR *)v36, v39, (OLECHAR *)v38, v41, &v35);
              if ( TopoBuilder >= 0 )
              {
                *((_QWORD *)this + 3) = v35;
                v35 = 0;
              }
              else
              {
                v31 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
                  CallStackTracing::s_wpInstance = v32;
                  if ( v32
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                  {
                    v31 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v31 = &qword_180069A90;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                  }
                }
                if ( *((_BYTE *)v31 + 8) )
                {
                  ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v31);
                  if ( *((_DWORD *)ThreadRelativeContext + 499) != TopoBuilder )
                    CallStackContext::TraceFailure(ThreadRelativeContext, "CTranscodeManager::Init", 639, TopoBuilder);
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v9 = 76;
                  goto LABEL_12;
                }
              }
            }
            else
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
                CallStackTracing::s_wpInstance = v28;
                if ( v28
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                {
                  v27 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v27 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v27 + 8) )
              {
                v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
                if ( *((_DWORD *)v29 + 499) != TopoBuilder )
                  CallStackContext::TraceFailure(v29, "CTranscodeManager::Init", 638, TopoBuilder);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 75;
                goto LABEL_12;
              }
            }
          }
          else
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
              CallStackTracing::s_wpInstance = v24;
              if ( v24
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v23 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
              if ( *((_DWORD *)v25 + 499) != TopoBuilder )
                CallStackContext::TraceFailure(v25, "CTranscodeManager::Init", 636, TopoBuilder);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 74;
              goto LABEL_12;
            }
          }
        }
        else
        {
          v19 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18);
            CallStackTracing::s_wpInstance = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v19 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v19);
            if ( *((_DWORD *)v21 + 499) != TopoBuilder )
              CallStackContext::TraceFailure(v21, "CTranscodeManager::Init", 635, TopoBuilder);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 73;
            goto LABEL_12;
          }
        }
      }
      else
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != TopoBuilder )
            CallStackContext::TraceFailure(v17, "CTranscodeManager::Init", 634, TopoBuilder);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 72;
          goto LABEL_12;
        }
      }
    }
    else
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
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
        v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v13 + 499) != TopoBuilder )
          CallStackContext::TraceFailure(v13, "CTranscodeManager::Init", 633, TopoBuilder);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 71;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    TopoBuilder = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v8 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v8, "CTranscodeManager::Init", 627, -2147467261);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 70;
LABEL_12:
      WPP_SF_qd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids,
        this,
        TopoBuilder);
    }
  }
  if ( v36 )
  {
    ((void (__fastcall *)(struct IMFMediaSource *))v36->lpVtbl->Release)(v36);
    v36 = 0;
  }
  if ( v41 )
  {
    ((void (__fastcall *)(struct IMFTranscodeProfile *))v41->lpVtbl->Release)(v41);
    v41 = 0;
  }
  if ( v35 )
  {
    ((void (__fastcall *)(struct IMFTopology *))v35->lpVtbl->Release)(v35);
    v35 = 0;
  }
  if ( v37 )
    CTranscodeTopoBuilder::`scalar deleting destructor'(v37, 1u);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v40);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>((__int64 *)&v38);
  return (unsigned int)TopoBuilder;
}

```

## disassembly

```asm
0x180035b70  mov     [rsp-28h+arg_0], rbx
0x180035b75  push    rbp
0x180035b76  push    rsi
0x180035b77  push    rdi
0x180035b78  push    r12
0x180035b7a  push    r14
0x180035b7c  mov     rbp, rsp
0x180035b7f  sub     rsp, 60h
0x180035b83  xor     r14d, r14d
0x180035b86  lea     r12, aCtranscodemana; "CTranscodeManager::Init"
0x180035b8d  mov     rdi, rdx
0x180035b90  mov     [rbp+var_28], r14
0x180035b94  mov     rsi, rcx
0x180035b97  mov     [rbp+var_10], r14
0x180035b9b  mov     rdx, r12; char *
0x180035b9e  mov     [rbp+var_18], r14
0x180035ba2  mov     r8d, 272h; int
0x180035ba8  mov     [rbp+arg_18], r14
0x180035bac  lea     rcx, [rbp+arg_10]; this
0x180035bb0  mov     [rbp+var_30], r14
0x180035bb4  mov     [rbp+var_20], r14
0x180035bb8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180035bbd  test    rdi, rdi
0x180035bc0  jnz     loc_180035C74
0x180035bc6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035bcd  mov     ebx, 80004003h
0x180035bd2  test    rcx, rcx
0x180035bd5  jnz     short loc_180035C18
0x180035bd7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035bdd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035be4  mov     rcx, rax
0x180035be7  test    rax, rax
0x180035bea  jz      short loc_180035C0A
0x180035bec  mov     rax, [rax]
0x180035bef  mov     edx, 7F0h
0x180035bf4  mov     rax, [rax+8]
0x180035bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bfd  test    eax, eax
0x180035bff  jz      short loc_180035C0A
0x180035c01  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035c08  jmp     short loc_180035C18
0x180035c0a  lea     rcx, qword_180069A90; this
0x180035c11  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035c18  cmp     [rcx+8], r14b
0x180035c1c  jz      short loc_180035C3F
0x180035c1e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035c23  cmp     [rax+7CCh], ebx
0x180035c29  jz      short loc_180035C3F
0x180035c2b  mov     r9d, ebx; int
0x180035c2e  mov     r8d, 273h; int
0x180035c34  mov     rdx, r12; char *
0x180035c37  mov     rcx, rax; this
0x180035c3a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035c3f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035c44  cmp     al, 1
0x180035c46  jb      loc_180036095
0x180035c4c  mov     edx, 46h ; 'F'
0x180035c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180035c58  lea     r8, WPP_ac9e624cc7b93371a829705ad5fff251_Traceguids
0x180035c5f  mov     r9, rsi
0x180035c62  mov     dword ptr [rsp+60h+var_40], ebx
0x180035c66  mov     rcx, [rcx+10h]
0x180035c6a  call    WPP_SF_qd
0x180035c6f  jmp     loc_180036095
0x180035c74  mov     rcx, rsi; this
0x180035c77  call    ?Reset@CTranscodeManager@@AEAAXXZ; CTranscodeManager::Reset(void)
0x180035c7c  mov     [rsi+10h], rdi
0x180035c80  mov     rcx, rdi
0x180035c83  mov     rax, [rdi]
0x180035c86  mov     rax, [rax+8]
0x180035c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035c8f  mov     rax, [rdi]
0x180035c92  lea     rdx, [rbp+var_28]
0x180035c96  mov     rcx, rdi
0x180035c99  mov     rax, [rax+20h]
0x180035c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ca2  mov     ebx, eax
0x180035ca4  test    eax, eax
0x180035ca6  jns     loc_180035D37
0x180035cac  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035cb3  test    rcx, rcx
0x180035cb6  jnz     short loc_180035CF9
0x180035cb8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035cbe  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035cc5  mov     rcx, rax
0x180035cc8  test    rax, rax
0x180035ccb  jz      short loc_180035CEB
0x180035ccd  mov     rax, [rax]
0x180035cd0  mov     edx, 7F0h
0x180035cd5  mov     rax, [rax+8]
0x180035cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035cde  test    eax, eax
0x180035ce0  jz      short loc_180035CEB
0x180035ce2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ce9  jmp     short loc_180035CF9
0x180035ceb  lea     rcx, qword_180069A90; this
0x180035cf2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035cf9  cmp     [rcx+8], r14b
0x180035cfd  jz      short loc_180035D20
0x180035cff  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035d04  cmp     [rax+7CCh], ebx
0x180035d0a  jz      short loc_180035D20
0x180035d0c  mov     r9d, ebx; int
0x180035d0f  mov     r8d, 279h; int
0x180035d15  mov     rdx, r12; char *
0x180035d18  mov     rcx, rax; this
0x180035d1b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035d20  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035d25  cmp     al, 1
0x180035d27  jb      loc_180036095
0x180035d2d  mov     edx, 47h ; 'G'
0x180035d32  jmp     loc_180035C51
0x180035d37  mov     rax, [rdi]
0x180035d3a  lea     rdx, [rbp+var_18]
0x180035d3e  mov     rcx, rdi
0x180035d41  mov     rax, [rax+40h]
0x180035d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d4a  mov     ebx, eax
0x180035d4c  test    eax, eax
0x180035d4e  jns     loc_180035DDF
0x180035d54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035d5b  test    rcx, rcx
0x180035d5e  jnz     short loc_180035DA1
0x180035d60  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035d66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035d6d  mov     rcx, rax
0x180035d70  test    rax, rax
0x180035d73  jz      short loc_180035D93
0x180035d75  mov     rax, [rax]
0x180035d78  mov     edx, 7F0h
0x180035d7d  mov     rax, [rax+8]
0x180035d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d86  test    eax, eax
0x180035d88  jz      short loc_180035D93
0x180035d8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035d91  jmp     short loc_180035DA1
0x180035d93  lea     rcx, qword_180069A90; this
0x180035d9a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035da1  cmp     [rcx+8], r14b
0x180035da5  jz      short loc_180035DC8
0x180035da7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035dac  cmp     [rax+7CCh], ebx
0x180035db2  jz      short loc_180035DC8
0x180035db4  mov     r9d, ebx; int
0x180035db7  mov     r8d, 27Ah; int
0x180035dbd  mov     rdx, r12; char *
0x180035dc0  mov     rcx, rax; this
0x180035dc3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035dc8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035dcd  cmp     al, 1
0x180035dcf  jb      loc_180036095
0x180035dd5  mov     edx, 48h ; 'H'
0x180035dda  jmp     loc_180035C51
0x180035ddf  mov     rax, [rdi]
0x180035de2  lea     rdx, [rbp+var_10]
0x180035de6  mov     rcx, rdi
0x180035de9  mov     rax, [rax+30h]
0x180035ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035df2  mov     ebx, eax
0x180035df4  test    eax, eax
0x180035df6  jns     loc_180035E87
0x180035dfc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e03  test    rcx, rcx
0x180035e06  jnz     short loc_180035E49
0x180035e08  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035e0e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e15  mov     rcx, rax
0x180035e18  test    rax, rax
0x180035e1b  jz      short loc_180035E3B
0x180035e1d  mov     rax, [rax]
0x180035e20  mov     edx, 7F0h
0x180035e25  mov     rax, [rax+8]
0x180035e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e2e  test    eax, eax
0x180035e30  jz      short loc_180035E3B
0x180035e32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e39  jmp     short loc_180035E49
0x180035e3b  lea     rcx, qword_180069A90; this
0x180035e42  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035e49  cmp     [rcx+8], r14b
0x180035e4d  jz      short loc_180035E70
0x180035e4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035e54  cmp     [rax+7CCh], ebx
0x180035e5a  jz      short loc_180035E70
0x180035e5c  mov     r9d, ebx; int
0x180035e5f  mov     r8d, 27Bh; int
0x180035e65  mov     rdx, r12; char *
0x180035e68  mov     rcx, rax; this
0x180035e6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035e70  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035e75  cmp     al, 1
0x180035e77  jb      loc_180036095
0x180035e7d  mov     edx, 49h ; 'I'
0x180035e82  jmp     loc_180035C51
0x180035e87  mov     rax, [rdi]
0x180035e8a  lea     rdx, [rbp+arg_18]
0x180035e8e  mov     rcx, rdi
0x180035e91  mov     rax, [rax+50h]
0x180035e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e9a  mov     ebx, eax
0x180035e9c  test    eax, eax
0x180035e9e  jns     loc_180035F2F
0x180035ea4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035eab  test    rcx, rcx
0x180035eae  jnz     short loc_180035EF1
0x180035eb0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035eb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ebd  mov     rcx, rax
0x180035ec0  test    rax, rax
0x180035ec3  jz      short loc_180035EE3
0x180035ec5  mov     rax, [rax]
0x180035ec8  mov     edx, 7F0h
0x180035ecd  mov     rax, [rax+8]
0x180035ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ed6  test    eax, eax
0x180035ed8  jz      short loc_180035EE3
0x180035eda  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ee1  jmp     short loc_180035EF1
0x180035ee3  lea     rcx, qword_180069A90; this
0x180035eea  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035ef1  cmp     [rcx+8], r14b
0x180035ef5  jz      short loc_180035F18
0x180035ef7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035efc  cmp     [rax+7CCh], ebx
0x180035f02  jz      short loc_180035F18
0x180035f04  mov     r9d, ebx; int
0x180035f07  mov     r8d, 27Ch; int
0x180035f0d  mov     rdx, r12; char *
0x180035f10  mov     rcx, rax; this
0x180035f13  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035f18  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035f1d  cmp     al, 1
0x180035f1f  jb      loc_180036095
0x180035f25  mov     edx, 4Ah ; 'J'
0x180035f2a  jmp     loc_180035C51
0x180035f2f  mov     rcx, [rbp+arg_18]; struct IMFTranscodeProfile *
0x180035f33  lea     rdx, [rbp+var_20]; struct CTranscodeTopoBuilder **
0x180035f37  call    ?GetTopoBuilder@CTranscodeTopoBuilder@@SAJPEAUIMFTranscodeProfile@@PEAPEAV1@@Z; CTranscodeTopoBuilder::GetTopoBuilder(IMFTranscodeProfile *,CTranscodeTopoBuilder * *)
0x180035f3c  mov     ebx, eax
0x180035f3e  test    eax, eax
0x180035f40  jns     loc_180035FD1
0x180035f46  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f4d  test    rcx, rcx
0x180035f50  jnz     short loc_180035F93
0x180035f52  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180035f58  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f5f  mov     rcx, rax
0x180035f62  test    rax, rax
0x180035f65  jz      short loc_180035F85
0x180035f67  mov     rax, [rax]
0x180035f6a  mov     edx, 7F0h
0x180035f6f  mov     rax, [rax+8]
0x180035f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f78  test    eax, eax
0x180035f7a  jz      short loc_180035F85
0x180035f7c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f83  jmp     short loc_180035F93
0x180035f85  lea     rcx, qword_180069A90; this
0x180035f8c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180035f93  cmp     [rcx+8], r14b
0x180035f97  jz      short loc_180035FBA
0x180035f99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180035f9e  cmp     [rax+7CCh], ebx
0x180035fa4  jz      short loc_180035FBA
0x180035fa6  mov     r9d, ebx; int
0x180035fa9  mov     r8d, 27Eh; int
0x180035faf  mov     rdx, r12; char *
0x180035fb2  mov     rcx, rax; this
0x180035fb5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180035fba  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180035fbf  cmp     al, 1
0x180035fc1  jb      loc_180036095
0x180035fc7  mov     edx, 4Bh ; 'K'
0x180035fcc  jmp     loc_180035C51
0x180035fd1  mov     rax, [rbp+arg_18]
0x180035fd5  lea     rcx, [rbp+var_30]
0x180035fd9  mov     r9, [rbp+var_18]; struct IMFByteStream *
0x180035fdd  mov     r8, [rbp+var_10]; unsigned __int16 *
0x180035fe1  mov     rdx, [rbp+var_28]; struct IMFMediaSource *
0x180035fe5  mov     [rsp+60h+var_38], rcx; struct IMFTopology **
0x180035fea  mov     rcx, [rbp+var_20]; this
0x180035fee  mov     [rsp+60h+var_40], rax; struct IMFTranscodeProfile *
0x180035ff3  call    ?Build@CTranscodeTopoBuilder@@QEAAJPEAUIMFMediaSource@@PEBGPEAUIMFByteStream@@PEAUIMFTranscodeProfile@@PEAPEAUIMFTopology@@@Z; CTranscodeTopoBuilder::Build(IMFMediaSource *,ushort const *,IMFByteStream *,IMFTranscodeProfile *,IMFTopology * *)
0x180035ff8  mov     ebx, eax
0x180035ffa  test    eax, eax
0x180035ffc  jns     loc_180036089
0x180036002  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180036009  test    rcx, rcx
0x18003600c  jnz     short loc_18003604F
0x18003600e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180036014  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003601b  mov     rcx, rax
0x18003601e  test    rax, rax
0x180036021  jz      short loc_180036041
0x180036023  mov     rax, [rax]
0x180036026  mov     edx, 7F0h
0x18003602b  mov     rax, [rax+8]
0x18003602f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036034  test    eax, eax
0x180036036  jz      short loc_180036041
  ... truncated ...
```
