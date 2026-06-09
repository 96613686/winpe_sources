# CDShowStream::NewSample(IMFSample *,_AMMediaType *,IMFMediaType *)

- ea: `0x180095ff8`
- end: `0x18009670a`
- name: `?NewSample@CDShowStream@@QEAAJPEAUIMFSample@@PEAU_AMMediaType@@PEAUIMFMediaType@@@Z`
- size: `1810`
- prototype: `__int64 __fastcall(CDShowStream *__hidden this, struct IMFSample *, struct _AMMediaType *pvRepresentation, struct IMFMediaType *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005bb20`
- `0x18006f980`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x1800227e0`
- `0x180032a50`
- `0x180041d8c`
- `0x18004f17c`
- `0x180051ce4`
- `0x18005a940`
- `0x18006affc`
- `0x180095ff8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800966d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800966d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096038`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096038`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096067`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800961f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800962ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009635e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096420`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800964ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009662d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096067`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096131`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800961f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800962ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009635e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096420`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800964ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180096586`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18009662d`
- `MFPlat!MFCreateMediaTypeFromRepresentation` at `0x18009610f`
- `MFPlat!MFCreateMediaTypeFromRepresentation` at `0x18009610f`
- `MFPlat!MFCreateMediaType` at `0x18009628a`
- `MFPlat!MFCreateMediaType` at `0x18009628a`

## pseudocode

```c
__int64 __fastcall CDShowStream::NewSample(
        CDShowStream *this,
        struct IMFSample *a2,
        struct _AMMediaType *pvRepresentation,
        struct IMFMediaType *a4)
{
  CallStackTracing *v8; // rcx
  HRESULT v9; // ebx
  CallStackTracing *v10; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rcx
  CallStackTracing *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  CallStackTracing *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  CallStackTracing *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  CallStackTracing *v26; // rcx
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  CallStackTracing *v32; // rcx
  CallStackTracing *v33; // rax
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  IMFMediaType *ppIMediaType[2]; // [rsp+30h] [rbp-48h] BYREF
  GUID guidRepresentation; // [rsp+40h] [rbp-38h] BYREF
  char v41; // [rsp+80h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "CDShowStream::NewSample", 905);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  ppIMediaType[0] = 0;
  if ( *((_DWORD *)this + 16) )
  {
    v8 = CallStackTracing::s_wpInstance;
    v9 = -1072873851;
    if ( !CallStackTracing::s_wpInstance )
    {
      v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v10;
      if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
      {
        v8 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873851 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowStream::NewSample", 910, -1072873851);
    }
    if ( g_wppLevels )
    {
      v12 = 90;
LABEL_106:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_abd0ed20453839f73f9a0958a5c12f4e_Traceguids, this, v9);
      goto LABEL_107;
    }
    goto LABEL_107;
  }
  if ( !pvRepresentation )
  {
    if ( !a4 )
      goto LABEL_72;
    v9 = MFCreateMediaType(ppIMediaType);
    if ( v9 < 0 )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext(v20);
        if ( *((_DWORD *)v22 + 499) != v9 )
          CallStackContext::TraceFailure(v22, "CDShowStream::NewSample", 937, v9);
      }
      if ( g_wppLevels )
      {
        v12 = 94;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
    v9 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a4->lpVtbl->CopyAllItems)(a4, ppIMediaType[0]);
    if ( v9 < 0 )
    {
      v23 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v23 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = CallStackTracing::GetThreadRelativeContext(v23);
        if ( *((_DWORD *)v25 + 499) != v9 )
          CallStackContext::TraceFailure(v25, "CDShowStream::NewSample", 938, v9);
      }
      if ( g_wppLevels )
      {
        v12 = 95;
        goto LABEL_106;
      }
      goto LABEL_107;
    }
LABEL_60:
    if ( ppIMediaType[0] )
    {
      v9 = ((__int64 (__fastcall *)(struct IMFSample *, GUID *))a2->lpVtbl->SetUnknown)(a2, &CLSID_DS_NewMT);
      if ( v9 < 0 )
      {
        v26 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v26 + 8) )
        {
          v28 = CallStackTracing::GetThreadRelativeContext(v26);
          if ( *((_DWORD *)v28 + 499) != v9 )
            CallStackContext::TraceFailure(v28, "CDShowStream::NewSample", 943, v9);
        }
        if ( g_wppLevels )
        {
          v12 = 96;
          goto LABEL_106;
        }
        goto LABEL_107;
      }
    }
LABEL_72:
    v9 = CSampleRequestQueue::NewSample(*((CSampleRequestQueue **)this + 18), a2);
    if ( v9 >= 0 )
    {
      if ( *(_DWORD *)(*((_QWORD *)this + 18) + 464LL) > *(_DWORD *)(*((_QWORD *)this + 18) + 912LL)
        || (v9 = CDShowStream::StopPullingSamples(this), v9 >= 0) )
      {
        v9 = CSampleRequestQueue::FillRequests(*((CSampleRequestQueue **)this + 18));
        if ( v9 < 0 )
        {
          v35 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v36;
            if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
            {
              v35 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v35 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v35 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext(v35);
            if ( *((_DWORD *)v37 + 499) != v9 )
              CallStackContext::TraceFailure(v37, "CDShowStream::NewSample", 953, v9);
          }
          if ( g_wppLevels )
          {
            v12 = 99;
            goto LABEL_106;
          }
        }
      }
      else
      {
        v32 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v33;
          if ( v33 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
          {
            v32 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v32 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v32 + 8) )
        {
          v34 = CallStackTracing::GetThreadRelativeContext(v32);
          if ( *((_DWORD *)v34 + 499) != v9 )
            CallStackContext::TraceFailure(v34, "CDShowStream::NewSample", 950, v9);
        }
        if ( g_wppLevels )
        {
          v12 = 98;
          goto LABEL_106;
        }
      }
    }
    else
    {
      v29 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v29 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v29 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v29 + 8) )
      {
        v31 = CallStackTracing::GetThreadRelativeContext(v29);
        if ( *((_DWORD *)v31 + 499) != v9 )
          CallStackContext::TraceFailure(v31, "CDShowStream::NewSample", 946, v9);
      }
      if ( g_wppLevels )
      {
        v12 = 97;
        goto LABEL_106;
      }
    }
    goto LABEL_107;
  }
  guidRepresentation = AM_MEDIA_TYPE_REPRESENTATION;
  v9 = MFCreateMediaTypeFromRepresentation(&guidRepresentation, pvRepresentation, ppIMediaType);
  if ( v9 >= 0 )
  {
    v16 = *((_QWORD *)this + 14);
    if ( v16 != -184 && *(int *)(v16 + 216) > 0 )
    {
      v9 = MediaSubTypeTransform(ppIMediaType[0]);
      if ( v9 < 0 )
      {
        v17 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          v19 = CallStackTracing::GetThreadRelativeContext(v17);
          if ( *((_DWORD *)v19 + 499) != v9 )
            CallStackContext::TraceFailure(v19, "CDShowStream::NewSample", 932, v9);
        }
        if ( g_wppLevels )
        {
          v12 = 93;
          goto LABEL_106;
        }
        goto LABEL_107;
      }
    }
    goto LABEL_60;
  }
  v13 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
    CallStackTracing::s_wpInstance = v14;
    if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
    {
      v13 = CallStackTracing::s_wpInstance;
    }
    else
    {
      v13 = (CallStackTracing *)&qword_1800EB130;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
    }
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext(v13);
    if ( *((_DWORD *)v15 + 499) != v9 )
      CallStackContext::TraceFailure(v15, "CDShowStream::NewSample", 928, v9);
  }
  if ( g_wppLevels )
  {
    v12 = 92;
    goto LABEL_106;
  }
LABEL_107:
  ATL::CComPtrBase<IMediaSeeking>::~CComPtrBase<IMediaSeeking>(ppIMediaType);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180095ff8  mov     rax, rsp
0x180095ffb  mov     [rax+10h], rbx
0x180095fff  mov     [rax+18h], rbp
0x180096003  push    rsi
0x180096004  push    rdi
0x180096005  push    r12
0x180096007  push    r14
0x180096009  push    r15
0x18009600b  sub     rsp, 50h
0x18009600f  mov     rbx, r8
0x180096012  lea     r12, aCdshowstreamNe; "CDShowStream::NewSample"
0x180096019  mov     r14, rdx
0x18009601c  mov     rdi, rcx
0x18009601f  mov     rdx, r12; char *
0x180096022  lea     rcx, [rax+8]; this
0x180096026  mov     r8d, 389h; int
0x18009602c  mov     rsi, r9
0x18009602f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180096034  lea     rcx, [rdi+18h]; lpCriticalSection
0x180096038  call    cs:__imp_EnterCriticalSection
0x18009603f  nop     dword ptr [rax+rax+00h]
0x180096044  xor     r15d, r15d
0x180096047  mov     [rsp+78h+ppIMediaType], r15
0x18009604c  cmp     [rdi+40h], r15d
0x180096050  jz      loc_1800960EC
0x180096056  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009605d  mov     ebx, 0C00D3E85h
0x180096062  test    rcx, rcx
0x180096065  jnz     short loc_1800960AE
0x180096067  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18009606e  nop     dword ptr [rax+rax+00h]
0x180096073  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009607a  mov     rcx, rax
0x18009607d  test    rax, rax
0x180096080  jz      short loc_1800960A0
0x180096082  mov     rax, [rax]
0x180096085  mov     edx, 7F0h
0x18009608a  mov     rax, [rax+8]
0x18009608e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096093  test    eax, eax
0x180096095  jz      short loc_1800960A0
0x180096097  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009609e  jmp     short loc_1800960AE
0x1800960a0  lea     rcx, qword_1800EB130; this
0x1800960a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800960ae  cmp     [rcx+8], r15b
0x1800960b2  jz      short loc_1800960D5
0x1800960b4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800960b9  cmp     [rax+7CCh], ebx
0x1800960bf  jz      short loc_1800960D5
0x1800960c1  mov     r9d, ebx; int
0x1800960c4  mov     r8d, 38Eh; int
0x1800960ca  mov     rdx, r12; char *
0x1800960cd  mov     rcx, rax; this
0x1800960d0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800960d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800960dc  jb      loc_1800966C7
0x1800960e2  mov     edx, 5Ah ; 'Z'
0x1800960e7  jmp     loc_1800966A9
0x1800960ec  test    rbx, rbx
0x1800960ef  jz      loc_18009627C
0x1800960f5  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x1800960fc  lea     r8, [rsp+78h+ppIMediaType]; ppIMediaType
0x180096101  mov     rdx, rbx; pvRepresentation
0x180096104  lea     rcx, [rsp+78h+guidRepresentation]; guidRepresentation
0x180096109  movdqu  xmmword ptr [rsp+78h+guidRepresentation.Data1], xmm0
0x18009610f  call    cs:__imp_MFCreateMediaTypeFromRepresentation
0x180096116  nop     dword ptr [rax+rax+00h]
0x18009611b  mov     ebx, eax
0x18009611d  test    eax, eax
0x18009611f  jns     loc_1800961B6
0x180096125  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009612c  test    rcx, rcx
0x18009612f  jnz     short loc_180096178
0x180096131  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096138  nop     dword ptr [rax+rax+00h]
0x18009613d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096144  mov     rcx, rax
0x180096147  test    rax, rax
0x18009614a  jz      short loc_18009616A
0x18009614c  mov     rax, [rax]
0x18009614f  mov     edx, 7F0h
0x180096154  mov     rax, [rax+8]
0x180096158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009615d  test    eax, eax
0x18009615f  jz      short loc_18009616A
0x180096161  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096168  jmp     short loc_180096178
0x18009616a  lea     rcx, qword_1800EB130; this
0x180096171  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180096178  cmp     [rcx+8], r15b
0x18009617c  jz      short loc_18009619F
0x18009617e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180096183  cmp     [rax+7CCh], ebx
0x180096189  jz      short loc_18009619F
0x18009618b  mov     r9d, ebx; int
0x18009618e  mov     r8d, 3A0h; int
0x180096194  mov     rdx, r12; char *
0x180096197  mov     rcx, rax; this
0x18009619a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009619f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800961a6  jb      loc_1800966C7
0x1800961ac  mov     edx, 5Ch ; '\'
0x1800961b1  jmp     loc_1800966A9
0x1800961b6  mov     rcx, [rdi+70h]
0x1800961ba  lea     rax, [rcx+0B8h]
0x1800961c1  test    rax, rax
0x1800961c4  jz      loc_1800963E3
0x1800961ca  cmp     [rcx+0D8h], r15d
0x1800961d1  jle     loc_1800963E3
0x1800961d7  mov     rcx, [rsp+78h+ppIMediaType]; struct IMFMediaType *
0x1800961dc  call    ?MediaSubTypeTransform@@YAJPEAUIMFMediaType@@@Z; MediaSubTypeTransform(IMFMediaType *)
0x1800961e1  mov     ebx, eax
0x1800961e3  test    eax, eax
0x1800961e5  jns     loc_1800963E3
0x1800961eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800961f2  test    rcx, rcx
0x1800961f5  jnz     short loc_18009623E
0x1800961f7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800961fe  nop     dword ptr [rax+rax+00h]
0x180096203  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18009620a  mov     rcx, rax
0x18009620d  test    rax, rax
0x180096210  jz      short loc_180096230
0x180096212  mov     rax, [rax]
0x180096215  mov     edx, 7F0h
0x18009621a  mov     rax, [rax+8]
0x18009621e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096223  test    eax, eax
0x180096225  jz      short loc_180096230
0x180096227  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009622e  jmp     short loc_18009623E
0x180096230  lea     rcx, qword_1800EB130; this
0x180096237  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18009623e  cmp     [rcx+8], r15b
0x180096242  jz      short loc_180096265
0x180096244  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180096249  cmp     [rax+7CCh], ebx
0x18009624f  jz      short loc_180096265
0x180096251  mov     r9d, ebx; int
0x180096254  mov     r8d, 3A4h; int
0x18009625a  mov     rdx, r12; char *
0x18009625d  mov     rcx, rax; this
0x180096260  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180096265  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18009626c  jb      loc_1800966C7
0x180096272  mov     edx, 5Dh ; ']'
0x180096277  jmp     loc_1800966A9
0x18009627c  test    rsi, rsi
0x18009627f  jz      loc_1800964A5
0x180096285  lea     rcx, [rsp+78h+ppIMediaType]; ppMFType
0x18009628a  call    cs:__imp_MFCreateMediaType
0x180096291  nop     dword ptr [rax+rax+00h]
0x180096296  mov     ebx, eax
0x180096298  test    eax, eax
0x18009629a  jns     loc_180096331
0x1800962a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800962a7  test    rcx, rcx
0x1800962aa  jnz     short loc_1800962F3
0x1800962ac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800962b3  nop     dword ptr [rax+rax+00h]
0x1800962b8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800962bf  mov     rcx, rax
0x1800962c2  test    rax, rax
0x1800962c5  jz      short loc_1800962E5
0x1800962c7  mov     rax, [rax]
0x1800962ca  mov     edx, 7F0h
0x1800962cf  mov     rax, [rax+8]
0x1800962d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962d8  test    eax, eax
0x1800962da  jz      short loc_1800962E5
0x1800962dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800962e3  jmp     short loc_1800962F3
0x1800962e5  lea     rcx, qword_1800EB130; this
0x1800962ec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800962f3  cmp     [rcx+8], r15b
0x1800962f7  jz      short loc_18009631A
0x1800962f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800962fe  cmp     [rax+7CCh], ebx
0x180096304  jz      short loc_18009631A
0x180096306  mov     r9d, ebx; int
0x180096309  mov     r8d, 3A9h; int
0x18009630f  mov     rdx, r12; char *
0x180096312  mov     rcx, rax; this
0x180096315  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009631a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096321  jb      loc_1800966C7
0x180096327  mov     edx, 5Eh ; '^'
0x18009632c  jmp     loc_1800966A9
0x180096331  mov     rax, [rsi]
0x180096334  mov     rcx, rsi
0x180096337  mov     rdx, [rsp+78h+ppIMediaType]
0x18009633c  mov     rax, [rax+100h]
0x180096343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096348  mov     ebx, eax
0x18009634a  test    eax, eax
0x18009634c  jns     loc_1800963E3
0x180096352  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096359  test    rcx, rcx
0x18009635c  jnz     short loc_1800963A5
0x18009635e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096365  nop     dword ptr [rax+rax+00h]
0x18009636a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096371  mov     rcx, rax
0x180096374  test    rax, rax
0x180096377  jz      short loc_180096397
0x180096379  mov     rax, [rax]
0x18009637c  mov     edx, 7F0h
0x180096381  mov     rax, [rax+8]
0x180096385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009638a  test    eax, eax
0x18009638c  jz      short loc_180096397
0x18009638e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096395  jmp     short loc_1800963A5
0x180096397  lea     rcx, qword_1800EB130; this
0x18009639e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800963a5  cmp     [rcx+8], r15b
0x1800963a9  jz      short loc_1800963CC
0x1800963ab  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800963b0  cmp     [rax+7CCh], ebx
0x1800963b6  jz      short loc_1800963CC
0x1800963b8  mov     r9d, ebx; int
0x1800963bb  mov     r8d, 3AAh; int
0x1800963c1  mov     rdx, r12; char *
0x1800963c4  mov     rcx, rax; this
0x1800963c7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800963cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800963d3  jb      loc_1800966C7
0x1800963d9  mov     edx, 5Fh ; '_'
0x1800963de  jmp     loc_1800966A9
0x1800963e3  mov     r8, [rsp+78h+ppIMediaType]
0x1800963e8  test    r8, r8
0x1800963eb  jz      loc_1800964A5
0x1800963f1  mov     rax, [r14]
0x1800963f4  lea     rdx, CLSID_DS_NewMT
0x1800963fb  mov     rcx, r14
0x1800963fe  mov     rax, [rax+0D8h]
0x180096405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009640a  mov     ebx, eax
0x18009640c  test    eax, eax
0x18009640e  jns     loc_1800964A5
0x180096414  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18009641b  test    rcx, rcx
0x18009641e  jnz     short loc_180096467
0x180096420  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180096427  nop     dword ptr [rax+rax+00h]
0x18009642c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180096433  mov     rcx, rax
0x180096436  test    rax, rax
0x180096439  jz      short loc_180096459
0x18009643b  mov     rax, [rax]
0x18009643e  mov     edx, 7F0h
0x180096443  mov     rax, [rax+8]
0x180096447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009644c  test    eax, eax
0x18009644e  jz      short loc_180096459
0x180096450  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096457  jmp     short loc_180096467
0x180096459  lea     rcx, qword_1800EB130; this
0x180096460  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180096467  cmp     [rcx+8], r15b
0x18009646b  jz      short loc_18009648E
0x18009646d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180096472  cmp     [rax+7CCh], ebx
0x180096478  jz      short loc_18009648E
0x18009647a  mov     r9d, ebx; int
0x18009647d  mov     r8d, 3AFh; int
0x180096483  mov     rdx, r12; char *
0x180096486  mov     rcx, rax; this
0x180096489  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18009648e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180096495  jb      loc_1800966C7
0x18009649b  mov     edx, 60h ; '`'
0x1800964a0  jmp     loc_1800966A9
0x1800964a5  mov     rcx, [rdi+90h]; this
0x1800964ac  mov     rdx, r14; struct IMFSample *
0x1800964af  call    ?NewSample@CSampleRequestQueue@@QEAAJPEAUIMFSample@@@Z; CSampleRequestQueue::NewSample(IMFSample *)
0x1800964b4  mov     ebx, eax
0x1800964b6  test    eax, eax
0x1800964b8  jns     loc_18009654F
0x1800964be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800964c5  test    rcx, rcx
0x1800964c8  jnz     short loc_180096511
0x1800964ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800964d1  nop     dword ptr [rax+rax+00h]
0x1800964d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800964dd  mov     rcx, rax
0x1800964e0  test    rax, rax
0x1800964e3  jz      short loc_180096503
0x1800964e5  mov     rax, [rax]
0x1800964e8  mov     edx, 7F0h
0x1800964ed  mov     rax, [rax+8]
0x1800964f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800964f6  test    eax, eax
0x1800964f8  jz      short loc_180096503
0x1800964fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180096501  jmp     short loc_180096511
0x180096503  lea     rcx, qword_1800EB130; this
0x18009650a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180096511  cmp     [rcx+8], r15b
  ... truncated ...
```
