# CTranscodeSinkActivate::ActivateObject(_GUID const &,void * *)

- ea: `0x180031580`
- end: `0x180031a69`
- name: `?ActivateObject@CTranscodeSinkActivate@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1257`
- prototype: `__int64 __fastcall(CTranscodeSinkActivate *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000f05c`
- `0x18001a330`
- `0x18001c280`
- `0x180031580`
- `0x180031ff8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003163e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800316f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800317a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031847`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800318f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031980`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003163e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800316f4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800317a3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031847`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800318f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031980`
- `MFPlat!MFCreateFile` at `0x1800316d8`
- `MFPlat!MFCreateFile` at `0x1800316d8`

## pseudocode

```c
__int64 __fastcall CTranscodeSinkActivate::ActivateObject(
        CTranscodeSinkActivate *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  HRESULT MediaSink; // ebx
  __int64 *v10; // rcx
  CallStackTracing *v11; // rax
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  const WCHAR *v14; // rax
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
  struct CallStackContext *v30; // rax
  __int64 *v31; // rcx
  CallStackTracing *v32; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  IMFByteStream *ppIByteStream; // [rsp+30h] [rbp-10h] BYREF
  char v36; // [rsp+80h] [rbp+40h] BYREF
  struct IMFByteStream *v37; // [rsp+98h] [rbp+58h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v36, "CTranscodeSinkActivate::ActivateObject", 163);
  ppIByteStream = 0;
  v37 = 0;
  if ( !*((_QWORD *)this + 18) || (*((int *)this + 29) < 0 || !*((_DWORD *)this + 30)) && !*((_QWORD *)this + 17) )
  {
    v31 = (__int64 *)CallStackTracing::s_wpInstance;
    MediaSink = -2147418113;
    if ( !CallStackTracing::s_wpInstance )
    {
      v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v32;
      if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147418113 )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "CTranscodeSinkActivate::ActivateObject",
          172,
          -2147418113);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v13 = 18;
      goto LABEL_72;
    }
    goto LABEL_73;
  }
  if ( *((_QWORD *)this + 13) )
    goto LABEL_51;
  v7 = *((_QWORD *)this + 17);
  if ( v7 )
  {
    MediaSink = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct IMFByteStream **))(*(_QWORD *)v7 + 264LL))(
                  *((_QWORD *)this + 17),
                  &IID_IMFByteStream,
                  &v37);
    if ( MediaSink < 0 )
    {
      v10 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v11 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
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
        if ( *((_DWORD *)v12 + 499) != MediaSink )
          CallStackContext::TraceFailure(v12, "CTranscodeSinkActivate::ActivateObject", 179, MediaSink);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 19;
LABEL_72:
        WPP_SF_qd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids,
          this,
          MediaSink);
        goto LABEL_73;
      }
      goto LABEL_73;
    }
    goto LABEL_40;
  }
  v14 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents((char *)this + 112, v6);
  MediaSink = MFCreateFile(MF_ACCESSMODE_WRITE, MF_OPENMODE_DELETE_IF_EXIST, MF_FILEFLAGS_NONE, v14, &ppIByteStream);
  if ( MediaSink >= 0 )
  {
    MediaSink = ((__int64 (__fastcall *)(IMFByteStream *, GUID *, struct IMFByteStream **))ppIByteStream->lpVtbl->QueryInterface)(
                  ppIByteStream,
                  &IID_IMFByteStream,
                  &v37);
    if ( MediaSink < 0 )
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
        if ( *((_DWORD *)v22 + 499) != MediaSink )
          CallStackContext::TraceFailure(v22, "CTranscodeSinkActivate::ActivateObject", 192, MediaSink);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 21;
        goto LABEL_72;
      }
      goto LABEL_73;
    }
LABEL_40:
    MediaSink = CTranscodeSinkActivate::CreateMediaSink(this, v37, (struct IMFMediaSink **)this + 13);
    if ( MediaSink < 0 )
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
        if ( *((_DWORD *)v26 + 499) != MediaSink )
          CallStackContext::TraceFailure(v26, "CTranscodeSinkActivate::ActivateObject", 195, MediaSink);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 22;
        goto LABEL_72;
      }
      goto LABEL_73;
    }
LABEL_51:
    MediaSink = (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 13))(
                  *((_QWORD *)this + 13),
                  a2,
                  a3);
    if ( MediaSink < 0 )
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
        if ( *((_DWORD *)v30 + 499) != MediaSink )
          CallStackContext::TraceFailure(v30, "CTranscodeSinkActivate::ActivateObject", 198, MediaSink);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v13 = 23;
        goto LABEL_72;
      }
    }
    goto LABEL_73;
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
    if ( *((_DWORD *)v18 + 499) != MediaSink )
      CallStackContext::TraceFailure(v18, "CTranscodeSinkActivate::ActivateObject", 190, MediaSink);
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v13 = 20;
    goto LABEL_72;
  }
LABEL_73:
  if ( ppIByteStream )
  {
    ((void (__fastcall *)(IMFByteStream *))ppIByteStream->lpVtbl->Release)(ppIByteStream);
    ppIByteStream = 0;
  }
  if ( v37 )
  {
    ((void (__fastcall *)(struct IMFByteStream *))v37->lpVtbl->Release)(v37);
    v37 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v36);
  return (unsigned int)MediaSink;
}

```

## disassembly

```asm
0x180031580  mov     [rsp-38h+arg_8], rbx
0x180031585  push    rbp
0x180031586  push    rsi
0x180031587  push    rdi
0x180031588  push    r12
0x18003158a  push    r13
0x18003158c  push    r14
0x18003158e  push    r15
0x180031590  mov     rbp, rsp
0x180031593  sub     rsp, 40h
0x180031597  mov     r14, r8
0x18003159a  lea     r13, aCtranscodesink; "CTranscodeSinkActivate::ActivateObject"
0x1800315a1  mov     r15, rdx
0x1800315a4  mov     rdi, rcx
0x1800315a7  mov     rdx, r13; char *
0x1800315aa  lea     rcx, [rbp+arg_0]; this
0x1800315ae  mov     r8d, 0A3h; int
0x1800315b4  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800315b9  xor     r12d, r12d
0x1800315bc  mov     [rbp+var_10], r12
0x1800315c0  mov     [rbp+arg_18], r12
0x1800315c4  cmp     [rdi+90h], r12
0x1800315cb  jz      loc_18003196F
0x1800315d1  lea     rcx, [rdi+70h]
0x1800315d5  cmp     [rcx+4], r12d
0x1800315d9  jl      short loc_1800315E1
0x1800315db  cmp     [rcx+8], r12d
0x1800315df  jnz     short loc_1800315EE
0x1800315e1  cmp     [rdi+88h], r12
0x1800315e8  jz      loc_18003196F
0x1800315ee  lea     rsi, [rdi+68h]
0x1800315f2  cmp     [rsi], r12
0x1800315f5  jnz     loc_1800318C6
0x1800315fb  mov     r9, [rdi+88h]
0x180031602  test    r9, r9
0x180031605  jz      loc_1800316BD
0x18003160b  mov     rax, [r9]
0x18003160e  lea     r8, [rbp+arg_18]
0x180031612  lea     rdx, IID_IMFByteStream
0x180031619  mov     rcx, r9
0x18003161c  mov     rax, [rax+108h]
0x180031623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031628  mov     ebx, eax
0x18003162a  test    eax, eax
0x18003162c  jns     loc_180031822
0x180031632  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031639  test    rcx, rcx
0x18003163c  jnz     short loc_18003167F
0x18003163e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003164b  mov     rcx, rax
0x18003164e  test    rax, rax
0x180031651  jz      short loc_180031671
0x180031653  mov     rax, [rax]
0x180031656  mov     edx, 7F0h
0x18003165b  mov     rax, [rax+8]
0x18003165f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031664  test    eax, eax
0x180031666  jz      short loc_180031671
0x180031668  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003166f  jmp     short loc_18003167F
0x180031671  lea     rcx, qword_180069A90; this
0x180031678  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003167f  cmp     [rcx+8], r12b
0x180031683  jz      short loc_1800316A6
0x180031685  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003168a  cmp     [rax+7CCh], ebx
0x180031690  jz      short loc_1800316A6
0x180031692  mov     r9d, ebx; int
0x180031695  mov     r8d, 0B3h; int
0x18003169b  mov     rdx, r13; char *
0x18003169e  mov     rcx, rax; this
0x1800316a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800316a6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800316ab  cmp     al, 1
0x1800316ad  jb      loc_180031A14
0x1800316b3  mov     edx, 13h
0x1800316b8  jmp     loc_1800319F6
0x1800316bd  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x1800316c2  xor     r8d, r8d; fFlags
0x1800316c5  mov     r9, rax; pwszFileURL
0x1800316c8  lea     rax, [rbp+var_10]
0x1800316cc  mov     [rsp+40h+ppIByteStream], rax; ppIByteStream
0x1800316d1  lea     edx, [r8+4]; OpenMode
0x1800316d5  lea     ecx, [rdx-2]; AccessMode
0x1800316d8  call    cs:__imp_MFCreateFile
0x1800316de  mov     ebx, eax
0x1800316e0  test    eax, eax
0x1800316e2  jns     loc_180031773
0x1800316e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800316ef  test    rcx, rcx
0x1800316f2  jnz     short loc_180031735
0x1800316f4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800316fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031701  mov     rcx, rax
0x180031704  test    rax, rax
0x180031707  jz      short loc_180031727
0x180031709  mov     rax, [rax]
0x18003170c  mov     edx, 7F0h
0x180031711  mov     rax, [rax+8]
0x180031715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003171a  test    eax, eax
0x18003171c  jz      short loc_180031727
0x18003171e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031725  jmp     short loc_180031735
0x180031727  lea     rcx, qword_180069A90; this
0x18003172e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031735  cmp     [rcx+8], r12b
0x180031739  jz      short loc_18003175C
0x18003173b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031740  cmp     [rax+7CCh], ebx
0x180031746  jz      short loc_18003175C
0x180031748  mov     r9d, ebx; int
0x18003174b  mov     r8d, 0BEh; int
0x180031751  mov     rdx, r13; char *
0x180031754  mov     rcx, rax; this
0x180031757  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003175c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031761  cmp     al, 1
0x180031763  jb      loc_180031A14
0x180031769  mov     edx, 14h
0x18003176e  jmp     loc_1800319F6
0x180031773  mov     rcx, [rbp+var_10]
0x180031777  lea     r8, [rbp+arg_18]
0x18003177b  lea     rdx, IID_IMFByteStream
0x180031782  mov     rax, [rcx]
0x180031785  mov     rax, [rax]
0x180031788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003178d  mov     ebx, eax
0x18003178f  test    eax, eax
0x180031791  jns     loc_180031822
0x180031797  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003179e  test    rcx, rcx
0x1800317a1  jnz     short loc_1800317E4
0x1800317a3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800317a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800317b0  mov     rcx, rax
0x1800317b3  test    rax, rax
0x1800317b6  jz      short loc_1800317D6
0x1800317b8  mov     rax, [rax]
0x1800317bb  mov     edx, 7F0h
0x1800317c0  mov     rax, [rax+8]
0x1800317c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317c9  test    eax, eax
0x1800317cb  jz      short loc_1800317D6
0x1800317cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800317d4  jmp     short loc_1800317E4
0x1800317d6  lea     rcx, qword_180069A90; this
0x1800317dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800317e4  cmp     [rcx+8], r12b
0x1800317e8  jz      short loc_18003180B
0x1800317ea  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800317ef  cmp     [rax+7CCh], ebx
0x1800317f5  jz      short loc_18003180B
0x1800317f7  mov     r9d, ebx; int
0x1800317fa  mov     r8d, 0C0h; int
0x180031800  mov     rdx, r13; char *
0x180031803  mov     rcx, rax; this
0x180031806  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003180b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180031810  cmp     al, 1
0x180031812  jb      loc_180031A14
0x180031818  mov     edx, 15h
0x18003181d  jmp     loc_1800319F6
0x180031822  mov     rdx, [rbp+arg_18]; struct IMFByteStream *
0x180031826  mov     r8, rsi; struct IMFMediaSink **
0x180031829  mov     rcx, rdi; this
0x18003182c  call    ?CreateMediaSink@CTranscodeSinkActivate@@IEAAJPEAUIMFByteStream@@PEAPEAUIMFMediaSink@@@Z; CTranscodeSinkActivate::CreateMediaSink(IMFByteStream *,IMFMediaSink * *)
0x180031831  mov     ebx, eax
0x180031833  test    eax, eax
0x180031835  jns     loc_1800318C6
0x18003183b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031842  test    rcx, rcx
0x180031845  jnz     short loc_180031888
0x180031847  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003184d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031854  mov     rcx, rax
0x180031857  test    rax, rax
0x18003185a  jz      short loc_18003187A
0x18003185c  mov     rax, [rax]
0x18003185f  mov     edx, 7F0h
0x180031864  mov     rax, [rax+8]
0x180031868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003186d  test    eax, eax
0x18003186f  jz      short loc_18003187A
0x180031871  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031878  jmp     short loc_180031888
0x18003187a  lea     rcx, qword_180069A90; this
0x180031881  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031888  cmp     [rcx+8], r12b
0x18003188c  jz      short loc_1800318AF
0x18003188e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180031893  cmp     [rax+7CCh], ebx
0x180031899  jz      short loc_1800318AF
0x18003189b  mov     r9d, ebx; int
0x18003189e  mov     r8d, 0C3h; int
0x1800318a4  mov     rdx, r13; char *
0x1800318a7  mov     rcx, rax; this
0x1800318aa  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800318af  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800318b4  cmp     al, 1
0x1800318b6  jb      loc_180031A14
0x1800318bc  mov     edx, 16h
0x1800318c1  jmp     loc_1800319F6
0x1800318c6  mov     rcx, [rsi]
0x1800318c9  mov     r8, r14
0x1800318cc  mov     rdx, r15
0x1800318cf  mov     rax, [rcx]
0x1800318d2  mov     rax, [rax]
0x1800318d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318da  mov     ebx, eax
0x1800318dc  test    eax, eax
0x1800318de  jns     loc_180031A14
0x1800318e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800318eb  test    rcx, rcx
0x1800318ee  jnz     short loc_180031931
0x1800318f0  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800318f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800318fd  mov     rcx, rax
0x180031900  test    rax, rax
0x180031903  jz      short loc_180031923
0x180031905  mov     rax, [rax]
0x180031908  mov     edx, 7F0h
0x18003190d  mov     rax, [rax+8]
0x180031911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031916  test    eax, eax
0x180031918  jz      short loc_180031923
0x18003191a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031921  jmp     short loc_180031931
0x180031923  lea     rcx, qword_180069A90; this
0x18003192a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031931  cmp     [rcx+8], r12b
0x180031935  jz      short loc_180031958
0x180031937  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003193c  cmp     [rax+7CCh], ebx
0x180031942  jz      short loc_180031958
0x180031944  mov     r9d, ebx; int
0x180031947  mov     r8d, 0C6h; int
0x18003194d  mov     rdx, r13; char *
0x180031950  mov     rcx, rax; this
0x180031953  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180031958  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003195d  cmp     al, 1
0x18003195f  jb      loc_180031A14
0x180031965  mov     edx, 17h
0x18003196a  jmp     loc_1800319F6
0x18003196f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031976  mov     ebx, 8000FFFFh
0x18003197b  test    rcx, rcx
0x18003197e  jnz     short loc_1800319C1
0x180031980  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031986  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003198d  mov     rcx, rax
0x180031990  test    rax, rax
0x180031993  jz      short loc_1800319B3
0x180031995  mov     rax, [rax]
0x180031998  mov     edx, 7F0h
0x18003199d  mov     rax, [rax+8]
0x1800319a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319a6  test    eax, eax
0x1800319a8  jz      short loc_1800319B3
0x1800319aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800319b1  jmp     short loc_1800319C1
0x1800319b3  lea     rcx, qword_180069A90; this
0x1800319ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800319c1  cmp     [rcx+8], r12b
0x1800319c5  jz      short loc_1800319E8
0x1800319c7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800319cc  cmp     [rax+7CCh], ebx
0x1800319d2  jz      short loc_1800319E8
0x1800319d4  mov     r9d, ebx; int
0x1800319d7  mov     r8d, 0ACh; int
0x1800319dd  mov     rdx, r13; char *
0x1800319e0  mov     rcx, rax; this
0x1800319e3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800319e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800319ed  cmp     al, 1
0x1800319ef  jb      short loc_180031A14
0x1800319f1  mov     edx, 12h
0x1800319f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319fd  lea     r8, WPP_0da654d48b5e36d7c578bf5d8a78d05f_Traceguids
0x180031a04  mov     r9, rdi
0x180031a07  mov     dword ptr [rsp+40h+ppIByteStream], ebx
0x180031a0b  mov     rcx, [rcx+10h]
0x180031a0f  call    WPP_SF_qd
0x180031a14  mov     rcx, [rbp+var_10]
0x180031a18  test    rcx, rcx
0x180031a1b  jz      short loc_180031A2D
0x180031a1d  mov     rax, [rcx]
0x180031a20  mov     rax, [rax+10h]
0x180031a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a29  mov     [rbp+var_10], r12
0x180031a2d  mov     rcx, [rbp+arg_18]
0x180031a31  test    rcx, rcx
0x180031a34  jz      short loc_180031A46
0x180031a36  mov     rax, [rcx]
0x180031a39  mov     rax, [rax+10h]
0x180031a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a42  mov     [rbp+arg_18], r12
0x180031a46  lea     rcx, [rbp+arg_0]; this
  ... truncated ...
```
