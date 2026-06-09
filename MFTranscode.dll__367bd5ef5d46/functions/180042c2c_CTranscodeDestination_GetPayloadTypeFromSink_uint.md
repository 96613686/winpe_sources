# CTranscodeDestination::GetPayloadTypeFromSink(uint *)

- ea: `0x180042c2c`
- end: `0x1800430e3`
- name: `?GetPayloadTypeFromSink@CTranscodeDestination@@IEAAJPEAI@Z`
- size: `1207`
- prototype: `__int64 __fastcall(CTranscodeDestination *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800405d0`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180042c2c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042f66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043015`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042c97`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042d46`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042df6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042e9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180042f66`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180043015`

## string_xrefs

- `0x180042c50`: `CTranscodeDestination::GetPayloadTypeFromSink`

## pseudocode

```c
__int64 __fastcall CTranscodeDestination::GetPayloadTypeFromSink(CTranscodeDestination *this, unsigned int *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 *v6; // rcx
  int v7; // ebx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
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
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v32; // [rsp+30h] [rbp-10h] BYREF
  __int64 v33; // [rsp+38h] [rbp-8h] BYREF
  char v34; // [rsp+70h] [rbp+30h] BYREF
  __int64 v35; // [rsp+80h] [rbp+40h] BYREF
  __int64 v36; // [rsp+88h] [rbp+48h] BYREF

  v33 = 0;
  v32 = 0;
  v36 = 0;
  v35 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v34,
    "CTranscodeDestination::GetPayloadTypeFromSink",
    269);
  v5 = *((_QWORD *)this + 7);
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v5 + 264LL))(
           v5,
           &GUID_6ef2a660_47c0_4666_b13d_cbb717f2fa2c,
           &v33);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 64LL))(
             v33,
             *(unsigned int *)(*((_QWORD *)this + 8) + 16LL),
             &v32);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 72LL))(v32, &v36);
        if ( v7 >= 0 )
        {
          if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v36 + 56LL))(v36, &v35) >= 0
            || (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v36 + 40LL))(v36, 0, &v35),
                v7 >= 0) )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, unsigned int *))(*(_QWORD *)v35 + 56LL))(
                   v35,
                   &MF_MT_AAC_PAYLOAD_TYPE,
                   a2);
            if ( v7 < 0 )
            {
              v28 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
                CallStackTracing::s_wpInstance = v29;
                if ( v29
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
                {
                  v28 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v28 = &qword_180069A90;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
                }
              }
              if ( *((_BYTE *)v28 + 8) )
              {
                ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
                if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
                  CallStackContext::TraceFailure(
                    ThreadRelativeContext,
                    "CTranscodeDestination::GetPayloadTypeFromSink",
                    278,
                    v7);
              }
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 45;
                goto LABEL_68;
              }
            }
          }
          else
          {
            v24 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
              CallStackTracing::s_wpInstance = v25;
              if ( v25
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
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
              if ( *((_DWORD *)v26 + 499) != v7 )
                CallStackContext::TraceFailure(v26, "CTranscodeDestination::GetPayloadTypeFromSink", 275, v7);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v10 = 44;
              goto LABEL_68;
            }
          }
        }
        else
        {
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
            if ( *((_DWORD *)v22 + 499) != v7 )
              CallStackContext::TraceFailure(v22, "CTranscodeDestination::GetPayloadTypeFromSink", 272, v7);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v10 = 43;
            goto LABEL_68;
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
          if ( *((_DWORD *)v18 + 499) != v7 )
            CallStackContext::TraceFailure(v18, "CTranscodeDestination::GetPayloadTypeFromSink", 271, v7);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 42;
          goto LABEL_68;
        }
      }
    }
    else
    {
      v12 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
        CallStackTracing::s_wpInstance = v13;
        if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
        {
          v12 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v12 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v12 + 8) )
      {
        v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
        if ( *((_DWORD *)v14 + 499) != v7 )
          CallStackContext::TraceFailure(v14, "CTranscodeDestination::GetPayloadTypeFromSink", 270, v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 41;
        goto LABEL_68;
      }
    }
  }
  else
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    v7 = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v4);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v9 + 499) != -2147418113 )
        CallStackContext::TraceFailure(v9, "CTranscodeDestination::GetPayloadTypeFromSink", 269, -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 40;
LABEL_68:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids, this, v7);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v34);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v35);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v36);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v32);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180042c2c  push    rbp
0x180042c2e  push    rbx
0x180042c2f  push    rsi
0x180042c30  push    rdi
0x180042c31  push    r15
0x180042c33  mov     rbp, rsp
0x180042c36  sub     rsp, 40h
0x180042c3a  mov     rsi, rdx
0x180042c3d  mov     [rbp+var_8], 0
0x180042c45  mov     rdi, rcx
0x180042c48  mov     [rbp+var_10], 0
0x180042c50  lea     r15, aCtranscodedest_3; "CTranscodeDestination::GetPayloadTypeFr"...
0x180042c57  mov     [rbp+arg_18], 0
0x180042c5f  mov     rdx, r15; char *
0x180042c62  mov     [rbp+arg_10], 0
0x180042c6a  mov     r8d, 10Dh; int
0x180042c70  lea     rcx, [rbp+arg_0]; this
0x180042c74  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180042c79  mov     rcx, [rdi+38h]
0x180042c7d  test    rcx, rcx
0x180042c80  jnz     loc_180042D16
0x180042c86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042c8d  mov     ebx, 8000FFFFh
0x180042c92  test    rcx, rcx
0x180042c95  jnz     short loc_180042CD8
0x180042c97  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042c9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ca4  mov     rcx, rax
0x180042ca7  test    rax, rax
0x180042caa  jz      short loc_180042CCA
0x180042cac  mov     rax, [rax]
0x180042caf  mov     edx, 7F0h
0x180042cb4  mov     rax, [rax+8]
0x180042cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cbd  test    eax, eax
0x180042cbf  jz      short loc_180042CCA
0x180042cc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cc8  jmp     short loc_180042CD8
0x180042cca  lea     rcx, qword_180069A90; this
0x180042cd1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042cd8  cmp     byte ptr [rcx+8], 0
0x180042cdc  jz      short loc_180042CFF
0x180042cde  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042ce3  cmp     [rax+7CCh], ebx
0x180042ce9  jz      short loc_180042CFF
0x180042ceb  mov     r9d, ebx; int
0x180042cee  mov     r8d, 10Dh; int
0x180042cf4  mov     rdx, r15; char *
0x180042cf7  mov     rcx, rax; this
0x180042cfa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042cff  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042d04  cmp     al, 1
0x180042d06  jb      loc_1800430A9
0x180042d0c  mov     edx, 28h ; '('
0x180042d11  jmp     loc_18004308B
0x180042d16  mov     rax, [rcx]
0x180042d19  lea     r8, [rbp+var_8]
0x180042d1d  lea     rdx, _GUID_6ef2a660_47c0_4666_b13d_cbb717f2fa2c
0x180042d24  mov     rax, [rax+108h]
0x180042d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d30  mov     ebx, eax
0x180042d32  test    eax, eax
0x180042d34  jns     loc_180042DC5
0x180042d3a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d41  test    rcx, rcx
0x180042d44  jnz     short loc_180042D87
0x180042d46  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042d4c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d53  mov     rcx, rax
0x180042d56  test    rax, rax
0x180042d59  jz      short loc_180042D79
0x180042d5b  mov     rax, [rax]
0x180042d5e  mov     edx, 7F0h
0x180042d63  mov     rax, [rax+8]
0x180042d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d6c  test    eax, eax
0x180042d6e  jz      short loc_180042D79
0x180042d70  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d77  jmp     short loc_180042D87
0x180042d79  lea     rcx, qword_180069A90; this
0x180042d80  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042d87  cmp     byte ptr [rcx+8], 0
0x180042d8b  jz      short loc_180042DAE
0x180042d8d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042d92  cmp     [rax+7CCh], ebx
0x180042d98  jz      short loc_180042DAE
0x180042d9a  mov     r9d, ebx; int
0x180042d9d  mov     r8d, 10Eh; int
0x180042da3  mov     rdx, r15; char *
0x180042da6  mov     rcx, rax; this
0x180042da9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042dae  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042db3  cmp     al, 1
0x180042db5  jb      loc_1800430A9
0x180042dbb  mov     edx, 29h ; ')'
0x180042dc0  jmp     loc_18004308B
0x180042dc5  mov     rcx, [rbp+var_8]
0x180042dc9  lea     r8, [rbp+var_10]
0x180042dcd  mov     rdx, [rdi+40h]
0x180042dd1  mov     rax, [rcx]
0x180042dd4  mov     edx, [rdx+10h]
0x180042dd7  mov     rax, [rax+40h]
0x180042ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042de0  mov     ebx, eax
0x180042de2  test    eax, eax
0x180042de4  jns     loc_180042E75
0x180042dea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042df1  test    rcx, rcx
0x180042df4  jnz     short loc_180042E37
0x180042df6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042dfc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e03  mov     rcx, rax
0x180042e06  test    rax, rax
0x180042e09  jz      short loc_180042E29
0x180042e0b  mov     rax, [rax]
0x180042e0e  mov     edx, 7F0h
0x180042e13  mov     rax, [rax+8]
0x180042e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e1c  test    eax, eax
0x180042e1e  jz      short loc_180042E29
0x180042e20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e27  jmp     short loc_180042E37
0x180042e29  lea     rcx, qword_180069A90; this
0x180042e30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e37  cmp     byte ptr [rcx+8], 0
0x180042e3b  jz      short loc_180042E5E
0x180042e3d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042e42  cmp     [rax+7CCh], ebx
0x180042e48  jz      short loc_180042E5E
0x180042e4a  mov     r9d, ebx; int
0x180042e4d  mov     r8d, 10Fh; int
0x180042e53  mov     rdx, r15; char *
0x180042e56  mov     rcx, rax; this
0x180042e59  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042e5e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042e63  cmp     al, 1
0x180042e65  jb      loc_1800430A9
0x180042e6b  mov     edx, 2Ah ; '*'
0x180042e70  jmp     loc_18004308B
0x180042e75  mov     rcx, [rbp+var_10]
0x180042e79  lea     rdx, [rbp+arg_18]
0x180042e7d  mov     rax, [rcx]
0x180042e80  mov     rax, [rax+48h]
0x180042e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e89  mov     ebx, eax
0x180042e8b  test    eax, eax
0x180042e8d  jns     loc_180042F1E
0x180042e93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042e9a  test    rcx, rcx
0x180042e9d  jnz     short loc_180042EE0
0x180042e9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042ea5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042eac  mov     rcx, rax
0x180042eaf  test    rax, rax
0x180042eb2  jz      short loc_180042ED2
0x180042eb4  mov     rax, [rax]
0x180042eb7  mov     edx, 7F0h
0x180042ebc  mov     rax, [rax+8]
0x180042ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ec5  test    eax, eax
0x180042ec7  jz      short loc_180042ED2
0x180042ec9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ed0  jmp     short loc_180042EE0
0x180042ed2  lea     rcx, qword_180069A90; this
0x180042ed9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042ee0  cmp     byte ptr [rcx+8], 0
0x180042ee4  jz      short loc_180042F07
0x180042ee6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042eeb  cmp     [rax+7CCh], ebx
0x180042ef1  jz      short loc_180042F07
0x180042ef3  mov     r9d, ebx; int
0x180042ef6  mov     r8d, 110h; int
0x180042efc  mov     rdx, r15; char *
0x180042eff  mov     rcx, rax; this
0x180042f02  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042f07  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042f0c  cmp     al, 1
0x180042f0e  jb      loc_1800430A9
0x180042f14  mov     edx, 2Bh ; '+'
0x180042f19  jmp     loc_18004308B
0x180042f1e  mov     rcx, [rbp+arg_18]
0x180042f22  lea     rdx, [rbp+arg_10]
0x180042f26  mov     rax, [rcx]
0x180042f29  mov     rax, [rax+38h]
0x180042f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f32  test    eax, eax
0x180042f34  jns     loc_180042FE5
0x180042f3a  mov     rcx, [rbp+arg_18]
0x180042f3e  lea     r8, [rbp+arg_10]
0x180042f42  xor     edx, edx
0x180042f44  mov     rax, [rcx]
0x180042f47  mov     rax, [rax+28h]
0x180042f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f50  mov     ebx, eax
0x180042f52  test    eax, eax
0x180042f54  jns     loc_180042FE5
0x180042f5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f61  test    rcx, rcx
0x180042f64  jnz     short loc_180042FA7
0x180042f66  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180042f6c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f73  mov     rcx, rax
0x180042f76  test    rax, rax
0x180042f79  jz      short loc_180042F99
0x180042f7b  mov     rax, [rax]
0x180042f7e  mov     edx, 7F0h
0x180042f83  mov     rax, [rax+8]
0x180042f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f8c  test    eax, eax
0x180042f8e  jz      short loc_180042F99
0x180042f90  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180042f97  jmp     short loc_180042FA7
0x180042f99  lea     rcx, qword_180069A90; this
0x180042fa0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180042fa7  cmp     byte ptr [rcx+8], 0
0x180042fab  jz      short loc_180042FCE
0x180042fad  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180042fb2  cmp     [rax+7CCh], ebx
0x180042fb8  jz      short loc_180042FCE
0x180042fba  mov     r9d, ebx; int
0x180042fbd  mov     r8d, 113h; int
0x180042fc3  mov     rdx, r15; char *
0x180042fc6  mov     rcx, rax; this
0x180042fc9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180042fce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042fd3  cmp     al, 1
0x180042fd5  jb      loc_1800430A9
0x180042fdb  mov     edx, 2Ch ; ','
0x180042fe0  jmp     loc_18004308B
0x180042fe5  mov     rcx, [rbp+arg_10]
0x180042fe9  lea     rdx, MF_MT_AAC_PAYLOAD_TYPE
0x180042ff0  mov     r8, rsi
0x180042ff3  mov     rax, [rcx]
0x180042ff6  mov     rax, [rax+38h]
0x180042ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042fff  mov     ebx, eax
0x180043001  test    eax, eax
0x180043003  jns     loc_1800430A9
0x180043009  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043010  test    rcx, rcx
0x180043013  jnz     short loc_180043056
0x180043015  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004301b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180043022  mov     rcx, rax
0x180043025  test    rax, rax
0x180043028  jz      short loc_180043048
0x18004302a  mov     rax, [rax]
0x18004302d  mov     edx, 7F0h
0x180043032  mov     rax, [rax+8]
0x180043036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004303b  test    eax, eax
0x18004303d  jz      short loc_180043048
0x18004303f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180043046  jmp     short loc_180043056
0x180043048  lea     rcx, qword_180069A90; this
0x18004304f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180043056  cmp     byte ptr [rcx+8], 0
0x18004305a  jz      short loc_18004307D
0x18004305c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180043061  cmp     [rax+7CCh], ebx
0x180043067  jz      short loc_18004307D
0x180043069  mov     r9d, ebx; int
0x18004306c  mov     r8d, 116h; int
0x180043072  mov     rdx, r15; char *
0x180043075  mov     rcx, rax; this
0x180043078  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004307d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180043082  cmp     al, 1
0x180043084  jb      short loc_1800430A9
0x180043086  mov     edx, 2Dh ; '-'
0x18004308b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043092  lea     r8, WPP_82ede244afe43de52d63f347cb6083ad_Traceguids
0x180043099  mov     r9, rdi
0x18004309c  mov     [rsp+40h+var_20], ebx
0x1800430a0  mov     rcx, [rcx+10h]
0x1800430a4  call    WPP_SF_qd
0x1800430a9  lea     rcx, [rbp+arg_0]; this
0x1800430ad  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800430b2  lea     rcx, [rbp+arg_10]
0x1800430b6  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800430bb  lea     rcx, [rbp+arg_18]
0x1800430bf  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800430c4  lea     rcx, [rbp+var_10]
0x1800430c8  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800430cd  lea     rcx, [rbp+var_8]
0x1800430d1  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800430d6  mov     eax, ebx
0x1800430d8  add     rsp, 40h
0x1800430dc  pop     r15
0x1800430de  pop     rdi
0x1800430df  pop     rsi
0x1800430e0  pop     rbx
0x1800430e1  pop     rbp
0x1800430e2  retn
```
