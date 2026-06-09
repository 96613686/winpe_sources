# CTranscodeEngine::_UpdateProfileForContainer(_GUID,IMFMediaType *,IMFAttributes *)

- ea: `0x180030b04`
- end: `0x180031100`
- name: `?_UpdateProfileForContainer@CTranscodeEngine@@IEAAJU_GUID@@PEAUIMFMediaType@@PEAUIMFAttributes@@@Z`
- size: `1532`
- prototype: `int(CTranscodeEngine *__hidden this, struct _GUID *__struct_ptr, struct IMFMediaType *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000b41c`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800174c0`
- `0x18001a330`
- `0x18001c280`
- `0x180030b04`
- `0x18004f410`
- `0x1800594b0`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030ded`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030ec0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031044`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030b72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030c53`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030d20`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030ded`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030ec0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180030f6d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031044`

## string_xrefs

- `0x180030b47`: `CTranscodeEngine::_UpdateProfileForContainer`

## pseudocode

```c
__int64 __fastcall CTranscodeEngine::_UpdateProfileForContainer(
        CTranscodeEngine *this,
        struct _GUID *a2,
        struct IMFMediaType *a3,
        struct IMFAttributes *a4)
{
  int v8; // ebx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v23; // rdx
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 *v28; // rcx
  CallStackTracing *v29; // rax
  struct CallStackContext *v30; // rax
  __int64 v31; // rdx
  __int64 *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  __int64 v35; // rdx
  __int64 *v36; // rcx
  CallStackTracing *v37; // rax
  struct CallStackContext *v38; // rax
  _BYTE v40[4]; // [rsp+30h] [rbp-58h] BYREF
  int v41; // [rsp+34h] [rbp-54h] BYREF
  GUID Buf1; // [rsp+38h] [rbp-50h] BYREF

  if ( a3 && a4 )
    v8 = 0;
  else
    v8 = -2147024809;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v40,
    "CTranscodeEngine::_UpdateProfileForContainer",
    1240);
  if ( v8 >= 0 )
  {
    if ( memcmp_0(&MFTranscodeContainerType_MPEG4, a2, 0x10u) )
      goto LABEL_88;
    v41 = 0;
    lpVtbl = a4->lpVtbl;
    Buf1 = GUID_00000000_0000_0000_0000_000000000000;
    v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *))lpVtbl->GetGUID)(
           a4,
           &MF_MT_SUBTYPE,
           &Buf1);
    if ( v8 >= 0 )
    {
      if ( !memcmp_0(&Buf1, &MFVideoFormat_H264_ES, 0x10u) )
      {
        v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, const GUID *))a4->lpVtbl->SetGUID)(
               a4,
               &MF_MT_SUBTYPE,
               &MFVideoFormat_H264);
        if ( v8 < 0 )
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
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v8 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CTranscodeEngine::_UpdateProfileForContainer",
                1249,
                v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 144;
            goto LABEL_87;
          }
          goto LABEL_88;
        }
      }
      else if ( !memcmp_0(&Buf1, &MFVideoFormat_HEVC_ES, 0x10u) )
      {
        v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, const GUID *))a4->lpVtbl->SetGUID)(
               a4,
               &MF_MT_SUBTYPE,
               &MFVideoFormat_HEVC);
        if ( v8 < 0 )
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
            if ( *((_DWORD *)v26 + 499) != v8 )
              CallStackContext::TraceFailure(v26, "CTranscodeEngine::_UpdateProfileForContainer", 1253, v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 145;
            goto LABEL_87;
          }
          goto LABEL_88;
        }
      }
      if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, int *))a4->lpVtbl->GetUINT32)(
             a4,
             &MF_MT_AVG_BITRATE,
             &v41) < 0 )
      {
        v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, _QWORD))a4->lpVtbl->SetUINT32)(
               a4,
               &MF_MT_AVG_BITRATE,
               0);
        if ( v8 < 0 )
        {
          v28 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27);
            CallStackTracing::s_wpInstance = v29;
            if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
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
            v30 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v28);
            if ( *((_DWORD *)v30 + 499) != v8 )
              CallStackContext::TraceFailure(v30, "CTranscodeEngine::_UpdateProfileForContainer", 1260, v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 146;
            goto LABEL_87;
          }
          goto LABEL_88;
        }
        v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, _QWORD))a3->lpVtbl->SetUINT32)(
               a3,
               &MF_MT_AVG_BITRATE,
               0);
        if ( v8 < 0 )
        {
          v32 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v31);
            CallStackTracing::s_wpInstance = v33;
            if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
            {
              v32 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v32 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v32 + 8) )
          {
            v34 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v32);
            if ( *((_DWORD *)v34 + 499) != v8 )
              CallStackContext::TraceFailure(v34, "CTranscodeEngine::_UpdateProfileForContainer", 1261, v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 147;
            goto LABEL_87;
          }
          goto LABEL_88;
        }
      }
      if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, int *))a4->lpVtbl->GetUINT32)(
             a4,
             &MF_MT_INTERLACE_MODE,
             &v41) < 0 )
      {
        v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int64))a4->lpVtbl->SetUINT32)(
               a4,
               &MF_MT_INTERLACE_MODE,
               7);
        if ( v8 < 0 )
        {
          v36 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
            CallStackTracing::s_wpInstance = v37;
            if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
            {
              v36 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v36 = &qword_180069A90;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
            }
          }
          if ( *((_BYTE *)v36 + 8) )
          {
            v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v36);
            if ( *((_DWORD *)v38 + 499) != v8 )
              CallStackContext::TraceFailure(v38, "CTranscodeEngine::_UpdateProfileForContainer", 1268, v8);
          }
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v13 = 148;
            goto LABEL_87;
          }
        }
      }
      goto LABEL_88;
    }
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
      if ( *((_DWORD *)v18 + 499) != v8 )
        CallStackContext::TraceFailure(v18, "CTranscodeEngine::_UpdateProfileForContainer", 1246, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 143;
      goto LABEL_87;
    }
  }
  else
  {
    v10 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9);
      CallStackTracing::s_wpInstance = v11;
      if ( v11 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v11 + 8LL))(v11, 2032) )
      {
        v10 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v10 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v12 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v10);
      if ( *((_DWORD *)v12 + 499) != v8 )
        CallStackContext::TraceFailure(v12, "CTranscodeEngine::_UpdateProfileForContainer", 1240, v8);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 142;
LABEL_87:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_e568207c201a3850f272ae9c45155cdf_Traceguids, this, v8);
    }
  }
LABEL_88:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v40);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030b04  push    rbx
0x180030b06  push    rbp
0x180030b07  push    rsi
0x180030b08  push    rdi
0x180030b09  push    r12
0x180030b0b  push    r13
0x180030b0d  push    r14
0x180030b0f  sub     rsp, 50h
0x180030b13  mov     rax, cs:__security_cookie
0x180030b1a  xor     rax, rsp
0x180030b1d  mov     [rsp+88h+var_40], rax
0x180030b22  mov     rdi, r9
0x180030b25  mov     r14, r8
0x180030b28  mov     rbp, rdx
0x180030b2b  mov     rsi, rcx
0x180030b2e  test    r8, r8
0x180030b31  jz      short loc_180030B3C
0x180030b33  test    r9, r9
0x180030b36  jz      short loc_180030B3C
0x180030b38  xor     ebx, ebx
0x180030b3a  jmp     short loc_180030B41
0x180030b3c  mov     ebx, 80070057h
0x180030b41  mov     r13d, 4D8h
0x180030b47  lea     r12, aCtranscodeengi_11; "CTranscodeEngine::_UpdateProfileForCont"...
0x180030b4e  mov     r8d, r13d; int
0x180030b51  lea     rcx, [rsp+88h+var_58]; this
0x180030b56  mov     rdx, r12; char *
0x180030b59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180030b5e  test    ebx, ebx
0x180030b60  jns     loc_180030BEE
0x180030b66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030b6d  test    rcx, rcx
0x180030b70  jnz     short loc_180030BB3
0x180030b72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030b78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030b7f  mov     rcx, rax
0x180030b82  test    rax, rax
0x180030b85  jz      short loc_180030BA5
0x180030b87  mov     rax, [rax]
0x180030b8a  mov     edx, 7F0h
0x180030b8f  mov     rax, [rax+8]
0x180030b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b98  test    eax, eax
0x180030b9a  jz      short loc_180030BA5
0x180030b9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ba3  jmp     short loc_180030BB3
0x180030ba5  lea     rcx, qword_180069A90; this
0x180030bac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030bb3  cmp     byte ptr [rcx+8], 0
0x180030bb7  jz      short loc_180030BD7
0x180030bb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030bbe  cmp     [rax+7CCh], ebx
0x180030bc4  jz      short loc_180030BD7
0x180030bc6  mov     r9d, ebx; int
0x180030bc9  mov     r8d, r13d; int
0x180030bcc  mov     rdx, r12; char *
0x180030bcf  mov     rcx, rax; this
0x180030bd2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030bd7  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030bdc  cmp     al, 1
0x180030bde  jb      loc_1800310D8
0x180030be4  mov     edx, 8Eh
0x180030be9  jmp     loc_1800310BA
0x180030bee  mov     r13d, 10h
0x180030bf4  lea     rcx, MFTranscodeContainerType_MPEG4; Buf1
0x180030bfb  mov     r8d, r13d; Size
0x180030bfe  mov     rdx, rbp; Buf2
0x180030c01  call    memcmp_0
0x180030c06  test    eax, eax
0x180030c08  jnz     loc_1800310D8
0x180030c0e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180030c15  mov     [rsp+88h+var_54], eax
0x180030c19  lea     rbp, MF_MT_SUBTYPE
0x180030c20  mov     rax, [rdi]
0x180030c23  lea     r8, [rsp+88h+Buf1]
0x180030c28  mov     rdx, rbp
0x180030c2b  mov     rcx, rdi
0x180030c2e  movdqu  [rsp+88h+Buf1], xmm0
0x180030c34  mov     rax, [rax+50h]
0x180030c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c3d  mov     ebx, eax
0x180030c3f  test    eax, eax
0x180030c41  jns     loc_180030CD2
0x180030c47  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c4e  test    rcx, rcx
0x180030c51  jnz     short loc_180030C94
0x180030c53  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030c59  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c60  mov     rcx, rax
0x180030c63  test    rax, rax
0x180030c66  jz      short loc_180030C86
0x180030c68  mov     rax, [rax]
0x180030c6b  mov     edx, 7F0h
0x180030c70  mov     rax, [rax+8]
0x180030c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c79  test    eax, eax
0x180030c7b  jz      short loc_180030C86
0x180030c7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c84  jmp     short loc_180030C94
0x180030c86  lea     rcx, qword_180069A90; this
0x180030c8d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030c94  cmp     byte ptr [rcx+8], 0
0x180030c98  jz      short loc_180030CBB
0x180030c9a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030c9f  cmp     [rax+7CCh], ebx
0x180030ca5  jz      short loc_180030CBB
0x180030ca7  mov     r9d, ebx; int
0x180030caa  mov     r8d, 4DEh; int
0x180030cb0  mov     rdx, r12; char *
0x180030cb3  mov     rcx, rax; this
0x180030cb6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030cbb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030cc0  cmp     al, 1
0x180030cc2  jb      loc_1800310D8
0x180030cc8  mov     edx, 8Fh
0x180030ccd  jmp     loc_1800310BA
0x180030cd2  mov     r8, r13; Size
0x180030cd5  lea     rdx, MFVideoFormat_H264_ES; Buf2
0x180030cdc  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180030ce1  call    memcmp_0
0x180030ce6  test    eax, eax
0x180030ce8  jnz     loc_180030D9F
0x180030cee  mov     rax, [rdi]
0x180030cf1  lea     r8, MFVideoFormat_H264
0x180030cf8  mov     rdx, rbp
0x180030cfb  mov     rcx, rdi
0x180030cfe  mov     rax, [rax+0C0h]
0x180030d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d0a  mov     ebx, eax
0x180030d0c  test    eax, eax
0x180030d0e  jns     loc_180030E6C
0x180030d14  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d1b  test    rcx, rcx
0x180030d1e  jnz     short loc_180030D61
0x180030d20  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030d26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d2d  mov     rcx, rax
0x180030d30  test    rax, rax
0x180030d33  jz      short loc_180030D53
0x180030d35  mov     rax, [rax]
0x180030d38  mov     edx, 7F0h
0x180030d3d  mov     rax, [rax+8]
0x180030d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d46  test    eax, eax
0x180030d48  jz      short loc_180030D53
0x180030d4a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d51  jmp     short loc_180030D61
0x180030d53  lea     rcx, qword_180069A90; this
0x180030d5a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030d61  cmp     byte ptr [rcx+8], 0
0x180030d65  jz      short loc_180030D88
0x180030d67  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030d6c  cmp     [rax+7CCh], ebx
0x180030d72  jz      short loc_180030D88
0x180030d74  mov     r9d, ebx; int
0x180030d77  mov     r8d, 4E1h; int
0x180030d7d  mov     rdx, r12; char *
0x180030d80  mov     rcx, rax; this
0x180030d83  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030d88  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030d8d  cmp     al, 1
0x180030d8f  jb      loc_1800310D8
0x180030d95  mov     edx, 90h
0x180030d9a  jmp     loc_1800310BA
0x180030d9f  mov     r8, r13; Size
0x180030da2  lea     rdx, MFVideoFormat_HEVC_ES; Buf2
0x180030da9  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180030dae  call    memcmp_0
0x180030db3  test    eax, eax
0x180030db5  jnz     loc_180030E6C
0x180030dbb  mov     rax, [rdi]
0x180030dbe  lea     r8, MFVideoFormat_HEVC
0x180030dc5  mov     rdx, rbp
0x180030dc8  mov     rcx, rdi
0x180030dcb  mov     rax, [rax+0C0h]
0x180030dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030dd7  mov     ebx, eax
0x180030dd9  test    eax, eax
0x180030ddb  jns     loc_180030E6C
0x180030de1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030de8  test    rcx, rcx
0x180030deb  jnz     short loc_180030E2E
0x180030ded  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030df3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030dfa  mov     rcx, rax
0x180030dfd  test    rax, rax
0x180030e00  jz      short loc_180030E20
0x180030e02  mov     rax, [rax]
0x180030e05  mov     edx, 7F0h
0x180030e0a  mov     rax, [rax+8]
0x180030e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e13  test    eax, eax
0x180030e15  jz      short loc_180030E20
0x180030e17  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030e1e  jmp     short loc_180030E2E
0x180030e20  lea     rcx, qword_180069A90; this
0x180030e27  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030e2e  cmp     byte ptr [rcx+8], 0
0x180030e32  jz      short loc_180030E55
0x180030e34  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030e39  cmp     [rax+7CCh], ebx
0x180030e3f  jz      short loc_180030E55
0x180030e41  mov     r9d, ebx; int
0x180030e44  mov     r8d, 4E5h; int
0x180030e4a  mov     rdx, r12; char *
0x180030e4d  mov     rcx, rax; this
0x180030e50  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030e55  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030e5a  cmp     al, 1
0x180030e5c  jb      loc_1800310D8
0x180030e62  mov     edx, 91h
0x180030e67  jmp     loc_1800310BA
0x180030e6c  mov     rax, [rdi]
0x180030e6f  lea     rbp, MF_MT_AVG_BITRATE
0x180030e76  lea     r8, [rsp+88h+var_54]
0x180030e7b  mov     rdx, rbp
0x180030e7e  mov     rcx, rdi
0x180030e81  mov     rax, [rax+38h]
0x180030e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e8a  test    eax, eax
0x180030e8c  jns     loc_180030FEC
0x180030e92  mov     rax, [rdi]
0x180030e95  xor     r8d, r8d
0x180030e98  mov     rdx, rbp
0x180030e9b  mov     rcx, rdi
0x180030e9e  mov     rax, [rax+0A8h]
0x180030ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030eaa  mov     ebx, eax
0x180030eac  test    eax, eax
0x180030eae  jns     loc_180030F3F
0x180030eb4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ebb  test    rcx, rcx
0x180030ebe  jnz     short loc_180030F01
0x180030ec0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030ec6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ecd  mov     rcx, rax
0x180030ed0  test    rax, rax
0x180030ed3  jz      short loc_180030EF3
0x180030ed5  mov     rax, [rax]
0x180030ed8  mov     edx, 7F0h
0x180030edd  mov     rax, [rax+8]
0x180030ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ee6  test    eax, eax
0x180030ee8  jz      short loc_180030EF3
0x180030eea  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030ef1  jmp     short loc_180030F01
0x180030ef3  lea     rcx, qword_180069A90; this
0x180030efa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f01  cmp     byte ptr [rcx+8], 0
0x180030f05  jz      short loc_180030F28
0x180030f07  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030f0c  cmp     [rax+7CCh], ebx
0x180030f12  jz      short loc_180030F28
0x180030f14  mov     r9d, ebx; int
0x180030f17  mov     r8d, 4ECh; int
0x180030f1d  mov     rdx, r12; char *
0x180030f20  mov     rcx, rax; this
0x180030f23  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180030f28  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180030f2d  cmp     al, 1
0x180030f2f  jb      loc_1800310D8
0x180030f35  mov     edx, 92h
0x180030f3a  jmp     loc_1800310BA
0x180030f3f  mov     rax, [r14]
0x180030f42  xor     r8d, r8d
0x180030f45  mov     rdx, rbp
0x180030f48  mov     rcx, r14
0x180030f4b  mov     rax, [rax+0A8h]
0x180030f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f57  mov     ebx, eax
0x180030f59  test    eax, eax
0x180030f5b  jns     loc_180030FEC
0x180030f61  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f68  test    rcx, rcx
0x180030f6b  jnz     short loc_180030FAE
0x180030f6d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180030f73  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f7a  mov     rcx, rax
0x180030f7d  test    rax, rax
0x180030f80  jz      short loc_180030FA0
0x180030f82  mov     rax, [rax]
0x180030f85  mov     edx, 7F0h
0x180030f8a  mov     rax, [rax+8]
0x180030f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f93  test    eax, eax
0x180030f95  jz      short loc_180030FA0
0x180030f97  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180030f9e  jmp     short loc_180030FAE
0x180030fa0  lea     rcx, qword_180069A90; this
0x180030fa7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180030fae  cmp     byte ptr [rcx+8], 0
0x180030fb2  jz      short loc_180030FD5
0x180030fb4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180030fb9  cmp     [rax+7CCh], ebx
0x180030fbf  jz      short loc_180030FD5
0x180030fc1  mov     r9d, ebx; int
0x180030fc4  mov     r8d, 4EDh; int
0x180030fca  mov     rdx, r12; char *
0x180030fcd  mov     rcx, rax; this
0x180030fd0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
